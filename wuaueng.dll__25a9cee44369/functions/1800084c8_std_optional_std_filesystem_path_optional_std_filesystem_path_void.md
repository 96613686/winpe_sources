# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x1800084c8`
- end: `0x1800084dc`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180016a88`
- `0x180016abe`
- `0x180016ad0`

## callees

- `0x1800084c8`
- `0x18000a98c`

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
0x1800084c8  sub     rsp, 28h
0x1800084cc  cmp     byte ptr [rcx+20h], 0
0x1800084d0  jz      short loc_1800084D7
0x1800084d2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800084d7  add     rsp, 28h
0x1800084db  retn
```
