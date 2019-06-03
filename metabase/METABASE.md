**Get starting with METABASE:**

- download Metabase here: http://schnautzi.gavagai.nl:8080/metabase-v0.32.4.jar

- move that file to your folder that you want:

  this is a example of mine: 

  ``` 
  $ mv Downloads/metabase-v0.32.4.jar /home/ony/Devel/database/metabase
  ```

- cd into directory and then dump the database of metabase

  ```
  $ $ cd Devel/database/metabase
  $ MB_DB_CONNECTION_URI="postgres:///metabase?user=ony&host=/run/postgresql" MB_JETTY_PORT="3003" MB_JETTY_HOST="0.0.0.0" MB_EMOJI_IN_LOGS="false" java -jar metabase-v0.32.4.jar
  ```

  

- Run this command as a  run the server of metabase in locally:

  ````
  $ java -jar metabase-v0.32.4.jar
  ````

- Go to the browser then run locally with this port:

  ```
  https://localhost:30303
  ```

  ```
  $ socat TCP-LISTEN:5433,reuseaddr,fork UNIX-CONNECT:/run/postgresql/.s.PGSQL.5432
  ```


  **Note:** That there are newer versions available but I haven't downloaded them. Thanks!

