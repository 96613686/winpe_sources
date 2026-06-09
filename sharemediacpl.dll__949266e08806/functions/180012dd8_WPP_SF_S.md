# WPP_SF_S

- ea: `0x180012dd8`
- end: `0x180012e32`
- name: `WPP_SF_S`
- size: `90`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000822c`
- `0x18000a130`
- `0x18000d338`
- `0x18000df2c`
- `0x1800100ac`
- `0x1800118b4`
- `0x18001458c`
- `0x1800150b0`
- `0x180015214`

## callees

- `0x180012dd8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180012e27`
- `ADVAPI32!TraceMessage` at `0x180012e27`

## pseudocode

```c
ULONG __fastcall WPP_SF_S(TRACEHANDLE a1, USHORT a2, const GUID *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x180012dd8  sub     rsp, 48h
0x180012ddc  xor     r11d, r11d
0x180012ddf  test    r9, r9
0x180012de2  jz      short loc_180012DFC
0x180012de4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012de8  inc     rax
0x180012deb  cmp     [r9+rax*2], r11w
0x180012df0  jnz     short loc_180012DE8
0x180012df2  lea     rax, ds:2[rax*2]
0x180012dfa  jmp     short loc_180012E01
0x180012dfc  mov     eax, 0Ah
0x180012e01  test    r9, r9
0x180012e04  mov     [rsp+48h+var_18], r11
0x180012e09  lea     r10, aNull_0; "NULL"
0x180012e10  mov     [rsp+48h+var_20], rax
0x180012e15  cmovz   r9, r10
0x180012e19  mov     [rsp+48h+var_28], r9
0x180012e1e  movzx   r9d, dx; MessageNumber
0x180012e22  mov     edx, 2Bh ; '+'; MessageFlags
0x180012e27  call    cs:__imp_TraceMessage
0x180012e2d  add     rsp, 48h
0x180012e31  retn
```
