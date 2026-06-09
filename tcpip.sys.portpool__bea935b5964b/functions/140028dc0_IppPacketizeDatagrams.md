# IppPacketizeDatagrams

- ea: `0x140028dc0`
- end: `0x140029c92`
- name: `IppPacketizeDatagrams`
- size: `3794`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
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
  unsigned __int64 v3; // r9
  __int64 v4; // rdi
  unsigned __int16 *v6; // r13
  __int64 v7; // r14
  _QWORD *v8; // rax
  unsigned int SegmentationOffloadPacketCount; // esi
  __int64 v10; // rcx
  int v11; // r12d
  __int64 result; // rax
  bool v13; // zf
  unsigned int v14; // r15d
  unsigned int v15; // r10d
  unsigned int v16; // r15d
  __int64 v17; // r8
  unsigned __int16 v18; // si
  int v19; // r13d
  int v20; // edi
  unsigned int v21; // r13d
  struct _NET_BUFFER *v22; // rsi
  unsigned __int8 v23; // di
  unsigned int v24; // ecx
  __int64 v25; // rax
  ULONG v26; // ecx
  int v27; // eax
  __int64 v28; // r8
  struct _NET_BUFFER **v29; // rsi
  int v30; // eax
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  int v35; // eax
  __int64 v36; // rax
  int v37; // r8d
  __int64 v38; // rcx
  _DWORD *v39; // rcx
  int v40; // eax
  __int64 *v41; // rsi
  __int64 v42; // r11
  char v43; // di
  _DWORD *v44; // rcx
  void *v45; // rdi
  int v46; // r15d
  int v47; // r12d
  int v48; // esi
  void *v49; // rcx
  void *v50; // rcx
  __int64 v51; // rdx
  _QWORD *v52; // rax
  int i; // r9d
  __int64 v54; // rax
  __int64 v55; // r11
  int MtuFromNextHop; // edi
  __int64 v57; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v59; // ecx
  __int64 v60; // rdx
  int PacketCount; // eax
  __int64 v62; // r9
  __int64 v63; // r10
  ULONG v64; // edx
  ULONG v65; // ecx
  ULONG CurrentMdlOffset; // eax
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // r11
  __m128i v70; // xmm7
  __m128i v71; // xmm4
  __m128i v72; // xmm6
  __m128i v73; // xmm5
  __m128i v74; // xmm3
  __int64 v75; // r8
  __m128i v76; // xmm2
  __m128i v77; // xmm1
  __m128i v78; // xmm3
  __m128i v79; // xmm3
  __m128i v80; // xmm5
  __m128i v81; // xmm6
  __m128i v82; // xmm5
  __m128i v83; // xmm6
  int v84; // ecx
  int *v85; // r10
  __int64 SecurityContext; // rax
  __int64 v87; // r9
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 j; // rax
  PMDL Mdl; // rax
  _DWORD *v94; // r9
  _QWORD *v95; // rcx
  _DWORD *v96; // r11
  bool v97; // sf
  int v98; // eax
  _QWORD *v99; // rdx
  __int64 v100; // rax
  unsigned int v101; // r8d
  unsigned __int64 v102; // rcx
  __int64 v103; // rax
  unsigned __int64 v104; // r8
  int v105; // [rsp+20h] [rbp-E0h]
  int v106; // [rsp+20h] [rbp-E0h]
  ULONG v107[2]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v108; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v109; // [rsp+61h] [rbp-9Fh]
  int v110; // [rsp+64h] [rbp-9Ch]
  char v111; // [rsp+68h] [rbp-98h]
  unsigned int v112; // [rsp+70h] [rbp-90h]
  ULONG v113; // [rsp+70h] [rbp-90h]
  __int64 v114; // [rsp+70h] [rbp-90h]
  ULONG BufferSize[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v116; // [rsp+80h] [rbp-80h]
  unsigned int v117; // [rsp+84h] [rbp-7Ch]
  int *v118; // [rsp+88h] [rbp-78h]
  int v119[4]; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v121; // [rsp+A8h] [rbp-58h]
  __int128 v122; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v123[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v124[4]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD DataOffsetDelta[9]; // [rsp+E4h] [rbp-1Ch]

  v3 = 0;
  v4 = *(_QWORD *)(a1 + 8);
  v111 = a2;
  v6 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 216) + 8LL);
  v121 = v6;
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
  Src = (void *)v3;
  if ( (_DWORD)v10 != 6 )
  {
    v10 = (unsigned int)(v10 - 1);
    if ( (_DWORD)v10 )
    {
      v10 = (unsigned int)(v10 - 16);
      if ( !(_DWORD)v10 )
      {
        v110 = 6;
        goto LABEL_7;
      }
      if ( (_DWORD)v10 != 41 )
      {
        v110 = v3;
        goto LABEL_7;
      }
    }
    v110 = 8;
    goto LABEL_7;
  }
  v110 = 5;
