# DARYA GERSHANOK
## Contacts
Email: gershanok32@gmail.com
Tel: +375293788127
## ABOUT ME
##### My strengths:
- learnability
- desire to learn new things
- purposefulness
- sociability
- responsibility
- diligence

##### My goals and priorities:
- to improve the level of my knowledge
- to achieve an acceptable level of knowledge for employment
- development within the profession

## SKILLS
- Object Oriented Programming Basics
- C++
- Git & GitHub

## CODE EXAMPLE
```c++
class TextFile
{
    char name[256];
    int length;
    char* buff;
    char temp[256];
public:

    //Constructor without parameters
    TextFile() :length(0)
    {

    }

    //Constructor with parameter
    TextFile(int par) : length(par)
    {
        strcpy_s(name, "\0");
        buff = nullptr;
    }

    //Copy constructor 
    TextFile(const TextFile& file) :
        length(file.length)
    {
        strcpy_s(name, file.name);
        if (file.buff)
        {
            buff = new char[length];
            for (int i = 0; i < length; i++)
            {
                buff[i] = file.buff[i];
            }
        }
        cout << "===================\nSuccessfully copied\n===================\n";
    }

    //Open file
    void Open(char* file_name)
    {
        strcpy_s(name, file_name);
        if ((fopen_s(&fl, name, "rt")) != NULL)
        {
            cout << "Oshibka pri otkritii" << endl;
            exit(1);
        }
        length = _filelength(_fileno(fl)) + 1;
        buff = new char[length];
        fgets(buff, length, fl);
        fclose(fl);
    }

    //Add text at the end
    void AddText(char* zapis)
    {
        if ((fopen_s(&fl, name, "a+")) != NULL)
        {
            cout << "Oshibka" << endl;
            exit(1);
        }
        fwrite(zapis, strlen(zapis), 1, fl);
        fclose(fl);
        delete[]buff;
        TextFile::Open(name);
    }

    //Output
    void Print()
    {
        puts(buff);
    }

    //Add text in position
    void PasteText(char* stroka, int position)
    {
        if ((fopen_s(&fl, name, "r+")) != NULL)
        {
            cout << "Oshibka" << endl;
            exit(1);
        }
        char temp[256];
        strncpy_s(temp, buff, position);
        strcat_s(temp, " ");
        strcat_s(temp, stroka);
        strcat_s(temp, " ");
        fseek(fl, position, SEEK_SET);
        fread(buff, length, 1, fl);
        strncat_s(temp, buff, length - position - 1);
        fseek(fl, 0, SEEK_SET);
        fwrite(temp, strlen(temp), 1, fl);
        fclose(fl);
        delete[]buff;
        TextFile::Open(name);
    }

    //Save
    void Save(char* file_name = NULL)
    {
        if (*file_name)
        {
            if ((fopen_s(&fl, file_name, "w+")) != NULL)
            {
                cout << "Oshibka" << endl;
                exit(1);
            }
            fwrite(buff, length, 1, fl);
            fclose(fl);
            cout << "File was saved successfully!\n";
        }
        else
        {
            if ((fopen_s(&fl, name, "w+")) != NULL)
            {
                cout << "Oshibka" << endl;
                exit(1);
            }
            fwrite(buff, length, 1, fl);
            fclose(fl);
            cout << "File was saved successfully!\n";
        }
    }

    //Destructor
    ~TextFile()
    {
        delete[] buff;
    }
};

cout << "===\nSuccessfully copied\n===\n";
    }
```
## EXPERIENCE

## EDUCATION
*2019-Nowadays* 
 **BELARUSIAN STATE UNIVERSITY OF INFORMATICS AND RADIOELECTRONICS**
- Faculty of Information Technologies ans Control
- Speciality: Automated Information Processing Systems
## ENGLISH
**ESTIMATED ENGLISH LEVEL 
B1**