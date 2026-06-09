# std::filesystem::path::~path(void)

- ea: `0x180008c68`
- end: `0x180008c6d`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e61c`
- `0x18000e62e`
- `0x18000e69a`
- `0x18000e6b0`
- `0x18000e6c6`
- `0x18000e6d8`
- `0x18000e704`
- `0x18000e730`
- `0x18000e766`
- `0x18000e778`
- `0x18000e78a`
- `0x18000e79c`
- `0x18000e7ae`

## callees

- `0x180008b08`

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
0x180008c68  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
