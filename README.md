# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [07.nginxReverseProxy]
==============================================================

**Tham khảo**
- https://viblo.asia/p/cach-cau-hinh-nginx-thanh-reverse-proxy-aWj53jkQl6m
- https://bkhost.vn/blog/reverse-proxy-server-nginx/
- https://bizflycloud.vn/tin-tuc/huong-dan-cau-hinh-reverse-proxy-voi-nginx-moi-nhat-20210106164206408.htm
- https://2coffee.dev/bai-viet/cach-su-dung-nginx-lam-reverse-proxy-cho-server
- https://viblo.asia/p/cau-hinh-ssltls-voi-nginx-3kY4gxbxJAe
- http://lsa.tdchien.com/k8s/k8s-thiet-lap-2-public-services-su-dung-traefik-ingress-tren-1-kubernetes-cluster-dua-vao-request-domain-name/

**Ta sẽ triển khai nginx dưới dạng 1 Reverse Proxy:**<br/>
- https://nginx-server.test.local
<br/> => Routing traffic đến service Docker Container có tên: nginx-server, port 80
- https://angular-server.test.local
<br/> => Routing traffic đến service Docker Container có tên: angular-server, port 3100
<br/> User truy cập vào nginx container ở port 80, 443 (với SSL tự tạo)

**Yêu cầu**<br/>
Trên file /etc/hosts hoặc C:\Windows\system32\etc\hosts cần có alias đến các domain kể trên:
```shell
# For nginx Reverse Proxy
127.0.0.1 nginx-server.test.local
127.0.0.1 angular-server.test.local
```

**Triển khai toàn bộ dưới dạng Docker Compose**
- nginx-reverse-proxy
<br/> Mở cổng `80, 443` để giao tiếp với bên ngoài (User UI interaction)
- nginx-server   (Server thứ nhất) , cổng nội bộ: 80
- angular-server (Server thứ hai), cổng nội bộ: 3100
- Tạo các file SSL/TLS để thử nghiệm trên môi trường local và đặt trong folder `/nginx-certs`
- File config chính cho `nginx reverse proxy` nằm trong folder `/nginx-config`

**Kết quả thực thi**<br/>
```shell
docker-compose up
```
- Truy cập trực tiếp:
  - Server 01 (nginx hello-world): http://localhost:8070
  - Server 02 (angular server): http://localhost:8090
- Truy cập qua nginx reverse proxy:
  - Server 01: https://nginx-server.test.local
  - Server 02: https://angular-server.test.local
