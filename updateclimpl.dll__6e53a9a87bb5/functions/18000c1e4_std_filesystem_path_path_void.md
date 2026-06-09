# std::filesystem::path::~path(void)

- ea: `0x18000c1e4`
- end: `0x18000c1e9`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64 this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800158c8`
- `0x1800158da`
- `0x180015910`

## callees

- `0x18000d3b4`

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
0x18000c1e4  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
