# Chatgpt-on-termux

![](https://raw.githubusercontent.com/atamshkai/Chatgpt-on-termux/main/Screenshot_2023-06-22-00-52-39-625_com.termux.jpg)

### First,we need to get our own api key from our account

### Generate Your Own OPENAI_Key From Here.

https://platform.openai.com/account/api-keys

## Installation

```

pkg update -y && pkg install python -y && pip install openai

```

## Change your openai api key in line 4 and paste it to termux
 
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
