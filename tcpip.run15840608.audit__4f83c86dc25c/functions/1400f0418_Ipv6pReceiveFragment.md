# Ipv6pReceiveFragment

- ea: `0x1400f0418`
- end: `0x1400f0df3`
- name: `Ipv6pReceiveFragment`
- size: `2523`
- prototype: ``
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
void __fastcall Ipv6pReceiveFragment(__int64 a1)
{
  __int64 v1; // r12
  bool v2; // zf
  struct _NET_BUFFER *v4; // r15
  __int64 v5; // r14
  __int64 LockArray_high; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  int v9; // esi
  _BYTE *DataBuffer; // rax
  unsigned __int8 *v11; // rsi
  __int16 v12; // ax
  unsigned __int16 v13; // r13
  __int16 v14; // bx
  _DWORD *v15; // rcx
  __int64 v16; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  int v18; // eax
  char v19; // bl
  char v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rax
  KIRQL v23; // r12
  __int64 v24; // rbx
  __int64 v25; // r8
  int v26; // r10d
  _DWORD *v27; // r8
  __int64 v28; // r8
  ULONG DataLength; // ecx
  int v30; // eax
  unsigned int v31; // ecx
  unsigned int v32; // eax
  SIZE_T v33; // r13
  SIZE_T v34; // r8
  SIZE_T v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rcx
  __int64 v39; // rdx
  ULONG v40; // edx
  __int64 v41; // r9
  struct _MDL *v42; // rcx
  int v43; // r8d
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rax
  __int16 v46; // r13
  __int64 v47; // rcx
  int v48; // eax
  __int16 v49; // ax
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // r8
  __int64 v53; // rax
  int v54; // [rsp+28h] [rbp-81h]
  int v55; // [rsp+28h] [rbp-81h]
  __int64 v56; // [rsp+60h] [rbp-49h] BYREF
  __int64 v57; // [rsp+68h] [rbp-41h]
  __int64 v58; // [rsp+70h] [rbp-39h]
  __int128 v59; // [rsp+78h] [rbp-31h] BYREF
  ULONG *v60; // [rsp+88h] [rbp-21h] BYREF
  _DWORD *v61; // [rsp+90h] [rbp-19h]
  __int64 v62; // [rsp+98h] [rbp-11h]
  __int64 v63; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-1h]
  _BYTE *v65; // [rsp+B0h] [rbp+7h]
  __int64 NewIrql; // [rsp+110h] [rbp+67h] BYREF
  unsigned __int16 v67; // [rsp+118h] [rbp+6Fh]
  __int64 v68; // [rsp+120h] [rbp+77h] BYREF
  PVOID P; // [rsp+128h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  v2 = (*(_BYTE *)(a1 + 184) & 4) == 0;
  v58 = v1;
  LOBYTE(NewIrql) = 0;
  v4 = *(struct _NET_BUFFER **)(v1 + 8);
  v63 = 0;
  v59 = 0;
  LODWORD(v56) = 18;
  if ( !v2 )
  {
    *(_DWORD *)(v1 + 140) = -1073741250;
    return;
  }
  v57 = *(_QWORD *)(*(_QWORD *)(a1 + 216) + 8LL);
  v5 = *(_QWORD *)(*(_QWORD *)v57 + 40LL);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v7 = *(_QWORD *)(v57 + 896);
  v62 = *(_QWORD *)(v5 + 20264);
  v8 = v62;
  v61 = *(_DWORD **)(v7 + 8 * LockArray_high);
  LODWORD(v7) = *v61 + 1;
  v64 = 192 * LockArray_high;
  *v61 = v7;
  ++*(_DWORD *)(v8 + 192 * LockArray_high + 132);
  if ( (*(_BYTE *)(a1 + 184) & 8) != 0 && !*(_BYTE *)(v5 + 19727) )
  {
    v9 = 16;
LABEL_73:
    v38 = v64;
    v39 = v62;
    ++v61[2];
    ++*(_DWORD *)(v39 + v38 + 140);
    goto LABEL_97;
  }
  if ( (*(_BYTE *)(a1 + 185) & 4) != 0 )
  {
    v9 = 15;
    v54 = _byteswap_ulong(*(_DWORD *)(a1 + 48));
    goto LABEL_8;
  }
  DataBuffer = NdisGetDataBuffer(v4, 8u, 0, 1u, 0);
  v65 = DataBuffer;
  v11 = DataBuffer;
  if ( !DataBuffer )
  {
    v9 = 3;
    if ( v4->DataLength >= 8 )
      goto LABEL_73;
    v54 = 0x4000000;
LABEL_8:
    IppSendError(0, (__int64)&Ipv6Global, a1, 4, 0, v54, 0);
    goto LABEL_73;
  }
  if ( !*DataBuffer )
  {
    v9 = 7;
    IppSendError(0, (__int64)&Ipv6Global, a1, 4, 1, _byteswap_ulong(*(_DWORD *)(a1 + 48)), 0);
    goto LABEL_73;
  }
  v12 = *((_WORD *)DataBuffer + 1);
  v13 = __ROR2__(v12 & 0xF8FF, 8);
  v67 = v13;
  if ( !*(_DWORD *)(v5 + 22460) && (v13 || (v12 & 0x100) != 0) )
  {
    v9 = 1;
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
              *((_DWORD *)v11 + 1),
              v13,
              v4->DataLength - 8,
              v1) >= 1 )
  {
    v9 = 2;
    goto LABEL_73;
  }
  v14 = *(_WORD *)(a1 + 48);
  NetioAdvanceNetBuffer(v4, 8);
  *(_DWORD *)(a1 + 48) += 8;
  if ( !v13 && !_bittest16((const signed __int16 *)v11 + 1, 8u) )
  {
    *(_BYTE *)(a1 + 187) |= 1u;
    v15 = v61;
    v16 = v62;
    *(_WORD *)(a1 + 290) = v14;
    ++v15[1];
    ++*(_DWORD *)(v16 + v64 + 136);
    *(_DWORD *)(a1 + 44) = *v11;
    return;
  }
  if ( (Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline(0);
  if ( IsEnabledDeviceUsageNoInline && !v13 )
  {
    v18 = *v11;
    LODWORD(P) = 0;
    v60 = 0;
    v19 = 0;
    LODWORD(v68) = v18;
    if ( (int)NetioPhSkipAllIpv6Options(v4, 0, &v68, &P) >= 0 )
    {
      if ( (unsigned int)(v68 - 50) <= 1 )
      {
        IppFindNlExtensionHeaderClient(v5, (unsigned int)v68, v1, &v60);
        v20 = 1;
      }
      else
      {
        IppFindNlFinalHeaderClient(v5, (unsigned int)v68, &v60);
      }
      if ( v60 && *v60 > v4->DataLength )
        v19 = v20;
    }
    if ( (int)NetioRetreatNetBuffer(v4, (unsigned int)P, 0) < 0 )
      __int2c();
    if ( v19 )
    {
      v9 = 17;
      IppSendError(0, (__int64)&Ipv6Global, a1, 4, 3, 0, 0);
LABEL_97:
      if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredContext) & 0x10) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCPIP_IP_REASSEMBLY_DROP,
          (unsigned int)MICROSOFT_TCPIP_PROVIDER,
          v9,
          23,
          *(_DWORD *)(v57 + 8));
      v53 = *(_QWORD *)(a1 + 8);
      if ( v53 )
        *(_DWORD *)(v53 + 140) = -1073741285;
      goto LABEL_101;
    }
  }
  v21 = *((unsigned int *)v11 + 1);
  v68 = *(_QWORD *)(a1 + 280);
  v22 = Ipv6pFragmentLookup(v57, v21, v68, &NewIrql);
  v23 = NewIrql;
  v24 = v22;
  if ( v22 )
  {
    if ( *(_DWORD *)(v22 + 200) != *(_DWORD *)(*(_QWORD *)(a1 + 8) + 272LL) )
      *(_DWORD *)(v22 + 200) = 0;
  }
  else
  {
    v24 = IppCreateInReassemblySet((PKSPIN_LOCK)(v5 + 22352), NewIrql);
    if ( !v24 )
    {
      v9 = 3;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v25,
          L"IPv6 reassembly structure (IPNG)");
      goto LABEL_73;
    }
    *(_DWORD *)(v24 + 200) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 272LL);
  }
  if ( (int)WfpTransferReassemblyContextForFragments(v58, *(_QWORD *)(v24 + 208)) < 0 )
  {
    LOBYTE(NewIrql) = BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20;
    if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_IP_REASSEMBLY_WFP,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        1,
        *(_DWORD *)(v57 + 8),
        23);
  }
  v26 = v58;
  v27 = (_DWORD *)v68;
  *(_DWORD *)(v24 + 184) |= *(_DWORD *)(v58 + 136) & 0xFFF00003;
  *(_DWORD *)(v24 + 184) |= 1 << ((*v27 >> 12) & 3);
  if ( v4->DataLength + v13 > 0xFFFF )
  {
    LOBYTE(v27) = v23;
    v9 = 5;
    IppDeleteFromReassemblySet(v5 + 22352, v24, v27);
    v55 = _byteswap_ulong(*(_DWORD *)(a1 + 48) - 6);
LABEL_52:
    IppSendError(0, (__int64)&Ipv6Global, a1, 4, 0, v55, 0);
    goto LABEL_73;
  }
  if ( (int)IPsecVerifyFragment((int)v24 + 192, v26, *(_DWORD *)(v5 + 24), (int)v27 + 8, (__int64)(v27 + 6)) < 0 )
  {
    v9 = 8;
LABEL_55:
    LOBYTE(v28) = v23;
    IppDeleteFromReassemblySet(v5 + 22352, v24, v28);
    goto LABEL_97;
  }
  DataLength = v4->DataLength;
  if ( !DataLength && (v13 || (*((_WORD *)v11 + 1) & 0x100) != 0) )
  {
    v9 = 9;
    goto LABEL_55;
  }
  if ( (*((_WORD *)v11 + 1) & 0x100) != 0 )
  {
    if ( (DataLength & 7) != 0 )
    {
      LOBYTE(v28) = v23;
      v9 = 6;
      IppDeleteFromReassemblySet(v5 + 22352, v24, v28);
      v55 = 0x4000000;
      goto LABEL_52;
    }
    v40 = *(_DWORD *)(v24 + 140);
    if ( v40 == -1 || DataLength + v13 <= v40 )
      goto LABEL_66;
LABEL_78:
    v9 = 11;
    goto LABEL_55;
  }
  v30 = *(_DWORD *)(v24 + 140);
  v28 = v13;
  v31 = v13 + DataLength;
  if ( v30 == -1 )
  {
    v32 = *(unsigned __int16 *)(v24 + 84);
    *(_DWORD *)(v24 + 140) = v31;
    if ( v32 <= v31 && *(unsigned __int16 *)(v24 + 86) <= v31 )
      goto LABEL_66;
    goto LABEL_78;
  }
  if ( v31 != v30 )
  {
    v9 = 10;
    goto LABEL_55;
  }
