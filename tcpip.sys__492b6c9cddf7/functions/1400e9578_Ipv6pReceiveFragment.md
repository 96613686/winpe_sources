# Ipv6pReceiveFragment

- ea: `0x1400e9578`
- end: `0x1400e9f53`
- name: `Ipv6pReceiveFragment`
- size: `2523`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400e9520`

## callees

- `0x140033ef0`
- `0x140053e98`
- `0x140063050`
- `0x1400c8414`
- `0x1400caa10`
- `0x1400de180`
- `0x1400e9578`
- `0x1400ea800`
- `0x1400eaa4c`
- `0x1400ead1c`
- `0x1400eadb4`
- `0x1400eaef0`
- `0x1400eaf48`
- `0x1400eb044`
- `0x1400eb074`
- `0x1400eb4fc`
- `0x1400ec024`
- `0x1400f8620`
- `0x14014cf98`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400e9b3c`
- `ntoskrnl!MmSizeOfMdl` at `0x1400e9b3c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e9cbf`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400e9cbf`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9b84`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9d8d`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9b84`
- `ntoskrnl!ExAllocatePool3` at `0x1400e9d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9de3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e9de3`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9e35`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9e7b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9e35`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400e9e7b`
- `NETIO!NetioPhSkipAllIpv6Options` at `0x1400e983d`
- `NETIO!NetioPhSkipAllIpv6Options` at `0x1400e983d`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400e9990`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400e9990`
- `NDIS!NdisGetDataBuffer` at `0x1400e96a0`
- `NDIS!NdisGetDataBuffer` at `0x1400e96a0`

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
0x1400e9578  push    rbp
0x1400e957a  push    rbx
0x1400e957b  push    rsi
0x1400e957c  push    rdi
0x1400e957d  push    r12
0x1400e957f  push    r13
0x1400e9581  push    r14
0x1400e9583  push    r15
0x1400e9585  lea     rbp, [rsp-1Fh]
0x1400e958a  sub     rsp, 0C8h
0x1400e9591  mov     r12, [rcx+8]
0x1400e9595  xor     r13d, r13d
0x1400e9598  test    byte ptr [rcx+0B8h], 4
0x1400e959f  xorps   xmm0, xmm0
0x1400e95a2  mov     rdi, rcx
0x1400e95a5  mov     [rbp+57h+var_90], r12
0x1400e95a9  mov     byte ptr [rbp+57h+NewIrql], r13b
0x1400e95ad  mov     r15, [r12+8]
0x1400e95b2  mov     [rbp+57h+var_60], r13
0x1400e95b6  movups  [rbp+57h+var_88], xmm0
0x1400e95ba  mov     dword ptr [rbp+57h+var_A0], 12h
0x1400e95c1  jz      short loc_1400E95D4
0x1400e95c3  mov     dword ptr [r12+8Ch], 0C000023Eh
0x1400e95cf  jmp     loc_1400E9F3E
0x1400e95d4  mov     rax, [rcx+0D8h]
0x1400e95db  mov     rdx, [rax+8]
0x1400e95df  mov     [rbp+57h+var_98], rdx
0x1400e95e3  mov     rax, [rdx]
0x1400e95e6  mov     r14, [rax+28h]
0x1400e95ea  mov     eax, gs:1A4h
0x1400e95f2  mov     ecx, eax
0x1400e95f4  mov     rax, [rdx+380h]
0x1400e95fb  mov     rdx, [r14+4F28h]
0x1400e9602  mov     [rbp+57h+var_68], rdx
0x1400e9606  lea     rsi, [rcx+rcx*2]
0x1400e960a  mov     rax, [rax+rcx*8]
0x1400e960e  shl     rsi, 6
0x1400e9612  mov     [rbp+57h+var_70], rax
0x1400e9616  mov     rcx, [rbp+57h+var_70]
0x1400e961a  mov     eax, [rax]
0x1400e961c  inc     eax
0x1400e961e  mov     [rbp+57h+var_58], rsi
0x1400e9622  mov     [rcx], eax
0x1400e9624  mov     eax, [rdx+rsi+84h]
0x1400e962b  inc     eax
0x1400e962d  mov     [rdx+rsi+84h], eax
0x1400e9634  test    byte ptr [rdi+0B8h], 8
0x1400e963b  jz      short loc_1400E9650
0x1400e963d  cmp     [r14+4D0Fh], r13b
0x1400e9644  jnz     short loc_1400E9650
0x1400e9646  mov     esi, 10h
0x1400e964b  jmp     loc_1400E9BDD
0x1400e9650  test    byte ptr [rdi+0B9h], 4
0x1400e9657  jz      short loc_1400E968A
0x1400e9659  mov     eax, [rdi+30h]
0x1400e965c  mov     esi, 0Fh
0x1400e9661  bswap   eax
0x1400e9663  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400e9668  mov     dword ptr [rsp+100h+var_D8], eax
0x1400e966c  mov     byte ptr [rsp+100h+AlignOffset], r13b
0x1400e9671  mov     r9b, 4
0x1400e9674  lea     rdx, Ipv6Global
0x1400e967b  mov     r8, rdi
0x1400e967e  xor     ecx, ecx
0x1400e9680  call    IppSendError
0x1400e9685  jmp     loc_1400E9BDD
0x1400e968a  mov     ebx, 1
0x1400e968f  mov     [rsp+100h+AlignOffset], r13d; AlignOffset
0x1400e9694  mov     r9d, ebx; AlignMultiple
0x1400e9697  xor     r8d, r8d; Storage
0x1400e969a  mov     rcx, r15; NetBuffer
0x1400e969d  lea     edx, [rbx+7]; BytesNeeded
0x1400e96a0  call    cs:__imp_NdisGetDataBuffer
0x1400e96a7  nop     dword ptr [rax+rax+00h]
0x1400e96ac  mov     [rbp+57h+var_50], rax
0x1400e96b0  mov     rsi, rax
0x1400e96b3  test    rax, rax
0x1400e96b6  jnz     short loc_1400E96D5
0x1400e96b8  cmp     dword ptr [r15+18h], 8
0x1400e96bd  lea     esi, [rbx+2]
0x1400e96c0  jnb     loc_1400E9BDD
0x1400e96c6  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400e96cb  mov     dword ptr [rsp+100h+var_D8], 4000000h
0x1400e96d3  jmp     short loc_1400E966C
0x1400e96d5  cmp     [rax], r13b
0x1400e96d8  jnz     short loc_1400E96F6
0x1400e96da  mov     eax, [rdi+30h]
0x1400e96dd  mov     esi, 7
0x1400e96e2  mov     byte ptr [rsp+100h+var_D0], r13b
0x1400e96e7  bswap   eax
0x1400e96e9  mov     dword ptr [rsp+100h+var_D8], eax
0x1400e96ed  mov     byte ptr [rsp+100h+AlignOffset], bl
0x1400e96f1  jmp     loc_1400E9671
0x1400e96f6  movzx   eax, word ptr [rax+2]
0x1400e96fa  mov     ecx, 0F8FFh
0x1400e96ff  movzx   r13d, ax
0x1400e9703  and     r13w, cx
0x1400e9707  xor     ecx, ecx
0x1400e9709  ror     r13w, 8
0x1400e970e  mov     [rbp+57h+arg_8], r13w
0x1400e9713  cmp     [r14+57BCh], ecx
0x1400e971a  jnz     short loc_1400E9730
0x1400e971c  test    r13w, r13w
0x1400e9720  jnz     short loc_1400E9729
0x1400e9722  bt      ax, 8
0x1400e9727  jnb     short loc_1400E9730
0x1400e9729  mov     esi, ebx
0x1400e972b  jmp     loc_1400E9BDD
0x1400e9730  mov     r9, [rdi+0E0h]
0x1400e9737  mov     cl, [rdi+10h]
0x1400e973a  mov     eax, [r15+18h]
0x1400e973e  and     cl, bl
0x1400e9740  mov     r8, [rdi+0D8h]
0x1400e9747  sub     eax, 8
0x1400e974a  mov     rdx, [rdi+108h]
0x1400e9751  mov     [rsp+100h+var_B0], r12
0x1400e9756  mov     [rsp+100h+var_B8], eax
0x1400e975a  mov     eax, [rsi+4]
0x1400e975d  mov     [rsp+100h+var_C0], r13w
0x1400e9763  mov     [rsp+100h+var_C8], eax
0x1400e9767  mov     eax, [rdi+30h]
0x1400e976a  mov     [rsp+100h+var_D0], eax
0x1400e976e  mov     eax, [r9+18h]
0x1400e9772  mov     r9, [r9+8]
0x1400e9776  mov     byte ptr [rsp+100h+var_D8], cl
0x1400e977a  mov     ecx, 29h ; ')'
0x1400e977f  mov     [rsp+100h+AlignOffset], eax
0x1400e9783  call    IppInspectFragmentIn
0x1400e9788  cmp     eax, ebx
0x1400e978a  jl      short loc_1400E9796
0x1400e978c  mov     esi, 2
0x1400e9791  jmp     loc_1400E9BDD
0x1400e9796  movzx   ebx, word ptr [rdi+30h]
0x1400e979a  mov     edx, 8
0x1400e979f  mov     rcx, r15
0x1400e97a2  call    NetioAdvanceNetBuffer
0x1400e97a7  add     dword ptr [rdi+30h], 8
0x1400e97ab  xor     ecx, ecx
0x1400e97ad  test    r13w, r13w
0x1400e97b1  jnz     short loc_1400E97F8
0x1400e97b3  bt      word ptr [rsi+2], 8
0x1400e97b9  jb      short loc_1400E97F8
0x1400e97bb  or      byte ptr [rdi+0BBh], 1
0x1400e97c2  mov     rcx, [rbp+57h+var_70]
0x1400e97c6  mov     rdx, [rbp+57h+var_68]
0x1400e97ca  mov     [rdi+122h], bx
0x1400e97d1  mov     eax, [rcx+4]
0x1400e97d4  inc     eax
0x1400e97d6  mov     [rcx+4], eax
0x1400e97d9  mov     rcx, [rbp+57h+var_58]
0x1400e97dd  mov     eax, [rdx+rcx+88h]
0x1400e97e4  inc     eax
0x1400e97e6  mov     [rdx+rcx+88h], eax
0x1400e97ed  movzx   eax, byte ptr [rsi]
0x1400e97f0  mov     [rdi+2Ch], eax
0x1400e97f3  jmp     loc_1400E9F3E
0x1400e97f8  mov     eax, cs:Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState
0x1400e97fe  test    al, 10h
0x1400e9800  jz      short loc_1400E9807
0x1400e9802  and     eax, 1
0x1400e9805  jmp     short loc_1400E980E
0x1400e9807  call    Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline
0x1400e980c  xor     ecx, ecx
0x1400e980e  test    eax, eax
0x1400e9810  jz      loc_1400E98D9
0x1400e9816  test    r13w, r13w
0x1400e981a  jnz     loc_1400E98D9
0x1400e9820  movzx   eax, byte ptr [rsi]
0x1400e9823  lea     r9, [rbp+57h+P]
0x1400e9827  mov     dword ptr [rbp+57h+P], ecx
0x1400e982a  lea     r8, [rbp+57h+arg_10]
0x1400e982e  mov     [rbp+57h+var_78], rcx
0x1400e9832  xor     edx, edx
0x1400e9834  movzx   ebx, cl
0x1400e9837  mov     rcx, r15
0x1400e983a  mov     dword ptr [rbp+57h+arg_10], eax
0x1400e983d  call    cs:__imp_NetioPhSkipAllIpv6Options
0x1400e9844  nop     dword ptr [rax+rax+00h]
0x1400e9849  test    eax, eax
0x1400e984b  js      short loc_1400E9891
0x1400e984d  mov     edx, dword ptr [rbp+57h+arg_10]
0x1400e9850  mov     r9d, 1
0x1400e9856  mov     rcx, r14
0x1400e9859  lea     eax, [rdx-32h]
0x1400e985c  cmp     eax, r9d
0x1400e985f  jbe     short loc_1400E986C
0x1400e9861  lea     r8, [rbp+57h+var_78]
0x1400e9865  call    IppFindNlFinalHeaderClient
0x1400e986a  jmp     short loc_1400E987E
0x1400e986c  lea     r9, [rbp+57h+var_78]
0x1400e9870  mov     r8, r12
0x1400e9873  call    IppFindNlExtensionHeaderClient
0x1400e9878  mov     r9d, 1
0x1400e987e  mov     rcx, [rbp+57h+var_78]
0x1400e9882  test    rcx, rcx
0x1400e9885  jz      short loc_1400E9891
0x1400e9887  mov     eax, [r15+18h]
0x1400e988b  cmp     [rcx], eax
0x1400e988d  cmova   ebx, r9d
0x1400e9891  mov     edx, dword ptr [rbp+57h+P]
0x1400e9894  xor     r8d, r8d
0x1400e9897  mov     rcx, r15
0x1400e989a  call    NetioRetreatNetBuffer
0x1400e989f  test    eax, eax
0x1400e98a1  jns     short loc_1400E98A5
0x1400e98a3  int     2Ch; Windows NT - assertion failure
0x1400e98a5  test    bl, bl
0x1400e98a7  jz      short loc_1400E98D9
0x1400e98a9  mov     byte ptr [rsp+100h+var_D0], 0
0x1400e98ae  lea     rdx, Ipv6Global
0x1400e98b5  mov     dword ptr [rsp+100h+var_D8], 0
0x1400e98bd  mov     r9b, 4
0x1400e98c0  mov     r8, rdi
0x1400e98c3  mov     byte ptr [rsp+100h+AlignOffset], 3
0x1400e98c8  xor     ecx, ecx
0x1400e98ca  mov     esi, 11h
0x1400e98cf  call    IppSendError
0x1400e98d4  jmp     loc_1400E9EEB
0x1400e98d9  mov     rax, [rdi+118h]
0x1400e98e0  lea     r9, [rbp+57h+NewIrql]
0x1400e98e4  mov     edx, [rsi+4]
0x1400e98e7  mov     r8, rax
0x1400e98ea  mov     rcx, [rbp+57h+var_98]
0x1400e98ee  mov     [rbp+57h+arg_10], rax
0x1400e98f2  call    Ipv6pFragmentLookup
0x1400e98f7  mov     r12b, byte ptr [rbp+57h+NewIrql]
0x1400e98fb  xor     edx, edx
0x1400e98fd  mov     rbx, rax
0x1400e9900  test    rax, rax
0x1400e9903  jnz     short loc_1400E996D
0x1400e9905  mov     r9d, [rsi+4]
0x1400e9909  lea     rcx, [r14+5750h]; SpinLock
0x1400e9910  mov     r8, [rbp+57h+var_98]
0x1400e9914  mov     rdx, [rdi+118h]
0x1400e991b  mov     byte ptr [rsp+100h+AlignOffset], r12b; NewIrql
0x1400e9920  call    IppCreateInReassemblySet
0x1400e9925  mov     rbx, rax
0x1400e9928  test    rax, rax
0x1400e992b  jnz     short loc_1400E995B
0x1400e992d  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x1400e9933  lea     esi, [rax+3]
0x1400e9936  jge     loc_1400E9BDD
0x1400e993c  lea     r9, aIpv6Reassembly_0; "IPv6 reassembly structure (IPNG)"
0x1400e9943  lea     rdx, TCPIP_MEMORY_FAILURES
0x1400e994a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400e9951  call    McTemplateK0z_EtwWriteTransfer
0x1400e9956  jmp     loc_1400E9BDD
0x1400e995b  mov     rax, [rdi+8]
0x1400e995f  mov     ecx, [rax+110h]
0x1400e9965  mov     [rbx+0C8h], ecx
0x1400e996b  jmp     short loc_1400E9985
0x1400e996d  mov     rax, [rdi+8]
0x1400e9971  mov     ecx, [rax+110h]
0x1400e9977  cmp     [rbx+0C8h], ecx
0x1400e997d  jz      short loc_1400E9985
0x1400e997f  mov     [rbx+0C8h], edx
0x1400e9985  mov     rdx, [rbx+0D0h]
0x1400e998c  mov     rcx, [rbp+57h+var_90]
0x1400e9990  call    cs:__imp_WfpTransferReassemblyContextForFragments
0x1400e9997  nop     dword ptr [rax+rax+00h]
0x1400e999c  test    eax, eax
0x1400e999e  jns     short loc_1400E99E0
0x1400e99a0  mov     al, byte ptr cs:WPP_MAIN_CB+14Dh
0x1400e99a6  and     al, 20h
0x1400e99a8  mov     byte ptr [rbp+57h+NewIrql], al
0x1400e99ab  jz      short loc_1400E99E0
0x1400e99ad  mov     rax, [rbp+57h+var_98]
0x1400e99b1  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1400e99b8  mov     dword ptr [rsp+100h+var_D8], 17h
0x1400e99c0  lea     rdx, TCPIP_IP_REASSEMBLY_WFP
0x1400e99c7  mov     r9d, 1
0x1400e99cd  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400e99d4  mov     eax, [rax+8]
0x1400e99d7  mov     [rsp+100h+AlignOffset], eax
0x1400e99db  call    McTemplateK0qqq_EtwWriteTransfer
0x1400e99e0  mov     r10, [rbp+57h+var_90]
0x1400e99e4  mov     r8, [rbp+57h+arg_10]
0x1400e99e8  mov     eax, [r10+88h]
0x1400e99ef  and     eax, 0FFF00003h
0x1400e99f4  or      [rbx+0B8h], eax
0x1400e99fa  mov     eax, 1
0x1400e99ff  mov     ecx, [r8]
0x1400e9a02  shr     ecx, 0Ch
0x1400e9a05  and     ecx, 3
0x1400e9a08  shl     eax, cl
0x1400e9a0a  or      [rbx+0B8h], eax
0x1400e9a10  movzx   ecx, r13w
0x1400e9a14  add     ecx, [r15+18h]
0x1400e9a18  cmp     ecx, 0FFFFh
0x1400e9a1e  jbe     short loc_1400E9A52
0x1400e9a20  lea     rcx, [r14+5750h]
0x1400e9a27  mov     r8b, r12b
0x1400e9a2a  mov     rdx, rbx
0x1400e9a2d  mov     esi, 5
0x1400e9a32  call    IppDeleteFromReassemblySet
0x1400e9a37  mov     eax, [rdi+30h]
0x1400e9a3a  sub     eax, 6
0x1400e9a3d  mov     byte ptr [rsp+100h+var_D0], 0
0x1400e9a42  bswap   eax
0x1400e9a44  mov     dword ptr [rsp+100h+var_D8], eax
  ... truncated ...
```
