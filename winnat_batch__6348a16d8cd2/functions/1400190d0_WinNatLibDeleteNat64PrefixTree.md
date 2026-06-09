# WinNatLibDeleteNat64PrefixTree

- ea: `0x1400190d0`
- end: `0x1400191be`
- name: `WinNatLibDeleteNat64PrefixTree`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140018f48`

## callees

- `0x14000caa0`
- `0x1400190d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019160`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019160`
- `NETIO!PtDestroyTable` at `0x14001918f`
- `NETIO!PtDestroyTable` at `0x14001918f`
- `NETIO!PtGetNumNodes` at `0x140019177`
- `NETIO!PtGetNumNodes` at `0x140019177`
- `NETIO!PtEnumOverTable` at `0x14001912e`
- `NETIO!PtEnumOverTable` at `0x14001912e`
- `NETIO!PtDeleteEntry` at `0x14001914f`
- `NETIO!PtDeleteEntry` at `0x14001914f`

## pseudocode

```c
__int64 __fastcall WinNatLibDeleteNat64PrefixTree(__int64 a1)
{
  _QWORD *v1; // rdi
  int v2; // esi
  void *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+28h] [rbp-40h]
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-18h]
  int v16; // [rsp+70h] [rbp+8h] BYREF
  __int64 v17; // [rsp+78h] [rbp+10h] BYREF

  v16 = 0;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  v1 = (_QWORD *)(a1 + 416);
  do
  {
    LOWORD(v13) = 0;
    v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, _QWORD, int, int *, __int64 *))PtEnumOverTable)(
           *v1,
           0,
           0,
           &v14,
           0,
           v13,
           &v16,
           &v17);
    if ( !v16 )
      break;
    v3 = (void *)(v17 - 24);
    PtDeleteEntry(*v1);
    ExFreePoolWithTag(v3, 0);
  }
  while ( v2 != -1073741197 );
  if ( (unsigned int)PtGetNumNodes(*v1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
  result = PtDestroyTable(v1);
  *v1 = 0;
  if ( (int)result < 0 )
    return MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9, v11, v12);
  return result;
}

```

## disassembly

```asm
0x1400190d0  mov     r11, rsp
0x1400190d3  mov     [r11+18h], rbx
0x1400190d7  mov     [r11+20h], rsi
0x1400190db  push    rdi
0x1400190dc  sub     rsp, 60h
0x1400190e0  xor     eax, eax
0x1400190e2  mov     [rsp+68h+arg_0], 0
0x1400190ea  xorps   xmm0, xmm0
0x1400190ed  mov     [r11+10h], rax
0x1400190f1  movups  [rsp+68h+var_28], xmm0
0x1400190f6  mov     [r11-18h], rax
0x1400190fa  lea     rdi, [rcx+1A0h]
0x140019101  xor     eax, eax
0x140019103  lea     rcx, [rsp+68h+arg_8]
0x140019108  mov     [rsp+68h+var_30], rcx
0x14001910d  lea     r9, [rsp+68h+var_28]
0x140019112  lea     rcx, [rsp+68h+arg_0]
0x140019117  xor     r8d, r8d
0x14001911a  mov     [rsp+68h+var_38], rcx
0x14001911f  xor     edx, edx
0x140019121  mov     rcx, [rdi]
0x140019124  mov     [rsp+68h+var_40], ax
0x140019129  mov     [rsp+68h+var_48], rax
0x14001912e  call    cs:__imp_PtEnumOverTable
0x140019135  nop     dword ptr [rax+rax+00h]
0x14001913a  cmp     [rsp+68h+arg_0], 0
0x14001913f  mov     esi, eax
0x140019141  jz      short loc_140019174
0x140019143  mov     rdx, [rsp+68h+arg_8]
0x140019148  mov     rcx, [rdi]
0x14001914b  lea     rbx, [rdx-18h]
0x14001914f  call    cs:__imp_PtDeleteEntry
0x140019156  nop     dword ptr [rax+rax+00h]
0x14001915b  xor     edx, edx; Tag
0x14001915d  mov     rcx, rbx; P
0x140019160  call    cs:__imp_ExFreePoolWithTag
0x140019167  nop     dword ptr [rax+rax+00h]
0x14001916c  cmp     esi, 0C0000273h
0x140019172  jnz     short loc_140019101
0x140019174  mov     rcx, [rdi]
0x140019177  call    cs:__imp_PtGetNumNodes
0x14001917e  nop     dword ptr [rax+rax+00h]
0x140019183  test    eax, eax
0x140019185  jz      short loc_14001918C
0x140019187  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001918c  mov     rcx, rdi
0x14001918f  call    cs:__imp_PtDestroyTable
0x140019196  nop     dword ptr [rax+rax+00h]
0x14001919b  mov     qword ptr [rdi], 0
0x1400191a2  test    eax, eax
0x1400191a4  jns     short loc_1400191AB
0x1400191a6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400191ab  lea     r11, [rsp+68h+var_8]
0x1400191b0  mov     rbx, [r11+20h]
0x1400191b4  mov     rsi, [r11+28h]
0x1400191b8  mov     rsp, r11
0x1400191bb  pop     rdi
0x1400191bc  retn
```
