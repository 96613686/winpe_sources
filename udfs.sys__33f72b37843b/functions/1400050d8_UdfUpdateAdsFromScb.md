# UdfUpdateAdsFromScb

- ea: `0x1400050d8`
- end: `0x140005e79`
- name: `UdfUpdateAdsFromScb`
- size: `3489`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x1400010f0`
- `0x140004514`
- `0x140006680`
- `0x14000cce0`
- `0x14000dc18`
- `0x14000efc8`
- `0x14000feb4`
- `0x1400104f0`
- `0x140051d74`
- `0x140052864`
- `0x140055060`

## callees

- `0x140004484`
- `0x1400050d8`
- `0x140005e80`
- `0x14000653c`
- `0x1400065c0`
- `0x140009450`
- `0x14000eda0`
- `0x140015344`
- `0x140016dd4`
- `0x14001758c`
- `0x140018594`
- `0x140018608`
- `0x14001bc30`
- `0x14001c080`
- `0x1400300ec`
- `0x14004d45c`

## pseudocode

```c
__int64 __fastcall UdfUpdateAdsFromScb(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // edi
  __int64 v6; // r14
  __int64 v7; // r13
  int v8; // edx
  __int64 v9; // rcx
  int v10; // eax
  char v11; // r10
  unsigned int v12; // esi
  unsigned int v13; // r15d
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r12d
  __int64 v18; // rcx
  int v19; // edx
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // r9
  int v22; // ecx
  int v23; // ecx
  unsigned int v24; // r8d
  unsigned int v25; // edx
  unsigned int i; // esi
  _QWORD *v27; // rdi
  unsigned int *v28; // rcx
  unsigned int v29; // ecx
  __int64 v30; // rdx
  __int16 v31; // r8
  int v32; // r8d
  bool v33; // dl
  unsigned int v34; // eax
  __int64 v35; // r9
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  __int64 v38; // rdi
  unsigned int v39; // ecx
  unsigned int v40; // eax
  unsigned int v41; // ecx
  __int128 *v42; // r8
  int v43; // r14d
  int v44; // r10d
  bool v45; // zf
  __int64 v46; // rax
  unsigned int v47; // edx
  unsigned int v48; // r10d
  unsigned int v49; // edx
  int v50; // edx
  int v51; // ecx
  unsigned int v52; // ecx
  int v53; // eax
  int BlockForIcb; // eax
  int v55; // ecx
  __int64 v56; // r9
  int v57; // edx
  unsigned int v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rdi
  unsigned int v65; // edi
  char v67; // [rsp+40h] [rbp-148h]
  char v68; // [rsp+41h] [rbp-147h]
  char v69; // [rsp+42h] [rbp-146h]
  char v70; // [rsp+43h] [rbp-145h]
  char v71; // [rsp+44h] [rbp-144h]
  char v72; // [rsp+45h] [rbp-143h]
  unsigned int v73; // [rsp+48h] [rbp-140h]
  unsigned int v74; // [rsp+4Ch] [rbp-13Ch]
  unsigned int v75; // [rsp+50h] [rbp-138h]
  unsigned int v76; // [rsp+60h] [rbp-128h]
  __int128 v78; // [rsp+70h] [rbp-118h] BYREF
  __int128 v79; // [rsp+80h] [rbp-108h]
  __int64 v80; // [rsp+90h] [rbp-F8h]
  unsigned int v81; // [rsp+98h] [rbp-F0h]
  unsigned int v82; // [rsp+9Ch] [rbp-ECh]
  unsigned int v83; // [rsp+A0h] [rbp-E8h]
  __int64 v84; // [rsp+A8h] [rbp-E0h]
  __int64 v85; // [rsp+B0h] [rbp-D8h]
  _QWORD *v86; // [rsp+B8h] [rbp-D0h]
  __int64 v87; // [rsp+C0h] [rbp-C8h]
  unsigned int v88; // [rsp+C8h] [rbp-C0h]
  unsigned __int64 v89; // [rsp+D0h] [rbp-B8h]
  unsigned int v90; // [rsp+D8h] [rbp-B0h]
  __int128 *v91; // [rsp+E0h] [rbp-A8h]
  unsigned int v92; // [rsp+E8h] [rbp-A0h]
  unsigned int v93; // [rsp+F0h] [rbp-98h]
  __int64 v94; // [rsp+F8h] [rbp-90h]
  unsigned int v95; // [rsp+100h] [rbp-88h]
  __int64 v96; // [rsp+108h] [rbp-80h]
  __int64 v97; // [rsp+110h] [rbp-78h]
  __int64 v98; // [rsp+118h] [rbp-70h]
  __int64 v99; // [rsp+120h] [rbp-68h]
  __int128 v100; // [rsp+128h] [rbp-60h] BYREF
  __int128 v101; // [rsp+138h] [rbp-50h] BYREF

  v83 = a4;
  v4 = a3;
  v74 = a3;
  v6 = a1;
  v97 = a1;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_DWORD *)(a2 + 212);
  v75 = (v8 & 0x20000) != 0 ? 16 : 8;
  v81 = (unsigned int)(0x40000000 - *(_DWORD *)(v7 + 68)) >> *(_DWORD *)(v7 + 72);
  v71 = 1;
  v9 = *(_QWORD *)(v7 + 352);
  v10 = *(_DWORD *)(v7 + 48);
  if ( v9 || (v67 = 1, (v10 & 0x20000000) != 0) )
    v67 = 0;
  if ( (v8 & 0x2000) != 0 || v9 || (v69 = 0, (v10 & 0x20000000) != 0) )
    v69 = 1;
  v11 = 0;
  v70 = 0;
  v87 = 0;
  v12 = 0;
  v101 = 0;
  v100 = 0;
  v13 = 0;
  v76 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_DDii(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      0,
      1,
      a3,
      a4,
      *(_QWORD *)(a2 + 304),
      *(_QWORD *)(a2 + 312));
    v11 = 0;
  }
  if ( (*(_DWORD *)(v7 + 48) & 0x8000000) == 0 && a2 == *(_QWORD *)(v7 + 320) )
  {
    v14 = *(_QWORD *)(v7 + 328);
    v15 = *(_DWORD *)(v14 + 212);
    if ( (v15 & 0x20000000) == 0 )
      *(_DWORD *)(v14 + 212) = v15 | 0x20000000;
  }
  v101 = 0;
  v100 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v16 = _mm_cvtsi128_si32((__m128i)0LL);
  v17 = 0;
  if ( !v67 )
    v16 = -1;
  LODWORD(v101) = v16;
  v18 = *(_QWORD *)(a2 + 304);
  v19 = *(_DWORD *)(v7 + 72);
  v20 = v18 - 1;
  if ( !v18 )
    v20 = 0;
  v21 = v20 >> v19;
  v89 = v21;
  v22 = *(_DWORD *)(a2 + 212);
  if ( (v22 & 0x2000) != 0
    || *(_DWORD *)(a2 + 296) != *(_DWORD *)(a2 + 300)
    || v4 <= (unsigned int)v21 && v83 >= (unsigned int)v21 )
  {
    v68 = 1;
    v72 = 1;
    if ( (v22 & 0x10) != 0 )
      goto LABEL_26;
  }
  else
  {
    v68 = 0;
  }
  v72 = 0;
