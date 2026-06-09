# std::filesystem::path::~path(void)

- ea: `0x140008a28`
- end: `0x140008a2d`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x14000add4`
- `0x14000ade6`
- `0x14000ae52`
- `0x14000ae68`
- `0x14000ae7e`
- `0x14000ae90`
- `0x14000aebc`
- `0x14000aee8`
- `0x14000af1e`
- `0x14000af30`
- `0x14000af42`
- `0x14000af54`
- `0x14000b045`
- `0x14000b057`
- `0x14000b069`

## callees

- `0x1400087c4`

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
0x140008a28  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
