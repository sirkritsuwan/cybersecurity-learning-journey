
- open and close phase
```
<?php    //start

?>       //close
```

- variable
`$' : can use with every data type

- display
  ```
  echo "abc <br>";

  // can use "" or ''
  //<br> : break / next line

  ex.
  $name = "Alice"
  $account = "123-456"
  $balance = 2336.33
  $active = true

  echo $name;
  echo "Account {$account} <br>";
  echo "Balance \${$balance}";       // use '\' to separate confusion of '$'
  echo "Active Status {$active}";    // true = 1, false = display nothing
  ```

- operator
  : just like C and others languadges


// short cut  [ ! + tap = html form ]


  - special variable
    : collect data from html then send to php
    ```
    $_GET  // not secure ***
              char limit
              for search page
              GET requests can be crash
    $_POST // more secure
              no data limit
              for submitting credentials ***
              requests are not crash
    ```


    - `GET`
      ```
        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Document</title>
        </head>
        <body>
            <form action="index.php" method="get">        // <-- **** define GET method use action from "index.php"
                <leble>username: </leble><br>
                <input type="text" name="username"><br>
                <leble>password: </leble><br>
                <input type="text" name="password"><br>
                <input type="submit" value="Log in"><br>
            </form>
        </body>
        </html>
        
        <?php
            echo "{$_GET["username"]} <br>";        // <-- **** GET variable
            echo $_GET["password"] . "<br>";        // and different way to use "<br>"
        ?>
      ```
      
      <img width="687" height="341" alt="image" src="https://github.com/user-attachments/assets/57460c1c-66f9-49d1-a351-e9cffb39e653" />


    - `POST`
      ```
        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Document</title>
        </head>
        <body>
            <form action="index.php" method="post">        // <-- **** define POST method use action from "index.php"
                <leble>username: </leble><br>
                <input type="text" name="username"><br>
                <leble>password: </leble><br>
                <input type="text" name="password"><br>
                <input type="submit" value="Log in"><br>
            </form>
        </body>
        </html>
        
        <?php
            echo "{$_POST["username"]} <br>";        // <-- **** POST variable
            echo $_POST["password"] . "<br>";
        ?>
      ```
      
      <img width="465" height="338" alt="image" src="https://github.com/user-attachments/assets/ebd8c530-94ae-4c55-a4e1-f1a3d90af021" />

