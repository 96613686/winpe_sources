# Ipv4pFragmentPacketHelper

- ea: `0x140144400`
- end: `0x1401452d7`
- name: `Ipv4pFragmentPacketHelper`
- size: `3799`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140053e98`
- `0x14006891c`
- `0x140068d10`
- `0x140087510`
- `0x14009be0c`
- `0x1400ca530`
- `0x1400d1500`
- `0x1400e6350`
- `0x14010a1b0`
- `0x140140b50`
- `0x140144400`
- `0x14014d0bc`
- `0x1401bf390`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!PsGetProcessImageFileName` at `0x1401451ea`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401451ea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401449e2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140144ced`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140144d5a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1401449e2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140144ced`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140144d5a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14014453a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14014453a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14014465c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140144679`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14014465c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140144679`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401451db`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401451db`
- `NETIO!NetioAllocateMdl` at `0x140144ca1`
- `NETIO!NetioAllocateMdl` at `0x140144d17`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144715`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144f2b`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144f3c`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144f5a`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144715`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144f2b`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144f3c`
- `NETIO!NetioDereferenceNetBufferList` at `0x140144f5a`
- `NETIO!NetioAdvanceNetBufferList` at `0x140144af7`
- `NETIO!NetioAdvanceNetBufferList` at `0x140144af7`
- `NETIO!NetioAllocateAndReferenceFragmentNetBufferList` at `0x140144a44`
- `NETIO!NetioAllocateAndReferenceFragmentNetBufferList` at `0x140144a44`
- `NDIS!NdisGetDataBuffer` at `0x140144b38`
- `NDIS!NdisGetDataBuffer` at `0x140144b38`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140144cb0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140144d27`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140144cb0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140144d27`

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
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 *v32; // rdx
  __int64 v33; // r10
  unsigned int jj; // eax
  int v35; // r10d
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 *v39; // rdx
  unsigned int kk; // eax
  __int64 v41; // rdx
  __int64 v42; // r11
  __int64 v43; // r8
  __int64 *v44; // rdx
  unsigned int mm; // eax
  __int64 *v46; // rbx
  unsigned int LockArray_high; // eax
  __int64 v48; // rdx
  __int64 v49; // rbx
  __int64 v50; // r12
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rcx
  _BYTE *v55; // rax
  ULONG v56; // esi
  int v57; // eax
  int v58; // r8d
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // rdi
  int PacketCount; // eax
  struct _NET_BUFFER *Alignment; // r12
  __int64 *v64; // rbx
  char *DataBuffer; // r8
  char v66; // dl
  __int64 v67; // xmm0_8
  __int16 v68; // cx
  int v69; // eax
  ULONG v70; // r13d
  unsigned __int8 *v71; // r14
  unsigned __int8 v72; // dl
  int v73; // r15d
  char v74; // r12
  bool v75; // zf
  int v76; // edi
  __int64 v77; // rax
  unsigned int v78; // edi
  __int16 v79; // r12
  unsigned __int16 v80; // cx
  unsigned __int16 v81; // r14
  __int16 j; // r12
  __int16 v83; // r15
  unsigned int v84; // eax
  __int64 v85; // rcx
  char *v86; // rax
  char *p_Src; // rdx
  size_t v88; // r8
  __int64 v89; // rcx
  char *v90; // rdi
  __int16 v91; // ax
  __int16 v92; // cx
  __int64 v93; // r8
  __int64 *v94; // rdx
  unsigned int k; // eax
  __int64 v96; // r9
  __int64 v97; // r10
  __int64 v98; // r8
  __int64 *v99; // rdx
  unsigned int m; // eax
  int v101; // eax
  __int64 v102; // r11
  __int64 v103; // rax
  __int64 v104; // r8
  __int64 *v105; // rdx
  unsigned int n; // eax
  __int64 v107; // rdx
  __int64 v108; // r10
  __int64 v109; // r8
  __int64 *v110; // rdx
  unsigned int ii; // eax
  __int64 CurrentProcess; // rax
  char *ProcessImageFileName; // rax
  int v114; // r8d
  __int64 v115; // rcx
  int v116; // ecx
  char v117; // al
  int BugCheckOnFailure; // [rsp+20h] [rbp-E0h]
  ULONG Priority; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v120; // [rsp+70h] [rbp-90h] BYREF
  char v121; // [rsp+72h] [rbp-8Eh] BYREF
  ULONG v122; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v123; // [rsp+78h] [rbp-88h] BYREF
  __int64 v124; // [rsp+80h] [rbp-80h] BYREF
  __int64 v125; // [rsp+88h] [rbp-78h] BYREF
  struct _NET_BUFFER *v126; // [rsp+90h] [rbp-70h]
  __int64 v127; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v128; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v129; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v130; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v131; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v132; // [rsp+C0h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-38h] BYREF
  char Src; // [rsp+E0h] [rbp-20h] BYREF
  int v135; // [rsp+E1h] [rbp-1Fh]
  char v136; // [rsp+E5h] [rbp-1Bh]
  __int16 v137; // [rsp+E6h] [rbp-1Ah]
  __int64 v138; // [rsp+E8h] [rbp-18h]
  int v139; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR v140; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v141; // [rsp+140h] [rbp+40h]
  __int64 v142; // [rsp+148h] [rbp+48h]
  __int64 *v143; // [rsp+150h] [rbp+50h]
  __int64 v144; // [rsp+158h] [rbp+58h]
  __int64 *v145; // [rsp+160h] [rbp+60h]
  __int64 v146; // [rsp+168h] [rbp+68h]
  __int64 *v147; // [rsp+170h] [rbp+70h]
  __int64 v148; // [rsp+178h] [rbp+78h]
  unsigned __int64 *v149; // [rsp+180h] [rbp+80h]
  __int64 v150; // [rsp+188h] [rbp+88h]
  __int64 *v151; // [rsp+190h] [rbp+90h]
  __int64 v152; // [rsp+198h] [rbp+98h]
  __int64 *v153; // [rsp+1A0h] [rbp+A0h]
  __int64 v154; // [rsp+1A8h] [rbp+A8h]
  __int64 *v155; // [rsp+1B0h] [rbp+B0h]
  __int64 v156; // [rsp+1B8h] [rbp+B8h]
  char *v157; // [rsp+1C0h] [rbp+C0h]
  int v158; // [rsp+1C8h] [rbp+C8h]
  int v159; // [rsp+1CCh] [rbp+CCh]
  char *v160; // [rsp+1D0h] [rbp+D0h]
  __int64 v161; // [rsp+1D8h] [rbp+D8h]
  unsigned int *v162; // [rsp+1E0h] [rbp+E0h]
  __int64 v163; // [rsp+1E8h] [rbp+E8h]
  __int16 *v164; // [rsp+1F0h] [rbp+F0h]
  __int64 v165; // [rsp+1F8h] [rbp+F8h]
  ULONG *v166; // [rsp+200h] [rbp+100h]
  __int64 v167; // [rsp+208h] [rbp+108h]
  char Storage[64]; // [rsp+210h] [rbp+110h] BYREF

  v75 = (*(_BYTE *)(a1 + 184) & 0x10) == 0;
  v4 = a2;
  v5 = *(_QWORD *)(a1 + 8);
  v6 = a1;
  v7 = *(_QWORD *)(a2 + 8);
  v125 = v5;
  v124 = v7;
  v131 = a2;
  v129 = a1;
  if ( v75 )
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
            v122 = *(_DWORD *)(v12 + 40);
            LOBYTE(v122) = v122 & 0xEF;
            *(_DWORD *)(v12 + 40) = v122;
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
        v5 = v125;
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
  v29 = (unsigned int)v27;
  if ( (int)v27 < 1 )
  {
    if ( *(_DWORD *)(v5 + 160) || *(_DWORD *)(v5 + 320) )
      goto LABEL_75;
    v46 = *(__int64 **)(v5 + 8);
    if ( !v46 )
      goto LABEL_74;
    while ( *((_DWORD *)v46 + 6) <= v9 )
    {
      v46 = (__int64 *)*v46;
      if ( !v46 )
        goto LABEL_74;
    }
    if ( (*(_BYTE *)(v6 + 88) & 4) == 0 )
    {
LABEL_78:
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      v48 = v124;
      v49 = *(_QWORD *)(v5 + 8);
      v50 = *(_QWORD *)(*(_QWORD *)(v4 + 104) + 8LL * LockArray_high);
      v51 = 3LL * LockArray_high;
      v52 = *(_QWORD *)v124;
      v132 = v50;
      v53 = (v51 << 6) + *(_QWORD *)(*(_QWORD *)(v52 + 40) + 20264LL);
      v54 = *(_QWORD *)(v49 + 8);
      v127 = v53;
      if ( (*(_BYTE *)(v54 + 10) & 5) != 0 )
      {
        v55 = *(_BYTE **)(v54 + 24);
      }
      else
      {
        v55 = MmMapLockedPagesSpecifyCache((PMDL)v54, 0, MmCached, 0, 0, 0x40000000u);
        v48 = v124;
      }
      v56 = (unsigned __int8)(4 * (v55[*(unsigned int *)(v49 + 16)] & 0xF));
      v122 = v56;
      if ( v56 + 8 > v9 )
      {
        v57 = -536854258;
        v58 = 259;
LABEL_87:
        IppDiscardSendPackets(*(_QWORD *)(*(_QWORD *)v124 + 40LL), v6, v58, 0, 0, 0, 3, v57);
        *(_DWORD *)(v5 + 140) = -1073741670;
        PacketCount = IppGetPacketCount(v5);
        *(_DWORD *)(v50 + 80) += PacketCount;
        result = (unsigned int)(*(_DWORD *)(v127 + 160) + PacketCount);
        *(_DWORD *)(v127 + 160) = result;
        return result;
      }
      LOBYTE(Priority) = 0;
      BugCheckOnFailure = *(unsigned __int16 *)(v48 + 130);
      v123 = ((_WORD)v9 - (_WORD)v56) & 0xFFF8;
      v59 = NetioAllocateAndReferenceFragmentNetBufferList(
              v5,
              v56,
              (unsigned __int16)(v9 - v56) & 0xFFF8,
              v56,
              BugCheckOnFailure,
              Priority);
      v130 = v59;
      v61 = v59;
      if ( !v59 )
      {
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
          McTemplateK0z_EtwWriteTransfer(
            &MICROSOFT_TCPIP_PROVIDER_Context,
            TCPIP_MEMORY_FAILURES,
            v60,
            L"IPv4 fragment (IPNG)");
        v57 = -536854257;
        v58 = 264;
        goto LABEL_87;
      }
      NetioAdvanceNetBufferList(v59, v56);
      Alignment = *(struct _NET_BUFFER **)(v5 + 8);
      v64 = *(__int64 **)(v61 + 8);
      v126 = Alignment;
      if ( Alignment )
      {
        do
        {
          DataBuffer = (char *)NdisGetDataBuffer(Alignment, v56, Storage, 1u, 0);
          v128 = (unsigned __int64)DataBuffer;
          v66 = *DataBuffer;
          v67 = *((_QWORD *)DataBuffer + 1);
          v135 = *(_DWORD *)(DataBuffer + 1);
          v136 = DataBuffer[5];
          v68 = *((_WORD *)DataBuffer + 3);
          v69 = *((_DWORD *)DataBuffer + 4);
          v120 = v68;
          v137 = v68;
          v139 = v69;
          Src = v66;
          v138 = v67;
          if ( v66 == 69 )
          {
            v70 = 20;
          }
          else
          {
            v71 = (unsigned __int8 *)(DataBuffer + 20);
            v72 = 4 * (v66 & 0xF);
            v70 = 20;
            v73 = v72 - 20;
            if ( v72 != 20 )
            {
              do
              {
                v74 = *v71;
                v75 = *v71 == 0;
                if ( (*v71 & 0x80u) != 0 )
                {
                  v76 = v71[1];
                  memmove(&Src + v70, v71, v71[1]);
                  v70 += v76;
                  v75 = v74 == 0;
                }
                if ( v75 )
                  break;
                if ( v74 == 1 )
                {
                  --v73;
                  ++v71;
                }
                else
                {
                  v77 = v71[1];
                  v73 -= v77;
                  v71 += v77;
                }
              }
              while ( v73 );
              v56 = v122;
              Alignment = v126;
            }
            v78 = -v70 & 3;
            if ( v78 )
            {
              memset(&Src + v70, 0, v78);
              v70 += v78;
            }
            Src = Src & 0xF0 | (v70 >> 2) & 0xF;
            v68 = v120;
          }
          v79 = *((_WORD *)&Alignment->NetBufferHeader.Link + 12);
          v137 &= 0xE0u;
          v80 = 8 * __ROR2__(v68 & 0xFF1F, 8);
          v120 = v80;
          v81 = v80;
          for ( j = v79 - v56; j; j -= v83 )
          {
            v83 = *((_WORD *)v64 + 12);
            v84 = *((_DWORD *)v64 + 4);
            if ( v81 == v80 )
            {
              if ( v84 < v56 )
              {
                NdisRetreatNetBufferDataStart((PNET_BUFFER)v64, v56, 0, NetioAllocateMdl);
              }
              else
              {
                *((_DWORD *)v64 + 10) -= v56;
                *((_DWORD *)v64 + 6) += v56;
                *((_DWORD *)v64 + 4) = v84 - v56;
              }
              v85 = v64[1];
              if ( (*(_BYTE *)(v85 + 10) & 5) != 0 )
                v86 = *(char **)(v85 + 24);
              else
                v86 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v85, 0, MmCached, 0, 0, 0x40000000u);
              p_Src = (char *)v128;
              v88 = v56;
            }
            else
            {
              if ( v84 < v70 )
              {
                NdisRetreatNetBufferDataStart((PNET_BUFFER)v64, v70, 0, NetioAllocateMdl);
              }
              else
              {
                *((_DWORD *)v64 + 10) -= v70;
                *((_DWORD *)v64 + 6) += v70;
                *((_DWORD *)v64 + 4) = v84 - v70;
              }
              v89 = v64[1];
              if ( (*(_BYTE *)(v89 + 10) & 5) != 0 )
                v86 = *(char **)(v89 + 24);
              else
                v86 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v89, 0, MmCached, 0, 0, 0x40000000u);
              v88 = v70;
              p_Src = &Src;
            }
            v90 = &v86[*((unsigned int *)v64 + 4)];
            memmove(v90, p_Src, v88);
            if ( v126->DataLength - v56 > v123 )
            {
              *((_WORD *)v90 + 1) = __ROR2__(*((_WORD *)v64 + 12), 8);
              v91 = 0;
              v92 = *((_WORD *)v90 + 3) | __ROR2__(v81 >> 3, 8);
              if ( j != v83 )
                v91 = 32;
              *((_WORD *)v90 + 3) = v92 & 0xFFDF ^ (v92 | v91) & 0x20;
            }
            v64 = (__int64 *)*v64;
            v81 += v83;
            v80 = v120;
          }
          Alignment = (struct _NET_BUFFER *)v126->Link.Alignment;
          v126 = Alignment;
        }
        while ( Alignment );
        v6 = v129;
        v5 = v125;
        v61 = v130;
        v4 = v131;
      }
      v93 = *(_QWORD *)(v5 + 160);
      v94 = *(__int64 **)(v5 + 8);
      if ( (_DWORD)v93 || *(_DWORD *)(v5 + 320) )
      {
        if ( !v93 )
          LODWORD(v93) = *(_DWORD *)(v5 + 320);
        k = (((unsigned int)v93 & 0xFFFFF) + *((_DWORD *)v94 + 21) - 1) / ((unsigned int)v93 & 0xFFFFF);
      }
      else
      {
        for ( k = 0; v94; ++k )
          v94 = (__int64 *)*v94;
      }
      v96 = v132;
      v97 = v127;
      *(_DWORD *)(v132 + 76) += k;
      *(_DWORD *)(v97 + 156) += k;
      v98 = *(_QWORD *)(v61 + 160);
      v99 = *(__int64 **)(v61 + 8);
      if ( (_DWORD)v98 || *(_DWORD *)(v61 + 320) )
      {
        if ( !v98 )
          LODWORD(v98) = *(_DWORD *)(v61 + 320);
        m = (((unsigned int)v98 & 0xFFFFF) + *((_DWORD *)v99 + 21) - 1) / ((unsigned int)v98 & 0xFFFFF);
      }
      else
      {
        for ( m = 0; v99; ++m )
          v99 = (__int64 *)*v99;
      }
      *(_DWORD *)(v96 + 84) += m;
      *(_DWORD *)(v97 + 164) += m;
      v101 = IPsecProcessOutboundFragList(0, v5, v61);
      if ( v101 >= 1 )
      {
        if ( v101 == 1 )
          IppDiscardSendPackets(*(_QWORD *)(*(_QWORD *)v124 + 40LL), v6, 9, 0, 0, 0, 3, -536854255);
        NetioDereferenceNetBufferList(v5, 0);
        result = NetioDereferenceNetBufferList(v61, 0);
        *(_QWORD *)(v6 + 8) = 0;
        return result;
      }
      NetioDereferenceNetBufferList(v5, 0);
      *(_QWORD *)(v6 + 8) = v61;
LABEL_74:
      Ipv4pChecksumPacket(v4, v6);
LABEL_75:
      result = *(_QWORD *)(v6 + 8);
      *(_DWORD *)(result + 140) = 0;
      return result;
    }
    *(_DWORD *)(v5 + 140) = -1073741306;
    v102 = *(_QWORD *)(*(_QWORD *)v7 + 40LL);
    v103 = *(_QWORD *)(v6 + 8);
    v104 = *(_QWORD *)(v103 + 160);
    v105 = *(__int64 **)(v103 + 8);
    if ( (_DWORD)v104 || *(_DWORD *)(v103 + 320) )
    {
      if ( !v104 )
        LODWORD(v104) = *(_DWORD *)(v103 + 320);
      v104 &= 0xFFFFFu;
      n = ((int)v104 + *((_DWORD *)v105 + 21) - 1) / (unsigned int)v104;
    }
    else
    {
      for ( n = 0; v105; ++n )
        v105 = (__int64 *)*v105;
    }
    LODWORD(v28) = HIDWORD(KeGetPcr()[1].LockArray);
    v107 = *(_QWORD *)(v102 + 20264) + 192 * v28;
    result = *(_DWORD *)(v107 + 152) + n;
    *(_DWORD *)(v107 + 152) = result;
    if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
    {
      v108 = *(_QWORD *)(v6 + 8);
      v109 = *(_QWORD *)(v108 + 160);
      v110 = *(__int64 **)(v108 + 8);
      if ( (_DWORD)v109 || *(_DWORD *)(v108 + 320) )
      {
        if ( !v109 )
          LODWORD(v109) = *(_DWORD *)(v108 + 320);
        ii = (((unsigned int)v109 & 0xFFFFF) + *((_DWORD *)v110 + 21) - 1) / ((unsigned int)v109 & 0xFFFFF);
      }
      else
      {
        for ( ii = 0; v110; ++ii )
          v110 = (__int64 *)*v110;
      }
      result = IppLogPacketDiscard(
                 *(unsigned __int16 *)(v102 + 28),
                 *(unsigned __int16 *)(v6 + 104),
                 *(_QWORD *)(v6 + 264),
                 *(_QWORD *)(v6 + 248),
                 258,
                 ii,
                 0,
                 v108,
                 *(_QWORD *)(*(_QWORD *)(v6 + 224) + 8LL),
                 3,
                 -536854259);
    }
    if ( *(_DWORD *)(v6 + 108) != -1 )
    {
      result = (unsigned int)dword_1402201F8;
      if ( (unsigned int)dword_1402201F8 > 5 )
      {
        result = qword_140220208;
        if ( (qword_140220208 & 0x400000000000LL) != 0 )
        {
          result = qword_140220210 & 0x400000000000LL;
          if ( (qword_140220210 & 0x400000000000LL) == qword_140220210 )
          {
            v132 = 1;
            v141 = &v132;
            v131 = *((unsigned int *)v46 + 6);
            v130 = v131;
            v129 = v131;
            v147 = &v129;
            v143 = &v131;
            v128 = v13;
            v127 = v13;
            v125 = v13;
            v145 = &v130;
            v153 = &v125;
            v149 = &v128;
            v155 = &v124;
            v142 = 8;
            v144 = 8;
            v146 = 8;
            v148 = 8;
            v150 = 8;
            v151 = &v127;
            v152 = 8;
            v154 = 8;
            v124 = 0x2000000;
            v156 = 8;
            CurrentProcess = PsGetCurrentProcess(&v127, 0x400000000000LL, v104, v29);
            ProcessImageFileName = (char *)PsGetProcessImageFileName(CurrentProcess);
            if ( ProcessImageFileName )
            {
              v115 = -1;
              do
                ++v115;
              while ( ProcessImageFileName[v115] );
              v116 = v115 + 1;
            }
            else
            {
              ProcessImageFileName = byte_1401DD2E3;
              v116 = 1;
            }
            v157 = ProcessImageFileName;
            v158 = v116;
            v160 = &v121;
            v123 = *(_DWORD *)(v6 + 108);
            v162 = &v123;
            v117 = (*(_BYTE *)(v6 + 90) >> 4) & 3;
            v159 = 0;
            LOBYTE(v120) = v117;
            v164 = (__int16 *)&v120;
            LOWORD(v122) = *(_WORD *)(v6 + 104);
            v166 = &v122;
            v121 = 2;
            v161 = 1;
            v163 = 4;
            v165 = 1;
            v167 = 2;
            return tlgWriteAgg((int)&dword_1402201F8, (int)&word_1401F34EA, v114, 15, &v140);
          }
        }
      }
    }
  }
  else
  {
    v30 = (unsigned int)(v27 - 1);
    if ( (unsigned int)v30 <= 1 )
    {
      LODWORD(v27) = HIDWORD(KeGetPcr()[1].LockArray);
      v31 = *(_QWORD *)(v5 + 160);
      v32 = *(__int64 **)(v5 + 8);
      v33 = qword_140216678 + 192 * v27;
      if ( (_DWORD)v31 || *(_DWORD *)(v5 + 320) )
      {
        if ( !v31 )
          LODWORD(v31) = *(_DWORD *)(v5 + 320);
        jj = (((unsigned int)v31 & 0xFFFFF) + *((_DWORD *)v32 + 21) - 1) / ((unsigned int)v31 & 0xFFFFF);
      }
      else
      {
        for ( jj = 0; v32; ++jj )
          v32 = (__int64 *)*v32;
      }
      *(_DWORD *)(v33 + 172) += jj;
      v35 = 9;
      *(_DWORD *)(*(_QWORD *)(v6 + 8) + 140LL) = -1073741285;
      if ( (_DWORD)v29 != 1 )
        v35 = 11;
      v36 = *(_QWORD *)(*(_QWORD *)v7 + 40LL);
      v37 = *(_QWORD *)(v6 + 8);
      v38 = *(_QWORD *)(v37 + 160);
      v39 = *(__int64 **)(v37 + 8);
      if ( (_DWORD)v38 || *(_DWORD *)(v37 + 320) )
      {
        if ( !v38 )
          LODWORD(v38) = *(_DWORD *)(v37 + 320);
        kk = (((unsigned int)v38 & 0xFFFFF) + *((_DWORD *)v39 + 21) - 1) / ((unsigned int)v38 & 0xFFFFF);
      }
      else
      {
        for ( kk = 0; v39; ++kk )
          v39 = (__int64 *)*v39;
      }
      LODWORD(v30) = HIDWORD(KeGetPcr()[1].LockArray);
      v41 = *(_QWORD *)(v36 + 20264) + 192 * v30;
      result = *(_DWORD *)(v41 + 152) + kk;
      *(_DWORD *)(v41 + 152) = result;
      if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
      {
        v42 = *(_QWORD *)(v6 + 8);
        v43 = *(_QWORD *)(v42 + 160);
        v44 = *(__int64 **)(v42 + 8);
        if ( (_DWORD)v43 || *(_DWORD *)(v42 + 320) )
        {
          if ( !v43 )
            LODWORD(v43) = *(_DWORD *)(v42 + 320);
          mm = (((unsigned int)v43 & 0xFFFFF) + *((_DWORD *)v44 + 21) - 1) / ((unsigned int)v43 & 0xFFFFF);
        }
        else
        {
          for ( mm = 0; v44; ++mm )
            v44 = (__int64 *)*v44;
        }
        return IppLogPacketDiscard(
                 *(unsigned __int16 *)(v36 + 28),
                 *(unsigned __int16 *)(v6 + 104),
                 *(_QWORD *)(v6 + 264),
                 *(_QWORD *)(v6 + 248),
                 v35,
                 mm,
                 0,
                 v42,
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
0x140144400  mov     [rsp-8+arg_10], rbx
0x140144405  push    rbp
0x140144406  push    rsi
0x140144407  push    rdi
0x140144408  push    r12
0x14014440a  push    r13
0x14014440c  push    r14
0x14014440e  push    r15
0x140144410  lea     rbp, [rsp-160h]
0x140144418  sub     rsp, 260h
0x14014441f  mov     rax, cs:__security_cookie
0x140144426  xor     rax, rsp
0x140144429  mov     [rbp+190h+var_40], rax
0x140144430  test    byte ptr [rcx+0B8h], 10h
0x140144437  mov     r15, rdx
0x14014443a  mov     r14, [rcx+8]
0x14014443e  mov     r13, rcx
0x140144441  mov     r12, [rdx+8]
0x140144445  mov     [rbp+190h+var_208], r14
0x140144449  mov     [rbp+190h+var_210], r12
0x14014444d  mov     [rbp+190h+var_1D8], rdx
0x140144451  mov     [rbp+190h+var_1E8], rcx
0x140144455  jnz     loc_1401444DB
0x14014445b  cmp     dword ptr [r14+0A0h], 0
0x140144463  jnz     loc_140144938
0x140144469  mov     r9, [r14+8]
0x14014446d  mov     edi, [rdx+5Ch]
0x140144470  cmp     [r9+18h], edi
0x140144474  jbe     loc_140144938
0x14014447a  mov     rax, [rcx+118h]
0x140144481  test    byte ptr [rax+6], 40h
0x140144485  jz      loc_14014497C
0x14014448b  mov     r9d, [r9+5Ch]
0x14014448f  mov     r8d, 102h
0x140144495  mov     dword ptr [r14+8Ch], 0C0000206h
0x1401444a0  mov     rdx, r13
0x1401444a3  mov     rcx, [r12]
0x1401444a7  shr     r9d, 4
0x1401444ab  mov     dword ptr [rsp+290h+var_258], 0E000410Ch
0x1401444b3  not     r9b
0x1401444b6  mov     [rsp+290h+var_260], 3
0x1401444be  and     r9b, 1
0x1401444c2  mov     rcx, [rcx+28h]
0x1401444c6  bswap   edi
0x1401444c8  mov     [rsp+290h+Priority], edi
0x1401444cc  mov     byte ptr [rsp+290h+BugCheckOnFailure], 0
0x1401444d1  call    IppDiscardSendPackets
0x1401444d6  jmp     loc_140144946
0x1401444db  mov     rbx, [rcx+0D0h]
0x1401444e2  test    rbx, rbx
0x1401444e5  jnz     short loc_1401444EF
0x1401444e7  mov     esi, [rdx+5Ch]
0x1401444ea  jmp     loc_14014468C
0x1401444ef  mov     rax, [rbx]
0x1401444f2  mov     r8, r15
0x1401444f5  mov     rcx, rbx
0x1401444f8  mov     rsi, [rax+8]
0x1401444fc  mov     rdx, rsi
0x1401444ff  call    Ipv4pPathMtuTimeoutFired
0x140144504  test    al, al
0x140144506  jz      loc_140144689
0x14014450c  xor     eax, eax
0x14014450e  xorps   xmm0, xmm0
0x140144511  mov     r8, r15
0x140144514  mov     qword ptr [rbp+190h+LockHandle.OldIrql], rax
0x140144518  mov     rdx, rsi
0x14014451b  movups  xmmword ptr [rbp+190h+LockHandle.LockQueue.Next], xmm0
0x14014451f  call    Ipv4pPathMtuTimeoutFired
0x140144524  test    al, al
0x140144526  jz      loc_140144689
0x14014452c  mov     r14, [rsi]
0x14014452f  lea     rdx, [rbp+190h+LockHandle]; LockHandle
0x140144533  lea     rcx, [r14+340h]; SpinLock
0x14014453a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140144541  nop     dword ptr [rax+rax+00h]
0x140144546  xor     r8d, r8d
0x140144549  cmp     [r14+348h], r8d
0x140144550  jl      short loc_140144588
0x140144552  nop     dword ptr [rax+00h]
0x140144556  nop     word ptr [rax+rax+00000000h]
0x140144560  movsxd  rcx, r8d
0x140144563  shl     rcx, 6
0x140144567  nop     word ptr [rax+rax+00000000h]
0x140144570  mov     eax, [rcx+r14+380h]
0x140144578  test    eax, eax
0x14014457a  jnz     short loc_140144570
0x14014457c  inc     r8d
0x14014457f  cmp     r8d, [r14+348h]
0x140144586  jle     short loc_140144560
0x140144588  mov     r8, r15
0x14014458b  mov     rdx, rsi
0x14014458e  mov     rcx, rbx
0x140144591  call    Ipv4pPathMtuTimeoutFired
0x140144596  test    al, al
0x140144598  jz      loc_140144675
0x14014459e  mov     edx, [rbx+70h]
0x1401445a1  lea     r8, Ipv4pMtuTable
0x1401445a8  mov     ecx, 8
0x1401445ad  nop     dword ptr [rax]
0x1401445b0  mov     eax, ecx
0x1401445b2  cmp     [r8+rax*4], edx
0x1401445b6  ja      short loc_1401445BD
0x1401445b8  add     ecx, 0FFFFFFFFh
0x1401445bb  jnz     short loc_1401445B0
0x1401445bd  mov     edi, [r15+5Ch]
0x1401445c1  mov     eax, ecx
0x1401445c3  mov     ecx, [r8+rax*4]
0x1401445c7  cmp     ecx, edi
0x1401445c9  cmovbe  edi, ecx
0x1401445cc  mov     eax, cs:Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState
0x1401445d2  test    al, 10h
0x1401445d4  jz      short loc_1401445DB
0x1401445d6  and     eax, 1
0x1401445d9  jmp     short loc_1401445E0
0x1401445db  call    Feature_TCPIP_2025_2512_KCSAN_Fix__private_IsEnabledDeviceUsageNoInline
0x1401445e0  test    eax, eax
0x1401445e2  jnz     short loc_1401445EA
0x1401445e4  and     byte ptr [rbx+28h], 0EFh
0x1401445e8  jmp     short loc_1401445FE
0x1401445ea  mov     eax, [rbx+28h]
0x1401445ed  mov     [rsp+290h+var_21C], eax
0x1401445f1  and     al, 0EFh
0x1401445f3  mov     byte ptr [rsp+290h+var_21C], al
0x1401445f7  mov     eax, [rsp+290h+var_21C]
0x1401445fb  mov     [rbx+28h], eax
0x1401445fe  mov     rcx, 0FFFFF78000000008h
0x140144608  mov     rax, 346DC5D63886594Bh
0x140144612  mov     rcx, [rcx]
0x140144615  mul     rcx
0x140144618  mov     rax, 624DD2F1A9FBE77h
0x140144622  mov     rcx, rdx
0x140144625  shr     rcx, 0Bh
0x140144629  mul     rcx
0x14014462c  mov     eax, [rbx+70h]
0x14014462f  sub     rcx, rdx
0x140144632  shr     rcx, 1
0x140144635  add     rcx, rdx
0x140144638  shr     rcx, 8
0x14014463c  cmp     eax, edi
0x14014463e  jbe     short loc_140144646
0x140144640  or      byte ptr [rbx+28h], 8
0x140144644  jmp     short loc_14014464E
0x140144646  test    eax, eax
0x140144648  jz      short loc_14014464E
0x14014464a  and     byte ptr [rbx+28h], 0F7h
0x14014464e  mov     [rbx+70h], edi
0x140144651  mov     [rbx+74h], ecx
0x140144654  lock inc dword ptr [rbx+1Ch]
0x140144658  lea     rcx, [rbp+190h+LockHandle]; LockHandle
0x14014465c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140144663  nop     dword ptr [rax+rax+00h]
0x140144668  mov     rdx, rbx
0x14014466b  mov     rcx, r14
0x14014466e  call    IppUpdatePathNotification
0x140144673  jmp     short loc_140144685
0x140144675  lea     rcx, [rbp+190h+LockHandle]; LockHandle
0x140144679  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140144680  nop     dword ptr [rax+rax+00h]
0x140144685  mov     r14, [rbp+190h+var_208]
0x140144689  mov     esi, [rbx+70h]
0x14014468c  movzx   eax, byte ptr [r13+5Ah]
0x140144691  and     al, 30h
0x140144693  sub     al, 20h ; ' '
0x140144695  test    al, 0EFh
0x140144697  mov     eax, esi
0x140144699  jnz     short loc_14014469F
0x14014469b  mov     eax, [r15+5Ch]
0x14014469f  mov     edi, [r13+6Ch]
0x1401446a3  lea     r8, [r13+0E8h]
0x1401446aa  movzx   edx, byte ptr [r13+58h]
0x1401446af  cmp     eax, edi
0x1401446b1  movzx   ecx, word ptr [r13+3Ch]
0x1401446b6  cmovb   edi, eax
0x1401446b9  mov     [rsp+290h+var_228], r14
0x1401446be  mov     eax, [r13+0C4h]
0x1401446c5  mov     [rsp+290h+var_230], eax
0x1401446c9  mov     eax, [r15+18h]
0x1401446cd  shr     dl, 2
0x1401446d0  and     dl, 1
0x1401446d3  mov     byte ptr [rsp+290h+var_240], dl
0x1401446d7  mov     rdx, [r13+0E0h]
0x1401446de  mov     [rsp+290h+var_248], edi
0x1401446e2  mov     dword ptr [rsp+290h+var_250], ecx
0x1401446e6  xor     ecx, ecx
0x1401446e8  mov     byte ptr [rsp+290h+var_260], 0
0x1401446ed  mov     [rsp+290h+Priority], eax
0x1401446f1  mov     qword ptr [rsp+290h+BugCheckOnFailure], r12
0x1401446f6  call    IppInspectLocalPacketsOut
0x1401446fb  mov     r9d, eax
0x1401446fe  cmp     eax, 1
0x140144701  jl      loc_1401448FD
0x140144707  lea     ecx, [rax-1]
0x14014470a  cmp     ecx, 1
0x14014470d  jbe     short loc_14014472E
0x14014470f  mov     rcx, [r13+8]
0x140144713  xor     edx, edx
0x140144715  call    cs:__imp_NetioDereferenceNetBufferList
0x14014471c  nop     dword ptr [rax+rax+00h]
0x140144721  mov     qword ptr [r13+8], 0
0x140144729  jmp     loc_140144946
0x14014472e  mov     eax, gs:1A4h
0x140144736  mov     r8, [r14+0A0h]
0x14014473d  mov     rdx, [r14+8]
0x140144741  lea     r10, [rax+rax*2]
0x140144745  shl     r10, 6
0x140144749  add     r10, cs:qword_140216678
0x140144750  test    r8d, r8d
0x140144753  jnz     short loc_140144771
0x140144755  cmp     [r14+140h], r8d
0x14014475c  jnz     short loc_140144771
0x14014475e  xor     eax, eax
0x140144760  test    rdx, rdx
0x140144763  jz      short loc_140144791
0x140144765  mov     rdx, [rdx]
0x140144768  inc     eax
0x14014476a  test    rdx, rdx
0x14014476d  jnz     short loc_140144765
0x14014476f  jmp     short loc_140144791
0x140144771  test    r8, r8
0x140144774  jnz     short loc_14014477D
0x140144776  mov     r8d, [r14+140h]
0x14014477d  mov     eax, [rdx+54h]
0x140144780  and     r8d, 0FFFFFh
0x140144787  dec     eax
0x140144789  xor     edx, edx
0x14014478b  add     eax, r8d
0x14014478e  div     r8d
0x140144791  add     [r10+0ACh], eax
0x140144798  mov     r10d, 9
0x14014479e  mov     rax, [r13+8]
0x1401447a2  cmp     r9d, 1
0x1401447a6  mov     dword ptr [rax+8Ch], 0C000021Bh
0x1401447b0  mov     eax, 0Bh
0x1401447b5  cmovnz  r10d, eax
0x1401447b9  mov     rax, [r12]
0x1401447bd  mov     rbx, [rax+28h]
0x1401447c1  mov     rax, [r13+8]
0x1401447c5  mov     r8, [rax+0A0h]
0x1401447cc  mov     rdx, [rax+8]
0x1401447d0  test    r8d, r8d
0x1401447d3  jnz     short loc_1401447F1
0x1401447d5  cmp     [rax+140h], r8d
0x1401447dc  jnz     short loc_1401447F1
0x1401447de  xor     eax, eax
0x1401447e0  test    rdx, rdx
0x1401447e3  jz      short loc_140144811
0x1401447e5  mov     rdx, [rdx]
0x1401447e8  inc     eax
0x1401447ea  test    rdx, rdx
0x1401447ed  jnz     short loc_1401447E5
0x1401447ef  jmp     short loc_140144811
0x1401447f1  test    r8, r8
0x1401447f4  jnz     short loc_1401447FD
0x1401447f6  mov     r8d, [rax+140h]
0x1401447fd  mov     eax, [rdx+54h]
0x140144800  and     r8d, 0FFFFFh
0x140144807  dec     eax
0x140144809  xor     edx, edx
0x14014480b  add     eax, r8d
0x14014480e  div     r8d
0x140144811  mov     ecx, gs:1A4h
0x140144819  lea     rdx, [rcx+rcx*2]
0x14014481d  shl     rdx, 6
0x140144821  add     rdx, [rbx+4F28h]
0x140144828  mov     ecx, [rdx+98h]
0x14014482e  add     eax, ecx
0x140144830  mov     [rdx+98h], eax
0x140144836  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+6, 0
0x14014483d  jl      short loc_14014484C
0x14014483f  cmp     cs:byte_140225C70, 0
0x140144846  jz      loc_140144946
0x14014484c  mov     r11, [r13+8]
0x140144850  mov     rax, [r13+0E0h]
0x140144857  mov     rdi, [r13+108h]
0x14014485e  mov     rsi, [r13+0F8h]
0x140144865  mov     r8, [r11+0A0h]
0x14014486c  mov     r14, [rax+8]
0x140144870  mov     rdx, [r11+8]
0x140144874  test    r8d, r8d
0x140144877  jnz     short loc_14014489C
0x140144879  cmp     [r11+140h], r8d
0x140144880  jnz     short loc_14014489C
0x140144882  xor     eax, eax
0x140144884  test    rdx, rdx
0x140144887  jz      short loc_1401448BC
0x140144889  nop     dword ptr [rax+00000000h]
0x140144890  mov     rdx, [rdx]
0x140144893  inc     eax
0x140144895  test    rdx, rdx
0x140144898  jnz     short loc_140144890
0x14014489a  jmp     short loc_1401448BC
0x14014489c  test    r8, r8
0x14014489f  jnz     short loc_1401448A8
0x1401448a1  mov     r8d, [r11+140h]
0x1401448a8  mov     eax, [rdx+54h]
0x1401448ab  and     r8d, 0FFFFFh
0x1401448b2  dec     eax
0x1401448b4  xor     edx, edx
0x1401448b6  add     eax, r8d
0x1401448b9  div     r8d
  ... truncated ...
```
