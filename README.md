# VBA-challenge
VBA Challenge Homework #2


VBA CODE








Sub StockChange():

For Each ws In Worksheets
Dim WorksheetName As String

Dim Ticker As String
Dim Yearly_Change As Double
Yearly_Change = 0
Dim Total_Volume As Double
Total_Volume = 0

Dim Summary_Table_Row As Integer
Summary_Table_Row = 2

'-------------------------------------

For i = 2 To 797711

If Cells(i + 1, 1).Value <> Cells(i, 1).Value Then
    Ticker = Cells(i, 1).Value
    Yearly_Change = Yearly_Change + (Cells(i, 6).Value - Cells(i, 3).Value)
    
Range("I" & Summary_Table_Row).Value = Ticker
Range("J" & Summary_Table_Row).Value = Yearly_Change
Range("K" & Summary_Table_Row).Value = Yearly_Change / Cells(i, 3).Value

Yearly_Change = 0

Else

End If

'----------------------------------------

If Cells(i + 1, 1).Value <> Cells(i, 1).Value Then
    Ticker = Cells(i, 1).Value
    Total_Volume = Total_Volume + Cells(i, 7).Value
    
Range("L" & Summary_Table_Row).Value = Total_Volume

Summary_Table_Row = Summary_Table_Row + 1

Total_Volume = 0

Else

End If

'-------------------------------------

If Range("J" & Summary_Table_Row).Value >= 0 Then
Range("J" & Summary_Table_Row).Interior.ColorIndex = 4

ElseIf Range("J" & Summary_Table_Row).Value <= 0 Then
Range("J" & Summary_Table_Row).Interior.ColorIndex = 3

Else

End If

Next i

Next ws

End Sub

