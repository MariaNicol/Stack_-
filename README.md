# Stack_-
задачи и сорсове, стек 

//17.05.2023
#1
// от десетична в произволна с основа от 2 до 16.
        // number - положително цяло число в десетична БС
        // baseSS – основа на бройната система
        // връща записа на числото в новата бройна система като низ
        public static string PreobrChislo(int number, int baseSS)
        {
            // създава се стек за съхраняване на остатъците
            Stack<int> s = new Stack<int>();
            // изчисляване на остатъците от делението
            while (number != 0)
            {
                s.Push(number % baseSS);
                number = number / baseSS;
            }
            // формиране на низово представяне записа на числото
            // след извличане на стойността от стека
            string res = "";
            try
            {
                while (true)
                {
                    int n = s.Pop();
                    if (n < 10)
                        res = res + n;
                    else
                        res = res + (char)((int)'A' + n - 10);
}
            }
            catch (Exception e)
            {
                // когато стека се изпразни,
                // представянето на числото е формирано
            }
            return res;
        }
        static void Main(string[] args)
        {
            int number = int.Parse(Console.ReadLine());
            int baseSS = int.Parse(Console.ReadLine());
            Console.WriteLine(PreobrChislo(number, baseSS));
        }
    }
}
