#include <iostream>
#include <cstdio>
using namespace std;

int main() {
    printf("Hello, World!");
    return 0;
}






#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */   
    return 0;
}




#include <iostream>
#include <cstdio>
using namespace std;

int main() {
    // Complete the code.
    return 0




    #include <bits/stdc++.h>

using namespace std;

string ltrim(const string &);
string rtrim(const string &);



int main()
{
    string n_temp;
    getline(cin, n_temp);

    int n = stoi(ltrim(rtrim(n_temp)));

    // Write your code here

    return 0;
}

string ltrim(const string &str) {
    string s(str);

    s.erase(
        s.begin(),
        find_if(s.begin(), s.end(), not1(ptr_fun<int, int>(isspace)))
    );

    return s;
}

string rtrim(const string &str) {
    string s(str);

    s.erase(
        find_if(s.rbegin(), s.rend(), not1(ptr_fun<int, int>(isspace))).base(),
        s.end()
    );

    return s;
}




#include <iostream>
#include <cstdio>
using namespace std;

int main() {
    // Complete the code.
    return 0;
}


#include <iostream>
#include <cstdio>
using namespace std;

/*
Add `int max_of_four(int a, int b, int c, int d)` here.
*/

int main() {
    int a, b, c, d;
    scanf("%d %d %d %d", &a, &b, &c, &d);
    int ans = max_of_four(a, b, c, d);
    printf("%d", ans);
    
    return 0;
}



#include <stdio.h>

void update(int *a,int *b) {
    // Complete this function    
}

int main() {
    int a, b;
    int *pa = &a, *pb = &b;
    
    scanf("%d %d", &a, &b);
    update(pa, pb);
    printf("%d\n%d", a, b);

    return 0;
}




#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;
    int arr[n];
    
    // Read array elements
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    
    // Print in reverse order
    for (int i = n - 1; i >= 0; i--) {
        cout << arr[i];
        if (i != 0) cout << " ";
    }
    
    return 0;
}




#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n, q;
    cin >> n >> q;

    vector<vector<int>> arr(n); // vector of n variable-length arrays

    // Read variable-length arrays
    for (int i = 0; i < n; i++) {
        int k; // number of elements in this array
        cin >> k;
        arr[i].resize(k); // resize the inner vector
        for (int j = 0; j < k; j++) {
            cin >> arr[i][j];
        }
    }

    // Process queries
    for (int i = 0; i < q; i++) {
        int a, b;
        cin >> a >> b;
        cout << arr[a][b] << endl;
    }

    return 0;
}




#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, q;
    cin >> n >> q;
    cin.ignore(); // ignore newline after numbers

    map<string, string> hrmlMap; // map of tag-path~attribute -> value
    vector<string> tagPath;      // stack to track current path

    for (int i = 0; i < n; i++) {
        string line;
        getline(cin, line);

        // Remove angle brackets
        if (line.substr(0, 2) == "</") {
            // Closing tag -> pop from path
            tagPath.pop_back();
        } else {
            // Opening tag
            line = line.substr(1, line.size() - 2); // remove < and >

            stringstream ss(line);
            string tagName;
            ss >> tagName;

            // Update current tag path
            tagPath.push_back(tagName);
            string prefix = "";
            for (int j = 0; j < tagPath.size(); j++) {
                if (j > 0) prefix += ".";
                prefix += tagPath[j];
            }

            string attrName, equalSign, attrValue;
            while (ss >> attrName) {
                ss >> equalSign >> attrValue;
                // remove quotes around value
                attrValue = attrValue.substr(1, attrValue.size() - 2);
                hrmlMap[prefix + "~" + attrName] = attrValue;
            }
        }
    }

    // Process queries
    for (int i = 0; i < q; i++) {
        string query;
        getline(cin, query);
        if (hrmlMap.find(query) != hrmlMap.end())
            cout << hrmlMap[query] << endl;
        else
            cout << "Not Found!" << endl;
    }

    return 0;
}





