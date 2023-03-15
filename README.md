# Create-VPC-connect-with-EC2

#實施步驟
![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20125640.png)


# 步驟1: 建立VPC

1.輸入搜尋VPC

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20121944.png)

2.選取 建立VPC

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122003.png)

3.建立VPC、名稱改為lab、子網遮罩改為10.0.0.0/16

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122425.png)

4.AZ數量、公私有子網數、NAT Gateway數量皆各一、公私子網遮罩改為10.0.0.0/24(公) 、 10.0.1.0/24(私)

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122444.png)

5.確定VPC端點為無，啟用DNS主機名稱及解析有被勾選後，建立VPC

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122501.png)

6.確認VPC資訊與下圖相同

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122514.png)

7.從欄位可以看到labVPC已建立

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122525.png)

8.進入子網設定建立子網路

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122537.png)

9.選擇labVPC

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122559.png)

10.新增一個公有子網

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122616.png)

11.新增一個私有子網

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122631.png)

12.可以查看所有子網已建立

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122644.png)


# 步驟2-1: 設定路由

13.進入路由表設定路由

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122709.png)

14.選取lab-rtb-private1-us-east-1a

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20122736.png)

15.進入子網路關聯表 編輯子網路關聯

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123035.png)

16.連接兩個私有子網

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123046.png)

17.選取lab-rtb-public

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123101.png)

18.進入子網路關聯表 編輯子網路關聯

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123118.png)

19.連接兩個公有子網

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123134.png)

20.兩組子網關聯各自連上

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123148.png)


# 步驟2-2: 設定安全群組

21.進入安全群組設定  建立安全群組

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123200.png)

22.安全群組設定如下圖  新增傳入規則

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123211.png)

23.傳入規則為HTTP(TCP/UDP埠:80)  IPv4=0.0.0.0/0

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123225.png)

24.輸入搜尋EC2  接下來要連接EC2

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123244.png)


# 步驟3: 建立EC2

25.建立EC2

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123357.png)

26.設定EC2名稱 選取機器類型Linux

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123417.png)

27.EC2類型為t2.micro  安全金鑰使用預設的vokey

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123439.png)

28.選擇Labvpc  公有子網2  選擇剛剛建立的安全群組

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123450.png)

29.不用動機器的規格

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123505.png)

30.輸入userdata佈署機器內的設定

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123517.png)

31.選取建立完成的EC2 狀態檢查為2/2 複製DNS網址

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123529.png)

# 步驟4: 測試連線

32.開啟無痕模式分頁 輸入剛剛複製的網址

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123546.png)

33.檢查EC2運行狀態

![image](https://github.com/JeanYu01/Create-VPC-connect-with-EC2/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-03-15%20123616.png)