LABEL_7:
  v116 = v3;
  HIDWORD(result) = 0;
  v112 = v3;
  v13 = (*(_BYTE *)(a1 + 187) & 2) == 0;
  v14 = v3;
  memset(v123, 0, 28);
  v15 = v3;
  v117 = v3;
  LODWORD(v118) = v3;
  v122 = 0;
  v109 = 0;
  if ( !v13 && *(_DWORD *)(v4 + 320) )
  {
    *(_OWORD *)v119 = 0;
    if ( (Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2512_KCSAN_Fix__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2512_KCSAN_Fix__private_IsEnabledDeviceUsageNoInline(
                                       v10,
                                       a2,
                                       a3);
    v59 = *(_DWORD *)(a1 + 44);
    v60 = *(unsigned __int16 *)(v7 + 40);
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( v59 > (unsigned int)v60 )
      {
        LOBYTE(v60) = 1;
        goto LABEL_96;
      }
      if ( (__int64 *)v7 == &Ipv6Global )
      {
        v103 = *(_QWORD *)(a1 + 208);
        if ( v103 )
        {
          if ( (*(_DWORD *)(v103 + 40) & 0x10) != 0 )
          {
            LOBYTE(v60) = 1;
            goto LABEL_96;
          }
        }
      }
    }
    else
    {
      if ( v59 > (unsigned int)v60 )
      {
        LOBYTE(v60) = 1;
        goto LABEL_96;
      }
      if ( (__int64 *)v7 == &Ipv6Global )
      {
        v100 = *(_QWORD *)(a1 + 208);
        if ( v100 )
        {
          if ( (*(_BYTE *)(v100 + 40) & 0x10) != 0 )
          {
            LOBYTE(v60) = 1;
            goto LABEL_96;
          }
        }
      }
    }
    LOBYTE(v60) = *(_WORD *)(a1 + 50) != (_WORD)v14 || *(_WORD *)(a1 + 48) != (_WORD)v14;
LABEL_96:
    IppQueryUso(*(_QWORD *)(a1 + 216), v60, *(_DWORD *)(v4 + 320) & 0xFFFFF, v119);
    result = (unsigned int)v119[3];
    v116 = v119[3];
    if ( !v119[3] )
    {
      v101 = *(_DWORD *)(v4 + 320);
      a2 = (v101 >> 20) & 0x3FF;
      result = (unsigned int)v119[1];
      v102 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 24LL) - a2) - 8LL;
      if ( v102 <= (unsigned int)v119[1] )
      {
        if ( LOBYTE(v119[2]) == (_BYTE)v14
          && (v104 = v101 & 0xFFFFF, v102 > v104)
          && (a2 = v102 % v104, result = v102 - v102 % v104, v102 >= v102 % v104) )
        {
          v116 = 9;
        }
        else
        {
          result = (unsigned int)v119[0];
          if ( v102 >= (unsigned int)v119[0] )
          {
            v116 = v14;
            v109 = 1;
            goto LABEL_98;
          }
          v116 = 8;
        }
      }
      else
      {
        v116 = 7;
      }
    }
    v109 = v14;
