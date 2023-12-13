# FDS-Practical-Batch-B
codes for batch B 
#code no.3 matrix operations


    def matrix_input(rows, cols):
        matrix = []
        print("Enter {rows}x{cols} matrix:")
        for i in range(rows):
            row = list(map(int, input().split()))
            matrix.append(row)
     return matrix
    
    def matrix_addition(mat1, mat2):
        return [[mat1[i][j] + mat2[i][j] for j in range(len(mat1[0]))] for i in range(len(mat1))]
    
    def matrix_subtraction(mat1, mat2):
        return [[mat1[i][j] - mat2[i][j] for j in range(len(mat1[0]))] for i in range(len(mat1))]
    
    def matrix_multiplication(mat1, mat2):
        return [[sum(mat1[i][k] * mat2[k][j] for k in range(len(mat2))) for j in range(len(mat2[0]))] for i in range(len(mat1))]
    
    def matrix_transpose(matrix):
        return [[matrix[j][i] for j in range(len(matrix))] for i in range(len(matrix[0]))]
    
    def print_matrix(matrix):
        for row in matrix:
            print(" ".join(map(str, row)))
    
    # Get matrices once
    rows1, cols1 = map(int, input("Enter rows and columns of matrix 1: ").split())
    mat1 = matrix_input(rows1, cols1)
    
    rows2, cols2 = map(int, input("Enter rows and columns of matrix 2: ").split())
    mat2 = matrix_input(rows2, cols2)
    
    while True:
        print("\nMatrix Operations Menu:")
        print("1. Addition")
        print("2. Subtraction")
        print("3. Multiplication")
        print("4. Transpose")
        print("5. Exit")

    choice = input("Enter your choice (1-5): ")

    if choice == '5':
        break

    if choice in {'1', '2', '3'}:
        if choice == '1':
            result = matrix_addition(mat1, mat2)
            print("\nMatrix Addition Result:")
        elif choice == '2':
            result = matrix_subtraction(mat1, mat2)
            print("\nMatrix Subtraction Result:")
        else:
            result = matrix_multiplication(mat1, mat2)
            print("\nMatrix Multiplication Result:")

        print_matrix(result)

    elif choice == '4':
        result = matrix_transpose(mat1)
        print("\nMatrix 1 Transpose Result:")
        print_matrix(result)

        result = matrix_transpose(mat2)
        print("\nMatrix 2 Transpose Result:")
        print_matrix(result)

    else:
        print("Invalid choice. Please enter a number between 1 and 5.")
