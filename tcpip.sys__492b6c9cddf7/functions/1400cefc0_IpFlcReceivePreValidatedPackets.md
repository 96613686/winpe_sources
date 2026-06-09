# IpFlcReceivePreValidatedPackets

- ea: `0x1400cefc0`
- end: `0x1400cfb0c`
- name: `IpFlcReceivePreValidatedPackets`
- size: `2892`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ce290`
- `0x1401499bc`
- `0x1401abc60`

## callees

- `0x14002f4f0`
- `0x1400300f0`
- `0x140030580`
- `0x140039910`
- `0x1400615f0`
- `0x14006ddb0`
- `0x14006f8d0`
- `0x140091840`
- `0x1400c9640`
- `0x1400cefc0`
- `0x1400d01e0`
- `0x14014cdc4`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cf06d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cf06d`
- `ntoskrnl!KfRaiseIrql` at `0x1400cf0fe`
- `ntoskrnl!KfRaiseIrql` at `0x1400cf56e`
- `ntoskrnl!KfRaiseIrql` at `0x1400cf0fe`
- `ntoskrnl!KfRaiseIrql` at `0x1400cf56e`
- `ntoskrnl!KeLowerIrql` at `0x1400cf560`
- `ntoskrnl!KeLowerIrql` at `0x1400cf9c6`
- `ntoskrnl!KeLowerIrql` at `0x1400cfad3`
- `ntoskrnl!KeLowerIrql` at `0x1400cf560`
- `ntoskrnl!KeLowerIrql` at `0x1400cf9c6`
- `ntoskrnl!KeLowerIrql` at `0x1400cfad3`
- `ntoskrnl!KeShouldYieldProcessor` at `0x1400cf540`
- `ntoskrnl!KeShouldYieldProcessor` at `0x1400cf540`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cf09a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cf09a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cf0d8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cf0d8`
- `NETIO!KfdIsLayerEmpty` at `0x1400cf136`
- `NETIO!KfdIsLayerEmpty` at `0x1400cf136`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400cf040`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400cf040`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cf71a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cfa5d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cf71a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cfa5d`

## pseudocode

