//Girilen bir rakamın çift mi yoksa tek mi olduğunu bulup ekrana yazan C# programını yazın


Console.Write("Sayi : ");

//string tempSayi = Console.ReadLine();
//int sayi = Convert.ToInt32(tempSayi);
int sayi = Convert.ToInt32(Console.ReadLine());

int kalan = sayi % 2;
if(kalan == 1)
{
    Console.WriteLine("Sayı tek");
}
else
{
    Console.WriteLine("Sayı çift");

}
