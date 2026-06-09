# __security_check_cookie

- ea: `0x180003bb0`
- end: `0x180003bce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800017c0`
- `0x180002130`
- `0x1800030d0`
- `0x180003530`
- `0x180003614`
- `0x1800046c0`
- `0x180004cc0`
- `0x180005140`
- `0x18000570c`
- `0x180005f70`
- `0x180006158`
- `0x180006514`
- `0x180006690`
- `0x180006c6c`
- `0x1800070c4`
- `0x1800074e8`
- `0x180007664`
- `0x180007798`
- `0x180007a68`
- `0x180007e34`
- `0x180008260`
- `0x180008980`
- `0x180008ab0`
- `0x180009170`
- `0x1800092a0`
- `0x180009714`
- `0x180009838`
- `0x180009cb4`
- `0x18000a1d8`
- `0x18000a700`

## callees

- `0x180003bb0`
- `0x180003be0`

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
0x180003bb0  cmp     rcx, cs:__security_cookie
0x180003bb7  jnz     short ReportFailure
0x180003bb9  rol     rcx, 10h
0x180003bbd  test    cx, 0FFFFh
0x180003bc2  jnz     short RestoreRcx
0x180003bc4  retn
0x180003bc5  ror     rcx, 10h; StackCookie
0x180003bc9  jmp     __report_gsfailure
```
