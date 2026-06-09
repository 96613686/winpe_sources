# PfPdPfnDBWrite

- ea: `0x18007e748`
- end: `0x18007f71b`
- name: `PfPdPfnDBWrite`
- size: `4051`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180015e14`
- `0x18005a9e4`

## callees

- `0x180004948`
- `0x180006fa0`
- `0x180007198`
- `0x18000fcd8`
- `0x180017370`
- `0x180021e0c`
- `0x18002c990`
- `0x18002dce0`
- `0x180031e50`
- `0x180035f58`
- `0x180052aec`
- `0x180068f00`
- `0x18006e934`
- `0x180073e28`
- `0x18007560c`
- `0x1800789a8`
- `0x18007c448`
- `0x18007d224`
- `0x18007e748`
- `0x18008a70c`
- `0x18008af00`
- `0x18008b084`
- `0x18008baa8`
- `0x18008cd5c`
- `0x18008d700`
- `0x18008da60`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b6580`

## import_xrefs

- `msvcrt!fclose` at `0x18007f6cd`
- `msvcrt!fclose` at `0x18007f6db`
- `msvcrt!fclose` at `0x18007f6e9`
- `msvcrt!fclose` at `0x18007f6cd`
- `msvcrt!fclose` at `0x18007f6db`
- `msvcrt!fclose` at `0x18007f6e9`
- `msvcrt!fopen` at `0x18007ea93`
- `msvcrt!fopen` at `0x18007eb0e`
- `msvcrt!fopen` at `0x18007f4a7`
- `msvcrt!fopen` at `0x18007ea93`
- `msvcrt!fopen` at `0x18007eb0e`
- `msvcrt!fopen` at `0x18007f4a7`
- `msvcrt!fprintf` at `0x18007ea00`
- `msvcrt!fprintf` at `0x18007eac1`
- `msvcrt!fprintf` at `0x18007eb2b`
- `msvcrt!fprintf` at `0x18007eb3b`
- `msvcrt!fprintf` at `0x18007ecae`
- `msvcrt!fprintf` at `0x18007ef8b`
- `msvcrt!fprintf` at `0x18007f4ce`
- `msvcrt!fprintf` at `0x18007f4e8`
- `msvcrt!fprintf` at `0x18007f64a`
- `msvcrt!fprintf` at `0x18007ea00`
- `msvcrt!fprintf` at `0x18007eac1`
- `msvcrt!fprintf` at `0x18007eb2b`
- `msvcrt!fprintf` at `0x18007eb3b`
- `msvcrt!fprintf` at `0x18007ecae`
- `msvcrt!fprintf` at `0x18007ef8b`
- `msvcrt!fprintf` at `0x18007f4ce`
- `msvcrt!fprintf` at `0x18007f4e8`
- `msvcrt!fprintf` at `0x18007f64a`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18007ebe1`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18007ec64`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18007f05a`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18007ebe1`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18007ec64`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsForceCrash` at `0x18007f05a`

## string_xrefs

- `0x18007e9f6`: `Compaction failed! EC: 0x%x\n`
- `0x18007eaba`: `Could not opene %s for write!\n`
- `0x18007f4c7`: `Could not opene %s for write!\n`
- `0x18007eb31`: `Unknown, Pfn, Deleted, Key, Type, RefCount\n`
- `0x18007ef48`: `Deleted`
- `0x18007f3e4`: `%s\WsCompPages%s.db`

## pseudocode

