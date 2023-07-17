# Automatically Generate a PDF and send it by Email

## Introduction
You work for a company that sells second hand cars. Management wants to get a summary of the amounts of vehicles that have been sold at the end of every month. The company already has a web service which serves sales data at the end of every month but management wants an email to be sent out with an attached PDF so that data is more easily readable.
## What you’ll do

>* Write a script that summarizes and processes sales data into different categories
>* Generate a PDF using Python
>* Automatically send a PDF by email


## Script file
Edit the script file
```
vi ~/scripts/cars.py.txt
```
The answer is saved in cars.py

## Sales summary
In this section, let's view the summary of last month's sales for all the models offered by the company. This data is in a JSON file named car_sales.json. Let's have a look at it.
```
cat car_sales.json
```
![image](https://github.com/cleatherbury/Automatically_Generate_a_PDF_send_it_by_email/assets/49545285/8365acde-5745-4669-aa15-36debcf2514e)

To simplify the JSON structure, here is an example of one of the JSON objects among the list.

```{
        "id": 47,
        "car": {
                "car_make": "Lamborghini",
                "car_model": "Murciélago",
                "car_year": 2002
        },
        "price": "$13724.05",
        "total_sales": 149
}
```
Here id, car, price and total_sales are the field names (key).

The script cars.py already contains part of the work, but learners need to complete the task by writing the remaining pieces. The script already calculates the car model with the most revenue (price * total_sales) in the process_data method. Learners need to add the following:

1. Calculate the car model which had the most sales by completing the process_data method, and then appending a formatted string to the summary list in the below format:

* "The {car model} had the most sales: {total sales}"

2. Calculate the most popular car_year across all car make/models (in other words, find the total count of cars with the car_year equal to 2005, equal to 2006, etc. and then figure out the most popular year) by completing the process_data method, and append a formatted string to the summary list in the below format:

* "The most popular year was {year} with {total sales in that year} sales."

## The challenge
Here, you are going to update the script cars.py. You will be using the above JSON data to process information. A part of the script is already done for you, where it calculates the car model with the most revenue (price * total_sales). You should now fulfil the following objectives with the script:

1. Calculate the car model which had the most sales.
	* Call format_car method for the car model.
2. Calculate the most popular car_year across all car make/models.

>__Hint:__ Find the total count of cars with the car_year equal to 2005, equal to 2006, etc. and then figure out the most popular year.

Grant required permissions to the file cars.py and open it using vi editor.
```
sudo chmod o+wx ~/scripts/cars.py
```
```
vi ~/scripts/cars.py
```
The code is well commented including the TODO sections for you to understand and fulfill the objectives.

## Generate PDF and send Email
Once the data is collected, you will also need to further update the script to generate a PDF report and automatically send it through email.

To generate a PDF:

* Use the reports.generate() function within the main function.

* The report should be named as cars.pdf, and placed in the folder /tmp/.

* The PDF should contain:

	* A summary paragraph which contains the most sales/most revenue/most popular year values worked out in the previous step.
	* A table which contains all the information parsed from the JSON file, organised by id_number. The car details should be combined into one column in the form <car_make> <car_model> (<car_year>).

>__Hint:__ To add line breaks in the PDF, use: \<br/> between the lines.
		
		
>__Hint__: You can use the cars_dict_to_table function for the above task.
		
Example:

| ID | Car | Price | Total Sales |
| --- | --- | --- | --- |
| 47 | Acura TL (2007) | €14459,15 | 1192 |
| 73 | Porsche 911 (2010) | €6057,74 |882|
| 85 | Mercury Sable (2005) | €45660,46 | 874 |

To send the PDF through email:

Once the PDF is generated, you need to send the email, using the emails.generate() and emails.send() methods.

Use the following details to pass the parameters to emails.generate():

__From:__ automation@example.com
__To:__ <user>@example.com
__Subject line:__ Sales summary for last month
__E-mail Body:__ The same summary from the PDF, but using \n between the lines
__Attachment:__ Attach the PDF path i.e. generated in the previous step
Once you have completed editing cars.py script, __save the file by typing ':wq'__.

Run the cars.py script, which will generate mail to their user.
```
./scripts/cars.py
```
Now, check the webmail for any new mail. You can click on the Refresh button to refresh your inbox.
![image](https://github.com/cleatherbury/Automatically_Generate_a_PDF_send_it_by_email/assets/49545285/f58861b6-e784-4ce1-94df-c4c51d2fbbfa)
Open cars.pdf that's located on the right most side.
![image](https://github.com/cleatherbury/Automatically_Generate_a_PDF_send_it_by_email/assets/49545285/5639b231-6997-447e-9062-61d6d34b9f78)
___THE END!___
