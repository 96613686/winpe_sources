# IppPacketizeDatagrams

- ea: `0x140028dc0`
- end: `0x140029c92`
- name: `IppPacketizeDatagrams`
- size: `3794`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140045ad0`
- `0x1400cca84`
- `0x14018d800`

## callees

- `0x140014a08`
- `0x14001b404`
- `0x140027b7c`
- `0x14002821c`
- `0x140028790`
- `0x1400289c0`
- `0x140028bf8`
- `0x140028d80`
- `0x140028dc0`
- `0x140029ca0`
- `0x14002a0c0`
- `0x14002a140`
- `0x14002a5d0`
- `0x1400bbea0`
- `0x1400dec50`
- `0x140129abc`
- `0x14012f1d0`
- `0x1401317c8`
- `0x14014edf4`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x140276760`
- `0x14027aa58`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002904f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029344`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029363`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002904f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029344`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029363`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029c7d`
- `NETIO!NetioAllocateMdl` at `0x140029a2f`
- `NETIO!NetioAllocateMdl` at `0x140029856`
- `NETIO!NetioAllocateMdl` at `0x140029a2f`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029988`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029b49`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029b82`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029988`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029b49`
- `NETIO!NetioDereferenceNetBufferList` at `0x140029b82`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x14002995d`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x14002995d`
- `NETIO!NetioCompleteCloneNetBufferListChain` at `0x1400299e8`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140029a70`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140029b36`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140029a70`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140029b36`
- `NETIO!NetioExpandNetBuffer` at `0x140029a55`
- `NETIO!NetioExpandNetBuffer` at `0x140029a55`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferListEx` at `0x1400299f8`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferListEx` at `0x1400299f8`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140029863`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140029863`

## string_xrefs

- `0x140029c41`: `retreat extension header (IPNG)`

## pseudocode

