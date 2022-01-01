# CS116-HierarchicalClustering

Bài toán phân cụm là một nhánh ứng dụng chính của lĩnh vực Học không giám sát (Unsupervised Learning), trong đó dữ liệu huấn luyện trong bài toán chưa được dán nhãn. Trong trường hợp này, thuật toán sẽ tìm cách phân cụm - chia dữ liệu thành từng nhóm có đặc điểm tương tự nhau, nhưng đồng thời đặc tính giữa các nhóm đó lại phải càng khác biệt càng tốt.
	Có nhiều phương pháp để thực hiện gom nhóm dữ liệu, mỗi cách sẽ có mục đích cũng như hiệu quả khác nhau, tùy vào mục đích và yêu cầu của bài toán. Trong bài viết này, nhóm sẽ đề cập đến một trong những phương pháp gom cụm khá phổ biến, đó là: 
Hierarchical Clustering (phân cụm phân cấp)

Khi sử dụng thuật toán Hierarchical Clustering, chúng ta không cần phải khai báo trước số lượng cụm, thay vào đó, thuật toán chỉ yêu cầu phải xác định thước đo về sự khác biệt giữa hai cụm (không giao nhau) với nhau. 
Phương pháp phân cụm phân cấp hoạt động thông qua việc nhóm dữ liệu thành một cây các cụm. Theo phương pháp này, chúng ta biểu diễn được những sự phân cấp, trong đó mỗi cụm được hình thành bằng cách hợp nhất tất cả các cụm ở cấp thấp hơn. Sự phân cấp này được thể hiện qua đồ thị dendrogram.
 
Trước khi thực hiện gom cụm, ta cần phải xác định tiêu chí gom cụm và điều kiện dừng của bài toán. Khi đã xác định được, bài toán được mô tả như sau:

                    WHILE (điều kiện dừng = = False) DO
                    •	Chọn hai cụm gần nhau nhất theo tiêu chí đã xác định ban đầu.
                    •	Sát nhập hai cụm gần nhau thành cụm lớn hơn.
                    END WHILE;


BÀI TOÁN:
         Giả sử có 6 điểm dữ liệu: A, B, C, D, E và F (như hình vẽ)
 
![image](https://user-images.githubusercontent.com/81065789/147846213-44a3874e-3c06-4c23-b4cd-f0b5fabe3134.png)

A/ Chiến lược hợp nhất (agglomerative):
Bước 1: Phân cụm phân cấp theo chiến lược hợp nhất bắt đầu bằng cách coi mỗi điểm dữ liệu là một cụm riêng biệt.
Bước 2: Xác định khoảng cách giữa các cụm với nhau. Gom 2 cụm có khoảng cách gần nhất với nhau. Đồng thời xác định tâm mới của cụm vừa gom. Tiếp tục lặp lại cho đến khi chỉ còn 1 cụm duy nhất.
![Quy trình gom cụm hợp nhất](https://user-images.githubusercontent.com/81065789/147846115-bdc89dce-dad9-49bb-bdad-c24981f9f3ca.gif)
![Kết quả](https://user-images.githubusercontent.com/81065789/147846163-1790ff52-9961-4106-8621-492f87214012.png)

B/ Chiến lược phân chia (devise):
Bước 1: Phân cụm phân cấp theo chiến lược phân chia bắt đầu bằng cách coi mọi điểm dữ liệu đều nằm trong một cụm duy nhất (S1).
Bước 2: Chúng ta sẽ lựa chọn ra điểm F là điểm đầu tiên thuộc cụm mới vì khoảng cách so với các điểm còn lại là xa nhất. Tiếp tục lặp lại cho các điểm dữ liệu trong S1.
Bước 3: Đệ quy trên từng cụm con đến khi mỗi điểm dữ liệu là 1 cụm riêng biệt.
![Quy trình gom cụm phân chia](https://user-images.githubusercontent.com/81065789/147846182-3c0a1a32-4cdf-4b5b-a959-e337d0487798.gif)
![Kết quả](https://user-images.githubusercontent.com/81065789/147846186-28452018-47e7-4b04-832c-70885926a757.png)


