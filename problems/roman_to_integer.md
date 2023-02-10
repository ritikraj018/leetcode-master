class Solution {
public:
//Function to get value of each char
    int getVal(char chh){
           //Using Switch Case to return the values
           switch(chh){
                case 'I': return 1;
                case 'V': return 5;
                case 'X': return 10;
                case 'L': return 50;
                case 'C': return 100;
                case 'D': return 500;
                case 'M': return 1000;
                default: return -1;
           }
       }
    //Conversion Function
    int romanToInt(string s) {

        int sum=0;
        for ( int i = 0; i < s.length(); i++){
            int curr = getVal(s[i]), next=getVal(s[i+1]);
            if( curr < next){       //If current value is less than next value then subtract the current value from sum, Eg:- IX = 9
                sum -= curr;
            }
            else{
                sum = sum + curr;
            }
        }
        return sum;
    }
};
