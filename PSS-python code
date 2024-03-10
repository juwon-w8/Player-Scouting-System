import sqlite3
import sys

conn = sqlite3.connect('player.db')

c = conn.cursor()
#This is where each table is made. If the data base is deleted to create a new database uncomment this code.
#After the code is run that first time comment the code out again otherwise there will be an error because
#all the tables above would have been created again.
#c.execute("""CREATE TABLE Players(
#            name text,
#            height real,
#            ID text,
#            position text,
#            age integer,
#            games_played integer,
#            mins_per_game real,
#            assists real,
#            goals integer,
#            shots_per_game real,
#            shot_conversion_rate real,
#            chances_created real
#)""")

#c.execute("""CREATE TABLE Defenders(
#            name text,
#           height real,
#            ID text,
#            position text,
#            age integer,
#            games_played integer,
#            mins_per_game real,
#            assists real,
#            goals integer,
#            tackle_success real,
#            ariel_duel_success real,
#            passes_completed integer,
#            short_passes integer,
#            long_passes integer,
#            interceptions_per_game real,
#            blocks_per_game real
# )""")
#c.execute("""CREATE TABLE Midfielders(
#           name text,
#           height real,
#            ID text,
#            position text,
#            age integer,
#            games_played integer,
#            mins_per_game real,
#            assists real,
#            goals integer,
#            tackle_success real,
#            ariel_duel_success real,
#            passes_completed integer,
#            short_passes integer,
#            long_passes integer,
#            keypasses_game real,
#            chances_created_game real
# )""")

def password_check():
    for i in range (3):
        pw="848484"
        password= input("Please enter password" )
        if password==pw:
            return True
    return False

