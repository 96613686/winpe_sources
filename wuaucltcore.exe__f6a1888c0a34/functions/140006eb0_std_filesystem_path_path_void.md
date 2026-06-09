# std::filesystem::path::~path(void)

- ea: `0x140006eb0`
- end: `0x140006eb5`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(std::filesystem::path *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140021539`
- `0x140021565`
- `0x140021591`
- `0x1400215a3`
- `0x1400215b5`
- `0x1400215d9`
- `0x1400215eb`
- `0x140021657`

## callees

- `0x140009214`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(std::filesystem::path *this)
{
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x140006eb0  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
