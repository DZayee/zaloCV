# zaloCV
import requests

def send_zalo_message(user_id, message):
    access_token = 'your_access_token'
    headers = {
        'Content-Type': 'application/json',
        'access_token': access_token
    }
    data = {
        "recipient": {
            "user_id": user_id
        },
        "message": {
            "text": message
        }
    }
    response = requests.post('https://openapi.zalo.me/v2.0/oa/message', headers=headers, json=data)
    return response.json()

# Gửi tin nhắn nhắc nhở công việc
send_zalo_message('user_id', 'Bạn có một công việc cần hoàn thành vào 5 giờ chiều hôm nay.')
