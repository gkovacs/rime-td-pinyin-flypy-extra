# rime-td-pinyin-flypy

## About

This is a layout for typing in Shuangpin (双拼) with the Flypy (小鹤双拼) layout. Tones can be entered as follows:

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

Then install `gkovacs/rime-td-pinyin-flypy` using plum:

```bash
bash rime-install gkovacs/rime-td-pinyin-flypy
```

Finally edit `default.custom.yaml` and add `td_pinyin_flypy` to the schema list:

```bash
patch:
  schema_list:
    - schema: international
```

Now reload RIME and it should appear under your layouts.

Note that if Tone 4 is not working for you, please ensure you define `key_binder/bindings` in `default.custom.yaml`, like the following:

```yaml
patch:
  schema_list:
    - schema: td_pinyin_flypy
  "menu/page_size": 9
  ascii_composer/switch_key:
    Shift_L: noop
    Shift_R: noop
  key_binder:
    bindings:
      - {accept: "Control+p", send: Up, when: composing}
      - {accept: "Control+n", send: Down, when: composing}
      - {accept: "Control+b", send: Left, when: composing}
      - {accept: "Control+f", send: Right, when: composing}
      - {accept: "Control+a", send: Home, when: composing}
      - {accept: "Control+e", send: End, when: composing}
      - {accept: "Control+d", send: Delete, when: composing}
      - {accept: "Control+k", send: "Shift+Delete", when: composing}
      - {accept: "Control+h", send: BackSpace, when: composing}
      - {accept: "Control+g", send: Escape, when: composing}
      - {accept: "Control+bracketleft", send: Escape, when: composing}
      - {accept: "Alt+v", send: Page_Up, when: composing}
      - {accept: "Control+v", send: Page_Down, when: composing}
      - {accept: ISO_Left_Tab, send: Page_Up, when: composing}
      - {accept: "Shift+Tab", send: Page_Up, when: composing}
      - {accept: Tab, send: Page_Down, when: composing}
      - {accept: minus, send: Page_Up, when: has_menu}
      - {accept: equal, send: Page_Down, when: has_menu}
      - {accept: "Control+Shift+1", select: .next, when: always}
      - {accept: "Control+Shift+2", toggle: ascii_mode, when: always}
      - {accept: "Control+Shift+3", toggle: full_shape, when: always}
      - {accept: "Control+Shift+4", toggle: simplification, when: always}
      - {accept: "Control+Shift+5", toggle: extended_charset, when: always}
      - {accept: "Control+Shift+exclam", select: .next, when: always}
      - {accept: "Control+Shift+at", toggle: ascii_mode, when: always}
      - {accept: "Control+Shift+numbersign", toggle: full_shape, when: always}
      - {accept: "Control+Shift+dollar", toggle: simplification, when: always}
      - {accept: "Control+Shift+percent", toggle: extended_charset, when: always}
      - {accept: "Control+period", toggle: ascii_punct, when: always}
      - {accept: "Control+Shift+a", toggle: ascii_mode, when: always}
      - {accept: "Control+Shift+A", toggle: ascii_mode, when: always}
      - {accept: "Control+Shift+z", toggle: .next, when: always}
      - {accept: "Control+Shift+Z", toggle: .next, when: always}
      - {accept: "Shift+space", toggle: noop, when: always} #取消全半角切换
```
