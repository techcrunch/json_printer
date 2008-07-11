@JsonPrinter@ allows you to convert arbitrarily nested Ruby data structures into 
human-and-machine-readable JSON output.  The input data can be any combination 
of arrays, hashes, symbols, strings, numbers, and false, true, and nil values.

<pre><code>
  data = 
   {"attribute" => "value",
    "blank" => nil,
    "list" => 
      [true,
       2,
       "elem_number_three"],
    "nested_hash" =>
      {"key" => 7,
       "other_key" => 13.5}}
  
  JsonPrinter.render(data)
  #=>
  {"nested_hash":
   {"other_key": 13.5,
    "key": 7},
   "list":
    [true,
     2,
     "elem_number_three"],
   "blank": null,
   "attribute": "value"}

  JSON.parse(JsonPrinter.render(data)) == data
  #=> true
</code></pre>