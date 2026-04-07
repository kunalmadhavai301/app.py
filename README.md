#!/bin/bash

file="book.txt"

while true
do
echo "1.Create  2.View  3.Insert  4.Delete  5.Modify  6.Exit"
read ch

case $ch in

1) touch $file
   echo "Created"
   ;;

2) cat $file
   ;;

3) echo "Enter name:"
   read n
   echo "Enter phone:"
   read p
   echo "$n $p" >> $file
   ;;

4) echo "Enter name to delete:"
   read n
   grep -v "$n" $file > temp
   mv temp $file
   ;;

5) echo "Enter name to modify:"
   read n
   grep -v "$n" $file > temp
   mv temp $file
   echo "Enter new name:"
   read n1
   echo "Enter new phone:"
   read p1
   echo "$n1 $p1" >> $file
   ;;

6) break
   ;;

*) echo "Wrong choice"
   ;;

esac
done
