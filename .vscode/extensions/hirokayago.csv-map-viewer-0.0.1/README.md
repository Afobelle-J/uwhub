# csv-map-viewer README

The VSCode extension "csv-map-viewer" is a viewer for CSV that has a different number of columns for each row.

For example, if you show the below CSV file that has a row for Profile and another row for Address, this extension will tell you what the current cursor column means.

```csv
A,John,john@gmail,Company1,0123456789
B,3374 Vitae Road,Merrickville-Wolford,88383,Ontario,Saint Martin
A,Alex,alex@gmail,Company2,1123456789
B,171-328 Pellentesque St.,Bhagalpur,3542 CJ,BR,Netherlands
0,a,b,c,d,e,f
```

![Screen_Shot_2021-04-29_at_21_49_55](https://user-images.githubusercontent.com/8636660/116554832-9b136600-a936-11eb-9f44-168686bbd13a.jpg)

## Features

First, in Extension Settings, define the meaning of the columns in JSON. The following example defines that when the value of the first column is `A`, the second column is `Name` and the third column is `Email`.

````json
"A": {
    "0": { "title" : "A", "description": "A description" },
    "1": { "title" : "Names", "description": "Names description" },
    "2": { "title" : "Email", "description": "Email description" },
    "3": { "title" : "Company", "description": "Company description" },
    "4": { "title" : "Phone", "description": "Phone description" }
},
"B": { 
    // ... 
}
````

If you open the Editor and run `CSV Map Viewer: Show` from the Command Palette, the meaning of the column where the cursor is currently located will be displayed in the lower left bar.

<img width="749" alt="Screen Shot 2021-04-29 at 22 07 30" src="https://user-images.githubusercontent.com/8636660/116556475-6ef8e480-a938-11eb-91a1-17b69710e25b.png">

![Screen_Shot_2021-04-29_at_21_49_55](https://user-images.githubusercontent.com/8636660/116554832-9b136600-a936-11eb-9f44-168686bbd13a.jpg)

![sample](https://user-images.githubusercontent.com/8636660/116559599-943b2200-a93b-11eb-9611-f7596fc69d0e.gif)


Next, run `CSV Map Viewer: Output` from the Command Palette to display the information of the whole file in the Output of `CSV Map Viewer` in the Output Window. 

<img width="899" alt="Screen Shot 2021-04-29 at 22 08 16" src="https://user-images.githubusercontent.com/8636660/116556465-6d2f2100-a938-11eb-8d40-a3b990b8be77.png">



## Extension Settings

* `csv-map-viewer.map`(Object): Defines the meaning of a column for each row in the CSV file.

Example:

```json
"csv-map-viewer.map": {

    "YOUR FIRST COLUMN TEXT": {
        "0": { "title" : "column 0 title", "description": "" },
        "1": { "title" : "column 1 title", "description": "" }
    },
    "A": {
        "0": { "title" : "A", "description": "A description" },
        "1": { "title" : "Names", "description": "Names description" },
        "2": { "title" : "Email", "description": "Email description" },
        "3": { "title" : "Company", "description": "Company description" },
        "4": { "title" : "Phone", "description": "Phone description" }
    },
    "B": {
        "0": { "title" : "B", "description": "B description" },
        "1": { "title" : "Street Address", "description": "description-B-0" },
        "2": { "title" : "City", "description": "description-B-1" },
        "3": { "title" : "Zip", "description": "description-B-1" },
        "4": { "title" : "Region", "description": "description-B-1" },
        "5": { "title" : "Country", "description": "description-B-1" }
    }
}
```

## Known Issues

The `,` inside the double quotation marks are not supported.

## Release Notes



### 0.0.1

Initial release