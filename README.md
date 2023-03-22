  Dim xmlDoc As New XmlDocument()
        xmlDoc.Load("C:\Users\ma7m0\source\repos\Program14\Program14\HiScores.xml")
        Dim nodes As XmlNodeList = xmlDoc.SelectNodes("entries/entry")
        Dim sw As New StreamWriter("C:\Users\ma7m0\source\repos\Program14\Program14\HiScores.csv")                    ' Also can use fille path of text file
        For Each node As XmlNode In nodes
            Dim values As String = ""
            For Each childNode As XmlNode In node.ChildNodes
                values += childNode.InnerText & ","
            Next
            sw.WriteLine(values.TrimEnd(","))
        Next
        sw.Close()
