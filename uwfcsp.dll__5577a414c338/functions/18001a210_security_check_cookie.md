# __security_check_cookie

- ea: `0x18001a210`
- end: `0x18001a22e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001594`
- `0x1800018b0`
- `0x180001b54`
- `0x180001f6c`
- `0x1800022a4`
- `0x180002600`
- `0x180002934`
- `0x1800041d0`
- `0x1800042fc`
- `0x180004994`
- `0x180004c28`
- `0x180004f1c`
- `0x1800052ec`
- `0x180005794`
- `0x180005bb0`
- `0x180006dbc`
- `0x18000745c`
- `0x180007788`
- `0x180007b18`
- `0x180007ee8`
- `0x180008624`
- `0x180008ee0`
- `0x1800091c0`
- `0x180009c8c`
- `0x18000a068`
- `0x18000a1b8`
- `0x18000a348`
- `0x18000a50c`
- `0x18000b568`
- `0x18000b61c`
- `0x18000b820`
- `0x18000bb3c`
- `0x18000be5c`
- `0x18000c1ec`
- `0x18000cbfc`
- `0x18000d2d0`
- `0x18000dcb0`
- `0x18000e300`
- `0x18000e610`
- `0x18000e9f0`
- `0x18000ed30`
- `0x18000f340`
- `0x18000f8a0`
- `0x18000ff08`
- `0x180019144`
- `0x180019238`

## callees

- `0x180003c00`
- `0x18001a210`

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
0x18001a210  cmp     rcx, cs:__security_cookie
0x18001a217  jnz     short ReportFailure
0x18001a219  rol     rcx, 10h
0x18001a21d  test    cx, 0FFFFh
0x18001a222  jnz     short RestoreRcx
0x18001a224  retn
0x18001a225  ror     rcx, 10h
0x18001a229  jmp     __report_gsfailure
```
