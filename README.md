# Vrantika-Br-Samosir
String LOGIN = “admin”;
String PASSWORD = “admin123”;
	
	Class.forName(DRIVER);//Make connection to DB
		Connection connection = DriverManager.getConnection(DataURL, LOGIN, PASSWORD);

String Username = request.getParameter(“USER”); // From HTTP request
String Password = request.getParameter(“PASSWORD”); // From HTTP request
	
	int iUserID = -1;
		
String sLoggedUser = “”;
String sel = “SELECT User_id, Username FROM USERS WHERE Username = ‘” +Username + “‘ AND Password = ‘” + Password + “‘”;

	Statement selectStatement = connection.createStatement ();
		ResultSet resultSet = selectStatement.executeQuery(sel);

			if (resultSet.next()) {
			iUserID = resultSet.getInt(1);
			sLoggedUser = resultSet.getString(2);

	}PrintWriter writer = response.getWriter ();if (iUserID >= 0) {
	writer.println (“User logged in: ” + sLoggedUser);

} else {


writer.println (“Access Denied!”)
