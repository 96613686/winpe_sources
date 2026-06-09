# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x180002d50`
- end: `0x180002d64`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800160a9`
- `0x1800160df`
- `0x1800160f1`

## callees

- `0x180002d50`
- `0x1800078ac`

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
0x180002d50  sub     rsp, 28h
0x180002d54  cmp     byte ptr [rcx+20h], 0
0x180002d58  jz      short loc_180002D5F
0x180002d5a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002d5f  add     rsp, 28h
0x180002d63  retn
```
