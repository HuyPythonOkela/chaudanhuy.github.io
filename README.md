import os
import calendar
from datetime import date
from time import sleep
import random
os.system('cls' if os.name=='nt' else 'clear')
thiencan = ['Canh','Tân','Nhâm','Quý','Giáp','Ất','Bính','Đinh','Mậu','Kỷ']
diachi = ['Thân','Dậu','Tuất','Hợi','Tí','Sửu','Dần','Mão','Thìn','Tị','Ngọ','Mùi']
date = date.today()
nam = date.year
cld = calendar.TextCalendar(calendar.MONDAY)
username = input("Nhập tên của bạn: ")
username2 = username.title()
for string in ('Chào mừng {} đến với bài tập của cô Diệp. Tui là Châu Đan Huy - Người thiết kế nên cái củ khoai này.\nHãy nhập bất kì "chữ cái" nào vào vị trí <Nhập tháng> hoặc vị trí <Nhập năm> nếu bạn muốn kết thúc chương trình!'.format(username2)):
    print(string,end='',flush=True)
    sleep(0.001)
print()
print("=="*51)
while True:
    try:
        t = int(input("- Nhập tháng: "))
        try:
            n = int(input("- Nhập năm: "))
            def thongtinnam():    
                vitri_can = n % 10
                vitri_chi = n % 12
                if n > nam:
                    print("- Năm",n,"là năm",thiencan[vitri_can] , diachi[vitri_chi],"\t ("+str(n-nam),"năm sau)")
                else:
                    if n < nam:
                        if n < 0:
                            print("- Năm",abs(n),"trước công nguyên là năm",thiencan[vitri_can] , diachi[vitri_chi],"\t ("+str(nam-n),"năm trước)")
                        else:
                            if n == 0:
                                print("- Năm 0 được xem là năm công nguyên, có can chi là",thiencan[vitri_can] , diachi[vitri_chi],"\t ("+str(nam-n),"năm trước)")
                            else:
                                print("- Năm",n,"là năm",thiencan[vitri_can] , diachi[vitri_chi],"\t ("+str(nam-n),"năm trước)")
                    else:
                        print("- Năm",n,"là năm",thiencan[vitri_can] , diachi[vitri_chi],"\t (Chính là năm nay)")
                return;
            thongtinnam()
            if n >= 0:
                if n == 0:
                    if 0 <= t <= 12:
                        if t == 4 or t == 6 or t == 9 or t == 11:
                            print("--"*20,"\n Tháng",t,"của năm công nguyên có 30 ngày","\n"+"--"*20)
                        else:
                            if t == 2:
                                print("--"*20,"\n Tháng 2 của năm công nguyên có 29 ngày","\n"+"--"*20)
                            else:
                                print("--"*20,"\n Tháng",t,"của năm công nguyên có 31 ngày","\n"+"--"*20)
                        kh = cld.formatmonth(n,t)
                        print(kh)
                    else:
                        print("- Có tháng {} luôn hả {}?. Nhập lại đi trùi ui".format(t,username2))
                else:
                    if 0 <= t <= 12:
                        if t == 4 or t == 6 or t == 9 or t == 11:
                            print("--"*18,"\n Tháng",t,"của năm",n,"có 30 ngày","\n"+"--"*18)
                        else:
                            if t == 2:
                                if n%400==0 or (n%4==0 and n%100!=0) or n == 0:
                                    print("--"*17,"\n Tháng 2 của năm",n,"có 29 ngày","\n"+"--"*17)
                                else:
                                    print("--"*17,"\n Tháng 2 của năm",n,"có 28 ngày","\n"+"--"*17)
                            else:
                                print("--"*17,"\n Tháng",t,"của năm",n,"có 31 ngày","\n"+"--"*17)
                        kh = cld.formatmonth(n,t)
                        print(kh)
                    else:
                        print("- Có tháng {} luôn hả {}?. Nhập lại đi trùi ui".format(t,username2))
            else:
                n = abs(n)
                if 0 <= t <= 12:
                    if t == 4 or t == 6 or t == 9 or t == 11:
                        print("--"*25,"\n- Tháng",t,"của năm",n,"trước công nguyên có 30 ngày","\n"+"--"*25)
                    else:
                        if t == 2:
                            if (n%400==0 and n != 0) or (n%4==0 and n%100!=0):
                                print("--"*25,"\n Tháng 2 của năm",n,"trước công nguyên có 29 ngày","\n"+"--"*25)
                            else:
                                print("--"*25,"\n Tháng 2 của năm",n,"trước công nguyên có 28 ngày","\n"+"--"*25)
                        else:
                            print("--"*25,"\n Tháng",t,"của năm",n,"trước công nguyên có 31 ngày","\n"+"--"*25)
                else:
                    print("- Có tháng {} luôn hả {}?. Nhập lại đi trùi ui".format(t,username2))
            print("\n")
        except:
            if n == 'x' or n == 'X' or t == 'x' or t == 'X':
                print("=="*51)
                for thanks in "- Chương trình kết thúc, hãy hỏi cô Diệp về số điểm của bạn.\n- Riêng Huy thì Huy chấm cho {} ".format(username2)+str(rd)+"/10 điểm á.\n"+"- Cảm ơn "+username.upper()+" nhiều nha!":
                    print(thanks,end='',flush=True)
                    sleep(0.1)
                print()
                print("\n")
                break
            else:
                print("Bắt đầu chướng rồi á, nhập tào lao gì dị {}? Nhập lại ik nè:>".format(username2))
                print("\n")
    except:
        print("Có phải {} vừa nhập tào lao cái gì đúng hong?".format(username2))
        cf = input("Nhập chữ x vô đây để xác nhận là {} mới bấm tào lao đi, đồng thời kết thúc chương trình luôn: ".format(username2))
        if cf == 'x' or cf == 'X' or cf == 'x' or cf == 'X':
                print("=="*51)
                rd = random.randint(1,11)
                for thanks in "- Chương trình kết thúc, hãy hỏi cô Diệp về số điểm của bạn.\n- Riêng Huy thì Huy chấm cho {} ".format(username2)+str(rd)+"/10 điểm á.\n"+"- Cảm ơn "+username.upper()+" nhiều nha!\n"+"- Ò sẵn đây {} có thể đánh giá chương trình này của Huy không?".format(username2)+"\n"+"--"*45:        
                    print(thanks,end='',flush=True)
                    sleep(0.001)
                print()
                while True:
                    ans = input("- Nhập 'c' nếu {} muốn đánh giá, nhập 'k' nếu {} không muốn đánh giá: ".format(username2, username2))
                    print("--"*45)
                    if ans == "c" or ans == 'C':
                        danhgia = int(input("- Oh, zậy từ 1 sao đến 5 sao thì {} muốn đánh giá Huy mấy sao? Nhập số sao vô đây: ".format(username2)))
                        print("--"*45)
                        if 1 <= danhgia < 6:
                            if danhgia == 1:
                                print("- Gì mà 1 sao? Tệ vậy {}?, thôi cũng được. Bye {}!".format(username2, username2))
                                print("--"*45)
                                break 
                            else:
                                if danhgia == 2:
                                    print("- Có 2 sao à? Tệ dữ zậy luôn á hả {}, mà cũng được. Bye {}!".format(username2, username2))
                                    print("--"*45)
                                    break 
                                else:
                                    if danhgia == 3:
                                        print("- Chỉ 3 sao thôi hả {}?. OK 3 sao cũng đủ mà, thank {} and bye {}!".format(username2, username2, username2))
                                        print("--"*45)
                                        break 
                                    else:
                                        if danhgia == 4:
                                            print("- Ủa sao cho 4 sao zậy, còn 1 sao nữa tiếc hả {}?. Giỡn chớ cảm ơn {} nhiều nha. Bye {}!".format(username2, username2, username2))
                                            print("--"*45)
                                            break 
                                        else:
                                            print("- Wow! 5 sao luônnn, I'm so happy. Cảm ơn {} rất nhiều. Bye {}!".format(username2, username2))
                                            print("--"*45)
                                            break 
                        else:
                            if danhgia > 5:
                                print("- Gì mà {} sao dữ zậy {}. Tốt tới mức đó luôn hả? Nghịch ngợm ghê á, đánh giá lại ik {}".format(danhgia, username2, username2))
                                print("--"*45)
                            else:
                                print("- A đù men, đánh giá mà âm sao luôn? Tui có tệ tới mức đó đâu, đánh giá lại ik {}".format(username2))
                                print("--"*45)
                    else:
                        if ans == 'k' or ans == 'K':
                            print("- Ò {} hong thích đánh giá thì thui. Bye {} nha".format(username2, username2))
                            break 
                        else:
                            print("- Gì zị {}, chỉ nhập chữ 'c' hoặc chữ 'k' thôi {}. Lại ik {}".format(username2, username2,username2))
                print("\n")
                break
        else:
            print("- Bắt đầu chướng rồi á, nhập tào lao gì dị {}? Nhập lại ik nè:>".format(username2))
            print("\n")
