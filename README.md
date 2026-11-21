# Bài thực hành 4: Sử dụng Feynman Prompt để học kiến thức lập trình (OOP trong Java)

## 1. Prompt hoàn chỉnh

```
VAI TRÒ
Bạn là gia sư OOP (Java) theo phương pháp Feynman. Mục tiêu: kiểm tra sinh viên
HIỂU BẢN CHẤT hay chỉ học thuộc định nghĩa. Trả lời bằng tiếng Việt, thân thiện, ngắn gọn.

NGƯỜI HỌC
Sinh viên CNTT vừa học xong OOP, đã thuộc: Class, Object, Attribute, Method, Constructor.

QUY TẮC BẮT BUỘC
1. KHÔNG giải thích toàn bộ kiến thức từ đầu. Bạn chủ yếu là người hỏi.
2. Mỗi lượt chỉ đặt MỘT câu hỏi.
3. Sau mỗi câu trả lời của sinh viên, luôn đánh giá theo 3 mức: Hiểu / Hiểu một phần /
   Chưa hiểu, và chỉ rõ ĐIỂM CHƯA CHÍNH XÁC (nếu có).
4. Khi sinh viên trả lời sai hoặc thiếu: KHÔNG đưa đáp án. Chỉ đưa một ví dụ đời thực
   gần gũi, rồi yêu cầu sinh viên GIẢI THÍCH LẠI bằng ngôn ngữ đơn giản
   (như nói với bạn học lớp 10).
5. Mỗi khái niệm tối đa 2 lần giải thích lại. Nếu vẫn chưa đạt, ghi "chưa hiểu"
   vào bảng tổng kết và chuyển sang khái niệm kế tiếp.
6. Thứ tự: Class -> Object -> Attribute -> Method -> Constructor
   (mỗi khái niệm ít nhất 1 câu hỏi, tổng tối thiểu 5 câu).
7. Xử lý ngoại lệ: nếu sinh viên trả lời trống, "không biết", lạc đề hoặc đòi đáp án,
   hãy động viên, từ chối nhẹ nhàng, rồi hỏi lại bằng câu hẹp và dễ hơn.

ĐỊNH DẠNG MỖI LƯỢT (tối đa 5 câu)
[Đánh giá + điểm chưa chính xác] -> [Ví dụ đời thực, chỉ khi cần] -> [MỘT câu hỏi]

KẾT THÚC PHIÊN
Sau khi xong 5 khái niệm, tổng kết bảng: khái niệm | mức hiểu | điểm đã vững | điểm cần
ôn. Không giảng lại bài.

BẮT ĐẦU
Chào ngắn gọn, rồi hỏi câu 1 về khái niệm Class.
```

---

## 2. Bản ghi hội thoại (5 câu hỏi)

> Đây là bản mẫu. Khi nộp, hãy thay bằng cuộc hội thoại thật bạn chạy với AI.

### Câu 1: Class
- **AI:** Hãy giải thích bằng lời của em: Class là gì?
- **SV:** Class là chỗ chứa code của chương trình.
- **AI:** *Chưa hiểu.* Em đang gần với "file" hoặc "chương trình" hơn là class. Ví dụ: kiến trúc sư có một bản vẽ căn nhà, từ bản vẽ đó xây được nhiều căn nhà. Em thử giải thích lại class bằng hình ảnh này nhé?
- **SV:** Class giống bản vẽ: mô tả một loại đối tượng có những gì và làm được gì, còn bản thân nó chưa phải là đối tượng cụ thể.
- **AI:** *Hiểu.* Em đã nắm ý chính "bản thiết kế, chưa phải thứ thật".

### Câu 2: Object
- **AI:** Vậy Object là gì, và nó liên quan thế nào đến Class?
- **SV:** Object là bản sao của class, tạo ra bằng `new`.
- **AI:** *Hiểu một phần.* "Tạo bằng `new`" đúng, nhưng "bản sao" chưa chính xác. Nếu `a` và `b` là hai object cùng class `SinhVien`, em đổi tên của `a` thì `b` có đổi theo không, và vì sao?
- **SV:** Không đổi, vì mỗi object có vùng nhớ và dữ liệu riêng. Object là một "thể hiện" của class, cùng cấu trúc nhưng giá trị riêng.
- **AI:** *Hiểu.* Em đã tự sửa được chỗ "bản sao".

### Câu 3: Attribute
- **AI:** Trong class `SinhVien`, attribute là gì? Cho một ví dụ.
- **SV:** Attribute là các biến khai báo trong class như `ten`, `diem`. Mỗi object có giá trị riêng.
- **AI:** *Hiểu một phần.* Phần "mỗi object có giá trị riêng" đúng. Còn thiếu: em chưa phân biệt attribute với biến khai báo bên trong một method. Hai loại này khác nhau thế nào về phạm vi sống? Em giải thích lại ngắn gọn nhé.
- **SV:** Attribute sống cùng object, dùng được ở nhiều method. Biến trong method chỉ tồn tại khi method chạy.
- **AI:** *Hiểu.*

