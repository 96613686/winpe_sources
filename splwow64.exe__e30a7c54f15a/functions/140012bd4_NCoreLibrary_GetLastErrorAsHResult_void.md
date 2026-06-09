# NCoreLibrary::GetLastErrorAsHResult(void)

- ea: `0x140012bd4`
- end: `0x140012bef`
- name: `?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ`
- size: `27`
- prototype: `__int64 __fastcall(NCoreLibrary *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14001293c`
- `0x140012a9c`
- `0x140012bf8`
- `0x140012fdc`
- `0x1400139b0`
- `0x140013b24`

## callees

- `0x140012bd4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012bd8`
- `KERNEL32!GetLastError` at `0x140012bd8`

## pseudocode

```c
signed int __fastcall NCoreLibrary::GetLastErrorAsHResult(NCoreLibrary *this)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140012bd4  sub     rsp, 28h
0x140012bd8  call    cs:__imp_GetLastError
0x140012bde  test    eax, eax
0x140012be0  jle     short loc_140012BEA
0x140012be2  movzx   eax, ax
0x140012be5  or      eax, 80070000h
0x140012bea  add     rsp, 28h
0x140012bee  retn
```
