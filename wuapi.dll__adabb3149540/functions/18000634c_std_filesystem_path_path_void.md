# std::filesystem::path::~path(void)

- ea: `0x18000634c`
- end: `0x180006351`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(std::filesystem::path *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180016823`
- `0x18001684f`
- `0x18001688d`
- `0x1800168a3`
- `0x1800168b9`
- `0x18001691b`
- `0x180016931`
- `0x180016959`
- `0x18001696b`
- `0x18001697d`
- `0x18001698f`
- `0x1800169a1`
- `0x1800169d7`
- `0x180016a0d`
- `0x180016a79`

## callees

- `0x1800085e8`

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
0x18000634c  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
