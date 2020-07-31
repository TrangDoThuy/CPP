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
