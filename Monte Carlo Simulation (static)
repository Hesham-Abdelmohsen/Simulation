

import numpy
import random
import matplotlib.pyplot as plt

# arrays of first simulation

f_arr = []  # profit array
f_c1_arr = []
f_c2_arr = []
f_x_arr = []

# arrays of second simulation

s_arr = []  # profit array
s_c1_arr = []
s_c2_arr = []
s_x_arr = []


def Generate_C1():
    r1 = random.random()

    if r1 < 0.1:
        return (43)
    elif r1 < 0.3:
        return (44)
    elif r1 < 0.7:
        return (45)
    elif r1 < 0.9:
        return (46)
    else:
        return (47)


def Generate_C2():
    r2 = random.random()  # generate random between 0 and 1
    c2 = 80 + (r2 * 20)
    return c2


def Generate_X():
    x = numpy.random.normal(loc=15000, scale=4500)
    return x


def simulation(num_trial, arr, c1_arr, c2_arr, x_arr):
    unit_price = 249
    fixed_cost = 1000000
    number_of_trials = num_trial

    for i in range(number_of_trials):
        c1 = Generate_C1()
        c2 = Generate_C2()
        x = Generate_X()

        c1_arr.append(c1)
        c2_arr.append(c2)
        x_arr.append(x)

        profit = (unit_price - c1 - c2) * x - fixed_cost
        arr.append(profit)


def calculations(num_trial, arr):
    max_num = max(arr)

    if max_num > 0:
        print("maximum profit     = ", max_num)
    else:
        print("maximum profit     = 0")

    min_num = min(arr)
    if min_num < 0:
        print("maximum loss       = ", min_num)
    else:
        print("maximum loss       = 0 ")

    profit_only = [num for num in arr if num > 0]

    averag_profit = sum(profit_only) / len(profit_only)

    print("Average profit     = ", averag_profit)

    loss_only = [num for num in arr if num < 0]

    prob_of_loss = len(loss_only) / num_trial

    print("probability of loss= ", prob_of_loss)


def Histogram(arr, c1_arr, c2_arr, x_arr):
    print("Histogram of profit ")
    plt.hist(arr)
    plt.show()

    print("Histogram of C1 ")
    plt.hist(c1_arr)
    plt.show()

    print("Histogram of C2 ")
    plt.hist(c2_arr)
    plt.show()

    print("Histogram of Demand (x) ")
    plt.hist(x_arr)
    plt.show()


def compare_resullts():
    print("(1)simulation of 10 runs results ")
    print("---------------------------------")
    calculations(10, f_arr)

    print("--------------------------------------")
    print("(2)simulation of 1000000 runs results ")
    print("--------------------------------------")

    calculations(1000000, s_arr)

    print()
    print()
    print("*********************************")
    print("Histograms for 10 run simulation")
    print("--------------------------------")
    Histogram(f_arr, f_c1_arr, f_c2_arr, f_x_arr)
    print("*************************************")
    print("Histograms for 1000000 run simulation")
    print("-------------------------------------")
    Histogram(s_arr, s_c1_arr, s_c2_arr, s_x_arr)


# **********************************
# **********************************

simulation(10, f_arr, f_c1_arr, f_c2_arr, f_x_arr)

simulation(1000000, s_arr, s_c1_arr, s_c2_arr, s_x_arr)

compare_resullts()
