# IppEnsureContiguousHeaders

- ea: `0x14006a030`
- end: `0x14006a441`
- name: `IppEnsureContiguousHeaders`
- size: `1041`
- prototype: `__int64 __fastcall(int, int, int, int, int, ULONG DataOffsetDelta, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140069150`

## callees

- `0x140033ef0`
- `0x140053e98`
- `0x14005b10c`
- `0x140063050`
- `0x14006a030`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a2a1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a2d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a31a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a346`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a3e1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a2a1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a2d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a31a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a346`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a3e1`
- `NETIO!NetioAllocateMdl` at `0x14006a142`
- `NETIO!NetioDereferenceNetBufferList` at `0x14006a1e2`
- `NETIO!NetioDereferenceNetBufferList` at `0x14006a1e2`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14006a3a8`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14006a3a8`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x14006a195`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x14006a195`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14006a275`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14006a275`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006a14c`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006a14c`

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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v30,
        L"retreat contiguous header (IPNG)");
    return (unsigned int)v18;
  }
  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x14006a030  push    rbx
0x14006a032  push    rbp
0x14006a033  push    rsi
0x14006a034  push    rdi
0x14006a035  push    r12
0x14006a037  push    r13
0x14006a039  push    r14
0x14006a03b  sub     rsp, 30h
0x14006a03f  mov     ebp, [rsp+68h+arg_20]
0x14006a046  xor     r12d, r12d
0x14006a049  mov     r13, [rdx+8]
0x14006a04d  mov     esi, r9d
0x14006a050  mov     rdi, r8
0x14006a053  mov     r14, rdx
0x14006a056  test    ebp, ebp
0x14006a058  jnz     loc_14006A3EF
0x14006a05e  mov     ebx, [rsp+68h+DataOffsetDelta]
0x14006a065  mov     rcx, [r8]; NetBuffer
0x14006a068  mov     [rsp+68h+arg_0], r15
0x14006a06d  lea     edx, [r9+rbx]; DataOffsetDelta
0x14006a071  mov     eax, [rcx+10h]
0x14006a074  cmp     eax, edx
0x14006a076  jb      loc_14006A142
0x14006a07c  sub     [rcx+28h], edx
0x14006a07f  sub     eax, edx
0x14006a081  add     [rcx+18h], edx
0x14006a084  mov     [rcx+10h], eax
0x14006a087  xor     r15d, r15d
0x14006a08a  mov     r10, [rdi]
0x14006a08d  lea     eax, [r12+rsi]
0x14006a091  add     eax, ebp
0x14006a093  mov     [rsp+68h+DataOffsetDelta], eax
0x14006a09a  mov     r11, [r10+8]
0x14006a09e  lea     edx, [rax+rbx]
0x14006a0a1  lea     rax, [r10+10h]
0x14006a0a5  mov     [rsp+68h+arg_20], edx
0x14006a0ac  mov     [rsp+68h+arg_8], rax
0x14006a0b1  mov     ecx, [r11+28h]
0x14006a0b5  sub     ecx, [rax]
0x14006a0b7  cmp     ecx, edx
0x14006a0b9  jb      loc_14006A188
0x14006a0bf  test    byte ptr [r11+0Ah], 5
0x14006a0c4  jz      loc_14006A2B2
0x14006a0ca  mov     rax, [r11+18h]
0x14006a0ce  mov     rcx, [rsp+68h+arg_8]
0x14006a0d3  mov     r10, [rdi]
0x14006a0d6  mov     ecx, [rcx]
0x14006a0d8  add     rcx, rax
0x14006a0db  jz      loc_14006A188
0x14006a0e1  test    ebx, ebx
0x14006a0e3  jz      short loc_14006A104
0x14006a0e5  mov     rax, [r10+8]
0x14006a0e9  mov     ecx, [r10+10h]
0x14006a0ed  add     ecx, ebx
0x14006a0ef  cmp     ecx, [rax+28h]
0x14006a0f2  jnb     loc_14006A26A
0x14006a0f8  add     [r10+28h], ebx
0x14006a0fc  sub     [r10+18h], ebx
0x14006a100  mov     [r10+10h], ecx
0x14006a104  mov     rbx, [rdi]
0x14006a107  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14006a10b  test    byte ptr [rcx+0Ah], 5
0x14006a10f  jz      loc_14006A286
0x14006a115  mov     rax, [rcx+18h]
0x14006a119  mov     ecx, [rbx+10h]
0x14006a11c  add     rcx, rax
0x14006a11f  mov     rax, [rsp+68h+arg_30]
0x14006a127  mov     [rax], rcx
0x14006a12a  mov     eax, r15d
0x14006a12d  mov     r15, [rsp+68h+arg_0]
0x14006a132  add     rsp, 30h
0x14006a136  pop     r14
0x14006a138  pop     r13
0x14006a13a  pop     r12
0x14006a13c  pop     rdi
0x14006a13d  pop     rsi
0x14006a13e  pop     rbp
0x14006a13f  pop     rbx
0x14006a140  retn
0x14006a142  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14006a149  xor     r8d, r8d; DataBackFill
0x14006a14c  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006a153  nop     dword ptr [rax+rax+00h]
0x14006a158  mov     r15d, eax
0x14006a15b  test    eax, eax
0x14006a15d  jns     loc_14006A08A
0x14006a163  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x14006a16a  jge     short loc_14006A12A
0x14006a16c  lea     r9, aRetreatContigu; "retreat contiguous header (IPNG)"
0x14006a173  lea     rdx, TCPIP_MEMORY_FAILURES
0x14006a17a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14006a181  call    McTemplateK0z_EtwWriteTransfer
0x14006a186  jmp     short loc_14006A12A
0x14006a188  mov     rcx, r10
0x14006a18b  call    NetioAdvanceNetBuffer
0x14006a190  xor     edx, edx
0x14006a192  mov     rcx, r13
0x14006a195  call    cs:__imp_NetioAllocateAndReferenceCloneNetBufferList
0x14006a19c  nop     dword ptr [rax+rax+00h]
0x14006a1a1  mov     [rsp+68h+arg_10], rax
0x14006a1a9  mov     r10, rax
0x14006a1ac  test    rax, rax
0x14006a1af  jz      loc_14006A2E8
0x14006a1b5  mov     rdx, r13
0x14006a1b8  mov     rcx, rax
0x14006a1bb  call    IppCopyNetBufferListInfo
0x14006a1c0  mov     [r14+8], r10
0x14006a1c4  mov     rax, [r10+8]
0x14006a1c8  mov     r14, [r13+8]
0x14006a1cc  test    r14, r14
0x14006a1cf  jz      short loc_14006A1DD
0x14006a1d1  cmp     [rdi], r14
0x14006a1d4  jnz     loc_14006A436
0x14006a1da  mov     [rdi], rax
0x14006a1dd  xor     edx, edx
0x14006a1df  mov     rcx, r13
0x14006a1e2  call    cs:__imp_NetioDereferenceNetBufferList
0x14006a1e9  nop     dword ptr [rax+rax+00h]
0x14006a1ee  mov     edx, [rsp+68h+DataOffsetDelta]
0x14006a1f5  mov     r8d, ebx
0x14006a1f8  mov     rcx, [rdi]
0x14006a1fb  call    NetioRetreatNetBuffer
0x14006a200  mov     r15d, eax
0x14006a203  test    eax, eax
0x14006a205  js      loc_14006A163
0x14006a20b  test    ebp, ebp
0x14006a20d  jnz     loc_14006A357
0x14006a213  mov     rbx, [rdi]
0x14006a216  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14006a21a  test    byte ptr [rcx+0Ah], 5
0x14006a21e  jz      loc_14006A2FF
0x14006a224  mov     rax, [rcx+18h]
0x14006a228  mov     ecx, [rbx+10h]
0x14006a22b  mov     rbx, [rsp+68h+arg_10]
0x14006a233  add     rcx, rax
0x14006a236  mov     rax, [rsp+68h+arg_30]
0x14006a23e  mov     rbx, [rbx+8]
0x14006a242  mov     [rax], rcx
0x14006a245  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14006a249  test    byte ptr [rcx+0Ah], 5
0x14006a24d  jz      loc_14006A32B
0x14006a253  mov     rax, [rcx+18h]
0x14006a257  mov     ecx, [rbx+10h]
0x14006a25a  add     rcx, rax
0x14006a25d  mov     rax, [rsp+68h+arg_38]
0x14006a265  jmp     loc_14006A127
0x14006a26a  xor     r9d, r9d; FreeMdlHandler
0x14006a26d  xor     r8d, r8d; FreeMdl
0x14006a270  mov     edx, ebx; DataOffsetDelta
0x14006a272  mov     rcx, r10; NetBuffer
0x14006a275  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14006a27c  nop     dword ptr [rax+rax+00h]
0x14006a281  jmp     loc_14006A104
0x14006a286  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a28e  xor     r9d, r9d; RequestedAddress
0x14006a291  xor     edx, edx; AccessMode
0x14006a293  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a29b  mov     r8d, 1; CacheType
0x14006a2a1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a2a8  nop     dword ptr [rax+rax+00h]
0x14006a2ad  jmp     loc_14006A119
0x14006a2b2  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a2ba  xor     r9d, r9d; RequestedAddress
0x14006a2bd  xor     edx, edx; AccessMode
0x14006a2bf  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a2c7  mov     r8d, 1; CacheType
0x14006a2cd  mov     rcx, r11; MemoryDescriptorList
0x14006a2d0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a2d7  nop     dword ptr [rax+rax+00h]
0x14006a2dc  mov     edx, [rsp+68h+arg_20]
0x14006a2e3  jmp     loc_14006A0CE
0x14006a2e8  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x14006a2ef  jl      loc_14006A417
0x14006a2f5  mov     eax, 0C000009Ah
0x14006a2fa  jmp     loc_14006A12D
0x14006a2ff  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a307  xor     r9d, r9d; RequestedAddress
0x14006a30a  xor     edx, edx; AccessMode
0x14006a30c  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a314  mov     r8d, 1; CacheType
0x14006a31a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a321  nop     dword ptr [rax+rax+00h]
0x14006a326  jmp     loc_14006A228
0x14006a32b  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a333  xor     r9d, r9d; RequestedAddress
0x14006a336  xor     edx, edx; AccessMode
0x14006a338  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a340  mov     r8d, 1; CacheType
0x14006a346  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a34d  nop     dword ptr [rax+rax+00h]
0x14006a352  jmp     loc_14006A257
0x14006a357  mov     rcx, [rdi]
0x14006a35a  mov     edx, esi
0x14006a35c  call    NetioAdvanceNetBuffer
0x14006a361  lea     ebx, [r12+rbp]
0x14006a365  xor     r8d, r8d
0x14006a368  mov     edx, ebx
0x14006a36a  mov     rcx, r14
0x14006a36d  call    NetioRetreatNetBuffer
0x14006a372  mov     rbp, [rdi]
0x14006a375  mov     rcx, [rbp+8]; MemoryDescriptorList
0x14006a379  test    byte ptr [rcx+0Ah], 5
0x14006a37d  jz      short loc_14006A3C6
0x14006a37f  mov     rax, [rcx+18h]
0x14006a383  mov     r8d, [rbp+10h]
0x14006a387  mov     edx, [r14+28h]
0x14006a38b  add     r8, rax
0x14006a38e  mov     rcx, [r14+20h]
0x14006a392  lea     rax, [rsp+68h+arg_8]
0x14006a397  mov     r9d, ebx
0x14006a39a  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x14006a39f  mov     [rsp+68h+arg_8], 0
0x14006a3a8  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14006a3af  nop     dword ptr [rax+rax+00h]
0x14006a3b4  mov     rcx, [rdi]
0x14006a3b7  xor     r8d, r8d
0x14006a3ba  mov     edx, esi
0x14006a3bc  call    NetioRetreatNetBuffer
0x14006a3c1  jmp     loc_14006A213
0x14006a3c6  mov     [rsp+68h+Priority], 40000000h; Priority
0x14006a3ce  xor     r9d, r9d; RequestedAddress
0x14006a3d1  xor     edx, edx; AccessMode
0x14006a3d3  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006a3db  mov     r8d, 1; CacheType
0x14006a3e1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a3e8  nop     dword ptr [rax+rax+00h]
0x14006a3ed  jmp     short loc_14006A383
0x14006a3ef  lea     rax, Ipv6Global
0x14006a3f6  cmp     rcx, rax
0x14006a3f9  jnz     loc_14006A05E
0x14006a3ff  movzx   eax, word ptr [rdx+32h]
0x14006a403  movzx   r12d, word ptr [rdx+34h]
0x14006a408  add     r12d, eax
0x14006a40b  movzx   eax, word ptr [rdx+30h]
0x14006a40f  add     r12d, eax
0x14006a412  jmp     loc_14006A05E
0x14006a417  lea     r9, aCloneForContig; "clone for contiguous header (IPNG)"
0x14006a41e  lea     rdx, TCPIP_MEMORY_FAILURES
0x14006a425  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14006a42c  call    McTemplateK0z_EtwWriteTransfer
0x14006a431  jmp     loc_14006A2F5
0x14006a436  mov     r14, [r14]
0x14006a439  mov     rax, [rax]
0x14006a43c  jmp     loc_14006A1CC
```
