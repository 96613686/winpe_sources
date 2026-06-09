# Ipv4pReceiveFragment

- ea: `0x1400f1340`
- end: `0x1400f1b6f`
- name: `Ipv4pReceiveFragment`
- size: `2095`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400f12e0`

## callees

- `0x140014a08`
- `0x1400f1340`
- `0x1400f1b80`
- `0x1400f1e78`
- `0x1400f201c`
- `0x1400f20b4`
- `0x1400f21f0`
- `0x1400f2248`
- `0x1400f2344`
- `0x1400f2374`
- `0x1400f27fc`
- `0x1400f28d0`
- `0x1400f3a14`
- `0x1400fb148`
- `0x14014ecd0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400f1610`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f1610`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400f172a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400f172a`
- `ntoskrnl!KeBugCheck` at `0x1400f195d`
- `ntoskrnl!KeBugCheck` at `0x1400f195d`
- `ntoskrnl!ExAllocatePool3` at `0x1400f16ad`
- `ntoskrnl!ExAllocatePool3` at `0x1401d341f`
- `ntoskrnl!ExAllocatePool3` at `0x1400f16ad`
- `ntoskrnl!ExAllocatePool3` at `0x1401d341f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d347b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d347b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400f1775`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1401d34ce`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400f1775`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1401d34ce`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400f1526`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400f1526`

## pseudocode

