# WinNatLibDeleteNat64PrefixTree

- ea: `0x1400195b0`
- end: `0x14001969e`
- name: `WinNatLibDeleteNat64PrefixTree`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140019428`

## callees

- `0x14000caa0`
- `0x1400195b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019640`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019640`
- `NETIO!PtDestroyTable` at `0x14001966f`
- `NETIO!PtDestroyTable` at `0x14001966f`
- `NETIO!PtGetNumNodes` at `0x140019657`
- `NETIO!PtGetNumNodes` at `0x140019657`
- `NETIO!PtEnumOverTable` at `0x14001960e`
- `NETIO!PtEnumOverTable` at `0x14001960e`
- `NETIO!PtDeleteEntry` at `0x14001962f`
- `NETIO!PtDeleteEntry` at `0x14001962f`

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
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // [rsp+28h] [rbp-40h]
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]
  int v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 v15; // [rsp+78h] [rbp+10h] BYREF

  v14 = 0;
  v15 = 0;
  v12 = 0;
  v13 = 0;
  v1 = (_QWORD *)(a1 + 416);
  do
  {
    LOWORD(v11) = 0;
    v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, _QWORD, int, int *, __int64 *))PtEnumOverTable)(
           *v1,
           0,
           0,
           &v12,
           0,
           v11,
           &v14,
           &v15);
    if ( !v14 )
      break;
    v3 = (void *)(v15 - 24);
    PtDeleteEntry(*v1, v15);
    ExFreePoolWithTag(v3, 0);
  }
  while ( v2 != -1073741197 );
  if ( (unsigned int)PtGetNumNodes(*v1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6);
  result = PtDestroyTable(v1);
  *v1 = 0;
  if ( (int)result < 0 )
    return MicrosoftTelemetryAssertTriggeredNoArgsKM(v9, v8, v10);
  return result;
}

```

## disassembly

```asm
0x1400195b0  mov     r11, rsp
0x1400195b3  mov     [r11+18h], rbx
0x1400195b7  mov     [r11+20h], rsi
0x1400195bb  push    rdi
0x1400195bc  sub     rsp, 60h
0x1400195c0  xor     eax, eax
0x1400195c2  mov     [rsp+68h+arg_0], 0
0x1400195ca  xorps   xmm0, xmm0
0x1400195cd  mov     [r11+10h], rax
0x1400195d1  movups  [rsp+68h+var_28], xmm0
0x1400195d6  mov     [r11-18h], rax
0x1400195da  lea     rdi, [rcx+1A0h]
0x1400195e1  xor     eax, eax
0x1400195e3  lea     rcx, [rsp+68h+arg_8]
0x1400195e8  mov     [rsp+68h+var_30], rcx
0x1400195ed  lea     r9, [rsp+68h+var_28]
0x1400195f2  lea     rcx, [rsp+68h+arg_0]
0x1400195f7  xor     r8d, r8d
0x1400195fa  mov     [rsp+68h+var_38], rcx
0x1400195ff  xor     edx, edx
0x140019601  mov     rcx, [rdi]
0x140019604  mov     [rsp+68h+var_40], ax
0x140019609  mov     [rsp+68h+var_48], rax
0x14001960e  call    cs:__imp_PtEnumOverTable
0x140019615  nop     dword ptr [rax+rax+00h]
0x14001961a  cmp     [rsp+68h+arg_0], 0
0x14001961f  mov     esi, eax
0x140019621  jz      short loc_140019654
0x140019623  mov     rdx, [rsp+68h+arg_8]
0x140019628  mov     rcx, [rdi]
0x14001962b  lea     rbx, [rdx-18h]
0x14001962f  call    cs:__imp_PtDeleteEntry
0x140019636  nop     dword ptr [rax+rax+00h]
0x14001963b  xor     edx, edx; Tag
0x14001963d  mov     rcx, rbx; P
0x140019640  call    cs:__imp_ExFreePoolWithTag
0x140019647  nop     dword ptr [rax+rax+00h]
0x14001964c  cmp     esi, 0C0000273h
0x140019652  jnz     short loc_1400195E1
0x140019654  mov     rcx, [rdi]
0x140019657  call    cs:__imp_PtGetNumNodes
0x14001965e  nop     dword ptr [rax+rax+00h]
0x140019663  test    eax, eax
0x140019665  jz      short loc_14001966C
0x140019667  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001966c  mov     rcx, rdi
0x14001966f  call    cs:__imp_PtDestroyTable
0x140019676  nop     dword ptr [rax+rax+00h]
0x14001967b  mov     qword ptr [rdi], 0
0x140019682  test    eax, eax
0x140019684  jns     short loc_14001968B
0x140019686  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001968b  lea     r11, [rsp+68h+var_8]
0x140019690  mov     rbx, [r11+20h]
0x140019694  mov     rsi, [r11+28h]
0x140019698  mov     rsp, r11
0x14001969b  pop     rdi
0x14001969c  retn
```
