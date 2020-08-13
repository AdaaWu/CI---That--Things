# PHP CI Model



###### tags: `封裝查詢`


在Model 撰寫查詢語法時，

為了能避免SQL Injection，
會對參數做一個處理，或則SQL組合時，也都會字串與變數連接，

但不好維護，也麻煩。

 

使用封裝查詢，就不必字串與變數交叉連接，
也會自動幫你防SQL Injection，會是比較好的辦法

PDO

```
//較不好

$sql = "SELECT 
            * 
        FROM 
            some_table 
        WHERE 
            id = ? 
        AND 
            status = ? 
        AND 
            author = ?"; 
```



```
//較安全

$this->db->query($sql, array(3, 'live', 'Rick'));
```