<h1 align="center">Hi everyone, I'm Tien Vu Le</h1>
<p align="center"><img src="https://img.icons8.com/color/48/000000/vietnam-circular.png"/></p>
<h3 align="center">A student from Vietnam </h3>
<h3 align="center">I'm from Dak Nong, Currently studying in HO CHI MINH city </h3>
<p align="center"> <img src="https://komarev.com/ghpvc/?username=tiennhm" alt="tiennhm" /> <img src="https://badges.pufler.dev/repos/TienNHM" alt="tiennhm" /> </p>

- ✍ I'm a student of: [Ho Chi Minh city University of Science](https://hcmus.edu.vn) (HCMUS).

- 🌱 I’m currently learning **Computers - Embedded systems.**


## 📫 How to reach me:
<p align="center">
  <a href="https://www.instagram.com/erais.me/" alt="instagram">
    <img src="https://img.icons8.com/fluent/48/000000/instagram-new.png" target="_blank" />
  </a> 
    <a href="https://www.facebook.com/shinetotheend/" alt="Facebook">
    <img src="https://img.icons8.com/fluent/48/000000/facebook-new.png" target="_blank" />
  </a> 
      <a href="https://www.tiktok.com/@erais.me" alt="Tiktok">
    <img src="https://img.icons8.com/fluent/48/000000/tiktok.png" target="_blank" />
  </a> 
  <a href="https://github.com/LeTienVu2001" alt="Github">
    <img src="https://img.icons8.com/fluent/48/000000/github.png"/>
  </a> 
  <a href="mailto:19200574@student.hcmus.edu.vn" alt="Email">
    <img src="https://img.icons8.com/fluent/48/000000/mailing.png"/>
  </a>
</p>

## Skills:
<p align="center">
  <img src="https://img.icons8.com/fluent/48/000000/matlab.png"/>
   <img src="https://img.icons8.com/fluent/48/000000/tiktok.png"/>
  <img src="https://img.icons8.com/color/48/000000/github-2.png"/>
  <img src="https://img.icons8.com/color/48/000000/visual-studio-code-2019.png"/>
  <img src="https://img.icons8.com/color/48/000000/visual-studio-2019.png"/>
  <img src="https://img.icons8.com/dusk/48/000000/opera.png"/>
  <img src="https://img.icons8.com/fluent/48/000000/python.png"/>
</p>
<img src="https://cdn.dribbble.com/users/1059583/screenshots/4171367/coding-freak.gif" alt="dev" width="100%"/>


### Đôi chút về mình

Mình tên là Lê Tiến Vũ, hiện tại là sinh viên năm 3 chuyên ngành Nhúng - Hệ thống máy tính tại trường Đại Học Khoa Học Tự Nhiên Thành Phố Hồ Chí Minh.

* **Họ và tên:** Lê Tiến Vũ
* **Giới tính:** Nam
* **Nguyên quán:** Hà Tĩnh, Việt Nam
* **Quê quán:** Đăk Nông, Việt Nam
* **Trích dẫn yêu thích:** Chơi guitar, Phượt, Cắm mặt vào laptop, Street Workout, Đá bóng, bơi lội, chạy bộ thì lâu lâu :))))
	
