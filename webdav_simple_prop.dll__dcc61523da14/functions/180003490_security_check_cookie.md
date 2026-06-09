# __security_check_cookie

- ea: `0x180003490`
- end: `0x1800034ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a04`
- `0x180001c30`
- `0x180001cdc`
- `0x180002080`
- `0x180002220`
- `0x180002520`
- `0x180002974`
- `0x180002a7c`
- `0x180002b34`
- `0x180002c84`
- `0x180003340`
- `0x180003404`

## callees

- `0x180001790`
- `0x180003490`

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
0x180003490  cmp     rcx, cs:__security_cookie
0x180003497  jnz     short ReportFailure
0x180003499  rol     rcx, 10h
0x18000349d  test    cx, 0FFFFh
0x1800034a2  jnz     short RestoreRcx
0x1800034a4  retn
0x1800034a5  ror     rcx, 10h
0x1800034a9  jmp     __report_gsfailure
```
