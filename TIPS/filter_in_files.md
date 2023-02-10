I needed to use a filter in a json file that me bring only the values of the field "Usuario".

For this i used the command below:

~~~
cat teste.json | jq '.[].usuario' | sed 's/"//g'
~~~
