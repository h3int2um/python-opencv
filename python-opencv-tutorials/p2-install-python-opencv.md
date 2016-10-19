# Cài đặt OpenCV trên Ubuntu 16.04

Thực hiện: Thi Minh Nhựt - Email: thiminhnhut@gmail.com

Thời gian: Ngày 20 tháng 10 năm 2016

## Tài liệu tham khảo

[OpenCV Computer Vision with Python, Joseph Howse, Packt Publishing, April 2013](https://github.com/h3int2um/python-opencv/blob/master/references/OpenCV_Computer_Vision_with_Python.pdf)

## Hướng dẫn cài đặt OpenCV từ Ubutnu repository

Khi thực hiện cài đặt `OpenCV` từ `Ubuntu respository`, bị hạn chế một số chức năng 
(ví dụ: một chức năng liên quan đến `camera`) và chỉ cài được phiên bản cũ của `OpenCV`.

* Cách 1: Mở cửa sổ Terminal và thực hiện các lệnh sau:

		$ sudo apt-get update
	
		$ sudo apt-get install python-numpy
	
		$ sudo apt-get install python-scipy
	
		$ sudo apt-get install libopencv-*
	
		$ sudo apt-get install python-opencv
	
* Cách 2: Sử dụng script [install_opencv_ubuntu_repository.sh](https://github.com/h3int2um/python-opencv/blob/master/source-code/install_opencv_ubuntu_repository.sh)	
	
	- Bước 1: Download script [install_opencv_ubuntu_repository.sh](https://github.com/h3int2um/python-opencv/blob/master/source-code/install_opencv_ubuntu_repository.sh)
	
	- Bước 2: Mở cửa sổ Terminal và thực hiện các lệnh sau:
	
			$ chmod +x install_opencv_ubuntu_repository.sh
			
			$ ./install_opencv_ubuntu_repository.sh
			
		Làm theo hướng dẫn để hoàn thành quá trình cài đặt.
	
## Hướng dẫn cài đặt OpenCV từ mã nguồn bằng CMake

Khuyên dùng cách này, cài đặt theo cách này có nhiều chức năng hơn và cài đặt được phiên bản mới của `OpenCV`.

- Bước 1: Tải script [install_opencv_ubuntu_cmake.sh](https://github.com/h3int2um/python-opencv/blob/master/source-code/install_opencv_ubuntu_cmake.sh)

- Bước 2: Di chuyển đến thư mục chứa script `install_opencv_ubuntu_cmake.sh` vừa tải về. 
Di chuyển script `install_opencv_ubuntu_cmake.sh` vào thư mục bạn muốn cài đặt `OpenCV` sau này.

- Bước 3: Vào địa chỉ [opencv-unix](https://sourceforge.net/projects/opencvlibrary/files/opencv-unix/), 
tìm và chọn phiên bản mới nhất để lấy đường dẫn. Ví dụ: phiên bản hiện tại là `opencv-2.4.13`.

- Bước 4: Mở script `install_opencv_ubuntu_cmake.sh` tìm đến dòng `108 - 112`. Nội dung như bên dưới:

		echo "Downloading OpenCV"
		
		wget -O opencv-2.4.13.zip https://sourceforge.net/projects/opencvlibrary/files/opencv-unix/2.4.13/opencv-2.4.13.zip/download
		
		echo "Installing OpenCV"
		
		unzip opencv-2.4.13.zip
		
		cd opencv-2.4.13

- Bước 5: Thay `2.4.13` trong đoạn mã trên thành phiên bản mà bạn chọn cài đặt (có 5 chỗ cần thay thế). 
Lưu lại nội dung thay đổi.

- Bước 6: Mở cửa sổ Terminal và di chuyển đến thư mục chứa script `install_opencv_ubuntu_cmake.sh` 
thực hiện cài đặt theo các lệnh bên dưới

		$ sudo apt-get update
		
		$ chmod +x install_opencv_ubuntu_cmake.sh
		
		$ ./install_opencv_ubuntu_cmake.sh
		
	Đợi quá trình cài đặt hoàn thành, quá trình cài đặt sẽ tạo ra một thư mục `opencv`.
	
- Bước 7: Thực hiện một số test mẫu để thử nghiệm. Di chuyển đến thư mục `opencv` vừa được tạo ra 
và thực hiện theo các lệnh bên dưới. Trong thư mục `opencv` có thư mục `sample`.

		$ cd samples/python/
		
		$ ls
		
		camera.py	drawing.py	...
		
		$ python camera.py
		
		$ python drawing.py
		
	Để thoát khỏi chương trình đang thực hiện bởi script `.py` phía trên, nhấn `ESC`. 
	Nếu các lệnh trên không báo lỗi và hoạt động tốt thì `OpenCV` đã cài đặt thành công trên `Ubuntu`.
