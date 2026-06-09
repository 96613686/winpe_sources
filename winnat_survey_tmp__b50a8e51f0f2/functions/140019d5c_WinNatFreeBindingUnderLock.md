# WinNatFreeBindingUnderLock

- ea: `0x140019d5c`
- end: `0x14001a039`
- name: `WinNatFreeBindingUnderLock`
- size: `733`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000a7dc`
- `0x14000b220`
- `0x14001a954`

## callees

- `0x14000c948`
- `0x14000c990`
- `0x14000caa0`
- `0x140014aa4`
- `0x140018bf0`
- `0x140019884`
- `0x140019be8`
- `0x140019c68`
- `0x140019d5c`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140019db4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140019e53`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140019db4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140019e53`
- `ntoskrnl!RtlAreBitsClear` at `0x140019e9a`
- `ntoskrnl!RtlAreBitsClear` at `0x140019e9a`
- `ntoskrnl!RtlClearBits` at `0x140019ee5`
- `ntoskrnl!RtlClearBits` at `0x140019ee5`
- `NETIO!PtGetNumNodes` at `0x140019df1`
- `NETIO!PtGetNumNodes` at `0x140019df1`
- `NETIO!PtDeleteEntry` at `0x140019e0e`
- `NETIO!PtDeleteEntry` at `0x140019e0e`

## pseudocode

```c
void *__fastcall WinNatFreeBindingUnderLock(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rbp
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 BitMapForProtocol; // rax
  __int64 v14; // rdx
  _WORD *v15; // rcx
  struct _RTL_BITMAP *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // r9
  void *result; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  bool v24; // zf
  int v25; // r9d
  int v26; // r8d
  __int16 v27[16]; // [rsp+60h] [rbp-68h] BYREF
  __int16 v28[16]; // [rsp+80h] [rbp-48h] BYREF

  v2 = *(_QWORD *)(a1 + 80);
  if ( (*(_BYTE *)(a1 + 88) & 2) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( (*(_BYTE *)(a1 + 88) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  RtlRemoveEntryHashTable(
    *(PRTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(a1 + 80) + 384LL),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 16),
    0);
  if ( (*(_BYTE *)(a1 + 88) & 8) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 48);
    if ( !v6 || (*(_BYTE *)(v6 + 88) & 4) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4);
    if ( *(int *)(v6 + 64) <= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4);
    if ( (*(_BYTE *)(a1 + 88) & 0x10) == 0 )
    {
      v7 = *(_DWORD *)(v6 + 64);
      if ( (unsigned int)PtGetNumNodes(*(_QWORD *)(v6 + 16)) != v7 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v9, v8);
      if ( (int)PtDeleteEntry(*(_QWORD *)(v6 + 16), a1 + 40) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10);
    }
    if ( (int)--*(_DWORD *)(v6 + 64) > 0 )
    {
      v6 = 0;
      *(_QWORD *)(a1 + 48) = 0;
    }
  }
  else
  {
    v6 = a1;
  }
  if ( v6 )
  {
    RtlRemoveEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(v6 + 80) + 392LL),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v6 + 40),
      0);
    LOBYTE(v12) = *(_BYTE *)(v6 + 68);
    BitMapForProtocol = WinNatGetBitMapForProtocol(*(_QWORD *)(v6 + 72), v12);
    v15 = *(_WORD **)(v6 + 104);
    v16 = (struct _RTL_BITMAP *)BitMapForProtocol;
    if ( *v15 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v14);
    v17 = *(_QWORD *)(v6 + 104);
    if ( *(_DWORD *)(v17 + 4) && RtlAreBitsClear(v16, (unsigned __int16)__ROR2__(*(_WORD *)(v17 + 2), 8), 1u) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v18);
    LOBYTE(v15) = *(_BYTE *)(v6 + 68);
    v19 = WinNatDecrementPortUsage(v15, *(_QWORD *)(v6 + 72));
    if ( *(_BYTE *)(*(_QWORD *)(v6 + 72) + 124LL) && !v19 )
      SlbNatNotifyUnusedAddressEntry();
    RtlClearBits(v16, (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v6 + 104) + 2LL), 8), 1u);
  }
  if ( (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 384LL))
    || (result = (void *)WinNatHashTableRestructureRequired(*(_QWORD *)(v20 + 392)), (_BYTE)result) )
  {
    result = (void *)WinNatScheduleRestructureDpc(v2 - 768);
  }
  if ( (Microsoft_Windows_WinNatEnableBits & 4) != 0 && dword_140026104 )
  {
    v24 = (*(_BYTE *)(a1 + 88) & 4) == 0;
    memset(v28, 0, 28);
    memset(v27, 0, 28);
    if ( !v24 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, v22);
    WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 96), v28);
    result = WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 104), v27);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 4) != 0 )
    {
      v25 = 28;
      v26 = 28;
      if ( v27[0] == 2 )
        v26 = 16;
      if ( v28[0] == 2 )
        v25 = 16;
      result = (void *)McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer(
                         (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                         (unsigned int)WINNAT_BINDING_DELETE,
                         v26,
                         v25,
                         (__int64)v28,
                         v26,
                         (__int64)v27,
                         *(_BYTE *)(a1 + 68),
                         *(_DWORD *)(a1 + 64),
                         *(_BYTE *)(a1 + 88) & 1,
                         *(_DWORD *)(a1 + 92));
    }
  }
  *(_BYTE *)(a1 + 88) |= 2u;
  return result;
}

