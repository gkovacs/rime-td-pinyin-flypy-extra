# rime-td-pinyin-flypy-display

## About

This is a layout for typing in Shuangpin (双拼) with the Flypy (小鹤双拼) layout. Will display pronunciations in Cantonese as you type in Mandarin. You can also start typing in Cantonese by entering `\``. Tones can be entered as follows:

* Tone 1: `;`
* Tone 2: `/`
* Tone 3: `,`
* Tone 4: `.`

## Installing

First ensure you have plum installed. For macOS this would be:

```bash
cd ~/Library/Rime
wget https://git.io/rime-install
```

Then install `gkovacs/rime-td-pinyin-flypy-extra` using plum:

```bash
bash rime-install gkovacs/rime-double-jyutping gkovacs/rime-td-pinyin-flypy gkovacs/rime-double-jyutping-display gkovacs/rime-td-pinyin-flypy-display gkovacs/rime-td-pinyin-flypy-extra
```

Finally edit `default.custom.yaml` and add `td_pinyin_flypy_extra` to the schema list:

```bash
patch:
  schema_list:
    - schema: td_pinyin_flypy_extra
```

Now reload RIME and it should appear under your layouts.
