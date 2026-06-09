# __security_check_cookie

- ea: `0x180093c00`
- end: `0x180093c1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `238`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`
- `0x180006ef4`
- `0x18000a1d0`
- `0x18000bac0`
- `0x18000c260`
- `0x18000c840`
- `0x18000dad0`
- `0x18000ec10`
- `0x1800106f0`
- `0x180010890`
- `0x1800112c0`
- `0x180013b50`
- `0x180014850`
- `0x180015ee0`
- `0x180019974`
- `0x18001aa0c`
- `0x18001b100`
- `0x18001d414`
- `0x18001dfe0`
- `0x18001e5e4`
- `0x18001f580`
- `0x18001fb90`
- `0x18001ff28`
- `0x1800200d0`
- `0x1800219fc`
- `0x1800224c4`
- `0x1800238dc`
- `0x180024580`
- `0x180024d88`
- `0x180025380`
- `0x180025bb0`
- `0x1800267c0`
- `0x1800269b4`
- `0x180026a80`
- `0x180026b9c`
- `0x180026f28`
- `0x180027678`
- `0x180027794`
- `0x180027b20`
- `0x18002b9bc`
- `0x18002bbe0`
- `0x18002e060`
- `0x18002e888`
- `0x18002eb38`
- `0x180031ffc`
- `0x18003338c`
- `0x180033640`
- `0x180036310`
- `0x180036490`
- `0x180038970`

## callees

- `0x18004d370`
- `0x180093c00`

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
0x180093c00  cmp     rcx, cs:__security_cookie
0x180093c07  jnz     short ReportFailure
0x180093c09  rol     rcx, 10h
0x180093c0d  test    cx, 0FFFFh
0x180093c12  jnz     short RestoreRcx
0x180093c14  retn
0x180093c15  ror     rcx, 10h
0x180093c19  jmp     __report_gsfailure
```
