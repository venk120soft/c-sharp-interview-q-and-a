```
using System;
using System.Collections.Generic;
using System.Text;

namespace StringManipulations
{
    public class AllStringOperations
    {
        /*All string Methods
        //o/p
            *   Steven Clark
                1
                True
                False
                False
                1470518261
                System.String
                String
                2
                steven clark
                STEVEN CLARK
                HelloSteven Clark
                True
                4
                12
                Steve
                Stivin Clark
                St
                v
                n Clark
                True
                even
                Steven Clark
                Steven Clark
            * */
        public void AllStringMethods()
        {
            string firstname;
            string lastname;

            firstname = "Steven Clark";
            lastname = "Clark";


            Console.WriteLine(firstname.Clone());
            // Make String Clone
            Console.WriteLine(firstname.CompareTo(lastname));
            //Compare two string value and returns 0 for true and 1 for false

            Console.WriteLine(firstname.Contains("ven")); //Check whether specified value exists or not in string

            Console.WriteLine(firstname.EndsWith("n")); //Check whether specified value is the last character of string
            Console.WriteLine(firstname.Equals(lastname));
            //Compare two string and returns true and false


            Console.WriteLine(firstname.GetHashCode());
            //Returns HashCode of String

            Console.WriteLine(firstname.GetType());
            //Returns type of string

            Console.WriteLine(firstname.GetTypeCode());
            //Returns type of string

            Console.WriteLine(firstname.IndexOf("e")); //Returns the first index position of specified value the first index position of specified value

            Console.WriteLine(firstname.ToLower());
            //Covert string into lower case

            Console.WriteLine(firstname.ToUpper());
            //Convert string into Upper case

            Console.WriteLine(firstname.Insert(0, "Hello")); //Insert substring into string

            Console.WriteLine(firstname.IsNormalized());
            //Check Whether string is in Unicode normalization from C


            Console.WriteLine(firstname.LastIndexOf("e")); //Returns the last index position of specified value

            Console.WriteLine(firstname.Length);
            //Returns the Length of String

            Console.WriteLine(firstname.Remove(5));
            //Deletes all the characters from begining to specified index.

            Console.WriteLine(firstname.Replace('e', 'i')); // Replace the character

            string[] split = firstname.Split(new char[] { 'e' }); //Split the string based on specified value


            Console.WriteLine(split[0]);
            Console.WriteLine(split[1]);
            Console.WriteLine(split[2]);

            Console.WriteLine(firstname.StartsWith("S")); //Check wheter first character of string is same as specified value

            Console.WriteLine(firstname.Substring(2, 5));
            //Returns substring

            Console.WriteLine(firstname.ToCharArray());
            //Converts an string into char array.

            Console.WriteLine(firstname.Trim());
            //It removes starting and ending white spaces from string.
        }
        
        // My Name is Venkatesh
        //yM emaN si hsetakneV 
        public string PrintWordsInReverse1(string myString)
        {
            //char[] myArray=myString.ToCharArray();
            char[] revTemp;
            string resultString = string.Empty;

            for (int i = 0; i < myString.Split(' ').Length; i++)
            {
                revTemp = myString.Split(' ')[i].ToCharArray();
                for (int j = revTemp.Length - 1; j >= 0; j--)
                {
                    resultString = resultString + revTemp[j];
                }
                resultString = resultString + " ";
            }
            return resultString;
        }
        //Same programme without using split function
        public string PrintWordsInReverse2(string str)
        {
            string revWord = string.Empty;
            string finalSentance = string.Empty;
            for (int i = 0; i < str.Length; i++)
            {
                if (str[i] != ' ')
                {
                    revWord = str[i] + revWord;
                }
                else
                {
                    revWord = revWord + ' ';
                    finalSentance = finalSentance + revWord;
                    revWord = string.Empty;
                }
            }
            if (revWord != string.Empty)
                finalSentance = finalSentance + revWord;

            return finalSentance;
        }
        // My Name is Venkatesh
        // Venkatesh is Name My
        public string PrintWordsInReverseFromEndAsItIsReverse(string MyInputString)
        {
            string temp = null;
            for (int i = MyInputString.Split(' ').Length - 1; i >= 0; i--)
            {
                temp = temp + MyInputString.Split(' ')[i] + " ";
            }
            return temp;
        }
        // My Name is Venkatesh
        //hsetakneV si emaN yM
        public string ReverseTheWordsFromEndToStart(string inputString)
        {
            char[] myArray = inputString.ToCharArray();
            string temp = "";
            for (int i = myArray.Length - 1; i >= 0; i--)
            {
                temp = temp + myArray[i];
            }
            return temp;
        }
        //we can use givenString.Replace(findString,replaceString);
        //Without replace function
        public static string MyReplaceString(string givenString, string findString, string replaceString)
        {
            if (givenString != null)
            {
                var givenStringArr = givenString.Split(new[] { findString }, StringSplitOptions.None);

                var result = new StringBuilder();

                for (int i = 0; i < givenStringArr.Length; i++)
                {
                    result.Append(givenStringArr[i]);

                    if (i + 1 != givenStringArr.Length)
                    {
                        result.Append(replaceString);
                    }
                }

                return result.ToString();
            }
            return null;
        }

        //Using Linq
        public static string MyReplaceStringUsingLinq(string givenString, string findString, string replaceString)
        {
            if (givenString != null)
            {
                var givenStringArr = givenString.Split(new[] { findString }, StringSplitOptions.None);
                var start = givenStringArr.Take(1);
                var end =
                from originalString in givenStringArr.Skip(1)
                from newString in new[] { replaceString, originalString }
                select newString;
                var result = String.Join("", start.Concat(end));
                return result;
            }
            return null;
        }

        //Remove duplicate elements from string
        //ex: venkatesh o/p: venkatsh
        public string RemoveDuclicteChars(string givenString)
        {
            var temp = "";
            foreach (char ch in givenString)
            {
                if (temp.IndexOf(char.ToLower(ch)) == -1)
                {
                    //Adding uniq characters to the temp
                    temp += (char.ToLower(ch));
                }
            }
            return temp.Trim();
        }
        //counting the occurance of the each character in given string
        //ex: Rama
        //o/p: R-->1,a-->2 m-->1
        public void OccurenceOfEachChar(string givenString)
        {
            Console.WriteLine("Given String is:" + givenString);
            char[] myArray = givenString.ToCharArray();
            char temp = ' ';
            int count;
            //looping throw each char in givenString and checking with each with other
            for (int i = 0; i < myArray.Length - 1; i++)
            {
                //Making the count 0 all the time for each char check
                count = 0;
                temp = myArray[i];
                if (temp != '*')
                {
                    //checking the temp with each character in givenstring
                    for (int j = i; j < myArray.Length - 1; j++)
                    {
                        if (temp == myArray[j])
                        {
                            //setting the duplicate char with * (What ever we can take )
                            myArray[j] = '*';
                            count++;
                        }
                    }
                }
                if (count >= 1)
                {
                    Console.WriteLine("\n" + temp + " Repeated " + count + " Times ");
                    while (count > 0)
                    {
                        Console.Write("*");
                        count--;
                    }
                }
            }
            Console.WriteLine("Given String is:" + givenString);
        }

        //Finding the frequency of the substring in a GovenString 
        //ramu is men, he is handsome.
        //have to get occurance of is
        //o/p:2SS
        public int CountSubstringOccurance(string givenString, string subString)
        {
            int count = 0;
            //checking from the starting i.e index=0
            int firstIndex = givenString.IndexOf(subString, 0);
            int secondIndex = 0;
            //checking index of substring if it lies 
            while (firstIndex != -1)
            {
                //setting
                //ex: My Name is venkatesh
                //substring is "Name" then length of the Name is 4 so next occurance will come after the length of this string
                secondIndex = firstIndex + subString.Length;
                firstIndex = givenString.IndexOf(subString, secondIndex);
                count++;
            }
            return count;
        }
        
        //Checking the substring occurances in a string 
        public static int CountSubstring(string text, string value)
        {
            int count = 0, minIndex = text.IndexOf(value, 0);
            while (minIndex != -1)
            {
                minIndex = text.IndexOf(value, minIndex + value.Length);
                count++;
            }
            return count;
        }
        
        
        /// <summary>
        /// Algo : Anagram string means each char in givenString should be there in second string any where.
        /// </summary>
        /// <param name="text1"></param>
        /// <param name="text2"></param>
        /// <returns></returns>
        private bool IsAnagram(string text1, string text2)
        {
            
            if (text1.Length != text2.Length)
            {
                return false;
            }
            // This will keep track of the chars for any string 
            int[] resultedArray = new int[256]; // total no of characters
            for (int i = 0; i < text1.Length; i++)
            {
                // i.e resultedArray['a']++ means 97 is the ansci value for the a and on each count it will increase by 1
                // ex: 'abstract' after looping all elements a is 2 times repeated so at 97 the value is 2 b is 1 c is 1 t is 2 r is 1
                resultedArray[text1[i]]++;
                // If the count is 0 intially then on doing this step it should be -1
                resultedArray[text2[i]]--;
            }
            // at the end all values should be 0 otherwise false
            for (int i = 0; i < resultedArray.Length; i++)
            {
                if (resultedArray[i] != 0)
                {
                    return false;
                }
            }
            return true;
        }
        
        // best way for reverse string
        public static string BestWayReverseString(string givenString)
        {
            // only defination it wont take memeory
            // givenString.toCharArray file the memory just avoiding 
            char[] tempString = new Char[givenString.Length];
            for(int i = 0, j = givenString.Length-1 ; i<j ; i++, j--){
                tempString[i] = givenString[j];
                tempString[j] = givenString[i];
            }
            return tempString.ToString();
        }
        
        static void Main(string[] args)
        {
            AllStringOperations objProgram = new AllStringOperations();
            Console.ReadKey();
            Console.WriteLine(objProgram.PrintWordsInReverse1("Hi My Name is venkatesh"));
            Console.WriteLine(objProgram.PrintWordsInReverse2("Hi My Name is venkatesh"));

            Console.WriteLine("Enter the string you want to reverse");

            //Console.WriteLine(objProgram.MyStraightString("Hi My Name is venkatesh").TrimEnd());


            //string MyString = Console.ReadLine();
            //char[] charArray = MyString.ToCharArray();
            //string temp = "";
            //for (int i = MyString.Length - 1; i >= 0; i--)
            //{
            //    temp = temp + charArray[i];
            //}
            //Console.WriteLine(temp);
            Console.ReadLine();
        }
    }
}
```
