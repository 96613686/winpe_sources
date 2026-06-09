# __security_check_cookie

- ea: `0x180006c30`
- end: `0x180006c4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001110`
- `0x180001440`
- `0x180001d80`
- `0x180002c50`
- `0x180003170`
- `0x180003e70`
- `0x1800041d0`
- `0x1800048a0`
- `0x180004cb0`
- `0x180004fa0`
- `0x1800059a0`
- `0x180005de0`
- `0x180005f70`
- `0x180006620`
- `0x180006764`
- `0x180006b0c`

## callees

- `0x180006330`
- `0x180006c30`

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
0x180006c30  cmp     rcx, cs:__security_cookie
0x180006c37  jnz     short loc_180006C49
0x180006c39  rol     rcx, 10h
0x180006c3d  test    cx, 0FFFFh
0x180006c42  jnz     short loc_180006C45
0x180006c44  retn
0x180006c45  ror     rcx, 10h
0x180006c49  jmp     __report_gsfailure
```
