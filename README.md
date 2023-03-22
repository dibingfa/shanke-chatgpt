# shanke-chatgpt

- chatgpt 对话框：https://chat.openai.com/
- 国内体验版（超过次数限制需要付费）：http://chat.nqzyx.top/h5/10001
- 基于 GPT-4 的 IDE：https://www.cursor.so/
- 开源桌面客户端：https://github.com/Bin-Huang/chatbox

【开源模型】

- 清华发布的显卡级的模型：https://github.com/THUDM/ChatGLM-6B

【AI 绘图】

- openai 的：https://labs.openai.com/

【优质文章或视频】

- 一个较为深入的科普视频：https://b23.tv/vByqg4V

【聚合网站】
- AI 导航｜最新最前沿的 AI 产品：https://www.ainavpro.com/




一个最简单的访问 API 的 HTML 页面
```HTML
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>API 请求测试</title>
    <script>
        async function callAPI() {
            const apiKey = '你的API密钥'; // 请将这里替换为您的实际API密钥
            const url = 'https://api.openai.com/v1/chat/completions';
	    const inputText = document.getElementById('inputText').value;
            const requestData = {
                model: 'gpt-3.5-turbo',
                messages: [{"role": "user", "content": inputText}],
                temperature: 0.7
            };

            const response = await fetch(url, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'Authorization': `Bearer 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`
                },
                body: JSON.stringify(requestData)
            });

            if (response.ok) {
                const jsonResponse = await response.json();
                const result = jsonResponse.choices[0].message.content;
		console.log(jsonResponse.choices[0].message.content);
                document.getElementById('result').innerText = result;
            } else {
                document.getElementById('result').innerText = '请求失败';
            }
        }
    </script>
</head>
<body>
    <h1>ChatGPT API 请求测试</h1>
    <p>输入文本：</p>
    <textarea width:100px height:100px id="inputText"></textarea>
    <p/>
    <button onclick="callAPI()">发送请求</button>
    <p>返回结果:</p>
    <div id="result" style="border: 1px solid black; padding: 10px;"></div>
</body>
</html>
```
