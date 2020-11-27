fileIn = open('datafile1.dat', 'r')
fileOut = open('output.html','w')
data=[]
lines = fileIn.read().splitlines()
for line in lines:
     transactionRecord = line.split('_')
     data.append(transactionRecord)
print('%-20s%-30s%5s%10s'%('Name','Address','Txn', 'Ampunt'))
print('='*65)
for e in data:
     print('%-20s%-30s%5s%10s'%(e[0], e[1], e[2], e[3]))

fileOut.write('''
|Name|Adress|Txn|Amount|
|--  |--    |-- |--    |
''')
for e in data:
    fileOut.write('|'+e[0]+'|'
    + e[1] + '|'
    + e[2] +'|'
    + e[3] + '|' +'\n' )
fileIn.close()
fileOut.close()