```c
void __fastcall Ipv4pReceiveFragment(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // r14
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // r15
  unsigned int LockArray_high; // eax
  _DWORD *v9; // r13
  __int64 v10; // rcx
  unsigned __int16 v11; // r12
  __int64 v12; // rbx
  KIRQL v13; // r13
  __int64 v14; // r8
  unsigned __int16 v15; // dx
  int v16; // ecx
  unsigned int v17; // edx
  __int64 Location; // r13
  SIZE_T v19; // r14
  SIZE_T v20; // r8
  int v21; // esi
  SIZE_T v22; // rdx
  __int64 Pool3; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  SIZE_T v26; // r10
  _WORD *v27; // r14
  __int64 v28; // rcx
  int v29; // r8d
  unsigned int v30; // edx
  unsigned int v31; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  __int16 v33; // dx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // [rsp+60h] [rbp-78h]
  _DWORD *v39; // [rsp+68h] [rbp-70h]
  __int64 v40; // [rsp+70h] [rbp-68h] BYREF
  _OWORD v41[2]; // [rsp+78h] [rbp-60h] BYREF
  KIRQL NewIrql; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v43; // [rsp+E8h] [rbp+10h] BYREF
  SIZE_T v44; // [rsp+F0h] [rbp+18h]
  __int64 v45; // [rsp+F8h] [rbp+20h]

  v1 = (*(_BYTE *)(a1 + 184) & 4) == 0;
  v2 = *(_QWORD *)(a1 + 8);
  NewIrql = 0;
  LODWORD(v43) = 18;
  v4 = *(_QWORD *)(v2 + 8);
  v40 = 0;
  v41[0] = 0;
  if ( !v1 )
  {
    *(_DWORD *)(v2 + 140) = -1073741250;
    return;
  }
  v5 = *(_QWORD *)(a1 + 280);
  if ( *(_BYTE *)(v5 + 9) == 44 || *(_DWORD *)(a1 + 48) != (unsigned __int8)(4 * (*(_BYTE *)v5 & 0xF)) )
  {
    *(_DWORD *)(v2 + 140) = -1073741250;
    return;
  }
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 216) + 8LL);
  v45 = v6;
  v7 = *(_QWORD *)(*(_QWORD *)v6 + 40LL);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v9 = *(_DWORD **)(*(_QWORD *)(v6 + 896) + 8LL * LockArray_high);
  v10 = 192LL * LockArray_high + *(_QWORD *)(v7 + 20264);
  v39 = v9;
  v38 = v10;
  ++*v9;
  ++*(_DWORD *)(v10 + 132);
  if ( (*(_BYTE *)(a1 + 184) & 8) != 0 )
    KeBugCheck(0x4Fu);
  if ( !*(_DWORD *)(v7 + 22460) )
  {
    v21 = 1;
    goto LABEL_25;
  }
  v11 = 8 * __ROR2__(*(_WORD *)(v5 + 6) & 0xFF1F, 8);
  if ( (int)IppInspectFragmentIn(
              0,
              *(_QWORD *)(a1 + 264),
              *(_QWORD *)(a1 + 216),
              *(_QWORD *)(*(_QWORD *)(a1 + 224) + 8LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 224) + 24LL),
              *(_BYTE *)(a1 + 16) & 1,
              *(_DWORD *)(a1 + 48),
              *(unsigned __int16 *)(v5 + 4),
              v11,
              *(_DWORD *)(v4 + 24),
              v2) >= 1 )
  {
    v21 = 2;
    goto LABEL_24;
  }
  v12 = Ipv4pFragmentLookup(v6, *(unsigned __int16 *)(v5 + 4), v5, &NewIrql);
  if ( v12 )
  {
    if ( *(_BYTE *)(v12 + 153) != *(_BYTE *)(v5 + 9) )
    {
      v21 = 4;
      IppDeleteFromReassemblySet(v7 + 22352, v12, NewIrql);
      IppSendError(0, (__int64)&Ipv4Global, a1, 12, 0, _byteswap_ulong(*(_DWORD *)(a1 + 48) + 9), 0);
      goto LABEL_23;
    }
    v13 = NewIrql;
    if ( *(_DWORD *)(v12 + 200) != *(_DWORD *)(*(_QWORD *)(a1 + 8) + 272LL) )
      *(_DWORD *)(v12 + 200) = 0;
  }
  else
  {
    v13 = NewIrql;
    v12 = IppCreateInReassemblySet((PKSPIN_LOCK)(v7 + 22352), NewIrql);
    if ( !v12 )
    {
      v21 = 3;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v14,
          L"IPv4 reassembly structure (IPNG)");
      goto LABEL_22;
    }
    *(_DWORD *)(v12 + 200) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 272LL);
  }
  if ( (int)WfpTransferReassemblyContextForFragments(v2, *(_QWORD *)(v12 + 208)) < 0 )
  {
    LOBYTE(v44) = BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20;
    if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredContext) & 0x20) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_IP_REASSEMBLY_WFP,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        1,
        *(_DWORD *)(v45 + 8),
        2);
  }
  *(_DWORD *)(v12 + 184) |= *(_DWORD *)(v2 + 136) & 0xFFF00003;
  *(_DWORD *)(v12 + 184) |= 1 << (*(_BYTE *)(v5 + 1) & 3);
  if ( v11 || *(_WORD *)(v12 + 84) )
    v15 = -21;
  else
    v15 = ~(unsigned __int8)(4 * (*(_BYTE *)v5 & 0xF));
  if ( *(_DWORD *)(v4 + 24) + (unsigned int)v11 > v15 )
  {
    v21 = 5;
    IppDeleteFromReassemblySet(v7 + 22352, v12, v13);
    IppSendError(0, (__int64)&Ipv4Global, a1, 12, 0, _byteswap_ulong(*(_DWORD *)(a1 + 48) + 6), 0);
    goto LABEL_22;
  }
  if ( (int)IPsecVerifyFragment((int)v12 + 192, v2, *(_DWORD *)(v7 + 24), (int)v5 + 12, v5 + 16) < 0 )
  {
    v21 = 8;
    goto LABEL_39;
  }
  v16 = *(_DWORD *)(v4 + 24);
  if ( !v16 )
  {
    v21 = 9;
    goto LABEL_39;
  }
  if ( (*(_BYTE *)(v5 + 6) & 0x20) != 0 )
  {
    if ( (v16 & 7) != 0 )
    {
      v21 = 6;
      IppDeleteFromReassemblySet(v7 + 22352, v12, v13);
      IppSendError(0, (__int64)&Ipv4Global, a1, 12, 0, 0x2000000, 0);
      goto LABEL_22;
    }
    v17 = *(_DWORD *)(v12 + 140);
    if ( v17 != -1 && v16 + (unsigned int)v11 > v17 )
    {
LABEL_38:
      v21 = 11;
LABEL_39:
      IppDeleteFromReassemblySet(v7 + 22352, v12, v13);
LABEL_78:
      v6 = v45;
      goto LABEL_79;
    }
  }
  else
  {
    v29 = *(_DWORD *)(v12 + 140);
    v30 = v16 + v11;
    if ( v29 == -1 )
    {
      v31 = *(unsigned __int16 *)(v12 + 84);
      *(_DWORD *)(v12 + 140) = v30;
      if ( v31 > v30 || *(unsigned __int16 *)(v12 + 86) > v30 )
        goto LABEL_38;
    }
    else if ( v30 != v29 )
    {
      v21 = 10;
      goto LABEL_39;
    }
  }
  Location = IppReassemblyFindLocation(v7, v12, v11, *(unsigned __int16 *)(v4 + 24), v13, (__int64)&v43);
  if ( !Location )
  {
    v21 = v43;
    goto LABEL_78;
  }
  v19 = (MmSizeOfMdl((PVOID)0xFFF, *(unsigned int *)(v4 + 24)) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v20 = v19 + 16;
  if ( v19 >= 0xFFFFFFFFFFFFFFF0uLL || (v22 = v20 + *(unsigned int *)(v4 + 24), v22 < v20) )
  {
LABEL_21:
    v21 = 3;
    IppDeleteFromReassemblySet(v7 + 22352, v12, NewIrql);
LABEL_22:
    v9 = v39;
LABEL_23:
    v6 = v45;
LABEL_24:
    v10 = v38;
LABEL_25:
    ++v9[2];
    ++*(_DWORD *)(v10 + 140);
LABEL_79:
    if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredContext) & 0x10) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_IP_REASSEMBLY_DROP,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v21,
        2,
        *(_DWORD *)(v6 + 8));
    v37 = *(_QWORD *)(a1 + 8);
    if ( v37 )
      *(_DWORD *)(v37 + 140) = -1073741285;
    goto LABEL_32;
  }
  v41[0] = 1u;
  Pool3 = ExAllocatePool3(66, v22, 1701990473, v41, 1);
  if ( !Pool3 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v24,
        L"shim for IPv4 reassembly (IPNG)");
    goto LABEL_21;
  }
  v25 = *(unsigned int *)(v4 + 24);
  *(_QWORD *)(Pool3 + 16) = 0;
  v26 = Pool3 + v19 + 16;
  *(_DWORD *)(Pool3 + 56) = v25;
  v27 = (_WORD *)Pool3;
  v44 = v26;
  *(_DWORD *)(Pool3 + 60) = v26 & 0xFFF;
  *(_WORD *)(Pool3 + 26) = 0;
  *(_WORD *)(Pool3 + 24) = 8 * ((((v26 & 0xFFF) + v25 + 4095) >> 12) + 6);
  *(_QWORD *)(Pool3 + 48) = v26 & 0xFFFFFFFFFFFFF000uLL;
  MmBuildMdlForNonPagedPool((PMDL)(Pool3 + 16));
  v27[4] = *(_WORD *)(v4 + 24);
  v27[5] = v11;
  *(_QWORD *)v27 = 0;
  if ( Location == v12 + 96 )
  {
    *(_BYTE *)(v12 + 190) = *(_BYTE *)(v5 + 9);
    if ( (Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_USGv6_FirstFragmentSecurityHeaderFix__private_IsEnabledDeviceUsageNoInline(v28);
    if ( !IsEnabledDeviceUsageNoInline )
      *(_DWORD *)(v12 + 224) = (unsigned __int16)__ROR2__(*(_WORD *)(v5 + 2), 8);
    *(_DWORD *)(v12 + 216) = *(_DWORD *)(a1 + 316);
    *(_BYTE *)(v12 + 220) = *(_BYTE *)(a1 + 312);
    v33 = (unsigned __int8)(4 * (*(_BYTE *)v5 & 0xF));
    *(_WORD *)(v12 + 136) = v33 - 20;
    if ( v33 == 20 )
      goto LABEL_50;
    v41[0] = 1u;
    v35 = ExAllocatePool3(66, *(unsigned __int16 *)(v12 + 136), 1701990473, v41, 1);
    *(_QWORD *)(v12 + 128) = v35;
    if ( v35 )
    {
      IppIncreaseReassemblySize(v7 + 22352, v12, *(unsigned __int16 *)(v12 + 136), *(unsigned __int16 *)(v12 + 136));
      RtlCopyMdlToKernelBuffer(
        *(_QWORD *)(v4 + 32),
        (unsigned int)(*(_DWORD *)(v4 + 40) - *(_DWORD *)(a1 + 48)) + 20LL,
        *(_QWORD *)(v12 + 128),
        *(unsigned __int16 *)(v12 + 136),
        &v40);
LABEL_50:
      v34 = *(_QWORD *)(a1 + 280);
      *(_QWORD *)(v12 + 144) = *(_QWORD *)v34;
      *(_DWORD *)(v12 + 152) = *(_DWORD *)(v34 + 8);
      goto LABEL_29;
    }
    v21 = 3;
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v36,
        L"IPv4 reassembly unfragmentable data (IPNG)");
    IppDeleteFromReassemblySet(v7 + 22352, v12, NewIrql);
    ExFreePoolWithTag(v27, 0);
    goto LABEL_22;
  }
LABEL_29:
  RtlCopyMdlToKernelBuffer(*(_QWORD *)(v4 + 32), *(unsigned int *)(v4 + 40), v44, *(unsigned int *)(v4 + 24), &v40);
  IppReassemblyInsertFragment(v12, Location, v27);
  IppIncreaseReassemblySize(v7 + 22352, v12, (unsigned int)(*(_DWORD *)(v4 + 24) + 256), *(unsigned int *)(v4 + 24));
  if ( *(unsigned __int16 *)(v12 + 84) == *(_DWORD *)(v12 + 140) )
    Ipv4pReassembleDatagram(a1, v12, NewIrql);
  else
    IppCheckReassemblyQuota((PKSPIN_LOCK)(v7 + 22352));
  *(_DWORD *)(*(_QWORD *)(a1 + 8) + 140LL) = -1073741248;
LABEL_32:
  *(_DWORD *)(a1 + 44) = 59;
}

```

