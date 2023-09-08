![image](https://github.com/NoatToan/tech/assets/49062153/9f574bbe-b528-44f1-a96f-7d21507b7c16)https://developer.mozilla.org/en-US/docs/Web/CSS/:where



### Clear
![image](https://github.com/NoatToan/tech/assets/49062153/161bae8c-b823-4181-b33d-c6ec11ff0ae9)
Khi cả 2 thành phần A và thành phần B sử dụng float, chúng ta không thể sử dụng clear: left; hay clear: right; để ngăn chặn thành phần C chiếm vùng không gian còn trống, trong trường hợp này ta sử dụng thuộc tính clear: both; để ngăn chặn sự chiếm vùng của thành phần C.
Thuộc tính clear: both; có thể ngăn chặn sự chiếm vùng không gian cả khi chỉ có một thành phần sử dụng float (left hoặc right) hoặc nhiều thành phần sử dụng float.
Giả sử thành phần A và thành phần B đều sử dụng float:
```css
div {
    border: 1px solid red;
}

p.first {
    background: #f3f3cf;
    float: left;
    height: 100px;
}

p.second {
    background: #e0e0fc;
    float: right;
    height: 100px;
}

p.third {
    background: #befcc9;
    height: 100px;
}
```

## Hiển thị trình duyệt khi chưa sử dụng clear: both; cho "Thành phần C"

![image](https://github.com/NoatToan/tech/assets/49062153/e750e9d1-76a3-477c-8cfd-defa3e93de33)
```css
* {
    margin: 0;
    padding: 0;
}

div {
    border: 1px solid red;
}

p.first {
    background: #f3f3cf;
    float: left;
    height: 100px;
}

p.second {
    background: #e0e0fc;
    float: right;
    height: 100px;
}

p.third {
    background: #befcc9;
    clear: both;
    height: 100px;
}
![image](https://github.com/NoatToan/tech/assets/49062153/f58be8f8-81ff-4610-8ba4-eff3ab242190)

`
