# __security_check_cookie

- ea: `0x180001dc0`
- end: `0x180001dde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002780`
- `0x180003670`
- `0x1800037e0`
- `0x180005800`
- `0x180005950`
- `0x180005c10`
- `0x180005d60`
- `0x180006a80`
- `0x180006bf0`
- `0x1800095d0`
- `0x180009910`
- `0x180009b90`
- `0x180009c10`
- `0x180015890`

## callees

- `0x180001dc0`
- `0x1800022f0`

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
0x180001dc0  cmp     rcx, cs:__security_cookie
0x180001dc7  jnz     short ReportFailure
0x180001dc9  rol     rcx, 10h
0x180001dcd  test    cx, 0FFFFh
0x180001dd2  jnz     short RestoreRcx
0x180001dd4  retn
0x180001dd5  ror     rcx, 10h; StackCookie
0x180001dd9  jmp     __report_gsfailure
```
