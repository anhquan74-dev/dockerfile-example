# Sử dụng image chính thức của Nginx để phục vụ file static
FROM nginx:alpine

# Copy file index.html từ thư mục hiện tại vào thư mục mặc định của nginx
COPY index.html /usr/share/nginx/html/index.html

# Expose cổng 80 để truy cập trang web
EXPOSE 80

# Khởi chạy nginx
CMD ["nginx", "-g", "daemon off;"]
