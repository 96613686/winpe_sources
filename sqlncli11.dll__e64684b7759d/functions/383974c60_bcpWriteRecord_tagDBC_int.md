# bcpWriteRecord(tagDBC *,int *)

- ea: `0x383974c60`
- end: `0x3839769f4`
- name: `?bcpWriteRecord@@YAFPEAUtagDBC@@PEAH@Z`
- size: `7572`
- prototype: `__int16 __fastcall(struct tagDBC *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops`

## callers

- `0x3839743a0`

## callees

- `0x3838424f0`
- `0x3838427d0`
- `0x3838434c0`
- `0x3838435f0`
- `0x383869e70`
- `0x38386a410`
- `0x38386d210`
- `0x38386d3c0`
- `0x3838723c0`
- `0x38389a4e0`
- `0x38391aed0`
- `0x38391afe0`
- `0x383960610`
- `0x383961d40`
- `0x383962280`
- `0x383962350`
- `0x383969300`
- `0x38396a550`
- `0x3839740e0`
- `0x383974210`
- `0x383974c60`
- `0x38397dc10`
- `0x3839804e0`
- `0x3839905e0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x3839754c5`
- `KERNEL32!WriteFile` at `0x383975715`
- `KERNEL32!WriteFile` at `0x383975a5e`
- `KERNEL32!WriteFile` at `0x383975ce7`
- `KERNEL32!WriteFile` at `0x3839762c3`
- `KERNEL32!WriteFile` at `0x3839754c5`
- `KERNEL32!WriteFile` at `0x383975715`
- `KERNEL32!WriteFile` at `0x383975a5e`
- `KERNEL32!WriteFile` at `0x383975ce7`
- `KERNEL32!WriteFile` at `0x3839762c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall bcpWriteRecord(struct tagDBC *a1, int *a2)
{
  struct tagDBC *v2; // r12
  __int64 v3; // r8
  __int16 ColumnMetadata; // r14
  unsigned __int8 *v5; // r13
  __int64 v6; // rbx
  int v7; // esi
  int NewBatchCtx; // eax
  BATCHCTX *v9; // rcx
  struct tagDBC *v10; // rdi
  unsigned int v11; // edx
  unsigned __int8 *v12; // r9
  __int64 v13; // rbx
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // dx
  unsigned __int8 *v16; // r8
  int v17; // r15d
  char v18; // si
  char v19; // r12
  int v20; // edi
  __int64 v21; // r13
  void *v22; // rax
  __int64 v23; // rdx
  const unsigned __int8 *v24; // r9
  unsigned __int8 v25; // r8
  unsigned int v26; // r15d
  unsigned int v27; // ecx
  char v28; // al
  unsigned int v29; // edi
  unsigned int v30; // ecx
  unsigned int v31; // r14d
  void *v32; // rax
  __int64 v33; // rsi
  int *v34; // r15
  const unsigned __int8 *v35; // r9
  unsigned int v36; // edi
  __int16 v37; // ax
  __int16 v38; // ax
  char v39; // al
  __int16 v40; // cx
  int v41; // eax
  struct tagDBC *v42; // r12
  unsigned __int16 v43; // bx
  __int16 v44; // ax
  struct tagDBC *v45; // rbx
  int v46; // esi
  __int16 v47; // bx
  __int64 v48; // rdx
  __int64 v49; // rax
  int *v50; // r10
  __int16 v51; // dx
  __int64 v52; // rcx
  size_t v53; // r12
  struct BCPFILE *v54; // r15
  __int16 v55; // ax
  unsigned __int8 *v56; // r9
  int v57; // edi
  __int16 v58; // bx
  __int64 v59; // rdx
  unsigned __int64 v60; // rax
  __int64 v61; // rax
  int v62; // r8d
  int v63; // r8d
  int v64; // r8d
  unsigned __int8 *v65; // rsi
  __int64 v66; // rsi
  __int16 v67; // bx
  __int64 v68; // rdx
  __int64 v69; // rax
  __int16 v70; // bx
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int16 v73; // bx
  __int64 v74; // rdx
  char *v75; // rdi
  int v76; // r12d
  char *v77; // rbx
  struct BCPFILE *v78; // rbx
  const unsigned __int8 *v79; // r9
  int *v80; // r15
  __int64 v81; // r8
  struct tagOBJBASE *v82; // rdi
  int v83; // eax
  unsigned __int16 v84; // si
  __int64 v85; // rcx
  int v86; // eax
  __int64 *v87; // rdi
  struct BCPFILE *v88; // rsi
  unsigned __int64 v89; // rbx
  int v90; // edi
  const unsigned __int8 *v91; // r9
  __int16 v92; // bx
  __int64 v93; // rdx
  int v94; // eax
  __int16 v95; // ax
  char v96; // al
  __int64 v97; // rdx
  BATCHCTX *v98; // rax
  __int64 v99; // rbx
  __int64 *v102; // [rsp+28h] [rbp-D8h]
  __int64 v103; // [rsp+30h] [rbp-D0h]
  __int64 v104; // [rsp+38h] [rbp-C8h]
  int v105; // [rsp+50h] [rbp-B0h]
  struct tagDBC *v106; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v108; // [rsp+68h] [rbp-98h]
  __int16 v109; // [rsp+6Ch] [rbp-94h]
  int *Src; // [rsp+70h] [rbp-90h]
  unsigned __int16 v111; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v112; // [rsp+80h] [rbp-80h] BYREF
  int v113; // [rsp+88h] [rbp-78h]
  __int64 v114; // [rsp+90h] [rbp-70h] BYREF
  char *v115; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v116; // [rsp+A0h] [rbp-60h]
  unsigned int v117; // [rsp+A8h] [rbp-58h]
  struct BCPFILE *v118; // [rsp+B0h] [rbp-50h]
  __int64 v119; // [rsp+B8h] [rbp-48h] BYREF
  char *v120; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v121; // [rsp+C8h] [rbp-38h]
  int v122; // [rsp+D0h] [rbp-30h]
  int v123; // [rsp+D4h] [rbp-2Ch]
  unsigned int v124; // [rsp+D8h] [rbp-28h] BYREF
  int v125; // [rsp+DCh] [rbp-24h]
  __int64 v126; // [rsp+E0h] [rbp-20h] BYREF
  char v127; // [rsp+E8h] [rbp-18h]
  unsigned int v128; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v129; // [rsp+F8h] [rbp-8h] BYREF
  BATCHCTX *v130; // [rsp+100h] [rbp+0h]
  int v131; // [rsp+108h] [rbp+8h]
  int *v132; // [rsp+110h] [rbp+10h]
  __int64 v133; // [rsp+118h] [rbp+18h] BYREF
  __int64 v134; // [rsp+120h] [rbp+20h]
  BATCHCTX *v135; // [rsp+128h] [rbp+28h]
  DWORD v136; // [rsp+130h] [rbp+30h] BYREF
  struct BCPFILE *v137; // [rsp+138h] [rbp+38h]
  struct BCPFILE *v138; // [rsp+140h] [rbp+40h]
  DWORD v139; // [rsp+148h] [rbp+48h] BYREF
  DWORD v140; // [rsp+14Ch] [rbp+4Ch] BYREF
  DWORD v141; // [rsp+150h] [rbp+50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+154h] [rbp+54h] BYREF
  __int64 v143; // [rsp+158h] [rbp+58h]
  unsigned __int64 v144; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int8 v145[144]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int8 v146[1024]; // [rsp+200h] [rbp+100h] BYREF

  v143 = -2;
  v132 = a2;
  v2 = a1;
  v3 = 0;
  ColumnMetadata = 0;
  v116 = (unsigned __int8 *)*((_QWORD *)a1 + 1006);
  v125 = *((_DWORD *)a1 + 2514);
  v134 = 0;
  v135 = 0;
  v5 = v116 + 1672;
  v106 = (struct tagDBC *)(v116 + 1672);
  v138 = (struct BCPFILE *)*((_QWORD *)v116 + 215);
  *a2 = 0;
  v6 = *((_QWORD *)a1 + 1003);
  v7 = 0;
  if ( *(_QWORD *)(v6 + 1112)
    || (NewBatchCtx = CConnection::GetNewBatchCtx(
                        *(CConnection **)(*(_QWORD *)(v6 + 112) + 64LL),
                        *((struct CConnection **)a1 + 1003),
                        (struct BATCHCTX **)(v6 + 1112)),
        v7 = NewBatchCtx,
        NewBatchCtx >= 0) )
  {
    v9 = *(BATCHCTX **)(v6 + 1112);
    v130 = v9;
    if ( (*(_BYTE *)(*((_QWORD *)v9 + 8) + 400LL) & 1) != 0 )
    {
      v134 = v6;
      v135 = v9;
      ++*(_DWORD *)(v6 + 1120);
    }
  }
  else
  {
    v130 = 0;
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43228[0], 3964937, (unsigned int)NewBatchCtx);
  }
  if ( v7 < 0 )
  {
    ColumnMetadata = -1;
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7031817, off_383B49120[0], 6867);
    goto LABEL_11;
  }
  v11 = 0;
  v105 = 0;
  v12 = v116;
  if ( !*((_DWORD *)v116 + 5) )
    goto LABEL_424;
  while ( 1 )
  {
    v13 = *(_QWORD *)v12 + 448LL * v11;
    Src = (int *)v13;
    v14 = *(_WORD *)(v13 + 48);
    v111 = v14;
    v15 = v11 + 1;
    v108 = v15;
    v113 = 0;
    if ( v14 )
      break;
LABEL_368:
    v11 = v105 + 1;
    v105 = v11;
    if ( v11 >= *((_DWORD *)v12 + 5) )
      goto LABEL_424;
  }
  v16 = (unsigned __int8 *)(600LL * v14 + *((_QWORD *)v12 + 1) - 600LL);
  v121 = v16;
  v137 = (struct BCPFILE *)*((_QWORD *)v5 + 6);
  v122 = 0;
  v123 = 0;
  v120 = 0;
  v115 = 0;
  v112 = 0;
  v119 = 0;
  v117 = 0;
  v17 = 0;
  v18 = v16[36];
  v19 = v18;
  v20 = *(unsigned __int8 *)(v13 + 100);
  if ( v18 == 98 )
  {
    v126 = 0;
    v127 = 0;
    v21 = *((_QWORD *)v16 + 6);
    memcpy((void *)v21, v16, 0x258u);
    *(_DWORD *)(v21 + 56) = 0;
    *(_QWORD *)(v21 + 48) = 0;
    if ( v20 == 98 )
    {
      if ( !*(_QWORD *)(v13 + 144) )
      {
        v22 = SQLAllocateMemory(a1, 0x1C0u);
        *(_QWORD *)(v13 + 144) = v22;
        if ( !v22 )
        {
          ColumnMetadata = -1;
          if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
            bidTraceW(off_383B43238[0], 7095305, off_383B49120[0], 6929);
          goto LABEL_435;
        }
      }
      v13 = *(_QWORD *)(v13 + 144);
      if ( *(_QWORD *)(v13 + 120) && *(_QWORD *)(v13 + 72) )
      {
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
        *(_QWORD *)(v13 + 72) = 0;
      }
      v23 = *(_QWORD *)(v13 + 104);
      if ( v23 && v23 != *((_QWORD *)Src + 13) )
      {
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
        *(_QWORD *)(v13 + 104) = 0;
      }
      memcpy((void *)v13, Src, 0x1C0u);
      *(_QWORD *)(v13 + 104) = 0;
      *(_DWORD *)(v13 + 112) = 0;
      *(_DWORD *)(v13 + 152) = 0;
      *(_QWORD *)(v13 + 144) = 0;
    }
    if ( (unsigned __int16)GetColData(
                             *((struct tagSTMT **)a1 + 1003),
                             v146,
                             0,
                             (__int64 *)&v112,
                             &v119,
                             -2,
                             v108,
                             0xFFFFFFFF,
                             0,
                             0) == 0xFFFF )
    {
      ColumnMetadata = -1;
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7138313, off_383B49120[0], 6971);
      goto LABEL_435;
    }
    if ( v119 == -1 )
    {
      v5 = (unsigned __int8 *)v106;
      if ( *(_WORD *)(v13 + 50) )
      {
LABEL_30:
        if ( v20 == 98 )
        {
          *(_QWORD *)(v13 + 104) = *((_QWORD *)Src + 13);
          *(_DWORD *)(v13 + 112) = Src[28];
        }
        v15 = v108;
        v16 = v121;
        v12 = v116;
        goto LABEL_58;
      }
      LODWORD(v133) = 0;
      if ( bcpWrite(v106, (struct BCPFILE *)Src[24], (__int64)&v133, v24) != -1 )
      {
        *(_DWORD *)(v13 + 96) = 0;
        goto LABEL_30;
      }
      ColumnMetadata = -1;
      if ( (bidGblFlags & 2) == 0 || !off_383B49120[0] )
      {
LABEL_11:
        v10 = (struct tagDBC *)v5;
        goto LABEL_436;
      }
      bidTraceW(off_383B43238[0], 7152649, off_383B49120[0], 6985);
      v10 = v106;
LABEL_436:
      if ( bcpWriteSeek(v10, v138, v3) == -1 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7770121, off_383B49120[0], 7588);
        PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        goto LABEL_441;
      }
      goto LABEL_442;
    }
    v124 = 0;
    GetVariantHdrFromColInfo(a1, v108, (struct VariantHdr *)&v126, (struct tagCOLUMN_INFO *)v145, &v124);
    v19 = v126;
    if ( *((_WORD *)Src + 25) || *((_BYTE *)Src + 100) != 98 )
    {
      v5 = (unsigned __int8 *)v106;
      v13 = (__int64)Src;
      v15 = v108;
      v16 = v121;
      v12 = v116;
      goto LABEL_59;
    }
    *((_DWORD *)v121 + 14) = 1;
    v131 = 1;
    Src[38] = 1;
    ColumnMetadata = bcpGetColumnMetadata(a1, (struct tagBCPCOL *)v21, (struct tagCOLUMN_INFO *)v145, &v144);
    if ( ColumnMetadata == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7192585, off_383B49120[0], 7024);
      goto LABEL_435;
    }
    v25 = *(_BYTE *)(v21 + 36);
    v26 = v124;
    if ( v116[48] < 0x64u && (v25 == 41 || v25 == 42 || v25 == 43 || v25 == 40) )
    {
      v25 = -25;
      v27 = v124;
    }
    else
    {
      v27 = -1;
    }
    if ( !BCP_colfmt(a1, v105 + 1, v25, -1, v27, *((const unsigned __int8 **)Src + 13), Src[28], v105 + 1) )
    {
      ColumnMetadata = -1;
LABEL_435:
      v10 = v106;
      goto LABEL_436;
    }
    v28 = *(_BYTE *)(v21 + 36);
    if ( v28 == 108 || v28 == 106 )
      v117 = 2;
    *(_DWORD *)(v13 + 96) = 0;
    *(_DWORD *)(v13 + 160) = *(_DWORD *)(v21 + 72);
    *(_BYTE *)(v13 + 164) = *(_BYTE *)(v21 + 76);
    if ( v19 )
    {
      v29 = BYTE1(v126) + 2;
      v30 = v29 + Src[24];
      if ( v30 < v29 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43238[0], 7246889, off_383B49128[0], 2147942934LL);
        ColumnMetadata = -1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7247881, off_383B49120[0], 7078);
        goto LABEL_435;
      }
      v31 = v29 + Src[24];
      v32 = SQLAllocateMemory(a1, v30);
      v33 = (__int64)v32;
      if ( !v32 )
      {
        ColumnMetadata = -1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7253001, off_383B49120[0], 7083);
        goto LABEL_435;
      }
      v128 = v26 + v29;
      v34 = Src;
      memcpy(v32, &v128, Src[24]);
      memcpy((void *)(v33 + Src[24]), &v126, v29);
      v10 = v106;
      ColumnMetadata = bcpWrite(v106, (struct BCPFILE *)v31, v33, v35);
      ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl->Free)(g_pMO, v33);
      v18 = 98;
    }
    else
    {
      v10 = v106;
      v34 = Src;
    }
    if ( ColumnMetadata == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7268361, off_383B49120[0], 7098);
      goto LABEL_436;
    }
    *((_DWORD *)v121 + 14) = 0;
    v34[38] = 0;
    v16 = (unsigned __int8 *)v21;
    v121 = (unsigned __int8 *)v21;
    v17 = v131;
    v5 = (unsigned __int8 *)v106;
    v15 = v108;
    v12 = v116;
LABEL_58:
    Src = (int *)v13;
    goto LABEL_59;
  }
  if ( v12[48] < 0x64u && *(_DWORD *)(v13 + 152) )
  {
    v13 = *(_QWORD *)(v13 + 144);
    goto LABEL_58;
  }
LABEL_59:
  v36 = 1022;
  v37 = *(_WORD *)(v13 + 50);
  if ( v37 == 2 )
  {
    v146[0] = *v16;
    v146[1] = v16[18];
  }
  else if ( v37 == -12 && *(_BYTE *)(v13 + 100) == 122 || v37 == -23 && *(_BYTE *)(v13 + 100) == 58 )
  {
    v36 = 4;
  }
  else if ( v37 == 1 )
  {
    if ( (v38 = *((_WORD *)v16 + 8), v38 <= -2) && v38 >= -4
      || v38 == 14
      || v18 == 98 && (v19 == 45 || v19 == 37 || v19 == -83 || v19 == -91) )
    {
      v36 = 1021;
    }
  }
  if ( !ColumnMetadata )
  {
    if ( v119 == -1 )
    {
LABEL_102:
      v112 = 0;
LABEL_133:
      v46 = v105;
      v45 = a1;
      goto LABEL_134;
    }
    v39 = *(_BYTE *)(v13 + 100);
    if ( v39 == 41 )
    {
      v40 = -31;
    }
    else if ( v39 == 43 )
    {
      v40 = -32;
    }
    else
    {
      v40 = *(_WORD *)(v13 + 50);
    }
    if ( *((_DWORD *)v16 + 18) || v16[76] || *(_DWORD *)(v13 + 160) || *(_BYTE *)(v13 + 164) )
    {
      v41 = *(_DWORD *)(v13 + 156);
      v42 = a1;
      if ( *((_DWORD *)a1 + 2514) != v41 )
        *((_DWORD *)a1 + 2514) = v41;
    }
    else
    {
      v42 = a1;
    }
    ColumnMetadata = GetColData(
                       *((struct tagSTMT **)v42 + 1003),
                       v146,
                       v36,
                       (__int64 *)&v112,
                       &v119,
                       v40,
                       v15,
                       0xFFFFFFFF,
                       0,
                       0);
    if ( ColumnMetadata == -1 )
    {
      v94 = *((_DWORD *)v42 + 2514);
      if ( v94 != v125 )
        v94 = v125;
      *((_DWORD *)v42 + 2514) = v94;
      XferErrors(v42, *((struct tagOBJBASE **)v42 + 1003));
      goto LABEL_435;
    }
    if ( v119 != -1 && (unsigned __int8)(*(_BYTE *)(v13 + 100) - 40) <= 3u )
    {
      v43 = bcpConvertToDateTimeTDSFormat((struct tagBCPFLD *)v13, v146, (__int64)v146, v112, (__int64)&v112, v102);
      if ( v43 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7370761, off_383B49120[0], 7198);
        PostSQLErrorEx(v42, v43, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
        ColumnMetadata = -1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7371785, off_383B49120[0], 7199);
        goto LABEL_435;
      }
      v13 = (__int64)Src;
    }
    v12 = v116;
    if ( v116[48] >= 0x5Au
      && *(_DWORD *)(v13 + 96) == 8
      && (v112 == (unsigned __int8 *)-4LL || (__int64)v112 > 0x7FFFFFFF) )
    {
      v113 = 1;
    }
    v112 -= v117;
  }
  if ( v119 == -1 )
    goto LABEL_102;
  if ( !v112 && (v18 != 98 || !v17) )
  {
    if ( *(_DWORD *)(v13 + 96) )
      goto LABEL_133;
    v44 = *(_WORD *)(v13 + 50);
    if ( v44 != 1 && v44 != -8 )
      goto LABEL_133;
    v45 = a1;
    v46 = v105;
    if ( v44 == -8 )
    {
      v112 = (unsigned __int8 *)2;
      *(_WORD *)v146 = 0;
    }
    else
    {
      v112 = (unsigned __int8 *)1;
      v146[0] = 0;
    }
    goto LABEL_134;
  }
  if ( *((_WORD *)v121 + 8) != 11 || *(_WORD *)(v13 + 50) != 1 || (v12[50] & 4) == 0 )
    goto LABEL_133;
  v47 = 0;
  if ( (unsigned __int64)(*((_QWORD *)v5 + 5) + 5LL) <= 0x10000 )
    goto LABEL_121;
  if ( WriteFile(*(HANDLE *)v5, *((LPCVOID *)v5 + 3), *((_DWORD *)v5 + 10), &NumberOfBytesWritten, 0) )
  {
    *((_QWORD *)v5 + 5) = 0;
LABEL_121:
    qmemcpy((void *)(*((_QWORD *)v5 + 5) + *((_QWORD *)v5 + 3)), "{ts '", 5);
    *((_QWORD *)v5 + 5) += 5LL;
    *((_QWORD *)v5 + 6) += 5LL;
    goto LABEL_122;
  }
  *((_QWORD *)v5 + 5) = 0x10000;
  v47 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_383B49120[0] )
      bidTraceW(off_383B43238[0], 6652937, off_383B49120[0], 6497);
LABEL_122:
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( !v47 && (bidGblFlags & 0x40) == 0 )
        goto LABEL_133;
      v48 = 6685697;
      if ( v47 )
        v48 = 6685729;
      bidTraceW(off_383B43238[0], v48, off_383B494E8[0], (unsigned int)v47);
    }
  }
  if ( v47 != -1 )
    goto LABEL_133;
  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
    bidTraceW(off_383B43238[0], 7417865, off_383B49120[0], 7244);
  v46 = v105;
  v45 = a1;
  PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
LABEL_134:
  ColumnMetadata = 0;
  v49 = (__int64)v112;
  v114 = (__int64)v112;
  v50 = Src;
  v51 = *((_WORD *)Src + 25);
  if ( v51 == 1 )
  {
    v52 = 1;
  }
  else
  {
    v52 = 0;
    if ( v51 == -8 )
      v52 = 2;
  }
  if ( v112 == (unsigned __int8 *)-4LL || (v53 = v36, v54 = (struct BCPFILE *)(v36 - v52), (__int64)v112 > (__int64)v54) )
  {
    v53 = v36;
    v54 = (struct BCPFILE *)(v36 - v52);
    v118 = v54;
  }
  else
  {
    v118 = (struct BCPFILE *)v112;
  }
  v3 = Src[24];
  if ( (_DWORD)v3 )
  {
    if ( v119 == -1 )
    {
      v55 = bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)v3, (__int64)&qword_383911EF8, v12);
      v57 = v113;
LABEL_191:
      ColumnMetadata = v55;
      goto LABEL_192;
    }
    v57 = v113;
    if ( v113 )
    {
      v122 = 0;
      if ( bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)v3, (__int64)&qword_383911EF0, v12) == -1 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7457801, off_383B49120[0], 7283);
        PostSQLErrorEx(v45, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v46 + 1);
      }
      v58 = 0;
      if ( (unsigned __int64)(*((_QWORD *)v5 + 5) + 4LL) > 0x10000 )
      {
        if ( !WriteFile(*(HANDLE *)v5, *((LPCVOID *)v5 + 3), *((_DWORD *)v5 + 10), &v140, 0) )
        {
          *((_QWORD *)v5 + 5) = 0x10000;
          v58 = -1;
          if ( (bidGblFlags & 2) == 0 )
          {
LABEL_164:
            ColumnMetadata = v58;
LABEL_192:
            if ( ColumnMetadata == -1 )
            {
              if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                bidTraceW(off_383B43238[0], 7485449, off_383B49120[0], 7310);
              v45 = a1;
              PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v46 + 1);
              v49 = v114;
              v50 = Src;
              goto LABEL_205;
            }
            v45 = a1;
            goto LABEL_203;
          }
          if ( off_383B49120[0] )
            bidTraceW(off_383B43238[0], 6652937, off_383B49120[0], 6497);
LABEL_158:
          if ( (bidGblFlags & 2) != 0 )
          {
            v3 = (__int64)off_383B494E8[0];
            if ( v58 || (bidGblFlags & 0x40) != 0 )
            {
              v59 = 6685697;
              if ( v58 )
                v59 = 6685729;
              bidTraceW(off_383B43238[0], v59, off_383B494E8[0], (unsigned int)v58);
            }
          }
          goto LABEL_164;
        }
        *((_QWORD *)v5 + 5) = 0;
      }
      *(_DWORD *)(*((_QWORD *)v5 + 5) + *((_QWORD *)v5 + 3)) = (_DWORD)v118;
      *((_QWORD *)v5 + 5) += 4LL;
      *((_QWORD *)v5 + 6) += 4LL;
      goto LABEL_158;
    }
    v122 = 1;
    if ( v112 == (unsigned __int8 *)-4LL )
      goto LABEL_179;
    if ( (__int64)v112 <= 0 )
    {
LABEL_178:
      v61 = (__int64)v112;
      goto LABEL_189;
    }
    switch ( (_DWORD)v3 )
    {
      case 1:
        v60 = 254;
        break;
      case 2:
        v60 = 65534;
        break;
      case 4:
      case 8:
        v60 = 0x7FFFFFFF;
        break;
      default:
        v60 = 0;
        goto LABEL_177;
    }
    if ( *((_WORD *)Src + 25) == 0xFFF8 )
      v60 &= ~1uLL;
LABEL_177:
    if ( (unsigned __int64)v112 <= v60 )
      goto LABEL_178;
LABEL_179:
    v123 = 1;
    v62 = v3 - 1;
    if ( v62 )
    {
      v63 = v62 - 1;
      if ( v63 )
      {
        v64 = v63 - 2;
        if ( v64 && v64 != 4 )
        {
          v61 = 0;
          goto LABEL_189;
        }
        v61 = 0x7FFFFFFF;
      }
      else
      {
        v61 = 65534;
      }
    }
    else
    {
      v61 = 254;
    }
    v120 = (char *)v61;
    if ( *((_WORD *)Src + 25) != 0xFFF8 )
    {
LABEL_190:
      v129 = v61;
      v55 = bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)Src[24], (__int64)&v129, v12);
      goto LABEL_191;
    }
    v61 &= ~1uLL;
LABEL_189:
    v120 = (char *)v61;
    goto LABEL_190;
  }
  v56 = (unsigned __int8 *)Src[23];
  if ( (int)v56 > 0 && !Src[28] && (__int64)v112 > (__int64)v56 )
  {
    LODWORD(v104) = v46 + 1;
    LODWORD(v103) = Src[23];
    if ( (PostFormattedError(v45, 0xFFFFFFFFFFFFFFFFuLL, v46 + 1, 1, 0x9D41u, v112, v103, v104) & 0xFFFE) != 0 )
    {
      ColumnMetadata = -1;
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7502857, off_383B49120[0], 7327);
      goto LABEL_435;
    }
    v57 = v113;
LABEL_203:
    v49 = v114;
    v50 = Src;
    goto LABEL_205;
  }
  v57 = v113;
LABEL_205:
  if ( !v112 && v50[28] > 0 )
  {
    v65 = v116;
    if ( !*((_DWORD *)v116 + 543) )
    {
      bcpLog(v45, 0x9D68u, v105);
      *((_DWORD *)v65 + 543) = 1;
      v49 = v114;
    }
  }
  v66 = v123;
  while ( 1 )
  {
    if ( (ColumnMetadata & 0xFFFE) != 0 || v49 <= 0 && v49 != -4 )
    {
LABEL_301:
      v76 = v105;
      goto LABEL_302;
    }
    if ( v66 && &v115[(_QWORD)v118] > v120 )
      break;
    ColumnMetadata = bcpWrite((struct tagDBC *)v5, v118, (__int64)&v146[v117], v56);
    if ( ColumnMetadata == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7569417, off_383B49120[0], 7392);
      v76 = v105;
      PostSQLErrorEx(v45, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7570441, off_383B49120[0], 7393);
      goto LABEL_302;
    }
    v115 = &v115[(_QWORD)v118];
    v49 = v114;
    if ( v114 > (__int64)v54 )
      goto LABEL_239;
    if ( v114 == -4 )
      goto LABEL_239;
    v49 = 0;
    v114 = 0;
    if ( !v57 )
      goto LABEL_239;
    v67 = 0;
    if ( (unsigned __int64)(*((_QWORD *)v5 + 5) + 4LL) <= 0x10000 )
      goto LABEL_225;
    if ( WriteFile(*(HANDLE *)v5, *((LPCVOID *)v5 + 3), *((_DWORD *)v5 + 10), &v136, 0) )
    {
      *((_QWORD *)v5 + 5) = 0;
LABEL_225:
      *(_DWORD *)(*((_QWORD *)v5 + 5) + *((_QWORD *)v5 + 3)) = v114;
      *((_QWORD *)v5 + 5) += 4LL;
      *((_QWORD *)v5 + 6) += 4LL;
LABEL_226:
      if ( (bidGblFlags & 2) != 0 )
      {
        v3 = (__int64)off_383B494E8[0];
        if ( v67 || (bidGblFlags & 0x40) != 0 )
        {
          v68 = 6685697;
          if ( v67 )
            v68 = 6685729;
          bidTraceW(off_383B43238[0], v68, off_383B494E8[0], (unsigned int)v67);
        }
      }
      goto LABEL_232;
    }
    *((_QWORD *)v5 + 5) = 0x10000;
    v67 = -1;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49120[0] )
        bidTraceW(off_383B43238[0], 6652937, off_383B49120[0], 6497);
      goto LABEL_226;
    }
LABEL_232:
    ColumnMetadata = v67;
    if ( v67 == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7586825, off_383B49120[0], 7409);
      v45 = a1;
      PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
    }
    else
    {
      v45 = a1;
    }
    v49 = v114;
LABEL_239:
    if ( !ColumnMetadata && (v49 > 0 || v49 == -4) )
    {
      v109 = 0;
      ColumnMetadata = GetColData(
                         *((struct tagSTMT **)v45 + 1003),
                         v146,
                         v53,
                         &v114,
                         &v119,
                         *((_WORD *)Src + 25),
                         v108,
                         0xFFFFFFFF,
                         0,
                         0);
      if ( ColumnMetadata == 1 )
      {
        v69 = *((_QWORD *)v45 + 1003);
        v70 = 0;
        v71 = *(_QWORD *)(v69 + 8);
        if ( v71 )
        {
          v109 = *(_WORD *)(v71 + 8);
        }
        else if ( (*(_BYTE *)(v69 + 24) & 1) != 0 )
        {
          v109 = -25379;
        }
        else
        {
          v70 = 100;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          v3 = (__int64)off_383B494E8[0];
          if ( !v70 && (bidGblFlags & 0x40) == 0 )
          {
LABEL_255:
            v45 = a1;
            if ( v109 == -25126 )
              FreeErrors(*((struct tagOBJBASE **)a1 + 1003));
            goto LABEL_258;
          }
          v72 = 1789953;
          if ( v70 )
            v72 = 1789985;
          bidTraceW(off_383B43210[0], v72, off_383B494E8[0], (unsigned int)v70);
        }
        if ( !v70 )
          goto LABEL_255;
        v45 = a1;
      }
LABEL_258:
      v49 = v114;
      if ( v114 == -4 || (v118 = (struct BCPFILE *)v114, v114 > (__int64)v54) )
        v118 = v54;
      if ( (ColumnMetadata & 0xFFFE) != 0 )
        goto LABEL_301;
      if ( v57 )
      {
        v73 = 0;
        if ( (unsigned __int64)(*((_QWORD *)v5 + 5) + 4LL) <= 0x10000 )
          goto LABEL_269;
        if ( WriteFile(*(HANDLE *)v5, *((LPCVOID *)v5 + 3), *((_DWORD *)v5 + 10), &v139, 0) )
        {
          *((_QWORD *)v5 + 5) = 0;
LABEL_269:
          *(_DWORD *)(*((_QWORD *)v5 + 5) + *((_QWORD *)v5 + 3)) = (_DWORD)v118;
          *((_QWORD *)v5 + 5) += 4LL;
          *((_QWORD *)v5 + 6) += 4LL;
          goto LABEL_270;
        }
        *((_QWORD *)v5 + 5) = 0x10000;
        v73 = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_276;
        if ( off_383B49120[0] )
          bidTraceW(off_383B43238[0], 6652937, off_383B49120[0], 6497);
LABEL_270:
        if ( (bidGblFlags & 2) != 0 )
        {
          v3 = (__int64)off_383B494E8[0];
          if ( v73 || (bidGblFlags & 0x40) != 0 )
          {
            v74 = 6685697;
            if ( v73 )
              v74 = 6685729;
            bidTraceW(off_383B43238[0], v74, off_383B494E8[0], (unsigned int)v73);
          }
        }
LABEL_276:
        ColumnMetadata = v73;
        if ( v73 == -1 )
        {
          if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
            bidTraceW(off_383B43238[0], 7631881, off_383B49120[0], 7453);
          v45 = a1;
          PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
        }
        else
        {
          v45 = a1;
        }
        v49 = v114;
      }
    }
  }
  v75 = v115;
  v118 = (struct BCPFILE *)(v120 - v115);
  ColumnMetadata = bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)(v120 - v115), (__int64)&v146[v117], v56);
  if ( ColumnMetadata == -1 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7540745, off_383B49120[0], 7364);
    v76 = v105;
    PostSQLErrorEx(v45, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7541769, off_383B49120[0], 7365);
    goto LABEL_302;
  }
  v115 = &v75[(_QWORD)v118];
  ColumnMetadata = FlushColData(*((struct tagSTMT **)v45 + 1003), v108 + 1, 0xFFFFFFFF);
  if ( ColumnMetadata == -1 )
  {
    XferErrors(v45, *((struct tagOBJBASE **)v45 + 1003));
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7553033, off_383B49120[0], 7376);
    goto LABEL_435;
  }
  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
    bidTraceW(off_383B43238[0], 7558153, off_383B49120[0], 7381);
  v76 = v105;
  PostSQLErrorEx(v45, 0x9DDAu, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
LABEL_302:
  v77 = v115;
  if ( (ColumnMetadata & 0xFFFE) != 0 || !v122 || v115 == v120 )
  {
    v80 = Src;
LABEL_315:
    v2 = a1;
    v83 = *((_DWORD *)a1 + 2514);
    if ( v83 != v125 )
      v83 = v125;
    *((_DWORD *)a1 + 2514) = v83;
    v84 = v111;
    if ( ColumnMetadata
      || (*(_WORD *)(*((_QWORD *)a1 + 1003) + 264LL) = v111 + 1, v80[24])
      || v80[28]
      || (v85 = v80[23], (__int64)v77 >= (int)(v80[23] - v117)) && v77 )
    {
      v90 = v105;
    }
    else
    {
      v86 = *((__int16 *)v80 + 25);
      if ( v86 == -8 )
      {
        v87 = (__int64 *)L"                              ";
      }
      else
      {
        v87 = qword_383976A58;
        if ( v86 == 1 )
          v87 = (__int64 *)"                              ";
      }
      v88 = (struct BCPFILE *)(v85 - (_QWORD)v77);
      if ( (unsigned __int64)(v85 - (_QWORD)v77) > 0x1E )
      {
        v89 = ((unsigned __int64)v88 - 31) / 0x1E + 1;
        v88 = (struct BCPFILE *)((char *)v88 - 30 * v89);
        do
        {
          ColumnMetadata = bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)0x1E, (__int64)v87, v56);
          --v89;
        }
        while ( v89 );
        v77 = v115;
      }
      if ( v88 )
        ColumnMetadata = bcpWrite((struct tagDBC *)v5, v88, (__int64)v87, v56);
      if ( ColumnMetadata == -1 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 7719945, off_383B49120[0], 7539);
        v90 = v105;
        PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v105 + 1);
      }
      else
      {
        v90 = v105;
      }
      v84 = v111;
    }
    if ( !(unsigned int)BATCHCTX::FIsLenRemaining(v130) )
      *(_WORD *)(*((_QWORD *)a1 + 1003) + 264LL) = v84 + 1;
    if ( ColumnMetadata )
    {
      if ( ColumnMetadata != -1 )
      {
LABEL_367:
        v12 = v116;
        goto LABEL_368;
      }
      goto LABEL_423;
    }
    if ( !v77 || *((_WORD *)v121 + 8) != 11 || *((_WORD *)v80 + 25) != 1 || (v116[50] & 4) == 0 )
    {
LABEL_362:
      if ( v80[28] > 0 )
        ColumnMetadata = bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)v80[28], *((_QWORD *)v80 + 13), v91);
      if ( ColumnMetadata != -1 )
        goto LABEL_367;
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7736329, off_383B49120[0], 7555);
      PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v90 + 1);
LABEL_423:
      FlushColData(*((struct tagSTMT **)a1 + 1003), 0, 0xFFFFFFFF);
      v12 = v116;
      v11 = *((unsigned __int16 *)v116 + 12);
LABEL_424:
      if ( v11 == *((unsigned __int16 *)v12 + 12) )
      {
        v95 = ProcessTDSStream(*((struct tagSTMT **)v2 + 1003), 0x24u, *((_DWORD *)v2 + 2250));
        if ( !ColumnMetadata && v95 == 1 || (ColumnMetadata & 0xFFFE) == 0 && v95 )
          ColumnMetadata = v95;
        v96 = *((_BYTE *)v130 + 48);
        if ( v96 != -47 && v96 != -45 && v96 != -46 )
        {
          *(_DWORD *)(*((_QWORD *)v2 + 1003) + 1484LL) |= 4u;
          CleanUphStmt(*((struct tagSTMT **)v2 + 1003), 0);
        }
      }
      if ( ColumnMetadata != -1 )
        goto LABEL_442;
      goto LABEL_435;
    }
    v92 = 0;
    if ( (unsigned __int64)(*((_QWORD *)v5 + 5) + 2LL) > 0x10000 )
    {
      if ( !WriteFile(*(HANDLE *)v5, *((LPCVOID *)v5 + 3), *((_DWORD *)v5 + 10), &v141, 0) )
      {
        *((_QWORD *)v5 + 5) = 0x10000;
        v92 = -1;
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_361:
          ColumnMetadata = v92;
          goto LABEL_362;
        }
        if ( off_383B49120[0] )
          bidTraceW(off_383B43238[0], 6652937, off_383B49120[0], 6497);
LABEL_355:
        if ( (bidGblFlags & 2) != 0 )
        {
          v3 = (__int64)off_383B494E8[0];
          if ( v92 || (bidGblFlags & 0x40) != 0 )
          {
            v93 = 6685697;
            if ( v92 )
              v93 = 6685729;
            bidTraceW(off_383B43238[0], v93, off_383B494E8[0], (unsigned int)v92);
          }
        }
        goto LABEL_361;
      }
      *((_QWORD *)v5 + 5) = 0;
    }
    *(_WORD *)(*((_QWORD *)v5 + 5) + *((_QWORD *)v5 + 3)) = *(_WORD *)"'}";
    *((_QWORD *)v5 + 5) += 2LL;
    *((_QWORD *)v5 + 6) += 2LL;
    goto LABEL_355;
  }
  v78 = (struct BCPFILE *)*((_QWORD *)v5 + 6);
  ColumnMetadata = bcpWriteSeek((struct tagDBC *)v5, v137, v3);
  if ( ColumnMetadata == -1 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7648265, off_383B49120[0], 7469);
    PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v76 + 1);
  }
  else
  {
    v129 = (__int64)v115;
    v80 = Src;
    if ( bcpWrite((struct tagDBC *)v5, (struct BCPFILE *)Src[24], (__int64)&v129, v79) == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 7661577, off_383B49120[0], 7482);
      v82 = a1;
      PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v76 + 1);
    }
    else
    {
      v82 = a1;
    }
    ColumnMetadata = bcpWriteSeek((struct tagDBC *)v5, v78, v81);
    if ( ColumnMetadata != -1 )
    {
      v77 = v115;
      goto LABEL_315;
    }
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 7667721, off_383B49120[0], 7488);
    PostSQLErrorEx(v82, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v76 + 1);
  }
LABEL_441:
  *v132 = 1;
LABEL_442:
  if ( (bidGblFlags & 2) != 0 && (ColumnMetadata || (bidGblFlags & 0x40) != 0) )
  {
    v97 = 7775233;
    if ( ColumnMetadata )
      v97 = 7775265;
    bidTraceW(off_383B43238[0], v97, off_383B494E8[0], (unsigned int)ColumnMetadata);
  }
  v98 = v135;
  if ( v135 )
  {
    v99 = v134;
    if ( (*(_DWORD *)(v134 + 1120))-- == 1 && !*((_QWORD *)v98 + 12) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v99 + 312) + 32LL) + 8LL))(*(_QWORD *)(v99 + 312) + 32LL);
      BATCHCTX::Release(*(BATCHCTX **)(v99 + 1112));
      *(_QWORD *)(v99 + 1112) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v99 + 312) + 32LL) + 24LL))(*(_QWORD *)(v99 + 312) + 32LL);
    }
  }
  return (unsigned __int16)ColumnMetadata;
}

```

