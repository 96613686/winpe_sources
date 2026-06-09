# Ipv4pReceiveFragment

- ea: `0x1400e9fc0`
- end: `0x1400ea7ef`
- name: `Ipv4pReceiveFragment`
- size: `2095`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400e9f60`

## callees

- `0x140053e98`
- `0x1400c8414`
- `0x1400e9fc0`
- `0x1400ea800`
- `0x1400eab6c`
- `0x1400ead1c`
- `0x1400eadb4`
- `0x1400eaef0`
- `0x1400eaf48`
- `0x1400eb044`
- `0x1400eb074`
- `0x1400eb4fc`
- `0x1400eb5d0`
- `0x1400ec024`
- `0x14014cf98`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400ea290`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ea290`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ea3aa`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ea3aa`
- `ntoskrnl!KeBugCheck` at `0x1400ea5dd`
- `ntoskrnl!KeBugCheck` at `0x1400ea5dd`
- `ntoskrnl!ExAllocatePool3` at `0x1400ea32d`
- `ntoskrnl!ExAllocatePool3` at `0x1401cf829`
- `ntoskrnl!ExAllocatePool3` at `0x1400ea32d`
- `ntoskrnl!ExAllocatePool3` at `0x1401cf829`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cf885`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cf885`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400ea3f5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1401cf8d8`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400ea3f5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1401cf8d8`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400ea1a6`
- `NETIO!WfpTransferReassemblyContextForFragments` at `0x1400ea1a6`

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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    LOBYTE(v44) = *((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 0x20;
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 13) & 0x20) != 0 )
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
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 14) & 0x10) != 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x1400e9fc0  mov     r11, rsp
0x1400e9fc3  push    rbp
0x1400e9fc4  push    rdi
0x1400e9fc5  push    r14
0x1400e9fc7  sub     rsp, 0C0h
0x1400e9fce  test    byte ptr [rcx+0B8h], 4
0x1400e9fd5  xorps   xmm0, xmm0
0x1400e9fd8  mov     r14, [rcx+8]
0x1400e9fdc  mov     rdi, rcx
0x1400e9fdf  mov     byte ptr [r11+8], 0
0x1400e9fe4  mov     dword ptr [r11+10h], 12h
0x1400e9fec  mov     rbp, [r14+8]
0x1400e9ff0  mov     qword ptr [r11-68h], 0
0x1400e9ff8  movups  [rsp+0D8h+var_60], xmm0
0x1400e9ffd  jnz     loc_1400EA5C8
0x1400ea003  mov     [r11-28h], rsi
0x1400ea007  mov     rsi, [rcx+118h]
0x1400ea00e  cmp     byte ptr [rsi+9], 2Ch ; ','
0x1400ea012  jz      loc_1400EA7DF
0x1400ea018  movzx   eax, byte ptr [rsi]
0x1400ea01b  and     al, 0Fh
0x1400ea01d  shl     al, 2
0x1400ea020  movzx   eax, al
0x1400ea023  cmp     [rcx+30h], eax
0x1400ea026  jnz     loc_1400EA7DF
0x1400ea02c  mov     rax, [rcx+0D8h]
0x1400ea033  mov     [r11-20h], rbx
0x1400ea037  mov     [r11-38h], r13
0x1400ea03b  mov     [r11-40h], r15
0x1400ea03f  mov     rbx, [rax+8]
0x1400ea043  mov     [rsp+0D8h+arg_18], rbx
0x1400ea04b  mov     rax, [rbx]
0x1400ea04e  mov     r15, [rax+28h]
0x1400ea052  mov     eax, gs:1A4h
0x1400ea05a  mov     ecx, eax
0x1400ea05c  mov     rax, [rbx+380h]
0x1400ea063  lea     rdx, [rcx+rcx*2]
0x1400ea067  mov     r13, [rax+rcx*8]
0x1400ea06b  mov     rcx, [r15+4F28h]
0x1400ea072  shl     rdx, 6
0x1400ea076  add     rcx, rdx
0x1400ea079  mov     [rsp+0D8h+var_70], r13
0x1400ea07e  mov     eax, [r13+0]
0x1400ea082  inc     eax
0x1400ea084  mov     [rsp+0D8h+var_78], rcx
0x1400ea089  mov     [r13+0], eax
0x1400ea08d  mov     eax, [rcx+84h]
0x1400ea093  inc     eax
0x1400ea095  mov     [rcx+84h], eax
0x1400ea09b  test    byte ptr [rdi+0B8h], 8
0x1400ea0a2  jnz     loc_1400EA5D8
0x1400ea0a8  cmp     dword ptr [r15+57BCh], 0
0x1400ea0b0  mov     [r11-30h], r12
0x1400ea0b4  jz      loc_1400EA5EA
0x1400ea0ba  mov     r9, [rdi+0E0h]
0x1400ea0c1  mov     eax, 0FF1Fh
0x1400ea0c6  movzx   ecx, word ptr [rsi+4]
0x1400ea0ca  movzx   edx, byte ptr [rdi+10h]
0x1400ea0ce  movzx   r12d, word ptr [rsi+6]
0x1400ea0d3  and     dl, 1
0x1400ea0d6  mov     r8, [rdi+0D8h]
0x1400ea0dd  and     r12w, ax
0x1400ea0e1  mov     eax, [rbp+18h]
0x1400ea0e4  mov     [rsp+0D8h+var_88], r14
0x1400ea0e9  mov     [rsp+0D8h+var_90], eax
0x1400ea0ed  mov     eax, [rdi+30h]
0x1400ea0f0  ror     r12w, 8
0x1400ea0f5  shl     r12w, 3
0x1400ea0fa  mov     [rsp+0D8h+var_98], r12w
0x1400ea100  mov     [rsp+0D8h+var_A0], ecx
0x1400ea104  xor     ecx, ecx
0x1400ea106  mov     [rsp+0D8h+var_A8], eax
0x1400ea10a  mov     eax, [r9+18h]
0x1400ea10e  mov     r9, [r9+8]
0x1400ea112  mov     byte ptr [rsp+0D8h+var_B0], dl
0x1400ea116  mov     rdx, [rdi+108h]
0x1400ea11d  mov     dword ptr [rsp+0D8h+NewIrql], eax
0x1400ea121  call    IppInspectFragmentIn
0x1400ea126  cmp     eax, 1
0x1400ea129  jge     loc_1400EA5F4
0x1400ea12f  movzx   edx, word ptr [rsi+4]
0x1400ea133  lea     r9, [rsp+0D8h+arg_0]
0x1400ea13b  mov     r8, rsi
0x1400ea13e  mov     rcx, rbx
0x1400ea141  call    Ipv4pFragmentLookup
0x1400ea146  mov     rbx, rax
0x1400ea149  test    rax, rax
0x1400ea14c  jnz     loc_1400EA4F0
0x1400ea152  movzx   r13d, [rsp+0D8h+arg_0]
0x1400ea15b  lea     rcx, [r15+5750h]; SpinLock
0x1400ea162  movzx   r9d, word ptr [rsi+4]
0x1400ea167  mov     r8, [rsp+0D8h+arg_18]
0x1400ea16f  mov     rdx, [rdi+118h]
0x1400ea176  mov     [rsp+0D8h+NewIrql], r13b; NewIrql
0x1400ea17b  call    IppCreateInReassemblySet
0x1400ea180  mov     rbx, rax
0x1400ea183  test    rax, rax
0x1400ea186  jz      loc_1400EA5FE
0x1400ea18c  mov     rax, [rdi+8]
0x1400ea190  mov     ecx, [rax+110h]
0x1400ea196  mov     [rbx+0C8h], ecx
0x1400ea19c  mov     rdx, [rbx+0D0h]
0x1400ea1a3  mov     rcx, r14
0x1400ea1a6  call    cs:__imp_WfpTransferReassemblyContextForFragments
0x1400ea1ad  nop     dword ptr [rax+rax+00h]
0x1400ea1b2  test    eax, eax
0x1400ea1b4  js      loc_1400EA67B
0x1400ea1ba  mov     eax, [r14+88h]
0x1400ea1c1  and     eax, 0FFF00003h
0x1400ea1c6  or      [rbx+0B8h], eax
0x1400ea1cc  mov     eax, 1
0x1400ea1d1  movzx   ecx, byte ptr [rsi+1]
0x1400ea1d5  and     ecx, 3
0x1400ea1d8  shl     eax, cl
0x1400ea1da  or      [rbx+0B8h], eax
0x1400ea1e0  test    r12w, r12w
0x1400ea1e4  jz      loc_1400EA52E
0x1400ea1ea  mov     edx, 0FFEBh
0x1400ea1ef  movzx   ecx, r12w
0x1400ea1f3  add     ecx, [rbp+18h]
0x1400ea1f6  movzx   eax, dx
0x1400ea1f9  cmp     ecx, eax
0x1400ea1fb  ja      loc_1400EA6CD
0x1400ea201  mov     r8d, [r15+18h]
0x1400ea205  lea     rax, [rsi+10h]
0x1400ea209  lea     r9, [rsi+0Ch]
0x1400ea20d  mov     qword ptr [rsp+0D8h+NewIrql], rax
0x1400ea212  lea     rcx, [rbx+0C0h]
0x1400ea219  mov     rdx, r14
0x1400ea21c  call    IPsecVerifyFragment
0x1400ea221  test    eax, eax
0x1400ea223  js      loc_1400EA714
0x1400ea229  mov     ecx, [rbp+18h]
0x1400ea22c  test    ecx, ecx
0x1400ea22e  jz      loc_1400EA71E
0x1400ea234  test    byte ptr [rsi+6], 20h
0x1400ea238  jz      loc_1400EA4A1
0x1400ea23e  test    cl, 7
0x1400ea241  jnz     loc_1400EA73B
0x1400ea247  mov     edx, [rbx+8Ch]
0x1400ea24d  cmp     edx, 0FFFFFFFFh
0x1400ea250  jnz     loc_1400EA77E
0x1400ea256  movzx   r9d, word ptr [rbp+18h]; int
0x1400ea25b  lea     rax, [rsp+0D8h+arg_8]
0x1400ea263  mov     [rsp+0D8h+var_B0], rax; __int64
0x1400ea268  movzx   r8d, r12w; int
0x1400ea26c  mov     rdx, rbx; int
0x1400ea26f  mov     [rsp+0D8h+NewIrql], r13b; NewIrql
0x1400ea274  mov     rcx, r15; int
0x1400ea277  call    IppReassemblyFindLocation
0x1400ea27c  mov     r13, rax
0x1400ea27f  test    rax, rax
0x1400ea282  jz      loc_1400EA7D3
0x1400ea288  mov     edx, [rbp+18h]; Length
0x1400ea28b  mov     ecx, 0FFFh; Base
0x1400ea290  call    cs:__imp_MmSizeOfMdl
0x1400ea297  nop     dword ptr [rax+rax+00h]
0x1400ea29c  lea     r14, [rax+7]
0x1400ea2a0  and     r14, 0FFFFFFFFFFFFFFF8h
0x1400ea2a4  lea     r8, [r14+10h]
0x1400ea2a8  cmp     r8, 10h
0x1400ea2ac  jnb     short loc_1400EA2FA
0x1400ea2ae  movzx   r8d, [rsp+0D8h+arg_0]
0x1400ea2b7  lea     rcx, [r15+5750h]
0x1400ea2be  mov     rdx, rbx
0x1400ea2c1  mov     esi, 3
0x1400ea2c6  call    IppDeleteFromReassemblySet
0x1400ea2cb  mov     r13, [rsp+0D8h+var_70]
0x1400ea2d0  mov     rbx, [rsp+0D8h+arg_18]
0x1400ea2d8  mov     rcx, [rsp+0D8h+var_78]
0x1400ea2dd  mov     eax, [r13+8]
0x1400ea2e1  inc     eax
0x1400ea2e3  mov     [r13+8], eax
0x1400ea2e7  mov     eax, [rcx+8Ch]
0x1400ea2ed  inc     eax
0x1400ea2ef  mov     [rcx+8Ch], eax
0x1400ea2f5  jmp     loc_1401CF8F2
0x1400ea2fa  mov     edx, [rbp+18h]
0x1400ea2fd  add     rdx, r8
0x1400ea300  cmp     rdx, r8
0x1400ea303  jb      short loc_1400EA2AE
0x1400ea305  xor     ecx, ecx
0x1400ea307  lea     r9, [rsp+0D8h+var_60]
0x1400ea30c  mov     eax, 1
0x1400ea311  mov     qword ptr [rsp+0D8h+var_60+8], rcx
0x1400ea319  mov     ecx, 42h ; 'B'
0x1400ea31e  mov     qword ptr [rsp+0D8h+var_60], rax
0x1400ea323  mov     r8d, 65725049h
0x1400ea329  mov     dword ptr [rsp+0D8h+NewIrql], eax
0x1400ea32d  call    cs:__imp_ExAllocatePool3
0x1400ea334  nop     dword ptr [rax+rax+00h]
0x1400ea339  test    rax, rax
0x1400ea33c  jz      loc_1400EA791
0x1400ea342  mov     r9d, [rbp+18h]
0x1400ea346  lea     rcx, [rax+10h]; MemoryDescriptorList
0x1400ea34a  lea     r10, [r14+10h]
0x1400ea34e  mov     qword ptr [rcx], 0
0x1400ea355  add     r10, rax
0x1400ea358  mov     [rcx+28h], r9d
0x1400ea35c  mov     r14, rax
0x1400ea35f  mov     [rsp+0D8h+arg_10], r10
0x1400ea367  mov     r8d, r10d
0x1400ea36a  lea     rdx, [r9+0FFFh]
0x1400ea371  mov     eax, r8d
0x1400ea374  and     r8d, 0FFFh
0x1400ea37b  and     eax, 0FFFh
0x1400ea380  mov     [rcx+2Ch], r8d
0x1400ea384  add     rdx, rax
0x1400ea387  xor     eax, eax
0x1400ea389  shr     rdx, 0Ch
0x1400ea38d  mov     [rcx+0Ah], ax
0x1400ea391  add     dx, 6
0x1400ea395  mov     rax, r10
0x1400ea398  shl     dx, 3
0x1400ea39c  and     rax, 0FFFFFFFFFFFFF000h
0x1400ea3a2  mov     [rcx+8], dx
0x1400ea3a6  mov     [rcx+20h], rax
0x1400ea3aa  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400ea3b1  nop     dword ptr [rax+rax+00h]
0x1400ea3b6  movzx   eax, word ptr [rbp+18h]
0x1400ea3ba  mov     [r14+8], ax
0x1400ea3bf  lea     rax, [rbx+60h]
0x1400ea3c3  mov     [r14+0Ah], r12w
0x1400ea3c8  mov     qword ptr [r14], 0
0x1400ea3cf  cmp     r13, rax
0x1400ea3d2  jz      loc_1400EA54C
0x1400ea3d8  mov     r9d, [rbp+18h]
0x1400ea3dc  lea     rax, [rsp+0D8h+var_68]
0x1400ea3e1  mov     edx, [rbp+28h]
0x1400ea3e4  mov     r8, [rsp+0D8h+arg_10]
0x1400ea3ec  mov     rcx, [rbp+20h]
0x1400ea3f0  mov     qword ptr [rsp+0D8h+NewIrql], rax
0x1400ea3f5  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x1400ea3fc  nop     dword ptr [rax+rax+00h]
0x1400ea401  mov     r8, r14
0x1400ea404  mov     rdx, r13
0x1400ea407  mov     rcx, rbx
0x1400ea40a  call    IppReassemblyInsertFragment
0x1400ea40f  mov     r9d, [rbp+18h]
0x1400ea413  lea     rcx, [r15+5750h]
0x1400ea41a  mov     rdx, rbx
0x1400ea41d  lea     r8d, [r9+100h]
0x1400ea424  call    IppIncreaseReassemblySize
0x1400ea429  movzx   eax, word ptr [rbx+54h]
0x1400ea42d  mov     rdx, rbx
0x1400ea430  movzx   r8d, [rsp+0D8h+arg_0]
0x1400ea439  cmp     eax, [rbx+8Ch]
0x1400ea43f  jz      short loc_1400EA497
0x1400ea441  lea     rcx, [r15+5750h]; SpinLock
0x1400ea448  call    IppCheckReassemblyQuota
0x1400ea44d  mov     rax, [rdi+8]
0x1400ea451  mov     dword ptr [rax+8Ch], 0C0000240h
0x1400ea45b  mov     r12, [rsp+0D8h+var_30]
0x1400ea463  mov     r13, [rsp+0D8h+var_38]
0x1400ea46b  mov     rbx, [rsp+0D8h+var_20]
0x1400ea473  mov     r15, [rsp+0D8h+var_40]
0x1400ea47b  mov     dword ptr [rdi+2Ch], 3Bh ; ';'
0x1400ea482  mov     rsi, [rsp+0D8h+var_28]
0x1400ea48a  add     rsp, 0C0h
0x1400ea491  pop     r14
0x1400ea493  pop     rdi
0x1400ea494  pop     rbp
0x1400ea495  retn
0x1400ea497  mov     rcx, rdi
0x1400ea49a  call    Ipv4pReassembleDatagram
0x1400ea49f  jmp     short loc_1400EA44D
0x1400ea4a1  mov     r8d, [rbx+8Ch]
0x1400ea4a8  movzx   edx, r12w
0x1400ea4ac  add     edx, ecx
0x1400ea4ae  cmp     r8d, 0FFFFFFFFh
0x1400ea4b2  jnz     loc_1400EA728
0x1400ea4b8  movzx   eax, word ptr [rbx+54h]
0x1400ea4bc  mov     [rbx+8Ch], edx
0x1400ea4c2  cmp     eax, edx
0x1400ea4c4  ja      short loc_1400EA4D2
0x1400ea4c6  movzx   eax, word ptr [rbx+56h]
0x1400ea4ca  cmp     eax, edx
0x1400ea4cc  jbe     loc_1400EA256
0x1400ea4d2  mov     esi, 0Bh
0x1400ea4d7  lea     rcx, [r15+5750h]
0x1400ea4de  movzx   r8d, r13b
0x1400ea4e2  mov     rdx, rbx
0x1400ea4e5  call    IppDeleteFromReassemblySet
0x1400ea4ea  nop
0x1400ea4eb  jmp     loc_1401CF8EA
0x1400ea4f0  movzx   eax, byte ptr [rsi+9]
0x1400ea4f4  cmp     [rbx+99h], al
0x1400ea4fa  jnz     loc_1400EA62F
0x1400ea500  mov     rax, [rdi+8]
0x1400ea504  movzx   r13d, [rsp+0D8h+arg_0]
0x1400ea50d  mov     ecx, [rax+110h]
0x1400ea513  cmp     [rbx+0C8h], ecx
0x1400ea519  jz      loc_1400EA19C
0x1400ea51f  mov     dword ptr [rbx+0C8h], 0
0x1400ea529  jmp     loc_1400EA19C
0x1400ea52e  cmp     word ptr [rbx+54h], 0
0x1400ea533  jnz     loc_1400EA1EA
0x1400ea539  movzx   eax, byte ptr [rsi]
0x1400ea53c  and     al, 0Fh
0x1400ea53e  shl     al, 2
  ... truncated ...
```
