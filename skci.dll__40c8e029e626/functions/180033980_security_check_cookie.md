# __security_check_cookie

- ea: `0x180033980`
- end: `0x18003399e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `87`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005610`
- `0x180006dd0`
- `0x180006f80`
- `0x180007070`
- `0x1800071f0`
- `0x180011090`
- `0x180011ac0`
- `0x180011c50`
- `0x180013810`
- `0x180013998`
- `0x180013b9c`
- `0x180013cd4`
- `0x180013da8`
- `0x180014124`
- `0x1800144c0`
- `0x180014614`
- `0x1800146d4`
- `0x180014748`
- `0x180014a14`
- `0x1800150c0`
- `0x180015360`
- `0x18001618c`
- `0x1800162e4`
- `0x180017f60`
- `0x18001805c`
- `0x1800181e4`
- `0x1800182c4`
- `0x180018404`
- `0x180018a6c`
- `0x180018d68`
- `0x18001cec8`
- `0x180020880`
- `0x18002151c`
- `0x180021920`
- `0x180021ce4`
- `0x180021d7c`
- `0x180021e4c`
- `0x180021f94`
- `0x180022080`
- `0x180022a80`
- `0x180022b78`
- `0x180022c8c`
- `0x180023d70`
- `0x180026108`
- `0x18002697c`
- `0x180026bf8`
- `0x1800270d4`
- `0x180027604`
- `0x180027c78`
- `0x180028174`

## callees

- `0x180007490`
- `0x180033980`

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
0x180033980  cmp     rcx, cs:__security_cookie
0x180033987  jnz     short ReportFailure
0x180033989  rol     rcx, 10h
0x18003398d  test    cx, 0FFFFh
0x180033992  jnz     short RestoreRcx
0x180033994  retn
0x180033995  ror     rcx, 10h; StackCookie
0x180033999  jmp     __report_gsfailure
```
