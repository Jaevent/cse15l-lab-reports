# Week 7 lab report
## Part 1
In `DocSearchServer.java`, change the name of the `start` parameter of `getfiles`, and its uses, to be called `base`.
Keystrokes in order (`week6-skill-demo` as the starting point:
* `vim D` `<Tab>` `<Enter>`
*  `/star` `<Enter>`
*  `ce`
*  `base` `<esc>`
*  `n.`
*  `n.`
*  `:wq` `<Enter>`
---
1. `vim D` `<Tab>` `<Enter>`:

`DocSearchServer.java` file in vim:

![image](https://user-images.githubusercontent.com/114322700/201546116-50e7c855-0733-49ee-94d4-f7384b529f47.png)

2. `/star` `<Enter>`

![image](https://user-images.githubusercontent.com/114322700/201546132-f5eba172-eb31-4662-8767-17d6ef5d2dc7.png)

3. `ce`
`start` is deleted and enters insert mode:

![image](https://user-images.githubusercontent.com/114322700/201546146-3101e748-3a58-4c48-a230-ce0c6befdf91.png)

4. `base` `<esc>`
`start` replaced by base and returns to normal mode:

![image](https://user-images.githubusercontent.com/114322700/201546163-441750ca-7eb3-4d2c-a9fb-b0371c0bdbb0.png)

5. `n.`
vim searches and replaces the next instance of `start` with `base`:

![image](https://user-images.githubusercontent.com/114322700/201546176-4c55fa5c-9fbd-442d-96d5-4b722ddff360.png)

6. `n.`
vim searches and replaces the next instance of `start` with `base`:

![image](https://user-images.githubusercontent.com/114322700/201546189-1da150aa-0d6c-4dfe-961a-81e484f533a3.png)

7. `:wq` `<Enter>`
saving and exiting the file and returning to the terminal:

![image](https://user-images.githubusercontent.com/114322700/201546199-ca265f95-7c1b-4341-bfc3-5395dd7529c3.png)