```

## disassembly

```asm
0x140019d5c  mov     [rsp+arg_8], rbx
0x140019d61  mov     [rsp+arg_10], rbp
0x140019d66  push    rsi
0x140019d67  push    rdi
0x140019d68  push    r14
0x140019d6a  sub     rsp, 0B0h
0x140019d71  mov     rax, cs:__security_cookie
0x140019d78  xor     rax, rsp
0x140019d7b  mov     [rsp+0C8h+var_28], rax
0x140019d83  mov     r14, [rcx+50h]
0x140019d87  xor     ebx, ebx
0x140019d89  test    byte ptr [rcx+58h], 2
0x140019d8d  mov     rsi, rcx
0x140019d90  jz      short loc_140019D97
0x140019d92  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019d97  test    byte ptr [rsi+58h], 4
0x140019d9b  jz      short loc_140019DA2
0x140019d9d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019da2  mov     rcx, [rsi+50h]
0x140019da6  lea     rdx, [rsi+10h]; Entry
0x140019daa  xor     r8d, r8d; Context
0x140019dad  mov     rcx, [rcx+180h]; HashTable
0x140019db4  call    cs:__imp_RtlRemoveEntryHashTable
0x140019dbb  nop     dword ptr [rax+rax+00h]
0x140019dc0  test    byte ptr [rsi+58h], 8
0x140019dc4  jz      short loc_140019E35
0x140019dc6  mov     rbp, [rsi+30h]
0x140019dca  test    rbp, rbp
0x140019dcd  jz      short loc_140019DD5
0x140019dcf  test    byte ptr [rbp+58h], 4
0x140019dd3  jnz     short loc_140019DDA
0x140019dd5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019dda  cmp     [rbp+40h], ebx
0x140019ddd  jg      short loc_140019DE4
0x140019ddf  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019de4  test    byte ptr [rsi+58h], 10h
0x140019de8  jnz     short loc_140019E23
0x140019dea  mov     rcx, [rbp+10h]
0x140019dee  mov     edi, [rbp+40h]
0x140019df1  call    cs:__imp_PtGetNumNodes
0x140019df8  nop     dword ptr [rax+rax+00h]
0x140019dfd  cmp     eax, edi
0x140019dff  jz      short loc_140019E06
0x140019e01  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019e06  mov     rcx, [rbp+10h]
0x140019e0a  lea     rdx, [rsi+28h]
0x140019e0e  call    cs:__imp_PtDeleteEntry
0x140019e15  nop     dword ptr [rax+rax+00h]
0x140019e1a  test    eax, eax
0x140019e1c  jns     short loc_140019E23
0x140019e1e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019e23  dec     dword ptr [rbp+40h]
0x140019e26  mov     eax, [rbp+40h]
0x140019e29  test    eax, eax
0x140019e2b  jle     short loc_140019E38
0x140019e2d  xor     ebp, ebp
0x140019e2f  mov     [rsi+30h], rbx
0x140019e33  jmp     short loc_140019E38
0x140019e35  mov     rbp, rsi
0x140019e38  test    rbp, rbp
0x140019e3b  jz      loc_140019EF1
0x140019e41  mov     rcx, [rbp+50h]
0x140019e45  lea     rdx, [rbp+28h]; Entry
0x140019e49  xor     r8d, r8d; Context
0x140019e4c  mov     rcx, [rcx+188h]; HashTable
0x140019e53  call    cs:__imp_RtlRemoveEntryHashTable
0x140019e5a  nop     dword ptr [rax+rax+00h]
0x140019e5f  mov     dl, [rbp+44h]
0x140019e62  mov     rcx, [rbp+48h]
0x140019e66  call    WinNatGetBitMapForProtocol
0x140019e6b  mov     rcx, [rbp+68h]
0x140019e6f  mov     rdi, rax
0x140019e72  cmp     word ptr [rcx], 2
0x140019e76  jz      short loc_140019E7D
0x140019e78  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019e7d  mov     rax, [rbp+68h]
0x140019e81  cmp     [rax+4], ebx
0x140019e84  jz      short loc_140019EAF
0x140019e86  movzx   eax, word ptr [rax+2]
0x140019e8a  mov     r8d, 1; Length
0x140019e90  ror     ax, 8
0x140019e94  mov     rcx, rdi; BitMapHeader
0x140019e97  movzx   edx, ax; StartingIndex
0x140019e9a  call    cs:__imp_RtlAreBitsClear
0x140019ea1  nop     dword ptr [rax+rax+00h]
0x140019ea6  test    al, al
0x140019ea8  jz      short loc_140019EAF
0x140019eaa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019eaf  mov     rdx, [rbp+48h]
0x140019eb3  mov     cl, [rbp+44h]
0x140019eb6  call    WinNatDecrementPortUsage
0x140019ebb  mov     rcx, [rbp+48h]
0x140019ebf  cmp     [rcx+7Ch], bl
0x140019ec2  jz      short loc_140019ECD
0x140019ec4  test    eax, eax
0x140019ec6  jnz     short loc_140019ECD
0x140019ec8  call    SlbNatNotifyUnusedAddressEntry
0x140019ecd  mov     rax, [rbp+68h]
0x140019ed1  mov     r8d, 1; NumberToClear
0x140019ed7  movzx   ecx, word ptr [rax+2]
0x140019edb  ror     cx, 8
0x140019edf  movzx   edx, cx; StartingIndex
0x140019ee2  mov     rcx, rdi; BitMapHeader
0x140019ee5  call    cs:__imp_RtlClearBits
0x140019eec  nop     dword ptr [rax+rax+00h]
0x140019ef1  mov     r9, [rsi+50h]
0x140019ef5  mov     rcx, [r9+180h]
0x140019efc  call    WinNatHashTableRestructureRequired
0x140019f01  test    al, al
0x140019f03  jnz     short loc_140019F15
0x140019f05  mov     rcx, [r9+188h]
0x140019f0c  call    WinNatHashTableRestructureRequired
0x140019f11  test    al, al
0x140019f13  jz      short loc_140019F21
0x140019f15  lea     rcx, [r14-300h]
0x140019f1c  call    WinNatScheduleRestructureDpc
0x140019f21  test    cs:Microsoft_Windows_WinNatEnableBits, 4
0x140019f28  jz      loc_14001A00C
0x140019f2e  cmp     cs:dword_140026104, ebx
0x140019f34  jz      loc_14001A00C
0x140019f3a  xorps   xmm0, xmm0
0x140019f3d  xorps   xmm1, xmm1
0x140019f40  xor     eax, eax
0x140019f42  test    byte ptr [rsi+58h], 4
0x140019f46  movups  xmmword ptr [rsp+0C8h+var_48], xmm0
0x140019f4e  movups  xmmword ptr [rsp+0C8h+var_68], xmm1
0x140019f53  movups  xmmword ptr [rsp+0C8h+var_48+0Ch], xmm0
0x140019f5b  movups  xmmword ptr [rsp+0C8h+var_68+0Ch], xmm1
0x140019f60  jz      short loc_140019F67
0x140019f62  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019f67  mov     rcx, [rsi+60h]
0x140019f6b  lea     rdx, [rsp+0C8h+var_48]
0x140019f73  call    WinNatCopyTransportAddrToSockAddr
0x140019f78  mov     rcx, [rsi+68h]
0x140019f7c  lea     rdx, [rsp+0C8h+var_68]
0x140019f81  call    WinNatCopyTransportAddrToSockAddr
0x140019f86  cmp     cs:dword_140026104, 1
0x140019f8d  jnz     short loc_14001A00C
0x140019f8f  test    cs:Microsoft_Windows_WinNatEnableBits, 4
0x140019f96  jz      short loc_14001A00C
0x140019f98  cmp     [rsp+0C8h+var_68], 2
0x140019f9e  mov     r9d, 1Ch
0x140019fa4  movzx   ecx, byte ptr [rsi+58h]
0x140019fa8  mov     r8d, r9d
0x140019fab  movzx   edx, byte ptr [rsi+44h]
0x140019faf  lea     eax, [r9-0Ch]
0x140019fb3  cmovz   r8d, eax
0x140019fb7  cmp     [rsp+0C8h+var_48], 2
0x140019fc0  cmovz   r9d, eax
0x140019fc4  mov     eax, [rsi+5Ch]
0x140019fc7  mov     [rsp+0C8h+var_78], eax
0x140019fcb  and     ecx, 1
0x140019fce  mov     eax, [rsi+40h]
0x140019fd1  mov     [rsp+0C8h+var_80], ecx
0x140019fd5  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140019fdc  mov     [rsp+0C8h+var_88], eax
0x140019fe0  lea     rax, [rsp+0C8h+var_68]
0x140019fe5  mov     [rsp+0C8h+var_90], edx
0x140019fe9  lea     rdx, WINNAT_BINDING_DELETE
0x140019ff0  mov     [rsp+0C8h+var_98], rax
0x140019ff5  lea     rax, [rsp+0C8h+var_48]
0x140019ffd  mov     [rsp+0C8h+var_A0], r8d
0x14001a002  mov     [rsp+0C8h+var_A8], rax
0x14001a007  call    McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer
0x14001a00c  or      byte ptr [rsi+58h], 2
0x14001a010  mov     rcx, [rsp+0C8h+var_28]
0x14001a018  xor     rcx, rsp; StackCookie
0x14001a01b  call    __security_check_cookie
0x14001a020  lea     r11, [rsp+0C8h+var_18]
0x14001a028  mov     rbx, [r11+28h]
0x14001a02c  mov     rbp, [r11+30h]
0x14001a030  mov     rsp, r11
0x14001a033  pop     r14
0x14001a035  pop     rdi
0x14001a036  pop     rsi
0x14001a037  retn
```
