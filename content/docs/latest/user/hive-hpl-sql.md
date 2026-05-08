INSERT OVERWRITE DIRECTORY "/tmp/pairs"
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
SELECT t1.BookTitle, t2.BookTitle, t2.Publisher, t2.YearOfPublication
FROM books t1
JOIN books t2
ON t1.Publisher = t2.Publisher
AND t1.YearOfPublication = t2.YearOfPublication
WHERE t1.BookTitle < t2.BookTitle;
