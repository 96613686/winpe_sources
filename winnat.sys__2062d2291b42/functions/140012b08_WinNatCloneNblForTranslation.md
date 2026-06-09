# WinNatCloneNblForTranslation

- ea: `0x140012b08`
- end: `0x140012db0`
- name: `WinNatCloneNblForTranslation`
- size: `680`
- prototype: `NET_BUFFER_LIST *__fastcall(NET_BUFFER_LIST *originalNetBufferList, __int64 DataOffsetDelta, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c400`
- `0x14001d7f0`
- `0x14001dd5c`
- `0x14001e20c`
- `0x14001e3dc`
- `0x14001e7d8`

## callees

- `0x14000caa0`
- `0x14000e4b0`
- `0x1400125cc`
- `0x140012b08`

## import_xrefs

- `NDIS!NdisAllocateNetBufferListContext` at `0x140012beb`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140012d02`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140012beb`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140012d02`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140012b8e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140012b8e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012c30`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012c4e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012c30`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012c4e`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x140012d9f`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x140012d9f`
- `fwpkclnt!FwpsAllocateCloneNetBufferList0` at `0x140012caf`
- `fwpkclnt!FwpsAllocateCloneNetBufferList0` at `0x140012caf`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x140012bc7`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x140012bc7`
- `fwpkclnt!FwpsAllocateNetBufferAndNetBufferList0` at `0x140012b50`
- `fwpkclnt!FwpsAllocateNetBufferAndNetBufferList0` at `0x140012b50`

## pseudocode

```c
NET_BUFFER_LIST *__fastcall WinNatCloneNblForTranslation(
        NET_BUFFER_LIST *originalNetBufferList,
        __int64 DataOffsetDelta,
        __int64 a3)
{
  ULONG v3; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  const wchar_t *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r8
  const wchar_t *v10; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  PNET_BUFFER_LIST_CONTEXT v16; // rcx
  UCHAR *v17; // rbx
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  UCHAR *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r8
  NET_BUFFER_LIST *netBufferList; // [rsp+50h] [rbp+10h] BYREF

  netBufferList = 0;
  v3 = DataOffsetDelta;
  if ( originalNetBufferList )
  {
    if ( (unsigned int)DataOffsetDelta >= 0x78 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(originalNetBufferList, DataOffsetDelta, a3);
    if ( FwpsAllocateCloneNetBufferList0(originalNetBufferList, WinNatNdisNblPoolHandle, 0, 0, &netBufferList) < 0 )
    {
      if ( dword_140027104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        return 0;
      v7 = L"NBL clone failed";
LABEL_28:
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v5, v6, v7);
      return 0;
    }
    if ( NdisAllocateNetBufferListContext(netBufferList, 0x10u, 0, 0x626E4E57u) < 0 )
    {
      if ( dword_140027104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        goto LABEL_11;
      v10 = L"NBL context allocation failed";
      goto LABEL_10;
    }
    Context = netBufferList->Context;
    v19 = &Context->ContextData[Context->Offset];
    if ( !v19 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(Context, v8, v9);
    *v19 &= ~1u;
    if ( v3 && (int)WinNatAddBackFillToNetBuffer(netBufferList->FirstNetBuffer, v3) < 0 )
    {
      if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
        McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v20, v21, L"MDL pool allocation failed");
      FwpsFreeCloneNetBufferList0(netBufferList, 0);
      return 0;
    }
  }
  else
  {
    if ( FwpsAllocateNetBufferAndNetBufferList0(WinNatNdisNblPoolHandle, 0, 0, 0, 0, 0, &netBufferList) < 0 )
    {
      if ( dword_140027104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        return 0;
      v7 = L"NBL allocation failed";
      goto LABEL_28;
    }
    if ( NdisRetreatNetBufferDataStart(netBufferList->FirstNetBuffer, v3, 0, 0) < 0 )
    {
      if ( dword_140027104 != 1 || (Microsoft_Windows_WinNatEnableBits & 0x20) == 0 )
        goto LABEL_11;
      v10 = L"NBL retreat failed";
LABEL_10:
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v8, v9, v10);
LABEL_11:
      FwpsFreeNetBufferList0(netBufferList);
      return 0;
    }
    if ( NdisAllocateNetBufferListContext(netBufferList, 0x10u, 0, 0x626E4E57u) < 0 )
    {
      if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          v12,
          v13,
          L"NBL context allocation failed");
      NdisAdvanceNetBufferDataStart(netBufferList->FirstNetBuffer, v3, 1u, 0);
      goto LABEL_11;
    }
    NdisAdvanceNetBufferDataStart(netBufferList->FirstNetBuffer, v3, 0, 0);
    v16 = netBufferList->Context;
    v17 = &v16->ContextData[v16->Offset];
    if ( !v17 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, v14, v15);
    *v17 |= 1u;
  }
  return netBufferList;
}

```

