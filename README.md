# JDBC-menu
	
	System.out.println("Menu");
        System.out.println("----------------");
        System.out.println("1. List all writing groups");
        System.out.println("2. List all the data for a group specified by the user");
        System.out.println("3. List all the publishers");
        System.out.println("4. List all the data for a publisher specified by user");
        System.out.println("5. List all book titles");
        System.out.println("6. List all the data for a book specified by the user");
        System.out.println("7. Insert a new book");
        System.out.println("8. Insert a new publisher");
        System.out.println("9. remove a book");

        
        Scanner in = new Scanner(System.in);
        int input = in.nextInt();
        switch(input){
            case 1:
                //method
                break;
            case 2:
                System.out.println("Enter name a group you want to see");
                String user = in.next();
		java.sql.PreparedStatement stmt = connection.PrepareStatement( " SELECT * FROM WritingGroup WHERE GROUPNAME = ?");
                stmt.setString(1,user);
                break;
                
            case 3:
                //method
                break;
            case 4:
                System.out.println("Enter name of publisher you want to see");
                String publisher = in.next();
                java.sql.PreparedStatement stmt = connection.PrepareStatement( " SELECT * FROM publisher WHERE PUBLISHERNAME = ?");
                stmt.setString(1,publisher);
                break;
            case 5:
                //method
                break;
            case 6:
                System.out.println("Enter name of book you want to see");
                String book = in.next();
		java.sql.PreparedStatement stmt = connection.PrepareStatement( " SELECT * FROM book WHERE BOOKTITLE = ?");
                stmt.setString(1,publisher);
                break;
            case 7:
		System.out.println("Entera new book into database with title, year published, and page numbers");
		String bTitle = in.next();
		String yPublished = in.next();
		String pNumbers = in.next();
		String sql = "INSERT INTO Book (book_title, year_published, number_pages)" +
       		 "VALUES (?, ?, ?)";
		PreparedStatement preparedStatement = connection.prepareStatement(sql);
		preparedStatement.setString(1, bTitle);
		preparedStatement.setString(2, yPublished);
		preparedStatement.setString(3, pNumbers);
	     case 8:
	     case 9:
