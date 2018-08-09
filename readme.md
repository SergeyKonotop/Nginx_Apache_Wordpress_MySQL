Rules:
•	You a not allowed to use GALAXY packages
•	Must be shipped as IaaC solution. 
Everything, including creating DB tables and populating them with data must be automated with Ansible and shipped as an IaaC solution.
•	Don’t overengineer and “keep it simple”. You don’t need to code your own application, just find example apps using Google.

task:
•	Automate a three-tier application
Create a traditional three-tier application with Frontend, Backend and DB tier. You are free to choose a tool/technology for each of layer. 
List of recommended tools:
Frontend: Nginx, Apache, $your_choice(if you an expert)
Backend: Apache, Tomcat, JBoss, Java, Django, rails, $your_choice(if you an expert)
DB: MySQL, Postgres, MongoDB
•	Multiple Environments
Your playbooks should be configured with 2 different environments. They should use the same role!
STAGING: 
* set global environment variable ENVIRONMENT = STAGING (you should see this variable when you run 'env' on your virtual server's shell)
* database password “password”
PRODUCTION:  
* global env variable ENVIRONMENT = PRODUCTION
* database password “Iwi11NeV3RevEeU$3defaultPA$$WORDS”
* extra users for DB (usernames: ecommerce-{{n}}, passwords: “pa$$wd{{n}}”, n = 1..5)
•	“Fault Tolerant” setup: 
Clustered Backend or at least 2 instances of the backend application running at the same time
Frontend load balancing requests to the Backend
•	High Available DB setup:
2 DB instances with master-slave replication.
•	HTTPS between Frontend and Backend
Secure the connection between Frontend and Backend

