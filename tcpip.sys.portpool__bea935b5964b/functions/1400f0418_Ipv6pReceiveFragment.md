# Ipv6pReceiveFragment

- ea: `0x1400f0418`
- end: `0x1400f0df3`
- name: `Ipv6pReceiveFragment`
- size: `2523`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f03c0`

## callees

- `0x140014a08`
- `0x140031300`
- `0x14007ef10`
- `0x1400dcb50`
- `0x1400e44f0`
- `0x1400f0418`
- `0x1400f0dfc`
- `0x1400f1b80`
- `0x1400f1d58`
- `0x1400f201c`
- `0x1400f20b4`
- `0x1400f21f0`
- `0x1400f2248`
- `0x1400f2344`
- `0x1400f2374`
- `0x1400f27fc`
- `0x1400f3a14`
- `0x1400fb148`
- `0x14014ecd0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400f09dc`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f09dc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400f0b5f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400f0b5f`
- `ntoskrnl!ExAllocatePool3` at `0x1400f0a24`
- `ntoskrnl!ExAllocatePool3` at `0x1400f0c2d`
- `ntoskrnl!ExAllocatePool3` at `0x1400f0a24`
- `ntoskrnl!ExAllocatePool3` at `0x1400f0c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0c83`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400f0cd5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400f0d1b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400f0cd5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400f0d1b`
- `NETIO!NetioPhSkipAllIpv6Options` at `0x1400f06dd`
- `NETIO!NetioPhSkipAllIpv6Options` at `0x1400f06dd`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400f0830`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400f0830`
- `NDIS!NdisGetDataBuffer` at `0x1400f0540`
- `NDIS!NdisGetDataBuffer` at `0x1400f0540`

## pseudocode

```c
void __fastcall Ipv6pReceiveFragment(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r12
  bool v5; // zf
  struct _NET_BUFFER *v7; // r15
  __int64 v8; // r14
  __int64 LockArray_high; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // esi
  _BYTE *DataBuffer; // rax
  unsigned __int8 *v14; // rsi
  __int16 v15; // ax
  unsigned __int16 v16; // r13
  __int16 v17; // bx
  _DWORD *v18; // rcx
  __int64 v19; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  int v21; // eax
  char v22; // bl
  char v23; // r9
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rax
  KIRQL v27; // r12
  __int64 v28; // rbx
  __int64 v29; // r8
  int v30; // r10d
  _DWORD *v31; // r8
  __int64 v32; // r8
  ULONG DataLength; // ecx
  int v34; // eax
  unsigned int v35; // ecx
  unsigned int v36; // eax
  SIZE_T v37; // r13
  SIZE_T v38; // r8
  SIZE_T v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rsi
  __int64 v42; // rcx
  __int64 v43; // rdx
  ULONG v44; // edx
  __int64 v45; // r9
  struct _MDL *v46; // rcx
  int v47; // r8d
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rax
  __int16 v50; // r13
  __int64 v51; // rcx
  int v52; // eax
  __int16 v53; // ax
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // rax
  int AlignOffset; // [rsp+20h] [rbp-89h]
  unsigned __int32 v59; // [rsp+28h] [rbp-81h]
  int v60; // [rsp+30h] [rbp-79h]
  __int64 v61; // [rsp+60h] [rbp-49h] BYREF
  __int64 v62; // [rsp+68h] [rbp-41h]
  __int64 v63; // [rsp+70h] [rbp-39h]
  __int128 v64; // [rsp+78h] [rbp-31h] BYREF
  ULONG *v65; // [rsp+88h] [rbp-21h] BYREF
  _DWORD *v66; // [rsp+90h] [rbp-19h]
  __int64 v67; // [rsp+98h] [rbp-11h]
  __int64 v68; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-1h]
  _BYTE *v70; // [rsp+B0h] [rbp+7h]
  __int64 NewIrql; // [rsp+110h] [rbp+67h] BYREF
  unsigned __int16 v72; // [rsp+118h] [rbp+6Fh]
  __int64 v73; // [rsp+120h] [rbp+77h] BYREF
  PVOID P; // [rsp+128h] [rbp+7Fh] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  v5 = (*(_BYTE *)(a1 + 184) & 4) == 0;
  v63 = v4;
  LOBYTE(NewIrql) = 0;
  v7 = *(struct _NET_BUFFER **)(v4 + 8);
  v68 = 0;
  v64 = 0;
  LODWORD(v61) = 18;
  if ( !v5 )
  {
    *(_DWORD *)(v4 + 140) = -1073741250;
    return;
  }
  v62 = *(_QWORD *)(*(_QWORD *)(a1 + 216) + 8LL);
  v8 = *(_QWORD *)(*(_QWORD *)v62 + 40LL);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v10 = *(_QWORD *)(v62 + 896);
  v67 = *(_QWORD *)(v8 + 20264);
  v11 = v67;
  v66 = *(_DWORD **)(v10 + 8 * LockArray_high);
  LODWORD(v10) = *v66 + 1;
  v69 = 192 * LockArray_high;
  *v66 = v10;
  ++*(_DWORD *)(v11 + 192 * LockArray_high + 132);
  if ( (*(_BYTE *)(a1 + 184) & 8) != 0 && !*(_BYTE *)(v8 + 19727) )
  {
    v12 = 16;
LABEL_73:
    v42 = v69;
    v43 = v67;
    ++v66[2];
    ++*(_DWORD *)(v43 + v42 + 140);
    goto LABEL_97;
  }
  if ( (*(_BYTE *)(a1 + 185) & 4) != 0 )
  {
    v12 = 15;
    LOBYTE(v60) = 0;
    v59 = _byteswap_ulong(*(_DWORD *)(a1 + 48));
LABEL_8:
    LOBYTE(AlignOffset) = 0;
LABEL_9:
    LOBYTE(a4) = 4;
    IppSendError(0, &Ipv6Global, a1, a4, AlignOffset, v59, v60);
    goto LABEL_73;
  }
  DataBuffer = NdisGetDataBuffer(v7, 8u, 0, 1u, 0);
  v70 = DataBuffer;
  v14 = DataBuffer;
  if ( !DataBuffer )
  {
    v12 = 3;
    if ( v7->DataLength >= 8 )
      goto LABEL_73;
    LOBYTE(v60) = 0;
    v59 = 0x4000000;
    goto LABEL_8;
  }
  if ( !*DataBuffer )
  {
    v12 = 7;
    LOBYTE(v60) = 0;
    v59 = _byteswap_ulong(*(_DWORD *)(a1 + 48));
    LOBYTE(AlignOffset) = 1;
    goto LABEL_9;
  }
  v15 = *((_WORD *)DataBuffer + 1);
  v16 = __ROR2__(v15 & 0xF8FF, 8);
  v72 = v16;
  if ( !*(_DWORD *)(v8 + 22460) && (v16 || (v15 & 0x100) != 0) )
  {
    v12 = 1;
    goto LABEL_73;
  }
  if ( (int)IppInspectFragmentIn(
              41,
              *(_QWORD *)(a1 + 264),
              *(_QWORD *)(a1 + 216),
              *(_QWORD *)(*(_QWORD *)(a1 + 224) + 8LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 224) + 24LL),
              *(_BYTE *)(a1 + 16) & 1,
              *(_DWORD *)(a1 + 48),
              *((_DWORD *)v14 + 1),
              v16,
              v7->DataLength - 8,
              v4) >= 1 )
  {
    v12 = 2;
    goto LABEL_73;
  }
  v17 = *(_WORD *)(a1 + 48);
  NetioAdvanceNetBuffer(v7, 8);
  *(_DWORD *)(a1 + 48) += 8;
  if ( !v16 && !_bittest16((const signed __int16 *)v14 + 1, 8u) )
  {
    *(_BYTE *)(a1 + 187) |= 1u;
    v18 = v66;
    v19 = v67;
    *(_WORD *)(a1 + 290) = v17;
    ++v18[1];
    ++*(_DWORD *)(v19 + v69 + 136);
    *(_DWORD *)(a1 + 44) = *v14;
    return;
  }
  if ( (Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline(0);
  if ( IsEnabledDeviceUsageNoInline && !v16 )
  {
    v21 = *v14;
    LODWORD(P) = 0;
    v65 = 0;
    v22 = 0;
    LODWORD(v73) = v21;
    if ( (int)NetioPhSkipAllIpv6Options(v7, 0, &v73, &P) >= 0 )
    {
      if ( (unsigned int)(v73 - 50) <= 1 )
      {
        IppFindNlExtensionHeaderClient(v8, (unsigned int)v73, v4, &v65);
        v23 = 1;
      }
      else
      {
        IppFindNlFinalHeaderClient(v8, (unsigned int)v73, &v65);
      }
      if ( v65 && *v65 > v7->DataLength )
        v22 = v23;
    }
    if ( (int)NetioRetreatNetBuffer(v7, (unsigned int)P, 0) < 0 )
      __int2c();
    if ( v22 )
    {
      LOBYTE(v60) = 0;
      LOBYTE(v24) = 4;
      LOBYTE(AlignOffset) = 3;
      v12 = 17;
      IppSendError(0, &Ipv6Global, a1, v24, AlignOffset, 0, v60);
LABEL_97:
      if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredContext) & 0x10) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCPIP_IP_REASSEMBLY_DROP,
          (unsigned int)MICROSOFT_TCPIP_PROVIDER,
          v12,
          23,
          *(_DWORD *)(v62 + 8));
      v57 = *(_QWORD *)(a1 + 8);
      if ( v57 )
        *(_DWORD *)(v57 + 140) = -1073741285;
      goto LABEL_101;
    }
  }
  v25 = *((unsigned int *)v14 + 1);
  v73 = *(_QWORD *)(a1 + 280);
  v26 = Ipv6pFragmentLookup(v62, v25, v73, &NewIrql);
  v27 = NewIrql;
  v28 = v26;
  if ( v26 )
  {
    if ( *(_DWORD *)(v26 + 200) != *(_DWORD *)(*(_QWORD *)(a1 + 8) + 272LL) )
      *(_DWORD *)(v26 + 200) = 0;
  }
  else
  {
    v28 = IppCreateInReassemblySet((PKSPIN_LOCK)(v8 + 22352), NewIrql);
    if ( !v28 )
    {
      v12 = 3;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v29,
          L"IPv6 reassembly structure (IPNG)");
      goto LABEL_73;
    }
    *(_DWORD *)(v28 + 200) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 272LL);
  }
  if ( (int)WfpTransferReassemblyContextForFragments(v63, *(_QWORD *)(v28 + 208)) < 0 )
  {
    LOBYTE(NewIrql) = BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20;
    if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_IP_REASSEMBLY_WFP,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        1,
        *(_DWORD *)(v62 + 8),
        23);
  }
  v30 = v63;
  v31 = (_DWORD *)v73;
  *(_DWORD *)(v28 + 184) |= *(_DWORD *)(v63 + 136) & 0xFFF00003;
  *(_DWORD *)(v28 + 184) |= 1 << ((*v31 >> 12) & 3);
  if ( v7->DataLength + v16 > 0xFFFF )
  {
    LOBYTE(v31) = v27;
    v12 = 5;
    IppDeleteFromReassemblySet(v8 + 22352, v28, v31);
    LOBYTE(v60) = 0;
    v59 = _byteswap_ulong(*(_DWORD *)(a1 + 48) - 6);
LABEL_52:
    LOBYTE(AlignOffset) = 0;
    goto LABEL_9;
  }
  if ( (int)IPsecVerifyFragment((int)v28 + 192, v30, *(_DWORD *)(v8 + 24), (int)v31 + 8, (__int64)(v31 + 6)) < 0 )
  {
    v12 = 8;
LABEL_55:
    LOBYTE(v32) = v27;
    IppDeleteFromReassemblySet(v8 + 22352, v28, v32);
    goto LABEL_97;
  }
  DataLength = v7->DataLength;
  if ( !DataLength && (v16 || (*((_WORD *)v14 + 1) & 0x100) != 0) )
  {
    v12 = 9;
    goto LABEL_55;
  }
  if ( (*((_WORD *)v14 + 1) & 0x100) != 0 )
  {
    if ( (DataLength & 7) != 0 )
    {
      LOBYTE(v32) = v27;
      v12 = 6;
      IppDeleteFromReassemblySet(v8 + 22352, v28, v32);
      LOBYTE(v60) = 0;
      v59 = 0x4000000;
      goto LABEL_52;
    }
    v44 = *(_DWORD *)(v28 + 140);
    if ( v44 == -1 || DataLength + v16 <= v44 )
      goto LABEL_66;
LABEL_78:
    v12 = 11;
    goto LABEL_55;
  }
  v34 = *(_DWORD *)(v28 + 140);
  v32 = v16;
  v35 = v16 + DataLength;
  if ( v34 == -1 )
  {
    v36 = *(unsigned __int16 *)(v28 + 84);
    *(_DWORD *)(v28 + 140) = v35;
    if ( v36 <= v35 && *(unsigned __int16 *)(v28 + 86) <= v35 )
      goto LABEL_66;
    goto LABEL_78;
  }
  if ( v35 != v34 )
  {
    v12 = 10;
    goto LABEL_55;
  }