## disassembly

```asm
0x383974c60  push    rbp
0x383974c62  push    rsi
0x383974c63  push    rdi
0x383974c64  push    r12
0x383974c66  push    r13
0x383974c68  push    r14
0x383974c6a  push    r15
0x383974c6c  lea     rbp, [rsp-510h]
0x383974c74  sub     rsp, 610h
0x383974c7b  mov     [rbp+540h+var_4E8], 0FFFFFFFFFFFFFFFEh
0x383974c83  mov     [rsp+640h+arg_10], rbx
0x383974c8b  mov     rax, cs:__security_cookie
0x383974c92  xor     rax, rsp
0x383974c95  mov     [rbp+540h+var_40], rax
0x383974c9c  mov     [rbp+540h+var_530], rdx
0x383974ca0  mov     r12, rcx
0x383974ca3  mov     [rsp+640h+var_5E0], rcx
0x383974ca8  xor     r8d, r8d
0x383974cab  movzx   r14d, r8w
0x383974caf  mov     rax, [rcx+1F70h]
0x383974cb6  mov     [rbp+540h+var_5A0], rax
0x383974cba  mov     ecx, [rcx+2748h]
0x383974cc0  mov     [rbp+540h+var_564], ecx
0x383974cc3  mov     [rbp+540h+var_520], r8
0x383974cc7  mov     [rbp+540h+var_518], r8
0x383974ccb  lea     r13, [rax+688h]
0x383974cd2  mov     [rsp+640h+var_5E8], r13
0x383974cd7  mov     rax, [r13+30h]
0x383974cdb  mov     [rbp+540h+var_500], rax
0x383974cdf  mov     [rdx], r8d
0x383974ce2  mov     rbx, [r12+1F58h]
0x383974cea  mov     esi, r8d
0x383974ced  lea     rdi, [rbx+458h]
0x383974cf4  cmp     [rdi], rsi
0x383974cf7  jnz     short loc_383974D38
0x383974cf9  mov     rcx, [rbx+70h]
0x383974cfd  mov     r8, rdi; struct BATCHCTX **
0x383974d00  mov     rdx, rbx; struct CConnection *
0x383974d03  mov     rcx, [rcx+40h]; this
0x383974d07  call    ?GetNewBatchCtx@CConnection@@QEAAJPEAXPEAPEAVBATCHCTX@@@Z; CConnection::GetNewBatchCtx(void *,BATCHCTX * *)
0x383974d0c  mov     esi, eax
0x383974d0e  test    eax, eax
0x383974d10  jns     short loc_383974D38
0x383974d12  xor     r10d, r10d
0x383974d15  mov     [rbp+540h+var_540], r10
0x383974d19  test    byte ptr cs:_bidGblFlags, 2
0x383974d20  jz      short loc_383974D60
0x383974d22  mov     r8d, eax
0x383974d25  mov     edx, 3C8009h
0x383974d2a  mov     rcx, cs:off_383B43228; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383974d31  call    _bidTraceHR
0x383974d36  jmp     short loc_383974D5D
0x383974d38  mov     rcx, [rdi]
0x383974d3b  mov     [rbp+540h+var_540], rcx
0x383974d3f  mov     rax, [rcx+40h]
0x383974d43  test    byte ptr [rax+190h], 1
0x383974d4a  jz      short loc_383974D5D
0x383974d4c  mov     [rbp+540h+var_520], rbx
0x383974d50  mov     rax, rcx
0x383974d53  mov     [rbp+540h+var_518], rcx
0x383974d57  inc     dword ptr [rbx+460h]
0x383974d5d  xor     r10d, r10d
0x383974d60  test    esi, esi
0x383974d62  jns     short loc_383974DA6
0x383974d64  or      rsi, 0FFFFFFFFFFFFFFFFh
0x383974d68  mov     r14d, esi
0x383974d6b  test    byte ptr cs:_bidGblFlags, 2
0x383974d72  jz      short loc_383974D9E
0x383974d74  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383974d7b  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383974d82  test    rax, rax
0x383974d85  jz      short loc_383974D9E
0x383974d87  mov     r9d, 1AD3h
0x383974d8d  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383974d94  mov     edx, 6B4C09h
0x383974d99  call    _bidTraceW
0x383974d9e  mov     rdi, r13
0x383974da1  jmp     loc_3839768C5
0x383974da6  mov     edx, r10d
0x383974da9  mov     dword ptr [rsp+640h+var_5F0], edx; __int16
0x383974dad  mov     ebx, 0FFFEh
0x383974db2  mov     r9, [rbp+540h+var_5A0]
0x383974db6  cmp     dword ptr [r9+14h], 0
0x383974dbb  jbe     loc_383976845
0x383974dc1  mov     r11d, 0FFFFFFE1h
0x383974dc7  nop     word ptr [rax+rax+00000000h]
0x383974dd0  mov     ebx, edx
0x383974dd2  imul    rbx, 1C0h
0x383974dd9  add     rbx, [r9]
0x383974ddc  mov     [rsp+640h+Src], rbx
0x383974de1  movzx   eax, word ptr [rbx+30h]
0x383974de5  mov     [rsp+640h+var_5C8], ax
0x383974dea  inc     dx
0x383974ded  mov     [rsp+640h+var_5D8], dx
0x383974df2  mov     [rbp+540h+var_5B8], r10d
0x383974df6  test    ax, ax
0x383974df9  jz      loc_3839763B3
0x383974dff  movzx   ecx, ax
0x383974e02  imul    rcx, 258h
0x383974e09  mov     r8, [r9+8]
0x383974e0d  add     r8, 0FFFFFFFFFFFFFDA8h
0x383974e14  add     r8, rcx
0x383974e17  mov     [rbp+540h+var_578], r8
0x383974e1b  mov     rax, [r13+30h]
0x383974e1f  mov     [rbp+540h+var_508], rax
0x383974e23  mov     [rbp+540h+var_570], r10d
0x383974e27  mov     [rbp+540h+var_56C], r10d
0x383974e2b  mov     [rbp+540h+var_580], r10
0x383974e2f  mov     [rbp+540h+var_5A8], r10
0x383974e33  mov     [rbp+540h+var_5C0], r10
0x383974e37  mov     [rbp+540h+var_588], r10
0x383974e3b  mov     [rbp+540h+var_598], r10d
0x383974e3f  mov     r15d, r10d
0x383974e42  movzx   esi, byte ptr [r8+24h]
0x383974e47  mov     byte ptr [rsp+640h+var_5D4], sil
0x383974e4c  movzx   r12d, sil
0x383974e50  movzx   edi, byte ptr [rbx+64h]
0x383974e54  cmp     sil, 62h ; 'b'
0x383974e58  jnz     loc_38397521A
0x383974e5e  xor     eax, eax
0x383974e60  mov     [rbp+540h+var_560], rax
0x383974e64  mov     [rbp+540h+var_558], al
0x383974e67  mov     r13, [r8+30h]
0x383974e6b  mov     rcx, r13; void *
0x383974e6e  mov     rdx, r8; Src
0x383974e71  mov     r8d, 258h; Size
0x383974e77  call    memcpy
0x383974e7c  xor     eax, eax
0x383974e7e  mov     [r13+38h], eax
0x383974e82  mov     [r13+30h], rax
0x383974e86  cmp     edi, 62h ; 'b'
0x383974e89  jnz     loc_383974F32
0x383974e8f  cmp     [rbx+90h], rax
0x383974e96  jnz     short loc_383974EB7
0x383974e98  mov     edx, 1C0h; unsigned __int64
0x383974e9d  mov     rcx, [rsp+640h+var_5E0]; struct tagOBJBASE *
0x383974ea2  call    ?SQLAllocateMemory@@YAPEAXPEAUtagOBJBASE@@_K@Z; SQLAllocateMemory(tagOBJBASE *,unsigned __int64)
0x383974ea7  mov     [rbx+90h], rax
0x383974eae  test    rax, rax
0x383974eb1  jz      loc_3839763CC
0x383974eb7  mov     rbx, [rbx+90h]
0x383974ebe  cmp     qword ptr [rbx+78h], 0
0x383974ec3  jbe     short loc_383974EE2
0x383974ec5  mov     rdx, [rbx+48h]
0x383974ec9  test    rdx, rdx
0x383974ecc  jz      short loc_383974EE2
0x383974ece  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383974ed5  mov     rax, [rcx]
0x383974ed8  call    qword ptr [rax+28h]
0x383974edb  xor     r11d, r11d
0x383974ede  mov     [rbx+48h], r11
0x383974ee2  mov     rdx, [rbx+68h]
0x383974ee6  test    rdx, rdx
0x383974ee9  jz      short loc_383974F09
0x383974eeb  mov     rcx, [rsp+640h+Src]
0x383974ef0  cmp     rdx, [rcx+68h]
0x383974ef4  jz      short loc_383974F09
0x383974ef6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383974efd  mov     rax, [rcx]
0x383974f00  call    qword ptr [rax+28h]
0x383974f03  xor     eax, eax
0x383974f05  mov     [rbx+68h], rax
0x383974f09  mov     rcx, rbx; void *
0x383974f0c  mov     rdx, [rsp+640h+Src]; Src
0x383974f11  mov     r8d, 1C0h; Size
0x383974f17  call    memcpy
0x383974f1c  xor     eax, eax
0x383974f1e  mov     [rbx+68h], rax
0x383974f22  mov     [rbx+70h], eax
0x383974f25  mov     [rbx+98h], eax
0x383974f2b  mov     [rbx+90h], rax
0x383974f32  mov     [rsp+640h+var_5F8], rax; struct tagCOLUMN_INFO *
0x383974f37  mov     [rsp+640h+var_600], eax; int
0x383974f3b  mov     dword ptr [rsp+640h+var_608], 0FFFFFFFFh; unsigned int
0x383974f43  movzx   eax, [rsp+640h+var_5D8]
0x383974f48  mov     [rsp+640h+var_610], ax; unsigned __int16
0x383974f4d  mov     eax, 0FFFFFFFEh
0x383974f52  mov     word ptr [rsp+640h+var_618], ax; __int16
0x383974f57  lea     rax, [rbp+540h+var_588]
0x383974f5b  mov     [rsp+640h+lpOverlapped], rax; __int64 *
0x383974f60  lea     r9, [rbp+540h+var_5C0]; __int64 *
0x383974f64  xor     r8d, r8d; __int64
0x383974f67  lea     rdx, [rbp+540h+var_440]; unsigned __int8 *
0x383974f6e  mov     rax, [rsp+640h+var_5E0]
0x383974f73  mov     rcx, [rax+1F58h]; struct tagSTMT *
0x383974f7a  call    ?GetColData@@YAFPEAUtagSTMT@@PEAE_JPEA_J3FGKHPEAUtagCOLUMN_INFO@@F@Z; GetColData(tagSTMT *,uchar *,__int64,__int64 *,__int64 *,short,ushort,ulong,int,tagCOLUMN_INFO *,short)
0x383974f7f  cmp     ax, 0FFFFh
0x383974f83  jz      loc_3839765B3
0x383974f89  cmp     [rbp+540h+var_588], 0FFFFFFFFFFFFFFFFh
0x383974f8e  jnz     short loc_383974FFC
0x383974f90  mov     r13, [rsp+640h+var_5E8]
0x383974f95  cmp     word ptr [rbx+32h], 0
0x383974f9a  jnz     short loc_383974FC9
0x383974f9c  xor     eax, eax
0x383974f9e  mov     dword ptr [rbp+540h+var_528], eax
0x383974fa1  mov     rax, [rsp+640h+Src]
0x383974fa6  movsxd  rdx, dword ptr [rax+60h]; struct BCPFILE *
0x383974faa  lea     r8, [rbp+540h+var_528]; __int64
0x383974fae  mov     rcx, r13; struct tagDBC *
0x383974fb1  call    ?bcpWrite@@YAFPEAUtagDBC@@PEAUBCPFILE@@_JPEBE@Z; bcpWrite(tagDBC *,BCPFILE *,__int64,uchar const *)
0x383974fb6  cmp     ax, 0FFFFh
0x383974fba  jz      loc_383976414
0x383974fc0  xor     r10d, r10d
0x383974fc3  mov     [rbx+60h], r10d
0x383974fc7  jmp     short loc_383974FCC
0x383974fc9  xor     r10d, r10d
0x383974fcc  cmp     edi, 62h ; 'b'
0x383974fcf  jnz     short loc_383974FE4
0x383974fd1  mov     rcx, [rsp+640h+Src]
0x383974fd6  mov     rax, [rcx+68h]
0x383974fda  mov     [rbx+68h], rax
0x383974fde  mov     eax, [rcx+70h]
0x383974fe1  mov     [rbx+70h], eax
0x383974fe4  movzx   edx, [rsp+640h+var_5D8]
0x383974fe9  mov     r8, [rbp+540h+var_578]
0x383974fed  mov     r9, [rbp+540h+var_5A0]
0x383974ff1  mov     r11d, 0FFFFFFE1h
0x383974ff7  jmp     loc_383975231
0x383974ffc  xor     eax, eax
0x383974ffe  mov     [rbp+540h+var_568], eax
0x383975001  lea     rax, [rbp+540h+var_568]
0x383975005  mov     [rsp+640h+lpOverlapped], rax; unsigned int *
0x38397500a  lea     r9, [rbp+540h+var_4D0]; struct tagCOLUMN_INFO *
0x38397500e  lea     r8, [rbp+540h+var_560]; struct VariantHdr *
0x383975012  movzx   edx, [rsp+640h+var_5D8]; unsigned __int16
0x383975017  mov     rcx, [rsp+640h+var_5E0]; struct tagDBC *
0x38397501c  call    ?GetVariantHdrFromColInfo@@YAFPEAUtagDBC@@GPEAUVariantHdr@@PEAUtagCOLUMN_INFO@@PEAK@Z; GetVariantHdrFromColInfo(tagDBC *,ushort,VariantHdr *,tagCOLUMN_INFO *,ulong *)
0x383975021  movzx   r12d, byte ptr [rbp+540h+var_560]
0x383975026  mov     rdi, [rsp+640h+Src]
0x38397502b  cmp     word ptr [rdi+32h], 0
0x383975030  jnz     loc_3839751FC
0x383975036  cmp     byte ptr [rdi+64h], 62h ; 'b'
0x38397503a  jnz     loc_3839751FC
0x383975040  mov     rax, [rbp+540h+var_578]
0x383975044  mov     dword ptr [rax+38h], 1
0x38397504b  mov     [rbp+540h+var_538], 1
0x383975052  mov     dword ptr [rdi+98h], 1
0x38397505c  lea     r9, [rbp+540h+var_4E0]; unsigned __int64 *
0x383975060  lea     r8, [rbp+540h+var_4D0]; struct tagCOLUMN_INFO *
0x383975064  mov     rdx, r13; struct tagBCPCOL *
0x383975067  mov     rcx, [rsp+640h+var_5E0]; struct tagDBC *
0x38397506c  call    ?bcpGetColumnMetadata@@YAFPEAUtagDBC@@PEAUtagBCPCOL@@PEAUtagCOLUMN_INFO@@PEA_K@Z; bcpGetColumnMetadata(tagDBC *,tagBCPCOL *,tagCOLUMN_INFO *,unsigned __int64 *)
0x383975071  movzx   r14d, ax
0x383975075  cmp     ax, 0FFFFh
0x383975079  jz      loc_383976573
0x38397507f  movzx   r8d, byte ptr [r13+24h]; unsigned __int8
0x383975084  mov     r15d, [rbp+540h+var_568]
0x383975088  mov     rax, [rbp+540h+var_5A0]
0x38397508c  cmp     byte ptr [rax+30h], 64h ; 'd'
0x383975090  jnb     short loc_3839750B2
0x383975092  cmp     r8b, 29h ; ')'
0x383975096  jz      short loc_3839750AA
0x383975098  cmp     r8b, 2Ah ; '*'
0x38397509c  jz      short loc_3839750AA
0x38397509e  cmp     r8b, 2Bh ; '+'
0x3839750a2  jz      short loc_3839750AA
0x3839750a4  cmp     r8b, 28h ; '('
0x3839750a8  jnz     short loc_3839750B2
0x3839750aa  mov     r8b, 0E7h
0x3839750ad  mov     ecx, r15d
0x3839750b0  jmp     short loc_3839750B5
0x3839750b2  or      ecx, 0FFFFFFFFh
0x3839750b5  mov     edx, dword ptr [rsp+640h+var_5F0]
0x3839750b9  inc     edx; int
0x3839750bb  mov     dword ptr [rsp+640h+var_608], edx; char
0x3839750bf  mov     eax, [rdi+70h]
0x3839750c2  mov     dword ptr [rsp+640h+var_610], eax; int
0x3839750c6  mov     rax, [rdi+68h]
0x3839750ca  mov     [rsp+640h+var_618], rax; unsigned __int8 *
0x3839750cf  mov     dword ptr [rsp+640h+lpOverlapped], ecx; int
0x3839750d3  or      r9d, 0FFFFFFFFh; int
0x3839750d7  mov     rcx, [rsp+640h+var_5E0]; struct tagDBC *
0x3839750dc  call    ?BCP_colfmt@@YAFPEAUtagDBC@@HEHJPEBEHH@Z; BCP_colfmt(tagDBC *,int,uchar,int,long,uchar const *,int,int)
0x3839750e1  test    ax, ax
0x3839750e4  jz      loc_383976566
0x3839750ea  movzx   eax, byte ptr [r13+24h]
0x3839750ef  cmp     al, 6Ch ; 'l'
0x3839750f1  jz      short loc_3839750F7
0x3839750f3  cmp     al, 6Ah ; 'j'
0x3839750f5  jnz     short loc_3839750FE
0x3839750f7  mov     [rbp+540h+var_598], 2
0x3839750fe  xor     r10d, r10d
0x383975101  mov     [rbx+60h], r10d
0x383975105  mov     eax, [r13+48h]
0x383975109  mov     [rbx+0A0h], eax
0x38397510f  movzx   eax, byte ptr [r13+4Ch]
0x383975114  mov     [rbx+0A4h], al
0x38397511a  test    r12b, r12b
0x38397511d  jz      loc_3839751B7
0x383975123  movzx   edi, byte ptr [rbp+540h+var_560+1]
0x383975127  add     edi, 2
0x38397512a  mov     rax, [rsp+640h+Src]
0x38397512f  mov     ecx, [rax+60h]
0x383975132  add     ecx, edi
0x383975134  cmp     ecx, edi
0x383975136  jb      loc_3839764A7
0x38397513c  mov     r14d, ecx
0x38397513f  mov     edx, ecx; unsigned __int64
0x383975141  mov     rcx, [rsp+640h+var_5E0]; struct tagOBJBASE *
0x383975146  call    ?SQLAllocateMemory@@YAPEAXPEAUtagOBJBASE@@_K@Z; SQLAllocateMemory(tagOBJBASE *,unsigned __int64)
  ... truncated ...
```
