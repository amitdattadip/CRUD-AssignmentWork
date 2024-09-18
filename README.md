CRUD APPLICATION USING VISUAL STUDIO AND MYSQL DATABASE

Faciliates in understanding and demonstrating about the basic concepts of CREATE,READ,UPDATE AND DELETE.

[Screenshot (4)](https://github.com/user-attachments/assets/cbacccdc-7199-4ffb-b67a-568b641b117c)

BUILT WITH
Programming Language: C#(.Net Framework)
 
Database: Microsoft SQL Server
 
IDE: Visual Studio / VS Code
 
FEATURES (BUTTONS)

Insert: Add new user data to the database.
 
Delete: Remove existing user data based on userid.
 
Update: Modify details of a selected user.
 
Search: Search for the existing data from the datagridview
 
SQL QUERY
Table Design
 
CREATE TABLE [dbo].[Tabel_1] ( [ProductID] INT (50), [ItemName] VARCHAR (50), [Desin] IVARCHAR(250) , [COLOR] VARCHAR (50), [Date] datetime , [UpdateDate] datetime, [InsertDate] datetime, CONSTRAINT [PK_Table_1] PRIMARY KEY CLUSTERED ([ProductID] ASC) );
 
Insert
 
"Insert into Table_1 values ('" + int.Parse(textBox1.Text) + "','"
 
   con.Open();
   SqlCommand command = new SqlCommand("insert into Table_1 values ('" + int.Parse(textBox1.Text) + "','" + textBox2.Text + "','" + textBox3.Text + "','" + comboBox1.Text + "', getdate(), getdate())",con);
   command.ExecuteNonQuery();
   MessageBox.Show("Successfully Inserted.");
   con.Close();
   BindData();
 
Update
 
update Table_1 set ItemName='" + textBox2.Text
 
  con.Open();
  SqlCommand command = new SqlCommand("update Table_1 set ItemName= '" + textBox2.Text + "', Color ='" + comboBox1.Text + "',Design = '"+textBox3.Text+"', UpdateDate = '"+DateTime.Parse(dateTimePicker1.Text) +"' 
  where ProductID = '" + int.Parse(textBox1.Text) + "'", con);
  command.ExecuteNonQuery();
  con.Close();
  MessageBox.Show("Successfully Update.");
  BindData();
 
Delete
 
con.Open();
SqlCommand command = new SqlCommand("Delete Table_1 where ProductID= '" + int.Parse(textBox1.Text) + "'", con);
command.ExecuteNonQuery();
con.Close();
MessageBox.Show("Successfully Deleted.");
BindData();
 
Search
 
SqlCommand command = new SqlCommand("select * from Table_1 where ProductID= '" + int.Parse(textBox1.Text) + "'", con);
SqlDataAdapter sd = new SqlDataAdapter(command);
DataTable dt = new DataTable();
sd.Fill(dt);
dataGridView1.DataSource = dt;
TECHNOLOGY
Programming Language: C#
 
Database: SQL Server
 
Framework: Windows Forms
 
UI Components:
 
Text Box for entering data.
Button for response.
Data Grid View for displaying and managing data
🛠 Skills
C#
 
NET Framework
 
SQL Server
 
Windows Forms Development
has context menu
