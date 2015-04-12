# Lex
Lex is a Regex Engine for lexical analyzer


### build

It's used cmake to build the project, and doxygen to generate the html doc.

1. `cd` to the project dir.
2. `mkdir build`
3. `cd build`
4. `cmake ..`
5. `make` or `make install`
6. `make doc` to build the doc

### test

use `./lextest` to test the project.


### use Lex to **Scan** the source file

you may use the **LexInterface** to get the token

first include the `.h files` in the `include` dir,

then you should link the `liblex.a` library you built.

```c

/it's a token for return
struct Token
{
	CHAR* pToken; // the string will return
	int type;     // type id for the token 
    int col_num;      // which column the token is
	int row_num;  // which rownum the token is
};

class LexInterface 
{
public:
    virtual Token* Read() = 0;  // get the next token

    virtual const wchar_t* getRule(int id) = 0; 

    virtual int getRuleSize() = 0;
};


```