```c
__int64 __fastcall PfPdPfnDBWrite(__int64 a1, __int64 a2, int a3)
{
  int v3; // r15d
  __int64 v4; // rsi
  unsigned int v5; // ebx
  __int128 v6; // xmm0
  int v7; // eax
  __int64 v8; // xmm1_8
  int v9; // ecx
  __int64 v10; // rcx
  FILE *v11; // r13
  FILE *v12; // r14
  FILE *v13; // rdi
  unsigned int v14; // ebx
  FILE *v15; // rax
  struct _BTDB_DATABASE *v16; // r12
  FILE *v17; // rax
  _QWORD *v18; // rcx
  unsigned __int16 *v19; // r15
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r14
  char v23; // r9
  unsigned int v24; // r8d
  unsigned int v25; // eax
  __int64 v26; // rbx
  __int64 v27; // rdi
  unsigned int v28; // eax
  unsigned int v29; // edx
  unsigned int v30; // r12d
  __int64 v31; // rbx
  unsigned int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // r9
  unsigned int v35; // ecx
  int v36; // edx
  __int64 v37; // rdi
  unsigned __int64 v38; // rdx
  bool v39; // zf
  __int64 v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __m128i *v44; // rax
  __m128i *v45; // rbx
  __m128i v46; // xmm0
  unsigned __int64 v47; // rcx
  int v48; // eax
  int v49; // ecx
  int v50; // edx
  __int64 SimilarForPfDb; // r8
  unsigned __int16 v52; // cx
  bool v53; // dl
  __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rax
  const char *v57; // r9
  int v58; // edx
  unsigned __int8 *Next; // rbx
  unsigned int v60; // eax
  int v61; // r14d
  unsigned int v62; // eax
  __int64 v63; // rdi
  unsigned int v64; // r12d
  unsigned int v65; // r15d
  unsigned int v66; // eax
  __int64 v67; // r13
  int v68; // r14d
  __int32 v69; // edx
  unsigned __int64 v70; // rdi
  __int64 v71; // rsi
  __int64 v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rcx
  unsigned __int64 v76; // r8
  __int64 v77; // rbx
  FILE *v78; // rax
  FILE *v79; // rax
  unsigned int i; // r14d
  __int64 v81; // rbx
  __int64 v82; // rdi
  int v83; // r8d
  __int64 *v84; // rcx
  __int64 v85; // r15
  __int64 *j; // rdx
  unsigned int v87; // ecx
  __int64 v88; // r8
  unsigned int v89; // eax
  __int64 v91; // [rsp+30h] [rbp-D0h]
  __int64 *v92; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v93; // [rsp+48h] [rbp-B8h]
  int v94; // [rsp+4Ch] [rbp-B4h]
  int v95; // [rsp+50h] [rbp-B0h]
  __int128 v96; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v97; // [rsp+68h] [rbp-98h]
  FILE *Stream; // [rsp+70h] [rbp-90h]
  FILE *v99; // [rsp+78h] [rbp-88h]
  __int64 v100; // [rsp+80h] [rbp-80h]
  __int64 v101; // [rsp+88h] [rbp-78h]
  __int64 v102; // [rsp+90h] [rbp-70h]
  __int64 v103; // [rsp+98h] [rbp-68h]
  FILE *v104; // [rsp+A0h] [rbp-60h]
  _QWORD v105[3]; // [rsp+A8h] [rbp-58h]
  _BYTE v106[64]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v107; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v108[624]; // [rsp+110h] [rbp+10h] BYREF
  int v109; // [rsp+380h] [rbp+280h]
  int v110; // [rsp+384h] [rbp+284h]
  __int128 v111; // [rsp+388h] [rbp+288h]
  __int64 v112; // [rsp+398h] [rbp+298h]
  _BYTE v113[624]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v114; // [rsp+620h] [rbp+520h] BYREF
  int v115; // [rsp+628h] [rbp+528h]
  _BYTE v116[624]; // [rsp+630h] [rbp+530h] BYREF
  int v117; // [rsp+8A0h] [rbp+7A0h]
  int v118; // [rsp+8A4h] [rbp+7A4h]
  __int128 v119; // [rsp+8A8h] [rbp+7A8h]
  __int64 v120; // [rsp+8B8h] [rbp+7B8h]
  _BYTE v121[624]; // [rsp+8D0h] [rbp+7D0h] BYREF
  int v122; // [rsp+B40h] [rbp+A40h]
  int v123; // [rsp+B44h] [rbp+A44h]
  __int128 v124; // [rsp+B48h] [rbp+A48h]
  __int64 v125; // [rsp+B58h] [rbp+A58h]
  _BYTE v126[624]; // [rsp+B70h] [rbp+A70h] BYREF
  int v127; // [rsp+DE0h] [rbp+CE0h]
  int v128; // [rsp+DE4h] [rbp+CE4h]
  __int128 v129; // [rsp+DE8h] [rbp+CE8h]
  __int64 v130; // [rsp+DF8h] [rbp+CF8h]
  _BYTE v131[624]; // [rsp+E10h] [rbp+D10h] BYREF
  int v132; // [rsp+1080h] [rbp+F80h]
  int v133; // [rsp+1084h] [rbp+F84h]
  __int128 v134; // [rsp+1088h] [rbp+F88h]
  __int64 v135; // [rsp+1098h] [rbp+F98h]
  _BYTE v136[624]; // [rsp+10B0h] [rbp+FB0h] BYREF
  int v137; // [rsp+1320h] [rbp+1220h]
  int v138; // [rsp+1324h] [rbp+1224h]
  __int128 v139; // [rsp+1328h] [rbp+1228h]
  __int64 v140; // [rsp+1338h] [rbp+1238h]
  char pszDest[272]; // [rsp+1350h] [rbp+1250h] BYREF
  wchar_t v142[264]; // [rsp+1460h] [rbp+1360h] BYREF
  _BYTE v143[528]; // [rsp+1670h] [rbp+1570h] BYREF

  v3 = a3;
  v94 = a3;
  v100 = a2;
  v4 = a1;
  v102 = a1;
  memset_0(v108, 0, 0x2A0u);
  memset_0(v116, 0, 0x2A0u);
  memset_0(v121, 0, 0x2A0u);
  memset_0(v131, 0, 0x2A0u);
  memset_0(v126, 0, 0x2A0u);
  memset_0(v136, 0, 0x2A0u);
  v97 = 0;
  v96 = 0;
  memset_0(v113, 0, 0x280u);
  v105[0] = "File";
  v105[1] = "Process";
  v105[2] = "Session";
  PfUDDatabaseInitializeEx(v108, 0);
  PfUDDatabaseInitializeEx(v116, 0);
  PfUDDatabaseInitializeEx(v121, 0);
  PfUDDatabaseInitializeEx(v131, 0);
  PfUDDatabaseInitializeEx(v126, 0);
  PfUDDatabaseInitializeEx(v136, 0);
  v5 = -16777216;
  if ( (v3 & 0xFF000000) != 0 )
    v5 = v3 & 0xFF000000;
  v93 = v5;
  LODWORD(v92) = v3 & 8;
  if ( (v3 & 8) != 0 )
  {
    v6 = *(_OWORD *)(v4 + 9792);
    v7 = *(_DWORD *)(v4 + 9784);
    v8 = *(_QWORD *)(v4 + 9808);
    v9 = *(_DWORD *)(v4 + 9788);
    v111 = v6;
    v109 = v7;
    v112 = v8;
  }
  else
  {
    v9 = 7;
    v8 = v112;
    v6 = v111;
    if ( *(_DWORD *)(v4 + 9788) > 7u )
      v9 = *(_DWORD *)(v4 + 9788);
    v7 = v109;
  }
  v110 = v9;
  v118 = v9;
  v123 = v9;
  v133 = v9;
  v128 = v9;
  v138 = v9;
  v117 = v7;
  v119 = v6;
  v122 = v7;
  v120 = v8;
  v124 = v6;
  v132 = v7;
  v125 = v8;
  v134 = v6;
  v127 = v7;
  v135 = v8;
  v129 = v6;
  v137 = v7;
  v130 = v8;
  v139 = v6;
  v114 = 0;
  v140 = v8;
  PfDbDatabaseInitialize(v113, 0);
  v115 = 1024;
  PfPrGetProcessSnapshot(v10, &v114);
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v104 = 0;
  v99 = 0;
  Stream = 0;
  if ( (v3 & 0x10) != 0 )
  {
    v14 = PfPdCompactData(v4, 1);
    if ( v14 )
    {
      v15 = _acrt_iob_func(2u);
      fprintf(v15, "Compaction failed! EC: 0x%x\n", v14);
      goto LABEL_137;
    }
    *(_BYTE *)(v4 + 352) = 1;
    PfPdPfnsQuery(v4, 10);
    v5 = v93;
  }
  v16 = (struct _BTDB_DATABASE *)(v4 + 8840);
  v101 = v4 + 8840;
  PfPrDatabaseGetNames(v4 + 8840, v113);
  v95 = v3 & 1;
  if ( (v3 & 1) != 0 )
  {
    StringCbPrintfA(pszDest, 0x104u, "%ws\\PfnDb%ws.csv", *(_QWORD *)&PfSvcGlobals + 888LL, v100);
    Stream = fopen(pszDest, "wt");
    v13 = Stream;
    if ( !Stream
      || (StringCbPrintfA(pszDest, 0x104u, "%ws\\PfnDbPFNUnknown%ws.csv", *(_QWORD *)&PfSvcGlobals + 888LL, v100),
          v99 = fopen(pszDest, "wt"),
          (v12 = v99) == 0) )
    {
      v17 = _acrt_iob_func(2u);
      fprintf(v17, "Could not opene %s for write!\n", pszDest);
      v14 = 996;
      goto LABEL_137;
    }
    fprintf(Stream, "Pfn, List, Use, Pri, VaOffset, DataImage, UseRange, LoweredPriority, Type, Key, Name\n");
    fprintf(v99, "Unknown, Pfn, Deleted, Key, Type, RefCount\n");
  }
  v93 = HIBYTE(v5);
  if ( !*(_QWORD *)(v4 + 8) )
    goto LABEL_81;
  do
  {
    v18 = *(_QWORD **)(v4 + 16);
    v19 = (unsigned __int16 *)(*(_QWORD *)v4 + 8LL * (_QWORD)v11);
    while ( 1 )
    {
      v20 = v18[1];
      if ( !v20 )
        break;
      v21 = v18[2];
      if ( (unsigned __int64)v19 < v21 + 8 * (v20 - *v18) )
      {
        v22 = *v18 + (((__int64)v19 - v21) >> 3);
        goto LABEL_24;
      }
      v18 += 3;
    }
    v22 = -1;
LABEL_24:
    v23 = *(_BYTE *)v19;
    v24 = *((_DWORD *)v19 + 1);
    if ( (*(_BYTE *)v19 & 1) != 0 )
    {
      v25 = v24 >> 20;
      if ( !(v24 >> 20) )
        goto LABEL_26;
      v27 = 8720;
    }
    else
    {
      v25 = v24 >> 12;
      if ( !(v24 >> 12) )
      {
LABEL_26:
        v26 = 0;
        goto LABEL_33;
      }
      v27 = 8640;
    }
    v29 = (v25 - 1) % *(_DWORD *)(v4 + v27 + 40);
    v28 = (v25 - 1) / *(_DWORD *)(v4 + v27 + 40);
    v30 = v29;
    v31 = v28;
    if ( v28 >= *(_DWORD *)(v4 + v27 + 44) )
    {
      PfsForceCrash(3221226528LL, 0, 0);
      v23 = *(_BYTE *)v19;
      v24 = *((_DWORD *)v19 + 1);
    }
    v26 = *(_DWORD *)(v4 + v27 + 28) * v30
        + (-(__int64)*(unsigned int *)(v4 + v27 + 32)
         & (*(_QWORD *)(112 * v31 + *(_QWORD *)(v4 + v27)) + *(unsigned int *)(v4 + v27 + 32) + 3LL));
    v16 = (struct _BTDB_DATABASE *)(v4 + 8840);
LABEL_33:
    if ( (v23 & 1) != 0 )
    {
      v32 = v24 >> 20;
      if ( !v32 )
        goto LABEL_40;
      v33 = 8760;
      v34 = 8764;
    }
    else
    {
      v32 = v24 >> 12;
      if ( !v32 )
        goto LABEL_40;
      v33 = 8680;
      v34 = 8684;
    }
    if ( (v32 - 1) / *(_DWORD *)(v33 + v4) >= *(_DWORD *)(v34 + v4) )
      PfsForceCrash(3221226528LL, 0, 0);
LABEL_40:
    v35 = v93;
    if ( _bittest((const int *)&v35, (*v19 >> 2) & 7) )
    {
      v36 = v95;
      if ( v95 )
      {
        PfPdPfnEntryToText(v4, v22, v143);
        fprintf(Stream, "%ws\n", v143);
        v36 = v95;
      }
      if ( v26 && (*(_BYTE *)(v26 + 20) & 2) == 0 && *(_DWORD *)(v26 + 16) )
      {
        v37 = **(_QWORD **)&PfSvcGlobals + *(unsigned int *)(v26 + 16);
        if ( (v94 & 2) == 0 || (*(_QWORD *)(v37 + 16) & 0x80000000000000LL) != 0 )
        {
          v38 = *((unsigned int *)v19 + 1);
          v39 = (*(_BYTE *)(v26 + 8) & 3) == 0;
          v40 = v19[1];
          v96 = 0;
          v97 = 0;
          if ( v39 )
          {
            v41 = (v38 >> 4) & 8 | (16 * (v40 | ((v38 & 0x7F) << 16)));
            v42 = v96 & 7;
          }
          else
          {
            LODWORD(v96) = 1;
            v43 = (v40 | ((v38 & 0x7FFFF) << 16)) + 0xFFFF800000000LL;
            if ( (v38 & 0x80000) == 0 )
              v43 = v40 | ((v38 & 0x7FFFF) << 16);
            v41 = v43 << 12;
            v42 = v96 & 0xFFF;
          }
          *(_QWORD *)&v96 = v42 | v41;
          v44 = (__m128i *)BtDbRangeFindEx(v16, v37, &v96, 0);
          v45 = v44;
          if ( v44 && (*(_BYTE *)v19 & 2) != 0 )
          {
            v46 = *v44;
            v107 = *v44;
            if ( (v96 & 3) != 0 )
              v47 = (unsigned __int64)v96 >> 12;
            else
              v47 = (unsigned __int64)v96 >> 4;
            if ( (_mm_cvtsi128_si32(v46) & 1) != 0 )
            {
              if ( v47 <= 0x7FFFFFFFFLL )
              {
                v48 = v107.m128i_i32[1];
              }
              else
              {
                v48 = v107.m128i_i32[1] | 0x80000;
                v47 -= 0xFFFF800000000LL;
              }
              v107.m128i_i16[1] = v47;
              v49 = v48 ^ (v48 ^ (v47 >> 16)) & 0x7FFFF;
            }
            else
            {
              v107.m128i_i16[1] = v47;
              v50 = v107.m128i_i32[1] & 0xFFFFFF7F | ((((unsigned __int64)v96 >> 3) & 1) << 7);
              v49 = v50 ^ ((unsigned __int8)v50 ^ BYTE2(v47)) & 0x7F;
            }
            v107.m128i_i32[1] = v49;
            SimilarForPfDb = BtDbRangeGetSimilarForPfDb(v108, v16, &v107);
            if ( SimilarForPfDb )
            {
              v39 = (_DWORD)v92 == 0;
              *(_QWORD *)(SimilarForPfDb + 16) = v45->m128i_i64[1];
              if ( v39 )
              {
                v52 = *v19;
                v53 = (v45->m128i_i8[0] & 8) != 0;
                *(_WORD *)(SimilarForPfDb + 18) = 0;
                *(_WORD *)(SimilarForPfDb + 16) = (v52 >> 2) & 7;
                *(_WORD *)(SimilarForPfDb + 20) = v53 + 1;
                *(_WORD *)(SimilarForPfDb + 22) = 1;
              }
              *(_DWORD *)(SimilarForPfDb + 8) = (v107.m128i_u8[0] >> 4) & 7
                                              | (*(_DWORD *)(SimilarForPfDb + 8)
                                               & 0xFFFFFF7F
                                               ^ (16 * (v107.m128i_i8[0] & 8)))
                                              & 0xFFFFFFF0;
              *(_QWORD *)(SimilarForPfDb + 8) &= 0xFFFFFFFFFFFFFF9FuLL;
            }
          }
          else
          {
            v54 = BtDbRangesGetSimilarForPfDb(v116, v16, v37, 1);
            v55 = v54;
            if ( v54 )
            {
              if ( !PfDbRangeFindEx(v116, v54, &v96) )
              {
                v56 = PfDbRangeCreate(v116, v55, &v96);
                if ( v56 )
                  *(_QWORD *)(v56 + 16) = 0;
              }
            }
          }
        }
      }
      else if ( v36 && v26 )
      {
        v57 = "Deleted";
        v58 = 0;
        if ( (*(_BYTE *)(v26 + 20) & 1) == 0 )
          v58 = *(_DWORD *)(v26 + 20) >> 3;
        LODWORD(v91) = v58;
        if ( (*(_BYTE *)(v26 + 20) & 2) == 0 )
          v57 = "Unknown";
        fprintf(
          v99,
          "UnknownPFN, %Ix, %s, %Ix, %s, %d\n",
          v22,
          v57,
          *(_QWORD *)(v26 + 8),
          v105[*(_QWORD *)(v26 + 8) & 3LL],
          v91);
      }
    }
    v11 = (FILE *)((char *)v11 + 1);
  }
  while ( (unsigned __int64)v11 < *(_QWORD *)(v4 + 8) );
  LOBYTE(v3) = v94;
LABEL_81:
  LODWORD(v92) = v3 & 2;
  BtDbDatabaseMergeToPfDb((struct _PFDB_DATABASE *)v121, v16);
  PfDbDatabaseSubtract(v121, v108);
  memset_0(v106, 0, sizeof(v106));
  BtDbIteratorAttachToDb(v16, v106);
  Next = (unsigned __int8 *)BtDbIteratorGetNext(v106);
  if ( Next )
  {
    do
    {
      v60 = *((_DWORD *)Next + 1);
      if ( (*Next & 1) != 0 )
      {
        v62 = v60 >> 20;
        v63 = v4 + 8896;
        v61 = 0;
      }
      else
      {
        v61 = 1;
        v62 = v60 >> 12;
        v63 = v4 + 8976;
      }
      v64 = *(_DWORD *)(v63 + 40);
      v65 = v62 - 1;
      v66 = (v62 - 1) / v64;
      v67 = v66;
      if ( v66 >= *(_DWORD *)(v63 + 44) )
        PfsForceCrash(3221226528LL, 0, 0);
      if ( !(_DWORD)v92
        || (*(_QWORD *)((-(__int64)*(unsigned int *)(v63 + 32)
                       & (*(unsigned int *)(v63 + 32) + *(_QWORD *)(112 * v67 + *(_QWORD *)v63) + 3LL))
                      + *(_DWORD *)(v63 + 28) * (v65 % v64)
                      + (-(__int64)(v61 != 0) & 0xFFFFFFFFFFFFFFE8uLL)
                      + 0x48)
          & 0x80000000000000LL) != 0 )
      {
        v68 = Next[1] + 1;
        v107 = *(__m128i *)Next;
        BtDbFillLogEntryForRange(&v107, &v96);
        v69 = v107.m128i_i32[1];
        v70 = v96;
        v71 = v101;
        do
        {
          if ( (*Next & 6) == 2 )
          {
            v72 = BtDbRangeGetSimilarForPfDb(v126, v71, &v107);
            v69 = v107.m128i_i32[1];
            v73 = v72;
            if ( v72 )
            {
              v74 = *((_QWORD *)Next + 1);
              *(_DWORD *)(v73 + 8) |= 0x10u;
              *(_QWORD *)(v73 + 16) = v74;
              *(_DWORD *)(v73 + 8) ^= (*(_DWORD *)(v73 + 8) ^ (16 * *Next)) & 0x80;
            }
          }
          else if ( (*Next & 0x70) == 0 )
          {
            BtDbRangeGetSimilarForPfDb(v131, v71, &v107);
            v69 = v107.m128i_i32[1];
          }
          --v68;
          v75 = 128;
          if ( (v107.m128i_i64[0] & 0x8000000001LL) != 0x8000000000LL )
            v75 = 16;
          v70 = v70 & 0xF | (v70 + v75) & 0xFFFFFFFFFFFFFFF0uLL;
          v76 = v70 >> 4;
          if ( (v70 & 3) != 0 )
            v76 = v70 >> 12;
          if ( (v107.m128i_i8[0] & 1) != 0 )
          {
            if ( v76 > 0x7FFFFFFFFLL )
            {
              v69 |= 0x80000u;
              v76 -= 0xFFFF800000000LL;
            }
            v107.m128i_i16[1] = v76;
            v69 ^= (v69 ^ (v76 >> 16)) & 0x7FFFF;
          }
          else
          {
            v107.m128i_i16[1] = v76;
            v69 = (v69 & 0xFFFFFF7F | (((v70 >> 3) & 1) << 7))
                ^ ((v69 & 0x7F | (unsigned __int8)(((v70 & 8) != 0) << 7))
                 ^ BYTE2(v76))
                & 0x7F;
          }
          v107.m128i_i32[1] = v69;
        }
        while ( v68 );
        v4 = v102;
        *(_QWORD *)&v96 = v70;
      }
      Next = (unsigned __int8 *)BtDbIteratorGetNext(v106);
    }
    while ( Next );
    LOBYTE(v3) = v94;
  }
  PfDbDatabaseSubtract(v121, v126);
  if ( (v3 & 4) != 0 )
  {
    PfDbDatabaseNormalize(v108);
    PfDbDatabaseNormalize(v121);
    PfDbDatabaseNormalize(v116);
    PfDbDatabaseNormalize(v131);
    PfDbDatabaseNormalize(v126);
    PfDbDatabaseNormalize(v136);
  }
  PfPrDatabaseGetNames(v108, v113);
  v77 = v100;
  StringCchPrintfW(v142, 0x104u, L"%s\\PfnDBKnown%s.db", *(_QWORD *)&PfSvcGlobals + 888LL, v100);
  PfUDFileWrite(v108, v142);
  PfPrDatabaseGetNames(v121, v113);
  StringCchPrintfW(v142, 0x104u, L"%s\\PfnDBNoPFNEntry%s.db", *(_QWORD *)&PfSvcGlobals + 888LL, v77);
  PfUDFileWrite(v121, v142);
  PfPrDatabaseGetNames(v116, v113);
  StringCchPrintfW(v142, 0x104u, L"%s\\PfnDBNoUDEntry%s.db", *(_QWORD *)&PfSvcGlobals + 888LL, v77);
  PfUDFileWrite(v116, v142);
  PfPrDatabaseGetNames(v131, v113);
  StringCchPrintfW(v142, 0x104u, L"%s\\NoPfnRefPages%s.db", *(_QWORD *)&PfSvcGlobals + 888LL, v77);
  PfUDFileWrite(v131, v142);
  PfPrDatabaseGetNames(v126, v113);
  StringCchPrintfW(v142, 0x104u, L"%s\\WsCompPages%s.db", *(_QWORD *)&PfSvcGlobals + 888LL, v77);
  PfUDFileWrite(v126, v142);
  PfPrDatabaseGetNames(v136, v113);
  StringCchPrintfW(v142, 0x104u, L"%s\\StorePages%s.db", *(_QWORD *)&PfSvcGlobals + 888LL, v77);
  PfUDFileWrite(v136, v142);
  if ( v95 )
  {
    StringCbPrintfA(pszDest, 0x104u, "%ws\\PfnDbFPUnknown%ws.csv", *(_QWORD *)&PfSvcGlobals + 888LL, v77);
    v78 = fopen(pszDest, "wt");
    v11 = v78;
    if ( !v78 )
    {
      v79 = _acrt_iob_func(2u);
      fprintf(v79, "Could not opene %s for write!\n", pszDest);
      v14 = 996;
      goto LABEL_136;
    }
    fprintf(v78, "UnknownKey, Key, Type, RefCount\n");
    for ( i = 0; i < 2; ++i )
    {
      v81 = 0;
      v82 = v4 + 16 * (i + 538LL);
      while ( 1 )
      {
        if ( v81 )
        {
          v83 = *(_DWORD *)(v82 + 4) >> 5;
          v103 = *(_QWORD *)(v81 + 8) & (-1LL << (*(_DWORD *)(v82 + 4) & 0x1F));
          v92 = (__int64 *)v81;
          v84 = (__int64 *)v81;
          v85 = *(_QWORD *)(v82 + 8)
              + 8LL
              * ((v83 - 1)
               & (HIBYTE(v103)
                + 37
                * (BYTE6(v103)
                 + 37
                 * (BYTE5(v103)
                  + 37
                  * (BYTE4(v103)
                   + 37
                   * (BYTE3(v103)
                    + 37 * (BYTE2(v103) + 37 * (BYTE1(v103) + 37 * ((unsigned int)(unsigned __int8)v103 + 11623883)))))))));
        }
        else
        {
          v81 = *(_QWORD *)(v82 + 8);
          v92 = (__int64 *)v81;
          v84 = (__int64 *)v81;
          v85 = v81;
          if ( !v81 )
            break;
        }
        if ( (*(_QWORD *)v81 & 0x8000000000000002uLL) == 0x8000000000000002uLL )
        {
          PfsHashTableCorruptionCallback(v82, 30, &v92);
          v84 = v92;
        }
        if ( !v84 )
          break;
        v81 = *v84;
        if ( (*v84 & 1) != 0 )
          break;
LABEL_127:
        if ( !v81 )
          goto LABEL_132;
        if ( !*(_DWORD *)(v81 + 16) )
        {
          v87 = 0;
          v88 = *(_QWORD *)(v81 + 8);
          v89 = *(_DWORD *)(v81 + 20);
          if ( (v89 & 1) == 0 )
            v87 = v89 >> 3;
          fprintf(v11, "UnknownKey, %Ix, %s, %d\n", v88, (const char *)v105[v88 & 3], v87);
        }
      }
      for ( j = (__int64 *)(v85 + 8);
            (unsigned __int64)j < *(_QWORD *)(v82 + 8) + 8 * ((unsigned __int64)*(unsigned int *)(v82 + 4) >> 5);
            ++j )
      {
        v81 = *j;
        if ( (*j & 1) == 0 )
        {
          v92 = (__int64 *)*j;
          goto LABEL_127;
        }
      }
LABEL_132:
      ;
    }
  }
  else
  {
    v11 = v104;
  }
  v14 = 0;
LABEL_136:
  v12 = v99;
  v13 = Stream;
LABEL_137:
  PfDbDatabaseCleanup(v108);
  PfDbDatabaseCleanup(v116);
  PfDbDatabaseCleanup(v121);
  PfDbDatabaseCleanup(v131);
  PfDbDatabaseCleanup(v126);
  PfDbDatabaseCleanup(v136);
  PfPrNameDbCleanup(v113);
  if ( v11 )
    fclose(v11);
  if ( v12 )
    fclose(v12);
  if ( v13 )
    fclose(v13);
  return v14;
}

```