```c
void __fastcall IpFlcReceivePreValidatedPackets(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r13
  __int64 v3; // r15
  _QWORD *v4; // rsi
  __int64 *v5; // r14
  __int64 v6; // rax
  __int64 v7; // rax
  __int16 v8; // r12
  __int64 v9; // rcx
  ULONG v10; // edi
  __int64 v11; // rbx
  unsigned int v12; // r15d
  __int64 v13; // r12
  __int64 v14; // r8
  __int64 v15; // r13
  _QWORD *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // r14
  signed __int32 v19; // eax
  __int64 (__fastcall *v20)(__int64); // rax
  __int64 v21; // rdi
  unsigned int v22; // ebx
  _DWORD *AddressInAddressSet; // rsi
  _DWORD *NextHopInFwdCacheOrRouteTable; // rax
  _QWORD *v25; // rax
  unsigned int j; // ebx
  int v27; // eax
  _BYTE *v28; // r9
  int v29; // ebx
  _QWORD *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r10
  __int64 v34; // r11
  __int64 v35; // rcx
  __int64 v36; // r13
  _QWORD *v37; // r12
  __int64 v38; // r15
  __int64 v39; // rdi
  bool v40; // al
  int ExternalScopeId; // eax
  _QWORD *v42; // rcx
  bool v43; // al
  char v44; // r15
  __int64 v45; // r10
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  KIRQL v49; // cl
  _BYTE *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdi
  signed __int32 v53; // eax
  unsigned int v54; // edi
  _DWORD *v55; // rax
  int v56; // eax
  int v57; // ecx
  unsigned int v58; // r15d
  __int64 v59; // rdx
  _QWORD *v60; // rcx
  __int64 v61; // r9
  unsigned int v62; // r13d
  _BYTE *v63; // rdi
  char v64; // al
  int v65; // eax
  _QWORD *v66; // r12
  int IsEnabledDeviceUsageNoInline; // eax
  _QWORD *v68; // r15
  unsigned __int8 v69; // al
  unsigned __int8 v70; // r11
  _BYTE *v71; // rbx
  __int64 v72; // r8
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  ULONG v77; // esi
  struct _NET_BUFFER *v78; // rcx
  ULONG v79; // edx
  _QWORD *v80; // rax
  int v81; // [rsp+30h] [rbp-F8h]
  __int16 v82; // [rsp+40h] [rbp-E8h]
  unsigned __int8 v83; // [rsp+42h] [rbp-E6h]
  char v84; // [rsp+43h] [rbp-E5h]
  unsigned __int8 v85; // [rsp+43h] [rbp-E5h]
  char v86; // [rsp+44h] [rbp-E4h]
  unsigned int LockArray_high; // [rsp+48h] [rbp-E0h]
  _QWORD *v88; // [rsp+50h] [rbp-D8h]
  _QWORD *v89; // [rsp+58h] [rbp-D0h] BYREF
  unsigned int v90; // [rsp+60h] [rbp-C8h]
  unsigned int v91; // [rsp+64h] [rbp-C4h]
  _BYTE *v92; // [rsp+68h] [rbp-C0h]
  PVOID Context; // [rsp+70h] [rbp-B8h]
  __int64 v94; // [rsp+78h] [rbp-B0h]
  unsigned int v95; // [rsp+80h] [rbp-A8h]
  ULONG DataOffsetDelta; // [rsp+84h] [rbp-A4h]
  _QWORD *v97; // [rsp+88h] [rbp-A0h]
  unsigned int v98; // [rsp+90h] [rbp-98h]
  int v99; // [rsp+94h] [rbp-94h]
  __int64 v100; // [rsp+98h] [rbp-90h]
  _QWORD *v101; // [rsp+A0h] [rbp-88h] BYREF
  _QWORD *v102; // [rsp+A8h] [rbp-80h]
  __int64 v103; // [rsp+B0h] [rbp-78h]
  __int64 v104; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v105; // [rsp+C0h] [rbp-68h]
  __int64 v106; // [rsp+C8h] [rbp-60h]
  __int64 v107; // [rsp+D0h] [rbp-58h]
  __int64 v108; // [rsp+D8h] [rbp-50h]
  __int64 i; // [rsp+E0h] [rbp-48h]
  _QWORD *v111; // [rsp+138h] [rbp+10h] BYREF
  KIRQL v112; // [rsp+140h] [rbp+18h]
  unsigned __int8 v113; // [rsp+148h] [rbp+20h]

  v111 = a2;
  v2 = a1;
  v88 = a2;
  HIDWORD(v3) = HIDWORD(a2);
  v4 = 0;
  v101 = 0;
  v5 = *(__int64 **)(a1 + 8);
  v104 = 0;
  v89 = 0;
  v86 = 0;
  v6 = *v5;
  v97 = v5;
  v7 = *(_QWORD *)(v6 + 40);
  v94 = v7;
  v8 = *(_WORD *)(v7 + 28);
  v82 = v8;
  if ( TcpipNblTrackerEnabled )
    NdisNblTrackerTransferOwnership(a2, 0, *(_QWORD *)(v7 + 23032), 157, 0);
  v9 = v5[12];
  v10 = *(unsigned __int8 *)v5[6];
  if ( v9
    && !*(_BYTE *)(v9 + 40)
    && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v9 + 16), 1u) )
  {
    IppIndicatePrevalidatedPacketsToIpsServiceChain(v2, &v111);
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v5[12] + 16), 1u);
    HIDWORD(v3) = HIDWORD(v111);
    v88 = v111;
    if ( !v111 )
      return;
    v86 = 1;
  }
  DataOffsetDelta = v10;
  if ( KeGetCurrentIrql() < 2u )
  {
    v83 = 0;
    v112 = KfRaiseIrql(2u);
  }
  else
  {
    v112 = 2;
    v83 = 1;
  }
  LODWORD(v3) = HIDWORD(KeGetPcr()[1].LockArray);
  LockArray_high = v3;
  v11 = 18LL * (v8 & 1);
  if ( !(unsigned int)KfdIsLayerEmpty(*(unsigned __int16 *)&AddressFamilyInformation[v11 + 8])
    || (v92 = (_BYTE *)*((_QWORD *)qword_140224858 + v3), *v92)
    || *((_DWORD *)v5 + 104)
    || (v5[49] & 1) != 0 )
  {
    v16 = v88;
    goto LABEL_26;
  }
  v12 = (unsigned __int8)AddressFamilyInformation[v11 + 2];
  v13 = (unsigned __int8)AddressFamilyInformation[v11 + 6];
  v14 = (unsigned __int8)AddressFamilyInformation[v11 + 7];
  v15 = (unsigned __int8)AddressFamilyInformation[v11 + 5];
  v16 = v88;
  v106 = (unsigned __int8)AddressFamilyInformation[v11 + 4];
  v17 = v88[14];
  v113 = *(_BYTE *)(v17 + v106);
  v18 = v94 + 72 * (v113 + 7LL);
  Context = *(PVOID *)(v18 + 56);
  do
  {
    v19 = *(_DWORD *)(v18 + 52);
    if ( (v19 & 1) != 0 )
      goto LABEL_24;
  }
  while ( v19 != _InterlockedCompareExchange((volatile signed __int32 *)(v18 + 52), v19 + 2, v19) );
  v20 = *(__int64 (__fastcall **)(__int64))(v94 + 176);
  v21 = v14 + v17;
  v105 = v14;
  v22 = v20(v14 + v17);
  if ( !*(_BYTE *)(v94 + 19729)
    || ((v22 - 1) & 0xFFFFFFFD) != 0
    || (AddressInAddressSet = (_DWORD *)IppFindAddressInAddressSet(v97, v21, v22)) == 0 )
  {
    NextHopInFwdCacheOrRouteTable = (_DWORD *)IppFindNextHopInFwdCacheOrRouteTable(*v97, (_DWORD)v97, 0, v21, v22);
    AddressInAddressSet = NextHopInFwdCacheOrRouteTable;
    if ( !NextHopInFwdCacheOrRouteTable )
    {
LABEL_22:
      IppDereferenceNlClient(Context);
      goto LABEL_23;
    }
    v27 = *NextHopInFwdCacheOrRouteTable;
    if ( v27 != 1634496585 )
    {
      if ( v27 == 1701736521 )
        IppDereferenceNeighbor(AddressInAddressSet);
      goto LABEL_22;
    }
  }
  if ( ((AddressInAddressSet[6] - 1) & 0xFFFFFFFD) != 0 )
  {
    IppDereferenceLocalAddress(AddressInAddressSet);
    goto LABEL_22;
  }
  v28 = v92;
  v29 = 0;
  v30 = v88;
  v31 = 0;
  v90 = 0;
  v32 = 0;
  v91 = 0;
  *v92 = 1;
  v33 = v15;
  v95 = 0;
  v34 = v13;
  v98 = v12;
  v100 = 0;
  v108 = v15;
  for ( i = v13; ; v34 = i )
  {
    v35 = v30[14];
    v36 = v30[1];
    v102 = v30;
    v37 = (_QWORD *)(v35 + v105);
    v38 = v34 + v35;
    v84 = *(_BYTE *)(v33 + v35);
    v99 = *(_DWORD *)(v36 + 92);
    v107 = v35;
    v103 = v34 + v35;
    v39 = *(unsigned __int8 *)(v35 + v106);
    if ( !v32
      || (v82 != 23
        ? (v40 = *(_DWORD *)v32 == *(_DWORD *)v38)
        : *(_QWORD *)(v32 + 8) != *(_QWORD *)(v38 + 8) || *(_QWORD *)v32 != *(_QWORD *)v38
        ? (v40 = 0)
        : (v40 = 1),
          !v40) )
    {
      ExternalScopeId = IppGetExternalScopeId(v97, v38);
      v31 = v90;
      v29 = ExternalScopeId;
      v28 = v92;
      v100 = v38;
    }
    v42 = (_QWORD *)**((_QWORD **)AddressInAddressSet + 2);
    if ( v82 == 23 )
      v43 = v42[1] == v37[1] && *v42 == *v37;
    else
      v43 = *(_DWORD *)v42 == *(_DWORD *)v37;
    if ( v43 )
    {
      v44 = 0;
      if ( (_BYTE)v39 == v113 && (_DWORD)v31 != 32 )
        goto LABEL_77;
    }
    else
    {
      v44 = 1;
    }
    *(_QWORD *)&v28[160 * (unsigned int)(v31 - 1) + 8] = 0;
    IppDeliverPreValidatedListToProtocol(
      v18,
      (_DWORD)v28 + 8,
      v31,
      (_DWORD)v28,
      (__int64)&v89,
      (__int64)&v101,
      v81,
      (__int64)&v104);
    v45 = v90;
    if ( v86 )
    {
      v31 = v94;
      v48 = 192LL * LockArray_high;
    }
    else
    {
      v46 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
      *(_QWORD *)(v46 + 48) += v90;
      v47 = v91;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high) + 56LL) += v91;
      v31 = v94;
      v48 = 192LL * LockArray_high;
      *(_QWORD *)(*(_QWORD *)(v94 + 20264) + v48) += v45;
      *(_QWORD *)(*(_QWORD *)(v31 + 20264) + v48 + 8) += v47;
    }
    *(_QWORD *)(v48 + *(_QWORD *)(v31 + 20264) + 24) += v45;
    if ( v89 )
    {
      IppDereferenceNlClient(Context);
      goto LABEL_114;
    }
    if ( !v83 )
    {
      v95 += v45;
      if ( v95 >= 0x20 )
      {
        if ( KeShouldYieldProcessor() )
        {
          v49 = v112;
          *v92 = 0;
          KeLowerIrql(v49);
          v112 = KfRaiseIrql(2u);
          LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
          v50 = (_BYTE *)*((_QWORD *)qword_140224858 + LockArray_high);
          v92 = v50;
          if ( *v50 )
          {
            v4 = v89;
            LODWORD(v3) = LockArray_high;
LABEL_112:
            v16 = v88;
            goto LABEL_25;
          }
          *v50 = 1;
          v95 = 0;
        }
      }
    }
    if ( (_BYTE)v39 != v113 )
    {
      v113 = v39;
      IppDereferenceNlClient(Context);
      v51 = v39 + 7;
      v52 = v94;
      v18 = v94 + 72 * v51;
      Context = *(PVOID *)(v18 + 56);
      while ( 1 )
      {
        v53 = *(_DWORD *)(v18 + 52);
        if ( (v53 & 1) != 0 )
          break;
        if ( v53 == _InterlockedCompareExchange((volatile signed __int32 *)(v18 + 52), v53 + 2, v53) )
          goto LABEL_70;
      }
LABEL_114:
      IppDereferenceLocalAddress(AddressInAddressSet);
      *v92 = 0;
LABEL_23:
      v4 = v89;
      v16 = v88;
LABEL_24:
      LODWORD(v3) = LockArray_high;
LABEL_25:
      v8 = v82;
      v2 = a1;
LABEL_26:
      if ( DataOffsetDelta )
      {
        j = 0;
        if ( v16 )
        {
          v77 = DataOffsetDelta;
          do
          {
            v78 = (struct _NET_BUFFER *)v16[1];
            v16[14] = 0;
            v79 = v77 + v78->CurrentMdlOffset;
            if ( v79 >= *(_DWORD *)(v78->Link.Region + 40) )
            {
              NdisAdvanceNetBufferDataStart(v78, v77, 0, 0);
            }
            else
            {
              v78->DataOffset += v77;
              v78->DataLength -= v77;
              v78->CurrentMdlOffset = v79;
            }
            v16 = (_QWORD *)*v16;
            ++j;
          }
          while ( v16 );
          v4 = v89;
        }
        v16 = v88;
      }
      else
      {
        v25 = v16;
        for ( j = 0; v25; v25 = (_QWORD *)*v25 )
        {
          v25[14] = 0;
          ++j;
        }
      }
      if ( v4 )
      {
        v80 = v4;
        do
        {
          v80 = (_QWORD *)*v80;
          ++j;
        }
        while ( v80 );
        *v101 = v16;
        v16 = v4;
      }
      if ( TcpipGlobalCounters && v8 == 2 )
        *((_QWORD *)TcpipGlobalCounters + 40 * (unsigned int)v3 + 3) += j;
      if ( !v83 )
        KeLowerIrql(v112);
      IppReceivePackets(v2, v16, v83, 0);
      return;
    }
    v52 = v94;
LABEL_70:
    v100 = 0;
    v91 = 0;
    v90 = 0;
    if ( v44 )
    {
      IppDereferenceLocalAddress(AddressInAddressSet);
      v54 = (*(__int64 (__fastcall **)(_QWORD *))(v52 + 176))(v37);
      if ( !*(_BYTE *)(v94 + 19729)
        || ((v54 - 1) & 0xFFFFFFFD) != 0
        || (AddressInAddressSet = (_DWORD *)IppFindAddressInAddressSet(v97, v37, v54)) == 0 )
      {
        v55 = (_DWORD *)IppFindNextHopInFwdCacheOrRouteTable(*v97, (_DWORD)v97, 0, (_DWORD)v37, v54);
        AddressInAddressSet = v55;
        if ( !v55 )
          goto LABEL_102;
        v56 = *v55;
        if ( v56 != 1634496585 )
        {
          if ( v56 == 1701736521 )
            IppDereferenceNeighbor(AddressInAddressSet);
          goto LABEL_102;
        }
      }
      if ( ((AddressInAddressSet[6] - 1) & 0xFFFFFFFD) != 0 )
      {
        IppDereferenceLocalAddress(AddressInAddressSet);
LABEL_102:
        IppDereferenceNlClient(Context);
        *v92 = 0;
        goto LABEL_23;
      }
    }
LABEL_77:
    v57 = *(_DWORD *)(v36 + 24);
    v91 += v57 - DataOffsetDelta;
    v58 = v98 + ((unsigned __int16)v99 >> 10);
    v59 = v58 + DataOffsetDelta;
    if ( v58 + DataOffsetDelta )
    {
      v31 = (unsigned int)(v59 + *(_DWORD *)(v36 + 16));
      if ( (unsigned int)v31 >= *(_DWORD *)(*(_QWORD *)(v36 + 8) + 40LL) )
      {
        NdisAdvanceNetBufferDataStart((PNET_BUFFER)v36, v59, 0, 0);
      }
      else
      {
        *(_DWORD *)(v36 + 40) += v59;
        *(_DWORD *)(v36 + 16) = v31;
        *(_DWORD *)(v36 + 24) = v57 - v59;
      }
    }
    v60 = v102;
    v61 = v103;
    v62 = v90 + 1;
    v63 = &v92[160 * v90++];
    *((_QWORD *)v63 + 2) = v102;
    *((_QWORD *)v63 + 1) = v63 + 168;
    v64 = v63[24];
    v63[25] = 0;
    *((_DWORD *)v63 + 7) = v29;
    v63[24] = v64 & 0xF6 | 8;
    *((_QWORD *)v63 + 4) = v61;
    *((_QWORD *)v63 + 5) = AddressInAddressSet;
    if ( AddressInAddressSet[6] == 1 )
      v65 = AddressInAddressSet[47];
    else
      v65 = 0;
    v66 = v97;
    *((_DWORD *)v63 + 12) = v65;
    *((_DWORD *)v63 + 13) = v113;
    *((_DWORD *)v63 + 14) = v58;
    *((_QWORD *)v63 + 8) = v66;
    *((_DWORD *)v63 + 18) = *(_DWORD *)(a1 + 24);
    if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    {
      IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_featureState & 1;
    }
    else
    {
      IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline(v60, v59, v31);
      v60 = v102;
      v61 = v103;
    }
    if ( IsEnabledDeviceUsageNoInline )
      *((_QWORD *)v63 + 10) = v107;
    *((_QWORD *)v63 + 11) = v60[14] + v98;
    *((_QWORD *)v63 + 12) = 0;
    v68 = (_QWORD *)*v88;
    v30 = v68;
    *v60 = 0;
    v60[14] = 0;
    *((_DWORD *)v60 + 35) = 261;
    v88 = v68;
    if ( AddressInAddressSet[6] == 1 )
    {
      v69 = v84 & 0x1F;
      v85 = v69;
      if ( v69 < *((_BYTE *)v66 + 451) && v69 )
      {
        if ( *AddressInAddressSet != 1634496585 )
          goto LABEL_97;
        if ( !(unsigned __int8)HasPrefix(
                                 v61,
                                 **((_QWORD **)AddressInAddressSet + 2),
                                 (unsigned int)AddressInAddressSet[47]) )
        {
          v69 = v85;
          goto LABEL_97;
        }
        v69 = 31;
        if ( v70 > 0x1Fu )
LABEL_97:
          *((_BYTE *)v66 + 451) = v69;
      }
      v30 = v68;
    }
    v31 = v62;
    if ( !v68 )
      break;
    v32 = v100;
    v28 = v92;
    v33 = v108;
  }
  v71 = v92;
  *((_QWORD *)v63 + 1) = 0;
  IppDeliverPreValidatedListToProtocol(
    v18,
    (_DWORD)v71 + 8,
    v62,
    v61,
    (__int64)&v89,
    (__int64)&v101,
    v81,
    (__int64)&v104);
  LODWORD(v3) = LockArray_high;
  v72 = v94;
  if ( v86 )
  {
    v76 = 192LL * LockArray_high;
  }
  else
  {
    v73 = v91;
    v74 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
    *(_QWORD *)(v74 + 48) += v62;
    v75 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
    *(_QWORD *)(v75 + 56) += v73;
    v76 = 192LL * LockArray_high;
    *(_QWORD *)(v76 + *(_QWORD *)(v72 + 20264)) += v62;
    *(_QWORD *)(v76 + *(_QWORD *)(v72 + 20264) + 8) += v73;
  }
  *(_QWORD *)(*(_QWORD *)(v72 + 20264) + v76 + 24) += v62;
  IppDereferenceLocalAddress(AddressInAddressSet);
  IppDereferenceNlClient(Context);
  v4 = v89;
  *v71 = 0;
  if ( v4 )
    goto LABEL_112;
  if ( !v83 )
    KeLowerIrql(v112);
}

```