## disassembly

```asm
0x1400f1340  mov     r11, rsp
0x1400f1343  push    rbp
0x1400f1344  push    rdi
0x1400f1345  push    r14
0x1400f1347  sub     rsp, 0C0h
0x1400f134e  test    byte ptr [rcx+0B8h], 4
0x1400f1355  xorps   xmm0, xmm0
0x1400f1358  mov     r14, [rcx+8]
0x1400f135c  mov     rdi, rcx
0x1400f135f  mov     byte ptr [r11+8], 0
0x1400f1364  mov     dword ptr [r11+10h], 12h
0x1400f136c  mov     rbp, [r14+8]
0x1400f1370  mov     qword ptr [r11-68h], 0
0x1400f1378  movups  [rsp+0D8h+var_60], xmm0
0x1400f137d  jnz     loc_1400F1948
0x1400f1383  mov     [r11-28h], rsi
0x1400f1387  mov     rsi, [rcx+118h]
0x1400f138e  cmp     byte ptr [rsi+9], 2Ch ; ','
0x1400f1392  jz      loc_1400F1B5F
0x1400f1398  movzx   eax, byte ptr [rsi]
0x1400f139b  and     al, 0Fh
0x1400f139d  shl     al, 2
0x1400f13a0  movzx   eax, al
0x1400f13a3  cmp     [rcx+30h], eax
0x1400f13a6  jnz     loc_1400F1B5F
0x1400f13ac  mov     rax, [rcx+0D8h]
0x1400f13b3  mov     [r11-20h], rbx
0x1400f13b7  mov     [r11-38h], r13
0x1400f13bb  mov     [r11-40h], r15
0x1400f13bf  mov     rbx, [rax+8]
0x1400f13c3  mov     [rsp+0D8h+arg_18], rbx
0x1400f13cb  mov     rax, [rbx]
0x1400f13ce  mov     r15, [rax+28h]
0x1400f13d2  mov     eax, gs:1A4h
0x1400f13da  mov     ecx, eax
0x1400f13dc  mov     rax, [rbx+380h]
0x1400f13e3  lea     rdx, [rcx+rcx*2]
0x1400f13e7  mov     r13, [rax+rcx*8]
0x1400f13eb  mov     rcx, [r15+4F28h]
0x1400f13f2  shl     rdx, 6
0x1400f13f6  add     rcx, rdx
0x1400f13f9  mov     [rsp+0D8h+var_70], r13
0x1400f13fe  mov     eax, [r13+0]
0x1400f1402  inc     eax
0x1400f1404  mov     [rsp+0D8h+var_78], rcx
0x1400f1409  mov     [r13+0], eax
0x1400f140d  mov     eax, [rcx+84h]
0x1400f1413  inc     eax
0x1400f1415  mov     [rcx+84h], eax
0x1400f141b  test    byte ptr [rdi+0B8h], 8
0x1400f1422  jnz     loc_1400F1958
0x1400f1428  cmp     dword ptr [r15+57BCh], 0
0x1400f1430  mov     [r11-30h], r12
0x1400f1434  jz      loc_1400F196A
0x1400f143a  mov     r9, [rdi+0E0h]
0x1400f1441  mov     eax, 0FF1Fh
0x1400f1446  movzx   ecx, word ptr [rsi+4]
0x1400f144a  movzx   edx, byte ptr [rdi+10h]
0x1400f144e  movzx   r12d, word ptr [rsi+6]
0x1400f1453  and     dl, 1
0x1400f1456  mov     r8, [rdi+0D8h]
0x1400f145d  and     r12w, ax
0x1400f1461  mov     eax, [rbp+18h]
0x1400f1464  mov     [rsp+0D8h+var_88], r14
0x1400f1469  mov     [rsp+0D8h+var_90], eax
0x1400f146d  mov     eax, [rdi+30h]
0x1400f1470  ror     r12w, 8
0x1400f1475  shl     r12w, 3
0x1400f147a  mov     [rsp+0D8h+var_98], r12w
0x1400f1480  mov     [rsp+0D8h+var_A0], ecx
0x1400f1484  xor     ecx, ecx
0x1400f1486  mov     [rsp+0D8h+var_A8], eax
0x1400f148a  mov     eax, [r9+18h]
0x1400f148e  mov     r9, [r9+8]
0x1400f1492  mov     byte ptr [rsp+0D8h+var_B0], dl
0x1400f1496  mov     rdx, [rdi+108h]
0x1400f149d  mov     dword ptr [rsp+0D8h+NewIrql], eax
0x1400f14a1  call    IppInspectFragmentIn
0x1400f14a6  cmp     eax, 1
0x1400f14a9  jge     loc_1400F1974
0x1400f14af  movzx   edx, word ptr [rsi+4]
0x1400f14b3  lea     r9, [rsp+0D8h+arg_0]
0x1400f14bb  mov     r8, rsi
0x1400f14be  mov     rcx, rbx
0x1400f14c1  call    Ipv4pFragmentLookup
0x1400f14c6  mov     rbx, rax
0x1400f14c9  test    rax, rax
0x1400f14cc  jnz     loc_1400F1870
0x1400f14d2  movzx   r13d, [rsp+0D8h+arg_0]
0x1400f14db  lea     rcx, [r15+5750h]; SpinLock
0x1400f14e2  movzx   r9d, word ptr [rsi+4]
0x1400f14e7  mov     r8, [rsp+0D8h+arg_18]
0x1400f14ef  mov     rdx, [rdi+118h]
0x1400f14f6  mov     [rsp+0D8h+NewIrql], r13b; NewIrql
0x1400f14fb  call    IppCreateInReassemblySet
0x1400f1500  mov     rbx, rax
0x1400f1503  test    rax, rax
0x1400f1506  jz      loc_1400F197E
0x1400f150c  mov     rax, [rdi+8]
0x1400f1510  mov     ecx, [rax+110h]
0x1400f1516  mov     [rbx+0C8h], ecx
0x1400f151c  mov     rdx, [rbx+0D0h]
0x1400f1523  mov     rcx, r14
0x1400f1526  call    cs:__imp_WfpTransferReassemblyContextForFragments
0x1400f152d  nop     dword ptr [rax+rax+00h]
0x1400f1532  test    eax, eax
0x1400f1534  js      loc_1400F19FB
0x1400f153a  mov     eax, [r14+88h]
0x1400f1541  and     eax, 0FFF00003h
0x1400f1546  or      [rbx+0B8h], eax
0x1400f154c  mov     eax, 1
0x1400f1551  movzx   ecx, byte ptr [rsi+1]
0x1400f1555  and     ecx, 3
0x1400f1558  shl     eax, cl
0x1400f155a  or      [rbx+0B8h], eax
0x1400f1560  test    r12w, r12w
0x1400f1564  jz      loc_1400F18AE
0x1400f156a  mov     edx, 0FFEBh
0x1400f156f  movzx   ecx, r12w
0x1400f1573  add     ecx, [rbp+18h]
0x1400f1576  movzx   eax, dx
0x1400f1579  cmp     ecx, eax
0x1400f157b  ja      loc_1400F1A4D
0x1400f1581  mov     r8d, [r15+18h]
0x1400f1585  lea     rax, [rsi+10h]
0x1400f1589  lea     r9, [rsi+0Ch]
0x1400f158d  mov     qword ptr [rsp+0D8h+NewIrql], rax
0x1400f1592  lea     rcx, [rbx+0C0h]
0x1400f1599  mov     rdx, r14
0x1400f159c  call    IPsecVerifyFragment
0x1400f15a1  test    eax, eax
0x1400f15a3  js      loc_1400F1A94
0x1400f15a9  mov     ecx, [rbp+18h]
0x1400f15ac  test    ecx, ecx
0x1400f15ae  jz      loc_1400F1A9E
0x1400f15b4  test    byte ptr [rsi+6], 20h
0x1400f15b8  jz      loc_1400F1821
0x1400f15be  test    cl, 7
0x1400f15c1  jnz     loc_1400F1ABB
0x1400f15c7  mov     edx, [rbx+8Ch]
0x1400f15cd  cmp     edx, 0FFFFFFFFh
0x1400f15d0  jnz     loc_1400F1AFE
0x1400f15d6  movzx   r9d, word ptr [rbp+18h]; int
0x1400f15db  lea     rax, [rsp+0D8h+arg_8]
0x1400f15e3  mov     [rsp+0D8h+var_B0], rax; __int64
0x1400f15e8  movzx   r8d, r12w; int
0x1400f15ec  mov     rdx, rbx; int
0x1400f15ef  mov     [rsp+0D8h+NewIrql], r13b; NewIrql
0x1400f15f4  mov     rcx, r15; int
0x1400f15f7  call    IppReassemblyFindLocation
0x1400f15fc  mov     r13, rax
0x1400f15ff  test    rax, rax
0x1400f1602  jz      loc_1400F1B53
0x1400f1608  mov     edx, [rbp+18h]; Length
0x1400f160b  mov     ecx, 0FFFh; Base
0x1400f1610  call    cs:__imp_MmSizeOfMdl
0x1400f1617  nop     dword ptr [rax+rax+00h]
0x1400f161c  lea     r14, [rax+7]
0x1400f1620  and     r14, 0FFFFFFFFFFFFFFF8h
0x1400f1624  lea     r8, [r14+10h]
0x1400f1628  cmp     r8, 10h
0x1400f162c  jnb     short loc_1400F167A
0x1400f162e  movzx   r8d, [rsp+0D8h+arg_0]
0x1400f1637  lea     rcx, [r15+5750h]
0x1400f163e  mov     rdx, rbx
0x1400f1641  mov     esi, 3
0x1400f1646  call    IppDeleteFromReassemblySet
0x1400f164b  mov     r13, [rsp+0D8h+var_70]
0x1400f1650  mov     rbx, [rsp+0D8h+arg_18]
0x1400f1658  mov     rcx, [rsp+0D8h+var_78]
0x1400f165d  mov     eax, [r13+8]
0x1400f1661  inc     eax
0x1400f1663  mov     [r13+8], eax
0x1400f1667  mov     eax, [rcx+8Ch]
0x1400f166d  inc     eax
0x1400f166f  mov     [rcx+8Ch], eax
0x1400f1675  jmp     loc_1401D34E8
0x1400f167a  mov     edx, [rbp+18h]
0x1400f167d  add     rdx, r8
0x1400f1680  cmp     rdx, r8
0x1400f1683  jb      short loc_1400F162E
0x1400f1685  xor     ecx, ecx
0x1400f1687  lea     r9, [rsp+0D8h+var_60]
0x1400f168c  mov     eax, 1
0x1400f1691  mov     qword ptr [rsp+0D8h+var_60+8], rcx
0x1400f1699  mov     ecx, 42h ; 'B'
0x1400f169e  mov     qword ptr [rsp+0D8h+var_60], rax
0x1400f16a3  mov     r8d, 65725049h
0x1400f16a9  mov     dword ptr [rsp+0D8h+NewIrql], eax
0x1400f16ad  call    cs:__imp_ExAllocatePool3
0x1400f16b4  nop     dword ptr [rax+rax+00h]
0x1400f16b9  test    rax, rax
0x1400f16bc  jz      loc_1400F1B11
0x1400f16c2  mov     r9d, [rbp+18h]
0x1400f16c6  lea     rcx, [rax+10h]; MemoryDescriptorList
0x1400f16ca  lea     r10, [r14+10h]
0x1400f16ce  mov     qword ptr [rcx], 0
0x1400f16d5  add     r10, rax
0x1400f16d8  mov     [rcx+28h], r9d
0x1400f16dc  mov     r14, rax
0x1400f16df  mov     [rsp+0D8h+arg_10], r10
0x1400f16e7  mov     r8d, r10d
0x1400f16ea  lea     rdx, [r9+0FFFh]
0x1400f16f1  mov     eax, r8d
0x1400f16f4  and     r8d, 0FFFh
0x1400f16fb  and     eax, 0FFFh
0x1400f1700  mov     [rcx+2Ch], r8d
0x1400f1704  add     rdx, rax
0x1400f1707  xor     eax, eax
0x1400f1709  shr     rdx, 0Ch
0x1400f170d  mov     [rcx+0Ah], ax
0x1400f1711  add     dx, 6
0x1400f1715  mov     rax, r10
0x1400f1718  shl     dx, 3
0x1400f171c  and     rax, 0FFFFFFFFFFFFF000h
0x1400f1722  mov     [rcx+8], dx
0x1400f1726  mov     [rcx+20h], rax
0x1400f172a  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400f1731  nop     dword ptr [rax+rax+00h]
0x1400f1736  movzx   eax, word ptr [rbp+18h]
0x1400f173a  mov     [r14+8], ax
0x1400f173f  lea     rax, [rbx+60h]
0x1400f1743  mov     [r14+0Ah], r12w
0x1400f1748  mov     qword ptr [r14], 0
0x1400f174f  cmp     r13, rax
0x1400f1752  jz      loc_1400F18CC
0x1400f1758  mov     r9d, [rbp+18h]
0x1400f175c  lea     rax, [rsp+0D8h+var_68]
0x1400f1761  mov     edx, [rbp+28h]
0x1400f1764  mov     r8, [rsp+0D8h+arg_10]
0x1400f176c  mov     rcx, [rbp+20h]
0x1400f1770  mov     qword ptr [rsp+0D8h+NewIrql], rax
0x1400f1775  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x1400f177c  nop     dword ptr [rax+rax+00h]
0x1400f1781  mov     r8, r14
0x1400f1784  mov     rdx, r13
0x1400f1787  mov     rcx, rbx
0x1400f178a  call    IppReassemblyInsertFragment
0x1400f178f  mov     r9d, [rbp+18h]
0x1400f1793  lea     rcx, [r15+5750h]
0x1400f179a  mov     rdx, rbx
0x1400f179d  lea     r8d, [r9+100h]
0x1400f17a4  call    IppIncreaseReassemblySize
0x1400f17a9  movzx   eax, word ptr [rbx+54h]
0x1400f17ad  mov     rdx, rbx
0x1400f17b0  movzx   r8d, [rsp+0D8h+arg_0]
0x1400f17b9  cmp     eax, [rbx+8Ch]
0x1400f17bf  jz      short loc_1400F1817
0x1400f17c1  lea     rcx, [r15+5750h]; SpinLock
0x1400f17c8  call    IppCheckReassemblyQuota
0x1400f17cd  mov     rax, [rdi+8]
0x1400f17d1  mov     dword ptr [rax+8Ch], 0C0000240h
0x1400f17db  mov     r12, [rsp+0D8h+var_30]
0x1400f17e3  mov     r13, [rsp+0D8h+var_38]
0x1400f17eb  mov     rbx, [rsp+0D8h+var_20]
0x1400f17f3  mov     r15, [rsp+0D8h+var_40]
0x1400f17fb  mov     dword ptr [rdi+2Ch], 3Bh ; ';'
0x1400f1802  mov     rsi, [rsp+0D8h+var_28]
0x1400f180a  add     rsp, 0C0h
0x1400f1811  pop     r14
0x1400f1813  pop     rdi
0x1400f1814  pop     rbp
0x1400f1815  retn
0x1400f1817  mov     rcx, rdi
0x1400f181a  call    Ipv4pReassembleDatagram
0x1400f181f  jmp     short loc_1400F17CD
0x1400f1821  mov     r8d, [rbx+8Ch]
0x1400f1828  movzx   edx, r12w
0x1400f182c  add     edx, ecx
0x1400f182e  cmp     r8d, 0FFFFFFFFh
0x1400f1832  jnz     loc_1400F1AA8
0x1400f1838  movzx   eax, word ptr [rbx+54h]
0x1400f183c  mov     [rbx+8Ch], edx
0x1400f1842  cmp     eax, edx
0x1400f1844  ja      short loc_1400F1852
0x1400f1846  movzx   eax, word ptr [rbx+56h]
0x1400f184a  cmp     eax, edx
0x1400f184c  jbe     loc_1400F15D6
0x1400f1852  mov     esi, 0Bh
0x1400f1857  lea     rcx, [r15+5750h]
0x1400f185e  movzx   r8d, r13b
0x1400f1862  mov     rdx, rbx
0x1400f1865  call    IppDeleteFromReassemblySet
0x1400f186a  nop
0x1400f186b  jmp     loc_1401D34E0
0x1400f1870  movzx   eax, byte ptr [rsi+9]
0x1400f1874  cmp     [rbx+99h], al
0x1400f187a  jnz     loc_1400F19AF
0x1400f1880  mov     rax, [rdi+8]
0x1400f1884  movzx   r13d, [rsp+0D8h+arg_0]
0x1400f188d  mov     ecx, [rax+110h]
0x1400f1893  cmp     [rbx+0C8h], ecx
0x1400f1899  jz      loc_1400F151C
0x1400f189f  mov     dword ptr [rbx+0C8h], 0
0x1400f18a9  jmp     loc_1400F151C
0x1400f18ae  cmp     word ptr [rbx+54h], 0
0x1400f18b3  jnz     loc_1400F156A
0x1400f18b9  movzx   eax, byte ptr [rsi]
0x1400f18bc  and     al, 0Fh
0x1400f18be  shl     al, 2
  ... truncated ...
```
