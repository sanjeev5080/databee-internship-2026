# Use Case — Data Analytics

**Track Lead:** Vinod

---

## SQL Internship — Setup and Week 1 Tasks

---

## Setup Steps

1. Install Microsoft SQL Server 2019 Developer Edition.
2. Install SQL Server Management Studio (SSMS).
3. Download the AdventureWorks sample database backup file (`.bak`).
4. Open SSMS and connect to the SQL Server instance.
5. Right-click on Databases and select **Restore Database**.
6. Choose **Device** and select the downloaded `.bak` file.
7. Complete the restore process and create the database.
8. Run a sample query to confirm the setup is working.

---

## Week 1 — SQL Practice Questions

Work against the **AdventureWorks** database (`Person.Person` table).

1. Get all records where `FirstName` starts with `A` and ends with `n`
2. Find people whose `LastName` length is more than 6 characters
3. Get records where `FirstName` contains `ar` but not at the start
4. Fetch records where `FirstName` is exactly 5 characters long
5. Find people where `FirstName` is equal to `LastName`
6. Get records where `FirstName` has no vowels
7. Find people whose `LastName` starts with same letter as `FirstName`
8. Get records where `FirstName` starts with `M` and `LastName` ends with `r`
9. Find people where `FirstName` starts with `J` or `LastName` starts with `S` but `BusinessEntityID` is less than 100
10. Get records where `FirstName` contains `a` and does not contain `e`
11. Find people where `FirstName` starts with `A` or `B` and `LastName` contains `son`
12. Find names where second letter is `a`
13. Find names where third letter is `r`
14. Get names where `FirstName` starts and ends with same letter
15. Find names that contain exactly one `a`
16. Get names that contain at least two `a` characters
17. Find records where `FirstName` is in `John`, `David`, `Mary` and `BusinessEntityID` is between 50 and 200
18. Get records where `FirstName` is not in `James`, `Robert` and `LastName` starts with `B`
19. Find people where `BusinessEntityID` is between 10 and 100 and `FirstName` starts with a vowel
20. Get records where ID is between 1 and 300 but exclude even numbers
21. Find people where `FirstName` starts with `S` and `LastName` ends with `n` or contains `ar`
22. Get records where `FirstName` starts with a vowel and `LastName` does not start with a vowel
23. Find people where `FirstName` length is greater than 5 and `LastName` length is less than 5
24. Get records where `FirstName` contains `a` and `LastName` contains `e` and `BusinessEntityID` is less than 150
25. Find people where `FirstName` starts with `A` or `LastName` ends with `e` and `FirstName` does not contain `z` and `BusinessEntityID` is between 10 and 200
26. Find people where `FirstName` has exactly two vowels and `LastName` starts with same letter as `FirstName` and ID is not between 50 and 100
27. Find people where `FirstName` contains `ar` only once and `LastName` length is greater than `FirstName` length
