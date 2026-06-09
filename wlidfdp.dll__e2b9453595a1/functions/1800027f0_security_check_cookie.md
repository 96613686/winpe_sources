# __security_check_cookie

- ea: `0x1800027f0`
- end: `0x18000280e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010d4`
- `0x1800011a4`
- `0x180001458`
- `0x18000176c`
- `0x1800017fc`
- `0x1800018f8`
- `0x180001b9c`
- `0x180001e94`
- `0x180003944`
- `0x180003ae0`
- `0x180003e18`
- `0x180004bb8`
- `0x180004e4c`
- `0x1800059e8`
- `0x180005f40`
- `0x1800067d4`
- `0x18000727c`
- `0x18000912c`
- `0x1800097a0`
- `0x1800099a8`
- `0x180009a40`
- `0x18000c6cc`
- `0x18000cec8`
- `0x18000d6dc`
- `0x18000dc00`
- `0x18000de3c`
- `0x18000e1c0`
- `0x18000e500`
- `0x18000e8b8`
- `0x18000ee14`
- `0x18000fc28`
- `0x18000fcf8`
- `0x18001048c`

## callees

- `0x1800027f0`
- `0x180002c00`

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
0x1800027f0  cmp     rcx, cs:__security_cookie
0x1800027f7  jnz     short ReportFailure
0x1800027f9  rol     rcx, 10h
0x1800027fd  test    cx, 0FFFFh
0x180002802  jnz     short RestoreRcx
0x180002804  retn
0x180002805  ror     rcx, 10h; StackCookie
0x180002809  jmp     __report_gsfailure
```
