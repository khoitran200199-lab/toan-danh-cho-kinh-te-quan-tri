# MASTER CONTEXT: TOÁN DÀNH CHO KINH TẾ & QUẢN TRỊ (UEH)
> **Cơ sở Dữ liệu Tri thức & Sổ bộ Thực thể Xuyên suốt Khóa học**  
> *Đại học Kinh tế TP. Hồ Chí Minh (UEH) - Học kỳ 2*  
> *Phiên bản: 2.0.0 (Cập nhật sau Chương 2 - Buổi 6: Hệ phương trình tuyến tính)*

---

## MỤC LỤC
1. [Nguyên tắc Thiết kế & Kiến trúc Thực thể](#1-nguyên-tắc-thiết-kế--kiến-trúc-thực-thể)
2. [Sổ bộ Thực thể Toàn khóa (Entity Registry)](#2-sổ-bộ-thực-thể-toàn-khóa-entity-registry)
3. [Cây Phả hệ Hệ thống (System Hierarchy)](#3-cây-phả-hệ-hệ-thống-system-hierarchy)
4. [Kho Tri thức Chi tiết Thực thể (Entity Knowledge Base)](#4-kho-tri-thức-chi-tiết-thực-thể-entity-knowledge-base)
5. [Ma trận Quan hệ Liên Thực thể (Cross-Entity Relationships)](#5-ma-trận-quan-hệ-liên-thực-thể-cross-entity-relationships)
6. [Ứng dụng Trọng tâm trong Kinh tế & Quản trị](#6-ứng-dụng-trọng-tâm-trong-kinh-tế--quản-trị)
7. [Theo dõi Tiến độ Chương (Chapter Coverage Tracker)](#7-theo-dõi-tiến-độ-chương-chapter-coverage-tracker)

---

## 1. NGUYÊN TẮC THIẾT KẾ & KIẾN TRÚC THỰC THỂ
Toàn bộ sơ đồ tư duy (Mindmap Draw.io) và tài liệu bối cảnh môn học được xây dựng dựa trên 27 quy chuẩn cốt lõi:
- **Kiến trúc phân tầng thực thể (Entity-Based Hierarchy):**
  $$\text{System} \longrightarrow \text{Entity} \longrightarrow \text{Group} \longrightarrow \text{Component} \longrightarrow \text{Detail}$$
  Thực thể là danh từ/cấu trúc toán học cốt lõi làm gốc (Spine/Root). Các khái niệm, phép toán và định lý chỉ là thuộc tính bổ trợ mô tả thực thể.
- **Thứ tự ưu tiên nhận thức:** Cấu trúc phân cấp trước (Hierarchy First) $\to$ Mối quan hệ liên kết sau (Relationship Second) $\to$ Chi tiết kỹ thuật cuối cùng (Detail Last).
- **Mã định danh Bất biến (Persistent Entity IDs):** Mỗi thực thể được gán một mã vĩnh viễn (`[E1]`, `[E2]`, ...) được bảo toàn qua mọi chương học theo nguyên lý *"Định nghĩa một lần $\to$ Mở rộng về sau $\to$ Liên kết khi cần thiết"*.
- **Ngữ pháp Thị giác Chuẩn Draw.io:** 
  - Khung bao vô hạn (`page="0"`), lưới chuẩn 10px (`grid="0"` hoặc `grid="1"`).
  - Tiêu đề toàn cục nền Slate Dark (`#1e293b`), bóng đổ nhẹ.
  - Header thực thể mang màu sắc chuyên biệt nhận diện theo chủ đề, bo góc `arcSize=10`, font chữ Helvetica 13px đậm.
  - Thẻ con mang màu phái sinh (lighter tint), bo góc `arcSize=8`, nội dung chia đầu mục ngắn gọn kèm biểu tượng nhận thức (🎯 Mục tiêu/Bản chất, ⚙️ Cơ chế/Phương pháp, 📐 Tính chất/Quy tắc, 🔄 Quy trình/Biến đổi, ⚠️ Cảnh báo/Bẫy thi cử).
  - Đường nối phân cấp trực giao (`orthogonalEdgeStyle;curved=0`), đường liên kết chéo (`CROSS_*`) có nhãn hành động rõ ràng.
  - Hỗ trợ công thức toán học LaTeX với `math="1"` trong `mxGraphModel`, bao bọc bởi `\( ... \)`.

---

## 2. SỔ BỘ THỰC THỂ TOÀN KHÓA (ENTITY REGISTRY)

| Mã ID | Tên Thực thể (Entity Name) | Biểu tượng | Mã màu Header | Mã màu Card | Giới thiệu tại | Vai trò & Bản chất Toán học |
| :---: | :--- | :---: | :---: | :---: | :---: | :--- |
| `[E1]` | **Ma trận & Các dạng Ma trận Đặc biệt** *(Matrix & Special Forms)* | 🏛️ | `#37474F`<br>viền `#212121` | `#ECEFF1`<br>viền `#546E7A` | Chương 1 (Buổi 1) | Cấu trúc dữ liệu đa chiều, bảng số chữ nhật $m \times n$, biểu diễn hệ vectơ dòng/cột và toán tử biến đổi tuyến tính. |
| `[E2]` | **Định thức của Ma trận Vuông** *(Determinant of Square Matrix)* | ⚖️ | `#1A237E`<br>viền `#0D47A1` | `#E8EAF6`<br>viền `#3949AB` | Chương 1 (Buổi 2) | Giá trị vô hướng vô cùng đặc thù gán cho ma trận vuông, đo lường sự co giãn thể tích và là "chữ ký số" chẩn đoán suy biến. |
| `[E3]` | **Ma trận Nghịch đảo & Phương trình Ma trận** *(Inverse Matrix & Matrix Equations)* | 💰 | `#1B5E20`<br>viền `#2E7D32` | `#E8F5E9`<br>viền `#388E3C` | Chương 1 (Buổi 3) | Toán tử nghịch đảo $A^{-1}$ đóng vai trò "phép chia", là chìa khóa giải quyết các phương trình ma trận và xác định điểm cân bằng kinh tế. |
| `[E4]` | **Hạng Ma trận & Phân tích Hệ Tuyến tính** *(Matrix Rank & Linear Systems)* | 🏭 | `#4A154B`<br>viền `#6B1D6D` | `#F3E5F5`<br>viền `#7B1FA2` | Chương 1 (Buổi 4) | Thước đo số chiều và số lượng tối đa các vectơ độc lập tuyến tính, xác định cấu trúc nghiệm theo Kronecker-Capelli và điều kiện OLS. |
| `[E5]` | **Hệ Phương trình Tuyến tính Tổng quát** *(General System of Linear Equations - SLE)* | 🧮 | `#B71C1C`<br>viền `#7F0000` | `#FFEBEE`<br>viền `#C62828` | Chương 2 (Buổi 6) | Cấu trúc đại số tổng quát gồm $m$ phương trình, $n$ ẩn ($AX=B$); mô hình hóa trạng thái cân bằng tương tác đa biến trong không gian $\mathbb{R}^n$. |
| `[E6]` | **Hệ Cramer & Quy tắc Định thức Cramer** *(Cramer's System & Determinant Rule)* | 🎯 | `#E65100`<br>viền `#BF360C` | `#FFF3E0`<br>viền `#FB8C00` | Chương 2 (Buổi 6) | Dạng thức chính quy của hệ tuyến tính vuông không suy biến ($m=n, \det(A) \ne 0$), cung cấp nghiệm giải tích đóng dạng tỷ số định thức $x_j = D_j/D$. |

---

## 3. CÂY PHẢ HỆ HỆ THỐNG (SYSTEM HIERARCHY)

```text
HỆ THỐNG: TOÁN CHO KINH TẾ & QUẢN TRỊ (UEH)
├── CHƯƠNG 1: ĐẠI SỐ MA TRẬN (MATRIX ALGEBRA)
│   ├── 🏛️ [E1] MA TRẬN & CÁC DẠNG ĐẶC BIỆT
│   │   ├── 1.1 🎯 Bản chất & Biểu diễn Hệ thống (Cấu trúc m×n, Hệ vectơ dòng/cột, Bảng I/O)
│   │   ├── 1.2 ⚙️ Các dạng Ma trận Đặc biệt (Ma trận Không, Vuông, Đường chéo, Đơn vị In, Tam giác, Đối xứng, Bậc thang REF)
│   │   ├── 1.3 🔄 Phép toán Đại số Ma trận (Cộng/Trừ, Nhân vô hướng, Chuyển vị AT, Nhân ma trận AB, Lũy thừa Ak)
│   │   └── 1.4 ⚠️ Bẫy Đại số & Nguy cơ Thi cử (Bẫy giao hoán AB ≠ BA, Không có phép chia, Bẫy hằng đẳng thức, Bẫy triệt tiêu)
│   │
│   ├── ⚖️ [E2] ĐỊNH THỨC CỦA MA TRẬN VUÔNG
│   │   ├── 2.1 🎯 Bản chất & Chữ ký Số học (|A|, Chỉ tồn tại cho ma trận vuông, Đo co dãn thể tích)
│   │   ├── 2.2 ⚙️ Phương pháp Tính toán theo Cấp (Cấp 1, 2, Cấp 3 Sarrus, Khai triển Laplace quy nạp, Định lý Alien Cofactors)
│   │   ├── 2.3 📐 5 Tính chất Đại số Nền tảng (Đổi chỗ dòng đổi dấu, Thừa số chung k^n, Bảo toàn qua phép biến đổi loại 3, det tam giác, det(AT)=det(A))
│   │   └── 2.4 ⚠️ Dấu hiệu Nhận biết Nhanh det=0 (Dòng 0, Dòng trùng nhau, Dòng tỉ lệ, Tổ hợp tuyến tính, Suy biến)
│   │
│   ├── 💰 [E3] MA TRẬN NGHỊCH ĐẢO & PHƯƠNG TRÌNH MA TRẬN
│   │   ├── 3.1 🎯 Điều kiện Khả nghịch & Bản chất (A·A^(-1) = In, Duy nhất, det(A) ≠ 0, Rủi ro gần suy biến Near Singularity)
│   │   ├── 3.2 ⚙️ Tính chất Hệ thống (Tự nghịch đảo, Nghịch đảo chuyển vị, Đảo chiều tích (AB)^(-1) = B^(-1)A^(-1), (kA)^(-1) = (1/k)A^(-1))
│   │   ├── 3.3 🔄 2 Phương pháp Xác định Chuẩn thi (Phương pháp Phụ hợp Adjugate A^(-1) = (1/det)·C^T, Khử Gauss-Jordan [A|In] -> [In|A^(-1)])
│   │   └── 3.4 ⚠️ Giải Phương trình Ma trận (Quy tắc Tả - Hữu: AX=B -> X=A^(-1)B, XA=B -> X=BA^(-1), AXB=C -> X=A^(-1)CB^(-1))
│   │
│   └── 🏭 [E4] HẠNG MA TRẬN & PHÂN TÍCH HỆ TUYẾN TÍNH
│       ├── 4.1 🎯 Định nghĩa & Bản chất của Hạng (ρ(A), Số vectơ độc lập tuyến tính tối đa, Cấp định thức con khác 0, Số dòng khác 0 của REF)
│       ├── 4.2 ⚙️ Biến đổi Sơ cấp Bảo toàn Hạng (Hoán đổi 2 dòng, Nhân dòng với k≠0, Cộng bội số dòng khác; Thuật toán khử Gauss)
│       ├── 4.3 📐 Tính chất & Bất đẳng thức Hạng (0 ≤ ρ(A) ≤ min(m,n), ρ(A)=ρ(AT)=ρ(AAT), ρ(AB) ≤ min(ρ(A),ρ(B)), Hạng đầy đủ Full Rank)
│       └── 4.4 ⚖️ Tam giác Vàng & Ứng dụng Kinh tế (ρ(A)=n ⟺ det(A)≠0 ⟺ ∃ A^(-1); Định lý Kronecker-Capelli; Bẫy Đa cộng tuyến OLS)
│
└── CHƯƠNG 2: HỆ PHƯƠNG TRÌNH TUYẾN TÍNH (SYSTEM OF LINEAR EQUATIONS)
    ├── 🧮 [E5] HỆ PHƯƠNG TRÌNH TUYẾN TÍNH TỔNG QUÁT (SLE)
    │   ├── 5.1 🎯 Bản chất & Biểu diễn Ma trận Hệ thống (Cấu trúc m×n, AX=B, Ma trận mở rộng [A|B], Không gian nghiệm S, Hệ tương đương)
    │   ├── 5.2 ⚖️ Tiêu chuẩn Nghiệm Kronecker - Capelli (Chẩn đoán số nghiệm qua so sánh ρ(A) & ρ(A|B) với n: Vô nghiệm, Duy nhất, Vô số nghiệm)
    │   ├── 5.3 🔄 Thuật toán Khử Gauss & Gauss - Jordan (Đưa [A|B] về REF/RREF, Phân định Ẩn cơ sở vs Ẩn tự do, Kỹ thuật thế ngược)
    │   └── 5.4 ⚠️ Bẫy Biện luận Tham số & Rủi ro Học thuật UEH (Bẫy chia dòng cho tham số, Kết luận sớm khi chưa đạt REF, Nhầm m với n, Quên dòng mâu thuẫn)
    │
    └── 🎯 [E6] HỆ CRAMER & QUY TẮC ĐỊNH THỨC CRAMER
        ├── 6.1 🎯 Bản chất & Điều kiện Cấu trúc Hệ Cramer (Hệ vuông m=n, Ma trận không suy biến det(A)=D≠0, Luôn có nghiệm duy nhất)
        ├── 6.2 ⚙️ Quy tắc Định thức Cramer & Thuật toán 4 Bước (Định thức chính D, Định thức phụ Dj thay cột j bằng B, Công thức xj = Dj/D)
        ├── 6.3 🔄 Nguồn gốc Đại số & Cầu nối Ma trận Nghịch đảo (X = A^(-1)B, Chứng minh qua Ma trận Phụ hợp, Định lý Alien Cofactors, Mẹo nhớ UEH)
        └── 6.4 ⚠️ Bẫy Suy biến D = 0 & Giới hạn Thuật toán (Bẫy tử huyệt D=0 không suy ra vô nghiệm, Bắt buộc chuyển sang Gauss, Chi phí tính toán O(n!))
```

---

## 4. KHO TRI THỨC CHI TIẾT THỰC THỂ (ENTITY KNOWLEDGE BASE)

### 🏛️ THỰC THỂ `[E1]`: MA TRẬN & CÁC DẠNG ĐẶC BIỆT
- **Định nghĩa Toán học:** Ma trận kích thước $m \times n$ là một bảng số thực gồm $m$ dòng và $n$ cột:
  $$A = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix} = (a_{ij})_{m \times n}$$
- **Hệ Vectơ Sinh:**
  - $m$ vectơ dòng trong $\mathbb{R}^n$: $\mathbf{r}_i = (a_{i1}, a_{i2}, \dots, a_{in})$.
  - $n$ vectơ cột trong $\mathbb{R}^m$: $\mathbf{c}_j = (a_{1j}, a_{2j}, \dots, a_{mj})^T$.
- **Các Dạng Ma trận Đặc biệt:**
  - *Ma trận Không ($O$):* $a_{ij} = 0, \forall i, j$.
  - *Ma trận Vuông cấp $n$ ($m=n$):* Có đường chéo chính ($a_{ii}$) và vết $\text{tr}(A) = \sum_{i=1}^n a_{ii}$.
  - *Ma trận Đường chéo:* $a_{ij} = 0, \forall i \neq j$. Ký hiệu $\text{diag}(d_1, d_2, \dots, d_n)$.
  - *Ma trận Đơn vị ($I_n$):* Ma trận đường chéo có $a_{ii} = 1, \forall i$.
  - *Ma trận Tam giác:* Tam giác trên ($U$: $a_{ij} = 0$ khi $i > j$), tam giác dưới ($L$: $a_{ij} = 0$ khi $i < j$).
  - *Ma trận Đối xứng & Phản đối xứng:* Đối xứng nếu $A = A^T$; Phản đối xứng nếu $A = -A^T$ (đặc biệt đường chéo chính phải toàn số 0).
  - *Ma trận Bậc thang (REF - Row Echelon Form):* Các dòng toàn 0 nằm dưới cùng; Phần tử khác 0 đầu tiên của dòng dưới (pivot) nằm dịch sang bên phải pivot của dòng trên.
- **Quy tắc Nhân Ma trận:** $A_{m \times p} \times B_{p \times n} = C_{m \times n}$ với $c_{ij} = \sum_{k=1}^p a_{ik} b_{kj} = \mathbf{r}_i(A) \cdot \mathbf{c}_j(B)$.
- **Cảnh báo Bẫy UEH:**
  - $AB \neq BA$ (Tổng quát không giao hoán).
  - Không có phép chia $\frac{A}{B}$.
  - $(A+B)^2 = A^2 + AB + BA + B^2 \neq A^2 + 2AB + B^2$.
  - $AB = O \nRightarrow A=O \lor B=O$.

---

### ⚖️ THỰC THỂ `[E2]`: ĐỊNH THỨC CỦA MA TRẬN VUÔNG
- **Bản chất:** Ánh xạ từ không gian ma trận vuông vào trường số thực $\det: \mathcal{M}_{n}(\mathbb{R}) \to \mathbb{R}$.
- **Phương pháp Tính:**
  - Cấp 2: $\begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc$.
  - Cấp 3 (Quy tắc Sarrus): Đường chéo chính thuận trừ chéo phụ.
  - Cấp $n$ (Laplace):
    $$\det(A) = \sum_{j=1}^n a_{ij} A_{ij} \quad (\text{khai triển theo dòng } i)$$
    trong đó phần bù đại số $A_{ij} = (-1)^{i+j} M_{ij}$, với $M_{ij}$ là định thức con bù bỏ dòng $i$, cột $j$.
  - *Định lý Alien Cofactors:* $\sum_{j=1}^n a_{ij} A_{kj} = 0$ với mọi $i \ne k$.
- **5 Tính chất Cốt tử:**
  1. Đổi chỗ 2 dòng/cột $\implies \det$ đổi dấu.
  2. Nhân một dòng với hằng số $k \implies \det$ tăng $k$ lần. **Hệ quả thi cử:** $\det(k \cdot A_{n \times n}) = k^n \det(A)$.
  3. Biến đổi dòng loại 3 ($d_i \to d_i + c \cdot d_j$) giữ nguyên $\det$.
  4. $\det$ ma trận tam giác bằng tích các phần tử đường chéo chính: $\det(A) = \prod_{i=1}^n a_{ii}$.
  5. $\det(A^T) = \det(A)$ và $\det(AB) = \det(A) \cdot \det(B)$.
- **Dấu hiệu Nhận biết $\det(A) = 0$:** Có dòng/cột bằng 0, hai dòng/cột trùng nhau, hai dòng/cột tỉ lệ, hoặc một dòng là tổ hợp tuyến tính của các dòng khác.

---

### 💰 THỰC THỂ `[E3]`: MA TRẬN NGHỊCH ĐẢO & PHƯƠNG TRÌNH MA TRẬN
- **Định nghĩa:** $A \in \mathcal{M}_n(\mathbb{R})$ khả nghịch khi và chỉ khi tồn tại duy nhất $A^{-1}$ thỏa $A A^{-1} = A^{-1} A = I_n$.
- **Điều kiện Cần & Đủ:** $\det(A) \neq 0$ (Ma trận không suy biến - Non-singular).
- **Tính chất Đại số:**
  - $(A^{-1})^{-1} = A$
  - $(A^T)^{-1} = (A^{-1})^T$
  - $(AB)^{-1} = B^{-1} A^{-1}$ (Đảo ngược thứ tự các thừa số)
  - $(kA)^{-1} = \frac{1}{k} A^{-1}$ với $k \ne 0$
  - $\det(A^{-1}) = \frac{1}{\det(A)}$
- **2 Quy trình Tìm Nghịch đảo:**
  - *Quy trình 1: Ma trận Phụ hợp (Adjugate Method - Chuẩn thi tự luận UEH):*
    1. Tính $\det(A)$. Nếu $\det(A)=0 \implies$ kết luận không khả nghịch.
    2. Lập ma trận phần bù đại số $C = (A_{ij})_{n \times n}$.
    3. Chuyển vị ma trận $C$ để thu được ma trận phụ hợp: $\text{adj}(A) = C^T$.
    4. Nhân vô hướng: $A^{-1} = \frac{1}{\det(A)} C^T$.
  - *Quy trình 2: Khử Gauss-Jordan:*
    Thiết lập ma trận khối ghép $[A \mid I_n]$ và dùng các phép biến đổi dòng sơ cấp đưa về dạng $[I_n \mid A^{-1}]$.
- **Quy tắc Giải Phương trình Ma trận (Tả - Hữu):**
  - $A X = B \implies X = A^{-1} B$ (Nhân trái 2 vế với $A^{-1}$).
  - $X A = B \implies X = B A^{-1}$ (Nhân phải 2 vế với $A^{-1}$).
  - $A X B = C \implies X = A^{-1} C B^{-1}$.

---

### 🏭 THỰC THỂ `[E4]`: HẠNG MA TRẬN & PHÂN TÍCH HỆ TUYẾN TÍNH
- **Định nghĩa:** Hạng của ma trận $A_{m \times n}$, ký hiệu $\rho(A)$ hoặc $\text{rank}(A)$, là:
  - Số lượng tối đa các vectơ dòng (hoặc cột) độc lập tuyến tính của $A$.
  - Cấp cao nhất của các định thức con khác 0 trích ra từ $A$.
  - Số lượng dòng khác 0 của ma trận bậc thang REF sau khi khử Gauss.
- **Bất đẳng thức & Tính chất:**
  - $0 \le \rho(A) \le \min(m, n)$.
  - $\rho(A) = 0 \iff A = O$.
  - $\rho(A) = \rho(A^T) = \rho(A A^T) = \rho(A^T A)$.
  - $\rho(AB) \le \min\{\rho(A), \rho(B)\}$.
  - $\rho(A+B) \le \rho(A) + \rho(B)$.
- **Mối liên hệ "Tam giác Vàng" (Cho ma trận vuông cấp $n$):**
  $$\rho(A) = n \iff \det(A) \neq 0 \iff \exists A^{-1} \iff A \text{ Không suy biến}$$
- **Định lý Kronecker-Capelli:** Xét hệ phương trình đại số tuyến tính $AX = b$ với ma trận hệ số mở rộng $\bar{A} = [A \mid b]$:
  1. $\rho(A) < \rho(\bar{A}) \iff$ Hệ **Vô nghiệm**.
  2. $\rho(A) = \rho(\bar{A}) = n \iff$ Hệ có **Nghiệm duy nhất** ($X = A^{-1}b$).
  3. $\rho(A) = \rho(\bar{A}) = r < n \iff$ Hệ có **Vô số nghiệm** (phụ thuộc vào $n - r$ ẩn số tự do).

---

### 🧮 THỰC THỂ `[E5]`: HỆ PHƯƠNG TRÌNH TUYẾN TÍNH TỔNG QUÁT (SLE)
- **Định nghĩa Đại số Tổng quát:** Hệ gồm $m$ phương trình đại số tuyến tính với $n$ ẩn số ($x_1, x_2, \dots, x_n$):
  $$\begin{cases} a_{11} x_1 + a_{12} x_2 + \cdots + a_{1n} x_n = b_1 \\ a_{21} x_1 + a_{22} x_2 + \cdots + a_{2n} x_n = b_2 \\ \vdots \\ a_{m1} x_1 + a_{m2} x_2 + \cdots + a_{mn} x_n = b_m \end{cases}$$
- **Biểu diễn Ma trận Đương lượng:**
  $$A_{m \times n} \cdot X_{n \times 1} = B_{m \times 1}$$
  trong đó:
  - Ma trận hệ số: $A = (a_{ij})_{m \times n} \in \mathcal{M}_{m \times n}(\mathbb{R})$.
  - Cột ẩn số: $X = (x_1, x_2, \dots, x_n)^T \in \mathcal{M}_{n \times 1}(\mathbb{R})$.
  - Cột hệ số tự do (vế phải): $B = (b_1, b_2, \dots, b_m)^T \in \mathcal{M}_{m \times 1}(\mathbb{R})$.
  - Ma trận hệ số mở rộng (bổ sung): $\bar{A} = [A \mid B] \in \mathcal{M}_{m \times (n+1)}(\mathbb{R})$.
- **Không gian Nghiệm & Tính Tương đương:**
  - Tập nghiệm: $S = \{X \in \mathbb{R}^n \mid AX = B\}$. Hệ vô nghiệm khi $S = \emptyset$; Hệ tương thích khi $S \neq \emptyset$.
  - Phép biến đổi tương đương: Hai hệ phương trình được gọi là tương đương khi chúng có cùng tập nghiệm $S$.
  - 3 phép biến đổi dòng sơ cấp trên $\bar{A}$ bảo toàn nguyên vẹn tập nghiệm $S$:
    1. Hoán đổi vị trí 2 dòng: $d_i \leftrightarrow d_j$.
    2. Nhân một dòng với số thực khác 0: $d_i \to k \cdot d_i \ (k \neq 0)$.
    3. Cộng vào một dòng bội số của dòng khác: $d_i \to d_i + k \cdot d_j$.
- **Định lý Kronecker - Capelli (Tiêu chuẩn Tồn tại & Cấu trúc Nghiệm):**
  Cho hệ phương trình $AX = B$ gồm $m$ phương trình, $n$ ẩn số và ma trận mở rộng $\bar{A} = [A \mid B]$:
  $$\text{Hệ có nghiệm} \iff \rho(A) = \rho(\bar{A})$$
  Ba trạng thái phân lập cấu trúc nghiệm:
  1. **Vô nghiệm (Inconsistent):**
     $$\rho(A) < \rho(\bar{A})$$
     Dấu hiệu nhận biết trên ma trận bậc thang REF: Xuất hiện dòng mâu thuẫn dạng $[0 \ 0 \dots 0 \mid c]$ với $c \neq 0$ (phương trình tương đương $0x_1 + \dots + 0x_n = c \neq 0$, vô lý).
  2. **Có nghiệm duy nhất (Unique Solution):**
     $$\rho(A) = \rho(\bar{A}) = n \quad (\text{đúng bằng số ẩn số})$$
     Mọi cột của ma trận hệ số $A$ đều có một phần tử trụ (pivot) dẫn đầu. Tập nghiệm là một điểm đơn lẻ $X^* \in \mathbb{R}^n$.
  3. **Có vô số nghiệm (Infinitely Many Solutions):**
     $$\rho(A) = \rho(\bar{A}) = r < n$$
     Hệ có $r$ ẩn cơ sở (pivot variables) và $k = n - r$ ẩn tự do (free variables/tham số). Tập nghiệm là một không gian afin con $S \subset \mathbb{R}^n$ có số chiều $\dim(S) = n - r$.
- **Thuật toán Khử Gauss & Gauss - Jordan:**
  - *Bước 1 (Lập ma trận):* Viết ma trận mở rộng $\bar{A} = [A \mid B]$.
  - *Bước 2 (Khử thuận Gauss):* Áp dụng 3 phép biến đổi dòng sơ cấp đưa $\bar{A}$ về ma trận bậc thang REF:
    $$\bar{A} \xrightarrow{\text{Gauss}} \bar{A}_{\text{REF}} = \begin{pmatrix} p_{11} & * & \cdots & * & \mid & * \\ 0 & p_{22} & \cdots & * & \mid & * \\ \vdots & \vdots & \ddots & \vdots & \mid & \vdots \\ 0 & 0 & \cdots & p_{rr} & \mid & * \\ 0 & 0 & \cdots & 0 & \mid & c \end{pmatrix}$$
  - *Bước 3 (Phân định biến số):*
    - Các cột chứa pivot $p_{ii} \ne 0$ ứng với các **Ẩn cơ sở (Pivot variables)**.
    - Các cột không chứa pivot ứng với các **Ẩn tự do (Free variables)**. Gán các ẩn tự do bằng tham số thực $t_1, t_2, \dots \in \mathbb{R}$.
  - *Bước 4 (Thế ngược Back-substitution):* Giải từ phương trình dòng cuối cùng ngược lên dòng đầu tiên, biểu diễn các ẩn cơ sở theo các tham số tự do.
  - *Gauss - Jordan:* Biến đổi tiếp tục để triệt tiêu các phần tử nằm PHÍA TRÊN các pivot, đưa về bậc thang rút gọn RREF (Reduced Row Echelon Form) với mọi pivot bằng 1 $\implies$ Đọc trực tiếp nghiệm của hệ thống mà không cần giải thế ngược.
- **Cảnh báo Bẫy Biện luận Tham số & Rủi ro Học thuật UEH:**
  - **BẪY TỬ HUYỆT 1: Chia dòng cho biểu thức chứa tham số.** Tuyệt đối không thực hiện $d_i \to \frac{1}{m-1} d_i$ trước khi xét riêng trường hợp $m = 1$. Việc chia dòng khi tham số bằng 0 sẽ làm biến mất nghiệm hoặc sinh ra nghiệm ảo phi lý.
  - **BẪY TỬ HUYỆT 2: Kết luận số nghiệm khi ma trận CHƯA ĐẠT REF.** Nhiều sinh viên vội vàng đếm dòng khác 0 hoặc so sánh hạng khi các phần tử bên dưới đường chéo chưa triệt tiêu hoàn toàn về 0.
  - **BẪY TỬ HUYỆT 3: Nhầm số phương trình $m$ với số ẩn $n$.** Để hệ có nghiệm duy nhất, điều kiện cần và đủ là $\rho(A) = \rho(\bar{A}) = n$ (bằng số ẩn), KHÔNG PHẢI bằng số phương trình $m$.
  - **BẪY TỬ HUYỆT 4: Bỏ sót giá trị tham số tại dòng mâu thuẫn.** Dòng có dạng $[0 \dots 0 \mid m^2 - 4]$ sẽ gây vô nghiệm khi $m \neq \pm 2$, nhưng khi $m = 2$ hoặc $m = -2$ thì dòng này biến thành dòng toàn 0, dẫn tới khả năng hệ có vô số nghiệm. Bắt buộc phải thay trực tiếp từng giá trị đặc biệt của tham số vào lại ma trận ban đầu để kiểm chứng độc lập.

---

### 🎯 THỰC THỂ `[E6]`: HỆ CRAMER & QUY TẮC ĐỊNH THỨC CRAMER
- **Định nghĩa Hệ Cramer:** Hệ phương trình đại số tuyến tính $AX = B$ được gọi là một **Hệ Cramer** khi và chỉ khi thỏa mãn đồng thời hai điều kiện cấu trúc:
  1. Số phương trình bằng đúng số ẩn số ($m = n$, ma trận hệ số $A$ là ma trận vuông cấp $n$).
  2. Ma trận hệ số $A$ không suy biến: $\det(A) = D \neq 0$.
- **Định lý Cramer:** Mọi hệ Cramer **LUÔN LUÔN CÓ NGHIỆM DUY NHẤT**.
- **Cơ sở Đại số & Nguồn gốc từ Ma trận Nghịch đảo:**
  Do $\det(A) \neq 0$, ma trận $A$ khả nghịch và tồn tại duy nhất ma trận nghịch đảo $A^{-1} \in [E3]$. Khi đó:
  $$AX = B \iff X = A^{-1} B = \frac{1}{\det(A)} \text{adj}(A) \cdot B$$
  Tọa độ thứ $j$ của vectơ nghiệm $X = (x_1, x_2, \dots, x_n)^T$ là tích của dòng $j$ của ma trận phụ hợp $\text{adj}(A) = C^T$ với vectơ vế phải $B$:
  $$x_j = \frac{1}{\det(A)} \sum_{i=1}^n (\text{adj}(A))_{ji} b_i = \frac{1}{\det(A)} \sum_{i=1}^n b_i A_{ij}$$
  Theo công thức khai triển Laplace theo cột thứ $j$, biểu thức $\sum_{i=1}^n b_i A_{ij}$ chính là định thức của ma trận thu được bằng cách thay cột thứ $j$ của $A$ bằng vectơ $B$:
  $$\sum_{i=1}^n b_i A_{ij} = \det(A_j) = D_j \implies x_j = \frac{D_j}{D}$$
- **Hệ thống Công thức & Quy tắc Cramer:**
  - Định thức chính: $D = \det(A) \neq 0$.
  - Định thức phụ $D_j = \det(A_j)$ ($j = 1, 2, \dots, n$): Định thức của ma trận $A_j$ nhận được từ $A$ bằng cách thay cột thứ $j$ bằng cột hệ số tự do $B = (b_1, b_2, \dots, b_n)^T$:
    $$D_j = \begin{vmatrix} a_{11} & \cdots & a_{1,j-1} & b_1 & a_{1,j+1} & \cdots & a_{1n} \\ a_{21} & \cdots & a_{2,j-1} & b_2 & a_{2,j+1} & \cdots & a_{2n} \\ \vdots & \ddots & \vdots & \vdots & \vdots & \ddots & \vdots \\ a_{n1} & \cdots & a_{n,j-1} & b_n & a_{n,j+1} & \cdots & a_{nn} \end{vmatrix}$$
  - Công thức nghiệm đóng:
    $$x_j = \frac{D_j}{D} \quad (\forall j = 1, 2, \dots, n)$$
- **Quy trình 4 Bước Chuẩn Tự luận UEH:**
  - *Bước 1:* Thiết lập ma trận hệ số $A$ và tính định thức chính $D = \det(A)$.
  - *Bước 2:* Biện luận điều kiện Cramer: Khẳng định $D \neq 0$ để kết luận hệ là Hệ Cramer có nghiệm duy nhất.
  - *Bước 3:* Thiết lập các ma trận thành phần $A_j$ và tính các định thức phụ $D_j$.
  - *Bước 4:* Tính toán và kết luận nghiệm $x_j = \frac{D_j}{D}$. Nếu đề bài chỉ yêu cầu tìm một biến kinh tế cụ thể (ví dụ: sản lượng cân bằng $Y^*$ hoặc giá cân bằng $P_1^*$), chỉ cần tính duy nhất định thức phụ tương ứng.
- **Cảnh báo Bẫy Suy biến $D = 0$ & Giới hạn Thuật toán UEH:**
  - **BẪY TỬ HUYỆT KINH ĐIỂN: $D = 0 \nRightarrow$ Hệ vô nghiệm!**  
    Khi $D = 0$, quy tắc Cramer hoàn toàn **BẤT LỰC (Inapplicable)**. Ta tuyệt đối KHÔNG ĐƯỢC KẾT LUẬN hệ vô nghiệm. Lúc này hệ phương trình có thể **Vô nghiệm** hoặc **Vô số nghiệm**.
  - **HÀNH ĐỘNG BẮT BUỘC:** Khi $D = 0$, sinh viên bắt buộc phải từ bỏ phương pháp Cramer và quay lại **Thuật toán khử Gauss `[E5]`** trên ma trận mở rộng $\bar{A} = [A \mid B]$ để so sánh hạng $\rho(A)$ và $\rho(\bar{A})$.
  - **BẪY $D_1 = D_2 = \dots = D_n = 0$:** Nếu $D = 0$ và đồng thời tất cả các $D_j = 0$, hệ vẫn có thể VÔ NGHIỆM! Không được ngộ nhận hệ có vô số nghiệm.
  - **Chi phí Thuật toán & Phạm vi Ứng dụng:**
    - Tính $n+1$ định thức cấp $n$ đòi hỏi chi phí tính toán $O((n+1)!)$ bằng định nghĩa hoặc $O(n^4)$ bằng biến đổi, trong khi khử Gauss chỉ tốn $O(n^3)$.
    - Phương pháp Cramer chỉ nên dùng khi $n \le 3$ hoặc khi bài toán chứa tham số cần nghiệm giải tích tường minh cho một biến duy nhất. Với bài toán số liệu thực tế lớn ($n \ge 4$), khử Gauss là lựa chọn bắt buộc.

---

## 5. MA TRẬN QUAN HỆ LIÊN THỰC THỂ (CROSS-ENTITY RELATIONSHIPS)

| Mã Liên kết | Thực thể Nguồn | Thực thể Đích | Cơ chế Toán học | Ý nghĩa & Ứng dụng Thực tiễn |
| :---: | :---: | :---: | :--- | :--- |
| `CROSS_E1_E2` | `[E1]` | `[E2]` | Định thức chỉ xác định trên tập hợp con Ma trận Vuông $A_{n \times n} \in [E1]$ | Ngăn chặn sai lầm tính định thức cho ma trận chữ nhật trong mô hình dữ liệu bảng. |
| `CROSS_E2_E3` | `[E2]` | `[E3]` | $\det(A) \neq 0$ là điều kiện ắt có và đủ để $A$ khả nghịch; Hệ số nghịch đảo $A^{-1} = \frac{1}{\det(A)} C^T$ | Kiểm tra tính ổn định của mô hình kinh tế; Cảnh báo rủi ro near-singularity khi $\det \approx 0$. |
| `CROSS_E1_E4` | `[E1]` | `[E4]` | Dùng 3 phép biến đổi dòng sơ cấp đưa $A \in [E1]$ về ma trận bậc thang REF để đếm pivots | Xác định số chiều thực tế của không gian sản xuất hoặc danh mục đầu tư. |
| `CROSS_E4_E2_E3` | `[E4]` | `[E2]`, `[E3]` | Quan hệ Tam giác Vàng: $\rho(A) = n \iff \det(A) \ne 0 \iff \exists A^{-1}$ | Chẩn đoán tính đóng/mở và tính duy nhất nghiệm của toàn bộ hệ cân bằng kinh tế. |
| `CROSS_E3_E4` | `[E3]` | `[E4]` | Mọi ma trận khả nghịch đều có hạng đầy đủ: $\rho(A) = n$ | Bảo toàn số chiều dữ liệu khi thực hiện biến đổi ma trận trong kinh tế lượng. |
| `CROSS_E5_E6` | `[E5]` | `[E6]` | Hệ Cramer là trường hợp riêng chính quy của Hệ tuyến tính tổng quát khi $m = n$ và $\det(A) \neq 0$ | Thu hẹp bài toán cân bằng từ không gian tổng quát sang mô hình giải tích đóng có nghiệm duy nhất. |
| `CROSS_E6_E5_FALLBACK` | `[E6]` | `[E5]` | Khi định thức chính $D = 0$, quy tắc Cramer bất lực; Bắt buộc quay về Thuật toán khử Gauss trên $\bar{A}$ | Ngăn chặn bẫy thi cử tử huyệt kết luận vội vàng; Bảo đảm phân loại chính xác vô nghiệm hay vô số nghiệm. |
| `CROSS_E4_E5` | `[E4]` | `[E5]` | Hạng $\rho(A)$ và $\rho(\bar{A})$ là điều kiện ắt có và đủ của Định lý Kronecker - Capelli | Cung cấp thuật toán tự động kiểm tra tính tương thích và số ẩn tự do của hệ kinh tế đa ngành. |
| `CROSS_E2_E6` | `[E2]` | `[E6]` | Định thức cấp $n$ từ `[E2]` là công cụ định lượng tính tỷ số $x_j = \frac{D_j}{D}$ | Tính toán giải tích trực tiếp nghiệm của từng biến kinh tế riêng lẻ mà không cần giải toàn bộ hệ thống. |
| `CROSS_E3_E6` | `[E3]` | `[E6]` | Nghiệm giải tích Cramer $x_j = \frac{D_j}{D}$ đồng nhất về mặt đại số với nghiệm ma trận $X = A^{-1} B$ | Chứng minh tính nhất quán giữa đại số ma trận nghịch đảo và lý thuyết định thức phụ hợp. |

---

## 6. ỨNG DỤNG TRỌNG TÂM TRONG KINH TẾ & QUẢN TRỊ

1. **Mô hình Cân bằng Thị trường Nhiều Hàng hóa (Multi-Market Equilibrium):**
   - Thiết lập hệ hàm cung - cầu tương tác giữa $n$ sản phẩm có quan hệ thay thế hoặc bổ sung:
     $$Q_{Si}(P_i) = Q_{Di}(P_1, P_2, \dots, P_n) \quad (i = 1, 2, \dots, n)$$
   - Chuyển hệ về dạng ma trận $A P = B$, với $P = (P_1, P_2, \dots, P_n)^T$ là vectơ giá cân bằng.
   - Khi $\det(A) \neq 0$, hệ là Hệ Cramer, nghiệm giá cân bằng thị trường được xác định duy nhất bởi $P_j^* = \frac{D_j}{D}$.
2. **Mô hình Cân bằng Thu nhập Quốc dân Keynesian & Đánh giá Số nhân Chính sách:**
   - Hệ phương trình kinh tế vĩ mô đóng có chính phủ:
     $$\begin{cases} Y = C + I_0 + G_0 \\ C = C_0 + c Y_d \\ Y_d = Y - T \\ T = T_0 + t Y \end{cases}$$
   - Đưa về hệ phương trình tuyến tính dạng ma trận cho 2 biến nội sinh $(Y, C)$:
     $$\begin{pmatrix} 1 & -1 \\ -c(1-t) & 1 \end{pmatrix} \begin{pmatrix} Y \\ C \end{pmatrix} = \begin{pmatrix} I_0 + G_0 \\ C_0 - c T_0 \end{pmatrix}$$
   - Tính định thức chính: $D = 1 - c(1-t) > 0$ (do khuynh hướng tiêu dùng biên $0 < c < 1$ và thuế suất biên $0 < t < 1$).
   - Áp dụng quy tắc Cramer tính sản lượng cân bằng quốc dân:
     $$Y^* = \frac{D_Y}{D} = \frac{C_0 - c T_0 + I_0 + G_0}{1 - c(1-t)}$$
   - Đạo hàm riêng để tính **Số nhân Chi tiêu Chính phủ**: $k_G = \frac{\partial Y^*}{\partial G_0} = \frac{1}{1 - c(1-t)} > 1$.
3. **Mô hình Cân bằng Kinh tế Vĩ mô IS-LM:**
   - Tương tác đồng thời giữa Thị trường Hàng hóa (Đường IS) và Thị trường Tiền tệ (Đường LM):
     $$\begin{cases} \text{IS}: & Y = C(Y) + I(r) + G_0 \implies (1 - c)Y + a r = C_0 + I_0 + G_0 \\ \text{LM}: & M^s = L_1(Y) + L_2(r) \implies k Y - h r = M_0 \end{cases}$$
   - Chuyển về hệ 2 phương trình bậc nhất 2 ẩn $(Y, r)$ dạng ma trận:
     $$\begin{pmatrix} 1-c & a \\ k & -h \end{pmatrix} \begin{pmatrix} Y \\ r \end{pmatrix} = \begin{pmatrix} A_0 \\ M_0 \end{pmatrix}$$
   - Định thức chính: $D = -(1-c)h - ak < 0$. Vì $D \neq 0$, hệ luôn có điểm cân bằng vĩ mô $(Y^*, r^*)$ duy nhất:
     $$Y^* = \frac{D_Y}{D}, \quad r^* = \frac{D_r}{D}$$
4. **Phân tích Cân đối Đầu vào - Đầu ra Leontief (Static Input-Output Model):**
   - Cho ma trận hệ số kỹ thuật $A_{n \times n}$ và vectơ cầu cuối cùng $D_{n \times 1}$.
   - Phương trình cân đối tổng sản lượng: $X = AX + D \iff (I - A)X = D$.
   - Giải bằng thuật toán khử Gauss hoặc ma trận nghịch đảo Leontief $X = (I - A)^{-1} D$ để xác định kế hoạch sản xuất của toàn bộ các ngành kinh tế quốc dân.
5. **Bài toán Phân bổ Nguồn lực Sản xuất Khan hiếm & Hoạch định Tối ưu:**
   - Doanh nghiệp sản xuất $n$ loại sản phẩm bằng $m$ loại tài nguyên khan hiếm.
   - Hệ phương trình công nghệ: $A x = b$, trong đó $a_{ij}$ là định mức tiêu hao tài nguyên $i$ cho một đơn vị sản phẩm $j$, $b_i$ là giới hạn tài nguyên khả dụng.
   - Khi $m < n$ (số tài nguyên ít hơn số loại sản phẩm), hệ có vô số nghiệm phụ thuộc $n - r$ tham số tự do, cho phép nhà quản trị lựa chọn phương án sản xuất tối đa hóa lợi nhuận.

---

## 7. THEO DÕI TIẾN ĐỘ CHƯƠNG (CHAPTER COVERAGE TRACKER)

| Chương học | Tên Chương | Nội dung Buổi học | Trạng thái Mindmap | Trạng thái Master Context | File Bản đồ Mindmap |
| :---: | :--- | :--- | :---: | :---: | :--- |
| **Chương 1** | **Đại số ma trận** | • Buổi 1: Ma trận & Ma trận đặc biệt<br>• Buổi 2: Định thức ma trận vuông<br>• Buổi 3: Ma trận nghịch đảo<br>• Buổi 4: Hạng của ma trận | ✅ **HOÀN THÀNH** | ✅ **HOÀN THÀNH** | `Chương 1 - Đại số ma trận.drawio.xml` |
| **Chương 2** | **Hệ phương trình tuyến tính** | • Buổi 6: Hệ PTTT tổng quát, Kronecker-Capelli, Khử Gauss, Hệ Cramer & Quy tắc Cramer | ✅ **HOÀN THÀNH**<br>(Kiến trúc 5 Cột Tuần tự E2 ➔ E6) | ✅ **HOÀN THÀNH** | `Drawio/Chương 2 - Hệ phương trình tuyến tính.drawio.xml` |
| **Chương 3** | **Không gian vectơ $\mathbb{R}^n$** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |
| **Chương 4** | **Phép tính vi phân hàm nhiều biến** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |
| **Chương 5** | **Bài toán tối ưu trong kinh tế** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |

---
*Tài liệu được biên soạn và bảo trì tự động theo chuẩn học thuật UEH.*
