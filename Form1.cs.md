namespace TCDD.TemelOrnekler.WinForm
{
    public partial class Form1 : Form
    {
        Ogrenci[] ogreciList = new Ogrenci[15];
        int rowIdex = -1;
        public Form1()
        {
            InitializeComponent();

            OgrenciOlustur("Mustafa", "Okur", 4);
            OgrenciOlustur("Ahmet", "Yazar", 4);
            OgrenciOlustur("Ayşe", "Söyler", 4);
            OgrenciOlustur("Fata", "Konuşur", 4);



        }

        private void Form1_Load(object sender, EventArgs e)
        {
            dgwOgrenci.DataSource = ogreciList;

            btnSil.Visible = false;

        }


        private void OgrenciOlustur(string ad, string soyad, int sinif)
        {
            Ogrenci ogrenci = new Ogrenci();
            ogrenci.Ad = ad;
            ogrenci.Soyad = soyad;
            ogrenci.Sinif = sinif;



            for (int i = 0; i < ogreciList.Length; i++)
            {
                if (ogreciList[i] == null)
                {
                    ogreciList[i] = ogrenci;
                    break;
                }
            }
        }

        private void btnKaydet_Click(object sender, EventArgs e)
        {
            string ad = txtAd.Text;
            if (ad == null || ad == "")
            {
                MessageBox.Show("Ad alanı boş geçilemez");
                return;
            }
            string soyad = txtSoyad.Text;
            if (String.IsNullOrEmpty(soyad))
            {
                MessageBox.Show("Soyad alanı boş geçilemez");
                return;
            }
            int sinif;
            if (!Int32.TryParse(txtSinif.Text, out sinif))
            {
                MessageBox.Show("Sınıf alanı sayı olmalıdır");
                return;
            }
            if (rowIdex == -1)
            {
                OgrenciOlustur(ad, soyad, sinif);

            }
            else
            {
                ogreciList[rowIdex].Ad = ad;
                ogreciList[rowIdex].Soyad = soyad;
                ogreciList[rowIdex].Sinif = sinif;
            }
            dgwOgrenci.DataSource = ogreciList;
            dgwOgrenci.Refresh();

            txtAd.Text = "";
            txtSoyad.Text = "";
            txtSinif.Text = "";
            rowIdex = -1;

        }

        private void dgwOgrenci_CellClick(object sender, DataGridViewCellEventArgs e)
        {
            txtAd.Text = ogreciList[e.RowIndex].Ad;
            txtSoyad.Text = ogreciList[e.RowIndex].Soyad;
            txtSinif.Text = ogreciList[e.RowIndex].Sinif.ToString();

            rowIdex = e.RowIndex;
        }

        private void btnSil_Click(object sender, EventArgs e)
        {
            if (rowIdex == -1)
                return;

            ogreciList[rowIdex] = null;

            dgwOgrenci.DataSource = ogreciList;
            dgwOgrenci.Refresh();
        }
    }
}
