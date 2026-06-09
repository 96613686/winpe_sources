# WPP_SF_sqss

- ea: `0x1400140ac`
- end: `0x14001417e`
- name: `WPP_SF_sqss`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400023b0`

## callees

- `0x1400140ac`
- `0x140018590`

## string_xrefs

- `0x14001415b`: `TdxConnectConnectionTlRequestComplete`

## pseudocode

```c
__int64 __fastcall WPP_SF_sqss(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, const char *a6, const char *a7)
{
  const char *v7; // rdx
  __int64 v8; // rax
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r8
  const char *v13; // rcx
  bool v14; // zf

  v7 = a7;
  v8 = -1;
  v10 = 5;
  if ( a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a7[v11] );
    v12 = v11 + 1;
  }
  else
  {
    v12 = 5;
  }
  v13 = a6;
  if ( !a7 )
    v7 = "NULL";
  v14 = a6 == 0;
  if ( a6 )
  {
    do
      ++v8;
    while ( a6[v8] );
    v10 = v8 + 1;
    v14 = a6 == 0;
  }
  if ( v14 )
    v13 = "NULL";
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
           43,
           "TdxConnectConnectionTlRequestComplete",
           38,
           &a5,
           8,
           v13,
           v10,
           v7,
           v12,
           0);
}

```

## disassembly

```asm
0x1400140ac  sub     rsp, 78h
0x1400140b0  mov     rdx, [rsp+78h+arg_30]
0x1400140b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400140bc  mov     r10, rcx
0x1400140bf  mov     r9d, 5
0x1400140c5  test    rdx, rdx
0x1400140c8  jz      short loc_1400140DC
0x1400140ca  mov     r8, rax
0x1400140cd  inc     r8
0x1400140d0  cmp     byte ptr [rdx+r8], 0
0x1400140d5  jnz     short loc_1400140CD
0x1400140d7  inc     r8
0x1400140da  jmp     short loc_1400140DF
0x1400140dc  mov     r8, r9
0x1400140df  mov     rcx, [rsp+78h+arg_28]
0x1400140e7  lea     r11, aNull; "NULL"
0x1400140ee  test    rdx, rdx
0x1400140f1  cmovz   rdx, r11
0x1400140f5  test    rcx, rcx
0x1400140f8  jz      short loc_14001410A
0x1400140fa  inc     rax
0x1400140fd  cmp     byte ptr [rcx+rax], 0
0x140014101  jnz     short loc_1400140FA
0x140014103  lea     r9, [rax+1]
0x140014107  test    rcx, rcx
0x14001410a  mov     rax, cs:pfnWppTraceMessage
0x140014111  cmovz   rcx, r11
0x140014115  mov     [rsp+78h+var_18], 0
0x14001411e  mov     r11d, 2Bh ; '+'
0x140014124  mov     [rsp+78h+var_20], r8
0x140014129  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140014130  mov     [rsp+78h+var_28], rdx
0x140014135  mov     edx, r11d
0x140014138  mov     [rsp+78h+var_30], r9
0x14001413d  mov     r9d, r11d
0x140014140  mov     [rsp+78h+var_38], rcx
0x140014145  lea     rcx, [rsp+78h+arg_20]
0x14001414d  mov     [rsp+78h+var_40], 8
0x140014156  mov     [rsp+78h+var_48], rcx
0x14001415b  lea     rcx, aTdxconnectconn_0; "TdxConnectConnectionTlRequestComplete"
0x140014162  mov     [rsp+78h+var_50], 26h ; '&'
0x14001416b  mov     [rsp+78h+var_58], rcx
0x140014170  mov     rcx, r10
0x140014173  call    _guard_dispatch_icall
0x140014178  add     rsp, 78h
0x14001417c  retn
```
