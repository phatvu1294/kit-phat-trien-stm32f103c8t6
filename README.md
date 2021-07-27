# KIT Phát Triển STM32F103C8T6
*KIT Phát Triển STM32F103C8T6 được vẽ trên Altium Designer*

### Giới thiệu
KIT phát triển trên lõi ARM Cortex-M3 STM32F103C8T6, hỗ trợ JTAG, SWD. Trên mạch được tích hợp sẵn chip USB to Serial CH340G cho phép nạp/debug thông qua USART1 hoặc USART2.

### Tính năng:
- KIT được xây dựng dựa trên vi điều khiển STM32F103C8T6 (ARM Cortex-M3) lõi 32-bit, chạy với tần số max lên đến 72MHz.
- Hỗ trợ cổng nạp SWD/JTAG tương thích với các mạch nạp ST-LINK, JLINK, ...
- Mạch được tích hợp sẵn IC giao tiếp UART, cho phép debug hoặc nạp chương trình dễ dàng qua Serial
- Có thể sử dụng Arduino IDE để lập trình và nạp chương trình trực tiếp mà không cần thêm bất cứ mạch nạp nào
- Sử dụng với các IDE thông dụng như KeilC, STM32CubeIDE, ..., bên cạnh đó còn hỗ trợ sử dụng với Arduino IDE
  
### Hướng dẫn nạp chương trình với Arduino IDE:
- Cài đặt core stm32duino theo đường dẫn sau: https://github.com/stm32duino/Arduino_Core_STM32
- Sử dụng dây MiniUSB kết nối với cổng UART Debug, chuyển 2 jump chốt sang UART1 Select, sau đó cắm vào máy tính
- Tiếp theo, chuyển jump chốt BOOT0 sang mức 1, bấm RESET để chuyển chế độ BOOT thông qua Serial
- Build chương trình, sau đó chọn các thông số như trong hình vẽ thứ 4 của sản phẩm
- Bấm nạp chương trình để hoàn tất

*Lưu ý: Sau khi nạp xong, chương trình sẽ được nạp vào Flash và hoạt động, tuy nhiên BOOT0 vẫn ở mức 1, nếu RESET chương trình sẽ lại vào chế độ BOOT thông qua Serial. Do đó chúng ta cần chuyển BOOT0 xuống mức 0 để chương trình chạy trực tiếp từ Flash*
