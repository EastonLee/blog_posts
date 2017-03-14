I don't use Octave myself actually, instead I use R with Python, Octave is the chosen language in Coursera course: Machine Learning by Stanford University.

So this article will only cover necessary concept to finish Machine Learning course.

# Index

In Octave, matrix and vector are indexed from 1, which differs from many other languages.

# Output

One line not ending with a semicolon will print the result to output, with semicolon with suppress that output.

Or use `disp(i);` or `sprintf(i)`

# Range

`1:10` will create a 1x10 matrix or say 10-element vector with numbers from 1 to 10. `1:2:10` will create vector with each other numbers from 1 to 10, i.e. `[1 3 5 7 9]`. The middle 2 is the specified step.

# Matrix, Vector

    % assign a matrix to A: 
    A = [1 2; 3 4; 5 6]
    A =
        1   2
        3   4
        5   6

    % access A at first row and second column.
    >> A(1,2)
    ans = 2

    % access second row, here colon refers to all columns
    >> A(2,:)
    ans =
        3   4

    % access second column
    >> A(:,2)
    ans =
        2
        4
        6

    % assign to second column
    >> A(:,2) = [10 11 12]
    % space, comma or semicolon doesn't matter here
    >> A(:,2) = [10, 11, 12]
    >> A(:,2) = [10; 11; 12]

    >> B = [20 21; 22 23; 24 25]
    >> C = [A B] % concatenate A B horizontally
    ans =
        1   2   20   21
        3   4   22   23
        5   6   24   25

    >> D = [A; B] % concatenate A B vertically
    ans =
        1   2
        3   4
        5   6
        20  21
        22  23
        24  25

    >> A' % transpose
    ans =
        1   3   5
        2   4   6

    >> max(magic(4)) % return every column's max
    ans =
        16  14  15  13

    >> max(magic(4), [], 2) % return every row's max
    ans =
       16
       11
       12
       15

    >> [val, ind] = max(magic(4)) % retuns every column's max and their index in corresponding column
    val =
        16  14  15  13
    ind =
        1   4   4   1

    >> max(max(A)); % max element in matrix
    >> A(:) % convert matrix into one column
    ans =
        1
        3
        5
        2
        4
        6
    >> max(A(:)) % max element in matrix
    ans =
        6

    >> sum(A) % sum of column
    >> sum(A, 2) % sum of row

    >> flipud(A) $ flip matrix upside down
    ans =
        5   6
        3   4
        1   2

## Sum of diagonals in a square matrix

    >> M = magic(4);
    >> sum(sum(M.*eye(4))) % sum of diagonal top left to bottom right
    ans = 34
    >> sum(sum(M.* flipud(eye(4) ))) % sum of diagonal bottom left to top right
    ans = 34

## Matrix select

    A(A==2)

# Functions & control statements

Functions are saved in files with the file-ending .m for MATLAB. 

    function y = function_name(x)
        y = x^2;
    % y is the return value
    % x is a parameter
    % is also possible to return multiple values
    function [y1, y2] = function_name(x)
        y1 = x^2
        y2 = x^3

    >> for i=1:10
    >>      disp(i)
    >> end;

    >> i = 1;
    >> while (i ~= 10)
    >>      disp(i);
    >>      i = i+1;
    >> endwhile;

    % i = 10
    >> if (i == 10)
    >>      sprintf('yes')
    >> else
    >>      sprintf('no')
    >> endif
    ans = yes

# Logic operations

not equal ~=

logical AND &&

logical OR ||

logical XOR xor(1,0)


**Reference**:

https://gist.github.com/obstschale/7320846

http://folk.ntnu.no/joern/itgk/refcard-a4.pdf