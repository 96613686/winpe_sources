# NCoreLibrary::GetLastErrorAsFailHR(void)

- ea: `0x1400112c8`
- end: `0x1400112ec`
- name: `?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ`
- size: `36`
- prototype: `__int64 __fastcall(NCoreLibrary *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ad0`
- `0x140007dac`
- `0x1400102d8`
- `0x140012c80`
- `0x140012fdc`
- `0x140013f74`

## callees

- `0x1400112c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400112cc`
- `KERNEL32!GetLastError` at `0x1400112cc`

## pseudocode

```c
signed int __fastcall NCoreLibrary::GetLastErrorAsFailHR(NCoreLibrary *this)
{
  signed int result; // eax

  result = GetLastError();
  if ( !result )
    return -2147467259;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400112c8  sub     rsp, 28h
0x1400112cc  call    cs:__imp_GetLastError
0x1400112d2  test    eax, eax
0x1400112d4  jnz     short loc_1400112DD
0x1400112d6  mov     eax, 80004005h
0x1400112db  jmp     short loc_1400112E7
0x1400112dd  jle     short loc_1400112E7
0x1400112df  movzx   eax, ax
0x1400112e2  or      eax, 80070000h
0x1400112e7  add     rsp, 28h
0x1400112eb  retn
```
