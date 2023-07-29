
#!/bin/bash

age=25

echo -e "Enter age limit : \c "
read age
echo -e "Enter name  : \c "
 read name

if [ "$age" -gt 18 ] && [ "$age" -lt 60 ]
then
  echo "valid age"
sleep 2
  echo "Hello $name and welcome"
sleep 1
  echo "only 18+ can enter this"
sleep 2
  echo "want to know why?"
sleep 2
  echo "because"
sleep 1
  echo "this"
sleep 1
  echo "is"
sleep 1
  echo "your"
sleep 1
  echo "lucky day"
sleep 2
  echo "to get your mind out the gutter lol :)"
sleep 3
else
  echo "age not valid"
  echo "18 and up required ;)"
fi
