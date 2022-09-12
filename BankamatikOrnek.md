
int[] musteriHesap = { 100, 100, 100, 100, 100 };

while (true)
{

    Console.Write("Müşteri index :");
    int musIndex = Convert.ToInt32(Console.ReadLine());

    int islem;
    do
    {
        Console.Clear();
        Console.WriteLine("******* {0} nolu müşteri / {1} *********", musIndex, musteriHesap[musIndex]);


        Console.WriteLine("1.Para çekeme");
        Console.WriteLine("2.Para yatırma");
        Console.WriteLine("3.Para gönderme");

        Console.Write("işlem No :");
        islem = Convert.ToInt32(Console.ReadLine());

        Console.Write("tutar :");
        int tutar = Convert.ToInt32(Console.ReadLine());

        if (islem == 1)
        {
            if (musteriHesap[musIndex] - tutar < 0)
            {
                Console.WriteLine("Hesabınızda yeterli bakiye bulunmuyor.");
            }
            else
            {
                musteriHesap[musIndex] -= tutar;
            }
        }
        else if (islem == 2)
        {
            musteriHesap[musIndex] += tutar;
        }
        else if (islem == 3)
        {
            if (musteriHesap[musIndex] - tutar < 0)
            {
                Console.WriteLine("Hesabınızda yeterli bakiye bulunmuyor.");
            }
            else
            {
                Console.Write("göderilecek hesap :");
                int gonIndex = Convert.ToInt32(Console.ReadLine());

                musteriHesap[musIndex] -= tutar;
                musteriHesap[gonIndex] += tutar;
            }
        }
    } while (islem != 0); 
}
