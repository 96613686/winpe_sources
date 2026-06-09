# __security_check_cookie

- ea: `0x18000cff0`
- end: `0x18000d00e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011c0`
- `0x1800013c0`
- `0x180001670`
- `0x180002360`
- `0x180002660`
- `0x180002910`
- `0x180002b70`
- `0x180002f80`
- `0x180003120`
- `0x1800032c0`
- `0x180003470`
- `0x180003620`
- `0x1800038d0`
- `0x180003b80`
- `0x180003e30`
- `0x180004110`
- `0x180004420`
- `0x1800044a0`
- `0x180004780`
- `0x180004a20`
- `0x180004cd0`
- `0x180004f80`
- `0x1800052f0`
- `0x1800055b0`
- `0x180005880`
- `0x180005b30`
- `0x180005de0`
- `0x1800060c0`
- `0x180007284`
- `0x180007520`
- `0x180007f30`
- `0x180008098`
- `0x180008260`
- `0x180008a04`
- `0x180008e14`
- `0x18000a0a4`
- `0x18000a288`
- `0x18000a9a0`
- `0x18000b59c`
- `0x18000c154`
- `0x18000c330`
- `0x18000c850`
- `0x18000cb40`
- `0x18000cd44`
- `0x18000cec0`

## callees

- `0x180001c50`
- `0x18000cff0`

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
0x18000cff0  cmp     rcx, cs:__security_cookie
0x18000cff7  jnz     short ReportFailure
0x18000cff9  rol     rcx, 10h
0x18000cffd  test    cx, 0FFFFh
0x18000d002  jnz     short RestoreRcx
0x18000d004  retn
0x18000d005  ror     rcx, 10h
0x18000d009  jmp     __report_gsfailure
```
