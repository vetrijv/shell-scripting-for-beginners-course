# Lab For Loop

  - Take me to the [Lab](https://kodekloud.com/topic/lab-for-loops/)


  1. Solution is given below

     <details>

     ```
     for mission in lunar-mission mars-mission jupiter-mission saturn-mission mercury-mission
     do
        bash /home/bob/create-and-launch-rocket $mission
     done
     ```
     </details>

  2. Solution is given below

     <details>

     ```
     for mission_name in $(cat /tmp/assets/mission-names.txt)
     do
         bash /home/bob/create-and-launch-rocket $mission_name
     done
     ```
     </details>

  3. Solution is given below

     <details>

     ```
     for i in {31..40}
     do
             echo $i
     done

     ```
     </details>

  4. Solution is given below

     <details>

     ```
     echo -e " Log name   \t      GET      \t      POST    \t   DELETE "
     echo -e "------------------------------------------------------------"
     
     for app in $(cat /tmp/assets/apps.txt)
     do
       get_requests=$(cat /var/log/apps/${app}_app.log | grep "GET" | wc -l)
       post_requests=$(cat /var/log/apps/${app}_app.log | grep "POST" | wc -l)
       delete_requests=$(cat /var/log/apps/${app}_app.log | grep "DELETE" | wc -l)
       echo -e " ${app}    \t ${get_requests}    \t    ${post_requests}   \t   ${delete_requests}"
     
     done
     ```
     </details>

  5.
Question 
We have some images under the directory /home/bob/images. Develop a script /home/bob/rename-images.sh to rename all files within the images folder that has extension jpeg to jpg. A file with any other extension should remain the same.


Tip: Use a for loop to iterate over the files within /home/bob/images

Tip: Use an if conditional to check if the file extension is jpeg.

Tip: Use mv to rename a file.

To replace jpeg to jpg in a filename use echo user1.jpeg | sed 's/jpeg/jpg/g'.

Solution is given below

     <details>

     ```
     for file in $(ls images)
     do
             if [[ $file = *.jpeg ]]
                     then
                     new_name=$(echo $file| sed 's/jpeg/jpg/g')
                     mv images/$file images/$new_name
             fi
     done
     ```
     </details>
