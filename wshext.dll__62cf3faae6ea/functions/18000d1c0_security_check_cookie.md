# __security_check_cookie

- ea: `0x18000d1c0`
- end: `0x18000d1de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `44`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e20`
- `0x180001f40`
- `0x180002810`
- `0x1800028e0`
- `0x18000494c`
- `0x180004d28`
- `0x1800051a8`
- `0x180005980`
- `0x180006160`
- `0x180006440`
- `0x1800067c0`
- `0x180006b40`
- `0x1800072c4`
- `0x1800076a0`
- `0x180007860`
- `0x180007940`
- `0x180008c5c`
- `0x1800093c0`
- `0x180009cc8`
- `0x180009e90`
- `0x18000a038`
- `0x18000a270`
- `0x18000a55c`
- `0x18000a848`
- `0x18000aacc`
- `0x18000acd0`
- `0x18000aeb0`
- `0x18000b004`
- `0x18000b1c0`
- `0x18000b304`
- `0x18000b49c`
- `0x18000b574`
- `0x18000b6d0`
- `0x18000b924`
- `0x18000bbdc`
- `0x18000be68`
- `0x18000bfe0`
- `0x18000c05c`
- `0x18000c33c`
- `0x18000c480`
- `0x18000c594`
- `0x18000ca88`
- `0x18000cba0`
- `0x18000d088`

## callees

- `0x180003750`
- `0x18000d1c0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x18000d1c0  cmp     rcx, cs:__security_cookie
0x18000d1c7  jnz     short ReportFailure
0x18000d1c9  rol     rcx, 10h
0x18000d1cd  test    cx, 0FFFFh
0x18000d1d2  jnz     short RestoreRcx
0x18000d1d4  retn
0x18000d1d5  ror     rcx, 10h
0x18000d1d9  jmp     __report_gsfailure
```
