# Ipv6pReceiveFragment

- ea: `0x1400e9468`
- end: `0x1400e9e43`
- name: `Ipv6pReceiveFragment`
- size: `2523`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400e9410`

## callees

- `0x140034190`
- `0x140054138`
- `0x1400632f0`
- `0x1400c81f4`
- `0x1400ca7f0`
- `0x1400ddf60`
- `0x1400e9468`
- `0x1400ea6f0`
- `0x1400ea93c`
- `0x1400eac0c`
- `0x1400eaca4`
- `0x1400eade0`
- `0x1400eae38`
- `0x1400eaf34`
- `0x1400eaf64`
- `0x1400eb3ec`
- `0x1400ebf14`
- `0x1400f8510`
- `0x14014d128`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400e9a2c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e9a2c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e9baf`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e9baf`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9a74`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9c7d`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9a74`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9cd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9cd3`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9d25`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9d6b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9d25`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9d6b`
- `NETIO!NetioPhSkipAllIpv6Options` at `0x1400e972d`
- `NETIO!NetioPhSkipAllIpv6Options` at `0x1400e972d`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400e9880`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400e9880`
- `NDIS!NdisGetDataBuffer` at `0x1400e9590`
- `NDIS!NdisGetDataBuffer` at `0x1400e9590`

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
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 14) & 0x10) != 0 )
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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    LOBYTE(NewIrql) = *((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 0x20;
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 0x20) != 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x1400e9468  push    rbp
0x1400e946a  push    rbx
0x1400e946b  push    rsi
0x1400e946c  push    rdi
0x1400e946d  push    r12
0x1400e946f  push    r13
0x1400e9471  push    r14
0x1400e9473  push    r15
0x1400e9475  lea     rbp, [rsp-1Fh]
0x1400e947a  sub     rsp, 0C8h
0x1400e9481  mov     r12, [rcx+8]
0x1400e9485  xor     r13d, r13d
0x1400e9488  test    byte ptr [rcx+0B8h], 4
0x1400e948f  xorps   xmm0, xmm0
0x1400e9492  mov     rdi, rcx
0x1400e9495  mov     [rbp+57h+var_90], r12
0x1400e9499  mov     byte ptr [rbp+57h+NewIrql], r13b
0x1400e949d  mov     r15, [r12+8]
0x1400e94a2  mov     [rbp+57h+var_60], r13
0x1400e94a6  movups  [rbp+57h+var_88], xmm0
0x1400e94aa  mov     dword ptr [rbp+57h+var_A0], 12h
0x1400e94b1  jz      short loc_1400E94C4
0x1400e94b3  mov     dword ptr [r12+8Ch], 0C000023Eh
0x1400e94bf  jmp     loc_1400E9E2E
0x1400e94c4  mov     rax, [rcx+0D8h]
0x1400e94cb  mov     rdx, [rax+8]
0x1400e94cf  mov     [rbp+57h+var_98], rdx
0x1400e94d3  mov     rax, [rdx]
0x1400e94d6  mov     r14, [rax+28h]
0x1400e94da  mov     eax, gs:1A4h
0x1400e94e2  mov     ecx, eax
0x1400e94e4  mov     rax, [rdx+380h]
0x1400e94eb  mov     rdx, [r14+4F28h]
0x1400e94f2  mov     [rbp+57h+var_68], rdx
0x1400e94f6  lea     rsi, [rcx+rcx*2]
0x1400e94fa  mov     rax, [rax+rcx*8]
0x1400e94fe  shl     rsi, 6
0x1400e9502  mov     [rbp+57h+var_70], rax
0x1400e9506  mov     rcx, [rbp+57h+var_70]
0x1400e950a  mov     eax, [rax]
0x1400e950c  inc     eax
0x1400e950e  mov     [rbp+57h+var_58], rsi
0x1400e9512  mov     [rcx], eax
0x1400e9514  mov     eax, [rdx+rsi+84h]
0x1400e951b  inc     eax
0x1400e951d  mov     [rdx+rsi+84h], eax
0x1400e9524  test    byte ptr [rdi+0B8h], 8
0x1400e952b  jz      short loc_1400E9540
0x1400e952d  cmp     [r14+4D0Fh], r13b
0x1400e9534  jnz     short loc_1400E9540
0x1400e9536  mov     esi, 10h
0x1400e953b  jmp     loc_1400E9ACD
0x1400e9540  test    byte ptr [rdi+0B9h], 4
0x1400e9547  jz      short loc_1400E957A
0x1400e9549  mov     eax, [rdi+30h]
0x1400e954c  mov     esi, 0Fh
0x1400e9551  bswap   eax
0x1400e9553  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400e9558  mov     dword ptr [rsp+100h+var_D8], eax
0x1400e955c  mov     byte ptr [rsp+100h+AlignOffset], r13b
0x1400e9561  mov     r9b, 4
0x1400e9564  lea     rdx, Ipv6Global
0x1400e956b  mov     r8, rdi
0x1400e956e  xor     ecx, ecx
0x1400e9570  call    IppSendError
0x1400e9575  jmp     loc_1400E9ACD
0x1400e957a  mov     ebx, 1
0x1400e957f  mov     [rsp+100h+AlignOffset], r13d; AlignOffset
0x1400e9584  mov     r9d, ebx; AlignMultiple
0x1400e9587  xor     r8d, r8d; Storage
0x1400e958a  mov     rcx, r15; NetBuffer
0x1400e958d  lea     edx, [rbx+7]; BytesNeeded
0x1400e9590  call    cs:__imp_NdisGetDataBuffer
0x1400e9597  nop     dword ptr [rax+rax+00h]
0x1400e959c  mov     [rbp+57h+var_50], rax
0x1400e95a0  mov     rsi, rax
0x1400e95a3  test    rax, rax
0x1400e95a6  jnz     short loc_1400E95C5
0x1400e95a8  cmp     dword ptr [r15+18h], 8
0x1400e95ad  lea     esi, [rbx+2]
0x1400e95b0  jnb     loc_1400E9ACD
0x1400e95b6  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400e95bb  mov     dword ptr [rsp+100h+var_D8], 4000000h
0x1400e95c3  jmp     short loc_1400E955C
0x1400e95c5  cmp     [rax], r13b
0x1400e95c8  jnz     short loc_1400E95E6
0x1400e95ca  mov     eax, [rdi+30h]
0x1400e95cd  mov     esi, 7
0x1400e95d2  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400e95d7  bswap   eax
0x1400e95d9  mov     dword ptr [rsp+100h+var_D8], eax
0x1400e95dd  mov     byte ptr [rsp+100h+AlignOffset], bl
0x1400e95e1  jmp     loc_1400E9561
0x1400e95e6  movzx   eax, word ptr [rax+2]
0x1400e95ea  mov     ecx, 0F8FFh
0x1400e95ef  movzx   r13d, ax
0x1400e95f3  and     r13w, cx
0x1400e95f7  xor     ecx, ecx
0x1400e95f9  ror     r13w, 8
0x1400e95fe  mov     [rbp+57h+arg_8], r13w
0x1400e9603  cmp     [r14+57BCh], ecx
0x1400e960a  jnz     short loc_1400E9620
0x1400e960c  test    r13w, r13w
0x1400e9610  jnz     short loc_1400E9619
0x1400e9612  bt      ax, 8
0x1400e9617  jnb     short loc_1400E9620
0x1400e9619  mov     esi, ebx
0x1400e961b  jmp     loc_1400E9ACD
0x1400e9620  mov     r9, [rdi+0E0h]
0x1400e9627  mov     cl, [rdi+10h]
0x1400e962a  mov     eax, [r15+18h]
0x1400e962e  and     cl, bl
0x1400e9630  mov     r8, [rdi+0D8h]
0x1400e9637  sub     eax, 8
0x1400e963a  mov     rdx, [rdi+108h]
0x1400e9641  mov     [rsp+100h+var_B0], r12
0x1400e9646  mov     [rsp+100h+var_B8], eax
0x1400e964a  mov     eax, [rsi+4]
0x1400e964d  mov     [rsp+100h+var_C0], r13w
0x1400e9653  mov     [rsp+100h+var_C8], eax
0x1400e9657  mov     eax, [rdi+30h]
0x1400e965a  mov     [rsp+100h+var_D0], eax
0x1400e965e  mov     eax, [r9+18h]
0x1400e9662  mov     r9, [r9+8]
0x1400e9666  mov     byte ptr [rsp+100h+var_D8], cl
0x1400e966a  mov     ecx, 29h ; ')'
0x1400e966f  mov     [rsp+100h+AlignOffset], eax
0x1400e9673  call    IppInspectFragmentIn
0x1400e9678  cmp     eax, ebx
0x1400e967a  jl      short loc_1400E9686
0x1400e967c  mov     esi, 2
0x1400e9681  jmp     loc_1400E9ACD
0x1400e9686  movzx   ebx, word ptr [rdi+30h]
0x1400e968a  mov     edx, 8
0x1400e968f  mov     rcx, r15
0x1400e9692  call    NetioAdvanceNetBuffer
0x1400e9697  add     dword ptr [rdi+30h], 8
0x1400e969b  xor     ecx, ecx
0x1400e969d  test    r13w, r13w
0x1400e96a1  jnz     short loc_1400E96E8
0x1400e96a3  bt      word ptr [rsi+2], 8
0x1400e96a9  jb      short loc_1400E96E8
0x1400e96ab  or      byte ptr [rdi+0BBh], 1
0x1400e96b2  mov     rcx, [rbp+57h+var_70]
0x1400e96b6  mov     rdx, [rbp+57h+var_68]
0x1400e96ba  mov     [rdi+122h], bx
0x1400e96c1  mov     eax, [rcx+4]
0x1400e96c4  inc     eax
0x1400e96c6  mov     [rcx+4], eax
0x1400e96c9  mov     rcx, [rbp+57h+var_58]
0x1400e96cd  mov     eax, [rdx+rcx+88h]
0x1400e96d4  inc     eax
0x1400e96d6  mov     [rdx+rcx+88h], eax
0x1400e96dd  movzx   eax, byte ptr [rsi]
0x1400e96e0  mov     [rdi+2Ch], eax
0x1400e96e3  jmp     loc_1400E9E2E
0x1400e96e8  mov     eax, cs:Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState
0x1400e96ee  test    al, 10h
0x1400e96f0  jz      short loc_1400E96F7
0x1400e96f2  and     eax, 1
0x1400e96f5  jmp     short loc_1400E96FE
0x1400e96f7  call    Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline
0x1400e96fc  xor     ecx, ecx
0x1400e96fe  test    eax, eax
0x1400e9700  jz      loc_1400E97C9
0x1400e9706  test    r13w, r13w
0x1400e970a  jnz     loc_1400E97C9
0x1400e9710  movzx   eax, byte ptr [rsi]
0x1400e9713  lea     r9, [rbp+57h+P]
0x1400e9717  mov     dword ptr [rbp+57h+P], ecx
0x1400e971a  lea     r8, [rbp+57h+arg_10]
0x1400e971e  mov     [rbp+57h+var_78], rcx
0x1400e9722  xor     edx, edx
0x1400e9724  movzx   ebx, cl
0x1400e9727  mov     rcx, r15
0x1400e972a  mov     dword ptr [rbp+57h+arg_10], eax
0x1400e972d  call    cs:__imp_NetioPhSkipAllIpv6Options
0x1400e9734  nop     dword ptr [rax+rax+00h]
0x1400e9739  test    eax, eax
0x1400e973b  js      short loc_1400E9781
0x1400e973d  mov     edx, dword ptr [rbp+57h+arg_10]
0x1400e9740  mov     r9d, 1
0x1400e9746  mov     rcx, r14
0x1400e9749  lea     eax, [rdx-32h]
0x1400e974c  cmp     eax, r9d
0x1400e974f  jbe     short loc_1400E975C
0x1400e9751  lea     r8, [rbp+57h+var_78]
0x1400e9755  call    IppFindNlFinalHeaderClient
0x1400e975a  jmp     short loc_1400E976E
0x1400e975c  lea     r9, [rbp+57h+var_78]
0x1400e9760  mov     r8, r12
0x1400e9763  call    IppFindNlExtensionHeaderClient
0x1400e9768  mov     r9d, 1
0x1400e976e  mov     rcx, [rbp+57h+var_78]
0x1400e9772  test    rcx, rcx
0x1400e9775  jz      short loc_1400E9781
0x1400e9777  mov     eax, [r15+18h]
0x1400e977b  cmp     [rcx], eax
0x1400e977d  cmova   ebx, r9d
0x1400e9781  mov     edx, dword ptr [rbp+57h+P]
0x1400e9784  xor     r8d, r8d
0x1400e9787  mov     rcx, r15
0x1400e978a  call    NetioRetreatNetBuffer
0x1400e978f  test    eax, eax
0x1400e9791  jns     short loc_1400E9795
0x1400e9793  int     2Ch; Windows NT - assertion failure
0x1400e9795  test    bl, bl
0x1400e9797  jz      short loc_1400E97C9
0x1400e9799  mov     byte ptr [rsp+100h+var_D0], 0
0x1400e979e  lea     rdx, Ipv6Global
0x1400e97a5  mov     dword ptr [rsp+100h+var_D8], 0
0x1400e97ad  mov     r9b, 4
0x1400e97b0  mov     r8, rdi
0x1400e97b3  mov     byte ptr [rsp+100h+AlignOffset], 3
0x1400e97b8  xor     ecx, ecx
0x1400e97ba  mov     esi, 11h
0x1400e97bf  call    IppSendError
0x1400e97c4  jmp     loc_1400E9DDB
0x1400e97c9  mov     rax, [rdi+118h]
0x1400e97d0  lea     r9, [rbp+57h+NewIrql]
0x1400e97d4  mov     edx, [rsi+4]
0x1400e97d7  mov     r8, rax
0x1400e97da  mov     rcx, [rbp+57h+var_98]
0x1400e97de  mov     [rbp+57h+arg_10], rax
0x1400e97e2  call    Ipv6pFragmentLookup
0x1400e97e7  mov     r12b, byte ptr [rbp+57h+NewIrql]
0x1400e97eb  xor     edx, edx
0x1400e97ed  mov     rbx, rax
0x1400e97f0  test    rax, rax
0x1400e97f3  jnz     short loc_1400E985D
0x1400e97f5  mov     r9d, [rsi+4]
0x1400e97f9  lea     rcx, [r14+5750h]; SpinLock
0x1400e9800  mov     r8, [rbp+57h+var_98]
0x1400e9804  mov     rdx, [rdi+118h]
0x1400e980b  mov     byte ptr [rsp+100h+AlignOffset], r12b; NewIrql
0x1400e9810  call    IppCreateInReassemblySet
0x1400e9815  mov     rbx, rax
0x1400e9818  test    rax, rax
0x1400e981b  jnz     short loc_1400E984B
0x1400e981d  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x1400e9823  lea     esi, [rax+3]
0x1400e9826  jge     loc_1400E9ACD
0x1400e982c  lea     r9, aIpv6Reassembly_0; "IPv6 reassembly structure (IPNG)"
0x1400e9833  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400e983a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400e9841  call    McTemplateK0z_EtwWriteTransfer
0x1400e9846  jmp     loc_1400E9ACD
0x1400e984b  mov     rax, [rdi+8]
0x1400e984f  mov     ecx, [rax+110h]
0x1400e9855  mov     [rbx+0C8h], ecx
0x1400e985b  jmp     short loc_1400E9875
0x1400e985d  mov     rax, [rdi+8]
0x1400e9861  mov     ecx, [rax+110h]
0x1400e9867  cmp     [rbx+0C8h], ecx
0x1400e986d  jz      short loc_1400E9875
0x1400e986f  mov     [rbx+0C8h], edx
0x1400e9875  mov     rdx, [rbx+0D0h]
0x1400e987c  mov     rcx, [rbp+57h+var_90]
0x1400e9880  call    cs:__imp_WfpTransferReassemblyContextForFragments
0x1400e9887  nop     dword ptr [rax+rax+00h]
0x1400e988c  test    eax, eax
0x1400e988e  jns     short loc_1400E98D0
0x1400e9890  mov     al, byte ptr cs:WPP_MAIN_CB+14Dh
0x1400e9896  and     al, 20h
0x1400e9898  mov     byte ptr [rbp+57h+NewIrql], al
0x1400e989b  jz      short loc_1400E98D0
0x1400e989d  mov     rax, [rbp+57h+var_98]
0x1400e98a1  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1400e98a8  mov     dword ptr [rsp+100h+var_D8], 17h
0x1400e98b0  lea     rdx, TCPIP_IP_REASSEMBLY_WFP
0x1400e98b7  mov     r9d, 1
0x1400e98bd  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400e98c4  mov     eax, [rax+8]
0x1400e98c7  mov     [rsp+100h+AlignOffset], eax
0x1400e98cb  call    McTemplateK0qqq_EtwWriteTransfer
0x1400e98d0  mov     r10, [rbp+57h+var_90]
0x1400e98d4  mov     r8, [rbp+57h+arg_10]
0x1400e98d8  mov     eax, [r10+88h]
0x1400e98df  and     eax, 0FFF00003h
0x1400e98e4  or      [rbx+0B8h], eax
0x1400e98ea  mov     eax, 1
0x1400e98ef  mov     ecx, [r8]
0x1400e98f2  shr     ecx, 0Ch
0x1400e98f5  and     ecx, 3
0x1400e98f8  shl     eax, cl
0x1400e98fa  or      [rbx+0B8h], eax
0x1400e9900  movzx   ecx, r13w
0x1400e9904  add     ecx, [r15+18h]
0x1400e9908  cmp     ecx, 0FFFFh
0x1400e990e  jbe     short loc_1400E9942
0x1400e9910  lea     rcx, [r14+5750h]
0x1400e9917  mov     r8b, r12b
0x1400e991a  mov     rdx, rbx
0x1400e991d  mov     esi, 5
0x1400e9922  call    IppDeleteFromReassemblySet
0x1400e9927  mov     eax, [rdi+30h]
0x1400e992a  sub     eax, 6
0x1400e992d  mov     byte ptr [rsp+100h+var_D0], 0
0x1400e9932  bswap   eax
0x1400e9934  mov     dword ptr [rsp+100h+var_D8], eax
  ... truncated ...
```
