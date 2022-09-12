//Kullanıcıdan alınan üç sayıdan en büyüğünü bulan programın C#
kodunu yazınız
int sayi1, sayi2, sayi3;

Console.Write("Sayı 1 :");
sayi1 = Convert.ToInt32(Console.ReadLine());
Console.Write("Sayı 2 :");
sayi2 = Convert.ToInt32(Console.ReadLine());
Console.Write("Sayı 3 :");
sayi3 = Convert.ToInt32(Console.ReadLine());

int enbuyukSayi = sayi1;
if(enbuyukSayi< sayi2)
{
    enbuyukSayi = sayi2;
}
if(enbuyukSayi< sayi3)
{
    enbuyukSayi = sayi3;
}
Console.WriteLine("En büyük sayı = " + enbuyukSayi);
