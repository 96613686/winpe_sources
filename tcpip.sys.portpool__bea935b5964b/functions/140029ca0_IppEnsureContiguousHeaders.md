# IppEnsureContiguousHeaders

- ea: `0x140029ca0`
- end: `0x14002a0b1`
- name: `IppEnsureContiguousHeaders`
- size: `1041`
- prototype: `__int64 __fastcall(__int64 *, __int64, PNET_BUFFER *, unsigned int, unsigned int, ULONG DataOffsetDelta, char **, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140028dc0`

## callees

- `0x140014a08`
- `0x14001b404`
- `0x140029ca0`
- `0x140031300`
- `0x14007ef10`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f11`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f40`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f8a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029fb6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a051`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f11`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f40`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f8a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029fb6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a051`
- `NETIO!NetioAllocateMdl` at `0x140029db2`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029e52`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029e52`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14002a018`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14002a018`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x140029e05`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x140029e05`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140029ee5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140029ee5`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140029dbc`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140029dbc`

## pseudocode

```c
__int64 __fastcall IppEnsureContiguousHeaders(
        __int64 *a1,
        __int64 a2,
        PNET_BUFFER *a3,
        unsigned int a4,
        unsigned int a5,
        ULONG DataOffsetDelta,
        char **a7,
        char **a8)
{
  unsigned int v8; // ebp
  int v9; // r12d
  __int64 v10; // r13
  ULONG v14; // ebx
  struct _NET_BUFFER *v15; // rcx
  ULONG v16; // edx
  ULONG CurrentMdlOffset; // eax
  NDIS_STATUS v18; // r15d
  PNET_BUFFER v19; // r10
  PMDL CurrentMdl; // r11
  __int64 v21; // rdx
  char *MappedSystemVa; // rax
  ULONG v23; // ecx
  PNET_BUFFER v24; // rbx
  PMDL v25; // rcx
  char *v26; // rax
  char *v27; // rcx
  char **v28; // rax
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // r10
  struct _NET_BUFFER *v34; // rax
  struct _NET_BUFFER *Alignment; // r14
  PNET_BUFFER v36; // rbx
  PMDL v37; // rcx
  char *v38; // rax
  char *v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rcx
  char *v42; // rax
  unsigned int v43; // ebx
  PNET_BUFFER v44; // rbp
  PMDL v45; // rcx
  char *v46; // rax
  __int64 DataOffset; // rdx
  char *v48; // r8
  PMDL MdlChain; // rcx
  ULONG *p_CurrentMdlOffset; // [rsp+78h] [rbp+10h] BYREF
  __int64 v51; // [rsp+80h] [rbp+18h]

  v8 = a5;
  v9 = 0;
  v10 = *(_QWORD *)(a2 + 8);
  if ( a5 && a1 == &Ipv6Global )
    v9 = *(unsigned __int16 *)(a2 + 48) + *(unsigned __int16 *)(a2 + 50) + *(unsigned __int16 *)(a2 + 52);
  v14 = DataOffsetDelta;
  v15 = *a3;
  v16 = a4 + DataOffsetDelta;
  CurrentMdlOffset = (*a3)->CurrentMdlOffset;
  if ( CurrentMdlOffset < a4 + DataOffsetDelta )
  {
    v18 = NdisRetreatNetBufferDataStart(v15, v16, 0, NetioAllocateMdl);
    if ( v18 < 0 )
      goto LABEL_17;
  }
  else
  {
    v15->DataOffset -= v16;
    v15->DataLength += v16;
    v15->CurrentMdlOffset = CurrentMdlOffset - v16;
    v18 = 0;
  }
  v19 = *a3;
  DataOffsetDelta = v8 + v9 + a4;
  CurrentMdl = v19->CurrentMdl;
  v21 = DataOffsetDelta + v14;
  a5 = v21;
  p_CurrentMdlOffset = &v19->CurrentMdlOffset;
  if ( CurrentMdl->ByteCount - v19->CurrentMdlOffset >= (unsigned int)v21 )
  {
    if ( (CurrentMdl->MdlFlags & 5) != 0 )
    {
      MappedSystemVa = (char *)CurrentMdl->MappedSystemVa;
    }
    else
    {
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u);
      v21 = a5;
    }
    v19 = *a3;
    if ( &MappedSystemVa[*p_CurrentMdlOffset] )
    {
      if ( v14 )
      {
        v23 = v14 + v19->CurrentMdlOffset;
        if ( v23 >= *(_DWORD *)(v19->Link.Region + 40) )
        {
          NdisAdvanceNetBufferDataStart(*a3, v14, 0, 0);
        }
        else
        {
          v19->DataOffset += v14;
          v19->DataLength -= v14;
          v19->CurrentMdlOffset = v23;
        }
      }
      v24 = *a3;
      v25 = (*a3)->CurrentMdl;
      if ( (v25->MdlFlags & 5) != 0 )
        v26 = (char *)v25->MappedSystemVa;
      else
        v26 = (char *)MmMapLockedPagesSpecifyCache(v25, 0, MmCached, 0, 0, 0x40000000u);
      v27 = &v26[v24->CurrentMdlOffset];
      v28 = a7;
LABEL_14:
      *v28 = v27;
      return (unsigned int)v18;
    }
  }
  NetioAdvanceNetBuffer(v19, v21);
  v31 = NetioAllocateAndReferenceCloneNetBufferList(v10, 0);
  v51 = v31;
  if ( v31 )
  {
    IppCopyNetBufferListInfo(v31, v10);
    *(_QWORD *)(a2 + 8) = v33;
    v34 = *(struct _NET_BUFFER **)(v33 + 8);
    Alignment = *(struct _NET_BUFFER **)(v10 + 8);
    while ( Alignment )
    {
      if ( *a3 == Alignment )
      {
        *a3 = v34;
        break;
      }
      Alignment = (struct _NET_BUFFER *)Alignment->Link.Alignment;
      v34 = (struct _NET_BUFFER *)v34->Link.Alignment;
    }
    NetioDereferenceNetBufferList(v10, 0);
    v18 = NetioRetreatNetBuffer(*a3, DataOffsetDelta, v14);
    if ( v18 >= 0 )
    {
      if ( v8 )
      {
        NetioAdvanceNetBuffer(*a3, a4);
        v43 = v9 + v8;
        NetioRetreatNetBuffer(Alignment, v9 + v8, 0);
        v44 = *a3;
        v45 = (*a3)->CurrentMdl;
        if ( (v45->MdlFlags & 5) != 0 )
          v46 = (char *)v45->MappedSystemVa;
        else
          v46 = (char *)MmMapLockedPagesSpecifyCache(v45, 0, MmCached, 0, 0, 0x40000000u);
        DataOffset = Alignment->DataOffset;
        v48 = &v46[v44->CurrentMdlOffset];
        MdlChain = Alignment->MdlChain;
        p_CurrentMdlOffset = 0;
        RtlCopyMdlToKernelBuffer(MdlChain, DataOffset, v48, v43, &p_CurrentMdlOffset);
        NetioRetreatNetBuffer(*a3, a4, 0);
      }
      v36 = *a3;
      v37 = (*a3)->CurrentMdl;
      if ( (v37->MdlFlags & 5) != 0 )
        v38 = (char *)v37->MappedSystemVa;
      else
        v38 = (char *)MmMapLockedPagesSpecifyCache(v37, 0, MmCached, 0, 0, 0x40000000u);
      v39 = &v38[v36->CurrentMdlOffset];
      v40 = *(_QWORD *)(v51 + 8);
      *a7 = v39;
      v41 = *(_QWORD *)(v40 + 8);
      if ( (*(_BYTE *)(v41 + 10) & 5) != 0 )
        v42 = *(char **)(v41 + 24);
      else
        v42 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v41, 0, MmCached, 0, 0, 0x40000000u);
      v27 = &v42[*(unsigned int *)(v40 + 16)];
      v28 = a8;
      goto LABEL_14;
    }
