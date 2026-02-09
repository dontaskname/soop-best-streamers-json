# SOOP Best Streamers Data

SOOP(숲, 구 아프리카TV) 베스트 스트리머 목록을 매달 업데이트합니다.

## 📥 데이터 사용

### version.json (가벼운 버전 체크용)

```
https://raw.githubusercontent.com/dontaskname/soop-best-streamers-json/main/version.json
```

약 200 bytes. 데이터 버전과 메타정보만 포함.

```json
{
  "version": "46cfdc7758904713",
  "last_updated": "2026-02-10T01:01:10.110386",
  "total_count": 8958
}
```

### data.json (전체 데이터)

```
https://raw.githubusercontent.com/dontaskname/soop-best-streamers-json/main/data.json
```

약 100-200 KB. 전체 스트리머 목록 포함.

```json
{
  "version": "46cfdc7758904713",
  "last_updated": "2026-02-10T01:01:10.110386",
  "total_count": 8958,
  "streamers": ["ebwlgml", "yerin302", ...]
}
```

## 💡 사용 예제

### Python

```python
import requests

BASE = "https://raw.githubusercontent.com/dontaskname/soop-best-streamers-json/main"

# 버전 체크 (200 bytes)
version = requests.get(f"{BASE}/version.json").json()
print(f"버전: {version['version']}, 총 {version['total_count']}명")

# 필요시 데이터 다운로드
if need_update(version):
    data = requests.get(f"{BASE}/data.json").json()
    streamers = data['streamers']
```

### JavaScript

```javascript
const BASE = "https://raw.githubusercontent.com/dontaskname/soop-best-streamers-json/main";

const version = await fetch(`${BASE}/version.json`).then(r => r.json());
console.log(`버전: ${version.version}, 총 ${version.total_count}명`);

if (needUpdate(version)) {
  const data = await fetch(`${BASE}/data.json`).then(r => r.json());
  const streamers = data.streamers;
}
```

## 🔄 업데이트 주기

매달 수동으로 업데이트됩니다.

마지막 업데이트: **2026-02-10**

## 📊 통계

- 총 스트리머 수: **8,958명**
- 데이터 크기: ~200 KB
- 버전 파일 크기: ~200 bytes

## 📜 라이선스

MIT License - 자유롭게 사용하세요!