```c
__int64 __fastcall IppPacketizeDatagrams(__int64 a1, __int64 a2, __int64 a3)
{
  void *v3; // r9
  __int64 v4; // rdi
  unsigned __int16 *v6; // r13
  __int64 v7; // r14
  _QWORD *v8; // rax
  unsigned int SegmentationOffloadPacketCount; // esi
  __int64 v10; // rcx
  int v11; // r12d
  __int64 result; // rax
  bool v13; // zf
  int v14; // r15d
  unsigned int v15; // r10d
  unsigned int v16; // r15d
  __int64 v17; // r8
  unsigned __int16 v18; // si
  int v19; // r13d
  NDIS_STATUS v20; // edi
  unsigned int v21; // r13d
  struct _NET_BUFFER *v22; // rsi
  unsigned __int8 v23; // di
  unsigned int v24; // ecx
  __int64 v25; // rax
  ULONG v26; // ecx
  int v27; // eax
  struct _NET_BUFFER **v28; // rsi
  int v29; // eax
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  int v33; // eax
  __int64 v34; // rax
  int v35; // r8d
  __int64 v36; // rcx
  _DWORD *v37; // rcx
  int v38; // eax
  __int64 v39; // r8
  __int64 *v40; // rsi
  __int64 v41; // r11
  char v42; // di
  unsigned int v43; // r8d
  _DWORD *v44; // rcx
  void *v45; // rdi
  int v46; // r15d
  int v47; // r12d
  int v48; // esi
  void *v49; // rcx
  void *v50; // rcx
  void *v51; // rcx
  __int64 v52; // rdx
  _QWORD *v53; // rax
  int i; // r9d
  __int64 v55; // rax
  __int64 v56; // r11
  int MtuFromNextHop; // edi
  __int64 v58; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v60; // ecx
  __int64 v61; // rdx
  int PacketCount; // eax
  __int64 v63; // r9
  __int64 v64; // r10
  ULONG v65; // edx
  ULONG v66; // ecx
  ULONG CurrentMdlOffset; // eax
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // r11
  __m128i v71; // xmm7
  __m128i v72; // xmm4
  __m128i v73; // xmm6
  __m128i v74; // xmm5
  __m128i v75; // xmm3
  __int64 v76; // r8
  __m128i v77; // xmm2
  __m128i v78; // xmm1
  __m128i v79; // xmm3
  __m128i v80; // xmm3
  __m128i v81; // xmm5
  __m128i v82; // xmm6
  __m128i v83; // xmm5
  __m128i v84; // xmm6
  int v85; // ecx
  __int64 v86; // r8
  int *v87; // r10
  __int64 SecurityContext; // rax
  __int64 v89; // r9
  __int64 v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 j; // rax
  PMDL Mdl; // rax
  _DWORD *v96; // r9
  _QWORD *v97; // rcx
  _DWORD *v98; // r11
  bool v99; // sf
  int v100; // eax
  _QWORD *v101; // rdx
  __int64 v102; // rax
  unsigned int v103; // r8d
  unsigned __int64 v104; // rcx
  __int64 v105; // rax
  unsigned __int64 v106; // r8
  int v107; // [rsp+20h] [rbp-E0h]
  int v108; // [rsp+20h] [rbp-E0h]
  ULONG v109[2]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v110; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v111; // [rsp+61h] [rbp-9Fh]
  int v112; // [rsp+64h] [rbp-9Ch]
  char v113; // [rsp+68h] [rbp-98h]
  unsigned int v114; // [rsp+70h] [rbp-90h]
  ULONG v115; // [rsp+70h] [rbp-90h]
  __int64 v116; // [rsp+70h] [rbp-90h]
  ULONG BufferSize[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v118; // [rsp+80h] [rbp-80h]
  unsigned int v119; // [rsp+84h] [rbp-7Ch]
  int *v120; // [rsp+88h] [rbp-78h]
  int v121[4]; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v123; // [rsp+A8h] [rbp-58h]
  __int128 v124; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v125[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v126[4]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD DataOffsetDelta[9]; // [rsp+E4h] [rbp-1Ch]

  v3 = 0;
  v4 = *(_QWORD *)(a1 + 8);
  v113 = a2;
  v6 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 216) + 8LL);
  v123 = v6;
  v7 = *(_QWORD *)(*(_QWORD *)v6 + 40LL);
  if ( *(_DWORD *)(v4 + 160) || *(_DWORD *)(v4 + 320) )
  {
    SegmentationOffloadPacketCount = IppGetSegmentationOffloadPacketCount(v4);
  }
  else
  {
    v8 = *(_QWORD **)(v4 + 8);
    for ( SegmentationOffloadPacketCount = 0; v8; ++SegmentationOffloadPacketCount )
      v8 = (_QWORD *)*v8;
  }
  v10 = *(unsigned int *)(a1 + 32);
  v11 = *(_DWORD *)(v4 + 136) & 0x400000;
  Src = v3;
  if ( (_DWORD)v10 != 6 )
  {
    v10 = (unsigned int)(v10 - 1);
    if ( (_DWORD)v10 )
    {
      v10 = (unsigned int)(v10 - 16);
      if ( !(_DWORD)v10 )
      {
        v112 = 6;
        goto LABEL_7;
      }
      if ( (_DWORD)v10 != 41 )
      {
        v112 = (int)v3;
        goto LABEL_7;
      }
    }
    v112 = 8;
    goto LABEL_7;
  }
  v112 = 5;
LABEL_7:
  v118 = (unsigned int)v3;
  HIDWORD(result) = 0;
  v114 = (unsigned int)v3;
  v13 = (*(_BYTE *)(a1 + 187) & 2) == 0;
  v14 = (int)v3;
  memset(v125, 0, 28);
  v15 = (unsigned int)v3;
  v119 = (unsigned int)v3;
  LODWORD(v120) = (_DWORD)v3;
  v124 = 0;
  v111 = 0;
  if ( !v13 && *(_DWORD *)(v4 + 320) )
  {
    *(_OWORD *)v121 = 0;
    if ( (Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2512_KCSAN_Fix__private_IsEnabledDeviceUsageNoInline(
                                       v10,
                                       a2,
                                       a3);
    v60 = *(_DWORD *)(a1 + 44);
    v61 = *(unsigned __int16 *)(v7 + 40);
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( v60 > (unsigned int)v61 )
      {
        LOBYTE(v61) = 1;
        goto LABEL_96;
      }
      if ( (__int64 *)v7 == &Ipv6Global )
      {
        v105 = *(_QWORD *)(a1 + 208);
        if ( v105 )
        {
          if ( (*(_DWORD *)(v105 + 40) & 0x10) != 0 )
          {
            LOBYTE(v61) = 1;
            goto LABEL_96;
          }
        }
      }
    }
    else
    {
      if ( v60 > (unsigned int)v61 )
      {
        LOBYTE(v61) = 1;
        goto LABEL_96;
      }
      if ( (__int64 *)v7 == &Ipv6Global )
      {
        v102 = *(_QWORD *)(a1 + 208);
        if ( v102 )
        {
          if ( (*(_BYTE *)(v102 + 40) & 0x10) != 0 )
          {
            LOBYTE(v61) = 1;
            goto LABEL_96;
          }
        }
      }
    }
    LOBYTE(v61) = *(_WORD *)(a1 + 50) != (_WORD)v14 || *(_WORD *)(a1 + 48) != (_WORD)v14;
LABEL_96:
    IppQueryUso(*(_QWORD *)(a1 + 216), v61, *(_DWORD *)(v4 + 320) & 0xFFFFF, v121);
    result = (unsigned int)v121[3];
    v118 = v121[3];
    if ( !v121[3] )
    {
      v103 = *(_DWORD *)(v4 + 320);
      a2 = (v103 >> 20) & 0x3FF;
      result = (unsigned int)v121[1];
      v104 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 24LL) - a2) - 8LL;
      if ( v104 <= (unsigned int)v121[1] )
      {
        if ( LOBYTE(v121[2]) == (_BYTE)v14
          && (v106 = v103 & 0xFFFFF, v104 > v106)
          && (a2 = v104 % v106, result = v104 - v104 % v106, v104 >= v104 % v106) )
        {
          v118 = 9;
        }
        else
        {
          result = (unsigned int)v121[0];
          if ( v104 >= (unsigned int)v121[0] )
          {
            v118 = v14;
            v111 = 1;
            goto LABEL_98;
          }
          v118 = 8;
        }
      }
      else
      {
        v118 = 7;
      }
    }
    v111 = v14;
LABEL_98:
    v15 = v14;
    LODWORD(v3) = v14;
  }
  if ( !v11 )
    goto LABEL_9;
  v34 = *(_QWORD *)(a1 + 216);
  *(_BYTE *)(a1 + 89) |= 2u;
  v35 = *(_DWORD *)(a1 + 32);
  memset(v125, 0, 28);
  v36 = *(_QWORD *)(a1 + 8);
  v124 = 0;
  LOBYTE(v3) = *(_DWORD *)v34 == 1634496585;
  *(_QWORD *)v109 = *(_QWORD *)(v34 + 8);
  result = IpSecGetSessionInformation(v36, a1, v35, (_DWORD)v3);
  v20 = result;
  if ( (_DWORD)result != 259 )
  {
    if ( (int)result < 0 )
    {
      LODWORD(result) = HIDWORD(KeGetPcr()[1].LockArray);
      v46 = 262;
      v47 = -536854184;
      ++*(_DWORD *)(192 * result + *(_QWORD *)(v7 + 20264) + 180);
      goto LABEL_70;
    }
    v15 = (unsigned int)v120;
    v70 = 0;
    v119 = (unsigned int)v120;
    if ( (unsigned int)v120 < 8 )
    {
      LODWORD(v3) = 0;
    }
    else
    {
      v71 = 0;
      v72 = 0;
      v73 = 0;
      v74 = 0;
      do
      {
        v75 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(DataOffsetDelta[2 * v70]),
                _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v70 + 1)]));
        v76 = (unsigned int)(v70 + 6);
        v77 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v70 + 2)]),
                _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v70 + 3)]));
        a2 = (unsigned int)(v70 + 5);
        v78 = _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v70 + 7)]);
        result = (unsigned int)(v70 + 4);
        v70 = (unsigned int)(v70 + 8);
        v79 = _mm_unpacklo_epi64(v75, v77);
        v72 = _mm_add_epi32(v72, v79);
        v71 = _mm_add_epi32(v71, v79);
        v80 = _mm_unpacklo_epi64(
                _mm_unpacklo_epi32(
                  _mm_cvtsi32_si128(DataOffsetDelta[2 * result]),
                  _mm_cvtsi32_si128(DataOffsetDelta[2 * a2])),
                _mm_unpacklo_epi32(_mm_cvtsi32_si128(DataOffsetDelta[2 * v76]), v78));
        v73 = _mm_add_epi32(v73, v80);
        v74 = _mm_add_epi32(v74, v80);
      }
      while ( (unsigned int)v70 < ((unsigned int)v120 & 0xFFFFFFF8) );
      v81 = _mm_add_epi32(v74, v71);
      v82 = _mm_add_epi32(v73, v72);
      v83 = _mm_add_epi32(v81, _mm_srli_si128(v81, 8));
      v84 = _mm_add_epi32(v82, _mm_srli_si128(v82, 8));
      LODWORD(v3) = _mm_cvtsi128_si32(_mm_add_epi32(v83, _mm_srli_si128(v83, 4)));
      v14 = _mm_cvtsi128_si32(_mm_add_epi32(v84, _mm_srli_si128(v84, 4)));
      v114 = v14;
    }
    if ( (unsigned int)v70 < (unsigned int)v120 )
    {
      do
      {
        v85 = DataOffsetDelta[2 * v70];
        v14 += v85;
        LODWORD(v3) = v85 + (_DWORD)v3;
        v70 = (unsigned int)(v70 + 1);
      }
      while ( (unsigned int)v70 < (unsigned int)v120 );
      v114 = v14;
    }
    *(_DWORD *)(a1 + 56) = (_DWORD)v3;
LABEL_9:
    LODWORD(result) = HIDWORD(KeGetPcr()[1].LockArray);
    *(_QWORD *)(*(_QWORD *)(v7 + 20264) + 192 * result + 32) += SegmentationOffloadPacketCount;
    if ( (*(_BYTE *)(a1 + 184) & 2) != 0 )
    {
      v16 = *(_DWORD *)(a1 + 44);
      goto LABEL_12;
    }
    a2 = *(unsigned __int16 *)(v7 + 40);
    if ( (int *)v7 == &Ipv4Global )
    {
      v16 = a2 + ((*(unsigned __int16 *)(a1 + 50) + *(unsigned __int16 *)(a1 + 48) + 3) & 0xFFFFFFFC);
LABEL_12:
      v17 = v114;
      goto LABEL_13;
    }
    if ( *(_QWORD *)(a1 + 80) )
    {
      v37 = &v126[8 * v15];
      v38 = *(unsigned __int16 *)(a1 + 50);
      ++v15;
      *v37 = 43;
      v14 += v38;
      v119 = v15;
      v114 = v14;
      v37[1] = v38;
    }
    v39 = *(_QWORD *)(a1 + 8);
    v40 = *(__int64 **)(v39 + 8);
    v41 = (unsigned int)*(_QWORD *)(v39 + 160);
    if ( !(unsigned int)*(_QWORD *)(v39 + 160)
      && *(_DWORD *)(v39 + 320) == (_DWORD)v41
      && (unsigned int)(v14 + *((_DWORD *)v40 + 6)) > 0xFFFF )
    {
      if ( (unsigned int)IppGetMtuFromNextHop(*(_QWORD *)(a1 + 216), a2, v39) <= 0xFFFF )
        goto LABEL_101;
      v42 = 1;
    }
    else
    {
      v42 = 0;
    }
    v16 = a2;
    a2 = *(_QWORD *)(a1 + 72);
    if ( !a2 )
    {
      if ( !v42 )
        goto LABEL_12;
LABEL_57:
      if ( v41 && *(_DWORD *)(v39 + 320) )
      {
        v43 = v114;
      }
      else
      {
        v43 = v114;
        while ( 1 )
        {
          v40 = (__int64 *)*v40;
          if ( !v40 )
            break;
          if ( v114 + *((_DWORD *)v40 + 6) > 0xFFFF != v42 )
            goto LABEL_101;
        }
      }
      if ( a2 )
        a2 = *(unsigned __int16 *)(a1 + 48);
      else
        a2 = 8;
      if ( v42 )
        *(_WORD *)(a1 + 52) += a2;
      v44 = &v126[8 * v15++];
      *v44 = 0;
      v44[1] = (unsigned __int16)a2;
      v17 = (unsigned __int16)a2 + v43;
      v119 = v15;
LABEL_13:
      v18 = v16 + v17;
      *(_WORD *)(a1 + 60) = v16 + v17;
      v19 = v6[65];
      v20 = 0;
      if ( !v11 )
      {
        IppPreparePacketChecksum(v7, a1);
        v21 = v18 + v19;
        v112 = 0;
LABEL_15:
        v22 = *(struct _NET_BUFFER **)(*(_QWORD *)(a1 + 8) + 8LL);
        while ( 2 )
        {
          *(_QWORD *)v121 = v22;
          if ( v22 )
          {
            v23 = *(_BYTE *)(a1 + 32);
            v24 = v21;
            v110 = v23;
            if ( v11 && LODWORD(v125[0]) )
            {
              IppTruncateTrailer(*(_QWORD *)(a1 + 8), v22, &v124);
              v24 = v21;
            }
            v25 = 0;
            while ( 1 )
            {
              BufferSize[0] = v25;
              if ( (unsigned int)v25 >= v119 )
                break;
              v65 = DataOffsetDelta[2 * v25];
              v66 = v24 - v65;
              v120 = (int *)&v126[8 * v25];
              CurrentMdlOffset = v22->CurrentMdlOffset;
              v115 = v66;
              if ( CurrentMdlOffset < v65 )
              {
                v20 = NdisRetreatNetBufferDataStart(v22, v65, v66, NetioAllocateMdl);
                if ( v20 < 0 )
                {
                  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
                    McTemplateK0z_EtwWriteTransfer(
                      &MICROSOFT_TCPIP_PROVIDER_Context,
                      TCPIP_MEMORY_FAILURES,
                      v86,
                      L"retreat extension header (IPNG)");
LABEL_69:
                  v46 = 264;
                  v47 = -536853950;
                  goto LABEL_70;
                }
                v23 = v110;
              }
              else
              {
                v22->DataOffset -= v65;
                v22->DataLength += v65;
                v22->CurrentMdlOffset = CurrentMdlOffset - v65;
              }
              v68 = *v120;
              LODWORD(v120) = v68;
              if ( (_DWORD)v68 == 17 )
                v69 = ((__int64 (__fastcall *)(__int64, __int64, struct _NET_BUFFER *, _QWORD, __int128 *, _QWORD))off_1402156D8)(
                        a1,
                        v7,
                        v22,
                        v23,
                        &v124,
                        *(_QWORD *)v109);
              else
                v69 = (*(__int64 (__fastcall **)(__int64, __int64, struct _NET_BUFFER *, _QWORD, __int128 *, ULONG *))(v7 + 72 * v68 + 544))(
                        a1,
                        v7,
                        v22,
                        v23,
                        &v124,
                        *(ULONG **)v109);
              v20 = v69;
              if ( v69 < 0 )
                goto LABEL_69;
              v23 = (unsigned __int8)v120;
              v24 = v115;
              v25 = BufferSize[0] + 1;
              v110 = (unsigned __int8)v120;
            }
            v26 = v123[65];
            if ( Src )
            {
              *(_QWORD *)BufferSize = 0;
              v33 = IppEnsureContiguousHeaders(
                      (__int64 *)v7,
                      a1,
                      (PNET_BUFFER *)v121,
                      v16,
                      0,
                      v26,
                      (char **)BufferSize,
                      (char **)&Src);
              v28 = *(struct _NET_BUFFER ***)v121;
              v20 = v33;
              if ( v33 >= 0 )
              {
                memmove(*(void **)BufferSize, Src, v16);
                (*(void (__fastcall **)(__int64, _QWORD, struct _NET_BUFFER **))(v7 + 256))(
                  a1,
                  *(_QWORD *)BufferSize,
                  v28);
                v20 = 0;
              }
            }
            else
            {
              *(_QWORD *)BufferSize = 0;
              v27 = IppEnsureContiguousHeaders(
                      (__int64 *)v7,
                      a1,
                      (PNET_BUFFER *)v121,
                      v16,
                      8 * (unsigned int)v111,
                      v26,
                      (char **)BufferSize,
                      (char **)&Src);
              v28 = *(struct _NET_BUFFER ***)v121;
              v20 = v27;
              if ( v27 >= 0 )
              {
                if ( (*(_BYTE *)(a1 + 184) & 2) != 0 )
                {
                  v45 = *(void **)BufferSize;
                  memmove(*(void **)BufferSize, *(const void **)(a1 + 64), v16);
                  LOBYTE(v107) = v110;
                  (*(void (__fastcall **)(__int64, void *, struct _NET_BUFFER **, _QWORD, int))(v7 + 240))(
                    a1,
                    v45,
                    v28,
                    v16,
                    v107);
                  Src = v45;
                  v20 = 0;
                }
                else
                {
                  LOBYTE(v107) = v110;
                  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int))(v7 + 248))(
                          a1,
                          *(_QWORD *)BufferSize,
                          *(_QWORD *)v121,
                          v16,
                          v107);
                  v20 = 0;
                  if ( v29 < 0 )
                    v20 = v29;
                }
              }
            }
            if ( v20 < 0 )
            {
              v46 = 264;
              v47 = -536854178;
            }
            else
            {
              if ( !v11 || !BYTE8(v125[1]) || (v20 = IppAuthenticatePacket(v7, a1, v28, &v124), v20 >= 0) )
              {
                v22 = *v28;
                continue;
              }
              v46 = 262;
              v47 = -536854177;
            }
          }
          else
          {
            if ( (*(_BYTE *)(a1 + 187) & 2) == 0
              || !*(_DWORD *)(*(_QWORD *)(a1 + 8) + 320LL)
              || v111
              || (IppLogHwUsoFailure(v7, a1, v118), v20 = IppSegmentUsoPacket(v7, a1), v20 >= 0) )
            {
              v30 = *(void **)(a1 + 64);
              if ( v30 )
              {
                ExFreePoolWithTag(v30, 0);
                *(_QWORD *)(a1 + 64) = 0;
              }
              v31 = *(void **)(a1 + 72);
              if ( v31 )
              {
                ExFreePoolWithTag(v31, 0);
                *(_QWORD *)(a1 + 72) = 0;
              }
              v32 = *(void **)(a1 + 80);
              if ( v32 )
              {
                ExFreePoolWithTag(v32, 0);
                *(_QWORD *)(a1 + 80) = 0;
              }
              if ( !v113 )
                IppDispatchSendPacketHelper(v7, a1);
              return (unsigned int)v20;
            }
            v46 = 293;
            v47 = -536853938;
          }
          goto LABEL_70;
        }
      }
      v55 = *(_QWORD *)(a1 + 208);
      v56 = *(_QWORD *)(a1 + 8);
      if ( v55 )
        MtuFromNextHop = *(_DWORD *)(v55 + 112);
      else
        MtuFromNextHop = IppGetMtuFromNextHop(*(_QWORD *)(a1 + 216), a2, v17);
      v58 = IpSecNLFramedPacketIndication(
              v56,
              *(_DWORD *)(a1 + 32),
              (int)v17 - (int)v3,
              *(_DWORD *)(v7 + 24),
              *(_QWORD *)(*(_QWORD *)(a1 + 216) + 8LL) + 16LL,
              MtuFromNextHop,
              (int)v17 - (int)v3,
              v16,
              (*(_BYTE *)(a1 + 88) & 4) != 0,
              v15,
              (__int64)v126);
      v20 = v58;
      if ( (int)v58 < 0 )
      {
        LODWORD(v58) = HIDWORD(KeGetPcr()[1].LockArray);
        v46 = 262;
        v47 = -536854182;
        ++*(_DWORD *)(192 * v58 + *(_QWORD *)(v7 + 20264) + 180);
LABEL_70:
        v48 = v112;
LABEL_71:
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 140LL) = v20;
        v49 = *(void **)(a1 + 64);
        if ( v49 )
        {
          ExFreePoolWithTag(v49, 0);
          *(_QWORD *)(a1 + 64) = 0;
        }
        v50 = *(void **)(a1 + 72);
        if ( v50 )
        {
          ExFreePoolWithTag(v50, 0);
          *(_QWORD *)(a1 + 72) = 0;
        }
        v51 = *(void **)(a1 + 80);
        if ( v51 )
        {
          ExFreePoolWithTag(v51, 0);
          *(_QWORD *)(a1 + 80) = 0;
        }
        v52 = *(_QWORD *)(a1 + 8);
        if ( *(_DWORD *)(v52 + 160) || *(_DWORD *)(v52 + 320) )
        {
          i = IppGetSegmentationOffloadPacketCount(*(_QWORD *)(a1 + 8));
        }
        else
        {
          v53 = *(_QWORD **)(v52 + 8);
          for ( i = 0; v53; ++i )
            v53 = (_QWORD *)*v53;
        }
        LODWORD(v51) = HIDWORD(KeGetPcr()[1].LockArray);
        *(_DWORD *)(192LL * (_QWORD)v51 + *(_QWORD *)(v7 + 20264) + 152) += i;
        if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 || byte_140229CC0 )
        {
          PacketCount = IppGetPacketCount(*(_QWORD *)(a1 + 8));
          IppLogPacketDiscard(
            *(unsigned __int16 *)(v7 + 28),
            *(unsigned __int16 *)(a1 + 104),
            *(_QWORD *)(a1 + 264),
            *(_QWORD *)(a1 + 248),
            v46,
            PacketCount,
            0,
            v64,
            *(_QWORD *)(v63 + 8),
            v48,
            v47);
        }
        IppCompleteAndFreePacketList(a1, 0);
        return (unsigned int)v20;
      }
      v21 = v18 + v19;
      IppPreparePacketChecksum(v7, a1);
      v48 = 0;
      v112 = 0;
      if ( !LODWORD(v125[0]) )
        goto LABEL_148;
      v87 = *(int **)(a1 + 8);
      v120 = v87;
      if ( BYTE5(v124) )
      {
        SecurityContext = IpSecGetSecurityContext(v87);
        if ( !SecurityContext || !(unsigned int)IPSecIsInboundContextCryptoBypass(SecurityContext) )
        {
          if ( !v113 )
          {
            LOBYTE(v89) = 1;
            LOBYTE(v109[0]) = 0;
            LOBYTE(v108) = 1;
            v90 = NetioAllocateAndReferenceVacantNetBufferList(v120, v21, LODWORD(v125[0]), v89, v108, v109[0]);
            *(_QWORD *)v121 = v90;
            if ( !v90 )
            {
              v20 = -1073741285;
              v46 = 264;
              v47 = -536854181;
              goto LABEL_71;
            }
            IppCopyNetBufferListInfo(v90, v120);
            NetioDereferenceNetBufferList(v120, 0);
            *(_QWORD *)(a1 + 8) = *(_QWORD *)v121;
          }
          goto LABEL_148;
        }
        v87 = v120;
      }
      v91 = a1 + 208;
      v92 = *(_QWORD *)(a1 + 208);
      if ( v92 )
      {
        *(_BYTE *)(v92 + 40) |= 0x80u;
        v96 = (_DWORD *)*((_QWORD *)v87 + 1);
        v97 = v96;
        v98 = v96;
        while ( v97 )
        {
          v99 = (v98[23] & 0x80u) != 0;
          *(_QWORD *)v121 = *(_QWORD *)&v125[0];
          v48 = 0;
          v100 = v125[0];
          if ( !v99 || v98[22] < LODWORD(v125[0]) )
          {
            v101 = (_QWORD *)*((_QWORD *)v87 + 1);
            if ( v101 != v97 )
            {
              while ( 1 )
              {
                v96[6] -= v100;
                v98[22] += LODWORD(v125[0]);
                v101 = (_QWORD *)*v101;
                if ( v101 == (_QWORD *)v96 )
                  break;
                v100 = v125[0];
              }
            }
            goto LABEL_153;
          }
          v98[6] += LODWORD(v125[0]);
          v98[22] -= LODWORD(v125[0]);
          v97 = *(_QWORD **)v96;
          v96 = v97;
          v98 = v97;
        }
        goto LABEL_149;
      }
LABEL_153:
      v93 = NetioAllocateAndReferenceCloneNetBufferListEx(v87, NetioCompleteCloneNetBufferListChain, 0, 0);
      v116 = v93;
      if ( !v93 )
      {
        v20 = -1073741285;
        v46 = 264;
        v47 = -536854180;
        goto LABEL_71;
      }
      for ( j = *(_QWORD *)(v93 + 8); ; j = **(_QWORD **)v121 )
      {
        *(_QWORD *)v121 = j;
        if ( !j )
          break;
        BufferSize[0] = v125[0];
        Mdl = NetioAllocateMdl(BufferSize);
        if ( !Mdl )
        {
          NetioUpdateNetBufferListContext(v116, IppFreeCloneNetBufferListWithTrailer, *(_QWORD *)v121);
          NetioDereferenceNetBufferList(v116, 0);
          v20 = -1073741285;
          v46 = 264;
          v47 = -536854179;
          goto LABEL_71;
        }
        Mdl->ByteCount = v125[0];
        NetioExpandNetBuffer(*(_QWORD *)v121, Mdl, LODWORD(v125[0]));
        NetioUpdateNetBufferListContext(v116, IppFreeCloneNetBufferListWithTrailer, 0);
      }
      IppCopyNetBufferListInfo(v116, v120);
      NetioDereferenceNetBufferList(v120, 0);
      *(_QWORD *)(a1 + 8) = v116;
LABEL_148:
      v91 = a1 + 208;
LABEL_149:
      if ( BYTE12(v125[0]) )
      {
        if ( *(_QWORD *)v91 )
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 208LL) = *(unsigned int *)(*(_QWORD *)v91 + 12LL);
          *(_DWORD *)(a1 + 100) = *(_DWORD *)(*(_QWORD *)v91 + 124LL);
        }
        else
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 208LL) = 0;
          *(_DWORD *)(a1 + 100) = 0;
        }
      }
      goto LABEL_15;
    }
    if ( !v42 )
      goto LABEL_57;
LABEL_101:
    v20 = -1073741285;
    v46 = 263;
    v47 = -536854183;
    goto LABEL_70;
  }
  return result;
}

```

