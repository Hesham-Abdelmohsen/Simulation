

import random

avg_weekly_profit = []

for orders in range(2):
    stock = 0
    profit = []
    for week in range(500):
        demand = random.randint(0, 4)
        stock = stock + (orders + 1)

        if demand > stock:
            cost = (demand - stock) * 100
        else:
            cost = (stock - demand) * 50

        pc_sold = min(demand, stock)
        gross_profit = pc_sold * 450
        profit.append(gross_profit - cost)
        stock = abs(stock - demand)

    avg_weekly_profit.append(sum(profit) / len(profit))

print(avg_weekly_profit)

print("Average weekly profit for ordering 1 unit per week is : ", avg_weekly_profit[0])
print("Average weekly profit for ordering 2 unit per week is : ", avg_weekly_profit[1])
