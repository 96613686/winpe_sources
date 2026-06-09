# ERROR_HR_FROM_WIN32(ulong)

- ea: `0x180003fe4`
- end: `0x180003ffe`
- name: `?ERROR_HR_FROM_WIN32@@YAJK@Z`
- size: `26`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x180004260`
- `0x1800045cc`
- `0x180005fec`
- `0x180006340`
- `0x180006990`
- `0x180006ee0`
- `0x1800078a0`
- `0x180008b90`
- `0x180008dfc`
- `0x18000a32c`
- `0x18000ad10`
- `0x18000b1b4`
- `0x18000b5dc`
- `0x18000b82c`
- `0x18000cbc8`
- `0x18000daa0`
- `0x18000ee6c`
- `0x18000f834`
- `0x18000fb24`
- `0x18000fc94`
- `0x1800105c8`
- `0x180010938`
- `0x1800111c0`
- `0x1800115c4`
- `0x1800118a8`
- `0x180011af0`
- `0x180011fa8`
- `0x18001275c`
- `0x18001326c`
- `0x18001405c`
- `0x18001439c`
- `0x1800144b4`
- `0x180014740`

## callees

- `0x180003fe4`

## pseudocode

```c
__int64 __fastcall ERROR_HR_FROM_WIN32(signed int a1)
{
  if ( a1 > 0 )
    a1 = (unsigned __int16)a1 | 0x80070000;
  if ( a1 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180003fe4  test    ecx, ecx
0x180003fe6  jle     short loc_180003FF1
0x180003fe8  movzx   ecx, cx
0x180003feb  or      ecx, 80070000h
0x180003ff1  mov     eax, 80004005h
0x180003ff6  test    ecx, ecx
0x180003ff8  cmovns  ecx, eax
0x180003ffb  mov     eax, ecx
0x180003ffd  retn
```
