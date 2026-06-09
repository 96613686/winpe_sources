# __security_check_cookie

- ea: `0x18000f1f0`
- end: `0x18000f20e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cf0`
- `0x180002890`
- `0x180002ba0`
- `0x180003420`
- `0x1800042c0`
- `0x180005000`
- `0x1800063d0`
- `0x1800068f0`
- `0x180006b90`
- `0x180007020`
- `0x1800072f0`
- `0x180008e60`
- `0x180009570`
- `0x180009f18`
- `0x18000d228`
- `0x18000d514`
- `0x18000f144`

## callees

- `0x1800086c0`
- `0x18000f1f0`

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
0x18000f1f0  cmp     rcx, cs:__security_cookie
0x18000f1f7  jnz     short ReportFailure
0x18000f1f9  rol     rcx, 10h
0x18000f1fd  test    cx, 0FFFFh
0x18000f202  jnz     short RestoreRcx
0x18000f204  retn
0x18000f205  ror     rcx, 10h
0x18000f209  jmp     __report_gsfailure
```