LABEL_26:
  v23 = *(_DWORD *)(a2 + 296);
  v24 = v23 - 1;
  if ( !v23 )
    v24 = 0;
  if ( v69 )
  {
    if ( v24 <= (unsigned int)v21 )
      v24 = v21;
    v73 = v24;
    if ( v24 <= (unsigned int)v21 )
      goto LABEL_36;
  }
  else
  {
    v73 = v24;
  }
  if ( v4 >= (unsigned int)(*(_QWORD *)(a2 + 312) >> v19) )
  {
    v74 = *(_QWORD *)(a2 + 312) >> v19;
    v4 = v74;
  }
LABEL_36:
  v25 = *(_DWORD *)(a2 + 384);
  if ( v25 )
  {
    for ( i = 1; i <= v25; ++i )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a2 + 392) + 16LL * (i - 1) + 8) > v4 )
        break;
    }
    v24 = v73;
    v12 = i - 1;
    if ( v12 )
      v13 = *(_DWORD *)(*(_QWORD *)(a2 + 392) + 16LL * (v12 - 1) + 8);
  }
  v27 = (_QWORD *)(a2 + 184);
LABEL_43:
  v86 = v27;
  if ( v13 <= v24 && *(_QWORD *)(a2 + 304) )
  {
    if ( v12 )
      v28 = (unsigned int *)(*(_QWORD *)(a2 + 392) + 4LL + 16LL * (v12 - 1));
    else
      v28 = (unsigned int *)v27;
    v29 = *v28;
    v94 = *v27;
    UdfMapMetadataView(v6, (__int64)&v78, *(_QWORD *)(v6 + 16), SWORD2(v94), v29, *(_DWORD *)(v7 + 68), 20);
    if ( v12 )
    {
      v32 = 24;
    }
    else
    {
      if ( (*(_DWORD *)(a2 + 212) & 0x80000) != 0 )
      {
        v30 = v78;
        *(_WORD *)(v78 + 34) &= 0xFFF8u;
        v31 = *(_WORD *)(v30 + 34);
        if ( *(_QWORD *)(v7 + 352)
          || (*(_DWORD *)(*(_QWORD *)(v6 + 16) + 48LL) & 0x4000000) != 0
          && (*(_DWORD *)(a2 + 212) & 0x8000000) == 0
          && (v84 = *v27, WORD2(v84) == *(_WORD *)(*(_QWORD *)(v7 + 16) + 84LL)) )
        {
          *(_WORD *)(v30 + 34) = v31 | 1;
          *(_DWORD *)(a2 + 212) |= 0x20000u;
        }
        v75 = (*(_DWORD *)(a2 + 212) & 0x20000) != 0 ? 16 : 8;
        v92 = v75;
        v17 = 0;
        if ( *(_WORD *)v78 == 266 )
          *(_DWORD *)(v78 + 212) = 0;
        else
          *(_DWORD *)(v78 + 172) = 0;
        *(_DWORD *)(a2 + 212) &= ~0x80000u;
        memset(
          (void *)(v30 + *(unsigned int *)(a2 + 224)),
          0,
          (unsigned int)(*(_DWORD *)(v7 + 68) - *(_DWORD *)(a2 + 224)));
      }
      v32 = *(_DWORD *)(a2 + 224);
    }
    v33 = (*(_DWORD *)(a2 + 212) & 0x20000) != 0;
    v34 = ((unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 68LL) - v32) >> (v33 + 3)) - 1;
    LODWORD(v84) = v34;
    v35 = v78;
    if ( v12 )
    {
      v36 = *(_DWORD *)(v78 + 20);
    }
    else if ( *(_WORD *)v78 == 261 )
    {
      v36 = *(_DWORD *)(v78 + 172);
    }
    else
    {
      v36 = *(_DWORD *)(v78 + 212);
    }
    v37 = v36 >> (v33 + 3);
    if ( v12 )
      v38 = v78 + 24;
    else
      v38 = v78 + *(unsigned int *)(a2 + 224);
    v85 = v38;
    if ( v71 )
    {
      v39 = v74;
      while ( v17 < v37 )
      {
        v40 = v13
            + ((-*(_DWORD *)(v7 + 68) & (*(_DWORD *)(v7 + 68) + (*(_DWORD *)v38 & 0x3FFFFFFFu) - 1)) >> *(_DWORD *)(v7 + 72));
        v39 = v74;
        if ( v40 >= v74 )
          break;
        v13 += (-*(_DWORD *)(v7 + 68) & (*(_DWORD *)(v7 + 68) + (*(_DWORD *)v38 & 0x3FFFFFFFu) - 1)) >> *(_DWORD *)(v7 + 72);
        v82 = v40;
        v38 += v75;
        v85 = v38;
        ++v17;
      }
      if ( v13 < v39 )
        v39 = v13;
      v74 = v39;
      v93 = v39;
      DWORD2(v101) = v39;
      DWORD2(v100) = v39;
      UdfLookupNearestNonSparseExtent(v6, a2, a2 + 232, &v100);
      if ( v67 )
        UdfLookupNearestNonSparseExtent(v6, a2, a2 + 264, &v101);
      v71 = 0;
      v35 = v78;
      v34 = v84;
    }
    if ( !*(_QWORD *)(a2 + 304) )
    {
      v41 = v73;
      goto LABEL_130;
    }
    while ( 1 )
    {
      v41 = v73;
      if ( v17 >= v34 || v13 > v73 )
      {
LABEL_128:
        v6 = a1;
        goto LABEL_130;
      }
      v42 = 0;
      v91 = 0;
      if ( (_DWORD)v100 != -1 && v13 == DWORD2(v100) )
        break;
      if ( (_DWORD)v101 != -1 && v13 == DWORD2(v101) )
      {
        *(_DWORD *)v38 = *(_DWORD *)v38 & 0x3FFFFFFF | 0x40000000;
        v42 = &v101;
        goto LABEL_88;
      }
LABEL_89:
      if ( v42 )
      {
        *(_DWORD *)(v38 + 4) = *((_DWORD *)v42 + 1);
        v43 = v81;
        if ( *(_DWORD *)v42 <= v81 )
          v43 = *(_DWORD *)v42;
        v44 = v89;
        if ( v13 > (unsigned int)v89 || v43 + v13 - 1 < (unsigned int)v89 )
        {
          *(_DWORD *)v38 ^= (*(_DWORD *)v38 ^ (v43 << *(_DWORD *)(v7 + 72))) & 0x3FFFFFFF;
        }
        else
        {
          *(_DWORD *)v38 ^= (*(_DWORD *)v38
                           ^ (*(_DWORD *)(a2 + 304) - ((unsigned __int64)v13 << *(_DWORD *)(v7 + 72))))
                          & 0x3FFFFFFF;
          v43 = v44 - v13 + 1;
        }
        v45 = *(_DWORD *)v42 == v43;
        *(_DWORD *)v42 -= v43;
        if ( v45 )
        {
          v46 = a2 + 232;
          if ( &v100 != v42 )
            v46 = a2 + 264;
          UdfLookupNextNonSparseMcbExtent(a1, a2, v46, v42);
        }
        else
        {
          *((_DWORD *)v42 + 1) += v43;
          *((_DWORD *)v42 + 2) += v43;
        }
        v47 = *(_DWORD *)v38;
      }
      else
      {
        if ( v67 && (*(_DWORD *)(a2 + 212) & 0x2000) == 0 )
          goto LABEL_128;
        v48 = v89;
        if ( v13 > (unsigned int)v89 && (_DWORD)v101 == -1 && (_DWORD)v100 == -1 )
        {
          v6 = a1;
          if ( (*(_DWORD *)(v7 + 48) & 0x20000000) != 0 )
          {
            v13 = v73 + 1;
            v82 = v73 + 1;
          }
LABEL_130:
          if ( v69 && v13 <= v41
            || (*(_DWORD *)(a2 + 212) & 0x2000) == 0 && (v53 = *(_DWORD *)(a2 + 296)) != 0 && v13 <= v53 - 1 )
          {
            if ( v12 >= *(_DWORD *)(a2 + 384) )
            {
              v98 = *v86;
              BlockForIcb = UdfAllocateBlockForIcb(v6, WORD2(v98) == *(_WORD *)(*(_QWORD *)(v7 + 16) + 84LL));
              UdfInsertAdExtInfo(v6, a2, BlockForIcb, v12 + 1, v13);
            }
            *(_DWORD *)(v38 + 4) = *(_DWORD *)(*(_QWORD *)(a2 + 392) + 16LL * v12 + 4);
            v55 = *(_DWORD *)v38 ^ (*(_DWORD *)(v7 + 68) ^ *(_DWORD *)v38) & 0x3FFFFFFF;
            *(_DWORD *)v38 = v55;
            *(_DWORD *)v38 = v55 | 0xC0000000;
            if ( (*(_DWORD *)(a2 + 212) & 0x20000) != 0 )
            {
              v99 = *v86;
              *(_WORD *)(v38 + 8) = WORD2(v99);
            }
            *(_DWORD *)(*(_QWORD *)(a2 + 392) + 16LL * v12 + 8) = v13;
            v85 = 0;
            ++v17;
            v35 = v78;
          }
          if ( v12 )
          {
            *(_DWORD *)(*(_QWORD *)(a2 + 392) + 16LL * (v12 - 1) + 12) = v17;
            v56 = v78;
            *(_OWORD *)v78 = 0;
            *(_QWORD *)(v56 + 16) = 0;
            v57 = *(_DWORD *)(*(_QWORD *)(a2 + 392) + 16LL * (v12 - 1) + 4);
            *(_WORD *)v56 = 258;
            *(_WORD *)(v56 + 2) = 3 - (*(_WORD *)(*(_QWORD *)(v6 + 16) + 2136LL) != 10);
            *(_WORD *)(v56 + 6) = *(_WORD *)(*(_QWORD *)(v6 + 16) + 2140LL);
            *(_DWORD *)(v56 + 12) = v57;
            *(_DWORD *)(v56 + 20) = v75 * v17;
            UdfUpdateChecksumAndCrc(v56, 24);
            UdfSetMetaSectorState(v6, HIDWORD(v79), 1, &v78);
            UdfUnpinView(v6, &v78);
            v11 = v70;
          }
          else
          {
            if ( *(_WORD *)v35 == 261 )
              v58 = *(_DWORD *)(v35 + 172);
            else
              v58 = *(_DWORD *)(v35 + 212);
            if ( v58 > v75 * v17 )
            {
              if ( *(_WORD *)v35 == 261 )
                v59 = *(_DWORD *)(v35 + 172);
              else
                v59 = *(_DWORD *)(v35 + 212);
              memset((void *)(v35 + *(_DWORD *)(a2 + 224) + v75 * v17), 0, v59 - v75 * v17);
              v35 = v78;
            }
            v60 = v17 * v75;
            if ( *(_WORD *)v35 == 266 )
              *(_DWORD *)(v35 + 212) = v60;
            else
              *(_DWORD *)(v35 + 172) = v60;
            if ( v68 )
            {
              v61 = *(_QWORD *)(a2 + 304);
              v62 = v61 - *(_QWORD *)(v78 + 56);
              v87 = v62;
              v96 = v62;
              *(_QWORD *)(v78 + 56) = v61;
              if ( *(_WORD *)v78 == 266 )
                *(_QWORD *)(v78 + 64) += v62;
              v68 = 0;
            }
            UdfFinishModifyIcb(v6, (__int64)&v78, 1, (__int16 *)a2);
            v11 = 1;
            v70 = 1;
          }
          if ( *(_DWORD *)(a2 + 300) < v76 || v83 >= (unsigned int)v89 )
            *(_DWORD *)(a2 + 300) = v76;
          if ( *(_QWORD *)(a2 + 304) || v17 )
          {
            v90 = ++v12;
            v27 = v86;
            v24 = v73;
            v17 = 0;
            goto LABEL_43;
          }
          goto LABEL_164;
        }
        v49 = v13 + v81;
        v42 = (__int128 *)(*(_DWORD *)v38 & 0x3FFFFFFF);
        LODWORD(v42) = (unsigned int)v42 | 0x80000000;
        *(_DWORD *)v38 = (_DWORD)v42;
        *(_DWORD *)(v38 + 4) = 0;
        if ( (_DWORD)v100 != -1 && DWORD2(v100) < v49 )
          v49 = DWORD2(v100);
        if ( (_DWORD)v101 != -1 && DWORD2(v101) < v49 )
          v49 = DWORD2(v101);
        if ( v13 > v48 || v49 <= v48 )
          v50 = (v49 - v13) << *(_DWORD *)(v7 + 72);
        else
          v50 = *(_DWORD *)(a2 + 304) - ((unsigned __int64)v13 << *(_DWORD *)(v7 + 72));
        v47 = (unsigned int)v42 ^ ((unsigned int)v42 ^ v50) & 0x3FFFFFFF;
        *(_DWORD *)v38 = v47;
        v43 = (-*(_DWORD *)(v7 + 68) & ((v47 & 0x3FFFFFFF) + *(_DWORD *)(v7 + 68) - 1)) >> *(_DWORD *)(v7 + 72);
      }
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
      {
        WPP_SF_qdDDD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          v47 >> 30,
          v42,
          a2,
          v47 >> 30,
          *(_DWORD *)(v38 + 4),
          v47 & 0x3FFFFFFF,
          v43);
      }
      v51 = *(_DWORD *)(a2 + 212);
      if ( (v51 & 0x20000) != 0 )
      {
        *(_WORD *)(v38 + 8) = *(_WORD *)(((~v51 & 0x8000000 | 0x54000000uLL) >> 24) + *(_QWORD *)(v7 + 16));
        *(_DWORD *)(v38 + 10) = 0;
        *(_WORD *)(v38 + 14) = 0;
      }
      v13 += v43;
      v82 = v13;
      v52 = v76;
      if ( (*(_DWORD *)v38 & 0xC0000000) != 0x80000000 )
        v52 = v13;
      v76 = v52;
      v95 = v52;
      v38 += v75;
      v85 = v38;
      ++v17;
      v35 = v78;
      v34 = v84;
    }
    *(_DWORD *)v38 &= 0x3FFFFFFFu;
    v42 = &v100;
