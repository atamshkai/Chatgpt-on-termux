## Chatgpt-on-termux

### Generate Your Own OPENAI_Key From Here And Change It.

https://platform.openai.com/account/api-keys

## Installation

```

pkg update -y && pkg install python -y && pip install openai

```

## Add your openai api key in line 4
 
```

cat <<EOF > ~/chatgpt.py
import openai
import os
os.environ['OPENAI_Key']="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"
openai.api_key=os.environ['OPENAI_Key']
keep_prompting=True
while keep_prompting:
    prompt=input('chatgpt -> ')
    if prompt=='exit':
        keep_prompting=False
    else:
        response=openai.Completion.create(engine='text-davinci-003',prompt=prompt,max_tokens=200)
        print(response['choices'][0]['text'])
EOF

```

## Add chatgpt to ~/../usr/bin

```
echo "python ~/chatgpt.py" >>~/../usr/bin/chatgpt
 
chmod +x ~/../usr/bin/chatgpt
 
chatgpt

```

## Watch Video Here

https://youtu.be/PzrC_9655u4
