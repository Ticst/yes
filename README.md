    accounts = {}
    while True:
        print("What do you want to do?")
        print("Login(l)/Registe(r)")
        choice = input(">")
    
        def register():
            print("---register---")
    
            username = input("Enter username: ")
            if username in accounts:
                print("username already taken ")
            else:
                password = input("Enter password: ")
                accounts[username] = {"password": password, "status": "on", "admin": "off"}
    
        def login():
            print("---login---")
            username = input("Enter username: ")
            password = input("Enter password: ")
            if username in accounts and accounts[username]["password"] == password:
                print("Login successful!")
            else:
                print("Invalid login.")
    
        def status():
            print("---status---")
            username = input("Enter username: ")
            password = input("Enter password: ")
            if username in accounts and accounts[username]["password"] == password:
                stat=accounts[username]["status"]
                print("youe current status is",stat ,"\ndo you want to change your status?")
                valt=input(">")
                if valt=="yes":
                    newstat="off" if stat=="on" else "on"
                    accounts[username]["status"]=newstat
                    print("you changed your status to",newstat)
                else:
                    print("okay no changes have been done")
            else: (print("wrong password or user"))
        def admin():
            print("---admin---")
            username = input("Enter username: ")
            password = input("Enter admin password: ")
            if username in accounts and "156379" == password:
                adminr=accounts[username]["admin"]
                print("youe current status is",adminr ,"\ndo you want to change your status?")
                valtl=input(">")
                if valtl=="yes":
                    newadmin="off" if adminr=="on" else "on"
                    accounts[username]["admin"]=newadmin
                    print("you changed your status to",newadmin)
                else:
                    print("okay no changes have been done")
        def user_list():
            print("--- All Users and Statuses ---")
            if not accounts:
                print("No users registered yet.")
                return
    
            for username, info in accounts.items():
                print("user:",username,"status:",info["status"],"admin",info["admin"])
    
        if choice == "r":
            register()
        elif choice == "l":
            login()
        elif choice == "s":
            status()
        elif choice == "list":
            user_list()
        elif choice == "1234":
            admin()
        elif choice == "q":
            break
        else: print("invalid option")
