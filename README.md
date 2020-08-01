# C++ note
## typedef struct vs struct

struct and typedef are two very different things.

The struct keyword is used to define, or to refer to, a structure type. For example, this:

struct foo {
    int n;
};
creates a new type called struct foo.

A typedef, in spite of the name, does not define a new type; it merely creates a new name for an existing type. For example, given:

typedef int my_int;
my_int is a new name for int; my_int and int are exactly the same type. Similarly, given the struct definition above, you can write:

typedef struct foo foo;
The type already has a name, struct foo. The typedef declaration gives the same type a new name, foo.

The syntax allows you to combine a struct and typedef into a single declaration:
//The structure of the object.
typedef struct obj
{
	int			id;
	range*		MBR;

	//IR-tree augmentation.
	k_node_t*	k_head;

}	obj_t;

## Void pointer


The void pointer, also known as the generic pointer, is a special type of pointer that can be pointed at objects of any data type! A void pointer is declared like a normal pointer, using the void keyword as the pointer’s type:


void *ptr; // ptr is a void pointer

A void pointer can point to objects of any data type:


int nValue;

float fValue;


struct Something
{
    int n;
    
    float f;
};


Something sValue;
 
void *ptr;

ptr = &nValue; // valid

ptr = &fValue; // valid

ptr = &sValue; // valid


However, because the void pointer does not know what type of object it is pointing to, it cannot be dereferenced directly! Rather, the void pointer must first be explicitly cast to another pointer type before it is dereferenced.

int value{ 5 };

void *voidPtr{ &value };
 
 
// std::cout << *voidPtr << '\n'; // illegal: cannot dereference a void pointer


int *intPtr{ static_cast<int*>(voidPtr) }; // however, if we cast our void pointer to an int pointer...


std::cout << *intPtr << '\n'; // then we can dereference it like normal

This prints:


5

## Extern
The extern keyword may be applied to a global variable, function, or template declaration. It specifies that the symbol has external linkage. 


The extern keyword has four meanings depending on the context:


In a non-const global variable declaration, extern specifies that the variable or function is defined in another translation unit. The extern must be applied in all files except the one where the variable is defined.


In a const variable declaration, it specifies that the variable has external linkage. The extern must be applied to all declarations in all files. (Global const variables have internal linkage by default.)


extern "C" specifies that the function is defined elsewhere and uses the C-language calling convention. The extern "C" modifier may also be applied to multiple function declarations in a block.


In a template declaration, extern specifies that the template has already been instantiated elsewhere. extern tells the compiler it can reuse the other instantiation, rather than create a new one at the current location.
