Imports System.Data.SqlClient
Public Class Books
    Public CON = New SqlConnection("Data Source=DESKTOP-NSC8DNJ;Initial Catalog=LibraryManagementVB;Integrated Security=True")
    Private Sub SaveBtn_Click(sender As Object, e As EventArgs) Handles SaveBtn.Click
        If BNameTb.Text = "" Or BAuthorTb.Text = "" Or QtyTb.Text = "" Or BPriceTb.Text = "" Or BPublisherTb.Text = "" Then
            Dim unused = MsgBox("Missing Information")
        Else
            Con.Open()
            Dim query = "insert into BookTb1 values('" & BNameTb.Text & "','" & BAuthorTb.Text & "','" & BPublisherTb.Text & "'," & BPriceTb.Text & "," & QtyTb.Text & ")"
            Dim cmd As SqlCommand
            cmd = New SqlCommand(query, Con)
            cmd.ExecuteNonQuery()
            MsgBox("Book Saved")
            Con.Close()
        End If
    End Sub
End Class
