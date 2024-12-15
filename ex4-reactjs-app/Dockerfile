# Bước 1: Sử dụng image Node.js chính thức để build ứng dụng
FROM node:22.12-alpine3.21 AS build

# Đặt thư mục làm việc trong container
WORKDIR /app

# Sao chép package.json và package-lock.json vào container
COPY package*.json ./

# Cài đặt các dependencies cần thiết
RUN npm install

# Sao chép toàn bộ mã nguồn vào container
COPY . .

# Build ứng dụng React
RUN npm run build

# Bước 2: Sử dụng image Nginx để phục vụ ứng dụng đã build
FROM nginx:alpine

# Sao chép các tệp đã build từ bước trước vào thư mục của Nginx
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 để ứng dụng có thể truy cập
EXPOSE 80

# Chạy Nginx
CMD ["nginx", "-g", "daemon off;"]
