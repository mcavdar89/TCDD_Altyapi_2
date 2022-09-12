
Console.Write("Hangi Ay :");
int ay = Convert.ToInt32(Console.ReadLine());

if (ay == 1 || ay == 3 || ay == 5 || ay == 7 || ay == 8 || ay == 10 || ay == 12)
{
    Console.WriteLine(ay + ". ay " + 31 + " gündür.");
}
else if (ay == 2)
{
    Console.WriteLine(ay + ". ay " + 28 + " gündür.");
}

else if( ay <= 12)
{
    Console.WriteLine(ay + ". ay " + 30 + " gündür.");

}
else
{
    Console.WriteLine("1 ile 12 arasında değer giriniz!");

}
