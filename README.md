# python-tuples

#open file
name = raw_input("Enter file:")
handle = open(name)

#read the exact time and create a list
for line in handle:
   if line.startswith("From") and not line.startswith("From:"):
       words = line.split()
       time = words[5]
       exacttime = time[:2]
counts = dict()

#create a dictionary from a list
for i in exacttime:
  counts[i] = counts.get(i,0)+1

#reverse the key and value
lst = list()
for key,val in counts.items():
  lst.append((val,key))

#list in the reverse order
lst.sort(reverse = True)

#print the key & val
for val,key in lst:
  print key,val
   