LABEL_88:
    v91 = v42;
    v35 = v78;
    goto LABEL_89;
  }
LABEL_164:
  if ( !v68 && v11 )
  {
    v64 = v87;
  }
  else
  {
    UdfPrepareModifyIcbForScb(v6, a2, &v78);
    if ( v68 )
    {
      v63 = *(_QWORD *)(a2 + 304);
      v64 = v63 - *(_QWORD *)(v78 + 56);
      v96 = v64;
      *(_QWORD *)(v78 + 56) = v63;
      if ( !*(_QWORD *)(a2 + 304) )
      {
        *(_DWORD *)(a2 + 300) = 0;
        if ( *(_WORD *)v78 == 266 )
          *(_DWORD *)(v78 + 212) = 0;
        else
          *(_DWORD *)(v78 + 172) = 0;
      }
      if ( *(_WORD *)v78 == 266 )
        *(_QWORD *)(v78 + 64) += v64;
    }
    else
    {
      v64 = v87;
    }
    UdfFinishModifyIcb(v6, (__int64)&v78, 1, (__int16 *)a2);
  }
  *(_QWORD *)(a2 + 312) = *(_QWORD *)(a2 + 304);
  if ( v72 )
  {
    UdfPrepareModifyIcbForScb(v6, *(_QWORD *)(*(_QWORD *)(a2 + 136) + 16LL), &v78);
    *(_QWORD *)(v78 + 64) += v64;
    UdfFinishModifyIcb(v6, (__int64)&v78, 1, *(__int16 **)(*(_QWORD *)(a2 + 136) + 16LL));
  }
  if ( v12 )
    v90 = --v12;
  v65 = v12;
  v88 = v12;
  while ( v65 < *(_DWORD *)(a2 + 384) )
  {
    v87 = *(_QWORD *)(a2 + 184);
    UdfDeallocateMetaDataBlock(
      v6,
      *(unsigned int *)(*(_QWORD *)(a2 + 392) + 16LL * v65++ + 4),
      WORD2(v87) == *(_WORD *)(*(_QWORD *)(v7 + 16) + 84LL));
    v88 = v65;
  }
  *(_DWORD *)(a2 + 384) = v12;
  return UdfUnpinView(v6, &v78);
}

