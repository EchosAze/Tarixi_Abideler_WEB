Console.WriteLine("Adinizi daxil edin");
string name = Console.ReadLine();

Console.WriteLine("Balansinizi daxil edin");
double balance = Convert.ToDouble(Console.ReadLine());

double vergi = 1.01;



while (true)
{
    Console.WriteLine("Seciminizi edin");
    Console.WriteLine("1-Balansi goster");
    Console.WriteLine("2-Mexaric etmek");
    Console.WriteLine("3-Balansi artirin");
    Console.WriteLine("4-Cixis edin");

    int option = Convert.ToInt32(Console.ReadLine());
    switch (option)
    {
        case 1:
            Console.WriteLine($"Balansiniz - {balance}");
            break;
        case 2:
            Console.WriteLine("Daxil etmek istediyiniz meblegi daxil edin:");
            double mexaric = Convert.ToDouble(Console.ReadLine());
            double vergiDeyeri = mexaric * vergi;
            if (mexaric > 2000 && vergiDeyeri < balance)
            {
                balance =balance- vergiDeyeri ;
            }
            else if (vergiDeyeri>balance)
            {
                Console.WriteLine("Vegi deyeri balansinizi menfi etmek isteyir.Emeliyat kecersizdir");
            }
            else
            {
                balance -= mexaric;
            }
            Console.WriteLine($"Hal hazirki balansiniz {balance}");
            break;
        case 3:
            double daxil = Convert.ToDouble(Console.ReadLine());
            if (daxil > 2000)
            {
                Console.WriteLine("Cixaris limiti 2000 dir");
            }
            else
            {
                balance += daxil;
                Console.WriteLine();
                Console.WriteLine($"Hal hazirki balansiniz {balance}");
            }
            break;
        case 4:
            Console.WriteLine($"Bizi secdiyiniz ucun cox sagolun {name}");
            break;

        default:
            Console.WriteLine("Duzgun secim etmediniz");
            break;
    }
    if (option == 4)
    {
        break;
    }
}
