<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SIYA - Stadium In Your Area</title>
    <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a8/Icons8_flat_sports_mode.svg/768px-Icons8_flat_sports_mode.svg.png" type="image/x-icon">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: white;
            margin: 0;
            padding: 0;
        }
        .navbar {
            background-color: #0d3c6e;
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 20px;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        .navbar-logo {
            display: flex;
            font-size: 28px;
            font-weight: bold;
            margin-right: auto;
            align-items: center;
        }
        .navbar-logo a {
            display: flex;                 /* Đảm bảo tất cả nội dung trong a là flexbox */
            text-decoration: none;         /* Bỏ gạch chân ở liên kết */
            color: inherit;                /* Kế thừa màu chữ từ phần tử cha */
        }
        .navbar-logo img {
            width: 50px;
            height: auto;
            margin-right: 2px;
        }
        .logo-text {
            display: flex;
            flex-direction: column;
            text-align: center; /* Căn giữa chữ SIYA và subtitle */
        }
        .subtitle {      
            font-size: 12px;    /* Kích thước chữ nhỏ */
            color: white;        /* Màu chữ (tùy chọn) */
        }
        .navbar-menu {
            display: flex;
            list-style-type: none;
        }
        .navbar-menu li {
            margin-right: 20px;
            position: relative;
        }
        .navbar-menu a {
            text-decoration: none;
            color: white;
            font-size: 16px;
            font-weight: bold;
        }


        .dropdown-content, .sub-dropdown-content {
            display: none;
            position: absolute;
            background-color: white;
            min-width: 160px;
            box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }
        .dropdown:hover .dropdown-content,
        .sub-dropdown:hover .sub-dropdown-content {
            display: block;
        }
        .dropdown-content a, .sub-dropdown-content a {
            color: #0d3c6e;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
        }
        .dropdown-content a:hover, .sub-dropdown-content a:hover {
            background-color: #ddd;
            color: orange;
        }
        .sub-dropdown {
            position: relative;
        }
        .sub-dropdown-content {
            left: 100%;
            top: 0;
            min-width: 200px;
        }


        .dropbtn {
            color: white;
            font-size: 16px;
            border: none;
            background-color: inherit;
        }




        .home-section {
            position: relative;
            min-height: 100vh;
            /* background: url('https://www.insidesport.in/wp-content/uploads/2022/06/Football-Ground.jpg') no-repeat center center/cover; */
            display: flex;
            justify-content: center;
            align-items: center;
            color: black;
            text-align: center;
            background-color: white;
        }
        .home-section::after {
            /* content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: white; */
            display: none;
        }
        .home-content {
            position: relative;
            z-index: 1;
        }
        .home-content img {
            width: 500px;    /* Đặt chiều rộng logo (bạn có thể thay đổi theo ý muốn) */
            height: auto;    /* Giữ nguyên tỷ lệ của logo */
            justify-content: center;
            margin-bottom: 20px; /* Tạo khoảng cách giữa logo và đoạn văn */
        }
        /* .home-content h1 {
            font-size: 48px;
            margin-bottom: 20px;
        } */
        .home-content p {
            font-size: 20px;
            max-width: 700px;
            margin: 0 auto;
            justify-content: center;
            line-height: 1.6;
        }


        .search-bar {
            position: absolute; /* Đặt vị trí tuyệt đối */
            top: 15%; /* Điều chỉnh vị trí top để đặt nó phía trên logo */
            width: 100%; /* Đặt chiều rộng 100% để căn giữa */
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .search-input {
            width: 300px;
            padding: 10px;
            border: 2px solid #0d3c6e;
            border-radius: 5px;
            font-size: 16px;
            background-color: #0d3c6e; /* Màu nền xanh đậm */
            color: white; /* Màu chữ trắng để tương phản với nền */
        }
        .search-input::placeholder {
            color: white; /* Đổi màu placeholder thành trắng */
            font-style: italic;
        }
        .search-button {
            padding: 10px 20px;
            background-color: #0d3c6e;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin-left: 5px;
        }
        .search-button:hover {
            background-color: #ff8c00;
        }
        /* .venue-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            margin: 20px;
        }
        .venue-card {
            width: 30%;
            margin: 15px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 8px;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .venue-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 8px;
        }
        .venue-card h3 {
            margin: 10px 0;
            color: #2c3e50;
        }
        .venue-info {
            text-align: left;
            margin-top: 10px;
            font-size: 14px;
        }
        .venue-info p {
            margin: 5px 0;
        }
        .venue-info span {
            font-weight: bold;
        } */
    </style>
</head>
<body>


<!-- Navbar -->
<div class="navbar">
    <div class="navbar-logo">
        <a href="index.html" style="text-decoration: none; color: inherit;">
            <img src="https://i.postimg.cc/xTCbQbcG/image-removebg-preview.png" alt="logo">
            <div class="logo-text">
                SIYA
                <span class="subtitle">Stadium in your area</span>
            </div>
        </a>
    </div>
    <ul class="navbar-menu">
        <li><a href="#">Về chúng tôi</a></li>
        <li class="dropdown">
            <a href="#" class="dropbtn">Sân theo khu vực</a>
            <div class="dropdown-content">
                <!-- TPHCM Dropdown -->
                <div class="sub-dropdown">
                    <a href="#">TPHCM</a>
                    <div class="sub-dropdown-content">
                        <a href="quan1.html" onclick="showDistrictVenues('quan1')">Quận 1</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan2')">Quận 2</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan3')">Quận 3</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan4')">Quận 4</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan5')">Quận 5</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan6')">Quận 6</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan7')">Quận 7</a>
                        <a href="quan8.html" onclick="showDistrictVenues('quan8')">Quận 8</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan9')">Quận 9</a>
                        <a href="quan10.html" onclick="showDistrictVenues('quan10')">Quận 10</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan11')">Quận 11</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quan12')">Quận 12</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quanBinhThanh')">Bình Thạnh</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quanBinhTan')">Bình Tân</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quanPhuNhuan')">Phú Nhuận</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quanTanBinh')">Tân Bình</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quanTanPhu')">Tân Phú</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('quanGoVap')">Gò Vấp</a>
                    </div>
                </div>
                <!-- Hà Nội Dropdown -->
                <div class="sub-dropdown">
                    <a href="#">Hà Nội</a>
                    <div class="sub-dropdown-content">
                        <a href="javascript:void(0)" onclick="showDistrictVenues('badinh')">Quận Ba Đình</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('hoankiem')">Quận Hoàn Kiếm</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('dongda')">Quận Đống Đa</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('caugiay')">Quận Cầu Giấy</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('tayho')">Quận Tây Hồ</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('haibatrung')">Quận Hai Bà Trưng</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('hoangmai')">Quận Hoàng Mai</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('longbien')">Quận Long Biên</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('thanhxuan')">Quận Thanh Xuân</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('namtuliem')">Quận Nam Từ Liêm</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('bactuliem')">Quận Bắc Từ Liêm</a>
                    </div>
                </div>
                <!-- TP Đà Nẵng Dropdown -->
                <div class="sub-dropdown">
                    <a href="#">TP Đà Nẵng</a>
                    <div class="sub-dropdown-content">
                        <a href="javascript:void(0)" onclick="showDistrictVenues('haichau')">Quận Hải Châu</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('thanhkhe')">Quận Thanh Khê</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('sontra')">Quận Sơn Trà</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('nguHanhSon')">Quận Ngũ Hành Sơn</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('camLe')">Quận Cẩm Lệ</a>
                        <a href="javascript:void(0)" onclick="showDistrictVenues('lienChieu')">Quận Liên Chiểu</a>
                    </div>
                </div>
            </div>
        </li>
        <li><a href="#">Dành cho chủ sân</a></li>
        <li><a href="login.html">Đăng ký thành viên</a></li>
        <li><a href="#">CSKH</a></li>
    </ul>
</div>






<!-- Home Section -->
<div class="home-section">
    <div class="search-bar">
        <input type="search" id="venue-search" class="search-input" placeholder="Nhập tên sân thể thao...">
        <button type="submit" class="search-button">Tìm kiếm</button>
    </div>
    <div class="home-content">
        <img src="https://i.postimg.cc/ryD1YLyn/SIYA.png" alt="home-logo">
        <p>"Sứ mệnh của chúng tôi là mang đến cho bạn trải nghiệm đặt sân thể thao một cách nhanh chóng và tiện lợi. Tại SIYA, chúng tôi cung cấp thông tin chi tiết về các sân gần bạn để bạn dễ dàng lựa chọn. Hãy tham gia cùng chúng tôi và tận hưởng những giây phút thể thao tuyệt vời nhất!"</p>
    </div>
</div>


</body>
</html>

