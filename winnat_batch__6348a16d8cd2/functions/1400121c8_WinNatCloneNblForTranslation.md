# WinNatCloneNblForTranslation

- ea: `0x1400121c8`
- end: `0x140012470`
- name: `WinNatCloneNblForTranslation`
- size: `680`
- prototype: `__int64 __fastcall(NET_BUFFER_LIST *originalNetBufferList, ULONG DataOffsetDelta)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001bf20`
- `0x14001d310`
- `0x14001d87c`
- `0x14001dd2c`
- `0x14001defc`
- `0x14001e2a0`

## callees

- `0x14000caa0`
- `0x14000e488`
- `0x140011c8c`
- `0x1400121c8`

## import_xrefs

- `NDIS!NdisAllocateNetBufferListContext` at `0x1400122ab`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400123c2`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400122ab`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400123c2`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001224e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001224e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400122f0`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001230e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400122f0`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001230e`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14001245f`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14001245f`
- `fwpkclnt!FwpsAllocateCloneNetBufferList0` at `0x14001236f`
- `fwpkclnt!FwpsAllocateCloneNetBufferList0` at `0x14001236f`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x140012287`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x140012287`
- `fwpkclnt!FwpsAllocateNetBufferAndNetBufferList0` at `0x140012210`
- `fwpkclnt!FwpsAllocateNetBufferAndNetBufferList0` at `0x140012210`

## pseudocode

```c
NET_BUFFER_LIST *__fastcall WinNatCloneNblForTranslation(NET_BUFFER_LIST *originalNetBufferList, ULONG DataOffsetDelta)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  const wchar_t *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  const wchar_t *v9; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  UCHAR *v13; // rbx
  UCHAR *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  NET_BUFFER_LIST *netBufferList; // [rsp+50h] [rbp+10h] BYREF

  netBufferList = 0;
  if ( originalNetBufferList )
  {
    if ( DataOffsetDelta >= 0x78 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( FwpsAllocateCloneNetBufferList0(originalNetBufferList, WinNatNdisNblPoolHandle, 0, 0, &netBufferList) < 0 )
    {
      if ( dword_140026104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        return 0;
      v6 = L"NBL clone failed";
LABEL_28:
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v4, v5, v6);
      return 0;
    }
    if ( NdisAllocateNetBufferListContext(netBufferList, 0x10u, 0, 0x626E4E57u) < 0 )
    {
      if ( dword_140026104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        goto LABEL_11;
      v9 = L"NBL context allocation failed";
      goto LABEL_10;
    }
    v14 = &netBufferList->Context->ContextData[netBufferList->Context->Offset];
    if ( !v14 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    *v14 &= ~1u;
    if ( DataOffsetDelta && (int)WinNatAddBackFillToNetBuffer(netBufferList->FirstNetBuffer, DataOffsetDelta) < 0 )
    {
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
        McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v15, v16, L"MDL pool allocation failed");
      FwpsFreeCloneNetBufferList0(netBufferList, 0);
      return 0;
    }
  }
  else
  {
    if ( FwpsAllocateNetBufferAndNetBufferList0(WinNatNdisNblPoolHandle, 0, 0, 0, 0, 0, &netBufferList) < 0 )
    {
      if ( dword_140026104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        return 0;
      v6 = L"NBL allocation failed";
      goto LABEL_28;
    }
    if ( NdisRetreatNetBufferDataStart(netBufferList->FirstNetBuffer, DataOffsetDelta, 0, 0) < 0 )
    {
      if ( dword_140026104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        goto LABEL_11;
      v9 = L"NBL retreat failed";
LABEL_10:
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v7, v8, v9);
LABEL_11:
      FwpsFreeNetBufferList0(netBufferList);
      return 0;
    }
    if ( NdisAllocateNetBufferListContext(netBufferList, 0x10u, 0, 0x626E4E57u) < 0 )
    {
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          v11,
          v12,
          L"NBL context allocation failed");
      NdisAdvanceNetBufferDataStart(netBufferList->FirstNetBuffer, DataOffsetDelta, 1u, 0);
      goto LABEL_11;
    }
    NdisAdvanceNetBufferDataStart(netBufferList->FirstNetBuffer, DataOffsetDelta, 0, 0);
    v13 = &netBufferList->Context->ContextData[netBufferList->Context->Offset];
    if ( !v13 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    *v13 |= 1u;
  }
  return netBufferList;
}

```

