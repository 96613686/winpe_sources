# Ipv4pFragmentPacketHelper

- ea: `0x140147f40`
- end: `0x140148e17`
- name: `Ipv4pFragmentPacketHelper`
- size: `3799`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140014a08`
- `0x140027b7c`
- `0x140028790`
- `0x140083060`
- `0x1400aa9d0`
- `0x1400dc670`
- `0x1400defe0`
- `0x1400ec260`
- `0x140114024`
- `0x140144690`
- `0x140147f40`
- `0x14014edf4`
- `0x1401c0fd0`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!PsGetProcessImageFileName` at `0x140148d2a`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140148d2a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140148522`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14014882d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14014889a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140148522`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14014882d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14014889a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14014807a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14014807a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14014819c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401481b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14014819c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401481b9`
- `ntoskrnl!PsGetCurrentProcess` at `0x140148d1b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140148d1b`
- `NETIO!NetioAllocateMdl` at `0x1401487e1`
- `NETIO!NetioAllocateMdl` at `0x140148857`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148255`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148a6b`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148a7c`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148a9a`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148255`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148a6b`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148a7c`
- `NETIO!NetioDereferenceNetBufferList` at `0x140148a9a`
- `NETIO!NetioAdvanceNetBufferList` at `0x140148637`
- `NETIO!NetioAdvanceNetBufferList` at `0x140148637`
- `NETIO!NetioAllocateAndReferenceFragmentNetBufferList` at `0x140148584`
- `NETIO!NetioAllocateAndReferenceFragmentNetBufferList` at `0x140148584`
- `NDIS!NdisGetDataBuffer` at `0x140148678`
- `NDIS!NdisGetDataBuffer` at `0x140148678`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401487f0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140148867`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1401487f0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140148867`

## pseudocode