LABEL_98:
    v15 = v14;
    v3 = v14;
  }
  if ( !v11 )
    goto LABEL_9;
  v36 = *(_QWORD *)(a1 + 216);
  *(_BYTE *)(a1 + 89) |= 2u;
  v37 = *(_DWORD *)(a1 + 32);
  memset(v123, 0, 28);
  v38 = *(_QWORD *)(a1 + 8);
  v122 = 0;
  LOBYTE(v3) = *(_DWORD *)v36 == 1634496585;
  *(_QWORD *)v107 = *(_QWORD *)(v36 + 8);
  result = IpSecGetSessionInformation(v38, a1, v37, v3);
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
    v15 = (unsigned int)v118;
    v69 = 0;
    v117 = (unsigned int)v118;
    if ( (unsigned int)v118 < 8 )
    {
      v3 = 0;
    }
    else
    {
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v73 = 0;
      do
      {
        v74 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(DataOffsetDelta[2 * v69]),
                _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v69 + 1)]));
        v75 = (unsigned int)(v69 + 6);
        v76 = _mm_unpacklo_epi32(
                _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v69 + 2)]),
                _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v69 + 3)]));
        a2 = (unsigned int)(v69 + 5);
        v77 = _mm_cvtsi32_si128(DataOffsetDelta[2 * (unsigned int)(v69 + 7)]);
        result = (unsigned int)(v69 + 4);
        v69 = (unsigned int)(v69 + 8);
        v78 = _mm_unpacklo_epi64(v74, v76);
        v71 = _mm_add_epi32(v71, v78);
        v70 = _mm_add_epi32(v70, v78);
        v79 = _mm_unpacklo_epi64(
                _mm_unpacklo_epi32(
                  _mm_cvtsi32_si128(DataOffsetDelta[2 * result]),
                  _mm_cvtsi32_si128(DataOffsetDelta[2 * a2])),
                _mm_unpacklo_epi32(_mm_cvtsi32_si128(DataOffsetDelta[2 * v75]), v77));
        v72 = _mm_add_epi32(v72, v79);
        v73 = _mm_add_epi32(v73, v79);
      }
      while ( (unsigned int)v69 < ((unsigned int)v118 & 0xFFFFFFF8) );
      v80 = _mm_add_epi32(v73, v70);
      v81 = _mm_add_epi32(v72, v71);
      v82 = _mm_add_epi32(v80, _mm_srli_si128(v80, 8));
      v83 = _mm_add_epi32(v81, _mm_srli_si128(v81, 8));
      v3 = (unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v82, _mm_srli_si128(v82, 4)));
      v14 = _mm_cvtsi128_si32(_mm_add_epi32(v83, _mm_srli_si128(v83, 4)));
      v112 = v14;
    }
    if ( (unsigned int)v69 < (unsigned int)v118 )
    {
      do
      {
        v84 = DataOffsetDelta[2 * v69];
        v14 += v84;
        v3 = (unsigned int)(v84 + v3);
        v69 = (unsigned int)(v69 + 1);
      }
      while ( (unsigned int)v69 < (unsigned int)v118 );
      v112 = v14;
    }
    *(_DWORD *)(a1 + 56) = v3;
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
      v17 = v112;
      goto LABEL_13;
    }
    if ( *(_QWORD *)(a1 + 80) )
    {
      v39 = &v124[8 * v15];
      v40 = *(unsigned __int16 *)(a1 + 50);
      ++v15;
      *v39 = 43;
      v14 += v40;
      v117 = v15;
      v112 = v14;
      v39[1] = v40;
    }
    v28 = *(_QWORD *)(a1 + 8);
    v41 = *(__int64 **)(v28 + 8);
    v42 = (unsigned int)*(_QWORD *)(v28 + 160);
    if ( !(unsigned int)*(_QWORD *)(v28 + 160)
      && *(_DWORD *)(v28 + 320) == (_DWORD)v42
      && v14 + *((_DWORD *)v41 + 6) > 0xFFFF )
    {
      if ( (unsigned int)IppGetMtuFromNextHop(*(_QWORD *)(a1 + 216), a2, v28, v3) <= 0xFFFF )
        goto LABEL_101;
      v43 = 1;
    }
    else
    {
      v43 = 0;
    }
    v16 = a2;
    a2 = *(_QWORD *)(a1 + 72);
    if ( !a2 )
    {
      if ( !v43 )
        goto LABEL_12;
LABEL_57:
      if ( v42 && *(_DWORD *)(v28 + 320) )
      {
        LODWORD(v28) = v112;
      }
      else
      {
        v28 = v112;
        while ( 1 )
        {
          v41 = (__int64 *)*v41;
          if ( !v41 )
            break;
          if ( v112 + *((_DWORD *)v41 + 6) > 0xFFFF != v43 )
            goto LABEL_101;
        }
      }
      if ( a2 )
        a2 = *(unsigned __int16 *)(a1 + 48);
      else
        a2 = 8;
      if ( v43 )
        *(_WORD *)(a1 + 52) += a2;
      v44 = &v124[8 * v15++];
      *v44 = 0;
      v44[1] = (unsigned __int16)a2;
      v17 = (unsigned __int16)a2 + (unsigned int)v28;
      v117 = v15;
LABEL_13:
      v18 = v16 + v17;
      *(_WORD *)(a1 + 60) = v16 + v17;
      v19 = v6[65];
      v20 = 0;
      if ( !v11 )
      {
        IppPreparePacketChecksum(v7, a1);
        v21 = v18 + v19;
        v110 = 0;
LABEL_15:
        v22 = *(struct _NET_BUFFER **)(*(_QWORD *)(a1 + 8) + 8LL);
        while ( 2 )
        {
          *(_QWORD *)v119 = v22;
          if ( v22 )
          {
            v23 = *(_BYTE *)(a1 + 32);
            v24 = v21;
            v108 = v23;
            if ( v11 && LODWORD(v123[0]) )
            {
              IppTruncateTrailer(*(_QWORD *)(a1 + 8), v22, &v122);
              v24 = v21;
            }
            v25 = 0;
            while ( 1 )
            {
              BufferSize[0] = v25;
              if ( (unsigned int)v25 >= v117 )
                break;
              v64 = DataOffsetDelta[2 * v25];
              v65 = v24 - v64;
              v118 = (int *)&v124[8 * v25];
              CurrentMdlOffset = v22->CurrentMdlOffset;
              v113 = v65;
              if ( CurrentMdlOffset < v64 )
              {
                v20 = NdisRetreatNetBufferDataStart(v22, v64, v65, NetioAllocateMdl);
                if ( v20 < 0 )
                {
                  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
                    McTemplateK0z_EtwWriteTransfer(
                      &MICROSOFT_TCPIP_PROVIDER_Context,
                      TCPIP_MEMORY_FAILURES,
                      v28,
                      L"retreat extension header (IPNG)");
LABEL_69:
                  v46 = 264;
                  v47 = -536853950;
                  goto LABEL_70;
                }
                v23 = v108;
              }
              else
              {
                v22->DataOffset -= v64;
                v22->DataLength += v64;
                v22->CurrentMdlOffset = CurrentMdlOffset - v64;
              }
              v67 = *v118;
              LODWORD(v118) = v67;
              if ( (_DWORD)v67 == 17 )
                v68 = ((__int64 (__fastcall *)(__int64, __int64, struct _NET_BUFFER *, _QWORD, __int128 *, _QWORD))off_1402156D8)(
                        a1,
                        v7,
                        v22,
                        v23,
                        &v122,
                        *(_QWORD *)v107);
              else
                v68 = (*(__int64 (__fastcall **)(__int64, __int64, struct _NET_BUFFER *, _QWORD, __int128 *, ULONG *))(v7 + 72 * v67 + 544))(
                        a1,
                        v7,
                        v22,
                        v23,
                        &v122,
                        *(ULONG **)v107);
              v20 = v68;
              if ( v68 < 0 )
                goto LABEL_69;
              v23 = (unsigned __int8)v118;
              v24 = v113;
              v25 = BufferSize[0] + 1;
              v108 = (unsigned __int8)v118;
            }
            v26 = v121[65];
            if ( Src )
            {
              *(_QWORD *)BufferSize = 0;
              v35 = IppEnsureContiguousHeaders(
                      (__int64 *)v7,
                      a1,
                      (PNET_BUFFER *)v119,
                      v16,
                      0,
                      v26,
                      (char **)BufferSize,
                      (char **)&Src);
              v29 = *(struct _NET_BUFFER ***)v119;
              v20 = v35;
              if ( v35 >= 0 )
              {
                memmove(*(void **)BufferSize, Src, v16);
                (*(void (__fastcall **)(__int64, _QWORD, struct _NET_BUFFER **))(v7 + 256))(
                  a1,
                  *(_QWORD *)BufferSize,
                  v29);
                v20 = 0;
              }
            }
            else
            {
              *(_QWORD *)BufferSize = 0;
              v27 = IppEnsureContiguousHeaders(
                      (__int64 *)v7,
                      a1,
                      (PNET_BUFFER *)v119,
                      v16,
                      8 * (unsigned int)v109,
                      v26,
                      (char **)BufferSize,
                      (char **)&Src);
              v29 = *(struct _NET_BUFFER ***)v119;
              v20 = v27;
              if ( v27 >= 0 )
              {
                if ( (*(_BYTE *)(a1 + 184) & 2) != 0 )
                {
                  v45 = *(void **)BufferSize;
                  memmove(*(void **)BufferSize, *(const void **)(a1 + 64), v16);
                  LOBYTE(v105) = v108;
                  (*(void (__fastcall **)(__int64, void *, struct _NET_BUFFER **, _QWORD, int))(v7 + 240))(
                    a1,
                    v45,
                    v29,
                    v16,
                    v105);
                  Src = v45;
                  v20 = 0;
                }
                else
                {
                  LOBYTE(v105) = v108;
                  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int))(v7 + 248))(
                          a1,
                          *(_QWORD *)BufferSize,
                          *(_QWORD *)v119,
                          v16,
                          v105);
                  v20 = 0;
                  if ( v30 < 0 )
                    v20 = v30;
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
              if ( !v11 || !BYTE8(v123[1]) || (v20 = IppAuthenticatePacket(v7, a1, v29, &v122), v20 >= 0) )
              {
                v22 = *v29;
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
              || v109
              || (IppLogHwUsoFailure(v7, a1, v116), v20 = IppSegmentUsoPacket((int *)v7, a1), v20 >= 0) )
            {
              v31 = *(void **)(a1 + 64);
              if ( v31 )
              {
                ExFreePoolWithTag(v31, 0);
                *(_QWORD *)(a1 + 64) = 0;
              }
              v32 = *(void **)(a1 + 72);
              if ( v32 )
              {
                ExFreePoolWithTag(v32, 0);
                *(_QWORD *)(a1 + 72) = 0;
              }
              v33 = *(void **)(a1 + 80);
              if ( v33 )
              {
                ExFreePoolWithTag(v33, 0);
                *(_QWORD *)(a1 + 80) = 0;
              }
              if ( !v111 )
                IppDispatchSendPacketHelper(v7, a1);
              return (unsigned int)v20;
            }
            v46 = 293;
            v47 = -536853938;
          }
          goto LABEL_70;
        }
      }
      v54 = *(_QWORD *)(a1 + 208);
      v55 = *(_QWORD *)(a1 + 8);
      if ( v54 )
        MtuFromNextHop = *(_DWORD *)(v54 + 112);
      else
        MtuFromNextHop = IppGetMtuFromNextHop(*(_QWORD *)(a1 + 216), a2, v17, v3);
      v57 = IpSecNLFramedPacketIndication(
              v55,
              *(_DWORD *)(a1 + 32),
              (int)v17 - (int)v3,
              *(_DWORD *)(v7 + 24),
              *(_QWORD *)(*(_QWORD *)(a1 + 216) + 8LL) + 16LL,
              MtuFromNextHop,
              (int)v17 - (int)v3,
              v16,
              (*(_BYTE *)(a1 + 88) & 4) != 0,
              v15,
              (__int64)v124);
      v20 = v57;
      if ( (int)v57 < 0 )
      {
        LODWORD(v57) = HIDWORD(KeGetPcr()[1].LockArray);
        v46 = 262;
        v47 = -536854182;
        ++*(_DWORD *)(192 * v57 + *(_QWORD *)(v7 + 20264) + 180);
LABEL_70:
        v48 = v110;
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
        v34 = *(void **)(a1 + 80);
        if ( v34 )
        {
          ExFreePoolWithTag(v34, 0);
          *(_QWORD *)(a1 + 80) = 0;
        }
        v51 = *(_QWORD *)(a1 + 8);
        if ( *(_DWORD *)(v51 + 160) || *(_DWORD *)(v51 + 320) )
        {
          i = IppGetSegmentationOffloadPacketCount(*(_QWORD *)(a1 + 8));
        }
        else
        {
          v52 = *(_QWORD **)(v51 + 8);
          for ( i = 0; v52; ++i )
            v52 = (_QWORD *)*v52;
        }
        LODWORD(v34) = HIDWORD(KeGetPcr()[1].LockArray);
        *(_DWORD *)(192LL * (_QWORD)v34 + *(_QWORD *)(v7 + 20264) + 152) += i;
        if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 || byte_140229CC0 )
        {
          PacketCount = IppGetPacketCount(*(_QWORD *)(a1 + 8), 192LL * (_QWORD)v34, v28, *(_QWORD *)(a1 + 224));
          IppLogPacketDiscard(
            *(unsigned __int16 *)(v7 + 28),
            *(unsigned __int16 *)(a1 + 104),
            *(_QWORD *)(a1 + 264),
            *(_QWORD *)(a1 + 248),
            v46,
            PacketCount,
            0,
            v63,
            *(_QWORD *)(v62 + 8),
            v48,
            v47);
        }
        IppCompleteAndFreePacketList(a1, 0);
        return (unsigned int)v20;
      }
      v21 = v18 + v19;
      IppPreparePacketChecksum(v7, a1);
      v48 = 0;
      v110 = 0;
      if ( !LODWORD(v123[0]) )
        goto LABEL_148;
      v85 = *(int **)(a1 + 8);
      v118 = v85;
      if ( BYTE5(v122) )
      {
        SecurityContext = IpSecGetSecurityContext(v85);
        if ( !SecurityContext || !(unsigned int)IPSecIsInboundContextCryptoBypass(SecurityContext) )
        {
          if ( !v111 )
          {
            LOBYTE(v87) = 1;
            LOBYTE(v107[0]) = 0;
            LOBYTE(v106) = 1;
            v88 = NetioAllocateAndReferenceVacantNetBufferList(v118, v21, LODWORD(v123[0]), v87, v106, v107[0]);
            *(_QWORD *)v119 = v88;
            if ( !v88 )
            {
              v20 = -1073741285;
              v46 = 264;
              v47 = -536854181;
              goto LABEL_71;
            }
            IppCopyNetBufferListInfo(v88, v118);
            NetioDereferenceNetBufferList(v118, 0);
            *(_QWORD *)(a1 + 8) = *(_QWORD *)v119;
          }
          goto LABEL_148;
        }
        v85 = v118;
      }
      v89 = a1 + 208;
      v90 = *(_QWORD *)(a1 + 208);
      if ( v90 )
      {
        *(_BYTE *)(v90 + 40) |= 0x80u;
        v94 = (_DWORD *)*((_QWORD *)v85 + 1);
        v95 = v94;
        v96 = v94;
        while ( v95 )
        {
          v97 = (v96[23] & 0x80u) != 0;
          *(_QWORD *)v119 = *(_QWORD *)&v123[0];
          v48 = 0;
          v98 = v123[0];
          if ( !v97 || v96[22] < LODWORD(v123[0]) )
          {
            v99 = (_QWORD *)*((_QWORD *)v85 + 1);
            if ( v99 != v95 )
            {
              while ( 1 )
              {
                v94[6] -= v98;
                v96[22] += LODWORD(v123[0]);
                v99 = (_QWORD *)*v99;
                if ( v99 == (_QWORD *)v94 )
                  break;
                v98 = v123[0];
              }
            }
            goto LABEL_153;
          }
          v96[6] += LODWORD(v123[0]);
          v96[22] -= LODWORD(v123[0]);
          v95 = *(_QWORD **)v94;
          v94 = v95;
          v96 = v95;
        }
        goto LABEL_149;
      }
