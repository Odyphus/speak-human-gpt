# gpt,speak human!

**让 GPT 说人话，把复杂问题讲清楚。**

给 Codex 和 ChatGPT 的中文表达指令。简单问题直接答，复杂问题讲清楚为什么，保留读者理解和复核所需的技术细节。

[在 Codex 中使用](#codex-用完整提示词检查配置) · [在 ChatGPT 中使用](#chatgpt-粘贴自定义指令) · [看三个场景的对照示例](examples.md)

## 同一个问题，可以怎么讲？

**问：为什么加了缓存的数据有时还是旧的？**

> **常见写法**　缓存层与持久化层存在一致性窗口，因此读路径可能返回过期副本。
>
> **可以这样讲**　因为程序还在读缓存里保存的旧值。比如你把商品价格从 100 元改成 80 元，数据库已经更新了，但缓存里还是 100 元。如果读取时优先使用缓存，页面就会继续显示 100 元，直到这条缓存被清掉、被更新，或过期后重新从数据库读取。

“缓存一致性”这个术语可以保留。先让读者看见数据存在哪儿、程序读了哪一份，再用术语给这个问题命名。[更多对照](examples.md)

## 怎么用

### Codex 用完整提示词检查配置

打开 [完整提示词](prompt.md)（[纯文本](./prompt.md?raw=1)），复制到 Codex 的新对话。它会要求 Codex 先检查全局和当前项目的指令，找出要求过度简短或相互冲突的规则，再对实际生效的文件做必要修改。

**这份提示词会请求写入本机的指令文件。** 想先看看它会改什么，可以在末尾加一句「本轮只检查，给出拟修改内容，等我确认后再写入。」修改后，在目标项目中开一个新会话，检查模型是否读到了更新的规则。全局 `AGENTS.override.md` 和项目内更具体的指令都可能影响结果。[Codex 指令加载顺序](https://learn.chatgpt.com/docs/agent-configuration/agents-md#how-codex-discovers-guidance)

### ChatGPT 粘贴自定义指令

打开 [ChatGPT 自定义指令](chatgpt-custom-instructions.txt)，复制全文。在 ChatGPT 网页版或桌面版打开 **设置 → 个性化 → 自定义指令**，粘贴并开启自定义。已有自己的偏好时，把新内容合并进去即可。ChatGPT 和本地 Codex 的设置各自保存。[ChatGPT 自定义指令帮助](https://help.openai.com/en/articles/8096356-chatgpt-custom-instructions)

## 怎么判断有没有改善

找一个你以前读了两遍才懂的回复，在更新指令前后用同一个问题试一次。看三件事：能不能很快找到答案，能不能顺着理由读下去，判断成立的条件有没有交代。写法会随模型和上下文变化，本仓库的示例用于说明目标写法。

## 参考

OpenAI 的 GPT-6.2 指南建议迁移时重新审视笼统的简洁要求，GPT-6 指南给出了减少术语堆叠和套话的写法。本仓库把这些建议整理成可以直接复用的中文指令。[GPT-6.2 指南](https://developers.openai.com/api/docs/guides/latest-model#writing-style) · [GPT-6 指南](https://developers.openai.com/api/docs/guides/latest-model?model=gpt-6-astra#writing-style) · [GPT-6 系列使用指南](https://openai.com/index/practical-guide-building-gpt-6/)

遇到特别好读或特别费劲的一段回复，欢迎在 Issue 里贴去掉个人信息后的片段，再说说哪一句帮你读懂了，或者你从哪一句开始读不下去。