## disassembly

```asm
0x140012b08  mov     r11, rsp
0x140012b0b  mov     [r11+10h], rbx
0x140012b0f  mov     [r11+18h], rdi
0x140012b13  push    rbp
0x140012b14  mov     rbp, rsp
0x140012b17  sub     rsp, 40h
0x140012b1b  mov     [rbp+netBufferList], 0
0x140012b23  mov     ebx, edx
0x140012b25  mov     rdi, rcx
0x140012b28  test    rcx, rcx
0x140012b2b  jnz     loc_140012C8C
0x140012b31  mov     rcx, cs:WinNatNdisNblPoolHandle; poolHandle
0x140012b38  lea     rax, [rbp+netBufferList]
0x140012b3c  xor     edx, edx; contextSize
0x140012b3e  mov     [r11-18h], rax
0x140012b42  mov     [r11-20h], rdx
0x140012b46  xor     r8d, r8d; contextBackFill
0x140012b49  xor     r9d, r9d; mdlChain
0x140012b4c  mov     [rsp+40h+dataOffset], edx; dataOffset
0x140012b50  call    cs:__imp_FwpsAllocateNetBufferAndNetBufferList0
0x140012b57  nop     dword ptr [rax+rax+00h]
0x140012b5c  test    eax, eax
0x140012b5e  jns     short loc_140012B7E
0x140012b60  cmp     cs:dword_140027104, 1
0x140012b67  jnz     short loc_140012BD3
0x140012b69  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012b70  jz      short loc_140012BD3
0x140012b72  lea     r9, aNblAllocationF; "NBL allocation failed"
0x140012b79  jmp     loc_140012CE0
0x140012b7e  mov     rcx, [rbp+netBufferList]
0x140012b82  xor     r9d, r9d; AllocateMdlHandler
0x140012b85  xor     r8d, r8d; DataBackFill
0x140012b88  mov     edx, ebx; DataOffsetDelta
0x140012b8a  mov     rcx, [rcx+8]; NetBuffer
0x140012b8e  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140012b95  nop     dword ptr [rax+rax+00h]
0x140012b9a  test    eax, eax
0x140012b9c  jns     short loc_140012BDA
0x140012b9e  cmp     cs:dword_140027104, 1
0x140012ba5  jnz     short loc_140012BC3
0x140012ba7  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012bae  jz      short loc_140012BC3
0x140012bb0  lea     r9, aNblRetreatFail; "NBL retreat failed"
0x140012bb7  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140012bbe  call    McTemplateK0z_EtwWriteTransfer
0x140012bc3  mov     rcx, [rbp+netBufferList]; netBufferList
0x140012bc7  call    cs:__imp_FwpsFreeNetBufferList0
0x140012bce  nop     dword ptr [rax+rax+00h]
0x140012bd3  xor     eax, eax
0x140012bd5  jmp     loc_140012C7B
0x140012bda  mov     rcx, [rbp+netBufferList]; NetBufferList
0x140012bde  xor     r8d, r8d; ContextBackFill
0x140012be1  mov     r9d, 626E4E57h; PoolTag
0x140012be7  lea     edx, [r8+10h]; ContextSize
0x140012beb  call    cs:__imp_NdisAllocateNetBufferListContext
0x140012bf2  nop     dword ptr [rax+rax+00h]
0x140012bf7  test    eax, eax
0x140012bf9  jns     short loc_140012C3E
0x140012bfb  cmp     cs:dword_140027104, 1
0x140012c02  jnz     short loc_140012C20
0x140012c04  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012c0b  jz      short loc_140012C20
0x140012c0d  lea     r9, aNblContextAllo; "NBL context allocation failed"
0x140012c14  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140012c1b  call    McTemplateK0z_EtwWriteTransfer
0x140012c20  mov     rcx, [rbp+netBufferList]
0x140012c24  xor     r9d, r9d; FreeMdlHandler
0x140012c27  mov     r8b, 1; FreeMdl
0x140012c2a  mov     edx, ebx; DataOffsetDelta
0x140012c2c  mov     rcx, [rcx+8]; NetBuffer
0x140012c30  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140012c37  nop     dword ptr [rax+rax+00h]
0x140012c3c  jmp     short loc_140012BC3
0x140012c3e  mov     rcx, [rbp+netBufferList]
0x140012c42  xor     r9d, r9d; FreeMdlHandler
0x140012c45  xor     r8d, r8d; FreeMdl
0x140012c48  mov     edx, ebx; DataOffsetDelta
0x140012c4a  mov     rcx, [rcx+8]; NetBuffer
0x140012c4e  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140012c55  nop     dword ptr [rax+rax+00h]
0x140012c5a  mov     rax, [rbp+netBufferList]
0x140012c5e  mov     rcx, [rax+10h]
0x140012c62  movzx   eax, word ptr [rcx+0Ah]
0x140012c66  lea     rbx, [rcx+10h]
0x140012c6a  add     rbx, rax
0x140012c6d  jnz     short loc_140012C74
0x140012c6f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012c74  or      byte ptr [rbx], 1
0x140012c77  mov     rax, [rbp+netBufferList]
0x140012c7b  mov     rbx, [rsp+40h+arg_8]
0x140012c80  mov     rdi, [rsp+40h+arg_10]
0x140012c85  add     rsp, 40h
0x140012c89  pop     rbp
0x140012c8a  retn
0x140012c8c  cmp     ebx, 78h ; 'x'
0x140012c8f  jb      short loc_140012C96
0x140012c91  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012c96  mov     rdx, cs:WinNatNdisNblPoolHandle; netBufferListPoolHandle
0x140012c9d  lea     rax, [rbp+netBufferList]
0x140012ca1  xor     r9d, r9d; allocateCloneFlags
0x140012ca4  mov     qword ptr [rsp+40h+dataOffset], rax; netBufferList
0x140012ca9  xor     r8d, r8d; netBufferPoolHandle
0x140012cac  mov     rcx, rdi; originalNetBufferList
0x140012caf  call    cs:__imp_FwpsAllocateCloneNetBufferList0
0x140012cb6  nop     dword ptr [rax+rax+00h]
0x140012cbb  test    eax, eax
0x140012cbd  jns     short loc_140012CF1
0x140012cbf  cmp     cs:dword_140027104, 1
0x140012cc6  jnz     loc_140012BD3
0x140012ccc  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012cd3  jz      loc_140012BD3
0x140012cd9  lea     r9, aNblCloneFailed; "NBL clone failed"
0x140012ce0  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140012ce7  call    McTemplateK0z_EtwWriteTransfer
0x140012cec  jmp     loc_140012BD3
0x140012cf1  mov     rcx, [rbp+netBufferList]; NetBufferList
0x140012cf5  xor     r8d, r8d; ContextBackFill
0x140012cf8  mov     r9d, 626E4E57h; PoolTag
0x140012cfe  lea     edx, [r8+10h]; ContextSize
0x140012d02  call    cs:__imp_NdisAllocateNetBufferListContext
0x140012d09  nop     dword ptr [rax+rax+00h]
0x140012d0e  test    eax, eax
0x140012d10  jns     short loc_140012D38
0x140012d12  cmp     cs:dword_140027104, 1
0x140012d19  jnz     loc_140012BC3
0x140012d1f  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012d26  jz      loc_140012BC3
0x140012d2c  lea     r9, aNblContextAllo; "NBL context allocation failed"
0x140012d33  jmp     loc_140012BB7
0x140012d38  mov     rax, [rbp+netBufferList]
0x140012d3c  mov     rcx, [rax+10h]
0x140012d40  movzx   eax, word ptr [rcx+0Ah]
0x140012d44  lea     rdi, [rcx+10h]
0x140012d48  add     rdi, rax
0x140012d4b  jnz     short loc_140012D52
0x140012d4d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012d52  and     byte ptr [rdi], 0FEh
0x140012d55  test    ebx, ebx
0x140012d57  jz      loc_140012C77
0x140012d5d  mov     rcx, [rbp+netBufferList]
0x140012d61  mov     edx, ebx; DataOffsetDelta
0x140012d63  mov     rcx, [rcx+8]; NetBuffer
0x140012d67  call    WinNatAddBackFillToNetBuffer
0x140012d6c  test    eax, eax
0x140012d6e  jns     loc_140012C77
0x140012d74  cmp     cs:dword_140027104, 1
0x140012d7b  jnz     short loc_140012D99
0x140012d7d  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140012d84  jz      short loc_140012D99
0x140012d86  lea     r9, aMdlPoolAllocat; "MDL pool allocation failed"
0x140012d8d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140012d94  call    McTemplateK0z_EtwWriteTransfer
0x140012d99  mov     rcx, [rbp+netBufferList]; netBufferList
0x140012d9d  xor     edx, edx; freeCloneFlags
0x140012d9f  call    cs:__imp_FwpsFreeCloneNetBufferList0
0x140012da6  nop     dword ptr [rax+rax+00h]
0x140012dab  jmp     loc_140012BD3
```
