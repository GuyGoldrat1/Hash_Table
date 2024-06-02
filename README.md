# Hash Table Implementation in Java

## Overview
This Java project implements various types of open addressing hash tables, each employing a different probing technique for collision resolution. The supported types are:
1. **Linear Probing (LPHashTable)**
2. **Quadratic Probing (QPHashTable and AQPHashTable)**
3. **Double Hashing (DoubleHashTable)**

## Project Structure

- **AQPHashTable.java**: Implements a hash table using advanced quadratic probing.
- **DoubleHashTable.java**: Implements a hash table using double hashing.
- **HashTableElement.java**: Represents an element in the hash table, with key-value pairs.
- **IHashTable.java**: Defines the interface for the hash table operations.
- **LPHashTable.java**: Implements a hash table using linear probing.
- **ModHash.java**: Provides a modular hashing function used by the hash tables.
- **OAHashTable.java**: An abstract base class for open addressing hash tables, implementing common functionalities.
- **QPHashTable.java**: Implements a hash table using quadratic probing.

## Classes and Interfaces

### IHashTable.java
An interface defining the operations for the hash tables:
- **Insert(HashTableElement hte)**: Inserts a new element into the hash table.
- **Delete(long key)**: Deletes an element with the given key from the hash table.
- **Find(long key)**: Finds an element with the given key in the hash table.

Exceptions:
- **TableIsFullException**: Thrown when the hash table is full and cannot accommodate more elements.
- **KeyAlreadyExistsException**: Thrown when attempting to insert an element with a key that already exists in the table.
- **KeyDoesntExistException**: Thrown when attempting to delete or find an element with a key that does not exist in the table.

### OAHashTable.java
An abstract class that implements the IHashTable interface and provides common functionalities for open addressing hash tables:
- **table**: An array of `HashTableElement` representing the hash table.
- **m**: The size of the hash table.
- **Hash(long x, int i)**: An abstract method to be implemented by subclasses, defining the probing sequence.

### LPHashTable.java
A class extending `OAHashTable` and implementing linear probing:
- **Hash(long x, int i)**: Computes the hash value using linear probing.

### QPHashTable.java
A class extending `OAHashTable` and implementing quadratic probing:
- **Hash(long x, int i)**: Computes the hash value using quadratic probing.

### AQPHashTable.java
A class extending `OAHashTable` and implementing advanced quadratic probing:
- **Hash(long x, int i)**: Computes the hash value using advanced quadratic probing, which considers the sign of `i`.

### DoubleHashTable.java
A class extending `OAHashTable` and implementing double hashing:
- **Hash(long x, int i)**: Computes the hash value using double hashing.

### ModHash.java
A utility class providing a modular hash function:
- **GetFunc(int m, long p)**: Generates a `ModHash` instance with random coefficients `a` and `b`.
- **Hash(long key)**: Computes the hash value using the formula `((a * key + b) % p) % m`.

### HashTableElement.java
A class representing an element in the hash table with a key and value:
- **GetKey()**: Returns the key of the element.
- **GetValue()**: Returns the value of the element.

## How to Use

1. **Compile the Project**:
   ```
   javac *.java
   ```
2. **Run the Tests or Main Program**:
   Implement and run a test or main program to create instances of the hash tables and perform operations like insert, delete, and find.

