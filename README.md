# 1-5
// 1. Write a Program in C# to demonstrate Command line arguments processing for
// the following.
// a) To find the square root of a given number.
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace lab1a
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter the value");
            int i;
            i = int.Parse(Console.ReadLine());
            double sqr = Math.Sqrt(i);
            Console.WriteLine("square root of the num is{0}is:{1}", i, sqr);
            Console.ReadLine();
        }
    }
}
// b) To find the sum & average of three numbers.
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab1b
{
    class Program
    {
        static void Main(string[] args)
        {
            int a, b, c, sum;
            float avg;
            Console.WriteLine("Enter the 3 nums");
            a = int.Parse(Console.ReadLine());
            b = int.Parse(Console.ReadLine());
            c = int.Parse(Console.ReadLine());
            sum = a + b + c;
            Console.WriteLine("The sum is" + sum);
            Console.ReadLine();
            avg = sum / 3;
            Console.WriteLine("The avg of given sum is" + avg);
            Console.ReadLine();
        }
    }
}




2.Write a Program in C# to demonstrate the following :
a) Boxing and Unboxing

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace lab2a
{
    class Program
    {
        static void Main(string[] args)
        {
            int i = 123;
            object o = i;
            int j = (int)o;
            Console.WriteLine("The valuetype value before boxing is i=" + i);
            Console.WriteLine("The objecttype value after boxing is o=" + o);
            Console.WriteLine("The valuetype value after unboxing is j=" +
           j);
            Console.ReadLine();
        }
    }
}


b) Invalid Unboxing.
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab2b
{
    class Program
    {
        static void Main(string[] args)
        {
            int i = 123;
            object o = i;
            try
            {
                int j = (Short)o;
                Console.WriteLine("unboxing is successful");
            }
            catch (System.InvalidCastException e)
            {
                Console.WriteLine("Invalid boxing" + e.Message);
            }
            Console.ReadLine();
        }
    }
}





3.Write a program in C# to add Two complex numbers using Operator overloading .

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab3
{
    class complex
    {
        int real;
        int imaginary;
        public complex(int r, int img)
        {
            real = r;
            imaginary = img;
        }
        public static complex operator +(complex c1, complex c2)
        {
            return new complex(c1.real + c2.real, c1.imaginary +
           c2.imaginary);
        }
        public override string ToString()
        {
            return (String.Format("{0}+{1}i", real, imaginary));
        }
    }
    class demo
    {
        static void Main(string[] args)
        {
            int a1, b1, a2, b2;
            Console.WriteLine("Enter the value for a1 & b1");
            a1 = Int32.Parse(Console.ReadLine());
            b1 = Int32.Parse(Console.ReadLine());
            complex num1 = new complex(a1, b1);
            Console.WriteLine("Enter the value for a2 & b2");
            a2 = Int32.Parse(Console.ReadLine());
            b2 = Int32.Parse(Console.ReadLine());
            complex num2 = new complex(a2, b2);
            complex sum = num1 + num2;
            Console.WriteLine("First complex number is" + num1);
            Console.WriteLine("second complex number is" + num2);
            Console.WriteLine("sum of two complex number is" + sum);
            Console.ReadLine();
        }
    }
}

4.Write a Program in C# to find the sum of each row of given jagged array of 3
inner arrays.

using System;
namespace jag
{
    class Program
    {
        static void Main(string[] args)
        {
            const int rows = 3;
            int i, sum = 0;
            int[][] j_arr = new int[rows][];
            j_arr[0] = new int[2];
            j_arr[1] = new int[3];
            j_arr[2] = new int[4];
            j_arr[0][1] = 10;
            j_arr[1][0] = 20;
            j_arr[1][1] = 30;
            j_arr[2][0] = 40;
            j_arr[2][2] = 50;
            j_arr[2][3] = 60;
            for (i = 0; i < 2; i++)
                sum += j_arr[0][i];
            for (i = 0; i < 3; i++)
                sum += j_arr[1][i];
            for (i = 0; i < 4; i++)
                sum += j_arr[2][i];
           Console.WriteLine("sum is :{0}", sum);
           Console.Read();
        }
    }
}

5.Write a Program in C# to demonstrate Array Out of Bound Exception using Try,
Catch and Finally blocks.

using System.Collections.Generic;
using System.Linq;
using System.Text;
namespace lab5
{
    class Program
    {
        public static void Main(string[] args)
        {
            int i, ele;
            Console.WriteLine("Enter the number of elements");
            ele = int.Parse(Console.ReadLine());
            int[] a = new int[ele];
            Console.WriteLine("Enter the elements");
            for (i = 0; i != ele; i++)
            {
                a[i] = int.Parse(Console.ReadLine());
            }
            Console.WriteLine("Enter index size");
            int element = int.Parse(Console.ReadLine());
            try
            {
                Console.WriteLine("element is" + a[element]);
            }
            catch (IndexOutOfRangeException e)
            {
                Console.WriteLine("out of bound exception");
            }
            finally
            {
                Console.WriteLine("Give a valid Array Index size");
            }
            Console.ReadLine();
        }
    }
}
