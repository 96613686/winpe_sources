# __security_check_cookie

- ea: `0x180006cf0`
- end: `0x180006d0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001110`
- `0x180001450`
- `0x180001e00`
- `0x180002d40`
- `0x180003310`
- `0x180004020`
- `0x180004390`
- `0x180004a60`
- `0x180004e60`
- `0x180005170`
- `0x180005a90`
- `0x180005eb0`
- `0x180006030`
- `0x1800066f0`
- `0x180006834`
- `0x180006bdc`

## callees

- `0x180006400`
- `0x180006cf0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180006cf0  cmp     rcx, cs:__security_cookie
0x180006cf7  jnz     short loc_180006D09
0x180006cf9  rol     rcx, 10h
0x180006cfd  test    cx, 0FFFFh
0x180006d02  jnz     short loc_180006D05
0x180006d04  retn
0x180006d05  ror     rcx, 10h
0x180006d09  jmp     __report_gsfailure
```
