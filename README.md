# How to access Air Data

url = https://aqs.epa.gov/aqsweb/airdata/8hour_44201_2014.zip

- Way 1

      url = "https://aqs.epa.gov/aqsweb/airdata/8hour_44201_2014.zip"
      if (!dir.exists("./data")) { dir.create("./data") }
      if (!file.exists("./data/hourly_44201_2014.zip")) {
        download.file(url, "./data/hourly_44201_2014.zip", quiet = TRUE)}

      unzip("./data/hourly_44201_2014.zip", exdir = "./data")
      data = read.csv("./data/8hour_44201_2014.csv",header=TRUE)
      View(data)
