# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x180006f10`
- end: `0x180006f24`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800169b3`
- `0x1800169e9`
- `0x1800169fb`

## callees

- `0x180006f10`
- `0x1800085e8`

## pseudocode

```c
__int64 __fastcall std::optional<std::filesystem::path>::~optional<std::filesystem::path>(__int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
    return std::wstring::~wstring(a1);
  return result;
}

```

## disassembly

```asm
0x180006f10  sub     rsp, 28h
0x180006f14  cmp     byte ptr [rcx+20h], 0
0x180006f18  jz      short loc_180006F1F
0x180006f1a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006f1f  add     rsp, 28h
0x180006f23  retn
```
