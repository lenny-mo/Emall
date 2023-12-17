# Emall

## 介绍





## 1 架构图

![emall架构图.png](https://raw.githubusercontent.com/lenny-mo/PictureUploadFolder/main/emall%E6%9E%B6%E6%9E%84%E5%9B%BE.png)

## 2 具体的功能模块

### 2.1 网关层代码

[gin路由层](https://github.com/lenny-mo/emall-router)


### 2.2 API层代码

[orderAPI层](https://github.com/lenny-mo/order-api)

[cartAPI层](https://github.com/lenny-mo/cart-api)

[paymentAPI层](https://github.com/lenny-mo/payment-api)


### 2.3 领域层代码

[order微服务](https://github.com/lenny-mo/order)

[cart微服务](https://github.com/lenny-mo/cart)

[payment微服务](https://github.com/lenny-mo/payment)



## 3 采用的技术点

### 3.1 乐观锁 + google UUID 保证下单幂等性
代码位置：UpdateOrder
https://github.com/lenny-mo/order/blob/main/domain/dao/order.go#L42



### 3.2  timer 和 waitGroup 定时查询支付状况
代码位置：CreatePaymentRecord
https://github.com/lenny-mo/payment/blob/main/domain/services/payment.go#L55


### 3.3 缓存双删 解决数据更新时的数据库缓存一致性
代码位置：UpdatePaymentRecord 
https://github.com/lenny-mo/payment/blob/main/domain/services/payment.go#L148



### 