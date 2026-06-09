# __security_check_cookie

- ea: `0x180026a30`
- end: `0x180026a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `56`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a60`
- `0x180002100`
- `0x1800029b0`
- `0x180005d90`
- `0x180008e10`
- `0x18000b7c4`
- `0x18000c340`
- `0x18000c698`
- `0x18000cd44`
- `0x18000d22c`
- `0x18000e3a0`
- `0x18000eec0`
- `0x18000f660`
- `0x18000fb30`
- `0x180010080`
- `0x180010ce0`
- `0x180011f50`
- `0x1800129b0`
- `0x180013044`
- `0x180016838`
- `0x180016c14`
- `0x180017470`
- `0x180017e90`
- `0x180019180`
- `0x180019880`
- `0x18001b404`
- `0x18001c238`
- `0x18001c630`
- `0x18001ce24`
- `0x18001dad0`
- `0x18001e2d0`
- `0x18001e3c4`
- `0x18001ed50`
- `0x18001f3e0`
- `0x1800208ec`
- `0x180022560`
- `0x180022d7c`
- `0x18002854c`
- `0x180028640`
- `0x180028c3c`
- `0x180028da4`
- `0x180028f6c`
- `0x180029604`
- `0x1800298c0`
- `0x18002aa0c`
- `0x18002ae10`
- `0x18002bc1c`
- `0x18002c658`
- `0x18002d094`
- `0x18002d6a8`

## callees

- `0x180026a30`
- `0x180026fc0`

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
0x180026a30  cmp     rcx, cs:__security_cookie
0x180026a37  jnz     short ReportFailure
0x180026a39  rol     rcx, 10h
0x180026a3d  test    cx, 0FFFFh
0x180026a42  jnz     short RestoreRcx
0x180026a44  retn
0x180026a45  ror     rcx, 10h; StackCookie
0x180026a49  jmp     __report_gsfailure
```
