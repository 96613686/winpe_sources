# IpFlcReceivePreValidatedPackets

- ea: `0x1400ceda0`
- end: `0x1400cf8ec`
- name: `IpFlcReceivePreValidatedPackets`
- size: `2892`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400ce070`
- `0x140149b4c`
- `0x1401abda0`

## callees

- `0x14002f790`
- `0x140030390`
- `0x140030820`
- `0x140039bb0`
- `0x140061890`
- `0x14006e050`
- `0x14006fb70`
- `0x1400926f0`
- `0x1400c9420`
- `0x1400ceda0`
- `0x1400cffc0`
- `0x14014cf54`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cee7a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cee7a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cee4d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cee4d`
- `ntoskrnl!KfRaiseIrql` at `0x1400ceede`
- `ntoskrnl!KfRaiseIrql` at `0x1400cf34e`
- `ntoskrnl!KfRaiseIrql` at `0x1400ceede`
- `ntoskrnl!KfRaiseIrql` at `0x1400cf34e`
- `ntoskrnl!KeLowerIrql` at `0x1400cf340`
- `ntoskrnl!KeLowerIrql` at `0x1400cf7a6`
- `ntoskrnl!KeLowerIrql` at `0x1400cf8b3`
- `ntoskrnl!KeLowerIrql` at `0x1400cf340`
- `ntoskrnl!KeLowerIrql` at `0x1400cf7a6`
- `ntoskrnl!KeLowerIrql` at `0x1400cf8b3`
- `ntoskrnl!KeShouldYieldProcessor` at `0x1400cf320`
- `ntoskrnl!KeShouldYieldProcessor` at `0x1400cf320`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ceeb8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ceeb8`
- `NETIO!KfdIsLayerEmpty` at `0x1400cef16`
- `NETIO!KfdIsLayerEmpty` at `0x1400cef16`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400cee20`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400cee20`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cf4fa`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cf83d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cf4fa`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400cf83d`

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
  if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
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
    || (v92 = (_BYTE *)*((_QWORD *)qword_140224818 + v3), *v92)
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
          v50 = (_BYTE *)*((_QWORD *)qword_140224818 + LockArray_high);
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
0x1400ceda0  mov     rax, rsp
0x1400ceda3  mov     [rax+10h], rdx
0x1400ceda7  mov     [rax+8], rcx
0x1400cedab  push    rsi
0x1400cedac  push    rdi
0x1400cedad  push    r12
0x1400cedaf  push    r13
0x1400cedb1  push    r14
0x1400cedb3  push    r15
0x1400cedb5  sub     rsp, 0F8h
0x1400cedbc  mov     r13, rcx
0x1400cedbf  mov     [rsp+128h+var_D8], rdx
0x1400cedc4  xor     ecx, ecx
0x1400cedc6  mov     r15, rdx
0x1400cedc9  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, cl
0x1400cedcf  mov     esi, ecx
0x1400cedd1  mov     [rax-88h], rcx
0x1400cedd8  mov     r14, [r13+8]
0x1400ceddc  mov     [rax-70h], rcx
0x1400cede0  mov     [rsp+128h+var_D0], rcx
0x1400cede5  mov     [rsp+128h+var_E4], cl
0x1400cede9  mov     rax, [r14]
0x1400cedec  mov     [rsp+128h+var_A0], r14
0x1400cedf4  mov     rax, [rax+28h]
0x1400cedf8  mov     [rsp+128h+var_B0], rax
0x1400cedfd  movzx   r12d, word ptr [rax+1Ch]
0x1400cee02  mov     [rsp+128h+var_E8], r12w
0x1400cee08  jz      short loc_1400CEE2C
0x1400cee0a  mov     r8, [rax+59F8h]
0x1400cee11  mov     r9d, 9Dh
0x1400cee17  mov     dword ptr [rsp+128h+var_108], ecx
0x1400cee1b  xor     edx, edx
0x1400cee1d  mov     rcx, r15
0x1400cee20  call    cs:__imp_NdisNblTrackerTransferOwnership
0x1400cee27  nop     dword ptr [rax+rax+00h]
0x1400cee2c  mov     rax, [r14+30h]
0x1400cee30  mov     rcx, [r14+60h]
0x1400cee34  movzx   edi, byte ptr [rax]
0x1400cee37  test    rcx, rcx
0x1400cee3a  jz      short loc_1400CEEA1
0x1400cee3c  movzx   eax, byte ptr [rcx+28h]
0x1400cee40  test    al, al
0x1400cee42  jnz     short loc_1400CEEA1
0x1400cee44  mov     rcx, [rcx+10h]; RunRefCacheAware
0x1400cee48  mov     edx, 1; Count
0x1400cee4d  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400cee54  nop     dword ptr [rax+rax+00h]
0x1400cee59  test    al, al
0x1400cee5b  jz      short loc_1400CEEA1
0x1400cee5d  lea     rdx, [rsp+128h+arg_8]
0x1400cee65  mov     rcx, r13
0x1400cee68  call    IppIndicatePrevalidatedPacketsToIpsServiceChain
0x1400cee6d  mov     rcx, [r14+60h]
0x1400cee71  mov     edx, 1; Count
0x1400cee76  mov     rcx, [rcx+10h]; RunRef
0x1400cee7a  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400cee81  nop     dword ptr [rax+rax+00h]
0x1400cee86  mov     r15, [rsp+128h+arg_8]
0x1400cee8e  mov     [rsp+128h+var_D8], r15
0x1400cee93  test    r15, r15
0x1400cee96  jz      loc_1400CF8D9
0x1400cee9c  mov     [rsp+128h+var_E4], 1
0x1400ceea1  mov     [rsp+128h+var_38], rbx
0x1400ceea9  movzx   ebx, r12w
0x1400ceead  and     bx, 1
0x1400ceeb1  mov     [rsp+128h+DataOffsetDelta], edi
0x1400ceeb8  call    cs:__imp_KeGetCurrentIrql
0x1400ceebf  nop     dword ptr [rax+rax+00h]
0x1400ceec4  cmp     al, 2
0x1400ceec6  jb      short loc_1400CEED7
0x1400ceec8  mov     [rsp+128h+arg_10], 2
0x1400ceed0  mov     [rsp+128h+var_E6], 1
0x1400ceed5  jmp     short loc_1400CEEF1
0x1400ceed7  mov     cl, 2; NewIrql
0x1400ceed9  mov     [rsp+128h+var_E6], sil
0x1400ceede  call    cs:__imp_KfRaiseIrql
0x1400ceee5  nop     dword ptr [rax+rax+00h]
0x1400ceeea  mov     [rsp+128h+arg_10], al
0x1400ceef1  mov     r15d, gs:1A4h
0x1400ceefa  lea     rdi, AddressFamilyInformation
0x1400cef01  movzx   ecx, bx
0x1400cef04  mov     [rsp+128h+var_E0], r15d
0x1400cef09  lea     rdx, [rcx+rcx*8]
0x1400cef0d  lea     rbx, [rdx+rdx]
0x1400cef11  movzx   ecx, word ptr [rbx+rdi+8]
0x1400cef16  call    cs:__imp_KfdIsLayerEmpty
0x1400cef1d  nop     dword ptr [rax+rax+00h]
0x1400cef22  test    eax, eax
0x1400cef24  jz      loc_1400CF7EA
0x1400cef2a  mov     rax, cs:qword_140224818
0x1400cef31  mov     rax, [rax+r15*8]
0x1400cef35  mov     [rsp+128h+var_C0], rax
0x1400cef3a  cmp     [rax], sil
0x1400cef3d  jnz     loc_1400CF7EA
0x1400cef43  cmp     [r14+1A0h], esi
0x1400cef4a  ja      loc_1400CF7EA
0x1400cef50  test    byte ptr [r14+188h], 1
0x1400cef58  jnz     loc_1400CF7EA
0x1400cef5e  movzx   r15d, byte ptr [rbx+rdi+2]
0x1400cef64  lea     rax, AddressFamilyInformation
0x1400cef6b  movzx   eax, byte ptr [rbx+rax+4]
0x1400cef70  movzx   r12d, byte ptr [rbx+rdi+6]
0x1400cef76  movzx   r8d, byte ptr [rbx+rdi+7]
0x1400cef7c  movzx   r13d, byte ptr [rbx+rdi+5]
0x1400cef82  mov     rdi, [rsp+128h+var_D8]
0x1400cef87  mov     r9, [rsp+128h+var_B0]
0x1400cef8c  mov     [rsp+128h+var_60], rax
0x1400cef94  mov     rdx, [rdi+70h]
0x1400cef98  movzx   eax, byte ptr [rdx+rax]
0x1400cef9c  mov     [rsp+128h+arg_18], al
0x1400cefa3  add     rax, 7
0x1400cefa7  lea     rax, [rax+rax*8]
0x1400cefab  lea     r14, [r9+rax*8]
0x1400cefaf  mov     rax, [r9+rax*8+38h]
0x1400cefb4  mov     [rsp+128h+Context], rax
0x1400cefb9  nop     dword ptr [rax+00000000h]
0x1400cefc0  mov     eax, [r14+34h]
0x1400cefc4  test    al, 1
0x1400cefc6  jnz     loc_1400CF065
0x1400cefcc  lea     ecx, [rax+2]
0x1400cefcf  lock cmpxchg [r14+34h], ecx
0x1400cefd5  jnz     short loc_1400CEFC0
0x1400cefd7  mov     rax, [r9+0B0h]
0x1400cefde  lea     rdi, [r8+rdx]
0x1400cefe2  mov     rcx, rdi
0x1400cefe5  mov     [rsp+128h+var_68], r8
0x1400cefed  call    _guard_dispatch_icall
0x1400ceff2  mov     ebx, eax
0x1400ceff4  mov     rax, [rsp+128h+var_B0]
0x1400ceff9  cmp     [rax+4D11h], sil
0x1400cf000  jz      short loc_1400CF02C
0x1400cf002  lea     ecx, [rbx-1]
0x1400cf005  test    ecx, 0FFFFFFFDh
0x1400cf00b  jnz     short loc_1400CF02C
0x1400cf00d  mov     rcx, [rsp+128h+var_A0]
0x1400cf015  mov     r8d, ebx
0x1400cf018  mov     rdx, rdi
0x1400cf01b  call    IppFindAddressInAddressSet
0x1400cf020  mov     rsi, rax
0x1400cf023  test    rax, rax
0x1400cf026  jnz     loc_1400CF0CD
0x1400cf02c  mov     rax, [rsp+128h+var_A0]
0x1400cf034  mov     r9, rdi
0x1400cf037  xor     r8d, r8d
0x1400cf03a  mov     dword ptr [rsp+128h+var_108], ebx
0x1400cf03e  mov     rdx, rax
0x1400cf041  mov     rcx, [rax]
0x1400cf044  call    IppFindNextHopInFwdCacheOrRouteTable
0x1400cf049  mov     rsi, rax
0x1400cf04c  test    rax, rax
0x1400cf04f  jnz     short loc_1400CF0B3
0x1400cf051  mov     rcx, [rsp+128h+Context]; Context
0x1400cf056  call    IppDereferenceNlClient
0x1400cf05b  mov     rsi, [rsp+128h+var_D0]
0x1400cf060  mov     rdi, [rsp+128h+var_D8]
0x1400cf065  mov     r15d, [rsp+128h+var_E0]
0x1400cf06a  movzx   r12d, [rsp+128h+var_E8]
0x1400cf070  mov     r13, [rsp+128h+arg_0]
0x1400cf078  cmp     [rsp+128h+DataOffsetDelta], 0
0x1400cf080  jnz     loc_1400CF7F4
0x1400cf086  xor     ecx, ecx
0x1400cf088  mov     rax, rdi
0x1400cf08b  mov     ebx, ecx
0x1400cf08d  test    rdi, rdi
0x1400cf090  jz      loc_1400CF85D
0x1400cf096  nop     word ptr [rax+rax+00000000h]
0x1400cf0a0  mov     [rax+70h], rcx
0x1400cf0a4  inc     ebx
0x1400cf0a6  mov     rax, [rax]
0x1400cf0a9  test    rax, rax
0x1400cf0ac  jnz     short loc_1400CF0A0
0x1400cf0ae  jmp     loc_1400CF85D
0x1400cf0b3  mov     eax, [rax]
0x1400cf0b5  cmp     eax, 616C7049h
0x1400cf0ba  jz      short loc_1400CF0CD
0x1400cf0bc  cmp     eax, 656E7049h
0x1400cf0c1  jnz     short loc_1400CF051
0x1400cf0c3  mov     rcx, rsi; P
0x1400cf0c6  call    IppDereferenceNeighbor
0x1400cf0cb  jmp     short loc_1400CF051
0x1400cf0cd  mov     eax, [rsi+18h]
0x1400cf0d0  dec     eax
0x1400cf0d2  test    eax, 0FFFFFFFDh
0x1400cf0d7  jz      short loc_1400CF0E6
0x1400cf0d9  mov     rcx, rsi
0x1400cf0dc  call    IppDereferenceLocalAddress
0x1400cf0e1  jmp     loc_1400CF051
0x1400cf0e6  mov     r9, [rsp+128h+var_C0]
0x1400cf0eb  xor     ebx, ebx
0x1400cf0ed  mov     rax, [rsp+128h+var_D8]
0x1400cf0f2  xor     r8d, r8d
0x1400cf0f5  xor     ecx, ecx
0x1400cf0f7  mov     [rsp+128h+var_C8], r8d
0x1400cf0fc  xor     edx, edx
0x1400cf0fe  mov     [rsp+128h+var_C4], ebx
0x1400cf102  mov     byte ptr [r9], 1
0x1400cf106  mov     r10, r13
0x1400cf109  mov     [rsp+128h+var_A8], ecx
0x1400cf110  mov     r11, r12
0x1400cf113  mov     [rsp+128h+var_98], r15d
0x1400cf11b  mov     [rsp+128h+var_90], rdx
0x1400cf123  mov     [rsp+128h+var_50], r13
0x1400cf12b  mov     [rsp+128h+var_48], r12
0x1400cf133  nop     dword ptr [rax+00h]
0x1400cf137  nop     word ptr [rax+rax+00000000h]
0x1400cf140  mov     rcx, [rax+70h]
0x1400cf144  mov     r13, [rax+8]
0x1400cf148  mov     r12, [rsp+128h+var_68]
0x1400cf150  mov     [rsp+128h+var_80], rax
0x1400cf158  add     r12, rcx
0x1400cf15b  movzx   eax, byte ptr [r10+rcx]
0x1400cf160  lea     r15, [r11+rcx]
0x1400cf164  mov     [rsp+128h+var_E5], al
0x1400cf168  mov     eax, [r13+5Ch]
0x1400cf16c  mov     [rsp+128h+var_94], eax
0x1400cf173  mov     rax, [rsp+128h+var_60]
0x1400cf17b  mov     [rsp+128h+var_58], rcx
0x1400cf183  mov     [rsp+128h+var_78], r15
0x1400cf18b  movzx   edi, byte ptr [rcx+rax]
0x1400cf18f  test    rdx, rdx
0x1400cf192  jz      short loc_1400CF1C2
0x1400cf194  cmp     [rsp+128h+var_E8], 17h
0x1400cf19a  jnz     short loc_1400CF1B6
0x1400cf19c  mov     rax, [r15+8]
0x1400cf1a0  cmp     [rdx+8], rax
0x1400cf1a4  jnz     short loc_1400CF1B2
0x1400cf1a6  mov     rax, [r15]
0x1400cf1a9  cmp     [rdx], rax
0x1400cf1ac  jnz     short loc_1400CF1B2
0x1400cf1ae  mov     al, 1
0x1400cf1b0  jmp     short loc_1400CF1BE
0x1400cf1b2  xor     al, al
0x1400cf1b4  jmp     short loc_1400CF1BE
0x1400cf1b6  mov     eax, [r15]
0x1400cf1b9  cmp     [rdx], eax
0x1400cf1bb  setz    al
0x1400cf1be  test    al, al
0x1400cf1c0  jnz     short loc_1400CF1E6
0x1400cf1c2  mov     rcx, [rsp+128h+var_A0]
0x1400cf1ca  mov     rdx, r15
0x1400cf1cd  call    IppGetExternalScopeId
0x1400cf1d2  mov     r8d, [rsp+128h+var_C8]
0x1400cf1d7  mov     ebx, eax
0x1400cf1d9  mov     r9, [rsp+128h+var_C0]
0x1400cf1de  mov     [rsp+128h+var_90], r15
0x1400cf1e6  cmp     [rsp+128h+var_E8], 17h
0x1400cf1ec  mov     rax, [rsi+10h]
0x1400cf1f0  mov     rcx, [rax]
0x1400cf1f3  jnz     short loc_1400CF211
0x1400cf1f5  mov     rax, [r12+8]
0x1400cf1fa  cmp     [rcx+8], rax
0x1400cf1fe  jnz     short loc_1400CF20D
0x1400cf200  mov     rax, [r12]
0x1400cf204  cmp     [rcx], rax
0x1400cf207  jnz     short loc_1400CF20D
0x1400cf209  mov     al, 1
0x1400cf20b  jmp     short loc_1400CF21A
0x1400cf20d  xor     al, al
0x1400cf20f  jmp     short loc_1400CF21A
0x1400cf211  mov     eax, [r12]
0x1400cf215  cmp     [rcx], eax
0x1400cf217  setz    al
0x1400cf21a  test    al, al
0x1400cf21c  jnz     short loc_1400CF223
0x1400cf21e  mov     r15b, 1
0x1400cf221  jmp     short loc_1400CF23A
0x1400cf223  xor     r15b, r15b
0x1400cf226  cmp     dil, [rsp+128h+arg_18]
0x1400cf22e  jnz     short loc_1400CF23A
0x1400cf230  cmp     r8d, 20h ; ' '
0x1400cf234  jnz     loc_1400CF4A0
0x1400cf23a  lea     eax, [r8-1]
0x1400cf23e  mov     rcx, r14
0x1400cf241  lea     rax, [rax+rax*4]
0x1400cf245  shl     rax, 5
0x1400cf249  lea     rdx, [r9+8]
0x1400cf24d  mov     qword ptr [rax+r9+8], 0
0x1400cf256  lea     rax, [rsp+128h+var_70]
0x1400cf25e  mov     [rsp+128h+var_F0], rax
0x1400cf263  lea     rax, [rsp+128h+var_88]
0x1400cf26b  mov     [rsp+128h+var_100], rax
0x1400cf270  lea     rax, [rsp+128h+var_D0]
0x1400cf275  mov     [rsp+128h+var_108], rax
0x1400cf27a  call    IppDeliverPreValidatedListToProtocol
0x1400cf27f  cmp     [rsp+128h+var_E4], 0
0x1400cf284  mov     r10d, [rsp+128h+var_C8]
0x1400cf289  mov     r8d, [rsp+128h+var_E0]
0x1400cf28e  jnz     short loc_1400CF2DA
0x1400cf290  mov     rdx, [rsp+128h+arg_0]
0x1400cf298  mov     rax, [rdx+68h]
0x1400cf29c  mov     rcx, [rax+r8*8]
0x1400cf2a0  add     [rcx+30h], r10
0x1400cf2a4  mov     rax, [rdx+68h]
0x1400cf2a8  mov     edx, [rsp+128h+var_C4]
0x1400cf2ac  mov     rcx, [rax+r8*8]
0x1400cf2b0  add     [rcx+38h], rdx
0x1400cf2b4  lea     rcx, [r8+r8*2]
0x1400cf2b8  mov     r8, [rsp+128h+var_B0]
0x1400cf2bd  shl     rcx, 6
0x1400cf2c1  mov     rax, [r8+4F28h]
  ... truncated ...
```
