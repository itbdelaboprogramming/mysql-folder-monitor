# MySQL Folder Monitor
Synchronize local folder to MySQL database

## How to Run
1. Make sure python 3.8.10 is installed
2. Clone this repository in ~/ directory
```bash
git clone https://github.com/itbdelaboprogramming/mysql-folder-monitor.git
```
3. cd to the repository folder
```bash
cd mysql-folder-monitor
```

4. Install requirements
```bash
pip install -r requirements.txt
```

5. Create a config.py file
```bash
# create a config.py file inside mysql-folder-monitor directory
# add this line, change and fill accordingly
DIRECTORY_TO_WATCH = "/path/to/directory/to/watch"
MYSQL_HOST = ""
MYSQL_DATABASE = ""
MYSQL_USER = ""
MYSQL_PASS = ""
```

6. Run the program in Systemd background service (auto on when computer starts)
```bash
# open mysql_folder_monitor.service and change <username>
# then follow these steps:
sudo cp mysql-folder-monitor.service /etc/systemd/system/   # copy service file
sudo systemctl daemon-reload                                # reload daemon
sudo systemctl enable mysql-folder-monitor.service          # auto on
sudo systemctl start mysql-folder-monitor.service           # start service
```