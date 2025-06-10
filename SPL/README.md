# Splunk Processing Language (SPL)

A curated collection of essential SPL commands for fast referencing and learning. Each snippet is tailored for real-world use cases in threat hunting, troubleshooting, and data analysis.

## Search Command Reference

### **Search for Specific Error Messages**
**Use case:** Identify events that contain common error keywords.  
**Example SPL:**  
`index=botsv3 ("error" OR "failed" OR "failure")`

---

### **Filter Events by Source IP Address**
**Use case:** Narrow results to events from a specific source IP.  
**Example SPL:**  
`index=botsv3 src_ip="172.16.0.178"`

---

### **Search for Login Failures in a Specific Time Range**
**Use case:** Analyze failed login attempts over a defined historical period.  
**Example SPL:**  
`index=botsv3 EventCode=4625 earliest=-15y latest=-5y`

---

### **Filter by Event Type and Status Code**
**Use case:** Isolate events of a certain type, useful for data model filtering.  
**Example SPL:**  
`index=botsv3 eventtype="cpu" cpu="all"`

---

### **Use Wildcards for Flexible User Filtering**
**Use case:** Find usernames containing specific patterns (e.g. admin access).  
**Example SPL:**  
`index=botsv3 user="*admin*"`

---

### **Search for Events with High Byte Count**
**Use case:** Spot data-heavy events for bandwidth analysis or anomalies.  
**Example SPL:**  
`index=botsv3 bytes>1000000`

---

### **Search for Specific Event IDs**
**Use case:** Focus on relevant Windows Security Events or exclude noise.  
**Example SPL:**  
`index=botsv3 EventCode IN (4624, 4625, 4634)`  
`index=botsv3 NOT EventCode IN (4625)`

---

### **Filter Web Requests by URL Path**
**Use case:** Investigate access to specific web application paths.  
**Example SPL:**  
`index=botsv3 sourcetype=stream:http uri_path="/admin*"`

---

### **Search by Protocol and Application Stack**
**Use case:** Examine traffic for specific cloud providers or stack layers.  
**Example SPL:**  
`index=botsv3 amazon_aws protocol="tcp"`

---

### **Find Events with Googlebot User Agent**
**Use case:** Identify or validate bot traffic from known sources like Google.  
**Example SPL:**  
`index=botsv3 useragent="googlebot*"`

---



