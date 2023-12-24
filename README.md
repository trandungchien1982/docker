# docker
Series về build docker image/docker-compose/tuỳ biến Docker Images ...

# Ví dụ [08.ViewLogsMultiContainers]
==============================================================

**Tham khảo**
- https://github.com/trandungchien1982/docker/tree/07.nginxReverseProxy

**Theo dõi Logs của các containers thuộc cùng 1 Group trong Docker-Compose:**<br/>
- Các services nằm trong `docker-compose.yml` thuộc cùng 1 folder
- Khi xem trên [Docker Desktop] (`Mac OS` hoặc `Windows`) thì các services này được gom nhóm lại.<br/>
  (tên của nhóm thường là tên của folder)

**Ví dụ**<br/>
- Folder có tên `smile`
- Các container được thiết lập chung 1 network để có thể hiểu nhau thông qua ServiceName
- Khi xem từng container thì ta sẽ thấy logs của riêng nó
- Khi xem nhóm `smile` thì ta sẽ thấy logs của tất cả service liên quan
