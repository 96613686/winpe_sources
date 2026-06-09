# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x140008830`
- end: `0x140008844`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000adf8`
- `0x14000aefa`
- `0x14000af0c`

## callees

- `0x1400087c4`
- `0x140008830`

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
0x140008830  sub     rsp, 28h
0x140008834  cmp     byte ptr [rcx+20h], 0
0x140008838  jz      short loc_14000883F
0x14000883a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000883f  add     rsp, 28h
0x140008843  retn
```
