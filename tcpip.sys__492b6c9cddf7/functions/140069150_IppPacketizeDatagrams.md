# IppPacketizeDatagrams

- ea: `0x140069150`
- end: `0x14006a022`
- name: `IppPacketizeDatagrams`
- size: `3794`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a88e0`
- `0x1400c2e20`
- `0x14018bb90`

## callees

- `0x140053e98`
- `0x14005b10c`
- `0x14006891c`
- `0x140068cdc`
- `0x140068d10`
- `0x140068d50`
- `0x140068f88`
- `0x140069110`
- `0x140069150`
- `0x14006a030`
- `0x14006a450`
- `0x14006a4d0`
- `0x14006a960`
- `0x1400845a0`
- `0x1400d1440`
- `0x1400dd720`
- `0x14011f37c`
- `0x140127b88`
- `0x14014d0bc`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf640`
- `0x1402723d0`
- `0x140276c38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400693c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400693df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ff2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a00d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400693c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400693df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400696f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069ff2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a00d`
- `NETIO!NetioAllocateMdl` at `0x140069dbf`
- `NETIO!NetioAllocateMdl` at `0x140069be6`
- `NETIO!NetioAllocateMdl` at `0x140069dbf`
- `NETIO!NetioDereferenceNetBufferList` at `0x140069d18`
- `NETIO!NetioDereferenceNetBufferList` at `0x140069ed9`
- `NETIO!NetioDereferenceNetBufferList` at `0x140069f12`
- `NETIO!NetioDereferenceNetBufferList` at `0x140069d18`
- `NETIO!NetioDereferenceNetBufferList` at `0x140069ed9`
- `NETIO!NetioDereferenceNetBufferList` at `0x140069f12`
- `NETIO!NetioCompleteCloneNetBufferListChain` at `0x140069d78`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140069ced`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140069ced`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140069e00`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140069ec6`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140069e00`
- `NETIO!NetioUpdateNetBufferListContext` at `0x140069ec6`
- `NETIO!NetioExpandNetBuffer` at `0x140069de5`
- `NETIO!NetioExpandNetBuffer` at `0x140069de5`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferListEx` at `0x140069d88`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferListEx` at `0x140069d88`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140069bf3`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140069bf3`

## string_xrefs

- `0x140069fd1`: `retreat extension header (IPNG)`

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
  __int64 v110; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v111; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v112; // [rsp+61h] [rbp-9Fh]
  int v113; // [rsp+64h] [rbp-9Ch]
  char v114; // [rsp+68h] [rbp-98h]
  unsigned int v115; // [rsp+70h] [rbp-90h]
  ULONG v116; // [rsp+70h] [rbp-90h]
  __int64 v117; // [rsp+70h] [rbp-90h]
  ULONG BufferSize[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v119; // [rsp+80h] [rbp-80h]
  unsigned int v120; // [rsp+84h] [rbp-7Ch]
  int *v121; // [rsp+88h] [rbp-78h]
  int v122[4]; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v124; // [rsp+A8h] [rbp-58h]
  __int128 v125; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v126[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v127[4]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD DataOffsetDelta[9]; // [rsp+E4h] [rbp-1Ch]

  v3 = 0;
  v4 = *(_QWORD *)(a1 + 8);
  v114 = a2;
  v6 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 216) + 8LL);
  v124 = v6;
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
        v113 = 6;
        goto LABEL_7;
      }
      if ( (_DWORD)v10 != 41 )
      {
        v113 = (int)v3;
        goto LABEL_7;
      }
    }
    v113 = 8;
    goto LABEL_7;
  }
  v113 = 5;
LABEL_7:
  v119 = (unsigned int)v3;
  HIDWORD(result) = 0;
  v115 = (unsigned int)v3;
  v13 = (*(_BYTE *)(a1 + 187) & 2) == 0;
  v14 = (int)v3;
  memset(v126, 0, 28);
  v15 = (unsigned int)v3;
  v120 = (unsigned int)v3;
  LODWORD(v121) = (_DWORD)v3;
  v125 = 0;
  v112 = 0;
  if ( !v13 && *(_DWORD *)(v4 + 320) )
  {
    *(_OWORD *)v122 = 0;
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
    IppQueryUso(*(_QWORD *)(a1 + 216), v61, *(_DWORD *)(v4 + 320) & 0xFFFFF, v122);
    result = (unsigned int)v122[3];
    v119 = v122[3];
    if ( !v122[3] )
    {
      v103 = *(_DWORD *)(v4 + 320);
      a2 = (v103 >> 20) & 0x3FF;
      result = (unsigned int)v122[1];
      v104 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 24LL) - a2) - 8LL;
      if ( v104 <= (unsigned int)v122[1] )
      {
        if ( LOBYTE(v122[2]) == (_BYTE)v14
          && (v106 = v103 & 0xFFFFF, v104 > v106)
          && (a2 = v104 % v106, result = v104 - v104 % v106, v104 >= v104 % v106) )
        {
          v119 = 9;
        }
        else
        {
          result = (unsigned int)v122[0];
          if ( v104 >= (unsigned int)v122[0] )
          {
            v119 = v14;
            v112 = 1;
            goto LABEL_98;
          }
          v119 = 8;
        }
      }
      else
      {
        v119 = 7;
      }
    }
    v112 = v14;
LABEL_98:
    v15 = v14;
    LODWORD(v3) = v14;
  }
  if ( !v11 )
    goto LABEL_9;
  v34 = *(_QWORD *)(a1 + 216);
  *(_BYTE *)(a1 + 89) |= 2u;
  v35 = *(_DWORD *)(a1 + 32);
  memset(v126, 0, 28);
  v36 = *(_QWORD *)(a1 + 8);
  v125 = 0;
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
    v15 = (unsigned int)v121;
    v70 = 0;
    v120 = (unsigned int)v121;
    if ( (unsigned int)v121 < 8 )
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
      while ( (unsigned int)v70 < ((unsigned int)v121 & 0xFFFFFFF8) );
      v81 = _mm_add_epi32(v74, v71);
      v82 = _mm_add_epi32(v73, v72);
      v83 = _mm_add_epi32(v81, _mm_srli_si128(v81, 8));
      v84 = _mm_add_epi32(v82, _mm_srli_si128(v82, 8));
      LODWORD(v3) = _mm_cvtsi128_si32(_mm_add_epi32(v83, _mm_srli_si128(v83, 4)));
      v14 = _mm_cvtsi128_si32(_mm_add_epi32(v84, _mm_srli_si128(v84, 4)));
      v115 = v14;
    }
    if ( (unsigned int)v70 < (unsigned int)v121 )
    {
      do
      {
        v85 = DataOffsetDelta[2 * v70];
        v14 += v85;
        LODWORD(v3) = v85 + (_DWORD)v3;
        v70 = (unsigned int)(v70 + 1);
      }
      while ( (unsigned int)v70 < (unsigned int)v121 );
      v115 = v14;
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
      v17 = v115;
      goto LABEL_13;
    }
    if ( *(_QWORD *)(a1 + 80) )
    {
      v37 = &v127[8 * v15];
      v38 = *(unsigned __int16 *)(a1 + 50);
      ++v15;
      *v37 = 43;
      v14 += v38;
      v120 = v15;
      v115 = v14;
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
        v43 = v115;
      }
      else
      {
        v43 = v115;
        while ( 1 )
        {
          v40 = (__int64 *)*v40;
          if ( !v40 )
            break;
          if ( v115 + *((_DWORD *)v40 + 6) > 0xFFFF != v42 )
            goto LABEL_101;
        }
      }
      if ( a2 )
        a2 = *(unsigned __int16 *)(a1 + 48);
      else
        a2 = 8;
      if ( v42 )
        *(_WORD *)(a1 + 52) += a2;
      v44 = &v127[8 * v15++];
      *v44 = 0;
      v44[1] = (unsigned __int16)a2;
      v17 = (unsigned __int16)a2 + v43;
      v120 = v15;
LABEL_13:
      v18 = v16 + v17;
      *(_WORD *)(a1 + 60) = v16 + v17;
      v19 = v6[65];
      v20 = 0;
      if ( !v11 )
      {
        IppPreparePacketChecksum(v7, a1);
        v21 = v18 + v19;
        v113 = 0;
LABEL_15:
        v22 = *(struct _NET_BUFFER **)(*(_QWORD *)(a1 + 8) + 8LL);
        while ( 2 )
        {
          *(_QWORD *)v122 = v22;
          if ( v22 )
          {
            v23 = *(_BYTE *)(a1 + 32);
            v24 = v21;
            v111 = v23;
            if ( v11 && LODWORD(v126[0]) )
            {
              IppTruncateTrailer(*(_QWORD *)(a1 + 8), v22, &v125);
              v24 = v21;
            }
            v25 = 0;
            while ( 1 )
            {
              BufferSize[0] = v25;
              if ( (unsigned int)v25 >= v120 )
                break;
              v65 = DataOffsetDelta[2 * v25];
              v66 = v24 - v65;
              v121 = (int *)&v127[8 * v25];
              CurrentMdlOffset = v22->CurrentMdlOffset;
              v116 = v66;
              if ( CurrentMdlOffset < v65 )
              {
                v20 = NdisRetreatNetBufferDataStart(v22, v65, v66, NetioAllocateMdl);
                if ( v20 < 0 )
                {
                  if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
                v23 = v111;
              }
              else
              {
                v22->DataOffset -= v65;
                v22->DataLength += v65;
                v22->CurrentMdlOffset = CurrentMdlOffset - v65;
              }
              v68 = *v121;
              LODWORD(v121) = v68;
              if ( (_DWORD)v68 == 17 )
                v69 = ((__int64 (__fastcall *)(__int64, __int64, struct _NET_BUFFER *, _QWORD, __int128 *, _QWORD))off_1402116D8)(
                        a1,
                        v7,
                        v22,
                        v23,
                        &v125,
                        *(_QWORD *)v109);
              else
                v69 = (*(__int64 (__fastcall **)(__int64, __int64, struct _NET_BUFFER *, _QWORD, __int128 *, ULONG *))(v7 + 72 * v68 + 544))(
                        a1,
                        v7,
                        v22,
                        v23,
                        &v125,
                        *(ULONG **)v109);
              v20 = v69;
              if ( v69 < 0 )
                goto LABEL_69;
              v23 = (unsigned __int8)v121;
              v24 = v116;
              v25 = BufferSize[0] + 1;
              v111 = (unsigned __int8)v121;
            }
            v26 = v124[65];
            if ( Src )
            {
              *(_QWORD *)BufferSize = 0;
              v33 = IppEnsureContiguousHeaders(
                      (__int64 *)v7,
                      a1,
                      (PNET_BUFFER *)v122,
                      v16,
                      0,
                      v26,
                      (char **)BufferSize,
                      (char **)&Src);
              v28 = *(struct _NET_BUFFER ***)v122;
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
                      (PNET_BUFFER *)v122,
                      v16,
                      8 * (unsigned int)v112,
                      v26,
                      (char **)BufferSize,
                      (char **)&Src);
              v28 = *(struct _NET_BUFFER ***)v122;
              v20 = v27;
              if ( v27 >= 0 )
              {
                if ( (*(_BYTE *)(a1 + 184) & 2) != 0 )
                {
                  v45 = *(void **)BufferSize;
                  memmove(*(void **)BufferSize, *(const void **)(a1 + 64), v16);
                  LOBYTE(v107) = v111;
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
                  LOBYTE(v107) = v111;
                  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int))(v7 + 248))(
                          a1,
                          *(_QWORD *)BufferSize,
                          *(_QWORD *)v122,
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
              if ( !v11 || !BYTE8(v126[1]) || (v20 = IppAuthenticatePacket(v7, a1, v28, &v125), v20 >= 0) )
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
              || v112
              || (IppLogHwUsoFailure(v7, a1, v119), v20 = IppSegmentUsoPacket(v7, a1), v20 >= 0) )
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
              if ( !v114 )
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
              (__int64)v127);
      v20 = v58;
      if ( (int)v58 < 0 )
      {
        LODWORD(v58) = HIDWORD(KeGetPcr()[1].LockArray);
        v46 = 262;
        v47 = -536854182;
        ++*(_DWORD *)(192 * v58 + *(_QWORD *)(v7 + 20264) + 180);
LABEL_70:
        v48 = v113;
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
        if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
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
      v113 = 0;
      if ( !LODWORD(v126[0]) )
        goto LABEL_148;
      v87 = *(int **)(a1 + 8);
      v121 = v87;
      if ( BYTE5(v125) )
      {
        SecurityContext = IpSecGetSecurityContext(v87);
        if ( !SecurityContext || !(unsigned int)IPSecIsInboundContextCryptoBypass(SecurityContext) )
        {
          if ( !v114 )
          {
            LOBYTE(v89) = 1;
            LOBYTE(v109[0]) = 0;
            LOBYTE(v108) = 1;
            v90 = NetioAllocateAndReferenceVacantNetBufferList(v121, v21, LODWORD(v126[0]), v89, v108, v109[0], v110);
            *(_QWORD *)v122 = v90;
            if ( !v90 )
            {
              v20 = -1073741285;
              v46 = 264;
              v47 = -536854181;
              goto LABEL_71;
            }
            IppCopyNetBufferListInfo(v90, v121);
            NetioDereferenceNetBufferList(v121, 0);
            *(_QWORD *)(a1 + 8) = *(_QWORD *)v122;
          }
          goto LABEL_148;
        }
        v87 = v121;
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
          *(_QWORD *)v122 = *(_QWORD *)&v126[0];
          v48 = 0;
          v100 = v126[0];
          if ( !v99 || v98[22] < LODWORD(v126[0]) )
          {
            v101 = (_QWORD *)*((_QWORD *)v87 + 1);
            if ( v101 != v97 )
            {
              while ( 1 )
              {
                v96[6] -= v100;
                v98[22] += LODWORD(v126[0]);
                v101 = (_QWORD *)*v101;
                if ( v101 == (_QWORD *)v96 )
                  break;
                v100 = v126[0];
              }
            }
            goto LABEL_153;
          }
          v98[6] += LODWORD(v126[0]);
          v98[22] -= LODWORD(v126[0]);
          v97 = *(_QWORD **)v96;
          v96 = v97;
          v98 = v97;
        }
        goto LABEL_149;
      }
LABEL_153:
      v93 = NetioAllocateAndReferenceCloneNetBufferListEx(v87, NetioCompleteCloneNetBufferListChain, 0, 0);
      v117 = v93;
      if ( !v93 )
      {
        v20 = -1073741285;
        v46 = 264;
        v47 = -536854180;
        goto LABEL_71;
      }
      for ( j = *(_QWORD *)(v93 + 8); ; j = **(_QWORD **)v122 )
      {
        *(_QWORD *)v122 = j;
        if ( !j )
          break;
        BufferSize[0] = v126[0];
        Mdl = NetioAllocateMdl(BufferSize);
        if ( !Mdl )
        {
          NetioUpdateNetBufferListContext(v117, IppFreeCloneNetBufferListWithTrailer, *(_QWORD *)v122);
          NetioDereferenceNetBufferList(v117, 0);
          v20 = -1073741285;
          v46 = 264;
          v47 = -536854179;
          goto LABEL_71;
        }
        Mdl->ByteCount = v126[0];
        NetioExpandNetBuffer(*(_QWORD *)v122, Mdl, LODWORD(v126[0]));
        NetioUpdateNetBufferListContext(v117, IppFreeCloneNetBufferListWithTrailer, 0);
      }
      IppCopyNetBufferListInfo(v117, v121);
      NetioDereferenceNetBufferList(v121, 0);
      *(_QWORD *)(a1 + 8) = v117;
LABEL_148:
      v91 = a1 + 208;
LABEL_149:
      if ( BYTE12(v126[0]) )
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
0x140069150  push    rbp
0x140069152  push    rbx
0x140069153  push    rsi
0x140069154  push    rdi
0x140069155  push    r12
0x140069157  push    r13
0x140069159  push    r14
0x14006915b  push    r15
0x14006915d  lea     rbp, [rsp-38h]
0x140069162  sub     rsp, 138h
0x140069169  mov     rax, cs:__security_cookie
0x140069170  xor     rax, rsp
0x140069173  mov     [rbp+70h+var_68], rax
0x140069177  mov     rax, [rcx+0D8h]
0x14006917e  xor     r9d, r9d
0x140069181  mov     rdi, [rcx+8]
0x140069185  mov     rbx, rcx
0x140069188  mov     [rsp+170h+var_108], dl
0x14006918c  mov     r13, [rax+8]
0x140069190  mov     [rbp+70h+var_C8], r13
0x140069194  mov     rax, [r13+0]
0x140069198  mov     r14, [rax+28h]
0x14006919c  cmp     [rdi+0A0h], r9d
0x1400691a3  jnz     loc_1400698BC
0x1400691a9  cmp     [rdi+140h], r9d
0x1400691b0  jnz     loc_1400698BC
0x1400691b6  mov     rax, [rdi+8]
0x1400691ba  mov     esi, r9d
0x1400691bd  test    rax, rax
0x1400691c0  jz      short loc_1400691CC
0x1400691c2  mov     rax, [rax]
0x1400691c5  inc     esi
0x1400691c7  test    rax, rax
0x1400691ca  jnz     short loc_1400691C2
0x1400691cc  mov     r12d, [rdi+88h]
0x1400691d3  mov     ecx, [rbx+20h]
0x1400691d6  and     r12d, 400000h
0x1400691dd  mov     [rbp+70h+Src], r9
0x1400691e1  cmp     ecx, 6
0x1400691e4  jnz     loc_14006947F
0x1400691ea  mov     [rsp+170h+var_10C], 5
0x1400691f2  xorps   xmm0, xmm0
0x1400691f5  mov     [rbp+70h+var_F0], r9d
0x1400691f9  xor     eax, eax
0x1400691fb  mov     dword ptr [rsp+170h+var_100], r9d
0x140069200  test    byte ptr [rbx+0BBh], 2
0x140069207  mov     r15d, r9d
0x14006920a  movups  [rbp+70h+var_B0], xmm0
0x14006920e  mov     r10d, r9d
0x140069211  mov     [rbp+70h+var_EC], r9d
0x140069215  movups  [rbp+70h+var_B0+0Ch], xmm0
0x140069219  mov     dword ptr [rbp+70h+var_E8], r9d
0x14006921d  movups  [rbp+70h+var_C0], xmm0
0x140069221  mov     [rsp+170h+var_10F], al
0x140069225  jnz     loc_140069843
0x14006922b  test    r12d, r12d
0x14006922e  jnz     loc_140069508
0x140069234  mov     eax, gs:1A4h
0x14006923c  lea     rcx, [rax+rax*2]
0x140069240  mov     eax, esi
0x140069242  shl     rcx, 6
0x140069246  add     rcx, [r14+4F28h]
0x14006924d  add     [rcx+20h], rax
0x140069251  test    byte ptr [rbx+0B8h], 2
0x140069258  jnz     loc_140069577
0x14006925e  movzx   edx, word ptr [r14+28h]
0x140069263  lea     rax, Ipv4Global
0x14006926a  cmp     r14, rax
0x14006926d  jnz     loc_140069580
0x140069273  movzx   r15d, word ptr [rbx+30h]
0x140069278  movzx   ecx, word ptr [rbx+32h]
0x14006927c  add     r15d, 3
0x140069280  add     r15d, ecx
0x140069283  and     r15d, 0FFFFFFFCh
0x140069287  add     r15d, edx
0x14006928a  mov     r8d, dword ptr [rsp+170h+var_100]
0x14006928f  lea     esi, [r15+r8]
0x140069293  mov     [rbx+3Ch], si
0x140069297  movzx   r13d, word ptr [r13+82h]
0x14006929f  xor     edi, edi
0x1400692a1  test    r12d, r12d
0x1400692a4  jnz     loc_140069752
0x1400692aa  mov     rdx, rbx
0x1400692ad  mov     rcx, r14
0x1400692b0  call    IppPreparePacketChecksum
0x1400692b5  movzx   eax, si
0x1400692b8  add     r13d, eax
0x1400692bb  mov     [rsp+170h+var_10C], edi
0x1400692bf  mov     rax, [rbx+8]
0x1400692c3  mov     rsi, [rax+8]
0x1400692c7  mov     qword ptr [rbp+70h+var_E0], rsi
0x1400692cb  test    rsi, rsi
0x1400692ce  jz      loc_1400693A6
0x1400692d4  movzx   edi, byte ptr [rbx+20h]
0x1400692d8  mov     ecx, r13d
0x1400692db  mov     [rsp+170h+var_110], dil
0x1400692e0  test    r12d, r12d
0x1400692e3  jnz     loc_140069A1D
0x1400692e9  xor     eax, eax
0x1400692eb  mov     [rsp+170h+BufferSize], eax
0x1400692ef  cmp     eax, [rbp+70h+var_EC]
0x1400692f2  jb      loc_14006997F
0x1400692f8  cmp     [rbp+70h+Src], 0
0x1400692fd  lea     r8, [rbp+70h+var_E0]; int
0x140069301  mov     rax, [rbp+70h+var_C8]
0x140069305  mov     r9d, r15d; int
0x140069308  movzx   ecx, word ptr [rax+82h]
0x14006930f  jnz     loc_14006949E
0x140069315  movzx   eax, [rsp+170h+var_10F]
0x14006931a  lea     rdx, [rbp+70h+Src]
0x14006931e  mov     [rsp+170h+var_138], rdx; __int64
0x140069323  lea     rdx, [rsp+170h+BufferSize]
0x140069328  mov     [rsp+170h+var_140], rdx; __int64
0x14006932d  mov     rdx, rbx; int
0x140069330  mov     [rsp+170h+var_148], ecx; DataOffsetDelta
0x140069334  mov     rcx, r14; int
0x140069337  shl     eax, 3
0x14006933a  mov     qword ptr [rsp+170h+BufferSize], 0
0x140069343  mov     [rsp+170h+var_150], eax; int
0x140069347  call    IppEnsureContiguousHeaders
0x14006934c  mov     rsi, qword ptr [rbp+70h+var_E0]
0x140069350  mov     edi, eax
0x140069352  test    eax, eax
0x140069354  js      short loc_14006938D
0x140069356  test    byte ptr [rbx+0B8h], 2
0x14006935d  jnz     loc_140069654
0x140069363  movzx   ecx, [rsp+170h+var_110]
0x140069368  mov     r9d, r15d
0x14006936b  mov     rax, [r14+0F8h]
0x140069372  mov     r8, rsi
0x140069375  mov     rdx, qword ptr [rsp+170h+BufferSize]
0x14006937a  mov     byte ptr [rsp+170h+var_150], cl
0x14006937e  mov     rcx, rbx
0x140069381  call    _guard_dispatch_icall
0x140069386  xor     edi, edi
0x140069388  test    eax, eax
0x14006938a  cmovs   edi, eax
0x14006938d  test    edi, edi
0x14006938f  js      loc_140069694
0x140069395  test    r12d, r12d
0x140069398  jnz     loc_140069B90
0x14006939e  mov     rsi, [rsi]
0x1400693a1  jmp     loc_1400692C7
0x1400693a6  test    byte ptr [rbx+0BBh], 2
0x1400693ad  jnz     loc_1400697F2
0x1400693b3  mov     rcx, [rbx+40h]; P
0x1400693b7  test    rcx, rcx
0x1400693ba  jz      loc_140069A0C
0x1400693c0  xor     edx, edx; Tag
0x1400693c2  call    cs:__imp_ExFreePoolWithTag
0x1400693c9  nop     dword ptr [rax+rax+00h]
0x1400693ce  xor     esi, esi
0x1400693d0  mov     [rbx+40h], rsi
0x1400693d4  mov     rcx, [rbx+48h]; P
0x1400693d8  test    rcx, rcx
0x1400693db  jz      short loc_1400693EF
0x1400693dd  xor     edx, edx; Tag
0x1400693df  call    cs:__imp_ExFreePoolWithTag
0x1400693e6  nop     dword ptr [rax+rax+00h]
0x1400693eb  mov     [rbx+48h], rsi
0x1400693ef  mov     rcx, [rbx+50h]; P
0x1400693f3  test    rcx, rcx
0x1400693f6  jnz     loc_14006A00B
0x1400693fc  cmp     [rsp+170h+var_108], 0
0x140069401  jnz     short loc_14006945C
0x140069403  mov     rdx, rbx
0x140069406  mov     rcx, r14
0x140069409  call    IppDispatchSendPacketHelper
0x14006940e  jmp     short loc_14006945C
0x140069410  mov     ecx, gs:1A4h
0x140069418  lea     rdx, [rcx+rcx*2]
0x14006941c  mov     rcx, [r14+4F28h]
0x140069423  shl     rdx, 6
0x140069427  mov     eax, [rdx+rcx+98h]
0x14006942e  add     eax, r9d
0x140069431  mov     [rdx+rcx+98h], eax
0x140069438  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+6, 0
0x14006943f  jl      loc_14006990D
0x140069445  cmp     cs:byte_140225C70, 0
0x14006944c  jnz     loc_14006990D
0x140069452  xor     edx, edx
0x140069454  mov     rcx, rbx
0x140069457  call    IppCompleteAndFreePacketList
0x14006945c  mov     eax, edi
0x14006945e  mov     rcx, [rbp+70h+var_68]
0x140069462  xor     rcx, rsp; StackCookie
0x140069465  call    __security_check_cookie
0x14006946a  add     rsp, 138h
0x140069471  pop     r15
0x140069473  pop     r14
0x140069475  pop     r13
0x140069477  pop     r12
0x140069479  pop     rdi
0x14006947a  pop     rsi
0x14006947b  pop     rbx
0x14006947c  pop     rbp
0x14006947d  retn
0x14006947f  sub     ecx, 1
0x140069482  jz      loc_140069972
0x140069488  sub     ecx, 10h
0x14006948b  jnz     loc_140069969
0x140069491  mov     [rsp+170h+var_10C], 6
0x140069499  jmp     loc_1400691F2
0x14006949e  xor     edx, edx
0x1400694a0  lea     rax, [rbp+70h+Src]
0x1400694a4  mov     [rsp+170h+var_138], rax; __int64
0x1400694a9  lea     rax, [rsp+170h+BufferSize]
0x1400694ae  mov     [rsp+170h+var_140], rax; __int64
0x1400694b3  mov     [rsp+170h+var_148], ecx; DataOffsetDelta
0x1400694b7  mov     rcx, r14; int
0x1400694ba  mov     [rsp+170h+var_150], edx; int
0x1400694be  mov     qword ptr [rsp+170h+BufferSize], rdx
0x1400694c3  mov     rdx, rbx; int
0x1400694c6  call    IppEnsureContiguousHeaders
0x1400694cb  mov     rsi, qword ptr [rbp+70h+var_E0]
0x1400694cf  mov     edi, eax
0x1400694d1  test    eax, eax
0x1400694d3  js      loc_14006938D
0x1400694d9  mov     rdx, [rbp+70h+Src]; Src
0x1400694dd  mov     rcx, qword ptr [rsp+170h+BufferSize]; void *
0x1400694e2  mov     r8d, r15d; Size
0x1400694e5  call    memmove
0x1400694ea  mov     rax, [r14+100h]
0x1400694f1  mov     r8, rsi
0x1400694f4  mov     rdx, qword ptr [rsp+170h+BufferSize]
0x1400694f9  mov     rcx, rbx
0x1400694fc  call    _guard_dispatch_icall
0x140069501  xor     edi, edi
0x140069503  jmp     loc_14006938D
0x140069508  mov     rax, [rbx+0D8h]
0x14006950f  lea     rcx, [rbp+70h+var_90]
0x140069513  or      byte ptr [rbx+59h], 2
0x140069517  xorps   xmm0, xmm0
0x14006951a  mov     r8d, [rbx+20h]
0x14006951e  mov     rdx, rbx
0x140069521  mov     [rsp+170h+var_120], rcx
0x140069526  lea     rcx, [rbp+70h+var_E8]
0x14006952a  mov     [rsp+170h+var_128], rcx
0x14006952f  lea     rcx, [rbp+70h+var_C0]
0x140069533  movups  [rbp+70h+var_B0], xmm0
0x140069537  mov     [rsp+170h+var_130], rcx
0x14006953c  mov     rcx, [rbx+8]
0x140069540  movups  [rbp+70h+var_C0], xmm0
0x140069544  mov     [rsp+170h+var_138], rax
0x140069549  movups  [rbp+70h+var_B0+0Ch], xmm0
0x14006954d  cmp     dword ptr [rax], 616C7049h
0x140069553  mov     rax, [rax+8]
0x140069557  setz    r9b
0x14006955b  mov     qword ptr [rsp+170h+var_148], rax
0x140069560  call    IpSecGetSessionInformation
0x140069565  mov     edi, eax
0x140069567  cmp     eax, 103h
0x14006956c  jnz     loc_140069A4B
0x140069572  jmp     loc_14006945E
0x140069577  mov     r15d, [rbx+2Ch]
0x14006957b  jmp     loc_14006928A
0x140069580  cmp     qword ptr [rbx+50h], 0
0x140069585  jz      short loc_1400695AE
0x140069587  mov     eax, r10d
0x14006958a  lea     rcx, [rbp+70h+var_90]
0x14006958e  lea     rcx, [rcx+rax*8]
0x140069592  movzx   eax, word ptr [rbx+32h]
0x140069596  inc     r10d
0x140069599  mov     dword ptr [rcx], 2Bh ; '+'
0x14006959f  add     r15d, eax
0x1400695a2  mov     [rbp+70h+var_EC], r10d
0x1400695a6  mov     dword ptr [rsp+170h+var_100], r15d
0x1400695ab  mov     [rcx+4], eax
0x1400695ae  mov     r8, [rbx+8]
0x1400695b2  mov     eax, 0FFFFFFFFh
0x1400695b7  mov     r11, [r8+0A0h]
0x1400695be  mov     rsi, [r8+8]
0x1400695c2  and     r11, rax
0x1400695c5  jnz     short loc_1400695E2
0x1400695c7  cmp     [r8+140h], r11d
0x1400695ce  jnz     short loc_1400695E2
0x1400695d0  mov     ecx, [rsi+18h]
0x1400695d3  add     ecx, r15d
0x1400695d6  cmp     ecx, 0FFFFh
0x1400695dc  ja      loc_140069BC7
0x1400695e2  xor     dil, dil
0x1400695e5  mov     r15d, edx
0x1400695e8  mov     rdx, [rbx+48h]
0x1400695ec  test    rdx, rdx
0x1400695ef  jnz     loc_1400698CB
0x1400695f5  test    dil, dil
0x1400695f8  jz      loc_14006928A
0x1400695fe  test    r11, r11
0x140069601  jnz     loc_140069C1B
0x140069607  mov     r8d, dword ptr [rsp+170h+var_100]
0x14006960c  mov     rsi, [rsi]
0x14006960f  test    rsi, rsi
0x140069612  jnz     loc_140069C62
0x140069618  test    rdx, rdx
0x14006961b  jz      loc_140069FBE
0x140069621  movzx   edx, word ptr [rbx+30h]
0x140069625  test    dil, dil
0x140069628  jz      short loc_14006962E
0x14006962a  add     [rbx+34h], dx
0x14006962e  mov     eax, r10d
  ... truncated ...
```
