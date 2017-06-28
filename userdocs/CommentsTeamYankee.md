

# Comments

## Lee Torgerson & Justin Ridings

### June 28th, 2017


1. Created Database Softball

1. Created Tables:
	- Calendar(CalendarID(PK), TeamId, TeamName, Time, Date, Location)
		- Calendar meant to track dates, locations and times for player games
	- Member(MemberID(PK), First Name, Last Name, Position, PhoneNum, Picture, Username, Password, TeamID, Role)
		- Member is the base table that we use for player, coaches and admin data, and also is associated with the individuals themselves. Roles are relevant to what users can access
	- Pics(pictureID(PK), MemberID, TeamID, Description)
		- Pictures was created as a possible add-on in the future that can display profile pictures, etc.
	- Profiles(MemberID(PK), Username, Password, Image)
		- Created originally so that we could track members, although later on decided to use the member table for everything
	- Stats(MemberID(PK), teamID, hr, rbi, strikeouts, battavg)
		- Created so that we can track players by member id to store stats based off of the game

1. Added Data:
	- Manually entered sample data into members and calendar		
	- Created 8 users; 1 admin, 1 coach, and 6 users

1. Wrote Queries:
	- SELECT COUNT(1) FROM [Member] WHERE (([Username] = '"+user+"') AND ([Password] = '"+pass+"'))
	- Used to verify the login of users into the website; 
	- INSERT INTO [Member] ([First Name], [Last Name], [PhoneNum], [Username], [Password]) 
	VALUES ('" + f + "','" + l+ "','" + ph+ "','" + u + "', '" + pa + "')
	- Used to create an account to access the website
	- SELECT[time] FROM[Calendar] WHERE(TeamName = '" + DropDownList1.SelectedItem.Text + "') 
	AND [date] = '" + year + "-" + month + "-" + day + "';
	- Used to Return TIME data into a physical representation of the Calendar
	- Select[location] from [Calendar] WHERE (TeamName = '" + DropDownList1.SelectedItem.Text + "') 
	AND [date] = '" + year + "-" + month + "-" + day + "';
	- Used to return Location data into a physical representation of the Calendar