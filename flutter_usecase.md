Phần này để rõ hơn thì flutter nó có cơ chế sau, hơi giống vitural dom của react:
- Với flutter, bên trong widget nó sẽ có 1 element đi kèm.
- Trường hợp rerender giao diện, flutter nó sẽ cất đi những widget cũ vào 1 góc. Nếu dùng lại dc nó sẽ dùng
- Sau đó nó compare key + type widget để quyết định có tạo mới widget không hay dùng widget cũ.

Trong case này của mình, vì key mình đặt là index, và widget là type text giống nhau
Hơn nữa, khi mình xóa item trong [A,B,C,D] - mình xóa A => Lúc này mảng còn [B,C,D]
=> rõ ràng lúc này index của B đã được cập nhật từ 1 về 0 
=> key 0 vẫn còn trên giao diện, tiếp tục type widget vẫn là text. => Flutter nó lụm cái widget của A lúc này là Text(A.toString()) và key là 0 để vào chỗ của B.
