# __security_check_cookie

- ea: `0x140006330`
- end: `0x14000634e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001044`
- `0x140001308`
- `0x140001464`
- `0x140001f8c`
- `0x140002228`
- `0x140002318`
- `0x1400025bc`
- `0x1400027e4`
- `0x140003118`
- `0x140003368`
- `0x140003e20`
- `0x14000c010`

## callees

- `0x140001010`
- `0x140006330`

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
0x140006330  cmp     rcx, cs:__security_cookie
0x140006337  jnz     short ReportFailure
0x140006339  rol     rcx, 10h
0x14000633d  test    cx, 0FFFFh
0x140006342  jnz     short RestoreRcx
0x140006344  retn
0x140006345  ror     rcx, 10h; StackCookie
0x140006349  jmp     __report_gsfailure
```