Nếu bạn có câu hỏi hay bất cứ vấn đề gì thì có thể liên lạc với mình qua Facebook [Tiến Vũ](https://www.facebook.com/shinetotheend/) hoặc có thể gửi mail cho mình tại email [letienvu878@gmail.com](mailto:letienvu878@gmail.com).

<h3 align="center">Sau đây mình sẽ hướng dẫn các bạn một số thuật toán sắp xếp trong Bài giảng Cấu trúc dữ liệu và giải thuật. </h3>
<h3 align="center"> Phần 1: Thuật toán Interchange Sort dùng danh sách liên kết </h3>

- Ý tưởng thuật toán: Thuật toán Interchange Sort hay còn gọi là thuật toán sắp xếp đổi chỗ trực tiếp. Chúng ta có thể xuất phát từ vị trí đầu mảng, gán giá trị i cho dãy chạy từ đầu, và gán j = i + 1 để chúng ta so sánh 2 giá trị của phần tử a[i] và a[j] nếu a[j] < a[i] thì swap 2 giá trị đó với nhau, sau đó gán j = j+1 rồi thực hiện so sánh giá trị tiếp. Sau khi kết thúc mảng thì ta tăng giá trị i lên 1 đơn vị và tiếp tục so sánh cho đến khi dãy được sắp xếp hoàn toàn thì dừng chương trình
- Sau đây là code mình viết theo c++:

			   
			   #include<iostream>#include<fstream>
			   #include<Windows.h>
			   
			   using namespace std;
			   
			   void swap(int& a, int& b)
			   {
			   	int temp = a;
			   	a = b;
			   	b = temp; 
			   }
			   
			   typedef struct Node 
			   {
			   	int data;
			   	Node* link;
			   }node;
			   
			   typedef struct Listkep
			   {
			   	node* first; 
				node* last;
			   }list;
				
			void Init(list& l)
			{
				l.first = l.last = NULL;
			}
			// Cấp phát vùng nhớ cho phần tử
			
			node* GetNode(int x) 
			{
				node* p = new node;
				p->data = x; 
				p->link = NULL;
				return p;
			}
			
			void addlast(list& l, int x)
			{
				node* new_ele = GetNode(x);
				if (l.first == NULL) 
				{
					l.first = new_ele;
					l.last = l.first;
				}
				else
				{
					l.last->link = new_ele;
					l.last = new_ele;
				}
			}
		
			void Output(list l) 
			{
				for (node* p = l.first; p != NULL; p = p->link)
				{
					cout << p->data << "\t";
				}
				cout << endl;
			}
		
			void SLL_InterChangeSort(list& l)
			{
				for (Node* p = l.first; p != l.last; p = p->link)
					for (Node* q = p->link; q != NULL; q = q->link)
						if (p->data > q->data)
							swap(p->data, q->data);
			}
		
			void FileIn(list& l) 
			{
				fstream filein;
				filein.open("C:\\Users\\ADMIN\\Desktop\\LIST.txt", ios::in); // đường dẫn mảng được đọc từ file tạo sẵn
				int value;
				while(filein>>value)
				{
					addlast(l, value);
				}
				filein.close();
			}
		
			void main()
			{
				list l;
				system("color A");
				Init(l);
				FileIn(l);
				cout << "Danh sach ban dau:\t ";
				Output(l);
				SLL_InterChangeSort(l);
				cout << "Danh sach da xep:\t ";
				Output(l);
			}
			   
<h3 align="center"> Phần 2: Thuật toán Shaker Sort dùng danh sách liên kết </h3>

- Ý tưởng thuật toán: Thuật toán Shaker Sort là thuật toán sắp xếp dựa trên Buble Sort.
			   
			   Trong mỗi lần sắp xếp, duyệt mảng theo 2 lượt từ 2 phía khác nhau:
			   Lượt đi: đẩy phần tử nhỏ về đầu mảng.
			   Lượt về: đẩy phần tử lớn về cuối mảng.
			  
			   Bước 1: l=0; r=n-1; //Đoạn l->r là đoạn cần được sắp xếp
			   k=n;  //ghi nhận vị trí k xảy ra hoán vị sau cùng
			   // để làm cơ sơ thu hẹp đoạn l->r
			   Bước 2:
			   Bước 2a: j=r; //đẩy phần tử nhỏ về đầu mảng
			   Trong khi j>l
			   nếu a[j]<a[j-1] thì {swap(a[j],a[j-1]): k=j;}
			   j--;
			   l=k; //loại phần tử đã có thứ tự ở đầu dãy
			   Bước 2b: j=l
			   Trong khi j<r
			   nếu a[j]>a[j+1] thì {swap(a[j],a[j+1]); k=j;}
			   j++;
			   r=k; //loại phần tử đã có thứ tự ở cuối dãy
			   Bước 3: Nếu l<r lặp lại bước 2
			   Ngược lại: dừng
			   
   - Sau đây là code mình viết theo c++: Giá trị mảng được đọc từ file tạo sẵn bên ngoài.	

			  #include<iostream>
			  #include<fstream>
			  #include<Windows.h>
			  
			  using namespace std;
			  
			  typedef struct Node {
			  	 int data;
			 	 Node* next;
			 	 Node* pre;
			  }node;
			  
			  typedef struct Listkep {
			  	node* first;
			  	node* last;
			  }list;
			  
			  void init(list& l)
			  {
			  	l.first = l.last = NULL;
			  }
			  
			  void swap(int& a, int& b)
			  {
			  	int temp = a;
			  	a = b;
			  	b = temp;
			  }
			  
			  node* getnode(int x)
			  {
			  	node* p = new node;
			  	p->data = x;
			 	p->next = NULL;
			  	p->pre = NULL;
				return p;
			  }
			  
			  void addlast(list& l, int x)
			  {
			  	node* new_ele = getnode(x);
			  	if (l.first == NULL)
			 	{
			  		l.first = new_ele;
			  		l.last = l.first;
			  	}
			  	else
			 	{
			  		l.last->next = new_ele;
			  		new_ele->pre = l.last;
			  		l.last = new_ele;
			  	}
			  }
			  
			  void SharkerSort(list& l)
			  {
			  	Node* left = l.first;
			  	Node* right = l.last;
			  	Node* k = l.last;
			  	while (left != right)
			  	{
			  		for (Node* j = left; j != right; j = j->next)
			  		{
						if (j->data > j->next->data)
						{
							swap(j->data, j->next->data);
							k = j;
						}
					}
					right = k;
					for (Node* j = right; j != left; j = j->pre)
					{
						if (j->data < j->pre->data)
						{
							swap(j->data, j->pre->data);
							k = j;
						}
					}
					left = k;
					}
				}
			
			void docfile(list& l)
			{
				fstream filein;
				filein.open("C:\\Users\\ADMIN\\Desktop\\LIST.txt", ios::in);
				int value;
				while (filein >> value)
				{
					addlast(l, value);
				}
			}
			
			void xuat(list& l)
			{
				for (node* p = l.first; p != NULL; p = p->next)
				{
					cout << p -> data << "\t";
				}
				cout << endl;
			}
			
			void main()
			{
				list l;
				system("color A");
				init(l);
				cout << "Ham doc tu file la:\t";
				docfile(l);
				xuat(l);
				cout << "\nHam sau khi sap xep la:\t";
				SharkerSort(l);
				xuat(l);
			}
			 
* **Họ và tên:** Lê Tiến Vũ
Nếu bạn có câu hỏi hay bất cứ vấn đề gì thì có thể liên lạc với mình qua Facebook [Tiến Vũ](https://www.facebook.com/shinetotheend/) hoặc có thể gửi mail cho mình tại email [letienvu878@gmail.com](mailto:letienvu878@gmail.com).

