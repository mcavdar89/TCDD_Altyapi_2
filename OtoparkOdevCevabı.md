
do
{
    
    int ucret = 0;

    Console.Write("Araç Giriş Saat :");
    int girisSaat = Convert.ToInt32(Console.ReadLine());

    Console.Write("Araç Giriş Dakika :");
    int girisDakika = Convert.ToInt32(Console.ReadLine());


    Console.Write("Araç Çıkış Saat :");
    int cikisSaat = Convert.ToInt32(Console.ReadLine());

    Console.Write("Araç Çıkış Dakika :");
    int cikisDakika = Convert.ToInt32(Console.ReadLine());

    int sureSaat = cikisSaat - girisSaat;
    if (sureSaat < 0)
    {
        Console.Write("Hatalı giriş");
        return;
    }

    int sureDakika = cikisDakika - girisDakika;
    if (sureDakika < 0)
    {
        sureDakika += 60;
        sureSaat--;
    }

    int tempSaat = sureSaat;

    //ilk saat ücretim sabit 10 TL
    ucret += 10;
    tempSaat--;

    if (sureDakika > 10)
        tempSaat++;


    if (tempSaat > 0)//(!(tempSaat<0 || tempSaat ==0 ))
    {

        if (tempSaat > 5)//6saat ten büyük
        {
            ucret += 8 * 5;
            tempSaat -= 5;
            if (tempSaat > 7)//12 saatten büyük
            {
                ucret += 6 * 7;
                tempSaat -= 7;
                if (tempSaat > 3)//15 saatten büyük
                {
                    ucret += 4 * 3;
                    tempSaat -= 3;
                    ucret += tempSaat * 2;
                }
                else
                {
                    ucret += 4 * tempSaat;
                }
            }
            else
            {
                ucret += 6 * tempSaat;
            }
        }
        else
        {
            ucret += 8 * tempSaat;
        }
    }

    Console.WriteLine("Süreniz {0} saat ve {1} dakikadır", sureSaat, sureDakika);
    Console.WriteLine("Ücretiniz {0} TL", ucret); 
} while (true);


