## Calculator Code
```markdown
print("1. Addition");
print("2. Subtraction");
print("3. Multiplication");
print("4. Division");
print("5. Exit");
choice = int(input("Enter your choice: "));
if (choice>=1 and choice<=4):
    print("Enter two numbers: ");
    number_1 = int(input());
    number_2 = int(input());
    if choice == 1:
        res = number_1 + number_2;
        print('{} + {} = '.format(number_1, number_2))
        print("Answer = ", res);
    elif choice == 2:
        res = number_1 - number_2;
        print('{} - {} = '.format(number_1, number_2))
        print("Answer = ", res);
    elif choice == 3:
        res = number_1 * number_2;
        print('{} * {} = '.format(number_1, number_2))
        print("Answer = ", res);
    else:
        res = number_1 / number_2;
        print('{} / {} = '.format(number_1, number_2))
        print("Answer = ", res);
elif choice == 5:
    exit();
else:
    print("You can only select numbers 1-5");
    
 ```

>  <a href="https://theresiap.github.io/Personal-Project/Calculator/">Return To Previous Page</a>