## disassembly

```asm
0x18007e748  mov     [rsp-8+arg_10], rbx
0x18007e74d  push    rbp
0x18007e74e  push    rsi
0x18007e74f  push    rdi
0x18007e750  push    r12
0x18007e752  push    r13
0x18007e754  push    r14
0x18007e756  push    r15
0x18007e758  lea     rbp, [rsp-1790h]
0x18007e760  mov     eax, 1890h
0x18007e765  call    _alloca_probe
0x18007e76a  sub     rsp, rax
0x18007e76d  mov     rax, cs:__security_cookie
0x18007e774  xor     rax, rsp
0x18007e777  mov     [rbp+17C0h+var_40], rax
0x18007e77e  mov     r15d, r8d
0x18007e781  mov     [rsp+18C0h+var_1874], r8d
0x18007e786  mov     [rbp+17C0h+var_1840], rdx
0x18007e78a  mov     rsi, rcx
0x18007e78d  mov     [rbp+17C0h+var_1830], rcx
0x18007e791  mov     ebx, 2A0h
0x18007e796  mov     r8d, ebx; Size
0x18007e799  lea     rcx, [rbp+17C0h+var_17B0]; void *
0x18007e79d  xor     edx, edx; Val
0x18007e79f  call    memset_0
0x18007e7a4  mov     r8d, ebx; Size
0x18007e7a7  lea     rcx, [rbp+17C0h+var_1290]; void *
0x18007e7ae  xor     edx, edx; Val
0x18007e7b0  call    memset_0
0x18007e7b5  mov     r8d, ebx; Size
0x18007e7b8  lea     rcx, [rbp+17C0h+var_FF0]; void *
0x18007e7bf  xor     edx, edx; Val
0x18007e7c1  call    memset_0
0x18007e7c6  mov     r8d, ebx; Size
0x18007e7c9  lea     rcx, [rbp+17C0h+var_AB0]; void *
0x18007e7d0  xor     edx, edx; Val
0x18007e7d2  call    memset_0
0x18007e7d7  mov     r8d, ebx; Size
0x18007e7da  lea     rcx, [rbp+17C0h+var_D50]; void *
0x18007e7e1  xor     edx, edx; Val
0x18007e7e3  call    memset_0
0x18007e7e8  mov     r8d, ebx; Size
0x18007e7eb  lea     rcx, [rbp+17C0h+var_810]; void *
0x18007e7f2  xor     edx, edx; Val
0x18007e7f4  call    memset_0
0x18007e7f9  xorps   xmm0, xmm0
0x18007e7fc  lea     r8d, [rbx-20h]; Size
0x18007e800  xor     eax, eax
0x18007e802  lea     rcx, [rbp+17C0h+var_1510]; void *
0x18007e809  xor     edx, edx; Val
0x18007e80b  mov     [rsp+18C0h+var_1858], rax
0x18007e810  movups  [rsp+18C0h+var_1868], xmm0
0x18007e815  call    memset_0
0x18007e81a  lea     rax, aFile; "File"
0x18007e821  xor     edx, edx
0x18007e823  mov     [rbp+17C0h+var_1818], rax
0x18007e827  lea     rcx, [rbp+17C0h+var_17B0]
0x18007e82b  lea     rax, aProcess; "Process"
0x18007e832  mov     [rbp+17C0h+var_1810], rax
0x18007e836  lea     rax, aSession; "Session"
0x18007e83d  mov     [rbp+17C0h+var_1808], rax
0x18007e841  call    PfUDDatabaseInitializeEx
0x18007e846  xor     edx, edx
0x18007e848  lea     rcx, [rbp+17C0h+var_1290]
0x18007e84f  call    PfUDDatabaseInitializeEx
0x18007e854  xor     edx, edx
0x18007e856  lea     rcx, [rbp+17C0h+var_FF0]
0x18007e85d  call    PfUDDatabaseInitializeEx
0x18007e862  xor     edx, edx
0x18007e864  lea     rcx, [rbp+17C0h+var_AB0]
0x18007e86b  call    PfUDDatabaseInitializeEx
0x18007e870  xor     edx, edx
0x18007e872  lea     rcx, [rbp+17C0h+var_D50]
0x18007e879  call    PfUDDatabaseInitializeEx
0x18007e87e  xor     edx, edx
0x18007e880  lea     rcx, [rbp+17C0h+var_810]
0x18007e887  call    PfUDDatabaseInitializeEx
0x18007e88c  mov     ebx, 0FF000000h
0x18007e891  mov     eax, r15d
0x18007e894  and     eax, ebx
0x18007e896  mov     edx, 7
0x18007e89b  cmovnz  ebx, eax
0x18007e89e  mov     eax, r15d
0x18007e8a1  and     eax, 8
0x18007e8a4  mov     [rsp+18C0h+var_1878], ebx
0x18007e8a8  mov     dword ptr [rsp+18C0h+var_1880], eax
0x18007e8ac  jz      short loc_18007E8E0
0x18007e8ae  movups  xmm0, xmmword ptr [rsi+2640h]
0x18007e8b5  mov     eax, [rsi+2638h]
0x18007e8bb  movsd   xmm1, qword ptr [rsi+2650h]
0x18007e8c3  mov     ecx, [rsi+263Ch]
0x18007e8c9  movups  [rbp+17C0h+var_1538], xmm0
0x18007e8d0  mov     [rbp+17C0h+var_1540], eax
0x18007e8d6  movsd   [rbp+17C0h+var_1528], xmm1
0x18007e8de  jmp     short loc_18007E902
0x18007e8e0  mov     eax, [rsi+263Ch]
0x18007e8e6  mov     ecx, edx
0x18007e8e8  movsd   xmm1, [rbp+17C0h+var_1528]
0x18007e8f0  cmp     eax, edx
0x18007e8f2  movups  xmm0, [rbp+17C0h+var_1538]
0x18007e8f9  cmova   ecx, eax
0x18007e8fc  mov     eax, [rbp+17C0h+var_1540]
0x18007e902  mov     [rbp+17C0h+var_153C], ecx
0x18007e908  xor     edx, edx
0x18007e90a  mov     [rbp+17C0h+var_101C], ecx
0x18007e910  mov     [rbp+17C0h+var_D7C], ecx
0x18007e916  mov     [rbp+17C0h+var_83C], ecx
0x18007e91c  mov     [rbp+17C0h+var_ADC], ecx
0x18007e922  mov     [rbp+17C0h+var_59C], ecx
0x18007e928  lea     rcx, [rbp+17C0h+var_1510]
0x18007e92f  mov     [rbp+17C0h+var_1020], eax
0x18007e935  movups  [rbp+17C0h+var_1018], xmm0
0x18007e93c  mov     [rbp+17C0h+var_D80], eax
0x18007e942  movsd   [rbp+17C0h+var_1008], xmm1
0x18007e94a  movups  [rbp+17C0h+var_D78], xmm0
0x18007e951  mov     [rbp+17C0h+var_840], eax
0x18007e957  movsd   [rbp+17C0h+var_D68], xmm1
0x18007e95f  movups  [rbp+17C0h+var_838], xmm0
0x18007e966  mov     [rbp+17C0h+var_AE0], eax
0x18007e96c  movsd   [rbp+17C0h+var_828], xmm1
0x18007e974  movups  [rbp+17C0h+var_AD8], xmm0
0x18007e97b  mov     [rbp+17C0h+var_5A0], eax
0x18007e981  movsd   [rbp+17C0h+var_AC8], xmm1
0x18007e989  movups  [rbp+17C0h+var_598], xmm0
0x18007e990  mov     [rbp+17C0h+var_12A0], 0
0x18007e99b  movsd   [rbp+17C0h+var_588], xmm1
0x18007e9a3  call    PfDbDatabaseInitialize
0x18007e9a8  lea     rdx, [rbp+17C0h+var_12A0]
0x18007e9af  mov     [rbp+17C0h+var_1298], 400h
0x18007e9b9  call    PfPrGetProcessSnapshot
0x18007e9be  xor     r13d, r13d
0x18007e9c1  xor     r14d, r14d
0x18007e9c4  xor     edi, edi
0x18007e9c6  mov     [rbp+17C0h+var_1820], r13
0x18007e9ca  mov     [rsp+18C0h+var_1848], r14
0x18007e9cf  mov     [rsp+18C0h+Stream], rdi
0x18007e9d4  test    r15b, 10h
0x18007e9d8  jz      short loc_18007EA28
0x18007e9da  lea     edx, [rdi+1]
0x18007e9dd  mov     rcx, rsi
0x18007e9e0  call    PfPdCompactData
0x18007e9e5  mov     ebx, eax
0x18007e9e7  test    eax, eax
0x18007e9e9  jz      short loc_18007EA0B
0x18007e9eb  lea     ecx, [rdi+2]; Ix
0x18007e9ee  call    __acrt_iob_func
0x18007e9f3  mov     rcx, rax; Stream
0x18007e9f6  lea     rdx, aCompactionFail; "Compaction failed! EC: 0x%x\n"
0x18007e9fd  mov     r8d, ebx
0x18007ea00  call    cs:__imp_fprintf
0x18007ea06  jmp     loc_18007F674
0x18007ea0b  mov     edi, 1
0x18007ea10  mov     rcx, rsi
0x18007ea13  mov     [rsi+160h], dil
0x18007ea1a  lea     edx, [rdi+9]
0x18007ea1d  call    PfPdPfnsQuery
0x18007ea22  mov     ebx, [rsp+18C0h+var_1878]
0x18007ea26  jmp     short loc_18007EA2D
0x18007ea28  mov     edi, 1
0x18007ea2d  lea     r12, [rsi+2288h]
0x18007ea34  mov     rcx, r12
0x18007ea37  mov     [rbp+17C0h+var_1838], r12
0x18007ea3b  lea     rdx, [rbp+17C0h+var_1510]
0x18007ea42  call    PfPrDatabaseGetNames
0x18007ea47  mov     edx, r15d
0x18007ea4a  and     edx, edi
0x18007ea4c  mov     [rsp+18C0h+var_1870], edx
0x18007ea50  jz      loc_18007EB46
0x18007ea56  mov     r9, cs:PfSvcGlobals
0x18007ea5d  lea     r8, aWsPfndbWsCsv; "%ws\\PfnDb%ws.csv"
0x18007ea64  mov     rax, [rbp+17C0h+var_1840]
0x18007ea68  lea     rcx, [rbp+17C0h+pszDest]; pszDest
0x18007ea6f  add     r9, 378h
0x18007ea76  mov     [rsp+18C0h+var_18A0], rax
0x18007ea7b  mov     edx, 104h; cbDest
0x18007ea80  call    StringCbPrintfA
0x18007ea85  lea     rdx, aWt_0; "wt"
0x18007ea8c  lea     rcx, [rbp+17C0h+pszDest]; FileName
0x18007ea93  call    cs:__imp_fopen
0x18007ea99  mov     [rsp+18C0h+Stream], rax
0x18007ea9e  mov     rdi, rax
0x18007eaa1  test    rax, rax
0x18007eaa4  jnz     short loc_18007EAD1
0x18007eaa6  mov     ecx, 2; Ix
0x18007eaab  call    __acrt_iob_func
0x18007eab0  mov     rcx, rax; Stream
0x18007eab3  lea     r8, [rbp+17C0h+pszDest]
0x18007eaba  lea     rdx, aCouldNotOpeneS; "Could not opene %s for write!\n"
0x18007eac1  call    cs:__imp_fprintf
0x18007eac7  mov     ebx, 3E4h
0x18007eacc  jmp     loc_18007F674
0x18007ead1  mov     r9, cs:PfSvcGlobals
0x18007ead8  lea     r8, aWsPfndbpfnunkn; "%ws\\PfnDbPFNUnknown%ws.csv"
0x18007eadf  mov     rax, [rbp+17C0h+var_1840]
0x18007eae3  lea     rcx, [rbp+17C0h+pszDest]; pszDest
0x18007eaea  add     r9, 378h
0x18007eaf1  mov     [rsp+18C0h+var_18A0], rax
0x18007eaf6  mov     edx, 104h; cbDest
0x18007eafb  call    StringCbPrintfA
0x18007eb00  lea     rdx, aWt_0; "wt"
0x18007eb07  lea     rcx, [rbp+17C0h+pszDest]; FileName
0x18007eb0e  call    cs:__imp_fopen
0x18007eb14  mov     [rsp+18C0h+var_1848], rax
0x18007eb19  mov     r14, rax
0x18007eb1c  test    rax, rax
0x18007eb1f  jz      short loc_18007EAA6
0x18007eb21  lea     rdx, aPfnListUsePriV; "Pfn, List, Use, Pri, VaOffset, DataImag"...
0x18007eb28  mov     rcx, rdi; Stream
0x18007eb2b  call    cs:__imp_fprintf
0x18007eb31  lea     rdx, aUnknownPfnDele; "Unknown, Pfn, Deleted, Key, Type, RefCo"...
0x18007eb38  mov     rcx, r14; Stream
0x18007eb3b  call    cs:__imp_fprintf
0x18007eb41  mov     edi, 1
0x18007eb46  shr     ebx, 18h
0x18007eb49  mov     [rsp+18C0h+var_1878], ebx
0x18007eb4d  cmp     [rsi+8], r13
0x18007eb51  jbe     loc_18007EFAA
0x18007eb57  mov     rax, [rsi]
0x18007eb5a  mov     rcx, [rsi+10h]
0x18007eb5e  lea     r15, [rax+r13*8]
0x18007eb62  mov     rax, [rcx+8]
0x18007eb66  test    rax, rax
0x18007eb69  jz      short loc_18007EB93
0x18007eb6b  mov     r8, [rcx]
0x18007eb6e  mov     rdx, [rcx+10h]
0x18007eb72  sub     rax, r8
0x18007eb75  lea     rax, [rdx+rax*8]
0x18007eb79  cmp     r15, rax
0x18007eb7c  jb      short loc_18007EB84
0x18007eb7e  add     rcx, 18h
0x18007eb82  jmp     short loc_18007EB62
0x18007eb84  mov     r14, r15
0x18007eb87  sub     r14, rdx
0x18007eb8a  sar     r14, 3
0x18007eb8e  add     r14, r8
0x18007eb91  jmp     short loc_18007EB97
0x18007eb93  or      r14, 0FFFFFFFFFFFFFFFFh
0x18007eb97  mov     r9b, [r15]
0x18007eb9a  mov     r8d, [r15+4]
0x18007eb9e  mov     eax, r8d
0x18007eba1  test    dil, r9b
0x18007eba4  jz      short loc_18007EBB8
0x18007eba6  shr     eax, 14h
0x18007eba9  test    eax, eax
0x18007ebab  jnz     short loc_18007EBB1
0x18007ebad  xor     ebx, ebx
0x18007ebaf  jmp     short loc_18007EC20
0x18007ebb1  mov     edi, 2210h
0x18007ebb6  jmp     short loc_18007EBC4
0x18007ebb8  shr     eax, 0Ch
0x18007ebbb  test    eax, eax
0x18007ebbd  jz      short loc_18007EBAD
0x18007ebbf  mov     edi, 21C0h
0x18007ebc4  dec     eax
0x18007ebc6  xor     edx, edx
0x18007ebc8  div     dword ptr [rsi+rdi+28h]
0x18007ebcc  mov     r12d, edx
0x18007ebcf  mov     ebx, eax
0x18007ebd1  cmp     eax, [rsi+rdi+2Ch]
0x18007ebd5  jb      short loc_18007EBEE
0x18007ebd7  xor     r8d, r8d
0x18007ebda  xor     edx, edx
0x18007ebdc  mov     ecx, 0C0000420h
0x18007ebe1  call    cs:__imp_PfsForceCrash
0x18007ebe7  mov     r9b, [r15]
0x18007ebea  mov     r8d, [r15+4]
0x18007ebee  imul    r12d, [rsi+rdi+1Ch]
0x18007ebf4  mov     edx, [rsi+rdi+20h]
0x18007ebf8  mov     rax, [rsi+rdi]
0x18007ebfc  mov     edi, 1
0x18007ec01  imul    rcx, rbx, 70h ; 'p'
0x18007ec05  lea     rbx, [rdx+3]
0x18007ec09  neg     rdx
0x18007ec0c  add     rbx, [rcx+rax]
0x18007ec10  mov     eax, r12d
0x18007ec13  and     rbx, rdx
0x18007ec16  add     rbx, rax
0x18007ec19  lea     r12, [rsi+2288h]
0x18007ec20  test    dil, r9b
0x18007ec23  jz      short loc_18007EC39
0x18007ec25  shr     r8d, 14h
0x18007ec29  test    r8d, r8d
0x18007ec2c  jz      short loc_18007EC6A
0x18007ec2e  mov     ecx, 2238h
0x18007ec33  lea     r9d, [rcx+4]
0x18007ec37  jmp     short loc_18007EC4B
0x18007ec39  shr     r8d, 0Ch
0x18007ec3d  test    r8d, r8d
0x18007ec40  jz      short loc_18007EC6A
0x18007ec42  mov     ecx, 21E8h
0x18007ec47  lea     r9d, [rcx+4]
0x18007ec4b  xor     edx, edx
0x18007ec4d  lea     eax, [r8-1]
0x18007ec51  div     dword ptr [rcx+rsi]
0x18007ec54  cmp     eax, [r9+rsi]
0x18007ec58  jb      short loc_18007EC6A
0x18007ec5a  xor     r8d, r8d
0x18007ec5d  xor     edx, edx
0x18007ec5f  mov     ecx, 0C0000420h
0x18007ec64  call    cs:__imp_PfsForceCrash
  ... truncated ...
```
