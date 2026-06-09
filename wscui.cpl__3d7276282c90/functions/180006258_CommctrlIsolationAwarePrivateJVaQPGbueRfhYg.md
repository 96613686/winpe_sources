# CommctrlIsolationAwarePrivateJVaQPGbueRfhYg

- ea: `0x180006258`
- end: `0x18000627c`
- name: `CommctrlIsolationAwarePrivateJVaQPGbueRfhYg`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006340`
- `0x180007bc8`

## callees

- `0x180006258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000625c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000625c`

## pseudocode

```c
signed int CommctrlIsolationAwarePrivateJVaQPGbueRfhYg()
{
  signed int result; // eax

  result = GetLastError();
  if ( result )
  {
    if ( result <= 0 )
      return result;
  }
  else
  {
    LOWORD(result) = 1359;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x180006258  sub     rsp, 28h
0x18000625c  call    cs:__imp_GetLastError
0x180006262  test    eax, eax
0x180006264  jnz     short loc_18000626D
0x180006266  mov     eax, 54Fh
0x18000626b  jmp     short loc_18000626F
0x18000626d  jle     short loc_180006277
0x18000626f  movzx   eax, ax
0x180006272  or      eax, 80070000h
0x180006277  add     rsp, 28h
0x18000627b  retn
```
