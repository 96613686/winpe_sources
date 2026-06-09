# __security_check_cookie

- ea: `0x100426580`
- end: `0x10042659e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100401420`
- `0x1004181d0`
- `0x100420450`
- `0x100421ba0`
- `0x100421d00`
- `0x100423260`
- `0x100427f94`
- `0x100428a08`
- `0x10042cae4`
- `0x10042d618`
- `0x10042e2ec`
- `0x10042ef20`
- `0x10042f444`
- `0x10042f864`
- `0x10042fe1c`
- `0x100432f40`
- `0x10043344c`
- `0x10043396c`
- `0x100433b04`
- `0x1004344e8`
- `0x100434964`
- `0x100434a6c`
- `0x100434b8c`
- `0x100435934`
- `0x100437f8c`
- `0x100438940`
- `0x1004391f8`

## callees

- `0x100426580`
- `0x100426970`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x100426580  cmp     rcx, cs:__security_cookie
0x100426587  jnz     short loc_100426599
0x100426589  rol     rcx, 10h
0x10042658d  test    cx, 0FFFFh
0x100426592  jnz     short loc_100426595
0x100426594  retn
0x100426595  ror     rcx, 10h
0x100426599  jmp     __report_gsfailure
```
