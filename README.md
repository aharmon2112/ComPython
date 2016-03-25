#ifndef PYTHONHEADER_H
#define PYTHONHEADER_H
#include<iostream>
#include<string>
#include<map>

class COMPy 
{ 
public: 
COMPy();

struct List
{
    int int_data;
    double double_data;
    std::string string_data;
    List* rlink; //used for normal linked lists.
    List* dlink; //used lists inside of lists.
	friend std::ostream& operator<<(std::ostream& out, const List*& obj)
	{
		out << obj->string_data;
		return out;
	}
};


std::map <std::string, std::map<std::string, List*>> mapDatabase;
std::map <std::string, std::map<std::string, List*>>::iterator iter_mapDatabase;

std::map <std::string, List*> database;
std::map <std::string, List*>::iterator iter_database;
private: 
void at(List* node, int index); void copyList(List* &node, List* objLeft, List* objRight, bool finished); int size(List* node);

List*& iter_at(List* &node, const int& index); //returns the node at a point

void createDic(std::string& user_input, size_t equals, size_t leftBrace, size_t rightBrace);
List*& findDataType(std::string data);

void change_item_int(std::string data, List* &node, const int& index);
void change_item_double(std::string data, List* &node, const int& index);
void change_item_string(std::string data, List* &node, const int& index);

void additem_int(std::string data, List* &node);
void additem_double(std::string data, List* &node);
void additem_string(std::string data, List* &node);
void display(const List* node);




};

#endif
