namespace TCDD.TemelOrnekler.WinForm
{
    public partial class Form1 : Form
    {
        Ogrenci[] ogreciList = new Ogrenci[15];
        public Form1()
        {
            InitializeComponent();

            OgrenciOlustur("Mustafa", "Okur", 4);
            OgrenciOlustur("Ahmet", "Yazar", 4);
            OgrenciOlustur("Ayşe", "Söyler", 4);
            OgrenciOlustur("Fata", "Konuşur", 4);



        }



        private void OgrenciOlustur(string ad,string soyad,int sinif)
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



    }
}
