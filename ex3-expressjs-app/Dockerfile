# Sử dụng image Node.js chính thức
FROM node:23.4-alpine3.21

# Đặt thư mục làm việc trong container
WORKDIR /app

# Sao chép package.json và package-lock.json (nếu có) vào container
COPY package*.json ./

# Cài đặt các dependencies
RUN npm install

# Sao chép toàn bộ mã nguồn vào container
COPY . .

# Expose port 3000 để ứng dụng có thể được truy cập ngoài container
EXPOSE 3000

# Chạy ứng dụng khi container khởi động
CMD ["npm", "start"]
