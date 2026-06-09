# __security_check_cookie

- ea: `0x180016020`
- end: `0x18001603e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `43`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002a0c`
- `0x180002e64`
- `0x1800036b0`
- `0x180003838`
- `0x180003af4`
- `0x180003dc4`
- `0x180006020`
- `0x180006548`
- `0x180006e50`
- `0x180007120`
- `0x180007700`
- `0x180007880`
- `0x1800096e8`
- `0x18000b034`
- `0x18000c0ec`
- `0x18000c3f8`
- `0x18000c590`
- `0x18000c69c`
- `0x18000d39c`
- `0x18000d638`
- `0x18000e330`
- `0x18000f06c`
- `0x18000f4b0`
- `0x1800102a0`
- `0x180010860`
- `0x1800111a0`
- `0x18001231c`
- `0x180012890`
- `0x180012a18`
- `0x180012c20`
- `0x180012d80`
- `0x180013030`
- `0x180013170`
- `0x180013ca0`
- `0x180013ed0`
- `0x180014050`
- `0x1800141b0`
- `0x1800142e0`
- `0x180014590`
- `0x180014740`
- `0x180014990`
- `0x180015540`
- `0x180015f98`

## callees

- `0x180001920`
- `0x180016020`

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
0x180016020  cmp     rcx, cs:__security_cookie
0x180016027  jnz     short ReportFailure
0x180016029  rol     rcx, 10h
0x18001602d  test    cx, 0FFFFh
0x180016032  jnz     short RestoreRcx
0x180016034  retn
0x180016035  ror     rcx, 10h
0x180016039  jmp     __report_gsfailure
```
