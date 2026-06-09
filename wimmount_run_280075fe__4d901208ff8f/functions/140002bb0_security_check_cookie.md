# __security_check_cookie

- ea: `0x140002bb0`
- end: `0x140002bce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001188`
- `0x140001c54`
- `0x140001d98`
- `0x14000223c`
- `0x140002b2c`
- `0x140009240`
- `0x140009378`
- `0x1400095c8`
- `0x14000a670`
- `0x14000a994`
- `0x14000aa98`
- `0x14000c4d0`

## callees

- `0x140001010`
- `0x140002bb0`

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
0x140002bb0  cmp     rcx, cs:__security_cookie
0x140002bb7  jnz     short ReportFailure
0x140002bb9  rol     rcx, 10h
0x140002bbd  test    cx, 0FFFFh
0x140002bc2  jnz     short RestoreRcx
0x140002bc4  retn
0x140002bc5  ror     rcx, 10h; StackCookie
0x140002bc9  jmp     __report_gsfailure
```
