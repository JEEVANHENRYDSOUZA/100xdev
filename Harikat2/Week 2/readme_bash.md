### What is terminal 
- Terminal is another interface using which you can do things on your computer 
### Some Important Bash Commands
1. pwd - print working directory
2. cd- change directory ----- cd .. goes back 
3. ls - listing all the files in the current folder
4. mkdir - make directory 
5. touch - create files
6. cat - prints  content of a file 
7. vi - lets you to edit files ----- press i for insert mode 
      esc to escape out of insert mode 
8. mv - move files 
9. cp - copy files  
    cp file name path 
10. node - starts a shell
     node file_name will run  the file 
11. npm - there are certain packages which are not available locally but are present in
         some other registry ,  we need to then bring those pacakges to our local machine
         for that we use npm intall pacakge_name
12. Curl Command
-   The `curl` command is a versatile command-line tool for making HTTP requests. It is available on various operating systems, including Linux, macOS, and Windows. Here are some common use cases of the `curl` command:

1. **Simple GET Request:**
   - To make a simple GET request to a URL:

   ```bash
   curl https://example.com
   ```

2. **Save Output to a File:**
   - To save the output of a request to a file:

   ```bash
   curl -o output.html https://example.com
   ```

3. **Follow Redirects:**
   - To follow HTTP redirects:

   ```bash
   curl -L https://example.com
   ```

4. **HTTP Headers:**
   - To include custom HTTP headers:

   ```bash
   curl -H "Authorization: Bearer TOKEN" https://api.example.com/data
   ```

5. **POST Request:**
   - To make a POST request with data:

   ```bash
   curl -X POST -d "key1=value1&key2=value2" https://example.com/resource
   ```

6. **JSON POST Request:**
   - To make a POST request with JSON data:

   ```bash
   curl -X POST -H "Content-Type: application/json" -d '{"key": "value"}' https://example.com/api
   ```

7. **Authentication:**
   - To include authentication credentials:

   ```bash
   curl -u username:password https://example.com/secure-resource
   ```

8. **Show Request and Response Headers:**
   - To display both request and response headers:

   ```bash
   curl -v https://example.com
   ```

9. **Insecure (ignore SSL verification):**
   - To make a request without verifying SSL certificates:

   ```bash
   curl -k https://example.com
   ```

10. **Upload File:**
    - To upload a file in a POST request:

    ```bash
    curl -X POST -F "file=@localfile.txt" https://example.com/upload
    ```

11. **Download File with Progress Bar:**
    - To download a file with a progress bar:

    ```bash
    curl -o output.zip -# https://example.com/file.zip
    ```

12. **Set Request Timeout:**
    - To set a request timeout:

    ```bash
    curl --max-time 10 https://example.com
    ```


