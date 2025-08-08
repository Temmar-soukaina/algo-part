FUNCTION SumOfDistinctElements(arr1, arr2):

    INITIALIZE sum = 0

    // Step 1: Compare elements from arr1 with arr2
    FOR each element in arr1:
        SET found = false
        FOR each element in arr2:
            IF arr1 element == arr2 element:
                SET found = true
                BREAK
        IF found == false:
            sum = sum + arr1 element

    // Step 2: Compare elements from arr2 with arr1
    FOR each element in arr2:
        SET found = false
        FOR each element in arr1:
            IF arr2 element == arr1 element:
                SET found = true
                BREAK
        IF found == false:
            sum = sum + arr2 element

    RETURN sum    
    
                          Part 1: Procedure to Compute Dot Product
       
       PROCEDURE dot_product(v1, v2, n, ps)
    // v1 and v2: vectors (arrays)
    // n: size of vectors
    // ps: result variable (passed by reference)

    SET ps = 0
    FOR i FROM 0 TO n - 1:
        ps = ps + (v1[i] * v2[i])
END PROCEDURE
                         Part 2: Check Orthogonality Using Procedure
   ALGORITHM check_orthogonal_pairs:

    INPUT n  // number of vector pairs

    FOR i FROM 1 TO n:
        INPUT size  // dimension of vectors
        DECLARE arrays v1[size], v2[size]

        // Read first vector
        FOR j FROM 0 TO size - 1:
            INPUT v1[j]

        // Read second vector
        FOR j FROM 0 TO size - 1:
            INPUT v2[j]

        DECLARE ps
        CALL dot_product(v1, v2, size, ps)

        IF ps == 0:
            OUTPUT "Vectors", i, "are orthogonal."
        ELSE:
            OUTPUT "Vectors", i, "are not orthogonal."
END ALGORITHM
                           Part 3: Using a Function Instead of a Procedure
FUNCTION dot_product(v1, v2, n) RETURNS ps
    SET ps = 0
    FOR i FROM 0 TO n - 1:
        ps = ps + (v1[i] * v2[i])
    RETURN ps
END FUNCTION
                          Orthogonality Check Using Function
ALGORITHM check_orthogonal_pairs_function:

    INPUT n  // number of vector pairs

    FOR i FROM 1 TO n:
        INPUT size
        DECLARE arrays v1[size], v2[size]

        FOR j FROM 0 TO size - 1:
            INPUT v1[j]

        FOR j FROM 0 TO size - 1:
            INPUT v2[j]

        ps = CALL dot_product(v1, v2, size)

        IF ps == 0:
            OUTPUT "Vectors", i, "are orthogonal."
        ELSE:
            OUTPUT "Vectors", i, "are not orthogonal."
END ALGORITHM