## disassembly

```asm
0x1400cefc0  mov     rax, rsp
0x1400cefc3  mov     [rax+10h], rdx
0x1400cefc7  mov     [rax+8], rcx
0x1400cefcb  push    rsi
0x1400cefcc  push    rdi
0x1400cefcd  push    r12
0x1400cefcf  push    r13
0x1400cefd1  push    r14
0x1400cefd3  push    r15
0x1400cefd5  sub     rsp, 0F8h
0x1400cefdc  mov     r13, rcx
0x1400cefdf  mov     [rsp+128h+var_D8], rdx
0x1400cefe4  xor     ecx, ecx
0x1400cefe6  mov     r15, rdx
0x1400cefe9  cmp     cs:TcpipNblTrackerEnabled, cl
0x1400cefef  mov     esi, ecx
0x1400ceff1  mov     [rax-88h], rcx
0x1400ceff8  mov     r14, [r13+8]
0x1400ceffc  mov     [rax-70h], rcx
0x1400cf000  mov     [rsp+128h+var_D0], rcx
0x1400cf005  mov     [rsp+128h+var_E4], cl
0x1400cf009  mov     rax, [r14]
0x1400cf00c  mov     [rsp+128h+var_A0], r14
0x1400cf014  mov     rax, [rax+28h]
0x1400cf018  mov     [rsp+128h+var_B0], rax
0x1400cf01d  movzx   r12d, word ptr [rax+1Ch]
0x1400cf022  mov     [rsp+128h+var_E8], r12w
0x1400cf028  jz      short loc_1400CF04C
0x1400cf02a  mov     r8, [rax+59F8h]
0x1400cf031  mov     r9d, 9Dh
0x1400cf037  mov     dword ptr [rsp+128h+var_108], ecx
0x1400cf03b  xor     edx, edx
0x1400cf03d  mov     rcx, r15
0x1400cf040  call    cs:__imp_NdisNblTrackerTransferOwnership
0x1400cf047  nop     dword ptr [rax+rax+00h]
0x1400cf04c  mov     rax, [r14+30h]
0x1400cf050  mov     rcx, [r14+60h]
0x1400cf054  movzx   edi, byte ptr [rax]
0x1400cf057  test    rcx, rcx
0x1400cf05a  jz      short loc_1400CF0C1
0x1400cf05c  movzx   eax, byte ptr [rcx+28h]
0x1400cf060  test    al, al
0x1400cf062  jnz     short loc_1400CF0C1
0x1400cf064  mov     rcx, [rcx+10h]; RunRefCacheAware
0x1400cf068  mov     edx, 1; Count
0x1400cf06d  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400cf074  nop     dword ptr [rax+rax+00h]
0x1400cf079  test    al, al
0x1400cf07b  jz      short loc_1400CF0C1
0x1400cf07d  lea     rdx, [rsp+128h+arg_8]
0x1400cf085  mov     rcx, r13
0x1400cf088  call    IppIndicatePrevalidatedPacketsToIpsServiceChain
0x1400cf08d  mov     rcx, [r14+60h]
0x1400cf091  mov     edx, 1; Count
0x1400cf096  mov     rcx, [rcx+10h]; RunRef
0x1400cf09a  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400cf0a1  nop     dword ptr [rax+rax+00h]
0x1400cf0a6  mov     r15, [rsp+128h+arg_8]
0x1400cf0ae  mov     [rsp+128h+var_D8], r15
0x1400cf0b3  test    r15, r15
0x1400cf0b6  jz      loc_1400CFAF9
0x1400cf0bc  mov     [rsp+128h+var_E4], 1
0x1400cf0c1  mov     [rsp+128h+var_38], rbx
0x1400cf0c9  movzx   ebx, r12w
0x1400cf0cd  and     bx, 1
0x1400cf0d1  mov     [rsp+128h+DataOffsetDelta], edi
0x1400cf0d8  call    cs:__imp_KeGetCurrentIrql
0x1400cf0df  nop     dword ptr [rax+rax+00h]
0x1400cf0e4  cmp     al, 2
0x1400cf0e6  jb      short loc_1400CF0F7
0x1400cf0e8  mov     [rsp+128h+arg_10], 2
0x1400cf0f0  mov     [rsp+128h+var_E6], 1
0x1400cf0f5  jmp     short loc_1400CF111
0x1400cf0f7  mov     cl, 2; NewIrql
0x1400cf0f9  mov     [rsp+128h+var_E6], sil
0x1400cf0fe  call    cs:__imp_KfRaiseIrql
0x1400cf105  nop     dword ptr [rax+rax+00h]
0x1400cf10a  mov     [rsp+128h+arg_10], al
0x1400cf111  mov     r15d, gs:1A4h
0x1400cf11a  lea     rdi, AddressFamilyInformation
0x1400cf121  movzx   ecx, bx
0x1400cf124  mov     [rsp+128h+var_E0], r15d
0x1400cf129  lea     rdx, [rcx+rcx*8]
0x1400cf12d  lea     rbx, [rdx+rdx]
0x1400cf131  movzx   ecx, word ptr [rbx+rdi+8]
0x1400cf136  call    cs:__imp_KfdIsLayerEmpty
0x1400cf13d  nop     dword ptr [rax+rax+00h]
0x1400cf142  test    eax, eax
0x1400cf144  jz      loc_1400CFA0A
0x1400cf14a  mov     rax, cs:qword_140224858
0x1400cf151  mov     rax, [rax+r15*8]
0x1400cf155  mov     [rsp+128h+var_C0], rax
0x1400cf15a  cmp     [rax], sil
0x1400cf15d  jnz     loc_1400CFA0A
0x1400cf163  cmp     [r14+1A0h], esi
0x1400cf16a  ja      loc_1400CFA0A
0x1400cf170  test    byte ptr [r14+188h], 1
0x1400cf178  jnz     loc_1400CFA0A
0x1400cf17e  movzx   r15d, byte ptr [rbx+rdi+2]
0x1400cf184  lea     rax, AddressFamilyInformation
0x1400cf18b  movzx   eax, byte ptr [rbx+rax+4]
0x1400cf190  movzx   r12d, byte ptr [rbx+rdi+6]
0x1400cf196  movzx   r8d, byte ptr [rbx+rdi+7]
0x1400cf19c  movzx   r13d, byte ptr [rbx+rdi+5]
0x1400cf1a2  mov     rdi, [rsp+128h+var_D8]
0x1400cf1a7  mov     r9, [rsp+128h+var_B0]
0x1400cf1ac  mov     [rsp+128h+var_60], rax
0x1400cf1b4  mov     rdx, [rdi+70h]
0x1400cf1b8  movzx   eax, byte ptr [rdx+rax]
0x1400cf1bc  mov     [rsp+128h+arg_18], al
0x1400cf1c3  add     rax, 7
0x1400cf1c7  lea     rax, [rax+rax*8]
0x1400cf1cb  lea     r14, [r9+rax*8]
0x1400cf1cf  mov     rax, [r9+rax*8+38h]
0x1400cf1d4  mov     [rsp+128h+Context], rax
0x1400cf1d9  nop     dword ptr [rax+00000000h]
0x1400cf1e0  mov     eax, [r14+34h]
0x1400cf1e4  test    al, 1
0x1400cf1e6  jnz     loc_1400CF285
0x1400cf1ec  lea     ecx, [rax+2]
0x1400cf1ef  lock cmpxchg [r14+34h], ecx
0x1400cf1f5  jnz     short loc_1400CF1E0
0x1400cf1f7  mov     rax, [r9+0B0h]
0x1400cf1fe  lea     rdi, [r8+rdx]
0x1400cf202  mov     rcx, rdi
0x1400cf205  mov     [rsp+128h+var_68], r8
0x1400cf20d  call    _guard_dispatch_icall
0x1400cf212  mov     ebx, eax
0x1400cf214  mov     rax, [rsp+128h+var_B0]
0x1400cf219  cmp     [rax+4D11h], sil
0x1400cf220  jz      short loc_1400CF24C
0x1400cf222  lea     ecx, [rbx-1]
0x1400cf225  test    ecx, 0FFFFFFFDh
0x1400cf22b  jnz     short loc_1400CF24C
0x1400cf22d  mov     rcx, [rsp+128h+var_A0]
0x1400cf235  mov     r8d, ebx
0x1400cf238  mov     rdx, rdi
0x1400cf23b  call    IppFindAddressInAddressSet
0x1400cf240  mov     rsi, rax
0x1400cf243  test    rax, rax
0x1400cf246  jnz     loc_1400CF2ED
0x1400cf24c  mov     rax, [rsp+128h+var_A0]
0x1400cf254  mov     r9, rdi
0x1400cf257  xor     r8d, r8d
0x1400cf25a  mov     dword ptr [rsp+128h+var_108], ebx
0x1400cf25e  mov     rdx, rax
0x1400cf261  mov     rcx, [rax]
0x1400cf264  call    IppFindNextHopInFwdCacheOrRouteTable
0x1400cf269  mov     rsi, rax
0x1400cf26c  test    rax, rax
0x1400cf26f  jnz     short loc_1400CF2D3
0x1400cf271  mov     rcx, [rsp+128h+Context]; Context
0x1400cf276  call    IppDereferenceNlClient
0x1400cf27b  mov     rsi, [rsp+128h+var_D0]
0x1400cf280  mov     rdi, [rsp+128h+var_D8]
0x1400cf285  mov     r15d, [rsp+128h+var_E0]
0x1400cf28a  movzx   r12d, [rsp+128h+var_E8]
0x1400cf290  mov     r13, [rsp+128h+arg_0]
0x1400cf298  cmp     [rsp+128h+DataOffsetDelta], 0
0x1400cf2a0  jnz     loc_1400CFA14
0x1400cf2a6  xor     ecx, ecx
0x1400cf2a8  mov     rax, rdi
0x1400cf2ab  mov     ebx, ecx
0x1400cf2ad  test    rdi, rdi
0x1400cf2b0  jz      loc_1400CFA7D
0x1400cf2b6  nop     word ptr [rax+rax+00000000h]
0x1400cf2c0  mov     [rax+70h], rcx
0x1400cf2c4  inc     ebx
0x1400cf2c6  mov     rax, [rax]
0x1400cf2c9  test    rax, rax
0x1400cf2cc  jnz     short loc_1400CF2C0
0x1400cf2ce  jmp     loc_1400CFA7D
0x1400cf2d3  mov     eax, [rax]
0x1400cf2d5  cmp     eax, 616C7049h
0x1400cf2da  jz      short loc_1400CF2ED
0x1400cf2dc  cmp     eax, 656E7049h
0x1400cf2e1  jnz     short loc_1400CF271
0x1400cf2e3  mov     rcx, rsi; P
0x1400cf2e6  call    IppDereferenceNeighbor
0x1400cf2eb  jmp     short loc_1400CF271
0x1400cf2ed  mov     eax, [rsi+18h]
0x1400cf2f0  dec     eax
0x1400cf2f2  test    eax, 0FFFFFFFDh
0x1400cf2f7  jz      short loc_1400CF306
0x1400cf2f9  mov     rcx, rsi
0x1400cf2fc  call    IppDereferenceLocalAddress
0x1400cf301  jmp     loc_1400CF271
0x1400cf306  mov     r9, [rsp+128h+var_C0]
0x1400cf30b  xor     ebx, ebx
0x1400cf30d  mov     rax, [rsp+128h+var_D8]
0x1400cf312  xor     r8d, r8d
0x1400cf315  xor     ecx, ecx
0x1400cf317  mov     [rsp+128h+var_C8], r8d
0x1400cf31c  xor     edx, edx
0x1400cf31e  mov     [rsp+128h+var_C4], ebx
0x1400cf322  mov     byte ptr [r9], 1
0x1400cf326  mov     r10, r13
0x1400cf329  mov     [rsp+128h+var_A8], ecx
0x1400cf330  mov     r11, r12
0x1400cf333  mov     [rsp+128h+var_98], r15d
0x1400cf33b  mov     [rsp+128h+var_90], rdx
0x1400cf343  mov     [rsp+128h+var_50], r13
0x1400cf34b  mov     [rsp+128h+var_48], r12
0x1400cf353  nop     dword ptr [rax+00h]
0x1400cf357  nop     word ptr [rax+rax+00000000h]
0x1400cf360  mov     rcx, [rax+70h]
0x1400cf364  mov     r13, [rax+8]
0x1400cf368  mov     r12, [rsp+128h+var_68]
0x1400cf370  mov     [rsp+128h+var_80], rax
0x1400cf378  add     r12, rcx
0x1400cf37b  movzx   eax, byte ptr [r10+rcx]
0x1400cf380  lea     r15, [r11+rcx]
0x1400cf384  mov     [rsp+128h+var_E5], al
0x1400cf388  mov     eax, [r13+5Ch]
0x1400cf38c  mov     [rsp+128h+var_94], eax
0x1400cf393  mov     rax, [rsp+128h+var_60]
0x1400cf39b  mov     [rsp+128h+var_58], rcx
0x1400cf3a3  mov     [rsp+128h+var_78], r15
0x1400cf3ab  movzx   edi, byte ptr [rcx+rax]
0x1400cf3af  test    rdx, rdx
0x1400cf3b2  jz      short loc_1400CF3E2
0x1400cf3b4  cmp     [rsp+128h+var_E8], 17h
0x1400cf3ba  jnz     short loc_1400CF3D6
0x1400cf3bc  mov     rax, [r15+8]
0x1400cf3c0  cmp     [rdx+8], rax
0x1400cf3c4  jnz     short loc_1400CF3D2
0x1400cf3c6  mov     rax, [r15]
0x1400cf3c9  cmp     [rdx], rax
0x1400cf3cc  jnz     short loc_1400CF3D2
0x1400cf3ce  mov     al, 1
0x1400cf3d0  jmp     short loc_1400CF3DE
0x1400cf3d2  xor     al, al
0x1400cf3d4  jmp     short loc_1400CF3DE
0x1400cf3d6  mov     eax, [r15]
0x1400cf3d9  cmp     [rdx], eax
0x1400cf3db  setz    al
0x1400cf3de  test    al, al
0x1400cf3e0  jnz     short loc_1400CF406
0x1400cf3e2  mov     rcx, [rsp+128h+var_A0]
0x1400cf3ea  mov     rdx, r15
0x1400cf3ed  call    IppGetExternalScopeId
0x1400cf3f2  mov     r8d, [rsp+128h+var_C8]
0x1400cf3f7  mov     ebx, eax
0x1400cf3f9  mov     r9, [rsp+128h+var_C0]
0x1400cf3fe  mov     [rsp+128h+var_90], r15
0x1400cf406  cmp     [rsp+128h+var_E8], 17h
0x1400cf40c  mov     rax, [rsi+10h]
0x1400cf410  mov     rcx, [rax]
0x1400cf413  jnz     short loc_1400CF431
0x1400cf415  mov     rax, [r12+8]
0x1400cf41a  cmp     [rcx+8], rax
0x1400cf41e  jnz     short loc_1400CF42D
0x1400cf420  mov     rax, [r12]
0x1400cf424  cmp     [rcx], rax
0x1400cf427  jnz     short loc_1400CF42D
0x1400cf429  mov     al, 1
0x1400cf42b  jmp     short loc_1400CF43A
0x1400cf42d  xor     al, al
0x1400cf42f  jmp     short loc_1400CF43A
0x1400cf431  mov     eax, [r12]
0x1400cf435  cmp     [rcx], eax
0x1400cf437  setz    al
0x1400cf43a  test    al, al
0x1400cf43c  jnz     short loc_1400CF443
0x1400cf43e  mov     r15b, 1
0x1400cf441  jmp     short loc_1400CF45A
0x1400cf443  xor     r15b, r15b
0x1400cf446  cmp     dil, [rsp+128h+arg_18]
0x1400cf44e  jnz     short loc_1400CF45A
0x1400cf450  cmp     r8d, 20h ; ' '
0x1400cf454  jnz     loc_1400CF6C0
0x1400cf45a  lea     eax, [r8-1]
0x1400cf45e  mov     rcx, r14
0x1400cf461  lea     rax, [rax+rax*4]
0x1400cf465  shl     rax, 5
0x1400cf469  lea     rdx, [r9+8]
0x1400cf46d  mov     qword ptr [rax+r9+8], 0
0x1400cf476  lea     rax, [rsp+128h+var_70]
0x1400cf47e  mov     [rsp+128h+var_F0], rax
0x1400cf483  lea     rax, [rsp+128h+var_88]
0x1400cf48b  mov     [rsp+128h+var_100], rax
0x1400cf490  lea     rax, [rsp+128h+var_D0]
0x1400cf495  mov     [rsp+128h+var_108], rax
0x1400cf49a  call    IppDeliverPreValidatedListToProtocol
0x1400cf49f  cmp     [rsp+128h+var_E4], 0
0x1400cf4a4  mov     r10d, [rsp+128h+var_C8]
0x1400cf4a9  mov     r8d, [rsp+128h+var_E0]
0x1400cf4ae  jnz     short loc_1400CF4FA
0x1400cf4b0  mov     rdx, [rsp+128h+arg_0]
0x1400cf4b8  mov     rax, [rdx+68h]
0x1400cf4bc  mov     rcx, [rax+r8*8]
0x1400cf4c0  add     [rcx+30h], r10
0x1400cf4c4  mov     rax, [rdx+68h]
0x1400cf4c8  mov     edx, [rsp+128h+var_C4]
0x1400cf4cc  mov     rcx, [rax+r8*8]
0x1400cf4d0  add     [rcx+38h], rdx
0x1400cf4d4  lea     rcx, [r8+r8*2]
0x1400cf4d8  mov     r8, [rsp+128h+var_B0]
0x1400cf4dd  shl     rcx, 6
0x1400cf4e1  mov     rax, [r8+4F28h]
  ... truncated ...
```
