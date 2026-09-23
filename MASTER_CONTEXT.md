# MASTER CONTEXT: TOÁN DÀNH CHO KINH TẾ & QUẢN TRỊ (UEH)
> **Cơ sở Dữ liệu Tri thức & Sổ bộ Thực thể Xuyên suốt Khóa học**  
> *Đại học Kinh tế TP. Hồ Chí Minh (UEH) - Học kỳ 2*  
> *Phiên bản: 1.0.0 (Cập nhật sau Chương 1)*

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
  - Khung bao vô hạn (`page="0"`), lưới chuẩn 10px (`grid="1" gridSize="10"`).
  - Tiêu đề toàn cục nền Slate Dark (`#1e293b`), bóng đổ nhẹ.
  - Header thực thể mang màu sắc chuyên biệt nhận diện theo chủ đề, bo góc `arcSize=10`, font chữ Helvetica 13px đậm.
  - Thẻ con mang màu phái sinh (lighter tint), bo góc `arcSize=8`, nội dung chia đầu mục ngắn gọn kèm biểu tượng nhận thức (🎯 Mục tiêu/Bản chất, ⚙️ Cơ chế/Phương pháp, 📐 Tính chất/Quy tắc, 🔄 Quy trình/Biến đổi, ⚠️ Cảnh báo/Bẫy thi cử).
  - Đường nối phân cấp trực giao (`orthogonalEdgeStyle;curved=0`), đường liên kết chéo (`CROSS_*`) có nhãn hành động rõ ràng.

---

## 2. SỔ BỘ THỰC THỂ TOÀN KHÓA (ENTITY REGISTRY)

| Mã ID | Tên Thực thể (Entity Name) | Biểu tượng | Mã màu Header | Mã màu Card | Giới thiệu tại | Vai trò & Bản chất Toán học |
| :---: | :--- | :---: | :---: | :---: | :---: | :--- |
| `[E1]` | **Ma trận & Các dạng Ma trận Đặc biệt** *(Matrix & Special Forms)* | 🏛️ | `#37474F`<br>viền `#212121` | `#ECEFF1`<br>viền `#546E7A` | Chương 1 (Buổi 1) | Cấu trúc dữ liệu đa chiều, bảng số chữ nhật $m \times n$, biểu diễn hệ vectơ dòng/cột và toán tử biến đổi tuyến tính. |
| `[E2]` | **Định thức của Ma trận Vuông** *(Determinant of Square Matrix)* | ⚖️ | `#1A237E`<br>viền `#0D47A1` | `#E8EAF6`<br>viền `#3949AB` | Chương 1 (Buổi 2) | Giá trị vô hướng vô cùng đặc thù gán cho ma trận vuông, đo lường sự co giãn thể tích và là "chữ ký số" chẩn đoán suy biến. |
| `[E3]` | **Ma trận Nghịch đảo & Phương trình Ma trận** *(Inverse Matrix & Matrix Equations)* | 💰 | `#1B5E20`<br>viền `#2E7D32` | `#E8F5E9`<br>viền `#388E3C` | Chương 1 (Buổi 3) | Toán tử nghịch đảo $A^{-1}$ đóng vai trò "phép chia", là chìa khóa giải quyết các phương trình ma trận và xác định điểm cân bằng kinh tế. |
| `[E4]` | **Hạng Ma trận & Phân tích Hệ Tuyến tính** *(Matrix Rank & Linear Systems)* | 🏭 | `#4A154B`<br>viền `#6B1D6D` | `#F3E5F5`<br>viền `#7B1FA2` | Chương 1 (Buổi 4) | Thước đo số chiều và số lượng tối đa các vectơ độc lập tuyến tính, xác định cấu trúc nghiệm theo Kronecker-Capelli và điều kiện OLS. |

---

## 3. CÂY PHẢ HỆ HỆ THỐNG (SYSTEM HIERARCHY)

