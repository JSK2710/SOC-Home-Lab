# SSH log analysis with dashboard

# Adding Data

- Settings → add data

![image.png](image.png)

- Click on upload

![image.png](image%201.png)

- Select the file

![image.png](image%202.png)

- Click on next then keep the source type default and next

 

![image.png](image%203.png)

- Change the hostname field to LinuxServer.
- Click next and start search.

![image.png](image%204.png)

- The logs are displayed

![image.png](image%205.png)

# Creating a dashboard

Click on the dashboards tab

![image.png](image%206.png)

Click on create new dashboards

![image.png](image%207.png)

Give a title and select classic dashboards and select create

![image.png](image%208.png)

## Creating a time range button

- Click on Add Input and Select Time

![image.png](image%209.png)

- Click on pencil icon Set Label to `Time Range` and Token `time_range`

![image.png](image%2010.png)

- Again Add Input and Select Submit

![image.png](image%2011.png)

- Save it

![image.png](image%2012.png)

## **Overview Panels**

### Total SSH Events

- Click on Edit
- Click on Add Panel
- Under New, choose Single Value
- Use Shared Time Picker `time_range`
- Set Content Title to "Total SSH Events"
- Enter the Search String as below

```bash
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json"
 | stats count AS "Total SSH Events"
```

![image.png](image%2013.png)

Successful Logins

Repeat the above steps change these values

- Set **Content Title** to `"Successful Logins"`
- Enter the **Search String** as below:

```bash
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json" event_type="Successful SSH Login" 
| stats count AS "Successful Logins"
```

![image.png](image%2014.png)

### **Failed Logins**

Repeat the steps of Total SSH Events change these values

- Set **Content Title** to `"Failed Logins"`
- Enter the **Search String** as below:

```
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json" event_type="Failed SSH Login"
| stats count AS "Failed Login"
```

![image.png](image%2015.png)

### **Connection without Authentication**

Repeat the steps of Total SSH Events change these values

- Set **Content Title** to `"Invalid User Attempts"`
- Enter the **Search String** as below:

```
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json" event_type="Connection Without Authentication" 
 | stats count AS "Connection Without Authentication"
```

![image.png](image%2016.png)

## **Login Activity Trends Pannels**

### **Failed Logins by username**

- Click on **Add Panel**
- Under **New**, choose **Bar Chart**
- Use **Shared Time Picker** `time_range`
- Set **Content Title** to `"Failed Logins by username"`
- Enter the **Search String** as below:

```
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json" event_type="Failed SSH Login" | top username
```

![image.png](image%2017.png)

### **Possible Brute Force**

- Click on Add Panel
- Under New, choose Statstics Table
- Use Shared Time Picker `time_range`
- Set Content Title to `Possible Brute Force IP Address`
- Enter the Search String as below:

```bash
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json" event_type="Multiple Failed Authentication Attempts" | top id.orig_h
```

![image.png](image%2018.png)

## **Visualizing Brute Force attack in geo-location**

Visualizing Brute Force attack with geo-location

- Click on Add Panel
- Under New, choose Choropleth Map
- Use Shared Time Picker time_range
- Set Content Title to Brute Force attack with geo-location
- Enter the Search String as below:

```bash
source="ssh_logs_new.json" host="LinuxServer" sourcetype="_json" event_type="Multiple Failed Authentication Attempts" 
| table id.orig_h
| iplocation id.orig_h
| stats count by Country
| geom geo_countries featureIdField="Country"
```

![image.png](image%2019.png)

After adding some colors the dashboard looks like this.

![image.png](image%2020.png)

### References

- [https://haxcamp.com/projects/f9b81d66-d338-4b82-8faf-437222b5e325/resources](https://haxcamp.com/projects/f9b81d66-d338-4b82-8faf-437222b5e325/resources)
