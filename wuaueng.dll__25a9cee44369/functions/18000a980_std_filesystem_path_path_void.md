# std::filesystem::path::~path(void)

- ea: `0x18000a980`
- end: `0x18000a985`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64 this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1800167f7`
- `0x180016962`
- `0x180016978`
- `0x18001698e`
- `0x1800169b2`
- `0x1800169c8`
- `0x1800169f0`
- `0x180016a02`
- `0x180016a14`
- `0x180016a64`
- `0x180016a76`
- `0x180016aac`
- `0x180016ae2`
- `0x180016b0e`
- `0x180016b66`

## callees

- `0x18000a98c`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(__int64 this)
{
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x18000a980  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
