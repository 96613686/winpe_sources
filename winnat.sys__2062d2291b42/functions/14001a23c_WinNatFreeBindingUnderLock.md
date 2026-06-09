# WinNatFreeBindingUnderLock

- ea: `0x14001a23c`
- end: `0x14001a519`
- name: `WinNatFreeBindingUnderLock`
- size: `733`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000a7dc`
- `0x14000b220`
- `0x14001ae34`

## callees

- `0x14000c948`
- `0x14000c990`
- `0x14000caa0`
- `0x1400153e4`
- `0x1400190d0`
- `0x140019d64`
- `0x14001a0c8`
- `0x14001a148`
- `0x14001a23c`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001a294`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001a333`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001a294`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001a333`
- `ntoskrnl!RtlAreBitsClear` at `0x14001a37a`
- `ntoskrnl!RtlAreBitsClear` at `0x14001a37a`
- `ntoskrnl!RtlClearBits` at `0x14001a3c5`
- `ntoskrnl!RtlClearBits` at `0x14001a3c5`
- `NETIO!PtGetNumNodes` at `0x14001a2d1`
- `NETIO!PtGetNumNodes` at `0x14001a2d1`
- `NETIO!PtDeleteEntry` at `0x14001a2ee`
- `NETIO!PtDeleteEntry` at `0x14001a2ee`

## pseudocode

```c
void *__fastcall WinNatFreeBindingUnderLock(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rbp
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 BitMapForProtocol; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  _WORD *v20; // rcx
  struct _RTL_BITMAP *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // r9
  void *result; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  bool v31; // zf
  int v32; // r9d
  int v33; // r8d
  __int16 v34[16]; // [rsp+60h] [rbp-68h] BYREF
  __int16 v35[16]; // [rsp+80h] [rbp-48h] BYREF

  v3 = *(_QWORD *)(a1 + 80);
  if ( (*(_BYTE *)(a1 + 88) & 2) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  if ( (*(_BYTE *)(a1 + 88) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  RtlRemoveEntryHashTable(
    *(PRTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(a1 + 80) + 384LL),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 16),
    0);
  if ( (*(_BYTE *)(a1 + 88) & 8) != 0 )
  {
    v8 = *(_QWORD *)(a1 + 48);
    if ( !v8 || (*(_BYTE *)(v8 + 88) & 4) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7);
    if ( *(int *)(v8 + 64) <= 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v7);
    if ( (*(_BYTE *)(a1 + 88) & 0x10) == 0 )
    {
      v9 = *(_DWORD *)(v8 + 64);
      if ( (unsigned int)PtGetNumNodes(*(_QWORD *)(v8 + 16)) != v9 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10, v12);
      if ( (int)PtDeleteEntry(*(_QWORD *)(v8 + 16), a1 + 40) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13, v15);
    }
    if ( (int)--*(_DWORD *)(v8 + 64) > 0 )
    {
      v8 = 0;
      *(_QWORD *)(a1 + 48) = 0;
    }
  }
  else
  {
    v8 = a1;
  }
  if ( v8 )
  {
    RtlRemoveEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(v8 + 80) + 392LL),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v8 + 40),
      0);
    LOBYTE(v16) = *(_BYTE *)(v8 + 68);
    BitMapForProtocol = WinNatGetBitMapForProtocol(*(_QWORD *)(v8 + 72), v16);
    v20 = *(_WORD **)(v8 + 104);
    v21 = (struct _RTL_BITMAP *)BitMapForProtocol;
    if ( *v20 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v18, v19);
    v22 = *(_QWORD *)(v8 + 104);
    if ( *(_DWORD *)(v22 + 4) && RtlAreBitsClear(v21, (unsigned __int16)__ROR2__(*(_WORD *)(v22 + 2), 8), 1u) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v23, v24);
    LOBYTE(v20) = *(_BYTE *)(v8 + 68);
    v25 = WinNatDecrementPortUsage(v20, *(_QWORD *)(v8 + 72));
    if ( *(_BYTE *)(*(_QWORD *)(v8 + 72) + 124LL) && !v25 )
      SlbNatNotifyUnusedAddressEntry();
    RtlClearBits(v21, (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v8 + 104) + 2LL), 8), 1u);
  }
  if ( (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 384LL))
    || (result = (void *)WinNatHashTableRestructureRequired(*(_QWORD *)(v26 + 392)), (_BYTE)result) )
  {
    result = (void *)WinNatScheduleRestructureDpc(v3 - 768);
  }
  if ( (Microsoft_Windows_WinNatEnableBits & 4) != 0 && dword_140027104 )
  {
    v31 = (*(_BYTE *)(a1 + 88) & 4) == 0;
    memset(v35, 0, 28);
    memset(v34, 0, 28);
    if ( !v31 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v29, v28, v30);
    WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 96), v35);
    result = WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 104), v34);
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 4) != 0 )
    {
      v32 = 28;
      v33 = 28;
      if ( v34[0] == 2 )
        v33 = 16;
      if ( v35[0] == 2 )
        v32 = 16;
      result = (void *)McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer(
                         (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                         (unsigned int)WINNAT_BINDING_DELETE,
                         v33,
                         v32,
                         (__int64)v35,
                         v33,
                         (__int64)v34,
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
0x14001a23c  mov     [rsp+arg_8], rbx
0x14001a241  mov     [rsp+arg_10], rbp
0x14001a246  push    rsi
0x14001a247  push    rdi
0x14001a248  push    r14
0x14001a24a  sub     rsp, 0B0h
0x14001a251  mov     rax, cs:__security_cookie
0x14001a258  xor     rax, rsp
0x14001a25b  mov     [rsp+0C8h+var_28], rax
0x14001a263  mov     r14, [rcx+50h]
0x14001a267  xor     ebx, ebx
0x14001a269  test    byte ptr [rcx+58h], 2
0x14001a26d  mov     rsi, rcx
0x14001a270  jz      short loc_14001A277
0x14001a272  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a277  test    byte ptr [rsi+58h], 4
0x14001a27b  jz      short loc_14001A282
0x14001a27d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a282  mov     rcx, [rsi+50h]
0x14001a286  lea     rdx, [rsi+10h]; Entry
0x14001a28a  xor     r8d, r8d; Context
0x14001a28d  mov     rcx, [rcx+180h]; HashTable
0x14001a294  call    cs:__imp_RtlRemoveEntryHashTable
0x14001a29b  nop     dword ptr [rax+rax+00h]
0x14001a2a0  test    byte ptr [rsi+58h], 8
0x14001a2a4  jz      short loc_14001A315
0x14001a2a6  mov     rbp, [rsi+30h]
0x14001a2aa  test    rbp, rbp
0x14001a2ad  jz      short loc_14001A2B5
0x14001a2af  test    byte ptr [rbp+58h], 4
0x14001a2b3  jnz     short loc_14001A2BA
0x14001a2b5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a2ba  cmp     [rbp+40h], ebx
0x14001a2bd  jg      short loc_14001A2C4
0x14001a2bf  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a2c4  test    byte ptr [rsi+58h], 10h
0x14001a2c8  jnz     short loc_14001A303
0x14001a2ca  mov     rcx, [rbp+10h]
0x14001a2ce  mov     edi, [rbp+40h]
0x14001a2d1  call    cs:__imp_PtGetNumNodes
0x14001a2d8  nop     dword ptr [rax+rax+00h]
0x14001a2dd  cmp     eax, edi
0x14001a2df  jz      short loc_14001A2E6
0x14001a2e1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a2e6  mov     rcx, [rbp+10h]
0x14001a2ea  lea     rdx, [rsi+28h]
0x14001a2ee  call    cs:__imp_PtDeleteEntry
0x14001a2f5  nop     dword ptr [rax+rax+00h]
0x14001a2fa  test    eax, eax
0x14001a2fc  jns     short loc_14001A303
0x14001a2fe  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a303  dec     dword ptr [rbp+40h]
0x14001a306  mov     eax, [rbp+40h]
0x14001a309  test    eax, eax
0x14001a30b  jle     short loc_14001A318
0x14001a30d  xor     ebp, ebp
0x14001a30f  mov     [rsi+30h], rbx
0x14001a313  jmp     short loc_14001A318
0x14001a315  mov     rbp, rsi
0x14001a318  test    rbp, rbp
0x14001a31b  jz      loc_14001A3D1
0x14001a321  mov     rcx, [rbp+50h]
0x14001a325  lea     rdx, [rbp+28h]; Entry
0x14001a329  xor     r8d, r8d; Context
0x14001a32c  mov     rcx, [rcx+188h]; HashTable
0x14001a333  call    cs:__imp_RtlRemoveEntryHashTable
0x14001a33a  nop     dword ptr [rax+rax+00h]
0x14001a33f  mov     dl, [rbp+44h]
0x14001a342  mov     rcx, [rbp+48h]
0x14001a346  call    WinNatGetBitMapForProtocol
0x14001a34b  mov     rcx, [rbp+68h]
0x14001a34f  mov     rdi, rax
0x14001a352  cmp     word ptr [rcx], 2
0x14001a356  jz      short loc_14001A35D
0x14001a358  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a35d  mov     rax, [rbp+68h]
0x14001a361  cmp     [rax+4], ebx
0x14001a364  jz      short loc_14001A38F
0x14001a366  movzx   eax, word ptr [rax+2]
0x14001a36a  mov     r8d, 1; Length
0x14001a370  ror     ax, 8
0x14001a374  mov     rcx, rdi; BitMapHeader
0x14001a377  movzx   edx, ax; StartingIndex
0x14001a37a  call    cs:__imp_RtlAreBitsClear
0x14001a381  nop     dword ptr [rax+rax+00h]
0x14001a386  test    al, al
0x14001a388  jz      short loc_14001A38F
0x14001a38a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a38f  mov     rdx, [rbp+48h]
0x14001a393  mov     cl, [rbp+44h]
0x14001a396  call    WinNatDecrementPortUsage
0x14001a39b  mov     rcx, [rbp+48h]
0x14001a39f  cmp     [rcx+7Ch], bl
0x14001a3a2  jz      short loc_14001A3AD
0x14001a3a4  test    eax, eax
0x14001a3a6  jnz     short loc_14001A3AD
0x14001a3a8  call    SlbNatNotifyUnusedAddressEntry
0x14001a3ad  mov     rax, [rbp+68h]
0x14001a3b1  mov     r8d, 1; NumberToClear
0x14001a3b7  movzx   ecx, word ptr [rax+2]
0x14001a3bb  ror     cx, 8
0x14001a3bf  movzx   edx, cx; StartingIndex
0x14001a3c2  mov     rcx, rdi; BitMapHeader
0x14001a3c5  call    cs:__imp_RtlClearBits
0x14001a3cc  nop     dword ptr [rax+rax+00h]
0x14001a3d1  mov     r9, [rsi+50h]
0x14001a3d5  mov     rcx, [r9+180h]
0x14001a3dc  call    WinNatHashTableRestructureRequired
0x14001a3e1  test    al, al
0x14001a3e3  jnz     short loc_14001A3F5
0x14001a3e5  mov     rcx, [r9+188h]
0x14001a3ec  call    WinNatHashTableRestructureRequired
0x14001a3f1  test    al, al
0x14001a3f3  jz      short loc_14001A401
0x14001a3f5  lea     rcx, [r14-300h]
0x14001a3fc  call    WinNatScheduleRestructureDpc
0x14001a401  test    cs:Microsoft_Windows_WinNatEnableBits, 4
0x14001a408  jz      loc_14001A4EC
0x14001a40e  cmp     cs:dword_140027104, ebx
0x14001a414  jz      loc_14001A4EC
0x14001a41a  xorps   xmm0, xmm0
0x14001a41d  xorps   xmm1, xmm1
0x14001a420  xor     eax, eax
0x14001a422  test    byte ptr [rsi+58h], 4
0x14001a426  movups  xmmword ptr [rsp+0C8h+var_48], xmm0
0x14001a42e  movups  xmmword ptr [rsp+0C8h+var_68], xmm1
0x14001a433  movups  xmmword ptr [rsp+0C8h+var_48+0Ch], xmm0
0x14001a43b  movups  xmmword ptr [rsp+0C8h+var_68+0Ch], xmm1
0x14001a440  jz      short loc_14001A447
0x14001a442  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a447  mov     rcx, [rsi+60h]
0x14001a44b  lea     rdx, [rsp+0C8h+var_48]
0x14001a453  call    WinNatCopyTransportAddrToSockAddr
0x14001a458  mov     rcx, [rsi+68h]
0x14001a45c  lea     rdx, [rsp+0C8h+var_68]
0x14001a461  call    WinNatCopyTransportAddrToSockAddr
0x14001a466  cmp     cs:dword_140027104, 1
0x14001a46d  jnz     short loc_14001A4EC
0x14001a46f  test    cs:Microsoft_Windows_WinNatEnableBits, 4
0x14001a476  jz      short loc_14001A4EC
0x14001a478  cmp     [rsp+0C8h+var_68], 2
0x14001a47e  mov     r9d, 1Ch
0x14001a484  movzx   ecx, byte ptr [rsi+58h]
0x14001a488  mov     r8d, r9d
0x14001a48b  movzx   edx, byte ptr [rsi+44h]
0x14001a48f  lea     eax, [r9-0Ch]
0x14001a493  cmovz   r8d, eax
0x14001a497  cmp     [rsp+0C8h+var_48], 2
0x14001a4a0  cmovz   r9d, eax
0x14001a4a4  mov     eax, [rsi+5Ch]
0x14001a4a7  mov     [rsp+0C8h+var_78], eax
0x14001a4ab  and     ecx, 1
0x14001a4ae  mov     eax, [rsi+40h]
0x14001a4b1  mov     [rsp+0C8h+var_80], ecx
0x14001a4b5  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001a4bc  mov     [rsp+0C8h+var_88], eax
0x14001a4c0  lea     rax, [rsp+0C8h+var_68]
0x14001a4c5  mov     [rsp+0C8h+var_90], edx
0x14001a4c9  lea     rdx, WINNAT_BINDING_DELETE
0x14001a4d0  mov     [rsp+0C8h+var_98], rax
0x14001a4d5  lea     rax, [rsp+0C8h+var_48]
0x14001a4dd  mov     [rsp+0C8h+var_A0], r8d
0x14001a4e2  mov     [rsp+0C8h+var_A8], rax
0x14001a4e7  call    McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer
0x14001a4ec  or      byte ptr [rsi+58h], 2
0x14001a4f0  mov     rcx, [rsp+0C8h+var_28]
0x14001a4f8  xor     rcx, rsp; StackCookie
0x14001a4fb  call    __security_check_cookie
0x14001a500  lea     r11, [rsp+0C8h+var_18]
0x14001a508  mov     rbx, [r11+28h]
0x14001a50c  mov     rbp, [r11+30h]
0x14001a510  mov     rsp, r11
0x14001a513  pop     r14
0x14001a515  pop     rdi
0x14001a516  pop     rsi
0x14001a517  retn
```
