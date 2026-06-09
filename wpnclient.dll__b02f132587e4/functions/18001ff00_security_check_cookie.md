# __security_check_cookie

- ea: `0x18001ff00`
- end: `0x18001ff1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `102`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001438`
- `0x180001584`
- `0x18000187c`
- `0x180001a24`
- `0x180001cfc`
- `0x180001dd0`
- `0x1800020d0`
- `0x180002b70`
- `0x180003990`
- `0x1800043d0`
- `0x180004880`
- `0x180005080`
- `0x180005a00`
- `0x180005f10`
- `0x1800061f0`
- `0x180006d30`
- `0x180007614`
- `0x180007760`
- `0x180007b40`
- `0x1800082b8`
- `0x180008390`
- `0x1800087d0`
- `0x1800089a0`
- `0x180008fe0`
- `0x180009380`
- `0x180009890`
- `0x18000a460`
- `0x18000b440`
- `0x18000bbf0`
- `0x18000c7d0`
- `0x18000cb68`
- `0x18000d0d0`
- `0x18000d7d8`
- `0x18000d980`
- `0x18000da20`
- `0x18000e4c0`
- `0x18000f000`
- `0x18000f750`
- `0x180010270`
- `0x180010800`
- `0x180010a54`
- `0x180010f1c`
- `0x1800119b0`
- `0x180011c60`
- `0x180015950`
- `0x180016334`
- `0x1800167e4`
- `0x180016e44`

## callees

- `0x18001ff00`
- `0x180020840`

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
0x18001ff00  cmp     rcx, cs:__security_cookie
0x18001ff07  jnz     short ReportFailure
0x18001ff09  rol     rcx, 10h
0x18001ff0d  test    cx, 0FFFFh
0x18001ff12  jnz     short RestoreRcx
0x18001ff14  retn
0x18001ff15  ror     rcx, 10h; StackCookie
0x18001ff19  jmp     __report_gsfailure
```