## disassembly

```asm
0x1400121c8  mov     r11, rsp
0x1400121cb  mov     [r11+10h], rbx
0x1400121cf  mov     [r11+18h], rdi
0x1400121d3  push    rbp
0x1400121d4  mov     rbp, rsp
0x1400121d7  sub     rsp, 40h
0x1400121db  mov     [rbp+netBufferList], 0
0x1400121e3  mov     ebx, edx
0x1400121e5  mov     rdi, rcx
0x1400121e8  test    rcx, rcx
0x1400121eb  jnz     loc_14001234C
0x1400121f1  mov     rcx, cs:WinNatNdisNblPoolHandle; poolHandle
0x1400121f8  lea     rax, [rbp+netBufferList]
0x1400121fc  xor     edx, edx; contextSize
0x1400121fe  mov     [r11-18h], rax
0x140012202  mov     [r11-20h], rdx
0x140012206  xor     r8d, r8d; contextBackFill
0x140012209  xor     r9d, r9d; mdlChain
0x14001220c  mov     [rsp+40h+dataOffset], edx; dataOffset
0x140012210  call    cs:__imp_FwpsAllocateNetBufferAndNetBufferList0
0x140012217  nop     dword ptr [rax+rax+00h]
0x14001221c  test    eax, eax
0x14001221e  jns     short loc_14001223E
0x140012220  cmp     cs:dword_140026104, 1
0x140012227  jnz     short loc_140012293
0x140012229  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012230  jz      short loc_140012293
0x140012232  lea     r9, aNblAllocationF; "NBL allocation failed"
0x140012239  jmp     loc_1400123A0
0x14001223e  mov     rcx, [rbp+netBufferList]
0x140012242  xor     r9d, r9d; AllocateMdlHandler
0x140012245  xor     r8d, r8d; DataBackFill
0x140012248  mov     edx, ebx; DataOffsetDelta
0x14001224a  mov     rcx, [rcx+8]; NetBuffer
0x14001224e  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140012255  nop     dword ptr [rax+rax+00h]
0x14001225a  test    eax, eax
0x14001225c  jns     short loc_14001229A
0x14001225e  cmp     cs:dword_140026104, 1
0x140012265  jnz     short loc_140012283
0x140012267  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14001226e  jz      short loc_140012283
0x140012270  lea     r9, aNblRetreatFail; "NBL retreat failed"
0x140012277  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001227e  call    McTemplateK0z_EtwWriteTransfer
0x140012283  mov     rcx, [rbp+netBufferList]; netBufferList
0x140012287  call    cs:__imp_FwpsFreeNetBufferList0
0x14001228e  nop     dword ptr [rax+rax+00h]
0x140012293  xor     eax, eax
0x140012295  jmp     loc_14001233B
0x14001229a  mov     rcx, [rbp+netBufferList]; NetBufferList
0x14001229e  xor     r8d, r8d; ContextBackFill
0x1400122a1  mov     r9d, 626E4E57h; PoolTag
0x1400122a7  lea     edx, [r8+10h]; ContextSize
0x1400122ab  call    cs:__imp_NdisAllocateNetBufferListContext
0x1400122b2  nop     dword ptr [rax+rax+00h]
0x1400122b7  test    eax, eax
0x1400122b9  jns     short loc_1400122FE
0x1400122bb  cmp     cs:dword_140026104, 1
0x1400122c2  jnz     short loc_1400122E0
0x1400122c4  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x1400122cb  jz      short loc_1400122E0
0x1400122cd  lea     r9, aNblContextAllo; "NBL context allocation failed"
0x1400122d4  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400122db  call    McTemplateK0z_EtwWriteTransfer
0x1400122e0  mov     rcx, [rbp+netBufferList]
0x1400122e4  xor     r9d, r9d; FreeMdlHandler
0x1400122e7  mov     r8b, 1; FreeMdl
0x1400122ea  mov     edx, ebx; DataOffsetDelta
0x1400122ec  mov     rcx, [rcx+8]; NetBuffer
0x1400122f0  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400122f7  nop     dword ptr [rax+rax+00h]
0x1400122fc  jmp     short loc_140012283
0x1400122fe  mov     rcx, [rbp+netBufferList]
0x140012302  xor     r9d, r9d; FreeMdlHandler
0x140012305  xor     r8d, r8d; FreeMdl
0x140012308  mov     edx, ebx; DataOffsetDelta
0x14001230a  mov     rcx, [rcx+8]; NetBuffer
0x14001230e  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140012315  nop     dword ptr [rax+rax+00h]
0x14001231a  mov     rax, [rbp+netBufferList]
0x14001231e  mov     rcx, [rax+10h]
0x140012322  movzx   eax, word ptr [rcx+0Ah]
0x140012326  lea     rbx, [rcx+10h]
0x14001232a  add     rbx, rax
0x14001232d  jnz     short loc_140012334
0x14001232f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012334  or      byte ptr [rbx], 1
0x140012337  mov     rax, [rbp+netBufferList]
0x14001233b  mov     rbx, [rsp+40h+arg_8]
0x140012340  mov     rdi, [rsp+40h+arg_10]
0x140012345  add     rsp, 40h
0x140012349  pop     rbp
0x14001234a  retn
0x14001234c  cmp     ebx, 78h ; 'x'
0x14001234f  jb      short loc_140012356
0x140012351  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012356  mov     rdx, cs:WinNatNdisNblPoolHandle; netBufferListPoolHandle
0x14001235d  lea     rax, [rbp+netBufferList]
0x140012361  xor     r9d, r9d; allocateCloneFlags
0x140012364  mov     qword ptr [rsp+40h+dataOffset], rax; netBufferList
0x140012369  xor     r8d, r8d; netBufferPoolHandle
0x14001236c  mov     rcx, rdi; originalNetBufferList
0x14001236f  call    cs:__imp_FwpsAllocateCloneNetBufferList0
0x140012376  nop     dword ptr [rax+rax+00h]
0x14001237b  test    eax, eax
0x14001237d  jns     short loc_1400123B1
0x14001237f  cmp     cs:dword_140026104, 1
0x140012386  jnz     loc_140012293
0x14001238c  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012393  jz      loc_140012293
0x140012399  lea     r9, aNblCloneFailed; "NBL clone failed"
0x1400123a0  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400123a7  call    McTemplateK0z_EtwWriteTransfer
0x1400123ac  jmp     loc_140012293
0x1400123b1  mov     rcx, [rbp+netBufferList]; NetBufferList
0x1400123b5  xor     r8d, r8d; ContextBackFill
0x1400123b8  mov     r9d, 626E4E57h; PoolTag
0x1400123be  lea     edx, [r8+10h]; ContextSize
0x1400123c2  call    cs:__imp_NdisAllocateNetBufferListContext
0x1400123c9  nop     dword ptr [rax+rax+00h]
0x1400123ce  test    eax, eax
0x1400123d0  jns     short loc_1400123F8
0x1400123d2  cmp     cs:dword_140026104, 1
0x1400123d9  jnz     loc_140012283
0x1400123df  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x1400123e6  jz      loc_140012283
0x1400123ec  lea     r9, aNblContextAllo; "NBL context allocation failed"
0x1400123f3  jmp     loc_140012277
0x1400123f8  mov     rax, [rbp+netBufferList]
0x1400123fc  mov     rcx, [rax+10h]
0x140012400  movzx   eax, word ptr [rcx+0Ah]
0x140012404  lea     rdi, [rcx+10h]
0x140012408  add     rdi, rax
0x14001240b  jnz     short loc_140012412
0x14001240d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012412  and     byte ptr [rdi], 0FEh
0x140012415  test    ebx, ebx
0x140012417  jz      loc_140012337
0x14001241d  mov     rcx, [rbp+netBufferList]
0x140012421  mov     edx, ebx; DataOffsetDelta
0x140012423  mov     rcx, [rcx+8]; NetBuffer
0x140012427  call    WinNatAddBackFillToNetBuffer
0x14001242c  test    eax, eax
0x14001242e  jns     loc_140012337
0x140012434  cmp     cs:dword_140026104, 1
0x14001243b  jnz     short loc_140012459
0x14001243d  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012444  jz      short loc_140012459
0x140012446  lea     r9, aMdlPoolAllocat; "MDL pool allocation failed"
0x14001244d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140012454  call    McTemplateK0z_EtwWriteTransfer
0x140012459  mov     rcx, [rbp+netBufferList]; netBufferList
0x14001245d  xor     edx, edx; freeCloneFlags
0x14001245f  call    cs:__imp_FwpsFreeCloneNetBufferList0
0x140012466  nop     dword ptr [rax+rax+00h]
0x14001246b  jmp     loc_140012293
```