## disassembly

```asm
0x140028dc0  push    rbp
0x140028dc2  push    rbx
0x140028dc3  push    rsi
0x140028dc4  push    rdi
0x140028dc5  push    r12
0x140028dc7  push    r13
0x140028dc9  push    r14
0x140028dcb  push    r15
0x140028dcd  lea     rbp, [rsp-38h]
0x140028dd2  sub     rsp, 138h
0x140028dd9  mov     rax, cs:__security_cookie
0x140028de0  xor     rax, rsp
0x140028de3  mov     [rbp+70h+var_68], rax
0x140028de7  mov     rax, [rcx+0D8h]
0x140028dee  xor     r9d, r9d
0x140028df1  mov     rdi, [rcx+8]
0x140028df5  mov     rbx, rcx
0x140028df8  mov     [rsp+170h+var_108], dl
0x140028dfc  mov     r13, [rax+8]
0x140028e00  mov     [rbp+70h+var_C8], r13
0x140028e04  mov     rax, [r13+0]
0x140028e08  mov     r14, [rax+28h]
0x140028e0c  cmp     [rdi+0A0h], r9d
0x140028e13  jnz     loc_14002952C
0x140028e19  cmp     [rdi+140h], r9d
0x140028e20  jnz     loc_14002952C
0x140028e26  mov     rax, [rdi+8]
0x140028e2a  mov     esi, r9d
0x140028e2d  test    rax, rax
0x140028e30  jz      short loc_140028E3C
0x140028e32  mov     rax, [rax]
0x140028e35  inc     esi
0x140028e37  test    rax, rax
0x140028e3a  jnz     short loc_140028E32
0x140028e3c  mov     r12d, [rdi+88h]
0x140028e43  mov     ecx, [rbx+20h]
0x140028e46  and     r12d, 400000h
0x140028e4d  mov     [rbp+70h+Src], r9
0x140028e51  cmp     ecx, 6
0x140028e54  jnz     loc_1400290EF
0x140028e5a  mov     [rsp+170h+var_10C], 5
0x140028e62  xorps   xmm0, xmm0
0x140028e65  mov     [rbp+70h+var_F0], r9d
0x140028e69  xor     eax, eax
0x140028e6b  mov     dword ptr [rsp+170h+var_100], r9d
0x140028e70  test    byte ptr [rbx+0BBh], 2
0x140028e77  mov     r15d, r9d
0x140028e7a  movups  [rbp+70h+var_B0], xmm0
0x140028e7e  mov     r10d, r9d
0x140028e81  mov     [rbp+70h+var_EC], r9d
0x140028e85  movups  [rbp+70h+var_B0+0Ch], xmm0
0x140028e89  mov     dword ptr [rbp+70h+var_E8], r9d
0x140028e8d  movups  [rbp+70h+var_C0], xmm0
0x140028e91  mov     [rsp+170h+var_10F], al
0x140028e95  jnz     loc_1400294B3
0x140028e9b  test    r12d, r12d
0x140028e9e  jnz     loc_140029178
0x140028ea4  mov     eax, gs:1A4h
0x140028eac  lea     rcx, [rax+rax*2]
0x140028eb0  mov     eax, esi
0x140028eb2  shl     rcx, 6
0x140028eb6  add     rcx, [r14+4F28h]
0x140028ebd  add     [rcx+20h], rax
0x140028ec1  test    byte ptr [rbx+0B8h], 2
0x140028ec8  jnz     loc_1400291E7
0x140028ece  movzx   edx, word ptr [r14+28h]
0x140028ed3  lea     rax, Ipv4Global
0x140028eda  cmp     r14, rax
0x140028edd  jnz     loc_1400291F0
0x140028ee3  movzx   r15d, word ptr [rbx+30h]
0x140028ee8  movzx   ecx, word ptr [rbx+32h]
0x140028eec  add     r15d, 3
0x140028ef0  add     r15d, ecx
0x140028ef3  and     r15d, 0FFFFFFFCh
0x140028ef7  add     r15d, edx
0x140028efa  mov     r8d, dword ptr [rsp+170h+var_100]
0x140028eff  lea     esi, [r15+r8]
0x140028f03  mov     [rbx+3Ch], si
0x140028f07  movzx   r13d, word ptr [r13+82h]
0x140028f0f  xor     edi, edi
0x140028f11  test    r12d, r12d
0x140028f14  jnz     loc_1400293C2
0x140028f1a  mov     rdx, rbx
0x140028f1d  mov     rcx, r14
0x140028f20  call    IppPreparePacketChecksum
0x140028f25  movzx   eax, si
0x140028f28  add     r13d, eax
0x140028f2b  mov     [rsp+170h+var_10C], edi
0x140028f2f  mov     rax, [rbx+8]
0x140028f33  mov     rsi, [rax+8]
0x140028f37  mov     qword ptr [rbp+70h+var_E0], rsi
0x140028f3b  test    rsi, rsi
0x140028f3e  jz      loc_140029016
0x140028f44  movzx   edi, byte ptr [rbx+20h]
0x140028f48  mov     ecx, r13d
0x140028f4b  mov     [rsp+170h+var_110], dil
0x140028f50  test    r12d, r12d
0x140028f53  jnz     loc_14002968D
0x140028f59  xor     eax, eax
0x140028f5b  mov     [rsp+170h+BufferSize], eax
0x140028f5f  cmp     eax, [rbp+70h+var_EC]
0x140028f62  jb      loc_1400295EF
0x140028f68  cmp     [rbp+70h+Src], 0
0x140028f6d  lea     r8, [rbp+70h+var_E0]; int
0x140028f71  mov     rax, [rbp+70h+var_C8]
0x140028f75  mov     r9d, r15d; int
0x140028f78  movzx   ecx, word ptr [rax+82h]
0x140028f7f  jnz     loc_14002910E
0x140028f85  movzx   eax, [rsp+170h+var_10F]
0x140028f8a  lea     rdx, [rbp+70h+Src]
0x140028f8e  mov     [rsp+170h+var_138], rdx; __int64
0x140028f93  lea     rdx, [rsp+170h+BufferSize]
0x140028f98  mov     [rsp+170h+var_140], rdx; __int64
0x140028f9d  mov     rdx, rbx; int
0x140028fa0  mov     [rsp+170h+var_148], ecx; DataOffsetDelta
0x140028fa4  mov     rcx, r14; int
0x140028fa7  shl     eax, 3
0x140028faa  mov     qword ptr [rsp+170h+BufferSize], 0
0x140028fb3  mov     [rsp+170h+var_150], eax; int
0x140028fb7  call    IppEnsureContiguousHeaders
0x140028fbc  mov     rsi, qword ptr [rbp+70h+var_E0]
0x140028fc0  mov     edi, eax
0x140028fc2  test    eax, eax
0x140028fc4  js      short loc_140028FFD
0x140028fc6  test    byte ptr [rbx+0B8h], 2
0x140028fcd  jnz     loc_1400292C4
0x140028fd3  movzx   ecx, [rsp+170h+var_110]
0x140028fd8  mov     r9d, r15d
0x140028fdb  mov     rax, [r14+0F8h]
0x140028fe2  mov     r8, rsi
0x140028fe5  mov     rdx, qword ptr [rsp+170h+BufferSize]
0x140028fea  mov     byte ptr [rsp+170h+var_150], cl
0x140028fee  mov     rcx, rbx
0x140028ff1  call    _guard_dispatch_icall
0x140028ff6  xor     edi, edi
0x140028ff8  test    eax, eax
0x140028ffa  cmovs   edi, eax
0x140028ffd  test    edi, edi
0x140028fff  js      loc_140029304
0x140029005  test    r12d, r12d
0x140029008  jnz     loc_140029800
0x14002900e  mov     rsi, [rsi]
0x140029011  jmp     loc_140028F37
0x140029016  test    byte ptr [rbx+0BBh], 2
0x14002901d  jnz     loc_140029462
0x140029023  mov     rcx, [rbx+40h]; P
0x140029027  test    rcx, rcx
0x14002902a  jz      loc_14002967C
0x140029030  xor     edx, edx; Tag
0x140029032  call    cs:__imp_ExFreePoolWithTag
0x140029039  nop     dword ptr [rax+rax+00h]
0x14002903e  xor     esi, esi
0x140029040  mov     [rbx+40h], rsi
0x140029044  mov     rcx, [rbx+48h]; P
0x140029048  test    rcx, rcx
0x14002904b  jz      short loc_14002905F
0x14002904d  xor     edx, edx; Tag
0x14002904f  call    cs:__imp_ExFreePoolWithTag
0x140029056  nop     dword ptr [rax+rax+00h]
0x14002905b  mov     [rbx+48h], rsi
0x14002905f  mov     rcx, [rbx+50h]; P
0x140029063  test    rcx, rcx
0x140029066  jnz     loc_140029C7B
0x14002906c  cmp     [rsp+170h+var_108], 0
0x140029071  jnz     short loc_1400290CC
0x140029073  mov     rdx, rbx; int
0x140029076  mov     rcx, r14; int
0x140029079  call    IppDispatchSendPacketHelper
0x14002907e  jmp     short loc_1400290CC
0x140029080  mov     ecx, gs:1A4h
0x140029088  lea     rdx, [rcx+rcx*2]
0x14002908c  mov     rcx, [r14+4F28h]
0x140029093  shl     rdx, 6
0x140029097  mov     eax, [rdx+rcx+98h]
0x14002909e  add     eax, r9d
0x1400290a1  mov     [rdx+rcx+98h], eax
0x1400290a8  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 0
0x1400290af  jl      loc_14002957D
0x1400290b5  cmp     cs:byte_140229CC0, 0
0x1400290bc  jnz     loc_14002957D
0x1400290c2  xor     edx, edx
0x1400290c4  mov     rcx, rbx
0x1400290c7  call    IppCompleteAndFreePacketList
0x1400290cc  mov     eax, edi
0x1400290ce  mov     rcx, [rbp+70h+var_68]
0x1400290d2  xor     rcx, rsp; StackCookie
0x1400290d5  call    __security_check_cookie
0x1400290da  add     rsp, 138h
0x1400290e1  pop     r15
0x1400290e3  pop     r14
0x1400290e5  pop     r13
0x1400290e7  pop     r12
0x1400290e9  pop     rdi
0x1400290ea  pop     rsi
0x1400290eb  pop     rbx
0x1400290ec  pop     rbp
0x1400290ed  retn
0x1400290ef  sub     ecx, 1
0x1400290f2  jz      loc_1400295E2
0x1400290f8  sub     ecx, 10h
0x1400290fb  jnz     loc_1400295D9
0x140029101  mov     [rsp+170h+var_10C], 6
0x140029109  jmp     loc_140028E62
0x14002910e  xor     edx, edx
0x140029110  lea     rax, [rbp+70h+Src]
0x140029114  mov     [rsp+170h+var_138], rax; __int64
0x140029119  lea     rax, [rsp+170h+BufferSize]
0x14002911e  mov     [rsp+170h+var_140], rax; __int64
0x140029123  mov     [rsp+170h+var_148], ecx; DataOffsetDelta
0x140029127  mov     rcx, r14; int
0x14002912a  mov     [rsp+170h+var_150], edx; int
0x14002912e  mov     qword ptr [rsp+170h+BufferSize], rdx
0x140029133  mov     rdx, rbx; int
0x140029136  call    IppEnsureContiguousHeaders
0x14002913b  mov     rsi, qword ptr [rbp+70h+var_E0]
0x14002913f  mov     edi, eax
0x140029141  test    eax, eax
0x140029143  js      loc_140028FFD
0x140029149  mov     rdx, [rbp+70h+Src]; Src
0x14002914d  mov     rcx, qword ptr [rsp+170h+BufferSize]; void *
0x140029152  mov     r8d, r15d; Size
0x140029155  call    memmove
0x14002915a  mov     rax, [r14+100h]
0x140029161  mov     r8, rsi
0x140029164  mov     rdx, qword ptr [rsp+170h+BufferSize]
0x140029169  mov     rcx, rbx
0x14002916c  call    _guard_dispatch_icall
0x140029171  xor     edi, edi
0x140029173  jmp     loc_140028FFD
0x140029178  mov     rax, [rbx+0D8h]
0x14002917f  lea     rcx, [rbp+70h+var_90]
0x140029183  or      byte ptr [rbx+59h], 2
0x140029187  xorps   xmm0, xmm0
0x14002918a  mov     r8d, [rbx+20h]
0x14002918e  mov     rdx, rbx
0x140029191  mov     [rsp+170h+var_120], rcx
0x140029196  lea     rcx, [rbp+70h+var_E8]
0x14002919a  mov     [rsp+170h+var_128], rcx
0x14002919f  lea     rcx, [rbp+70h+var_C0]
0x1400291a3  movups  [rbp+70h+var_B0], xmm0
0x1400291a7  mov     [rsp+170h+var_130], rcx
0x1400291ac  mov     rcx, [rbx+8]
0x1400291b0  movups  [rbp+70h+var_C0], xmm0
0x1400291b4  mov     [rsp+170h+var_138], rax
0x1400291b9  movups  [rbp+70h+var_B0+0Ch], xmm0
0x1400291bd  cmp     dword ptr [rax], 616C7049h
0x1400291c3  mov     rax, [rax+8]
0x1400291c7  setz    r9b
0x1400291cb  mov     qword ptr [rsp+170h+var_148], rax
0x1400291d0  call    IpSecGetSessionInformation
0x1400291d5  mov     edi, eax
0x1400291d7  cmp     eax, 103h
0x1400291dc  jnz     loc_1400296BB
0x1400291e2  jmp     loc_1400290CE
0x1400291e7  mov     r15d, [rbx+2Ch]
0x1400291eb  jmp     loc_140028EFA
0x1400291f0  cmp     qword ptr [rbx+50h], 0
0x1400291f5  jz      short loc_14002921E
0x1400291f7  mov     eax, r10d
0x1400291fa  lea     rcx, [rbp+70h+var_90]
0x1400291fe  lea     rcx, [rcx+rax*8]
0x140029202  movzx   eax, word ptr [rbx+32h]
0x140029206  inc     r10d
0x140029209  mov     dword ptr [rcx], 2Bh ; '+'
0x14002920f  add     r15d, eax
0x140029212  mov     [rbp+70h+var_EC], r10d
0x140029216  mov     dword ptr [rsp+170h+var_100], r15d
0x14002921b  mov     [rcx+4], eax
0x14002921e  mov     r8, [rbx+8]
0x140029222  mov     eax, 0FFFFFFFFh
0x140029227  mov     r11, [r8+0A0h]
0x14002922e  mov     rsi, [r8+8]
0x140029232  and     r11, rax
0x140029235  jnz     short loc_140029252
0x140029237  cmp     [r8+140h], r11d
0x14002923e  jnz     short loc_140029252
0x140029240  mov     ecx, [rsi+18h]
0x140029243  add     ecx, r15d
0x140029246  cmp     ecx, 0FFFFh
0x14002924c  ja      loc_140029837
0x140029252  xor     dil, dil
0x140029255  mov     r15d, edx
0x140029258  mov     rdx, [rbx+48h]
0x14002925c  test    rdx, rdx
0x14002925f  jnz     loc_14002953B
0x140029265  test    dil, dil
0x140029268  jz      loc_140028EFA
0x14002926e  test    r11, r11
0x140029271  jnz     loc_14002988B
0x140029277  mov     r8d, dword ptr [rsp+170h+var_100]
0x14002927c  mov     rsi, [rsi]
0x14002927f  test    rsi, rsi
0x140029282  jnz     loc_1400298D2
0x140029288  test    rdx, rdx
0x14002928b  jz      loc_140029C2E
0x140029291  movzx   edx, word ptr [rbx+30h]
0x140029295  test    dil, dil
0x140029298  jz      short loc_14002929E
0x14002929a  add     [rbx+34h], dx
0x14002929e  mov     eax, r10d
  ... truncated ...
```
