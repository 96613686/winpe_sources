# WinNatFreeBindingUnderLock

- ea: `0x140019d5c`
- end: `0x14001a039`
- name: `WinNatFreeBindingUnderLock`
- size: `733`
- prototype: ``
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
__int64 __fastcall WinNatFreeBindingUnderLock(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r14
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbp
  int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 BitMapForProtocol; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  _WORD *v25; // rcx
  struct _RTL_BITMAP *v26; // rdi
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // eax
  __int64 v32; // r9
  __int64 result; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  bool v38; // zf
  int v39; // r9d
  int v40; // r8d
  _WORD v41[16]; // [rsp+60h] [rbp-68h] BYREF
  _WORD v42[16]; // [rsp+80h] [rbp-48h] BYREF

  v4 = *(_QWORD *)(a1 + 80);
  if ( (*(_BYTE *)(a1 + 88) & 2) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( (*(_BYTE *)(a1 + 88) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  RtlRemoveEntryHashTable(
    *(PRTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(a1 + 80) + 384LL),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 16),
    0);
  if ( (*(_BYTE *)(a1 + 88) & 8) != 0 )
  {
    v10 = *(_QWORD *)(a1 + 48);
    if ( !v10 || (*(_BYTE *)(v10 + 88) & 4) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6, v8, v9);
    if ( *(int *)(v10 + 64) <= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6, v8, v9);
    if ( (*(_BYTE *)(a1 + 88) & 0x10) == 0 )
    {
      v11 = *(_DWORD *)(v10 + 64);
      if ( (unsigned int)PtGetNumNodes(*(_QWORD *)(v10 + 16)) != v11 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v13, v12, v14, v15);
      if ( (int)PtDeleteEntry(*(_QWORD *)(v10 + 16)) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18, v19);
    }
    if ( (int)--*(_DWORD *)(v10 + 64) > 0 )
    {
      v10 = 0;
      *(_QWORD *)(a1 + 48) = 0;
    }
  }
  else
  {
    v10 = a1;
  }
  if ( v10 )
  {
    RtlRemoveEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(v10 + 80) + 392LL),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v10 + 40),
      0);
    LOBYTE(v20) = *(_BYTE *)(v10 + 68);
    BitMapForProtocol = WinNatGetBitMapForProtocol(*(_QWORD *)(v10 + 72), v20);
    v25 = *(_WORD **)(v10 + 104);
    v26 = (struct _RTL_BITMAP *)BitMapForProtocol;
    if ( *v25 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v25, v22, v23, v24);
    v27 = *(_QWORD *)(v10 + 104);
    if ( *(_DWORD *)(v27 + 4) && RtlAreBitsClear(v26, (unsigned __int16)__ROR2__(*(_WORD *)(v27 + 2), 8), 1u) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v25, v28, v29, v30);
    LOBYTE(v25) = *(_BYTE *)(v10 + 68);
    v31 = WinNatDecrementPortUsage(v25, *(_QWORD *)(v10 + 72));
    if ( *(_BYTE *)(*(_QWORD *)(v10 + 72) + 124LL) && !v31 )
      SlbNatNotifyUnusedAddressEntry();
    RtlClearBits(v26, (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v10 + 104) + 2LL), 8), 1u);
  }
  if ( (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 384LL))
    || (result = WinNatHashTableRestructureRequired(*(_QWORD *)(v32 + 392)), (_BYTE)result) )
  {
    result = WinNatScheduleRestructureDpc(v4 - 768);
  }
  if ( (Microsoft_Windows_WinNatEnableBits & 4) != 0 && dword_140026104 )
  {
    v38 = (*(_BYTE *)(a1 + 88) & 4) == 0;
    memset(v42, 0, 28);
    memset(v41, 0, 28);
    if ( !v38 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v34, v36, v37);
    WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a1 + 96), v42);
    result = WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a1 + 104), v41);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 4) != 0 )
    {
      v39 = 28;
      v40 = 28;
      if ( v41[0] == 2 )
        v40 = 16;
      if ( v42[0] == 2 )
        v39 = 16;
      result = McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer(
                 (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                 (unsigned int)WINNAT_BINDING_DELETE,
                 v40,
                 v39,
                 (__int64)v42,
                 v40,
                 (__int64)v41,
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