```text
HỆ THỐNG: TOÁN CHO KINH TẾ & QUẢN TRỊ (UEH)
└── CHƯƠNG 1: ĐẠI SỐ MA TRẬN (MATRIX ALGEBRA)
    ├── 🏛️ [E1] MA TRẬN & CÁC DẠNG ĐẶC BIỆT
    │   ├── 1.1 🎯 Bản chất & Biểu diễn Hệ thống (Cấu trúc m×n, Hệ vectơ dòng/cột, Bảng I/O)
    │   ├── 1.2 ⚙️ Các dạng Ma trận Đặc biệt (Ma trận Không, Vuông, Đường chéo, Đơn vị In, Tam giác, Đối xứng, Bậc thang REF)
    │   ├── 1.3 🔄 Phép toán Đại số Ma trận (Cộng/Trừ, Nhân vô hướng, Chuyển vị AT, Nhân ma trận AB, Lũy thừa Ak)
    │   └── 1.4 ⚠️ Bẫy Đại số & Nguy cơ Thi cử (Bẫy giao hoán AB ≠ BA, Không có phép chia, Bẫy hằng đẳng thức, Bẫy triệt tiêu)
    │
    ├── ⚖️ [E2] ĐỊNH THỨC CỦA MA TRẬN VUÔNG
    │   ├── 2.1 🎯 Bản chất & Chữ ký Số học (|A|, Chỉ tồn tại cho ma trận vuông, Đo co dãn thể tích)
    │   ├── 2.2 ⚙️ Phương pháp Tính toán theo Cấp (Cấp 1, 2, Cấp 3 Sarrus, Khai triển Laplace quy nạp, Định lý Alien Cofactors)
    │   ├── 2.3 📐 5 Tính chất Đại số Nền tảng (Đổi chỗ dòng đổi dấu, Thừa số chung k^n, Bảo toàn qua phép biến đổi loại 3, det tam giác, det(AT)=det(A))
    │   └── 2.4 ⚠️ Dấu hiệu Nhận biết Nhanh det=0 (Dòng 0, Dòng trùng nhau, Dòng tỉ lệ, Tổ hợp tuyến tính, Suy biến)
    │
    ├── 💰 [E3] MA TRẬN NGHỊCH ĐẢO & PHƯƠNG TRÌNH MA TRẬN
    │   ├── 3.1 🎯 Điều kiện Khả nghịch & Bản chất (A·A^(-1) = In, Duy nhất, det(A) ≠ 0, Rủi ro gần suy biến Near Singularity)
    │   ├── 3.2 ⚙️ Tính chất Hệ thống (Tự nghịch đảo, Nghịch đảo chuyển vị, Đảo chiều tích (AB)^(-1) = B^(-1)A^(-1), (kA)^(-1) = (1/k)A^(-1))
    │   ├── 3.3 🔄 2 Phương pháp Xác định Chuẩn thi (Phương pháp Phụ hợp Adjugate A^(-1) = (1/det)·C^T, Khử Gauss-Jordan [A|In] -> [In|A^(-1)])
    │   └── 3.4 ⚠️ Giải Phương trình Ma trận (Quy tắc Tả - Hữu: AX=B -> X=A^(-1)B, XA=B -> X=BA^(-1), AXB=C -> X=A^(-1)CB^(-1))
    │
    └── 🏭 [E4] HẠNG MA TRẬN & PHÂN TÍCH HỆ TUYẾN TÍNH
        ├── 4.1 🎯 Định nghĩa & Bản chất của Hạng (ρ(A), Số vectơ độc lập tuyến tính tối đa, Cấp định thức con khác 0, Số dòng khác 0 của REF)
        ├── 4.2 ⚙️ Biến đổi Sơ cấp Bảo toàn Hạng (Hoán đổi 2 dòng, Nhân dòng với k≠0, Cộng bội số dòng khác; Thuật toán khử Gauss)
        ├── 4.3 📐 Tính chất & Bất đẳng thức Hạng (0 ≤ ρ(A) ≤ min(m,n), ρ(A)=ρ(AT)=ρ(AAT), ρ(AB) ≤ min(ρ(A),ρ(B)), Hạng đầy đủ Full Rank)
        └── 4.4 ⚖️ Tam giác Vàng & Ứng dụng Kinh tế (ρ(A)=n ⟺ det(A)≠0 ⟺ ∃ A^(-1); Định lý Kronecker-Capelli; Bẫy Đa cộng tuyến OLS)
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

## 5. MA TRẬN QUAN HỆ LIÊN THỰC THỂ (CROSS-ENTITY RELATIONSHIPS)

| Mã Liên kết | Thực thể Nguồn | Thực thể Đích | Cơ chế Toán học | Ý nghĩa & Ứng dụng Thực tiễn |
| :---: | :---: | :---: | :--- | :--- |
| `CROSS_E1_E2` | `[E1]` | `[E2]` | Định thức chỉ xác định trên tập hợp con Ma trận Vuông $A_{n \times n} \in [E1]$ | Ngăn chặn sai lầm tính định thức cho ma trận chữ nhật trong mô hình dữ liệu bảng. |
| `CROSS_E2_E3` | `[E2]` | `[E3]` | $\det(A) \neq 0$ là điều kiện ắt có và đủ để $A$ khả nghịch; Hệ số nghịch đảo $A^{-1} = \frac{1}{\det(A)} C^T$ | Kiểm tra tính ổn định của mô hình kinh tế; Cảnh báo rủi ro near-singularity khi $\det \approx 0$. |
| `CROSS_E1_E4` | `[E1]` | `[E4]` | Dùng 3 phép biến đổi dòng sơ cấp đưa $A \in [E1]$ về ma trận bậc thang REF để đếm pivots | Xác định số chiều thực tế của không gian sản xuất hoặc danh mục đầu tư. |
| `CROSS_E4_E2_E3` | `[E4]` | `[E2]`, `[E3]` | Quan hệ Tam giác Vàng: $\rho(A) = n \iff \det(A) \ne 0 \iff \exists A^{-1}$ | Chẩn đoán tính đóng/mở và tính duy nhất nghiệm của toàn bộ hệ cân bằng kinh tế. |
| `CROSS_E3_E4` | `[E3]` | `[E4]` | Mọi ma trận khả nghịch đều có hạng đầy đủ: $\rho(A) = n$ | Bảo toàn số chiều dữ liệu khi thực hiện biến đổi ma trận trong kinh tế lượng. |

---

## 6. ỨNG DỤNG TRỌNG TÂM TRONG KINH TẾ & QUẢN TRỊ

1. **Phân tích Cân bằng Kinh tế Vĩ mô (Mô hình IS-LM):**
   - Chuyển hệ phương trình thị trường hàng hóa (IS) và thị trường tiền tệ (LM) về dạng ma trận $A X = d$.
   - Tính $\det(A)$ để khẳng định sự tồn tại điểm cân bằng vĩ mô $(Y^*, r^*)$ duy nhất; Sử dụng $X = A^{-1}d$ hoặc quy tắc Cramer để phân tích độ nhạy của chính sách tài khóa và tiền tệ.
2. **Mô hình Cân đối Liên ngành Leontief (Input-Output Model):**
   - Cho ma trận hệ số kỹ thuật $A$ và vectơ cầu cuối dụng $D$.
   - Phương trình cân đối tổng sản lượng: $X = AX + D \iff (I - A)X = D$.
   - Điều kiện kinh tế học Hawkins-Simon và nghịch đảo Leontief: Nghiệm tổng sản lượng khả thi $X = (I - A)^{-1} D$ đòi hỏi $\det(I - A) > 0$.
3. **Kinh tế lượng & Phân tích Hồi quy Tuyến tính (OLS):**
   - Ước lượng vectơ tham số hồi quy: $\hat{\beta} = (X^T X)^{-1} X^T y$.
   - Đòi hỏi ma trận biến độc lập $X_{n \times k}$ phải có hạng cột đầy đủ: $\text{rank}(X) = k$.
   - **Bẫy Đa cộng tuyến hoàn hảo (Multicollinearity):** Nếu một biến độc lập là tổ hợp tuyến tính của các biến khác, $\text{rank}(X) < k \implies \det(X^T X) = 0 \implies X^T X$ suy biến, thuật toán OLS bị sụp đổ hoàn toàn.
4. **Mô hình Xích Markov trong Quản trị Khách hàng & Thị phần:**
   - Ma trận chuyển trạng thái $P$. Trạng thái cân bằng dài hạn $\pi^*$ là nghiệm của phương trình ma trận $\pi^* P = \pi^*$ tương đương $(\mathbf{P}^T - I)\pi^* = \mathbf{0}$, giải bằng phân tích hạng và nghiệm hệ phương trình thuần nhất.

---

## 7. THEO DÕI TIẾN ĐỘ CHƯƠNG (CHAPTER COVERAGE TRACKER)

| Chương học | Tên Chương | Nội dung Buổi học | Trạng thái Mindmap | Trạng thái Master Context | File Bản đồ Mindmap |
| :---: | :--- | :--- | :---: | :---: | :--- |
| **Chương 1** | **Đại số ma trận** | • Buổi 1: Ma trận & Ma trận đặc biệt<br>• Buổi 2: Định thức ma trận vuông<br>• Buổi 3: Ma trận nghịch đảo<br>• Buổi 4: Hạng của ma trận | ✅ **HOÀN THÀNH** | ✅ **HOÀN THÀNH** | `Chương 1 - Đại số ma trận.drawio.xml` |
| **Chương 2** | **Hệ phương trình tuyến tính** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |
| **Chương 3** | **Không gian vectơ $\mathbb{R}^n$** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |
| **Chương 4** | **Phép tính vi phân hàm nhiều biến** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |
| **Chương 5** | **Bài toán tối ưu trong kinh tế** | *Sắp triển khai theo lộ trình UEH* | ⏳ Chờ xử lý | ⏳ Chờ xử lý | *(Chưa tạo)* |

---
*Tài liệu được biên soạn và bảo trì tự động theo chuẩn học thuật UEH.*
