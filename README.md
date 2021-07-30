# Sign up now on [mediastack.com](https://mediastack.com/)

    npm install express ejs axios body-parser
    npm install --save-dev nodemon
    npm start

## How to parse response in Delphi?

    procedure TForm1.Btn1Click(Sender: TObject);
    var
      JSONValue: TJSONValue;
      JSONArray: TJSONArray;
      ArrayElement: TJSONValue;
    begin
      RESTRequest1.Execute;  // fetch data
    
      var Result := '';
    
      // create JSON Object from the response
      JSONValue := TJSonObject.ParseJSONValue(RESTResponse1.Content);
    
      // Get the needed array
      // articles are in the "data" array
      JSONArray := JSONValue.GetValue<TJSONArray>('data');
    
      // Iterate data array to get titles
      for ArrayElement in JSONArray do begin
        Result := Result + ' : ' + ArrayElement.GetValue<String>('title');
      end;
    
      Memo2.Lines.Add(Result);
    end;
