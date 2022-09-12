
int[] matematikNotlar = new int[15];


int islem;
do
{   
    Console.WriteLine("1.İşlem Not Girme ");
    Console.WriteLine("2.İşlem Not Sorgulama ");

    Console.Write("işlem :");
    islem = Convert.ToInt32(Console.ReadLine());
    if (islem == 1)
    {
        Console.Write("index :");
        int index = Convert.ToInt32(Console.ReadLine());


        Console.Write("Not :");
        matematikNotlar[index] = Convert.ToInt32(Console.ReadLine());
    }
    if (islem == 2)
    {
        Console.Write("index :");
        int index = Convert.ToInt32(Console.ReadLine());

        Console.WriteLine(matematikNotlar[index]);
    } 
} while (islem != 0);
