# __security_check_cookie

- ea: `0x14001b960`
- end: `0x14001b97e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `72`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006584`
- `0x140006a90`
- `0x1400094ac`
- `0x140009b1c`
- `0x14000af00`
- `0x14000b020`
- `0x14000b130`
- `0x14000b2d0`
- `0x14000cb30`
- `0x14000cce0`
- `0x14000d4e0`
- `0x14000d5d0`
- `0x14000d730`
- `0x14000d910`
- `0x140019028`
- `0x140019174`
- `0x1400192c0`
- `0x140019dc4`
- `0x140019ed8`
- `0x140019fec`
- `0x14001a554`
- `0x14001a9f0`
- `0x14001ae08`
- `0x14001b3c4`
- `0x14001b81c`
- `0x140029294`
- `0x14002de54`
- `0x14002e230`
- `0x14002eb3c`
- `0x14002f1e4`
- `0x140030a04`
- `0x1400316d4`
- `0x14003261c`
- `0x140034000`
- `0x1400349e0`
- `0x140034c20`
- `0x140035544`
- `0x1400358f4`
- `0x140037c44`
- `0x140037de8`
- `0x14003a0bc`
- `0x14003a7b0`
- `0x14003c4b4`
- `0x14003cb18`
- `0x14003d6c0`
- `0x14004012c`
- `0x1400401cc`
- `0x1400402dc`
- `0x140040de4`
- `0x140041bb8`

## callees

- `0x140008c40`
- `0x14001b960`

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
0x14001b960  cmp     rcx, cs:__security_cookie
0x14001b967  jnz     short ReportFailure
0x14001b969  rol     rcx, 10h
0x14001b96d  test    cx, 0FFFFh
0x14001b972  jnz     short RestoreRcx
0x14001b974  retn
0x14001b975  ror     rcx, 10h; StackCookie
0x14001b979  jmp     __report_gsfailure
```
