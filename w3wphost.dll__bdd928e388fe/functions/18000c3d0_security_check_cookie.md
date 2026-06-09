# __security_check_cookie

- ea: `0x18000c3d0`
- end: `0x18000c3ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c30`
- `0x180003684`
- `0x180003df0`
- `0x180004ad4`
- `0x1800051dc`
- `0x180005d44`
- `0x180006fe8`
- `0x1800073c0`
- `0x180007ce8`
- `0x180007e48`
- `0x180007f8c`
- `0x180008798`
- `0x180009044`
- `0x1800097a0`
- `0x18000abd0`
- `0x18000ba44`
- `0x18000bda8`
- `0x18000c310`

## callees

- `0x1800026f0`
- `0x18000c3d0`

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
0x18000c3d0  cmp     rcx, cs:__security_cookie
0x18000c3d7  jnz     short ReportFailure
0x18000c3d9  rol     rcx, 10h
0x18000c3dd  test    cx, 0FFFFh
0x18000c3e2  jnz     short RestoreRcx
0x18000c3e4  retn
0x18000c3e5  ror     rcx, 10h
0x18000c3e9  jmp     __report_gsfailure
```