```

## disassembly

```asm
0x1400050d8  push    rbx
0x1400050da  push    rsi
0x1400050db  push    rdi
0x1400050dc  push    r12
0x1400050de  push    r13
0x1400050e0  push    r14
0x1400050e2  push    r15
0x1400050e4  sub     rsp, 150h
0x1400050eb  mov     rax, cs:__security_cookie
0x1400050f2  xor     rax, rsp
0x1400050f5  mov     [rsp+188h+var_40], rax
0x1400050fd  mov     [rsp+188h+var_E8], r9d
0x140005105  mov     edi, r8d
0x140005108  mov     [rsp+188h+var_13C], r8d
0x14000510d  mov     rbx, rdx
0x140005110  mov     r14, rcx
0x140005113  mov     [rsp+188h+var_120], rcx
0x140005118  mov     [rsp+188h+var_78], rcx
0x140005120  xorps   xmm0, xmm0
0x140005123  xor     eax, eax
0x140005125  movups  [rsp+188h+var_118], xmm0
0x14000512a  movups  [rsp+188h+var_108], xmm0
0x140005132  mov     [rsp+188h+var_F8], rax
0x14000513a  mov     r13, [rcx+10h]
0x14000513e  mov     edx, [rdx+0D4h]
0x140005144  mov     eax, edx
0x140005146  and     eax, 20000h
0x14000514b  neg     eax
0x14000514d  sbb     eax, eax
0x14000514f  and     eax, 8
0x140005152  add     eax, 8
0x140005155  mov     [rsp+188h+var_138], eax
0x140005159  mov     eax, 40000000h
0x14000515e  sub     eax, [r13+44h]
0x140005162  mov     ecx, [r13+48h]
0x140005166  shr     eax, cl
0x140005168  mov     [rsp+188h+var_F0], eax
0x14000516f  mov     r8d, 1
0x140005175  mov     [rsp+188h+var_144], r8b
0x14000517a  mov     rcx, [r13+160h]
0x140005181  mov     eax, [r13+30h]
0x140005185  mov     r12d, 20000000h
0x14000518b  test    rcx, rcx
0x14000518e  jnz     short loc_14000519A
0x140005190  test    r12d, eax
0x140005193  mov     [rsp+188h+var_148], r8b
0x140005198  jz      short loc_14000519F
0x14000519a  mov     [rsp+188h+var_148], 0
0x14000519f  bt      edx, 0Dh
0x1400051a3  jb      short loc_1400051B3
0x1400051a5  test    rcx, rcx
0x1400051a8  jnz     short loc_1400051B3
0x1400051aa  test    r12d, eax
0x1400051ad  mov     [rsp+188h+var_146], cl
0x1400051b1  jz      short loc_1400051B8
0x1400051b3  mov     [rsp+188h+var_146], r8b
0x1400051b8  xor     r10b, r10b
0x1400051bb  mov     [rsp+188h+var_145], r10b
0x1400051c0  xor     edx, edx
0x1400051c2  mov     [rsp+188h+var_C8], rdx
0x1400051ca  xor     esi, esi
0x1400051cc  movups  [rsp+188h+var_50], xmm0
0x1400051d4  xorps   xmm1, xmm1
0x1400051d7  movups  [rsp+188h+var_60], xmm1
0x1400051df  xor     r15d, r15d
0x1400051e2  xor     r11d, r11d
0x1400051e5  mov     [rsp+188h+var_128], r11d
0x1400051ea  lea     rax, WPP_GLOBAL_Control
0x1400051f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400051f8  cmp     rcx, rax
0x1400051fb  jz      short loc_140005238
0x1400051fd  test    dword ptr [rcx+2Ch], 10000000h
0x140005204  jz      short loc_140005238
0x140005206  mov     rax, [rbx+138h]
0x14000520d  mov     [rsp+188h+var_158], rax
0x140005212  mov     rax, [rbx+130h]
0x140005219  mov     [rsp+188h+var_160], rax
0x14000521e  mov     [rsp+188h+var_168], r9d
0x140005223  mov     r9d, edi
0x140005226  mov     rcx, [rcx+18h]
0x14000522a  call    WPP_SF_DDii
0x14000522f  mov     r10b, [rsp+188h+var_145]
0x140005234  lea     r8d, [rsi+1]
0x140005238  test    dword ptr [r13+30h], 8000000h
0x140005240  jnz     short loc_140005266
0x140005242  cmp     rbx, [r13+140h]
0x140005249  jnz     short loc_140005266
0x14000524b  mov     rcx, [r13+148h]
0x140005252  mov     eax, [rcx+0D4h]
0x140005258  test    r12d, eax
0x14000525b  jnz     short loc_140005266
0x14000525d  or      eax, r12d
0x140005260  mov     [rcx+0D4h], eax
0x140005266  xorps   xmm2, xmm2
0x140005269  movups  [rsp+188h+var_50], xmm2
0x140005271  xorps   xmm0, xmm0
0x140005274  movups  [rsp+188h+var_60], xmm0
0x14000527c  xorps   xmm1, xmm1
0x14000527f  xor     eax, eax
0x140005281  movups  [rsp+188h+var_118], xmm1
0x140005286  movups  [rsp+188h+var_108], xmm1
0x14000528e  mov     [rsp+188h+var_F8], rax
0x140005296  movd    eax, xmm2
0x14000529a  or      r11d, 0FFFFFFFFh
0x14000529e  xor     r12d, r12d
0x1400052a1  cmp     [rsp+188h+var_148], r12b
0x1400052a6  cmovz   eax, r11d
0x1400052aa  mov     dword ptr [rsp+188h+var_50], eax
0x1400052b1  mov     rcx, [rbx+130h]
0x1400052b8  mov     edx, [r13+48h]
0x1400052bc  lea     r9, [rcx-1]
0x1400052c0  test    rcx, rcx
0x1400052c3  cmovz   r9, r12
0x1400052c7  mov     ecx, edx
0x1400052c9  shr     r9, cl
0x1400052cc  mov     [rsp+188h+var_B8], r9
0x1400052d4  mov     ecx, [rbx+0D4h]
0x1400052da  bt      ecx, 0Dh
0x1400052de  jb      short loc_140005304
0x1400052e0  mov     eax, [rbx+12Ch]
0x1400052e6  cmp     [rbx+128h], eax
0x1400052ec  jnz     short loc_140005304
0x1400052ee  cmp     edi, r9d
0x1400052f1  ja      short loc_1400052FD
0x1400052f3  cmp     [rsp+188h+var_E8], r9d
0x1400052fb  jnb     short loc_140005304
0x1400052fd  mov     [rsp+188h+var_147], r12b
0x140005302  jmp     short loc_140005313
0x140005304  mov     [rsp+188h+var_147], r8b
0x140005309  test    cl, 10h
0x14000530c  mov     [rsp+188h+var_143], r8b
0x140005311  jnz     short loc_140005318
0x140005313  mov     [rsp+188h+var_143], r12b
0x140005318  mov     ecx, [rbx+128h]
0x14000531e  lea     r8d, [rcx-1]
0x140005322  test    ecx, ecx
0x140005324  cmovz   r8d, r12d
0x140005328  cmp     [rsp+188h+var_146], r12b
0x14000532d  jz      short loc_140005342
0x14000532f  cmp     r8d, r9d
0x140005332  cmovbe  r8d, r9d
0x140005336  mov     [rsp+188h+var_140], r8d
0x14000533b  cmp     r8d, r9d
0x14000533e  ja      short loc_140005347
0x140005340  jmp     short loc_14000535D
0x140005342  mov     [rsp+188h+var_140], r8d
0x140005347  mov     ecx, edx
0x140005349  mov     rax, [rbx+138h]
0x140005350  shr     rax, cl
0x140005353  cmp     edi, eax
0x140005355  jb      short loc_14000535D
0x140005357  mov     [rsp+188h+var_13C], eax
0x14000535b  mov     edi, eax
0x14000535d  mov     edx, [rbx+180h]
0x140005363  test    edx, edx
0x140005365  jz      short loc_1400053AC
0x140005367  mov     r9d, 1
0x14000536d  mov     esi, r9d
0x140005370  cmp     edx, r9d
0x140005373  jb      short loc_140005395
0x140005375  mov     r8, [rbx+188h]
0x14000537c  lea     ecx, [rsi-1]
0x14000537f  add     rcx, rcx
0x140005382  cmp     [r8+rcx*8+8], edi
0x140005387  ja      short loc_140005390
0x140005389  add     esi, r9d
0x14000538c  cmp     esi, edx
0x14000538e  jbe     short loc_14000537C
0x140005390  mov     r8d, [rsp+188h+var_140]
0x140005395  add     esi, r11d
0x140005398  jz      short loc_1400053AC
0x14000539a  lea     ecx, [rsi-1]
0x14000539d  add     rcx, rcx
0x1400053a0  mov     rax, [rbx+188h]
0x1400053a7  mov     r15d, [rax+rcx*8+8]
0x1400053ac  lea     rdi, [rbx+0B8h]
0x1400053b3  mov     [rsp+188h+var_D0], rdi
0x1400053bb  cmp     r15d, r8d
0x1400053be  ja      loc_140005CCC
0x1400053c4  cmp     [rbx+130h], r12
0x1400053cb  jz      loc_140005CCC
0x1400053d1  test    esi, esi
0x1400053d3  jnz     short loc_1400053DA
0x1400053d5  mov     rcx, rdi
0x1400053d8  jmp     short loc_1400053EF
0x1400053da  lea     ecx, [rsi-1]
0x1400053dd  shl     rcx, 4
0x1400053e1  mov     rax, [rbx+188h]
0x1400053e8  add     rax, 4
0x1400053ec  add     rcx, rax
0x1400053ef  mov     ecx, [rcx]
0x1400053f1  mov     r9, [rdi]
0x1400053f4  mov     [rsp+188h+var_90], r9
0x1400053fc  shr     r9, 20h
0x140005400  mov     dword ptr [rsp+188h+var_158], 14h
0x140005408  mov     eax, [r13+44h]
0x14000540c  mov     dword ptr [rsp+188h+var_160], eax
0x140005410  mov     [rsp+188h+var_168], ecx
0x140005414  mov     r8, [r14+10h]
0x140005418  lea     rdx, [rsp+188h+var_118]
0x14000541d  mov     rcx, r14
0x140005420  call    UdfMapMetadataView
0x140005425  test    esi, esi
0x140005427  jnz     loc_140005510
0x14000542d  test    dword ptr [rbx+0D4h], 80000h
0x140005437  jz      loc_140005503
0x14000543d  mov     rdx, qword ptr [rsp+188h+var_118]
0x140005442  mov     eax, 0FFF8h
0x140005447  and     [rdx+22h], ax
0x14000544b  movzx   r8d, word ptr [rdx+22h]
0x140005450  cmp     [r13+160h], r12
0x140005457  jnz     short loc_14000548B
0x140005459  mov     rax, [r14+10h]
0x14000545d  test    dword ptr [rax+30h], 4000000h
0x140005464  jz      short loc_14000549D
0x140005466  test    dword ptr [rbx+0D4h], 8000000h
0x140005470  jnz     short loc_14000549D
0x140005472  mov     rcx, [rdi]
0x140005475  mov     [rsp+188h+var_E0], rcx
0x14000547d  shr     rcx, 20h
0x140005481  mov     rax, [r13+10h]
0x140005485  cmp     cx, [rax+54h]
0x140005489  jnz     short loc_14000549D
0x14000548b  or      r8w, 1
0x140005490  mov     [rdx+22h], r8w
0x140005495  bts     dword ptr [rbx+0D4h], 11h
0x14000549d  mov     eax, [rbx+0D4h]
0x1400054a3  and     eax, 20000h
0x1400054a8  neg     eax
0x1400054aa  sbb     r12d, r12d
0x1400054ad  and     r12d, 8
0x1400054b1  add     r12d, 8
0x1400054b5  mov     [rsp+188h+var_138], r12d
0x1400054ba  mov     [rsp+188h+var_A0], r12d
0x1400054c2  mov     rax, qword ptr [rsp+188h+var_118]
0x1400054c7  mov     ecx, 10Ah
0x1400054cc  xor     r12d, r12d
0x1400054cf  cmp     [rax], cx
0x1400054d2  jnz     short loc_1400054DD
0x1400054d4  mov     [rax+0D4h], r12d
0x1400054db  jmp     short loc_1400054E4
0x1400054dd  mov     [rax+0ACh], r12d
0x1400054e4  btr     dword ptr [rbx+0D4h], 13h
0x1400054ec  mov     ecx, [rbx+0E0h]
0x1400054f2  mov     r8d, [r13+44h]
0x1400054f6  sub     r8d, ecx; Size
0x1400054f9  add     rcx, rdx; void *
0x1400054fc  xor     edx, edx; Val
0x1400054fe  call    memset
0x140005503  test    esi, esi
0x140005505  jnz     short loc_140005510
0x140005507  mov     r8d, [rbx+0E0h]
0x14000550e  jmp     short loc_140005516
0x140005510  mov     r8d, 18h
0x140005516  mov     eax, [rbx+0D4h]
0x14000551c  and     eax, 20000h
0x140005521  neg     eax
0x140005523  sbb     edx, edx
0x140005525  neg     edx
0x140005527  mov     rax, [rbx+88h]
0x14000552e  mov     rcx, [rax+8]
0x140005532  mov     eax, [rcx+44h]
0x140005535  sub     eax, r8d
0x140005538  lea     ecx, [rdx+3]
0x14000553b  shr     eax, cl
0x14000553d  mov     r11d, 1
0x140005543  sub     eax, r11d
0x140005546  mov     dword ptr [rsp+188h+var_E0], eax
0x14000554d  mov     r9, qword ptr [rsp+188h+var_118]
0x140005552  test    esi, esi
0x140005554  jnz     short loc_140005573
0x140005556  mov     ecx, 105h
0x14000555b  cmp     [r9], cx
0x14000555f  jnz     short loc_14000556A
0x140005561  mov     r8d, [r9+0ACh]
0x140005568  jmp     short loc_140005577
0x14000556a  mov     r8d, [r9+0D4h]
0x140005571  jmp     short loc_140005577
0x140005573  mov     r8d, [r9+14h]
0x140005577  lea     ecx, [rdx+3]
0x14000557a  shr     r8d, cl
0x14000557d  mov     [rsp+188h+var_12C], r12d
0x140005582  test    esi, esi
0x140005584  jz      short loc_14000558C
0x140005586  lea     rdi, [r9+18h]
0x14000558a  jmp     short loc_140005595
0x14000558c  mov     edi, [rbx+0E0h]
0x140005592  add     rdi, r9
0x140005595  mov     [rsp+188h+var_D8], rdi
0x14000559d  cmp     [rsp+188h+var_144], 0
0x1400055a2  jz      loc_140005670
0x1400055a8  mov     ecx, [rsp+188h+var_13C]
0x1400055ac  mov     r10d, [rsp+188h+var_138]
0x1400055b1  cmp     r12d, r8d
0x1400055b4  jnb     short loc_1400055F9
0x1400055b6  mov     ecx, [r13+44h]
0x1400055ba  mov     eax, [rdi]
0x1400055bc  and     eax, 3FFFFFFFh
0x1400055c1  dec     eax
0x1400055c3  add     eax, ecx
  ... truncated ...
```
