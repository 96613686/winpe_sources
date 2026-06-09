# std::filesystem::path::~path(void)

- ea: `0x1400089f8`
- end: `0x1400089fd`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000adb4`
- `0x14000adc6`
- `0x14000ae32`
- `0x14000ae48`
- `0x14000ae5e`
- `0x14000ae70`
- `0x14000ae9c`
- `0x14000aec8`
- `0x14000aefe`
- `0x14000af10`
- `0x14000af22`
- `0x14000af34`

## callees

- `0x1400087e4`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(char **this)
{
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x1400089f8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