LABEL_153:
      v91 = NetioAllocateAndReferenceCloneNetBufferListEx(v85, NetioCompleteCloneNetBufferListChain, 0, 0);
      v114 = v91;
      if ( !v91 )
      {
        v20 = -1073741285;
        v46 = 264;
        v47 = -536854180;
        goto LABEL_71;
      }
      for ( j = *(_QWORD *)(v91 + 8); ; j = **(_QWORD **)v119 )
      {
        *(_QWORD *)v119 = j;
        if ( !j )
          break;
        BufferSize[0] = v123[0];
        Mdl = NetioAllocateMdl(BufferSize);
        if ( !Mdl )
        {
          NetioUpdateNetBufferListContext(v114, IppFreeCloneNetBufferListWithTrailer, *(_QWORD *)v119);
          NetioDereferenceNetBufferList(v114, 0);
          v20 = -1073741285;
          v46 = 264;
          v47 = -536854179;
          goto LABEL_71;
        }
        Mdl->ByteCount = v123[0];
        NetioExpandNetBuffer(*(_QWORD *)v119, Mdl, LODWORD(v123[0]));
        NetioUpdateNetBufferListContext(v114, IppFreeCloneNetBufferListWithTrailer, 0);
      }
      IppCopyNetBufferListInfo(v114, v118);
      NetioDereferenceNetBufferList(v118, 0);
      *(_QWORD *)(a1 + 8) = v114;
LABEL_148:
      v89 = a1 + 208;
LABEL_149:
      if ( BYTE12(v123[0]) )
      {
        if ( *(_QWORD *)v89 )
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 208LL) = *(unsigned int *)(*(_QWORD *)v89 + 12LL);
          *(_DWORD *)(a1 + 100) = *(_DWORD *)(*(_QWORD *)v89 + 124LL);
        }
        else
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 208LL) = 0;
          *(_DWORD *)(a1 + 100) = 0;
        }
      }
      goto LABEL_15;
    }
    if ( !v43 )
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
