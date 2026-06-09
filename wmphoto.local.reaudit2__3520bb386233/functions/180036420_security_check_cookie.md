# __security_check_cookie

- ea: `0x180036420`
- end: `0x18003643e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001024`
- `0x180003050`
- `0x180003170`
- `0x180003ab0`
- `0x180007400`
- `0x18000a330`
- `0x18000cd90`
- `0x18000ef30`
- `0x18000f3b4`
- `0x18000ffc0`
- `0x18001022c`
- `0x1800108a8`
- `0x180010e08`
- `0x180026620`
- `0x180028940`
- `0x180029040`
- `0x180029930`
- `0x18002c260`
- `0x18002d1a0`
- `0x180031850`
- `0x180033ee0`
- `0x1800355e0`
- `0x180035a80`
- `0x1800375d0`
- `0x180038430`
- `0x180039e90`
- `0x18003b1e0`
- `0x18003b700`
- `0x18003c2e0`
- `0x18003c9a0`
- `0x18003cc90`
- `0x18003d270`
- `0x18003d7c0`
- `0x18003db90`
- `0x18003de80`
- `0x18003e0d0`
- `0x18003e2f0`
- `0x180043cf8`

## callees

- `0x180036420`
- `0x180036cf0`

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
0x180036420  cmp     rcx, cs:__security_cookie
0x180036427  jnz     short ReportFailure
0x180036429  rol     rcx, 10h
0x18003642d  test    cx, 0FFFFh
0x180036432  jnz     short RestoreRcx
0x180036434  retn
0x180036435  ror     rcx, 10h; StackCookie
0x180036439  jmp     __report_gsfailure
```