LABEL_66:
  NewIrql = IppReassemblyFindLocation(
              v8,
              v28,
              v16,
              *((unsigned __int16 *)&v7->NetBufferHeader.Link + 12),
              v27,
              (__int64)&v61);
  if ( !NewIrql )
  {
    v12 = v61;
    goto LABEL_97;
  }
  v37 = (MmSizeOfMdl((PVOID)0xFFF, v7->DataLength) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v38 = v37 + 16;
  if ( v37 >= 0xFFFFFFFFFFFFFFF0uLL )
    goto LABEL_72;
  v39 = v38 + v7->DataLength;
  if ( v39 < v38 )
    goto LABEL_72;
  v64 = 1u;
  v40 = ExAllocatePool3(66, v39, 1701990473, &v64, 1);
  P = (PVOID)v40;
  v41 = v40;
  if ( !v40 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v38,
        L"shim for IPv6 reassembly (IPNG)");
LABEL_72:
    LOBYTE(v38) = v27;
    v12 = 3;
    IppDeleteFromReassemblySet(v8 + 22352, v28, v38);
    goto LABEL_73;
  }
  v45 = v7->DataLength;
  v46 = (struct _MDL *)(v40 + 16);
  *(_QWORD *)(v40 + 16) = 0;
  *(_WORD *)(v40 + 26) = 0;
  v63 = v40 + v37 + 16;
  *(_DWORD *)(v40 + 56) = v45;
  v47 = ((_WORD)v40 + (_WORD)v37 + 16) & 0xFFF;
  v48 = ((unsigned __int64)(((_WORD)v40 + (_WORD)v37 + 16) & 0xFFF) + v45 + 4095) >> 12;
  v49 = (v40 + v37 + 16) & 0xFFFFFFFFFFFFF000uLL;
  v46->ByteOffset = v47;
  v50 = 6;
  v46->StartVa = (PVOID)v49;
  v46->Size = 8 * (v48 + 6);
  MmBuildMdlForNonPagedPool(v46);
  *(_WORD *)(v41 + 8) = *((_WORD *)&v7->NetBufferHeader.Link + 12);
  *(_WORD *)(v41 + 10) = v72;
  *(_QWORD *)v41 = 0;
  if ( NewIrql == v28 + 96 )
  {
    *(_BYTE *)(v28 + 190) = *v70;
    if ( (Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 0x10) != 0 )
      v52 = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 1;
    else
      v52 = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline(v51);
    if ( !v52 )
      *(_DWORD *)(v28 + 224) = *(unsigned __int16 *)(v8 + 40) + (unsigned __int16)__ROR2__(*(_WORD *)(v73 + 4), 8);
    *(_DWORD *)(v28 + 216) = *(_DWORD *)(a1 + 316);
    *(_BYTE *)(v28 + 220) = *(_BYTE *)(a1 + 312);
    v53 = *(_WORD *)(a1 + 48) - 48;
    *(_WORD *)(v28 + 136) = v53;
    if ( v53 )
    {
      v64 = 1u;
      v54 = ExAllocatePool3(64, *(unsigned __int16 *)(v28 + 136), 1701990473, &v64, 1);
      *(_QWORD *)(v28 + 128) = v54;
      if ( !v54 )
      {
        v12 = 3;
        if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_TCPIP_PROVIDER_Context,
            TCPIP_MEMORY_FAILURES,
            v55,
            L"IPv6 reassembly unfragmentable data (IPNG)");
        LOBYTE(v55) = v27;
        IppDeleteFromReassemblySet(v8 + 22352, v28, v55);
        ExFreePoolWithTag(P, 0);
        goto LABEL_73;
      }
      IppIncreaseReassemblySize(v8 + 22352, v28, *(unsigned __int16 *)(v28 + 136), *(unsigned __int16 *)(v28 + 136));
      RtlCopyMdlToKernelBuffer(
        v7->MdlChain,
        v7->DataOffset - *(_DWORD *)(a1 + 48) + 40LL,
        *(_QWORD *)(v28 + 128),
        *(unsigned __int16 *)(v28 + 136),
        &v68);
      v50 = *(_WORD *)(a1 + 290);
    }
    *(_WORD *)(v28 + 188) = v50;
    *(_QWORD *)(v28 + 144) = **(_QWORD **)(a1 + 280);
  }
  RtlCopyMdlToKernelBuffer(v7->MdlChain, v7->DataOffset, v63, v7->DataLength, &v68);
  IppReassemblyInsertFragment(v28, NewIrql, v41);
  IppIncreaseReassemblySize(v8 + 22352, v28, v7->DataLength + 256, v7->DataLength);
  LOBYTE(v56) = v27;
  if ( *(unsigned __int16 *)(v28 + 84) == *(_DWORD *)(v28 + 140) )
    Ipv6pReassembleDatagram(a1, v28, v56);
  else
    IppCheckReassemblyQuota((PKSPIN_LOCK)(v8 + 22352));
  *(_DWORD *)(*(_QWORD *)(a1 + 8) + 140LL) = -1073741248;
