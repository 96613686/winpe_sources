# WPP_SF_ssD

- ea: `0x18000c248`
- end: `0x18000c2f7`
- name: `WPP_SF_ssD`
- size: `175`
- prototype: ``
- caller_count: `158`
- callee_count: `1`
- tags: ``

## callers

- `0x1800069e4`
- `0x180006ae8`
- `0x180006b58`
- `0x180006d50`
- `0x180006ed8`
- `0x180006f48`
- `0x180007100`
- `0x18000720c`
- `0x18000727c`
- `0x1800072ec`
- `0x18000735c`
- `0x180007468`
- `0x1800074d8`
- `0x180007548`
- `0x1800075b8`
- `0x18000778c`
- `0x1800077fc`
- `0x18000786c`
- `0x1800078dc`
- `0x18000c394`
- `0x18000de68`
- `0x18000ded8`
- `0x18000e000`
- `0x18000e070`
- `0x18000e0e0`
- `0x18000e150`
- `0x18000e1c0`
- `0x18000e338`
- `0x18000e460`
- `0x18000e4d0`
- `0x18000e59c`
- `0x18000e60c`
- `0x18000e67c`
- `0x18000e7a4`
- `0x18000e814`
- `0x18000e8e0`
- `0x18000e994`
- `0x18000ea04`
- `0x18000ea74`
- `0x18000eae4`
- `0x18000eb54`
- `0x18000ecd8`
- `0x18000eda4`
- `0x18000ee14`
- `0x18000ee84`
- `0x18000eef4`
- `0x18000ef64`
- `0x18000f08c`
- `0x18000f0fc`
- `0x18000f1c8`

## callees

- `0x18000c248`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c2e6`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c2e6`

## pseudocode

```c
ULONG WPP_SF_ssD(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, const char *a5, ...)
{
  const char *v5; // r10
  __int64 v6; // r9
  const char *v7; // r11
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
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
  return TraceMessage(a1, 0x2Bu, a3, a2, v7, v8, v5, v10, va, 4, 0);
}

```

## disassembly

```asm
0x18000c248  mov     [rsp+arg_0], rbx
0x18000c24d  push    rsi
0x18000c24e  sub     rsp, 60h
0x18000c252  mov     r10, [rsp+68h+arg_20]
0x18000c25a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000c25e  mov     r11, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000c265  mov     ebx, 5
0x18000c26a  test    r10, r10
0x18000c26d  jz      short loc_18000C281
0x18000c26f  mov     rax, r9
0x18000c272  inc     rax
0x18000c275  cmp     byte ptr [r10+rax], 0
0x18000c27a  jnz     short loc_18000C272
0x18000c27c  inc     rax
0x18000c27f  jmp     short loc_18000C284
0x18000c281  mov     rax, rbx
0x18000c284  test    r10, r10
0x18000c287  lea     rsi, aNull; "NULL"
0x18000c28e  cmovz   r10, rsi
0x18000c292  test    r11, r11
0x18000c295  jz      short loc_18000C2A7
0x18000c297  inc     r9
0x18000c29a  cmp     byte ptr [r11+r9], 0
0x18000c29f  jnz     short loc_18000C297
0x18000c2a1  lea     rbx, [r9+1]
0x18000c2a5  jmp     short loc_18000C2AA
0x18000c2a7  mov     r11, rsi
0x18000c2aa  mov     [rsp+68h+var_18], 0
0x18000c2b3  lea     r9, [rsp+68h+arg_28]
0x18000c2bb  mov     [rsp+68h+var_20], 4
0x18000c2c4  mov     [rsp+68h+var_28], r9
0x18000c2c9  mov     [rsp+68h+var_30], rax
0x18000c2ce  mov     [rsp+68h+var_38], r10
0x18000c2d3  movzx   r9d, dx; MessageNumber
0x18000c2d7  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c2dc  mov     [rsp+68h+var_40], rbx
0x18000c2e1  mov     [rsp+68h+var_48], r11
0x18000c2e6  call    cs:__imp_TraceMessage
0x18000c2ec  mov     rbx, [rsp+68h+arg_0]
0x18000c2f1  add     rsp, 60h
0x18000c2f5  pop     rsi
0x18000c2f6  retn
```
