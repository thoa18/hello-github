# hello-github
This repository is for practicing the GitHub Flow.
import re

def is_strong_password(password):
    """
    Kiểm tra xem mật khẩu có đủ mạnh không.
    Yêu cầu:
    - Ít nhất 8 ký tự
    - Chứa ít nhất một chữ cái viết hoa
    - Chứa ít nhất một chữ cái viết thường
    - Chứa ít nhất một chữ số
    - Chứa ít nhất một ký tự đặc biệt
    """
    if len(password) < 8:
        return False
    if not re.search(r"[A-Z]", password):
        return False
    if not re.search(r"[a-z]", password):
        return False
    if not re.search(r"\d", password):
        return False
    if not re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        return False
    return True

# Kiểm tra với một số mật khẩu
passwords = ["Hello123!", "weakpass", "StrongP@ss1", "NoSpecialChar123"]
for pwd in passwords:
    print(f"Password '{pwd}' is strong: {is_strong_password(pwd)}")
