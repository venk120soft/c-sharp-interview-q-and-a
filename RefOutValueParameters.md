## Differences between value, Ref, out, params parameters passing in to the methods
When we pass Value type parameters (default) the value of the passed parameter won't be changed.
```javascript
private int sum(int a, int b, int c){
    c=2
    return a+b;
}
Console.WriteLine(c);// compiler error
private int sum(int a, int b, ref int c){
    c=2;
    return a+b;
}
Console.WriteLine(c);// 2
private void sum(int a, int b, out sumValue=0){
    sumValue=a+b;
}
this.sum(2,3);
Console.WriteLine(sumValue);// 5
```
```javascript
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace MethodParameters
{
// Differences between value, Ref, out, params parameters passing in to the methods
    class Program
    {
        static void Main(string[] args)
        {
            int i = 0;
            Program objProgram = new Program();
            Console.WriteLine("\n**********************Value Parameter Operations********************\n");
            Console.WriteLine("i value before ValueParamterMethod is: " + i);
            objProgram.ValueParameters(i);
            Console.WriteLine("i value after ValueParamterMethod is: " + i);

            Console.WriteLine("\n\n\n**********************Ref Parameter Operations********************\n");
            Console.WriteLine("I value before refparametersMethod" + i);
            objProgram.RefParameters(ref i);
            Console.WriteLine("i value after RefParametersMethod is: " + i);

            Console.WriteLine("\n\n\n**********************out Parameter Operations********************\n");
            int a, b, sum, product;
            string FN;
            objProgram.OutParameters(10, 20, out sum, out product, out FN);
            Console.WriteLine("Sum of 10,20 is : {0}", sum);
            Console.WriteLine("Product of 10,20 is : {0}", product);
            Console.WriteLine("Full Name with 10,20 is:  {0}", FN);

            Console.WriteLine("\n\n\n**********************params Parameter Operations********************\n");
            // advantage of Params keyword is params argument is an optional
            objProgram.ParamsParameters();

            // the advantage of params keyword is we can pass the array of elements to the method by seperating with comma like below
            objProgram.ParamsParameters(1, 2, 3, 4);

            int[] NumbersArray = new int[] { 101, 502, 2, 3, 8, 106 };
            //We can pass array directly like below
            objProgram.ParamsParameters(NumbersArray);

            objProgram.ParamsParametersMethod2(58, "Venkatesh", NumbersArray);

            Console.ReadLine();
        }
        public void ValueParameters(int i)
        {
            i = 100;
            Console.WriteLine("j value is in ValueParametersMethod:{0} ", i);
        }
        public void RefParameters(ref int i)
        {
            i = 200;
            Console.WriteLine("i value is in RefParametersMethod:{0} ", i);
        }
        // when we want to get 2 or more outputs from the same method we will prefer to use out parameters
        //return type of this method would be void 
        public void OutParameters(int a, int b, out int sum,out int product, out string FullName )
        {
            sum = a + b;
            product = a * b;
            FullName = a + b + "MyString";
        }
        
        public void ParamsParameters(params int[] Numbers)
        {
            Console.WriteLine("Arrray is having {0} elements",Numbers.Length);
            foreach(int element in Numbers)
            {
                Console.WriteLine(element);
            }
        }
        //params parameter should be the last one
        //we cannot pass 2 params parameters to the method
        public void ParamsParametersMethod2(int a, string s, params int[] Numbers)
        {

            Console.WriteLine("Arrray is having {0} elements", Numbers.Length);
            foreach (int element in Numbers)
            {
                Console.WriteLine(element);
            }
            Console.WriteLine("Values of ParamsParametersMethod2 arguments FullName is {0} \nRoll Number is {1}",s,a);
        }
    }
}
```