LABEL_101:
  *(_DWORD *)(a1 + 44) = 59;
}

```

## disassembly

```asm
0x1400f0418  push    rbp
0x1400f041a  push    rbx
0x1400f041b  push    rsi
0x1400f041c  push    rdi
0x1400f041d  push    r12
0x1400f041f  push    r13
0x1400f0421  push    r14
0x1400f0423  push    r15
0x1400f0425  lea     rbp, [rsp-1Fh]
0x1400f042a  sub     rsp, 0C8h
0x1400f0431  mov     r12, [rcx+8]
0x1400f0435  xor     r13d, r13d
0x1400f0438  test    byte ptr [rcx+0B8h], 4
0x1400f043f  xorps   xmm0, xmm0
0x1400f0442  mov     rdi, rcx
0x1400f0445  mov     [rbp+57h+var_90], r12
0x1400f0449  mov     byte ptr [rbp+57h+NewIrql], r13b
0x1400f044d  mov     r15, [r12+8]
0x1400f0452  mov     [rbp+57h+var_60], r13
0x1400f0456  movups  [rbp+57h+var_88], xmm0
0x1400f045a  mov     dword ptr [rbp+57h+var_A0], 12h
0x1400f0461  jz      short loc_1400F0474
0x1400f0463  mov     dword ptr [r12+8Ch], 0C000023Eh
0x1400f046f  jmp     loc_1400F0DDE
0x1400f0474  mov     rax, [rcx+0D8h]
0x1400f047b  mov     rdx, [rax+8]
0x1400f047f  mov     [rbp+57h+var_98], rdx
0x1400f0483  mov     rax, [rdx]
0x1400f0486  mov     r14, [rax+28h]
0x1400f048a  mov     eax, gs:1A4h
0x1400f0492  mov     ecx, eax
0x1400f0494  mov     rax, [rdx+380h]
0x1400f049b  mov     rdx, [r14+4F28h]
0x1400f04a2  mov     [rbp+57h+var_68], rdx
0x1400f04a6  lea     rsi, [rcx+rcx*2]
0x1400f04aa  mov     rax, [rax+rcx*8]
0x1400f04ae  shl     rsi, 6
0x1400f04b2  mov     [rbp+57h+var_70], rax
0x1400f04b6  mov     rcx, [rbp+57h+var_70]
0x1400f04ba  mov     eax, [rax]
0x1400f04bc  inc     eax
0x1400f04be  mov     [rbp+57h+var_58], rsi
0x1400f04c2  mov     [rcx], eax
0x1400f04c4  mov     eax, [rdx+rsi+84h]
0x1400f04cb  inc     eax
0x1400f04cd  mov     [rdx+rsi+84h], eax
0x1400f04d4  test    byte ptr [rdi+0B8h], 8
0x1400f04db  jz      short loc_1400F04F0
0x1400f04dd  cmp     [r14+4D0Fh], r13b
0x1400f04e4  jnz     short loc_1400F04F0
0x1400f04e6  mov     esi, 10h
0x1400f04eb  jmp     loc_1400F0A7D
0x1400f04f0  test    byte ptr [rdi+0B9h], 4
0x1400f04f7  jz      short loc_1400F052A
0x1400f04f9  mov     eax, [rdi+30h]
0x1400f04fc  mov     esi, 0Fh
0x1400f0501  bswap   eax
0x1400f0503  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400f0508  mov     dword ptr [rsp+100h+var_D8], eax
0x1400f050c  mov     byte ptr [rsp+100h+AlignOffset], r13b
0x1400f0511  mov     r9b, 4
0x1400f0514  lea     rdx, Ipv6Global
0x1400f051b  mov     r8, rdi
0x1400f051e  xor     ecx, ecx
0x1400f0520  call    IppSendError
0x1400f0525  jmp     loc_1400F0A7D
0x1400f052a  mov     ebx, 1
0x1400f052f  mov     [rsp+100h+AlignOffset], r13d; AlignOffset
0x1400f0534  mov     r9d, ebx; AlignMultiple
0x1400f0537  xor     r8d, r8d; Storage
0x1400f053a  mov     rcx, r15; NetBuffer
0x1400f053d  lea     edx, [rbx+7]; BytesNeeded
0x1400f0540  call    cs:__imp_NdisGetDataBuffer
0x1400f0547  nop     dword ptr [rax+rax+00h]
0x1400f054c  mov     [rbp+57h+var_50], rax
0x1400f0550  mov     rsi, rax
0x1400f0553  test    rax, rax
0x1400f0556  jnz     short loc_1400F0575
0x1400f0558  cmp     dword ptr [r15+18h], 8
0x1400f055d  lea     esi, [rbx+2]
0x1400f0560  jnb     loc_1400F0A7D
0x1400f0566  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400f056b  mov     dword ptr [rsp+100h+var_D8], 4000000h
0x1400f0573  jmp     short loc_1400F050C
0x1400f0575  cmp     [rax], r13b
0x1400f0578  jnz     short loc_1400F0596
0x1400f057a  mov     eax, [rdi+30h]
0x1400f057d  mov     esi, 7
0x1400f0582  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400f0587  bswap   eax
0x1400f0589  mov     dword ptr [rsp+100h+var_D8], eax
0x1400f058d  mov     byte ptr [rsp+100h+AlignOffset], bl
0x1400f0591  jmp     loc_1400F0511
0x1400f0596  movzx   eax, word ptr [rax+2]
0x1400f059a  mov     ecx, 0F8FFh
0x1400f059f  movzx   r13d, ax
0x1400f05a3  and     r13w, cx
0x1400f05a7  xor     ecx, ecx
0x1400f05a9  ror     r13w, 8
0x1400f05ae  mov     [rbp+57h+arg_8], r13w
0x1400f05b3  cmp     [r14+57BCh], ecx
0x1400f05ba  jnz     short loc_1400F05D0
0x1400f05bc  test    r13w, r13w
0x1400f05c0  jnz     short loc_1400F05C9
0x1400f05c2  bt      ax, 8
0x1400f05c7  jnb     short loc_1400F05D0
0x1400f05c9  mov     esi, ebx
0x1400f05cb  jmp     loc_1400F0A7D
0x1400f05d0  mov     r9, [rdi+0E0h]
0x1400f05d7  mov     cl, [rdi+10h]
0x1400f05da  mov     eax, [r15+18h]
0x1400f05de  and     cl, bl
0x1400f05e0  mov     r8, [rdi+0D8h]
0x1400f05e7  sub     eax, 8
0x1400f05ea  mov     rdx, [rdi+108h]
0x1400f05f1  mov     [rsp+100h+var_B0], r12
0x1400f05f6  mov     [rsp+100h+var_B8], eax
0x1400f05fa  mov     eax, [rsi+4]
0x1400f05fd  mov     [rsp+100h+var_C0], r13w
0x1400f0603  mov     [rsp+100h+var_C8], eax
0x1400f0607  mov     eax, [rdi+30h]
0x1400f060a  mov     [rsp+100h+var_D0], eax
0x1400f060e  mov     eax, [r9+18h]
0x1400f0612  mov     r9, [r9+8]
0x1400f0616  mov     byte ptr [rsp+100h+var_D8], cl
0x1400f061a  mov     ecx, 29h ; ')'
0x1400f061f  mov     [rsp+100h+AlignOffset], eax
0x1400f0623  call    IppInspectFragmentIn
0x1400f0628  cmp     eax, ebx
0x1400f062a  jl      short loc_1400F0636
0x1400f062c  mov     esi, 2
0x1400f0631  jmp     loc_1400F0A7D
0x1400f0636  movzx   ebx, word ptr [rdi+30h]
0x1400f063a  mov     edx, 8
0x1400f063f  mov     rcx, r15
0x1400f0642  call    NetioAdvanceNetBuffer
0x1400f0647  add     dword ptr [rdi+30h], 8
0x1400f064b  xor     ecx, ecx
0x1400f064d  test    r13w, r13w
0x1400f0651  jnz     short loc_1400F0698
0x1400f0653  bt      word ptr [rsi+2], 8
0x1400f0659  jb      short loc_1400F0698
0x1400f065b  or      byte ptr [rdi+0BBh], 1
0x1400f0662  mov     rcx, [rbp+57h+var_70]
0x1400f0666  mov     rdx, [rbp+57h+var_68]
0x1400f066a  mov     [rdi+122h], bx
0x1400f0671  mov     eax, [rcx+4]
0x1400f0674  inc     eax
0x1400f0676  mov     [rcx+4], eax
0x1400f0679  mov     rcx, [rbp+57h+var_58]
0x1400f067d  mov     eax, [rdx+rcx+88h]
0x1400f0684  inc     eax
0x1400f0686  mov     [rdx+rcx+88h], eax
0x1400f068d  movzx   eax, byte ptr [rsi]
0x1400f0690  mov     [rdi+2Ch], eax
0x1400f0693  jmp     loc_1400F0DDE
0x1400f0698  mov     eax, cs:Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState
0x1400f069e  test    al, 10h
0x1400f06a0  jz      short loc_1400F06A7
0x1400f06a2  and     eax, 1
0x1400f06a5  jmp     short loc_1400F06AE
0x1400f06a7  call    Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline
0x1400f06ac  xor     ecx, ecx
0x1400f06ae  test    eax, eax
0x1400f06b0  jz      loc_1400F0779
0x1400f06b6  test    r13w, r13w
0x1400f06ba  jnz     loc_1400F0779
0x1400f06c0  movzx   eax, byte ptr [rsi]
0x1400f06c3  lea     r9, [rbp+57h+P]
0x1400f06c7  mov     dword ptr [rbp+57h+P], ecx
0x1400f06ca  lea     r8, [rbp+57h+arg_10]
0x1400f06ce  mov     [rbp+57h+var_78], rcx
0x1400f06d2  xor     edx, edx
0x1400f06d4  movzx   ebx, cl
0x1400f06d7  mov     rcx, r15
0x1400f06da  mov     dword ptr [rbp+57h+arg_10], eax
0x1400f06dd  call    cs:__imp_NetioPhSkipAllIpv6Options
0x1400f06e4  nop     dword ptr [rax+rax+00h]
0x1400f06e9  test    eax, eax
0x1400f06eb  js      short loc_1400F0731
0x1400f06ed  mov     edx, dword ptr [rbp+57h+arg_10]
0x1400f06f0  mov     r9d, 1
0x1400f06f6  mov     rcx, r14
0x1400f06f9  lea     eax, [rdx-32h]
0x1400f06fc  cmp     eax, r9d
0x1400f06ff  jbe     short loc_1400F070C
0x1400f0701  lea     r8, [rbp+57h+var_78]
0x1400f0705  call    IppFindNlFinalHeaderClient
0x1400f070a  jmp     short loc_1400F071E
0x1400f070c  lea     r9, [rbp+57h+var_78]
0x1400f0710  mov     r8, r12
0x1400f0713  call    IppFindNlExtensionHeaderClient
0x1400f0718  mov     r9d, 1
0x1400f071e  mov     rcx, [rbp+57h+var_78]
0x1400f0722  test    rcx, rcx
0x1400f0725  jz      short loc_1400F0731
0x1400f0727  mov     eax, [r15+18h]
0x1400f072b  cmp     [rcx], eax
0x1400f072d  cmova   ebx, r9d
0x1400f0731  mov     edx, dword ptr [rbp+57h+P]
0x1400f0734  xor     r8d, r8d
0x1400f0737  mov     rcx, r15
0x1400f073a  call    NetioRetreatNetBuffer
0x1400f073f  test    eax, eax
0x1400f0741  jns     short loc_1400F0745
0x1400f0743  int     2Ch; Windows NT - assertion failure
0x1400f0745  test    bl, bl
0x1400f0747  jz      short loc_1400F0779
0x1400f0749  mov     byte ptr [rsp+100h+var_D0], 0
0x1400f074e  lea     rdx, Ipv6Global
0x1400f0755  mov     dword ptr [rsp+100h+var_D8], 0
0x1400f075d  mov     r9b, 4
0x1400f0760  mov     r8, rdi
0x1400f0763  mov     byte ptr [rsp+100h+AlignOffset], 3
0x1400f0768  xor     ecx, ecx
0x1400f076a  mov     esi, 11h
0x1400f076f  call    IppSendError
0x1400f0774  jmp     loc_1400F0D8B
0x1400f0779  mov     rax, [rdi+118h]
0x1400f0780  lea     r9, [rbp+57h+NewIrql]
0x1400f0784  mov     edx, [rsi+4]
0x1400f0787  mov     r8, rax
0x1400f078a  mov     rcx, [rbp+57h+var_98]
0x1400f078e  mov     [rbp+57h+arg_10], rax
0x1400f0792  call    Ipv6pFragmentLookup
0x1400f0797  mov     r12b, byte ptr [rbp+57h+NewIrql]
0x1400f079b  xor     edx, edx
0x1400f079d  mov     rbx, rax
0x1400f07a0  test    rax, rax
0x1400f07a3  jnz     short loc_1400F080D
0x1400f07a5  mov     r9d, [rsi+4]
0x1400f07a9  lea     rcx, [r14+5750h]; SpinLock
0x1400f07b0  mov     r8, [rbp+57h+var_98]
0x1400f07b4  mov     rdx, [rdi+118h]
0x1400f07bb  mov     byte ptr [rsp+100h+AlignOffset], r12b; NewIrql
0x1400f07c0  call    IppCreateInReassemblySet
0x1400f07c5  mov     rbx, rax
0x1400f07c8  test    rax, rax
0x1400f07cb  jnz     short loc_1400F07FB
0x1400f07cd  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x1400f07d3  lea     esi, [rax+3]
0x1400f07d6  jge     loc_1400F0A7D
0x1400f07dc  lea     r9, aIpv6Reassembly_0; "IPv6 reassembly structure (IPNG)"
0x1400f07e3  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400f07ea  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f07f1  call    McTemplateK0z_EtwWriteTransfer
0x1400f07f6  jmp     loc_1400F0A7D
0x1400f07fb  mov     rax, [rdi+8]
0x1400f07ff  mov     ecx, [rax+110h]
0x1400f0805  mov     [rbx+0C8h], ecx
0x1400f080b  jmp     short loc_1400F0825
0x1400f080d  mov     rax, [rdi+8]
0x1400f0811  mov     ecx, [rax+110h]
0x1400f0817  cmp     [rbx+0C8h], ecx
0x1400f081d  jz      short loc_1400F0825
0x1400f081f  mov     [rbx+0C8h], edx
0x1400f0825  mov     rdx, [rbx+0D0h]
0x1400f082c  mov     rcx, [rbp+57h+var_90]
0x1400f0830  call    cs:__imp_WfpTransferReassemblyContextForFragments
0x1400f0837  nop     dword ptr [rax+rax+00h]
0x1400f083c  test    eax, eax
0x1400f083e  jns     short loc_1400F0880
0x1400f0840  mov     al, byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+5
0x1400f0846  and     al, 20h
0x1400f0848  mov     byte ptr [rbp+57h+NewIrql], al
0x1400f084b  jz      short loc_1400F0880
0x1400f084d  mov     rax, [rbp+57h+var_98]
0x1400f0851  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1400f0858  mov     dword ptr [rsp+100h+var_D8], 17h
0x1400f0860  lea     rdx, TCPIP_IP_REASSEMBLY_WFP
0x1400f0867  mov     r9d, 1
0x1400f086d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f0874  mov     eax, [rax+8]
0x1400f0877  mov     [rsp+100h+AlignOffset], eax
0x1400f087b  call    McTemplateK0qqq_EtwWriteTransfer
0x1400f0880  mov     r10, [rbp+57h+var_90]
0x1400f0884  mov     r8, [rbp+57h+arg_10]
0x1400f0888  mov     eax, [r10+88h]
0x1400f088f  and     eax, 0FFF00003h
0x1400f0894  or      [rbx+0B8h], eax
0x1400f089a  mov     eax, 1
0x1400f089f  mov     ecx, [r8]
0x1400f08a2  shr     ecx, 0Ch
0x1400f08a5  and     ecx, 3
0x1400f08a8  shl     eax, cl
0x1400f08aa  or      [rbx+0B8h], eax
0x1400f08b0  movzx   ecx, r13w
0x1400f08b4  add     ecx, [r15+18h]
0x1400f08b8  cmp     ecx, 0FFFFh
0x1400f08be  jbe     short loc_1400F08F2
0x1400f08c0  lea     rcx, [r14+5750h]
0x1400f08c7  mov     r8b, r12b
0x1400f08ca  mov     rdx, rbx
0x1400f08cd  mov     esi, 5
0x1400f08d2  call    IppDeleteFromReassemblySet
0x1400f08d7  mov     eax, [rdi+30h]
0x1400f08da  sub     eax, 6
0x1400f08dd  mov     byte ptr [rsp+100h+var_D0], 0
0x1400f08e2  bswap   eax
0x1400f08e4  mov     dword ptr [rsp+100h+var_D8], eax
  ... truncated ...
```
