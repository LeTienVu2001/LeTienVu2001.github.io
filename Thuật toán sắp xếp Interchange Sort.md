<h3 align="center">Hôm nay mình sẽ hướng dẫn các bạn một số thuật toán sắp xếp trong Bài giảng Cấu trúc dữ liệu và giải thuật. </h3>
<h3 align="center"> Thuật toán Interchange Sort dùng danh sách liên kết </h3>

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
			   
			   
		

   

   
## 📫 How to reach me:
<p align="center">
  <a href="https://www.instagram.com/smilecrush1221/" alt="instagram">
    <img src="https://img.icons8.com/fluent/48/000000/instagram-new.png" target="_blank" />
  </a> 
    <a href="https://www.facebook.com/AlbertEinstein2001/" alt="Facebook">
    <img src="https://img.icons8.com/fluent/48/000000/facebook-new.png" target="_blank" />
  </a> 
      <a href="https://www.tiktok.com/@vu_sniper" alt="Tiktok">
    <img src="https://img.icons8.com/fluent/48/000000/tiktok.png" target="_blank" />
  </a> 
  <a href="https://github.com/LeTienVu2001" alt="Github">
    <img src="https://img.icons8.com/fluent/48/000000/github.png"/>
  </a> 
  <a href="mailto:19200574@student.hcmus.edu.vn" alt="Email">
    <img src="https://img.icons8.com/fluent/48/000000/mailing.png"/>
  </a>
</p>

* **Họ và tên:** Lê Tiến Vũ
Nếu bạn có câu hỏi hay bất cứ vấn đề gì thì có thể liên lạc với mình qua Facebook [Tiến Vũ](https://www.facebook.com/AlbertEinstein2001/) hoặc có thể gửi mail cho mình tại email [letienvu878@gmail.com](mailto:letienvu878@gmail.com).
