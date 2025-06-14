# -Azure-Incident-Logging-System
This project demonstrates how to build a **serverless, event-driven incident logging system. It uses Azure Queue Storage to hold incident messages, and Logic Apps to automatically process and notify you when new incidents are logged.


## 🧱 How I Built This Project (Step-by-Step)

### 1. Created a Resource Group  
I started by creating a resource group named `IncidentRG` in the Azure Portal to keep all my project resources organized in one place.

---

### 2. Set Up a Storage Account  
Next, I created a storage account called `incidentstore12345` inside that resource group. I chose the standard performance with locally-redundant storage (LRS) for simplicity and free-tier eligibility.

---

### 3. Added a Queue to Store Incidents  
Inside the storage account, I created a new queue named `incidents` — this queue would hold all the incident messages I want to log.

---

### 4. Added a Sample Incident Message  
To test the queue, I manually added a message:  
`🔥 ERROR: CPU over 95% on VM01`  
This simulates how a real system would send alerts or error logs.

---

### 5. Created a Logic App to Process Queue Messages  
Then, I created a Logic App named `ProcessIncidentQueue` on the consumption plan. This serverless workflow listens for new messages in the `incidents` queue.

---

### 6. Designed the Logic App Workflow  
In the Logic App designer, I set a trigger:  
*When a message is received in the queue.*  
Then, I added an action to send myself an email with the incident details whenever a new message arrives.

---

### 7. Set Up Alerts for Queue Overload  
Finally, I added an alert rule in Azure Monitor to notify me by email if the number of messages in the queue exceeds 10 — this helps me monitor if incidents spike.

---

By following these steps, I built a simple but powerful cloud-based incident logging system using only Azure Portal tools, no coding needed!