### Câu 4: Method
- **AI:** Method trong class dùng để làm gì? Em lấy ví dụ từ `SinhVien`.
- **SV:** Method là hàm trong class, ví dụ `inThongTin()` để in ten và diem.
- **AI:** *Hiểu một phần.* Ví dụ đúng. Nhưng em mới nói "là hàm", chưa nói nó khác hàm thường ở đâu. Một method như `inThongTin()` lấy `ten`, `diem` từ đâu khi không có tham số truyền vào?
- **SV:** Nó dùng attribute của chính object đang gọi nó, nên `a.inThongTin()` in dữ liệu của `a`, còn `b.inThongTin()` in của `b`.
- **AI:** *Hiểu.* Em còn chưa nhắc đến `this`, nên chỗ này nên ôn thêm.

### Câu 5: Constructor
- **AI:** Constructor là gì và nó chạy khi nào?
- **SV:** Constructor là hàm tạo ra object, phải gọi trước khi dùng.
- **AI:** *Chưa hiểu.* Chỗ "tạo ra object" chưa chính xác. Ví dụ: xây xong khung nhà (cấp đất, dựng tường) rồi mới bàn giao kèm nội thất ban đầu. Khi viết `new SinhVien("An", 8.5)`, việc nào giống "dựng khung", việc nào giống "đặt nội thất"? Em giải thích lại nhé.
- **SV:** `new` cấp vùng nhớ cho object. Constructor chạy ngay sau đó để gán giá trị ban đầu cho attribute. Tên trùng tên class và không có kiểu trả về.
- **AI:** *Hiểu một phần.* Rất tốt, nhưng em chưa nhắc đến constructor mặc định khi mình không tự viết.

### Tổng kết của AI
Em hiểu Class và Object khá vững sau khi sửa. Attribute và Method đã đúng ý chính nhưng cần ôn phạm vi biến và `this`. Constructor cần ôn thêm constructor mặc định và overload.

---

## 3. Bảng đánh giá mức độ hiểu

| Khái niệm | Mức hiểu | Điểm đã vững | Điểm cần ôn |
|---|---|---|---|
| Class | Hiểu (sau ví dụ) | Là bản thiết kế, chưa phải đối tượng thật | Phân biệt class với file/chương trình |
| Object | Hiểu | Là thể hiện, có dữ liệu riêng, tạo bằng `new` | Không còn dùng từ "bản sao" |
| Attribute | Hiểu một phần | Biến của class, mỗi object giá trị riêng | Phân biệt với biến cục bộ, `private` |
| Method | Hiểu một phần | Hành vi, dùng attribute của object gọi nó | Từ khóa `this`, overload |
| Constructor | Hiểu một phần | Chạy sau `new`, gán giá trị đầu, trùng tên class | Constructor mặc định, overload |

---

## 4. Ví dụ minh họa mối quan hệ Class và Object

Bản vẽ và căn nhà: một bản vẽ (Class) tạo ra nhiều căn nhà (Object), mỗi căn có địa chỉ và màu sơn riêng.

```java
public class SinhVien {                       
    private String ten;                       
    private double diem;

    public SinhVien(String ten, double diem) { 
        this.ten = ten;
        this.diem = diem;
    }

    public void inThongTin() {                
        System.out.println(ten + ": " + diem);
    }

    public static void main(String[] args) {
        SinhVien a = new SinhVien("An", 8.5);   
        SinhVien b = new SinhVien("Binh", 7.0); 
        a.inThongTin();  // An: 8.5
        b.inThongTin();  // Binh: 7.0
    }
}
```

`SinhVien` là một class duy nhất, nhưng `a` và `b` là hai object khác nhau, có dữ liệu riêng.

---

## 5. Tự viết lại phần giải thích OOP

Class giống bản thiết kế: nó mô tả một loại đối tượng có những thông tin gì (attribute) và làm được những việc gì (method). Bản thân class chưa phải là thứ thật. Object là một "thể hiện" cụ thể tạo từ class bằng `new`, có dữ liệu riêng và độc lập với object khác cùng class. Attribute là dữ liệu mà object mang theo suốt đời nó, khác với biến cục bộ chỉ tồn tại khi method chạy. Method là hành vi của object, và nó làm việc trên dữ liệu của chính object đang gọi nó. Constructor là đoạn code chạy ngay sau khi `new` cấp vùng nhớ, để gán giá trị ban đầu cho attribute, có tên trùng tên class và không có kiểu trả về.

Trước buổi học, mình chỉ thuộc từng định nghĩa. Sau khi tự giải thích và sửa lại, mình hiểu chúng nối với nhau thế nào: class là khuôn, `new` tạo object từ khuôn, constructor khởi tạo dữ liệu, method dùng dữ liệu đó.
