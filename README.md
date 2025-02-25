# DV107-hank
dialog --title "PHPSYSINFO安裝程式" --msgbox "準備開始安裝程式" 10 50
dialog --title "安裝程式指令" --textbox ~/php.txt 30 60
dialog --title "選單模式" --menu "可上下選擇" 10 50 3 1 "安裝" 2 "取消" 
dialog --title "表單模式" --form "個人資訊" 10 50 3 "名稱:" 1 1 "" 1 15 25 0 "年齡:" 2 1 "" 2 15 25 0 "職業:" 3 1 "" 3 15 25 0

sudo apt install apache2 -y &> /dev/null 
echo "Apache2 installed."
sudo apt install php php-xml php-json -y
sudo service apache2 restart
wget https://github.com/phpsysinfo/phpsysinfo/archive/refs/tags/v3.4.4.zip
unzip v3.4.4.zip &> /dev/null
sudo mv phpsysinfo-3.4.4/* /var/www/html/ 
sudo cp /var/www/html/phpsysinfo.ini.new /var/www/html/phpsysinfo.ini
echo "You can visit my phpsysinfo now."
dialog -- title "完成安裝" -- msgbox "恭喜你,可以開始瀏覽我的網站了" 10 50
