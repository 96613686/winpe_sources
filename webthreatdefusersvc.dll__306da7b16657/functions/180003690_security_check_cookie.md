# __security_check_cookie

- ea: `0x180003690`
- end: `0x1800036ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001160`
- `0x180001240`
- `0x180001300`
- `0x1800013c4`
- `0x180001484`
- `0x180001514`
- `0x1800015e4`
- `0x180001754`
- `0x1800018a8`
- `0x180001a78`
- `0x180001b9c`
- `0x180001cc0`
- `0x180001d9c`
- `0x180001e58`
- `0x180001f54`
- `0x180002014`
- `0x1800020d0`
- `0x1800021a0`
- `0x180002244`
- `0x1800022e0`
- `0x180002410`
- `0x1800024ec`
- `0x180002580`
- `0x180002630`
- `0x1800027f4`
- `0x1800029f4`
- `0x180002b4c`
- `0x180002bfc`
- `0x180002d30`
- `0x180003130`
- `0x1800055d4`
- `0x1800092d0`
- `0x18000ab70`
- `0x18000b774`
- `0x18000bd70`
- `0x18000c884`
- `0x18000ca50`
- `0x18000cc70`
- `0x18000cfd8`
- `0x18000d120`
- `0x18000e874`
- `0x18000e9ac`
- `0x18000ef04`
- `0x18000fbf0`
- `0x180010d1c`
- `0x1800111c0`
- `0x180013194`
- `0x180014550`
- `0x180014e10`

## callees

- `0x180003690`
- `0x180003da0`

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
0x180003690  cmp     rcx, cs:__security_cookie
0x180003697  jnz     short ReportFailure
0x180003699  rol     rcx, 10h
0x18000369d  test    cx, 0FFFFh
0x1800036a2  jnz     short RestoreRcx
0x1800036a4  retn
0x1800036a5  ror     rcx, 10h; StackCookie
0x1800036a9  jmp     __report_gsfailure
```
