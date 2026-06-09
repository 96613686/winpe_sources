# __security_check_cookie

- ea: `0x18001b420`
- end: `0x18001b43e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `81`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000207c`
- `0x1800021cc`
- `0x180002658`
- `0x180002960`
- `0x180002b10`
- `0x180003260`
- `0x1800035dc`
- `0x180004104`
- `0x1800041ec`
- `0x180004540`
- `0x1800045f8`
- `0x1800059e0`
- `0x180005ce0`
- `0x180005e50`
- `0x180005fa0`
- `0x1800061d0`
- `0x180006688`
- `0x180006b50`
- `0x180007870`
- `0x1800079e0`
- `0x180007d44`
- `0x180008288`
- `0x180008408`
- `0x180009124`
- `0x1800094a8`
- `0x1800096c0`
- `0x180009d18`
- `0x18000a460`
- `0x18000a704`
- `0x18000a87c`
- `0x18000a908`
- `0x18000ab8c`
- `0x18000ace8`
- `0x18000b410`
- `0x18000b4f8`
- `0x18000b668`
- `0x18000bc10`
- `0x18000be1c`
- `0x18000c760`
- `0x18000c8b0`
- `0x18000ca10`
- `0x18000cdf0`
- `0x18000ce98`
- `0x18000d880`
- `0x18000db28`
- `0x18000dd70`
- `0x18000e224`
- `0x18000e6d4`
- `0x18000eb40`
- `0x18000ecb8`

## callees

- `0x180001a90`
- `0x18001b420`

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
0x18001b420  cmp     rcx, cs:__security_cookie
0x18001b427  jnz     short ReportFailure
0x18001b429  rol     rcx, 10h
0x18001b42d  test    cx, 0FFFFh
0x18001b432  jnz     short RestoreRcx
0x18001b434  retn
0x18001b435  ror     rcx, 10h
0x18001b439  jmp     __report_gsfailure
```
