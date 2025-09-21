# Proof of Impact - Smart Contract Testing

## 🚀 Tại sao không thấy nút "Run"?

Trong VS Code, nút "Run" chỉ xuất hiện khi:
1. **File có thể chạy trực tiếp** (như Python, JavaScript với Node.js)
2. **Có cấu hình launch.json** cho debugging
3. **File có main function hoặc entry point rõ ràng**

Với Solidity contracts, bạn cần sử dụng **Hardhat** để test và deploy.

## 🛠️ Cài đặt Dependencies

```bash
npm install
```

## 🧪 Chạy Tests

### 1. Compile Contracts
```bash
npm run compile
```

### 2. Chạy Unit Tests
```bash
npm test
```

### 3. Chạy Local Blockchain
```bash
npm run node
```

### 4. Deploy và Test Contract
```bash
npm run deploy
```

## 📊 Test Cases

### Impact Score Calculation
- **Test case chính**: baseline=0, target=100, current=50, alpha=2
- **Expected**: Score ≈ 0.75
- **Formula**: fi = 1 - (1-x)^α, where x = (current-baseline)/(target-baseline)

### Các Test Cases khác:
- Multiple KPIs với weights khác nhau
- Edge cases (current = baseline, current = target)
- Overflow protection
- Access control
- Staking và data submission

## 🔧 Cấu trúc Dự án

```
├── smart-contract/
│   └── ProofOfImpact.sol    # Smart contract chính
├── test/
│   └── ProofOfImpact.test.js # Unit tests
├── scripts/
│   └── deploy.js            # Script deploy
├── hardhat.config.js        # Cấu hình Hardhat
└── package.json             # Dependencies
```

## 🎯 Kết quả Expected

Khi chạy test case chính:
```
Impact Score: 0.75
Expected: ~0.75 for KPI 1 (baseline=0, target=100, current=50, alpha=2)
```

## 💡 Tips

1. **Luôn chạy `npm install` trước**
2. **Sử dụng `npm test` thay vì tìm nút Run**
3. **Kiểm tra console.log output để debug**
4. **Sử dụng Hardhat console để tương tác với contract**

## 🚨 Troubleshooting

Nếu gặp lỗi:
1. Kiểm tra Node.js version (cần v16+)
2. Xóa thư mục `node_modules` và chạy `npm install` lại
3. Kiểm tra Solidity version compatibility
4. Đảm bảo đã cài đặt Hardhat globally: `npm install -g hardhat`
