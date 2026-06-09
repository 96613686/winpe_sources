# __security_check_cookie

- ea: `0x140017a10`
- end: `0x140017a2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `100`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400012e0`
- `0x140001c40`
- `0x140001cf0`
- `0x140002000`
- `0x140002150`
- `0x1400022a0`
- `0x1400023c0`
- `0x140002500`
- `0x140002610`
- `0x140003210`
- `0x140003410`
- `0x1400036c0`
- `0x140003860`
- `0x140004cf0`
- `0x140004e40`
- `0x140004fb0`
- `0x140005340`
- `0x140005670`
- `0x140005d80`
- `0x140005f40`
- `0x140006050`
- `0x140006620`
- `0x140007240`
- `0x140007300`
- `0x1400073a0`
- `0x1400074e0`
- `0x140007540`
- `0x140007730`
- `0x140007910`
- `0x1400079b0`
- `0x140007b00`
- `0x140007bb0`
- `0x140007c90`
- `0x140008030`
- `0x140008210`
- `0x140008d30`
- `0x1400096c0`
- `0x14000a400`
- `0x14000a5f0`
- `0x14000a750`
- `0x14000a870`
- `0x14000abf0`
- `0x14000acb0`
- `0x14000b240`
- `0x14000b710`
- `0x14000b860`
- `0x14000bc20`
- `0x14000be40`
- `0x14000c0d0`

## callees

- `0x1400177e0`
- `0x140017a10`

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
0x140017a10  cmp     rcx, cs:__security_cookie
0x140017a17  jnz     short ReportFailure
0x140017a19  rol     rcx, 10h
0x140017a1d  test    cx, 0FFFFh
0x140017a22  jnz     short RestoreRcx
0x140017a24  retn
0x140017a25  ror     rcx, 10h; StackCookie
0x140017a29  jmp     __report_gsfailure
```
