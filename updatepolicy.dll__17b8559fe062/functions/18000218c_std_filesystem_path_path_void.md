# std::filesystem::path::~path(void)

- ea: `0x18000218c`
- end: `0x180002191`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64 this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180015f19`
- `0x180015f45`
- `0x180015f83`
- `0x180015f99`
- `0x180015faf`
- `0x180016011`
- `0x180016027`
- `0x18001604f`
- `0x180016061`
- `0x180016073`
- `0x180016085`
- `0x180016097`
- `0x1800160cd`
- `0x180016103`
- `0x18001616f`

## callees

- `0x1800078ac`

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
0x18000218c  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