def main():
    if password_check():
        ctrl = True
        while ctrl == True:
            print("Would you like to view player data or edit player data?(1=View/2=Edit)")
            c1 = input("Enter your choice 1:to View data/2:to Edit data")
            if c1 == "2":
                print("Would you like to Add or delete player data")
                cc2 = input("Enter choice 1:Add info/2:Delete")
                if cc2 == "1":
                    print("Which list would you like to Edit")
                    ccc3 = input("Enter 1: for Forwards/2:for Midfielders/3:for Defenders ")
                    if ccc3 == "1":

                        cc = True
                        cc1= True

                        while cc == True:
                            fname = input("Please enter Name ")
                            fheight = input("Please enter Height ")
                            fID = input("Please enter ID ")
                            fposition = input("Please enter position ")
                            fage = input("Please enter age ")
                            fgames_played = input("Please enter games played")
                            fmins_per_game = input("Please enter minutes per game")
                            fassists = input("Please enter assists ")
                            fgoals = input("Please enter goals ")
                            fshots_per_game = input("Please enter shots per game ")
                            fshot_conversion_rate = input("Please enter shot conversion rate ")
                            fchances_created = input("Please enter chances created ")
                            c.execute("""
                                INSERT INTO Players(name,
                                            height,
                                            ID,
                                            position,
                                            age,    
                                            games_played,
                                            mins_per_game,
                                            assists,
                                            goals,
                                            shots_per_game,
                                            shot_conversion_rate,
                                            chances_created) VALUES (?,?,?,?,?,?,?,?,?,?,?,?)""", (
                                fname, fheight, fID, fposition, fage, fgames_played, fmins_per_game, fassists, fgoals,
                                fshots_per_game, fshot_conversion_rate, fchances_created))
                            op1 = input("Would you like to enter more player data?(Yes/No)")
                            if op1 == "Yes":
                                cc = True
                            elif op1 == "No":
                                op4 = input("Would you like to see current forward rankings?(Yes/No) ")
                                if op4 == "Yes":
                                    fsort = "SELECT*FROM Players ORDER BY goals DESC"
                                    c.execute(fsort)
                                    data = c.fetchall()
                                    print("Forward rankings")
                                    for x in data:
                                        print(x)
                                    conn.commit()
                                elif op4 == "No":
                                    ctrlch = input("Would you like to continue using this application(Yes/No) ")
                                    if ctrlch == "Yes":
                                        ctrl = True
                                    elif ctrlch == "No":
                                        ctrl = False

                                cc = False
                            conn.commit()
                    elif ccc3 == "2":
                     cc1 = True
                     while cc1 == True:
                        mname = input("Please enter Name ")
                        mheight = input("Please enter Height ")
                        mID = input("Please enter ID ")
                        mposition = input("Please enter position ")
                        mage = input("Please enter age ")
                        mgames_played = input("Please enter games played")
                        mmins_per_game = input("Please enter minutes per game")
                        massists = input("Please enter assists ")
                        mgoals = input("Please enter goals ")
                        mtackle_success = input("Please enter tackle success rate ")
                        mariel_duel_success = input("Please enter ariel duel win percentage ")
                        mpasses_completed = input("Please enter passes completed ")
                        mshort_passes = input("Please enter short passes completed ")
                        mlong_passes = input("Please enter long passes completed ")
                        mkeypasses_game = input("Please enter key passes per game ")
                        mchances_created = input("Please enter chances created ")
                        c.execute("""
                                            INSERT INTO Midfielders(name,
                                            height,
                                             ID,
                                            position,
                                            age,    
                                            games_played,
                                            mins_per_game,
                                            assists,
                                            goals,
                                            tackle_success,
                                            ariel_duel_success,
                                            passes_completed,
                                            short_passes,
                                            long_passes,
                                            keypasses_game,
                                            chances_created_game) VALUES (?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?)""",
                                  (
                                      mname, mheight, mID, mposition, mage, mgames_played, mmins_per_game, massists,
                                      mgoals,
                                      mtackle_success,
                                      mariel_duel_success, mpasses_completed, mshort_passes, mlong_passes,
                                      mkeypasses_game,
                                      mchances_created))
                        op2 = input("Would you like to enter more player data?(Yes/No)")
                        if op2 == "Yes":
                            cc = True
                        elif op2 == "No":
                            op4 = input("Would you like to see current midfielder rankings?(Yes/No) ")
                            if op4 == "Yes":
                                msort = "SELECT*FROM Midfielders ORDER BY keypasses_game DESC"
                                c.execute(msort)
                                data1 = c.fetchall()
                                print("Midfielder rankings")
                                for y in data1:
                                    print(y)
                                    conn.commit()
                            elif op4 == "No":
                                ctrlch = input("Would you like to continue using this application(Yes/No) ")
                                if ctrlch == "Yes":
                                    ctrl = True
                                elif ctrlch == "No":
                                    ctrl = False

                                cc1 = False
                                conn.commit()

                    elif ccc3 == "3":
                            cc3 = True
                            while cc3 == True:
                                dname = input("Please enter Name ")
                                dheight = input("Please enter Height ")
                                dID = input("Please enter ID ")
                                dposition = input("Please enter position ")
                                dage = input("Please enter age ")
                                dgames_played = input("Please enter games played")
                                dmins_per_game = input("Please enter minutes per game")
                                dassists = input("Please enter assists ")
                                dgoals = input("Please enter goals ")
                                dtackle_success = input("Please enter tackle success rate ")
                                dariel_duel_success = input("Please enter ariel duel win percentage ")
                                dpasses_completed = input("Please enter passes completed ")
                                dshort_passes = input("Please enter short passes completed ")
                                dlong_passes = input("Please enter long passes completed ")

                                c.execute("""
                                                    INSERT INTO Defenders(name,
                                                                height,
                                                                ID,
                                                                position,
                                                                age,    
                                                                games_played,
                                                                mins_per_game,
                                                                assists,
                                                                goals,
                                                                tackle_success,
                                                                ariel_duel_success,
                                                                passes_completed,
                                                                short_passes,
                                                                long_passes) VALUES (?,?,?,?,?,?,?,?,?,?,?,?,?,?)""", (
                                    dname, dheight, dID, dposition, dage, dgames_played, dmins_per_game, dassists,
                                    dgoals,
                                    dtackle_success,
                                    dariel_duel_success, dpasses_completed, dshort_passes, dlong_passes))

                                op3 = input("Would you like to enter more player data?(Yes/No) ")

                                if op3 == "Yes":
                                    cc3 = True
                                elif op3 == "No":
                                    op2 = input("Would you like to see current defender rankings?(Yes/No) ")
                                    if op2 == "Yes":
                                        dsort = "SELECT*FROM Defenders ORDER BY tackle_success DESC"
                                        c.execute(dsort)
                                        data2 = c.fetchall()
                                        print("Defender rankings")
                                        for z in data2:
                                            print(z)
                                        conn.commit()
                                    elif op2 == "No":
                                        ctrlch = input("Would you like to continue using this application(Yes/No) ")
                                        if ctrlch == "Yes":
                                            ctrl = True
                                        elif ctrlch == "No":
                                            ctrl = False

                                    cc3 = False
                                conn.commit()
                elif cc2 == "2":
                    print("Which list would you like to delete a player from? ")
                    del_sel = input("Enter 1: for Forwards/2:for Midfielders/3:for Defenders ")
                    if del_sel == "1":
                        del_command = "DELETE FROM Players WHERE name=?"
                        del_name = (input("Enter name of player you would like to delete "),)
                        c.execute(del_command, del_name)
                        conn.commit()
                        ctrlch = input("Would you like to continue using this application(Yes/No) ")
                        if ctrlch == "Yes":
                            ctrl = True
                        elif ctrlch == "No":
                            ctrl = False
                    elif del_sel == "2":
                        del_command = "DELETE FROM Midfielders WHERE name=?"
                        del_name = (input("Enter name of player you would like to delete "),)
                        c.execute(del_command, del_name)
                        conn.commit()
                        ctrlch = input("Would you like to continue using this application(Yes/No) ")
                        if ctrlch == "Yes":
                            ctrl = True
                        elif ctrlch == "No":
                            ctrl = False
                    elif del_sel == "3":
                        del_command = "DELETE FROM Defenders WHERE name=?"
                        del_name = (input("Enter name of player you would like to delete "),)
                        c.execute(del_command, del_name)
                        conn.commit()
                        ctrlch = input("Would you like to continue using this application(Yes/No) ")
                        if ctrlch == "Yes":
                            ctrl = True
                        elif ctrlch == "No":
                            ctrl = False

            elif c1 == "1":
                fsort = "SELECT*FROM Players ORDER BY goals DESC"
                c.execute(fsort)
                data = c.fetchall()
                print("Forward rankings")
                for x in data:
                    print(x)
                conn.commit()

                msort = "SELECT*FROM Midfielders ORDER BY keypasses_game DESC"
                c.execute(msort)
                data1 = c.fetchall()
                print("Midfielder rankings")
                for y in data1:
                    print(y)
                conn.commit()

                dsort = "SELECT*FROM Defenders ORDER BY tackle_success DESC"
                c.execute(dsort)
                data2 = c.fetchall()
                print("Defender rankings")
                for z in data2:
                    print(z)
                conn.commit()

                ctrlch = input("Would you like to continue using this application(Yes/No) ")
                if ctrlch == "Yes":
                    ctrl = True
                elif ctrlch == "No":
                    ctrl = False


    else:
        sys.exit()


if __name__=='__main__':
    main()
