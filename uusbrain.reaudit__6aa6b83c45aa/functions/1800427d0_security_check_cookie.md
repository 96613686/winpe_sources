# __security_check_cookie

- ea: `0x1800427d0`
- end: `0x1800427ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `216`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000109c`
- `0x180001158`
- `0x18000140c`
- `0x180001704`
- `0x1800017b0`
- `0x1800018a4`
- `0x180004924`
- `0x180004aa8`
- `0x180004b14`
- `0x180005020`
- `0x180005a30`
- `0x1800064a0`
- `0x180006620`
- `0x180006fc0`
- `0x1800076f8`
- `0x180007820`
- `0x180007ad8`
- `0x180007ef8`
- `0x180008520`
- `0x18000868c`
- `0x180008770`
- `0x1800087f0`
- `0x1800089f4`
- `0x180008af0`
- `0x180008c48`
- `0x180008e30`
- `0x180008fc4`
- `0x180009180`
- `0x180009300`
- `0x1800094bc`
- `0x1800096d4`
- `0x1800097d8`
- `0x1800098c0`
- `0x180009938`
- `0x180009f40`
- `0x18000a2a8`
- `0x18000a4c8`
- `0x18000a5b0`
- `0x18000a748`
- `0x18000a8dc`
- `0x18000ab24`
- `0x18000b024`
- `0x18000b638`
- `0x18000b9d4`
- `0x18000bdc0`
- `0x18000bf10`
- `0x18000c510`
- `0x18000cf18`
- `0x18000d540`
- `0x18000d660`

## callees

- `0x1800427d0`
- `0x180043290`

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
0x1800427d0  cmp     rcx, cs:__security_cookie
0x1800427d7  jnz     short ReportFailure
0x1800427d9  rol     rcx, 10h
0x1800427dd  test    cx, 0FFFFh
0x1800427e2  jnz     short RestoreRcx
0x1800427e4  retn
0x1800427e5  ror     rcx, 10h
0x1800427e9  jmp     __report_gsfailure
```