LABEL_17:
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v30,
        L"retreat contiguous header (IPNG)");
    return (unsigned int)v18;
  }
  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    McTemplateK0z_EtwWriteTransfer(
      &MICROSOFT_TCPIP_PROVIDER_Context,
      TCPIP_MEMORY_FAILURES,
      v32,
      L"clone for contiguous header (IPNG)");
  return 3221225626LL;
}

```

## disassembly

```asm
0x140029ca0  push    rbx
0x140029ca2  push    rbp
0x140029ca3  push    rsi
0x140029ca4  push    rdi
0x140029ca5  push    r12
0x140029ca7  push    r13
0x140029ca9  push    r14
0x140029cab  sub     rsp, 30h
0x140029caf  mov     ebp, [rsp+68h+arg_20]
0x140029cb6  xor     r12d, r12d
0x140029cb9  mov     r13, [rdx+8]
0x140029cbd  mov     esi, r9d
0x140029cc0  mov     rdi, r8
0x140029cc3  mov     r14, rdx
0x140029cc6  test    ebp, ebp
0x140029cc8  jnz     loc_14002A05F
0x140029cce  mov     ebx, [rsp+68h+DataOffsetDelta]
0x140029cd5  mov     rcx, [r8]; NetBuffer
0x140029cd8  mov     [rsp+68h+arg_0], r15
0x140029cdd  lea     edx, [r9+rbx]; DataOffsetDelta
0x140029ce1  mov     eax, [rcx+10h]
0x140029ce4  cmp     eax, edx
0x140029ce6  jb      loc_140029DB2
0x140029cec  sub     [rcx+28h], edx
0x140029cef  sub     eax, edx
0x140029cf1  add     [rcx+18h], edx
0x140029cf4  mov     [rcx+10h], eax
0x140029cf7  xor     r15d, r15d
0x140029cfa  mov     r10, [rdi]
0x140029cfd  lea     eax, [r12+rsi]
0x140029d01  add     eax, ebp
0x140029d03  mov     [rsp+68h+DataOffsetDelta], eax
0x140029d0a  mov     r11, [r10+8]
0x140029d0e  lea     edx, [rax+rbx]
0x140029d11  lea     rax, [r10+10h]
0x140029d15  mov     [rsp+68h+arg_20], edx
0x140029d1c  mov     [rsp+68h+arg_8], rax
0x140029d21  mov     ecx, [r11+28h]
0x140029d25  sub     ecx, [rax]
0x140029d27  cmp     ecx, edx
0x140029d29  jb      loc_140029DF8
0x140029d2f  test    byte ptr [r11+0Ah], 5
0x140029d34  jz      loc_140029F22
0x140029d3a  mov     rax, [r11+18h]
0x140029d3e  mov     rcx, [rsp+68h+arg_8]
0x140029d43  mov     r10, [rdi]
0x140029d46  mov     ecx, [rcx]
0x140029d48  add     rcx, rax
0x140029d4b  jz      loc_140029DF8
0x140029d51  test    ebx, ebx
0x140029d53  jz      short loc_140029D74
0x140029d55  mov     rax, [r10+8]
0x140029d59  mov     ecx, [r10+10h]
0x140029d5d  add     ecx, ebx
0x140029d5f  cmp     ecx, [rax+28h]
0x140029d62  jnb     loc_140029EDA
0x140029d68  add     [r10+28h], ebx
0x140029d6c  sub     [r10+18h], ebx
0x140029d70  mov     [r10+10h], ecx
0x140029d74  mov     rbx, [rdi]
0x140029d77  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140029d7b  test    byte ptr [rcx+0Ah], 5
0x140029d7f  jz      loc_140029EF6
0x140029d85  mov     rax, [rcx+18h]
0x140029d89  mov     ecx, [rbx+10h]
0x140029d8c  add     rcx, rax
0x140029d8f  mov     rax, [rsp+68h+arg_30]
0x140029d97  mov     [rax], rcx
0x140029d9a  mov     eax, r15d
0x140029d9d  mov     r15, [rsp+68h+arg_0]
0x140029da2  add     rsp, 30h
0x140029da6  pop     r14
0x140029da8  pop     r13
0x140029daa  pop     r12
0x140029dac  pop     rdi
0x140029dad  pop     rsi
0x140029dae  pop     rbp
0x140029daf  pop     rbx
0x140029db0  retn
0x140029db2  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140029db9  xor     r8d, r8d; DataBackFill
0x140029dbc  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140029dc3  nop     dword ptr [rax+rax+00h]
0x140029dc8  mov     r15d, eax
0x140029dcb  test    eax, eax
0x140029dcd  jns     loc_140029CFA
0x140029dd3  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 0
0x140029dda  jge     short loc_140029D9A
0x140029ddc  lea     r9, aRetreatContigu; "retreat contiguous header (IPNG)"
0x140029de3  lea     rdx, TCPIP_MEMORY_FAILURES
0x140029dea  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140029df1  call    McTemplateK0z_EtwWriteTransfer
0x140029df6  jmp     short loc_140029D9A
0x140029df8  mov     rcx, r10
0x140029dfb  call    NetioAdvanceNetBuffer
0x140029e00  xor     edx, edx
0x140029e02  mov     rcx, r13
0x140029e05  call    cs:__imp_NetioAllocateAndReferenceCloneNetBufferList
0x140029e0c  nop     dword ptr [rax+rax+00h]
0x140029e11  mov     [rsp+68h+arg_10], rax
0x140029e19  mov     r10, rax
0x140029e1c  test    rax, rax
0x140029e1f  jz      loc_140029F58
0x140029e25  mov     rdx, r13
0x140029e28  mov     rcx, rax
0x140029e2b  call    IppCopyNetBufferListInfo
0x140029e30  mov     [r14+8], r10
0x140029e34  mov     rax, [r10+8]
0x140029e38  mov     r14, [r13+8]
0x140029e3c  test    r14, r14
0x140029e3f  jz      short loc_140029E4D
0x140029e41  cmp     [rdi], r14
0x140029e44  jnz     loc_14002A0A6
0x140029e4a  mov     [rdi], rax
0x140029e4d  xor     edx, edx
0x140029e4f  mov     rcx, r13
0x140029e52  call    cs:__imp_NetioDereferenceNetBufferList
0x140029e59  nop     dword ptr [rax+rax+00h]
0x140029e5e  mov     edx, [rsp+68h+DataOffsetDelta]
0x140029e65  mov     r8d, ebx
0x140029e68  mov     rcx, [rdi]
0x140029e6b  call    NetioRetreatNetBuffer
0x140029e70  mov     r15d, eax
0x140029e73  test    eax, eax
0x140029e75  js      loc_140029DD3
0x140029e7b  test    ebp, ebp
0x140029e7d  jnz     loc_140029FC7
0x140029e83  mov     rbx, [rdi]
0x140029e86  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140029e8a  test    byte ptr [rcx+0Ah], 5
0x140029e8e  jz      loc_140029F6F
0x140029e94  mov     rax, [rcx+18h]
0x140029e98  mov     ecx, [rbx+10h]
0x140029e9b  mov     rbx, [rsp+68h+arg_10]
0x140029ea3  add     rcx, rax
0x140029ea6  mov     rax, [rsp+68h+arg_30]
0x140029eae  mov     rbx, [rbx+8]
0x140029eb2  mov     [rax], rcx
0x140029eb5  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140029eb9  test    byte ptr [rcx+0Ah], 5
0x140029ebd  jz      loc_140029F9B
0x140029ec3  mov     rax, [rcx+18h]
0x140029ec7  mov     ecx, [rbx+10h]
0x140029eca  add     rcx, rax
0x140029ecd  mov     rax, [rsp+68h+arg_38]
0x140029ed5  jmp     loc_140029D97
0x140029eda  xor     r9d, r9d; FreeMdlHandler
0x140029edd  xor     r8d, r8d; FreeMdl
0x140029ee0  mov     edx, ebx; DataOffsetDelta
0x140029ee2  mov     rcx, r10; NetBuffer
0x140029ee5  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140029eec  nop     dword ptr [rax+rax+00h]
0x140029ef1  jmp     loc_140029D74
0x140029ef6  mov     [rsp+68h+Priority], 40000000h; Priority
0x140029efe  xor     r9d, r9d; RequestedAddress
0x140029f01  xor     edx, edx; AccessMode
0x140029f03  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140029f0b  mov     r8d, 1; CacheType
0x140029f11  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140029f18  nop     dword ptr [rax+rax+00h]
0x140029f1d  jmp     loc_140029D89
0x140029f22  mov     [rsp+68h+Priority], 40000000h; Priority
0x140029f2a  xor     r9d, r9d; RequestedAddress
0x140029f2d  xor     edx, edx; AccessMode
0x140029f2f  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140029f37  mov     r8d, 1; CacheType
0x140029f3d  mov     rcx, r11; MemoryDescriptorList
0x140029f40  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140029f47  nop     dword ptr [rax+rax+00h]
0x140029f4c  mov     edx, [rsp+68h+arg_20]
0x140029f53  jmp     loc_140029D3E
0x140029f58  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 0
0x140029f5f  jl      loc_14002A087
0x140029f65  mov     eax, 0C000009Ah
0x140029f6a  jmp     loc_140029D9D
0x140029f6f  mov     [rsp+68h+Priority], 40000000h; Priority
0x140029f77  xor     r9d, r9d; RequestedAddress
0x140029f7a  xor     edx, edx; AccessMode
0x140029f7c  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140029f84  mov     r8d, 1; CacheType
0x140029f8a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140029f91  nop     dword ptr [rax+rax+00h]
0x140029f96  jmp     loc_140029E98
0x140029f9b  mov     [rsp+68h+Priority], 40000000h; Priority
0x140029fa3  xor     r9d, r9d; RequestedAddress
0x140029fa6  xor     edx, edx; AccessMode
0x140029fa8  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140029fb0  mov     r8d, 1; CacheType
0x140029fb6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140029fbd  nop     dword ptr [rax+rax+00h]
0x140029fc2  jmp     loc_140029EC7
0x140029fc7  mov     rcx, [rdi]
0x140029fca  mov     edx, esi
0x140029fcc  call    NetioAdvanceNetBuffer
0x140029fd1  lea     ebx, [r12+rbp]
0x140029fd5  xor     r8d, r8d
0x140029fd8  mov     edx, ebx
0x140029fda  mov     rcx, r14
0x140029fdd  call    NetioRetreatNetBuffer
0x140029fe2  mov     rbp, [rdi]
0x140029fe5  mov     rcx, [rbp+8]; MemoryDescriptorList
0x140029fe9  test    byte ptr [rcx+0Ah], 5
0x140029fed  jz      short loc_14002A036
0x140029fef  mov     rax, [rcx+18h]
0x140029ff3  mov     r8d, [rbp+10h]
0x140029ff7  mov     edx, [r14+28h]
0x140029ffb  add     r8, rax
0x140029ffe  mov     rcx, [r14+20h]
0x14002a002  lea     rax, [rsp+68h+arg_8]
0x14002a007  mov     r9d, ebx
0x14002a00a  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x14002a00f  mov     [rsp+68h+arg_8], 0
0x14002a018  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14002a01f  nop     dword ptr [rax+rax+00h]
0x14002a024  mov     rcx, [rdi]
0x14002a027  xor     r8d, r8d
0x14002a02a  mov     edx, esi
0x14002a02c  call    NetioRetreatNetBuffer
0x14002a031  jmp     loc_140029E83
0x14002a036  mov     [rsp+68h+Priority], 40000000h; Priority
0x14002a03e  xor     r9d, r9d; RequestedAddress
0x14002a041  xor     edx, edx; AccessMode
0x14002a043  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002a04b  mov     r8d, 1; CacheType
0x14002a051  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002a058  nop     dword ptr [rax+rax+00h]
0x14002a05d  jmp     short loc_140029FF3
0x14002a05f  lea     rax, Ipv6Global
0x14002a066  cmp     rcx, rax
0x14002a069  jnz     loc_140029CCE
0x14002a06f  movzx   eax, word ptr [rdx+32h]
0x14002a073  movzx   r12d, word ptr [rdx+34h]
0x14002a078  add     r12d, eax
0x14002a07b  movzx   eax, word ptr [rdx+30h]
0x14002a07f  add     r12d, eax
0x14002a082  jmp     loc_140029CCE
0x14002a087  lea     r9, aCloneForContig; "clone for contiguous header (IPNG)"
0x14002a08e  lea     rdx, TCPIP_MEMORY_FAILURES
0x14002a095  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14002a09c  call    McTemplateK0z_EtwWriteTransfer
0x14002a0a1  jmp     loc_140029F65
0x14002a0a6  mov     r14, [r14]
0x14002a0a9  mov     rax, [rax]
0x14002a0ac  jmp     loc_140029E3C
```
