# Scinece-computer
#include <iostream>

using namespace std;

int Power(int a,int b){      // a的b次方
    if(b==0)
        return 1;
    int sum=a;
    for (int i = 1; i < b;i++){
        sum = a * sum;
    }
    return sum;
}

void printBinary(int a){     // 输出二进制值
    cout << "二进制值：";
    int cmpNum;
    if(a<0){
        a = abs(a);
        cout << '1';
    }
    else
        cout << '0';
    for (int i = 30; i >=0;i--){
        cmpNum = Power(2, i);
        if(a>=cmpNum){
            cout << '1';
            a = a - cmpNum;
        }
        else if(a<cmpNum&&a>=0)
            cout << '0';
        if(i%8==0)
            cout << ' ';
    }
}

int printDec(char x[]){     // 输出十六进制转十进制的值
    int num=0;
    int j = 0;
    for (int i = 10; i >= 2;i--){
        if(x[i]>'9'){
            switch(x[i]){
                case 'a':
                    num += 10 * Power(16,j);
                    break;
                case 'A':
                    num += 10 * Power(16,j);
                    break;
                case 'b':
                    num += 11 * Power(16,j);
                    break;
                    num += 11 * Power(16,j);
                    break;
                case 'c':
                    num += 12 * Power(16,j);
                    break;
                case 'C':
                    num += 12 * Power(16,j);
                    break;
                case 'd':
                    num += 13 * Power(16,j);
                    break;
                case 'D':
                    num += 13 * Power(16,j);
                    break;
                case 'e':
                    num += 14 * Power(16,j);
                    break;
                case 'E':
                    num += 14 * Power(16,j);
                    break;
                case 'f':
                    num += 15 * Power(16,j);
                    break;
                case 'F':
                    num += 15 * Power(16,j);
                    break;
            }
            j++;
        }
        else if(x[i]>='0'&&x[i]<='9'){
            num += (x[i] - '0') * Power(16,j);
            j++;
        }
    }
    return num;
}

int main(){
    char x[100]={0};
    int y;
    cout <<"                       请选择功能" << endl;
    cout << "1.进制转换" << "     " << "2.进制四则运算" << "     " << "3.科学计算器" << "     " <<"0.退出程序"<< endl;
    cin >> y;
    if (y == 1){
        cout << "请输入数字：";
        cin >> x;
        if (x[0] == '0' && x[1] == 'x'){
            int j = printDec(x);
            cout << "此数字是十六进制值" << endl;
            printBinary(j);
            cout << endl;
            cout<<"十进制值："<<j<<endl;
        }
    }
    else if (y == 2){
    }
    else if (y == 3){
    }
    //else if(y==0)
        //break;
    
    return 0;
}