#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, q;
    cin >> n >> q;
    cin.ignore(); // ignore newline after numbers

    map<string, string> hrmlMap; // map of tag-path~attribute -> value
    vector<string> tagPath;      // stack to track current path

    for (int i = 0; i < n; i++) {
        string line;
        getline(cin, line);

        // Remove angle brackets
        if (line.substr(0, 2) == "</") {
            // Closing tag -> pop from path
            tagPath.pop_back();
        } else {
            // Opening tag
            line = line.substr(1, line.size() - 2); // remove < and >

            stringstream ss(line);
            string tagName;
            ss >> tagName;

            // Update current tag path
            tagPath.push_back(tagName);
            string prefix = "";
            for (int j = 0; j < tagPath.size(); j++) {
                if (j > 0) prefix += ".";
                prefix += tagPath[j];
            }

            string attrName, equalSign, attrValue;
            while (ss >> attrName) {
                ss >> equalSign >> attrValue;
                // remove quotes around value
                attrValue = attrValue.substr(1, attrValue.size() - 2);
                hrmlMap[prefix + "~" + attrName] = attrValue;
            }
        }
    }

    // Process queries
    for (int i = 0; i < q; i++) {
        string query;
        getline(cin, query);
        if (hrmlMap.find(query) != hrmlMap.end())
            cout << hrmlMap[query] << endl;
        else
            cout << "Not Found!" << endl;
    }

    return 0;
}




#include <sstream>
#include <vector>
#include <iostream>
using namespace std;

// Function to parse comma-separated integers from a string
vector<int> parseInts(string str) {
    vector<int> result;
    stringstream ss(str);
    int num;
    char ch;

    // Read integers separated by commas
    while (ss >> num) {
        result.push_back(num);
        ss >> ch; // discard the comma
    }

    return result;
}

int main() {
    string str;
    cin >> str;

    vector<int> integers = parseInts(str);

    for (int i = 0; i < integers.size(); i++) {
        cout << integers[i] << "\n";
    }

    return 0;
}




#include <iostream>
#include <string>
using namespace std;

int main() {
    string a, b;
    cin >> a >> b;

    // 1. Print lengths
    cout << a.size() << " " << b.size() << endl;

    // 2. Print concatenated string
    cout << a + b << endl;

    // 3. Swap first characters
    char temp = a[0];
    a[0] = b[0];
    b[0] = temp;

    cout << a << " " << b << endl;

    return 0;
}




#include <iostream>
#include <string>
using namespace std;

struct Student {
    int age;
    string first_name;
    string last_name;
    int standard;
};

int main() {
    Student st;

    cin >> st.age >> st.first_name >> st.last_name >> st.standard;
    cout << st.age << " " << st.first_name << " " << st.last_name << " " << st.standard;

    return 0;
}






#include <iostream>
#include <sstream>
using namespace std;

class Student {
private:
    int age;
    string first_name;
    string last_name;
    int standard;

public:
    // Setters
    void set_age(int a) {
        age = a;
    }

    void set_first_name(string fn) {
        first_name = fn;
    }

    void set_last_name(string ln) {
        last_name = ln;
    }

    void set_standard(int s) {
        standard = s;
    }

    // Getters
    int get_age() {
        return age;
    }

    string get_first_name() {
        return first_name;
    }

    string get_last_name() {
        return last_name;
    }

    int get_standard() {
        return standard;
    }

    // Method to return all details as a comma-separated string
    string to_string() {
        stringstream ss;
        ss << age << "," << first_name << "," << last_name << "," << standard;
        return ss.str();
    }
};

int main() {
    int age, standard;
    string first_name, last_name;
    
    cin >> age >> first_name >> last_name >> standard;
    
    Student st;
    st.set_age(age);





    #include <iostream>
#include <string>
#include <sstream>
#include <exception>
using namespace std;
class BadLengthException : public exception {
private:
    int n;
public:
    BadLengthException(int length) {
        n = length;
    }
    int what() {
        return n;
    }
};





bool checkUsername(string username) {
	bool isValid = true;
	int n = username.length();
	if(n < 5) {
		throw BadLengthException(n);
	}
	for(int i = 0; i < n-1; i++) {
		if(username[i] == 'w' &
