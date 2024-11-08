# Minimum-Erasures-for-Multiple-of-3

In a land of numbers, you are entrusted with a magical number N, composed only of digits from 1 to 9. The number has k digits, and your quest is to create a multiple of 3 by erasing at least 0 but no more than k-1 digits, while keeping the remaining digits in the same order. Your challenge is to determine if it's possible to form a multiple of 3 in this way. If it is, figure out the minimum number of digits that need to be erased. If the task is impossible, return -1.


def min_erasures_to_multiple_of_3(N):
    num = str(N)
    length = len(num)
    total_sum = sum(int(ch) for ch in num)

    if total_sum % 3 == 0:

    remainder = total_sum % 3
    count_remainder1 = 0
    count_remainder2 = 0

    for ch in num:
        digit = int(ch)
        if digit % 3 == 1:
            count_remainder1 += 1
        elif digit % 3 == 2:
            count_remainder2 += 1

    if remainder == 1:
        if count_remainder1 >= 1 and length > 1:
            return 1
        elif count_remainder2 >= 2 and length > 2:
            return 2
    elif remainder == 2:
        if count_remainder2 >= 1 and length > 1:
            return 1
        elif count_remainder1 >= 2 and length > 2:
            return 2

    return -1

N = int(input().strip())
print(min_erasures_to_multiple_of_3(N))

