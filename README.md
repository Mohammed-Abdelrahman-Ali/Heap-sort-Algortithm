# Heap-sort-Algortithm

HEAPIFY(A, n, i):
    largest = i  # Initialize the largest as root
    left = 2 * i + 1  # Left child index
    right = 2 * i + 2  # Right child index

    IF left < n AND A[left] > A[largest]:
        largest = left

    IF right < n AND A[right] > A[largest]:
        largest = right

    IF largest != i:
        SWAP A[i] and A[largest]
        HEAPIFY(A, n, largest)

BUILD_MAX_HEAP(A):
    n = LENGTH(A)
    FOR i = n // 2 - 1 DOWNTO 0:
        HEAPIFY(A, n, i)

HEAP_SORT(A):
    BUILD_MAX_HEAP(A)
    n = LENGTH(A)

    FOR i = n - 1 DOWNTO 1:
        SWAP A[0] and A[i]  # Move the root (largest element) to the end
        HEAPIFY(A, i, 0)    # Heapify the reduced heap

