# WPP_SF_ss

- ea: `0x18000c6d8`
- end: `0x18000c771`
- name: `WPP_SF_ss`
- size: `153`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c338`
- `0x18000de0c`
- `0x18000df48`
- `0x18000dfa4`
- `0x18000e280`
- `0x18000e2dc`
- `0x18000e3a8`
- `0x18000e404`
- `0x18000e540`
- `0x18000e6ec`
- `0x18000e748`
- `0x18000e884`
- `0x18000ebc4`
- `0x18000ec20`
- `0x18000ec7c`
- `0x18000ed48`
- `0x18000efd4`
- `0x18000f030`
- `0x18000f16c`
- `0x18000f238`
- `0x180017db8`
- `0x180017e14`
- `0x1800276f4`
- `0x180027910`
- `0x180027bac`
- `0x180027c08`
- `0x180027c64`
- `0x180027da0`
- `0x18002a348`
- `0x18002a414`
- `0x18002a5c0`

## callees

- `0x18000c6d8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c760`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c760`

## pseudocode

```c
ULONG __fastcall WPP_SF_ss(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, const char *a5)
{
  const char *v5; // r10
  __int64 v6; // r9
  const char *v7; // r11
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax

  v5 = a5;
  v6 = -1;
  v7 = WPP_pszIndent;
  v8 = 5;
  if ( a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a5[v9] );
    v10 = v9 + 1;
  }
  else
  {
    v10 = 5;
  }
  if ( !a5 )
    v5 = "NULL";
  if ( WPP_pszIndent )
  {
    do
      ++v6;
    while ( WPP_pszIndent[v6] );
    v8 = v6 + 1;
  }
  else
  {
    v7 = "NULL";
  }
  return TraceMessage(a1, 0x2Bu, a3, a2, v7, v8, v5, v10, 0);
}

```

## disassembly

```asm
0x18000c6d8  mov     [rsp+arg_0], rbx
0x18000c6dd  push    rsi
0x18000c6de  sub     rsp, 50h
0x18000c6e2  mov     r10, [rsp+58h+arg_20]
0x18000c6ea  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000c6ee  mov     r11, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000c6f5  mov     ebx, 5
0x18000c6fa  test    r10, r10
0x18000c6fd  jz      short loc_18000C711
0x18000c6ff  mov     rax, r9
0x18000c702  inc     rax
0x18000c705  cmp     byte ptr [r10+rax], 0
0x18000c70a  jnz     short loc_18000C702
0x18000c70c  inc     rax
0x18000c70f  jmp     short loc_18000C714
0x18000c711  mov     rax, rbx
0x18000c714  test    r10, r10
0x18000c717  lea     rsi, aNull; "NULL"
0x18000c71e  cmovz   r10, rsi
0x18000c722  test    r11, r11
0x18000c725  jz      short loc_18000C737
0x18000c727  inc     r9
0x18000c72a  cmp     byte ptr [r11+r9], 0
0x18000c72f  jnz     short loc_18000C727
0x18000c731  lea     rbx, [r9+1]
0x18000c735  jmp     short loc_18000C73A
0x18000c737  mov     r11, rsi
0x18000c73a  mov     [rsp+58h+var_18], 0
0x18000c743  mov     [rsp+58h+var_20], rax
0x18000c748  mov     [rsp+58h+var_28], r10
0x18000c74d  movzx   r9d, dx; MessageNumber
0x18000c751  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c756  mov     [rsp+58h+var_30], rbx
0x18000c75b  mov     [rsp+58h+var_38], r11
0x18000c760  call    cs:__imp_TraceMessage
0x18000c766  mov     rbx, [rsp+58h+arg_0]
0x18000c76b  add     rsp, 50h
0x18000c76f  pop     rsi
0x18000c770  retn
```
