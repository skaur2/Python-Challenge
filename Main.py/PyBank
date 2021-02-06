#first import module
import os

#module to read csv file
import csv
csvpath = os.path.join('..', 'Resources', 'budget_data.csv')

#lists to add csv values to 
total_months = []
net_profit = []
profit_change = []

# Open and read csv
with open("budget_data.csv", newline="") as csvfile:
    csvreader = csv.reader(csvfile, delimiter=",")
    header = next(csvreader)
    
    #iterate values to add to list
    for row in csvreader:
        total_months.append(row[0])
        net_profit.append(int(row[1]))
        
    for i in range(len(net_profit)-1):
        profit_change.append(net_profit[i+1]-net_profit[i])

# review min and max from values
increase = max(profit_change)
decrease = min(profit_change)

# check index
monthly_increase = profit_change.index(max(profit_change))+1
monthly_decrease = profit_change.index(min(profit_change))+1

# print results
print("Financial Analysis")
print("-------------------")
print(f"Total Months:{len(total_months)}")
print(f"Total: ${sum(net_profit)}")
print(f"Average Change:{round(sum(profit_change)/len(profit_change),2)}")
print(f"Greatest Increase in Profits: {total_months[monthly_increase]} (${(str(increase))})")
print(f"Greatest Decrease in Profits: {total_months[monthly_decrease]} (${(str(decrease))})")

# export text file of results
output = "output.txt"
with open("output","w") as new:
    new.write("Financial Analysis")
    new.write("\n")
    new.write("--------------------")
    new.write("\n")
    new.write(f"Total Months:{len(total_months)}")
    new.write("\n")
    new.write(f"Total: ${sum(net_profit)}")
    new.write("\n")
    new.write(f"Average Change: {round(sum(profit_change)/len(profit_change),2)}")
    new.write("\n")
    new.write(f"Greatest Increase in Profits: {total_months[monthly_increase]} (${(str(increase))})")
    new.write("\n")
    new.write(f"Greatest Decrease in Profits: {total_months[monthly_decrease]} (${(str(increase))})")