LABEL_66:
  NewIrql = IppReassemblyFindLocation(
              v5,
              v24,
              v13,
              *((unsigned __int16 *)&v4->NetBufferHeader.Link + 12),
              v23,
              (__int64)&v56);
  if ( !NewIrql )
  {
    v9 = v56;
    goto LABEL_97;
  }
  v33 = (MmSizeOfMdl((PVOID)0xFFF, v4->DataLength) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v34 = v33 + 16;
  if ( v33 >= 0xFFFFFFFFFFFFFFF0uLL )
    goto LABEL_72;
  v35 = v34 + v4->DataLength;
  if ( v35 < v34 )
    goto LABEL_72;
  v59 = 1u;
  v36 = ExAllocatePool3(66, v35, 1701990473, &v59, 1);
  P = (PVOID)v36;
  v37 = v36;
  if ( !v36 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v34,
        L"shim for IPv6 reassembly (IPNG)");
LABEL_72:
    LOBYTE(v34) = v23;
    v9 = 3;
    IppDeleteFromReassemblySet(v5 + 22352, v24, v34);
    goto LABEL_73;
  }
  v41 = v4->DataLength;
  v42 = (struct _MDL *)(v36 + 16);
  *(_QWORD *)(v36 + 16) = 0;
  *(_WORD *)(v36 + 26) = 0;
  v58 = v36 + v33 + 16;
  *(_DWORD *)(v36 + 56) = v41;
  v43 = ((_WORD)v36 + (_WORD)v33 + 16) & 0xFFF;
  v44 = ((unsigned __int64)(((_WORD)v36 + (_WORD)v33 + 16) & 0xFFF) + v41 + 4095) >> 12;
  v45 = (v36 + v33 + 16) & 0xFFFFFFFFFFFFF000uLL;
  v42->ByteOffset = v43;
  v46 = 6;
  v42->StartVa = (PVOID)v45;
  v42->Size = 8 * (v44 + 6);
  MmBuildMdlForNonPagedPool(v42);
  *(_WORD *)(v37 + 8) = *((_WORD *)&v4->NetBufferHeader.Link + 12);
  *(_WORD *)(v37 + 10) = v67;
  *(_QWORD *)v37 = 0;
  if ( NewIrql == v24 + 96 )
  {
    *(_BYTE *)(v24 + 190) = *v65;
    if ( (Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 0x10) != 0 )
      v48 = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 1;
    else
      v48 = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline(v47);
    if ( !v48 )
      *(_DWORD *)(v24 + 224) = *(unsigned __int16 *)(v5 + 40) + (unsigned __int16)__ROR2__(*(_WORD *)(v68 + 4), 8);
    *(_DWORD *)(v24 + 216) = *(_DWORD *)(a1 + 316);
    *(_BYTE *)(v24 + 220) = *(_BYTE *)(a1 + 312);
    v49 = *(_WORD *)(a1 + 48) - 48;
    *(_WORD *)(v24 + 136) = v49;
    if ( v49 )
    {
      v59 = 1u;
      v50 = ExAllocatePool3(64, *(unsigned __int16 *)(v24 + 136), 1701990473, &v59, 1);
      *(_QWORD *)(v24 + 128) = v50;
      if ( !v50 )
      {
        v9 = 3;
        if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_TCPIP_PROVIDER_Context,
            TCPIP_MEMORY_FAILURES,
            v51,
            L"IPv6 reassembly unfragmentable data (IPNG)");
        LOBYTE(v51) = v23;
        IppDeleteFromReassemblySet(v5 + 22352, v24, v51);
        ExFreePoolWithTag(P, 0);
        goto LABEL_73;
      }
      IppIncreaseReassemblySize(v5 + 22352, v24, *(unsigned __int16 *)(v24 + 136), *(unsigned __int16 *)(v24 + 136));
      RtlCopyMdlToKernelBuffer(
        v4->MdlChain,
        v4->DataOffset - *(_DWORD *)(a1 + 48) + 40LL,
        *(_QWORD *)(v24 + 128),
        *(unsigned __int16 *)(v24 + 136),
        &v63);
      v46 = *(_WORD *)(a1 + 290);
    }
    *(_WORD *)(v24 + 188) = v46;
    *(_QWORD *)(v24 + 144) = **(_QWORD **)(a1 + 280);
  }
  RtlCopyMdlToKernelBuffer(v4->MdlChain, v4->DataOffset, v58, v4->DataLength, &v63);
  IppReassemblyInsertFragment(v24, NewIrql, v37);
  IppIncreaseReassemblySize(v5 + 22352, v24, v4->DataLength + 256, v4->DataLength);
  LOBYTE(v52) = v23;
  if ( *(unsigned __int16 *)(v24 + 84) == *(_DWORD *)(v24 + 140) )
    Ipv6pReassembleDatagram(a1, v24, v52);
  else
    IppCheckReassemblyQuota((PKSPIN_LOCK)(v5 + 22352));
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
