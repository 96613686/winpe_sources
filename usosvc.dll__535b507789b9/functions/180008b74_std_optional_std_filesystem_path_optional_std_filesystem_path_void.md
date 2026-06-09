# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x180008b74`
- end: `0x180008b88`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e640`
- `0x18000e742`
- `0x18000e754`

## callees

- `0x180008b08`
- `0x180008b74`

## pseudocode

```c
__int64 __fastcall std::optional<std::filesystem::path>::~optional<std::filesystem::path>(__int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
    return std::wstring::~wstring((char **)a1);
  return result;
}

```

## disassembly

```asm
0x180008b74  sub     rsp, 28h
0x180008b78  cmp     byte ptr [rcx+20h], 0
0x180008b7c  jz      short loc_180008B83
0x180008b7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008b83  add     rsp, 28h
0x180008b87  retn
```