```c
__int64 __fastcall Ipv4pFragmentPacketHelper(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // r15
  __int64 v5; // r14
  __int64 v6; // r13
  __int64 v7; // r12
  __int64 v8; // r9
  unsigned int v9; // edi
  unsigned int v10; // r9d
  __int64 result; // rax
  __int64 v12; // rbx
  unsigned int v13; // esi
  __int64 *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // r14
  int i; // r8d
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // edi
  __int64 v21; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 *v33; // rdx
  __int64 v34; // r10
  unsigned int jj; // eax
  int v36; // r10d
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 *v40; // rdx
  unsigned int kk; // eax
  __int64 v42; // rdx
  __int64 v43; // r11
  __int64 v44; // r8
  __int64 *v45; // rdx
  unsigned int mm; // eax
  __int64 *v47; // rbx
  unsigned int LockArray_high; // eax
  __int64 v49; // rdx
  __int64 v50; // rbx
  __int64 v51; // r12
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  _BYTE *v56; // rax
  ULONG v57; // esi
  int v58; // eax
  int v59; // r8d
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rdi
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  int PacketCount; // eax
  struct _NET_BUFFER *Alignment; // r12
  __int64 *v68; // rbx
  char *DataBuffer; // r8
  char v70; // dl
  __int64 v71; // xmm0_8
  __int16 v72; // cx
  int v73; // eax
  ULONG v74; // r13d
  unsigned __int8 *v75; // r14
  unsigned __int8 v76; // dl
  int v77; // r15d
  char v78; // r12
  bool v79; // zf
  int v80; // edi
  __int64 v81; // rax
  unsigned int v82; // edi
  __int16 v83; // r12
  unsigned __int16 v84; // cx
  unsigned __int16 v85; // r14
  __int16 j; // r12
  __int16 v87; // r15
  unsigned int v88; // eax
  __int64 v89; // rcx
  char *v90; // rax
  char *p_Src; // rdx
  size_t v92; // r8
  __int64 v93; // rcx
  char *v94; // rdi
  __int16 v95; // ax
  __int16 v96; // cx
  __int64 v97; // r8
  __int64 *v98; // rdx
  unsigned int k; // eax
  __int64 v100; // r9
  __int64 v101; // r10
  __int64 v102; // r8
  __int64 *v103; // rdx
  unsigned int m; // eax
  int v105; // eax
  __int64 v106; // r11
  __int64 v107; // rax
  __int64 v108; // r8
  __int64 *v109; // rdx
  unsigned int n; // eax
  __int64 v111; // rdx
  __int64 v112; // r10
  __int64 v113; // r8
  __int64 *v114; // rdx
  unsigned int ii; // eax
  __int64 CurrentProcess; // rax
  char *ProcessImageFileName; // rax
  int v118; // r8d
  __int64 v119; // rcx
  int v120; // ecx
  char v121; // al
  int BugCheckOnFailure; // [rsp+20h] [rbp-E0h]
  ULONG Priority; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v124; // [rsp+70h] [rbp-90h] BYREF
  char v125; // [rsp+72h] [rbp-8Eh] BYREF
  ULONG v126; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v127; // [rsp+78h] [rbp-88h] BYREF
  __int64 v128; // [rsp+80h] [rbp-80h] BYREF
  __int64 v129; // [rsp+88h] [rbp-78h] BYREF
  struct _NET_BUFFER *v130; // [rsp+90h] [rbp-70h]
  __int64 v131; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v132; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v133; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v134; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v135; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v136; // [rsp+C0h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-38h] BYREF
  char Src; // [rsp+E0h] [rbp-20h] BYREF
  int v139; // [rsp+E1h] [rbp-1Fh]
  char v140; // [rsp+E5h] [rbp-1Bh]
  __int16 v141; // [rsp+E6h] [rbp-1Ah]
  __int64 v142; // [rsp+E8h] [rbp-18h]
  int v143; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR v144; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v145; // [rsp+140h] [rbp+40h]
  __int64 v146; // [rsp+148h] [rbp+48h]
  __int64 *v147; // [rsp+150h] [rbp+50h]
  __int64 v148; // [rsp+158h] [rbp+58h]
  __int64 *v149; // [rsp+160h] [rbp+60h]
  __int64 v150; // [rsp+168h] [rbp+68h]
  __int64 *v151; // [rsp+170h] [rbp+70h]
  __int64 v152; // [rsp+178h] [rbp+78h]
  unsigned __int64 *v153; // [rsp+180h] [rbp+80h]
  __int64 v154; // [rsp+188h] [rbp+88h]
  __int64 *v155; // [rsp+190h] [rbp+90h]
  __int64 v156; // [rsp+198h] [rbp+98h]
  __int64 *v157; // [rsp+1A0h] [rbp+A0h]
  __int64 v158; // [rsp+1A8h] [rbp+A8h]
  __int64 *v159; // [rsp+1B0h] [rbp+B0h]
  __int64 v160; // [rsp+1B8h] [rbp+B8h]
  char *v161; // [rsp+1C0h] [rbp+C0h]
  int v162; // [rsp+1C8h] [rbp+C8h]
  int v163; // [rsp+1CCh] [rbp+CCh]
  char *v164; // [rsp+1D0h] [rbp+D0h]
  __int64 v165; // [rsp+1D8h] [rbp+D8h]
  unsigned int *v166; // [rsp+1E0h] [rbp+E0h]
  __int64 v167; // [rsp+1E8h] [rbp+E8h]
  __int16 *v168; // [rsp+1F0h] [rbp+F0h]
  __int64 v169; // [rsp+1F8h] [rbp+F8h]
  ULONG *v170; // [rsp+200h] [rbp+100h]
  __int64 v171; // [rsp+208h] [rbp+108h]
  char Storage[64]; // [rsp+210h] [rbp+110h] BYREF

  v79 = (*(_BYTE *)(a1 + 184) & 0x10) == 0;
  v4 = a2;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = a1;
  v7 = *(_QWORD *)(a2 + 8);
  v129 = v5;
  v128 = v7;
  v135 = a2;
  v133 = a1;
  if ( v79 )
  {
    if ( *(_DWORD *)(v5 + 160) )
      goto LABEL_75;
    v8 = *(_QWORD *)(v5 + 8);
    v9 = *(_DWORD *)(a2 + 92);
    if ( *(_DWORD *)(v8 + 24) <= v9 )
      goto LABEL_75;
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 280) + 6LL) & 0x40) != 0 )
    {
      v10 = *(_DWORD *)(v8 + 92);
      *(_DWORD *)(v5 + 140) = -1073741306;
      v10 >>= 4;
      LOBYTE(v10) = (v10 & 1) == 0;
      return IppDiscardSendPackets(
               *(_QWORD *)(*(_QWORD *)v7 + 40LL),
               a1,
               258,
               v10,
               0,
               _byteswap_ulong(v9),
               3,
               -536854260);
    }
    goto LABEL_78;
  }
  v12 = *(_QWORD *)(a1 + 208);
  if ( v12 )
  {
    v14 = *(__int64 **)(*(_QWORD *)v12 + 8LL);
    if ( (unsigned __int8)Ipv4pPathMtuTimeoutFired(*(_QWORD *)(a1 + 208), v14, a2) )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( (unsigned __int8)Ipv4pPathMtuTimeoutFired(v15, v14, v4) )
      {
        v16 = *v14;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*v14 + 832), &LockHandle);
        for ( i = 0; i <= *(_DWORD *)(v16 + 840); ++i )
        {
          while ( *(_DWORD *)(((__int64)i << 6) + v16 + 896) )
            ;
        }
        if ( (unsigned __int8)Ipv4pPathMtuTimeoutFired(v12, v14, v4) )
        {
          v18 = *(unsigned int *)(v12 + 112);
          v19 = 8;
          do
          {
            if ( *((_DWORD *)Ipv4pMtuTable + v19) > (unsigned int)v18 )
              break;
            --v19;
          }
          while ( v19 );
          v20 = *(_DWORD *)(v4 + 92);
          v21 = *((unsigned int *)Ipv4pMtuTable + v19);
          if ( (unsigned int)v21 <= v20 )
            v20 = v21;
          if ( (Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState & 0x10) != 0 )
            IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState & 1;
          else
            IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2512_KCSAN_Fix__private_IsEnabledDeviceUsageNoInline(
                                             v21,
                                             v18,
                                             Ipv4pMtuTable);
          if ( IsEnabledDeviceUsageNoInline )
          {
            v126 = *(_DWORD *)(v12 + 40);
            LOBYTE(v126) = v126 & 0xEF;
            *(_DWORD *)(v12 + 40) = v126;
          }
          else
          {
            *(_BYTE *)(v12 + 40) &= ~0x10u;
          }
          v23 = (MEMORY[0xFFFFF78000000008] / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
          v24 = *(_DWORD *)(v12 + 112);
          v25 = (v23 + ((MEMORY[0xFFFFF78000000008] / 0x2710uLL - v23) >> 1)) >> 8;
          if ( v24 <= v20 )
          {
            if ( v24 )
              *(_BYTE *)(v12 + 40) &= ~8u;
          }
          else
          {
            *(_BYTE *)(v12 + 40) |= 8u;
          }
          *(_DWORD *)(v12 + 112) = v20;
          *(_DWORD *)(v12 + 116) = v25;
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 28));
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          IppUpdatePathNotification(v16, v12);
        }
        else
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        v5 = v129;
      }
    }
    v13 = *(_DWORD *)(v12 + 112);
  }
  else
  {
    v13 = *(_DWORD *)(a2 + 92);
  }
  v26 = v13;
  if ( (((*(_BYTE *)(v6 + 90) & 0x30) - 32) & 0xEF) == 0 )
    v26 = *(_DWORD *)(v4 + 92);
  v9 = *(_DWORD *)(v6 + 108);
  if ( v26 < v9 )
    v9 = v26;
  v27 = IppInspectLocalPacketsOut(0, *(_QWORD *)(v6 + 224), (int)v6 + 232, a4, v7, *(_DWORD *)(v4 + 24), 0);
  v30 = (unsigned int)v27;
  if ( (int)v27 < 1 )
  {
    if ( *(_DWORD *)(v5 + 160) || *(_DWORD *)(v5 + 320) )
      goto LABEL_75;
    v47 = *(__int64 **)(v5 + 8);
    if ( !v47 )
      goto LABEL_74;
    while ( *((_DWORD *)v47 + 6) <= v9 )
    {
      v47 = (__int64 *)*v47;
      if ( !v47 )
        goto LABEL_74;
    }
    if ( (*(_BYTE *)(v6 + 88) & 4) == 0 )
    {
LABEL_78:
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      v49 = v128;
      v50 = *(_QWORD *)(v5 + 8);
      v51 = *(_QWORD *)(*(_QWORD *)(v4 + 104) + 8LL * LockArray_high);
      v52 = 3LL * LockArray_high;
      v53 = *(_QWORD *)v128;
      v136 = v51;
      v54 = (v52 << 6) + *(_QWORD *)(*(_QWORD *)(v53 + 40) + 20264LL);
      v55 = *(_QWORD *)(v50 + 8);
      v131 = v54;
      if ( (*(_BYTE *)(v55 + 10) & 5) != 0 )
      {
        v56 = *(_BYTE **)(v55 + 24);
      }
      else
      {
        v56 = MmMapLockedPagesSpecifyCache((PMDL)v55, 0, MmCached, 0, 0, 0x40000000u);
        v49 = v128;
      }
      v57 = (unsigned __int8)(4 * (v56[*(unsigned int *)(v50 + 16)] & 0xF));
      v126 = v57;
      if ( v57 + 8 > v9 )
      {
        v58 = -536854258;
        v59 = 259;
LABEL_87:
        IppDiscardSendPackets(*(_QWORD *)(*(_QWORD *)v128 + 40LL), v6, v59, 0, 0, 0, 3, v58);
        *(_DWORD *)(v5 + 140) = -1073741670;
        PacketCount = IppGetPacketCount(v5, v63, v64, v65);
        *(_DWORD *)(v51 + 80) += PacketCount;
        result = (unsigned int)(*(_DWORD *)(v131 + 160) + PacketCount);
        *(_DWORD *)(v131 + 160) = result;
        return result;
      }
      LOBYTE(Priority) = 0;
      BugCheckOnFailure = *(unsigned __int16 *)(v49 + 130);
      v127 = ((_WORD)v9 - (_WORD)v57) & 0xFFF8;
      v60 = NetioAllocateAndReferenceFragmentNetBufferList(
              v5,
              v57,
              (unsigned __int16)(v9 - v57) & 0xFFF8,
              v57,
              BugCheckOnFailure,
              Priority);
      v134 = v60;
      v62 = v60;
      if ( !v60 )
      {
        if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_TCPIP_PROVIDER_Context,
            TCPIP_MEMORY_FAILURES,
            v61,
            L"IPv4 fragment (IPNG)");
        v58 = -536854257;
        v59 = 264;
        goto LABEL_87;
      }
      NetioAdvanceNetBufferList(v60, v57);
      Alignment = *(struct _NET_BUFFER **)(v5 + 8);
      v68 = *(__int64 **)(v62 + 8);
      v130 = Alignment;
      if ( Alignment )
      {
        do
        {
          DataBuffer = (char *)NdisGetDataBuffer(Alignment, v57, Storage, 1u, 0);
          v132 = (unsigned __int64)DataBuffer;
          v70 = *DataBuffer;
          v71 = *((_QWORD *)DataBuffer + 1);
          v139 = *(_DWORD *)(DataBuffer + 1);
          v140 = DataBuffer[5];
          v72 = *((_WORD *)DataBuffer + 3);
          v73 = *((_DWORD *)DataBuffer + 4);
          v124 = v72;
          v141 = v72;
          v143 = v73;
          Src = v70;
          v142 = v71;
          if ( v70 == 69 )
          {
            v74 = 20;
          }
          else
          {
            v75 = (unsigned __int8 *)(DataBuffer + 20);
            v76 = 4 * (v70 & 0xF);
            v74 = 20;
            v77 = v76 - 20;
            if ( v76 != 20 )
            {
              do
              {
                v78 = *v75;
                v79 = *v75 == 0;
                if ( (*v75 & 0x80u) != 0 )
                {
                  v80 = v75[1];
                  memmove(&Src + v74, v75, v75[1]);
                  v74 += v80;
                  v79 = v78 == 0;
                }
                if ( v79 )
                  break;
                if ( v78 == 1 )
                {
                  --v77;
                  ++v75;
                }
                else
                {
                  v81 = v75[1];
                  v77 -= v81;
                  v75 += v81;
                }
              }
              while ( v77 );
              v57 = v126;
              Alignment = v130;
            }
            v82 = -v74 & 3;
            if ( v82 )
            {
              memset(&Src + v74, 0, v82);
              v74 += v82;
            }
            Src = Src & 0xF0 | (v74 >> 2) & 0xF;
            v72 = v124;
          }
          v83 = *((_WORD *)&Alignment->NetBufferHeader.Link + 12);
          v141 &= 0xE0u;
          v84 = 8 * __ROR2__(v72 & 0xFF1F, 8);
          v124 = v84;
          v85 = v84;
          for ( j = v83 - v57; j; j -= v87 )
          {
            v87 = *((_WORD *)v68 + 12);
            v88 = *((_DWORD *)v68 + 4);
            if ( v85 == v84 )
            {
              if ( v88 < v57 )
              {
                NdisRetreatNetBufferDataStart((PNET_BUFFER)v68, v57, 0, NetioAllocateMdl);
              }
              else
              {
                *((_DWORD *)v68 + 10) -= v57;
                *((_DWORD *)v68 + 6) += v57;
                *((_DWORD *)v68 + 4) = v88 - v57;
              }
              v89 = v68[1];
              if ( (*(_BYTE *)(v89 + 10) & 5) != 0 )
                v90 = *(char **)(v89 + 24);
              else
                v90 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v89, 0, MmCached, 0, 0, 0x40000000u);
              p_Src = (char *)v132;
              v92 = v57;
            }
            else
            {
              if ( v88 < v74 )
              {
                NdisRetreatNetBufferDataStart((PNET_BUFFER)v68, v74, 0, NetioAllocateMdl);
              }
              else
              {
                *((_DWORD *)v68 + 10) -= v74;
                *((_DWORD *)v68 + 6) += v74;
                *((_DWORD *)v68 + 4) = v88 - v74;
              }
              v93 = v68[1];
              if ( (*(_BYTE *)(v93 + 10) & 5) != 0 )
                v90 = *(char **)(v93 + 24);
              else
                v90 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v93, 0, MmCached, 0, 0, 0x40000000u);
              v92 = v74;
              p_Src = &Src;
            }
            v94 = &v90[*((unsigned int *)v68 + 4)];
            memmove(v94, p_Src, v92);
            if ( v130->DataLength - v57 > v127 )
            {
              *((_WORD *)v94 + 1) = __ROR2__(*((_WORD *)v68 + 12), 8);
              v95 = 0;
              v96 = *((_WORD *)v94 + 3) | __ROR2__(v85 >> 3, 8);
              if ( j != v87 )
                v95 = 32;
              *((_WORD *)v94 + 3) = v96 & 0xFFDF ^ (v96 | v95) & 0x20;
            }
            v68 = (__int64 *)*v68;
            v85 += v87;
            v84 = v124;
          }
          Alignment = (struct _NET_BUFFER *)v130->Link.Alignment;
          v130 = Alignment;
        }
        while ( Alignment );
        v6 = v133;
        v5 = v129;
        v62 = v134;
        v4 = v135;
      }
      v97 = *(_QWORD *)(v5 + 160);
      v98 = *(__int64 **)(v5 + 8);
      if ( (_DWORD)v97 || *(_DWORD *)(v5 + 320) )
      {
        if ( !v97 )
          LODWORD(v97) = *(_DWORD *)(v5 + 320);
        k = (((unsigned int)v97 & 0xFFFFF) + *((_DWORD *)v98 + 21) - 1) / ((unsigned int)v97 & 0xFFFFF);
      }
      else
      {
        for ( k = 0; v98; ++k )
          v98 = (__int64 *)*v98;
      }
      v100 = v136;
      v101 = v131;
      *(_DWORD *)(v136 + 76) += k;
      *(_DWORD *)(v101 + 156) += k;
      v102 = *(_QWORD *)(v62 + 160);
      v103 = *(__int64 **)(v62 + 8);
      if ( (_DWORD)v102 || *(_DWORD *)(v62 + 320) )
      {
        if ( !v102 )
          LODWORD(v102) = *(_DWORD *)(v62 + 320);
        m = (((unsigned int)v102 & 0xFFFFF) + *((_DWORD *)v103 + 21) - 1) / ((unsigned int)v102 & 0xFFFFF);
      }
      else
      {
        for ( m = 0; v103; ++m )
          v103 = (__int64 *)*v103;
      }
      *(_DWORD *)(v100 + 84) += m;
      *(_DWORD *)(v101 + 164) += m;
      v105 = IPsecProcessOutboundFragList(0, v5, v62);
      if ( v105 >= 1 )
      {
        if ( v105 == 1 )
          IppDiscardSendPackets(*(_QWORD *)(*(_QWORD *)v128 + 40LL), v6, 9, 0, 0, 0, 3, -536854255);
        NetioDereferenceNetBufferList(v5, 0);
        result = NetioDereferenceNetBufferList(v62, 0);
        *(_QWORD *)(v6 + 8) = 0;
        return result;
      }
      NetioDereferenceNetBufferList(v5, 0);
      *(_QWORD *)(v6 + 8) = v62;
LABEL_74:
      Ipv4pChecksumPacket(v4, v6, v29, v30);
LABEL_75:
      result = *(_QWORD *)(v6 + 8);
      *(_DWORD *)(result + 140) = 0;
      return result;
    }
    *(_DWORD *)(v5 + 140) = -1073741306;
    v106 = *(_QWORD *)(*(_QWORD *)v7 + 40LL);
    v107 = *(_QWORD *)(v6 + 8);
    v108 = *(_QWORD *)(v107 + 160);
    v109 = *(__int64 **)(v107 + 8);
    if ( (_DWORD)v108 || *(_DWORD *)(v107 + 320) )
    {
      if ( !v108 )
        LODWORD(v108) = *(_DWORD *)(v107 + 320);
      v108 &= 0xFFFFFu;
      n = ((int)v108 + *((_DWORD *)v109 + 21) - 1) / (unsigned int)v108;
    }
    else
    {
      for ( n = 0; v109; ++n )
        v109 = (__int64 *)*v109;
    }
    LODWORD(v28) = HIDWORD(KeGetPcr()[1].LockArray);
    v111 = *(_QWORD *)(v106 + 20264) + 192 * v28;
    result = *(_DWORD *)(v111 + 152) + n;
    *(_DWORD *)(v111 + 152) = result;
    if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 || byte_140229CC0 )
    {
      v112 = *(_QWORD *)(v6 + 8);
      v113 = *(_QWORD *)(v112 + 160);
      v114 = *(__int64 **)(v112 + 8);
      if ( (_DWORD)v113 || *(_DWORD *)(v112 + 320) )
      {
        if ( !v113 )
          LODWORD(v113) = *(_DWORD *)(v112 + 320);
        ii = (((unsigned int)v113 & 0xFFFFF) + *((_DWORD *)v114 + 21) - 1) / ((unsigned int)v113 & 0xFFFFF);
      }
      else
      {
        for ( ii = 0; v114; ++ii )
          v114 = (__int64 *)*v114;
      }
      result = IppLogPacketDiscard(
                 *(unsigned __int16 *)(v106 + 28),
                 *(unsigned __int16 *)(v6 + 104),
                 *(_QWORD *)(v6 + 264),
                 *(_QWORD *)(v6 + 248),
                 258,
                 ii,
                 0,
                 v112,
                 *(_QWORD *)(*(_QWORD *)(v6 + 224) + 8LL),
                 3,
                 -536854259);
    }
    if ( *(_DWORD *)(v6 + 108) != -1 )
    {
      result = (unsigned int)dword_1402241F8;
      if ( (unsigned int)dword_1402241F8 > 5 )
      {
        result = qword_140224208;
        if ( (qword_140224208 & 0x400000000000LL) != 0 )
        {
          result = qword_140224210 & 0x400000000000LL;
          if ( (qword_140224210 & 0x400000000000LL) == qword_140224210 )
          {
            v136 = 1;
            v145 = &v136;
            v135 = *((unsigned int *)v47 + 6);
            v134 = v135;
            v133 = v135;
            v151 = &v133;
            v147 = &v135;
            v132 = v13;
            v131 = v13;
            v129 = v13;
            v149 = &v134;
            v157 = &v129;
            v153 = &v132;
            v159 = &v128;
            v146 = 8;
            v148 = 8;
            v150 = 8;
            v152 = 8;
            v154 = 8;
            v155 = &v131;
            v156 = 8;
            v158 = 8;
            v128 = 0x2000000;
            v160 = 8;
            CurrentProcess = PsGetCurrentProcess(&v131, 0x400000000000LL, v108, v30);
            ProcessImageFileName = (char *)PsGetProcessImageFileName(CurrentProcess);
            if ( ProcessImageFileName )
            {
              v119 = -1;
              do
                ++v119;
              while ( ProcessImageFileName[v119] );
              v120 = v119 + 1;
            }
            else
            {
              ProcessImageFileName = byte_1401E115B;
              v120 = 1;
            }
            v161 = ProcessImageFileName;
            v162 = v120;
            v164 = &v125;
            v127 = *(_DWORD *)(v6 + 108);
            v166 = &v127;
            v121 = (*(_BYTE *)(v6 + 90) >> 4) & 3;
            v163 = 0;
            LOBYTE(v124) = v121;
            v168 = (__int16 *)&v124;
            LOWORD(v126) = *(_WORD *)(v6 + 104);
            v170 = &v126;
            v125 = 2;
            v165 = 1;
            v167 = 4;
            v169 = 1;
            v171 = 2;
            return tlgWriteAgg((int)&dword_1402241F8, (int)&word_1401F706A, v118, 15, &v144);
          }
        }
      }
    }
  }
  else
  {
    v31 = (unsigned int)(v27 - 1);
    if ( (unsigned int)v31 <= 1 )
    {
      LODWORD(v27) = HIDWORD(KeGetPcr()[1].LockArray);
      v32 = *(_QWORD *)(v5 + 160);
      v33 = *(__int64 **)(v5 + 8);
      v34 = qword_14021B5D8 + 192 * v27;
      if ( (_DWORD)v32 || *(_DWORD *)(v5 + 320) )
      {
        if ( !v32 )
          LODWORD(v32) = *(_DWORD *)(v5 + 320);
        jj = (((unsigned int)v32 & 0xFFFFF) + *((_DWORD *)v33 + 21) - 1) / ((unsigned int)v32 & 0xFFFFF);
      }
      else
      {
        for ( jj = 0; v33; ++jj )
          v33 = (__int64 *)*v33;
      }
      *(_DWORD *)(v34 + 172) += jj;
      v36 = 9;
      *(_DWORD *)(*(_QWORD *)(v6 + 8) + 140LL) = -1073741285;
      if ( (_DWORD)v30 != 1 )
        v36 = 11;
      v37 = *(_QWORD *)(*(_QWORD *)v7 + 40LL);
      v38 = *(_QWORD *)(v6 + 8);
      v39 = *(_QWORD *)(v38 + 160);
      v40 = *(__int64 **)(v38 + 8);
      if ( (_DWORD)v39 || *(_DWORD *)(v38 + 320) )
      {
        if ( !v39 )
          LODWORD(v39) = *(_DWORD *)(v38 + 320);
        kk = (((unsigned int)v39 & 0xFFFFF) + *((_DWORD *)v40 + 21) - 1) / ((unsigned int)v39 & 0xFFFFF);
      }
      else
      {
        for ( kk = 0; v40; ++kk )
          v40 = (__int64 *)*v40;
      }
      LODWORD(v31) = HIDWORD(KeGetPcr()[1].LockArray);
      v42 = *(_QWORD *)(v37 + 20264) + 192 * v31;
      result = *(_DWORD *)(v42 + 152) + kk;
      *(_DWORD *)(v42 + 152) = result;
      if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 || byte_140229CC0 )
      {
        v43 = *(_QWORD *)(v6 + 8);
        v44 = *(_QWORD *)(v43 + 160);
        v45 = *(__int64 **)(v43 + 8);
        if ( (_DWORD)v44 || *(_DWORD *)(v43 + 320) )
        {
          if ( !v44 )
            LODWORD(v44) = *(_DWORD *)(v43 + 320);
          mm = (((unsigned int)v44 & 0xFFFFF) + *((_DWORD *)v45 + 21) - 1) / ((unsigned int)v44 & 0xFFFFF);
        }
        else
        {
          for ( mm = 0; v45; ++mm )
            v45 = (__int64 *)*v45;
        }
        return IppLogPacketDiscard(
                 *(unsigned __int16 *)(v37 + 28),
                 *(unsigned __int16 *)(v6 + 104),
                 *(_QWORD *)(v6 + 264),
                 *(_QWORD *)(v6 + 248),
                 v36,
                 mm,
                 0,
                 v43,
                 *(_QWORD *)(*(_QWORD *)(v6 + 224) + 8LL),
                 3,
                 -536854256);
      }
    }
    else
    {
      result = NetioDereferenceNetBufferList(*(_QWORD *)(v6 + 8), 0);
      *(_QWORD *)(v6 + 8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140147f40  mov     [rsp-8+arg_10], rbx
0x140147f45  push    rbp
0x140147f46  push    rsi
0x140147f47  push    rdi
0x140147f48  push    r12
0x140147f4a  push    r13
0x140147f4c  push    r14
0x140147f4e  push    r15
0x140147f50  lea     rbp, [rsp-160h]
0x140147f58  sub     rsp, 260h
0x140147f5f  mov     rax, cs:__security_cookie
0x140147f66  xor     rax, rsp
0x140147f69  mov     [rbp+190h+var_40], rax
0x140147f70  test    byte ptr [rcx+0B8h], 10h
0x140147f77  mov     r15, rdx
0x140147f7a  mov     r14, [rcx+8]
0x140147f7e  mov     r13, rcx
0x140147f81  mov     r12, [rdx+8]
0x140147f85  mov     [rbp+190h+var_208], r14
0x140147f89  mov     [rbp+190h+var_210], r12
0x140147f8d  mov     [rbp+190h+var_1D8], rdx
0x140147f91  mov     [rbp+190h+var_1E8], rcx
0x140147f95  jnz     loc_14014801B
0x140147f9b  cmp     dword ptr [r14+0A0h], 0
0x140147fa3  jnz     loc_140148478
0x140147fa9  mov     r9, [r14+8]
0x140147fad  mov     edi, [rdx+5Ch]
0x140147fb0  cmp     [r9+18h], edi
0x140147fb4  jbe     loc_140148478
0x140147fba  mov     rax, [rcx+118h]
0x140147fc1  test    byte ptr [rax+6], 40h
0x140147fc5  jz      loc_1401484BC
0x140147fcb  mov     r9d, [r9+5Ch]
0x140147fcf  mov     r8d, 102h
0x140147fd5  mov     dword ptr [r14+8Ch], 0C0000206h
0x140147fe0  mov     rdx, r13
0x140147fe3  mov     rcx, [r12]
0x140147fe7  shr     r9d, 4
0x140147feb  mov     dword ptr [rsp+290h+var_258], 0E000410Ch
0x140147ff3  not     r9b
0x140147ff6  mov     [rsp+290h+var_260], 3
0x140147ffe  and     r9b, 1
0x140148002  mov     rcx, [rcx+28h]
0x140148006  bswap   edi
0x140148008  mov     [rsp+290h+Priority], edi
0x14014800c  mov     byte ptr [rsp+290h+BugCheckOnFailure], 0
0x140148011  call    IppDiscardSendPackets
0x140148016  jmp     loc_140148486
0x14014801b  mov     rbx, [rcx+0D0h]
0x140148022  test    rbx, rbx
0x140148025  jnz     short loc_14014802F
0x140148027  mov     esi, [rdx+5Ch]
0x14014802a  jmp     loc_1401481CC
0x14014802f  mov     rax, [rbx]
0x140148032  mov     r8, r15
0x140148035  mov     rcx, rbx
0x140148038  mov     rsi, [rax+8]
0x14014803c  mov     rdx, rsi
0x14014803f  call    Ipv4pPathMtuTimeoutFired
0x140148044  test    al, al
0x140148046  jz      loc_1401481C9
0x14014804c  xor     eax, eax
0x14014804e  xorps   xmm0, xmm0
0x140148051  mov     r8, r15
0x140148054  mov     qword ptr [rbp+190h+LockHandle.OldIrql], rax
0x140148058  mov     rdx, rsi
0x14014805b  movups  xmmword ptr [rbp+190h+LockHandle.LockQueue.Next], xmm0
0x14014805f  call    Ipv4pPathMtuTimeoutFired
0x140148064  test    al, al
0x140148066  jz      loc_1401481C9
0x14014806c  mov     r14, [rsi]
0x14014806f  lea     rdx, [rbp+190h+LockHandle]; LockHandle
0x140148073  lea     rcx, [r14+340h]; SpinLock
0x14014807a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140148081  nop     dword ptr [rax+rax+00h]
0x140148086  xor     r8d, r8d
0x140148089  cmp     [r14+348h], r8d
0x140148090  jl      short loc_1401480C8
0x140148092  nop     dword ptr [rax+00h]
0x140148096  nop     word ptr [rax+rax+00000000h]
0x1401480a0  movsxd  rcx, r8d
0x1401480a3  shl     rcx, 6
0x1401480a7  nop     word ptr [rax+rax+00000000h]
0x1401480b0  mov     eax, [rcx+r14+380h]
0x1401480b8  test    eax, eax
0x1401480ba  jnz     short loc_1401480B0
0x1401480bc  inc     r8d
0x1401480bf  cmp     r8d, [r14+348h]
0x1401480c6  jle     short loc_1401480A0
0x1401480c8  mov     r8, r15
0x1401480cb  mov     rdx, rsi
0x1401480ce  mov     rcx, rbx
0x1401480d1  call    Ipv4pPathMtuTimeoutFired
0x1401480d6  test    al, al
0x1401480d8  jz      loc_1401481B5
0x1401480de  mov     edx, [rbx+70h]
0x1401480e1  lea     r8, Ipv4pMtuTable
0x1401480e8  mov     ecx, 8
0x1401480ed  nop     dword ptr [rax]
0x1401480f0  mov     eax, ecx
0x1401480f2  cmp     [r8+rax*4], edx
0x1401480f6  ja      short loc_1401480FD
0x1401480f8  add     ecx, 0FFFFFFFFh
0x1401480fb  jnz     short loc_1401480F0
0x1401480fd  mov     edi, [r15+5Ch]
0x140148101  mov     eax, ecx
0x140148103  mov     ecx, [r8+rax*4]
0x140148107  cmp     ecx, edi
0x140148109  cmovbe  edi, ecx
0x14014810c  mov     eax, cs:Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState
0x140148112  test    al, 10h
0x140148114  jz      short loc_14014811B
0x140148116  and     eax, 1
0x140148119  jmp     short loc_140148120
0x14014811b  call    Feature_TCPIP_2025_2512_KCSAN_Fix__private_IsEnabledDeviceUsageNoInline
0x140148120  test    eax, eax
0x140148122  jnz     short loc_14014812A
0x140148124  and     byte ptr [rbx+28h], 0EFh
0x140148128  jmp     short loc_14014813E
0x14014812a  mov     eax, [rbx+28h]
0x14014812d  mov     [rsp+290h+var_21C], eax
0x140148131  and     al, 0EFh
0x140148133  mov     byte ptr [rsp+290h+var_21C], al
0x140148137  mov     eax, [rsp+290h+var_21C]
0x14014813b  mov     [rbx+28h], eax
0x14014813e  mov     rcx, 0FFFFF78000000008h
0x140148148  mov     rax, 346DC5D63886594Bh
0x140148152  mov     rcx, [rcx]
0x140148155  mul     rcx
0x140148158  mov     rax, 624DD2F1A9FBE77h
0x140148162  mov     rcx, rdx
0x140148165  shr     rcx, 0Bh
0x140148169  mul     rcx
0x14014816c  mov     eax, [rbx+70h]
0x14014816f  sub     rcx, rdx
0x140148172  shr     rcx, 1
0x140148175  add     rcx, rdx
0x140148178  shr     rcx, 8
0x14014817c  cmp     eax, edi
0x14014817e  jbe     short loc_140148186
0x140148180  or      byte ptr [rbx+28h], 8
0x140148184  jmp     short loc_14014818E
0x140148186  test    eax, eax
0x140148188  jz      short loc_14014818E
0x14014818a  and     byte ptr [rbx+28h], 0F7h
0x14014818e  mov     [rbx+70h], edi
0x140148191  mov     [rbx+74h], ecx
0x140148194  lock inc dword ptr [rbx+1Ch]
0x140148198  lea     rcx, [rbp+190h+LockHandle]; LockHandle
0x14014819c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401481a3  nop     dword ptr [rax+rax+00h]
0x1401481a8  mov     rdx, rbx
0x1401481ab  mov     rcx, r14
0x1401481ae  call    IppUpdatePathNotification
0x1401481b3  jmp     short loc_1401481C5
0x1401481b5  lea     rcx, [rbp+190h+LockHandle]; LockHandle
0x1401481b9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401481c0  nop     dword ptr [rax+rax+00h]
0x1401481c5  mov     r14, [rbp+190h+var_208]
0x1401481c9  mov     esi, [rbx+70h]
0x1401481cc  movzx   eax, byte ptr [r13+5Ah]
0x1401481d1  and     al, 30h
0x1401481d3  sub     al, 20h ; ' '
0x1401481d5  test    al, 0EFh
0x1401481d7  mov     eax, esi
0x1401481d9  jnz     short loc_1401481DF
0x1401481db  mov     eax, [r15+5Ch]
0x1401481df  mov     edi, [r13+6Ch]
0x1401481e3  lea     r8, [r13+0E8h]
0x1401481ea  movzx   edx, byte ptr [r13+58h]
0x1401481ef  cmp     eax, edi
0x1401481f1  movzx   ecx, word ptr [r13+3Ch]
0x1401481f6  cmovb   edi, eax
0x1401481f9  mov     [rsp+290h+var_228], r14
0x1401481fe  mov     eax, [r13+0C4h]
0x140148205  mov     [rsp+290h+var_230], eax
0x140148209  mov     eax, [r15+18h]
0x14014820d  shr     dl, 2
0x140148210  and     dl, 1
0x140148213  mov     byte ptr [rsp+290h+var_240], dl
0x140148217  mov     rdx, [r13+0E0h]
0x14014821e  mov     [rsp+290h+var_248], edi
0x140148222  mov     dword ptr [rsp+290h+var_250], ecx
0x140148226  xor     ecx, ecx
0x140148228  mov     byte ptr [rsp+290h+var_260], 0
0x14014822d  mov     [rsp+290h+Priority], eax
0x140148231  mov     qword ptr [rsp+290h+BugCheckOnFailure], r12
0x140148236  call    IppInspectLocalPacketsOut
0x14014823b  mov     r9d, eax
0x14014823e  cmp     eax, 1
0x140148241  jl      loc_14014843D
0x140148247  lea     ecx, [rax-1]
0x14014824a  cmp     ecx, 1
0x14014824d  jbe     short loc_14014826E
0x14014824f  mov     rcx, [r13+8]
0x140148253  xor     edx, edx
0x140148255  call    cs:__imp_NetioDereferenceNetBufferList
0x14014825c  nop     dword ptr [rax+rax+00h]
0x140148261  mov     qword ptr [r13+8], 0
0x140148269  jmp     loc_140148486
0x14014826e  mov     eax, gs:1A4h
0x140148276  mov     r8, [r14+0A0h]
0x14014827d  mov     rdx, [r14+8]
0x140148281  lea     r10, [rax+rax*2]
0x140148285  shl     r10, 6
0x140148289  add     r10, cs:qword_14021B5D8
0x140148290  test    r8d, r8d
0x140148293  jnz     short loc_1401482B1
0x140148295  cmp     [r14+140h], r8d
0x14014829c  jnz     short loc_1401482B1
0x14014829e  xor     eax, eax
0x1401482a0  test    rdx, rdx
0x1401482a3  jz      short loc_1401482D1
0x1401482a5  mov     rdx, [rdx]
0x1401482a8  inc     eax
0x1401482aa  test    rdx, rdx
0x1401482ad  jnz     short loc_1401482A5
0x1401482af  jmp     short loc_1401482D1
0x1401482b1  test    r8, r8
0x1401482b4  jnz     short loc_1401482BD
0x1401482b6  mov     r8d, [r14+140h]
0x1401482bd  mov     eax, [rdx+54h]
0x1401482c0  and     r8d, 0FFFFFh
0x1401482c7  dec     eax
0x1401482c9  xor     edx, edx
0x1401482cb  add     eax, r8d
0x1401482ce  div     r8d
0x1401482d1  add     [r10+0ACh], eax
0x1401482d8  mov     r10d, 9
0x1401482de  mov     rax, [r13+8]
0x1401482e2  cmp     r9d, 1
0x1401482e6  mov     dword ptr [rax+8Ch], 0C000021Bh
0x1401482f0  mov     eax, 0Bh
0x1401482f5  cmovnz  r10d, eax
0x1401482f9  mov     rax, [r12]
0x1401482fd  mov     rbx, [rax+28h]
0x140148301  mov     rax, [r13+8]
0x140148305  mov     r8, [rax+0A0h]
0x14014830c  mov     rdx, [rax+8]
0x140148310  test    r8d, r8d
0x140148313  jnz     short loc_140148331
0x140148315  cmp     [rax+140h], r8d
0x14014831c  jnz     short loc_140148331
0x14014831e  xor     eax, eax
0x140148320  test    rdx, rdx
0x140148323  jz      short loc_140148351
0x140148325  mov     rdx, [rdx]
0x140148328  inc     eax
0x14014832a  test    rdx, rdx
0x14014832d  jnz     short loc_140148325
0x14014832f  jmp     short loc_140148351
0x140148331  test    r8, r8
0x140148334  jnz     short loc_14014833D
0x140148336  mov     r8d, [rax+140h]
0x14014833d  mov     eax, [rdx+54h]
0x140148340  and     r8d, 0FFFFFh
0x140148347  dec     eax
0x140148349  xor     edx, edx
0x14014834b  add     eax, r8d
0x14014834e  div     r8d
0x140148351  mov     ecx, gs:1A4h
0x140148359  lea     rdx, [rcx+rcx*2]
0x14014835d  shl     rdx, 6
0x140148361  add     rdx, [rbx+4F28h]
0x140148368  mov     ecx, [rdx+98h]
0x14014836e  add     eax, ecx
0x140148370  mov     [rdx+98h], eax
0x140148376  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 0
0x14014837d  jl      short loc_14014838C
0x14014837f  cmp     cs:byte_140229CC0, 0
0x140148386  jz      loc_140148486
0x14014838c  mov     r11, [r13+8]
0x140148390  mov     rax, [r13+0E0h]
0x140148397  mov     rdi, [r13+108h]
0x14014839e  mov     rsi, [r13+0F8h]
0x1401483a5  mov     r8, [r11+0A0h]
0x1401483ac  mov     r14, [rax+8]
0x1401483b0  mov     rdx, [r11+8]
0x1401483b4  test    r8d, r8d
0x1401483b7  jnz     short loc_1401483DC
0x1401483b9  cmp     [r11+140h], r8d
0x1401483c0  jnz     short loc_1401483DC
0x1401483c2  xor     eax, eax
0x1401483c4  test    rdx, rdx
0x1401483c7  jz      short loc_1401483FC
0x1401483c9  nop     dword ptr [rax+00000000h]
0x1401483d0  mov     rdx, [rdx]
0x1401483d3  inc     eax
0x1401483d5  test    rdx, rdx
0x1401483d8  jnz     short loc_1401483D0
0x1401483da  jmp     short loc_1401483FC
0x1401483dc  test    r8, r8
0x1401483df  jnz     short loc_1401483E8
0x1401483e1  mov     r8d, [r11+140h]
0x1401483e8  mov     eax, [rdx+54h]
0x1401483eb  and     r8d, 0FFFFFh
0x1401483f2  dec     eax
0x1401483f4  xor     edx, edx
0x1401483f6  add     eax, r8d
0x1401483f9  div     r8d
  ... truncated ...
```
