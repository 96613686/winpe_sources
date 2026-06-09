# __security_check_cookie

- ea: `0x1800050f0`
- end: `0x18000510e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `174`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010dc`
- `0x1800011c4`
- `0x18000120c`
- `0x180001650`
- `0x1800018bc`
- `0x18000198c`
- `0x180001a7c`
- `0x180001b28`
- `0x180001c70`
- `0x180001d8c`
- `0x180001ef4`
- `0x180001f90`
- `0x180002040`
- `0x180002198`
- `0x180002318`
- `0x1800023d4`
- `0x18000249c`
- `0x1800025b0`
- `0x18000263c`
- `0x180002844`
- `0x1800029b4`
- `0x180002ac8`
- `0x180002bcc`
- `0x180002c90`
- `0x180002d9c`
- `0x180002ea0`
- `0x1800032c4`
- `0x18000341c`
- `0x1800036d0`
- `0x1800039e4`
- `0x180003a54`
- `0x180003ae4`
- `0x180003be0`
- `0x180003e84`
- `0x18000417c`
- `0x180004220`
- `0x180006600`
- `0x1800067d0`
- `0x1800069a0`
- `0x180006bc0`
- `0x180006e00`
- `0x180007050`
- `0x180007240`
- `0x180007450`
- `0x180007660`
- `0x1800078b0`
- `0x180007ad0`
- `0x180007cd0`
- `0x180007f20`
- `0x1800081a4`

## callees

- `0x1800050f0`
- `0x180005800`

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
0x1800050f0  cmp     rcx, cs:__security_cookie
0x1800050f7  jnz     short ReportFailure
0x1800050f9  rol     rcx, 10h
0x1800050fd  test    cx, 0FFFFh
0x180005102  jnz     short RestoreRcx
0x180005104  retn
0x180005105  ror     rcx, 10h; StackCookie
0x180005109  jmp     __report_gsfailure
```
