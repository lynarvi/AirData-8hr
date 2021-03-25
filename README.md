# How to access Air Data

url = https://aqs.epa.gov/aqsweb/airdata/8hour_44201_2014.zip


- Way 1
      
      library("readr")
      url = "https://aqs.epa.gov/aqsweb/airdata/8hour_44201_2014.zip"
      if (!dir.exists("./data")) { dir.create("./data") }
      if (!file.exists("./data/hourly_44201_2014.zip")) {
        download.file(url, "./data/hourly_44201_2014.zip", quiet = TRUE)}

      unzip("./data/hourly_44201_2014.zip", exdir = "./data")
      data = read.csv("./data/8hour_44201_2014.csv",header=TRUE)
      View(data)

- Way 2

      library("readr")
      url = "https://aqs.epa.gov/aqsweb/airdata/8hour_44201_2014.zip"
      destfile = "D:/AirData.zip"
      download.file(url,destfile)
      unzip("D:/AirData.zip",exdir = "D:/")
      Data = read.csv("D:/8hour_44201_2014.csv")
      View(Data)

- Way 3

      library("readr")
      download.file("https://aqs.epa.gov/aqsweb/airdata/8hour_44201_2014.zip",destfile="Air.zip")
      con = unz("Air.zip", filename = "8hour_44201_2014.csv")
      con2 = gzcon(con)
      AirData = read_csv(con2)
