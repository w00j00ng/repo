

```python
# 변수 0으로 초기화
rate_posture, rate_concentrate = 0, 0
rate_angry, rate_disgust, rate_fear, rate_happy, rate_sad = 0, 0, 0, 0, 0

# 정면 얼굴이 검출된 횟수에서 전체 횟수를 나누어 자세를 평가
rate_posture = (report['eye_data'][0] + report['eye_data'][1]) / report['loop_count']
if (report['eye_data'][0] + report['eye_data'][1]) != 0:
    # 눈을 뜨고 있는 횟수에서 정면 얼굴이 검출된 횟수를 나누어 집중도를 평가
    rate_concentrate = report['eye_data'][1] / (report['eye_data'][0] + report['eye_data'][1])

# emotion이 측정된 횟수가 없는 경우 모든 감정을 0으로 평가
# 해당 감정이 측정된 횟수에서 전체 감정이 측정된 횟수를 나누어 감정의 정도를 평가
if report['emotion_data']['Total'] != 0:
    rate_angry = report['emotion_data']['Angry'] / report['emotion_data']['Total']
    rate_disgust = report['emotion_data']['Disgust'] / report['emotion_data']['Total']
    rate_fear = report['emotion_data']['Fear'] / report['emotion_data']['Total']
    rate_happy = report['emotion_data']['Happy'] / report['emotion_data']['Total']
    rate_sad = report['emotion_data']['Sad'] / report['emotion_data']['Total']
```

