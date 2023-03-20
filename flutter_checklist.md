
## UX
- [ ] Show loading khi đang request API

## Validation
- [ ] Đã trim content
- [ ] Dùng validator của text form field để validate
- [ ] Dùng validate message theo template của dự án

## Conventions
- [ ] Các VM/view giao tiếp với nhau bằng cách truyền id cho nhau. Không dùng data bằng cách attach VM vào.
- [ ] Không object data/ class data để khởi tạo view, VM. Chỉ dùng class chuyên dụng cho việc giao tiếp giữa các view/vm


## UX
- [ ] Đã extend view từ GetView để show loading theo action loadmore/reload
- [ ] Khi reload screen thì data chỉ replace chứ không bị clear đi

## Model
- [ ] Các attribute cần tính toán của model đã define bằng get trong model class

## Abstract
- [ ] Các model từ response đã dùng từ base model
- [ ] Tái sử dụng common logic code (paginate, request, response)

## Project structure:
- [ ] Các response/request đặc biệt đã đặt vào models của feature

## Others Convention:
- [ ] Constant của model đã define vào enum + extension

