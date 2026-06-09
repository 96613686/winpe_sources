# __security_check_cookie

- ea: `0x180001590`
- end: `0x1800015ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002700`
- `0x180002810`
- `0x180003e48`
- `0x180004304`
- `0x180004a60`
- `0x180005ef4`
- `0x180006994`
- `0x180006f6c`
- `0x180007200`
- `0x180007848`
- `0x180007a24`
- `0x180007d64`
- `0x180008118`
- `0x1800083ec`
- `0x180008a48`
- `0x1800095ec`
- `0x180009798`
- `0x180009c50`
- `0x18000a160`
- `0x18000a298`
- `0x18000a3d0`
- `0x18000a668`
- `0x18000a99c`
- `0x18000aa00`
- `0x18000ad00`
- `0x18000b554`
- `0x18000b9b0`

## callees

- `0x180001590`
- `0x180001bd0`

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
0x180001590  cmp     rcx, cs:__security_cookie
0x180001597  jnz     short ReportFailure
0x180001599  rol     rcx, 10h
0x18000159d  test    cx, 0FFFFh
0x1800015a2  jnz     short RestoreRcx
0x1800015a4  retn
0x1800015a5  ror     rcx, 10h; StackCookie
0x1800015a9  jmp     __report_gsfailure
```
