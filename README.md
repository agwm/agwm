# agwm#include <iostream
#include <cstring> 
using namespace std;
class COM {
	char *pname;
	char *punit;
	char *pnum;
	char box[6];
public:
	COM();
	COM(char *name, char *unit, char *num, char *b);
	COM(const COM &p);

	COM operator =(COM &a);
	//重载赋值运算符函数 
	~COM();
	void print();
	void setname(char *name);
	void setuint(char *unit);
	void setnum(char *num);
	void setbox(char *b);
	char *getname();
	char *getuint();
	char *getnum();
	char *getbox();
};

COM::COM()
{

}

COM::COM( char *name, char *unit, char *num, char *b)
{
	pname = name;
	punit = unit;
	pnum = num;
	for (int i = 0; i <= 5; i++)
	{
		box[i] = b[i];
	}
}

COM::COM(const COM &p)
{
	pname = p.pname;
	punit = p.punit;
	pnum = p.pnum;
	for (int i = 0; i <= 5; i++)
	{
		box[i] = p.box[i];
	}
}

COM COM::operator =(COM &a)
{
	pname = a.pname;
	punit = a.punit;
	pnum = a.pnum;
	for (int i = 0; i <= 5; i++)
	{
		box[i] = a.box[i];
	}
	
}

COM::~COM()
{

}

void COM::print()
{
	cout << pname << endl << punit << endl << pnum << endl;
	for (int i = 0; i <= 5; i++)
	{
		cout << box[i];
	}
	cout << endl;
}

void COM::setname(char *name)
{
	pname = name;
}

void COM::setuint(char *unit)
{
	punit = unit;
}

void COM::setnum(char *num)
{
	pnum = num;
}

void COM::setbox(char *b)
{
	for (int i = 0; i <= 5; i++)
	{
		box[i] = b[i];
	}
}

char* COM::getuint()
{
	return punit;
}
char* COM::getname()
{
	return pname;
}
char * COM::getnum()
{
	return pnum;
}
char* COM::getbox()
{
	return box;
}
int main()
{
	COM c1("wangdahai", "江大", "88664455", "212013"),
		c2("张三", "江科技大", "88771111", "212034"), c3(c1), c4;
	c3.setname("李四");
	c4.setname("王五");
	c4.setuint("科大");
	c4.setnum("22334455");
	c4.setbox("212067");
	c1.print();
	c2.print();
	c3.print();
	c4.print();
	c4 = c1;
	c4.print();
	system("pause");
}
