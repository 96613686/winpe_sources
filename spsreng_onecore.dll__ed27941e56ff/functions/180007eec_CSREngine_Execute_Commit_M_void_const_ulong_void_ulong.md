# CSREngine::Execute_Commit_M(void const *,ulong,void * *,ulong *)

- ea: `0x180007eec`
- end: `0x180008d63`
- name: `?Execute_Commit_M@CSREngine@@QEAAJPEBXKPEAPEAXPEAK@Z`
- size: `3703`
- prototype: `__int64 __fastcall(CHistory **this, _DWORD *, __int64, void **)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ed20`

## callees

- `0x180002db8`
- `0x180002e00`
- `0x1800034b0`
- `0x1800040b8`
- `0x180004a80`
- `0x18000614c`
- `0x1800061d0`
- `0x180006684`
- `0x180006e94`
- `0x180007378`
- `0x180007eec`
- `0x18000a540`
- `0x18000dbe0`
- `0x18000dd54`
- `0x18001cc40`
- `0x180082988`
- `0x1800835e8`
- `0x180083838`
- `0x180083a54`
- `0x1800c77ac`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000828c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008317`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000828c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008317`

## string_xrefs

- `0x180008cf2`: `  CacheUnigramUpdated`
- `0x180008d4a`: `Commit  Reco %08x  LatticeSize %d  SymbolsSize %d  HistoryDepth %d\n  Range %04x  SLM %04x  TB %04x  Replace %04x  Elements %d  Requested %d  NewElements %d%s\n`

## pseudocode

```c
__int64 __fastcall CSREngine::Execute_Commit_M(CHistory **this, _DWORD *a2, __int64 a3, void **a4)
{
  CHistory **v5; // rdi
  ISpPhrase *v6; // r14
  int *v7; // r12
  ULONG v8; // esi
  int v9; // r13d
  struct LATTICE_HEADER *v10; // r15
  char *v11; // rbx
  __int64 v12; // r12
  LPVOID v13; // rcx
  LPVOID v14; // rbx
  unsigned __int64 v15; // r12
  int v16; // ecx
  struct CRecentReco *RecentReco; // rax
  unsigned int v18; // r8d
  int *v19; // r10
  struct CRecentReco *v20; // rbx
  unsigned __int64 v21; // r9
  __int64 v22; // rax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  LPVOID v28; // rdx
  unsigned int v29; // r14d
  ULONG v30; // r15d
  int v31; // r15d
  unsigned int v32; // r14d
  int v33; // r8d
  struct CSRTopicSLM *v34; // r13
  __int64 v35; // r15
  unsigned int v36; // r8d
  unsigned __int64 v37; // rcx
  int v38; // ebx
  int v39; // r15d
  int v40; // r13d
  int v41; // r12d
  unsigned int v42; // ecx
  __int64 i; // rdx
  unsigned int v44; // eax
  int v45; // r8d
  struct LATTICE_NODE *v46; // rcx
  unsigned int v47; // r10d
  __int64 v48; // r9
  __int64 v49; // r11
  unsigned int v50; // ecx
  const wchar_t *v51; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v53[2]; // [rsp+28h] [rbp-D8h]
  __int64 v54; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v55; // [rsp+38h] [rbp-C8h]
  __int64 v56; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v57; // [rsp+48h] [rbp-B8h]
  __int64 v58; // [rsp+50h] [rbp-B0h]
  struct CSRTopicSLM *v59; // [rsp+58h] [rbp-A8h]
  bool *v60; // [rsp+60h] [rbp-A0h]
  char v61; // [rsp+70h] [rbp-90h]
  bool v62; // [rsp+71h] [rbp-8Fh] BYREF
  char v63; // [rsp+72h] [rbp-8Eh]
  int *v64; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+88h] [rbp-78h]
  unsigned int v67; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v68; // [rsp+90h] [rbp-70h] BYREF
  ISpPhrase *v69; // [rsp+98h] [rbp-68h]
  unsigned int v70; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v72; // [rsp+B0h] [rbp-50h] BYREF
  int v73; // [rsp+B8h] [rbp-48h]
  struct CSRTopicSLM *v74; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v75; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v76; // [rsp+D0h] [rbp-30h] BYREF
  ULONG v77; // [rsp+D8h] [rbp-28h]
  ULONG v78; // [rsp+DCh] [rbp-24h]
  LPVOID v79; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v80; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID v81; // [rsp+F0h] [rbp-10h] BYREF
  struct LATTICE_NODE **v82; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v83; // [rsp+108h] [rbp+8h]
  CSREngine *v84; // [rsp+110h] [rbp+10h]
  tagSPPHRASEALTREQUEST v85; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v86[192]; // [rsp+150h] [rbp+50h] BYREF
  void **v87; // [rsp+210h] [rbp+110h] BYREF
  void *Src; // [rsp+218h] [rbp+118h]
  unsigned int v89; // [rsp+220h] [rbp+120h]
  __int16 v90; // [rsp+228h] [rbp+128h] BYREF
  void **v91; // [rsp+300h] [rbp+200h] BYREF
  __int16 *v92; // [rsp+308h] [rbp+208h]
  unsigned int v93; // [rsp+310h] [rbp+210h]
  __int16 v94; // [rsp+318h] [rbp+218h] BYREF
  void **v95; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int16 *v96; // [rsp+3F8h] [rbp+2F8h]
  unsigned int v97; // [rsp+400h] [rbp+300h]
  __int16 v98; // [rsp+408h] [rbp+308h] BYREF
  void **v99; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int16 *v100; // [rsp+4E8h] [rbp+3E8h]
  unsigned int v101; // [rsp+4F0h] [rbp+3F0h]
  __int16 v102; // [rsp+4F8h] [rbp+3F8h] BYREF
  void **v103; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 *v104; // [rsp+5D8h] [rbp+4D8h]
  unsigned int v105; // [rsp+5E0h] [rbp+4E0h]
  __int16 v106; // [rsp+5E8h] [rbp+4E8h] BYREF
  void **v107; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 *v108; // [rsp+6C8h] [rbp+5C8h]
  unsigned int v109; // [rsp+6D0h] [rbp+5D0h]
  __int16 v110; // [rsp+6D8h] [rbp+5D8h] BYREF
  void **v111; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int16 *v112; // [rsp+7B8h] [rbp+6B8h]
  unsigned int v113; // [rsp+7C0h] [rbp+6C0h]
  __int16 v114; // [rsp+7C8h] [rbp+6C8h] BYREF
  void **v115; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int16 *v116; // [rsp+8A8h] [rbp+7A8h]
  unsigned int v117; // [rsp+8B0h] [rbp+7B0h]
  __int16 v118; // [rsp+8B8h] [rbp+7B8h] BYREF
  void **v119; // [rsp+990h] [rbp+890h] BYREF
  __int16 *v120; // [rsp+998h] [rbp+898h]
  unsigned int v121; // [rsp+9A0h] [rbp+8A0h]
  __int16 v122; // [rsp+9A8h] [rbp+8A8h] BYREF
  void **v123; // [rsp+A80h] [rbp+980h] BYREF
  __int16 *v124; // [rsp+A88h] [rbp+988h]
  unsigned int v125; // [rsp+A90h] [rbp+990h]
  __int16 v126; // [rsp+A98h] [rbp+998h] BYREF
  void **v127; // [rsp+B70h] [rbp+A70h] BYREF
  __int16 *v128; // [rsp+B78h] [rbp+A78h]
  unsigned int v129; // [rsp+B80h] [rbp+A80h]
  __int16 v130; // [rsp+B88h] [rbp+A88h] BYREF
  void **v131; // [rsp+C60h] [rbp+B60h] BYREF
  __int16 *v132; // [rsp+C68h] [rbp+B68h]
  unsigned int v133; // [rsp+C70h] [rbp+B70h]
  __int16 v134; // [rsp+C78h] [rbp+B78h] BYREF
  void **v135; // [rsp+D50h] [rbp+C50h] BYREF
  __int16 *v136; // [rsp+D58h] [rbp+C58h]
  unsigned int v137; // [rsp+D60h] [rbp+C60h]
  __int16 v138; // [rsp+D68h] [rbp+C68h] BYREF
  void **v139; // [rsp+E40h] [rbp+D40h] BYREF
  __int16 *v140; // [rsp+E48h] [rbp+D48h]
  unsigned int v141; // [rsp+E50h] [rbp+D50h]
  __int16 v142; // [rsp+E58h] [rbp+D58h] BYREF
  void **v143; // [rsp+F30h] [rbp+E30h] BYREF
  __int16 *v144; // [rsp+F38h] [rbp+E38h]
  unsigned int v145; // [rsp+F40h] [rbp+E40h]
  __int16 v146; // [rsp+F48h] [rbp+E48h] BYREF
  void **v147; // [rsp+1020h] [rbp+F20h] BYREF
  __int16 *v148; // [rsp+1028h] [rbp+F28h]
  unsigned int v149; // [rsp+1030h] [rbp+F30h]
  __int16 v150; // [rsp+1038h] [rbp+F38h] BYREF
  void **v151; // [rsp+1110h] [rbp+1010h] BYREF
  __int16 *v152; // [rsp+1118h] [rbp+1018h]
  unsigned int v153; // [rsp+1120h] [rbp+1020h]
  __int16 v154; // [rsp+1128h] [rbp+1028h] BYREF
  void **v155; // [rsp+1200h] [rbp+1100h] BYREF
  __int16 *v156; // [rsp+1208h] [rbp+1108h]
  unsigned int v157; // [rsp+1210h] [rbp+1110h]
  __int16 v158; // [rsp+1218h] [rbp+1118h] BYREF
  void **v159; // [rsp+12F0h] [rbp+11F0h] BYREF
  __int16 *v160; // [rsp+12F8h] [rbp+11F8h]
  unsigned int v161; // [rsp+1300h] [rbp+1200h]
  __int16 v162; // [rsp+1308h] [rbp+1208h] BYREF
  void **v163; // [rsp+13E0h] [rbp+12E0h] BYREF
  __int16 *v164; // [rsp+13E8h] [rbp+12E8h]
  unsigned int v165; // [rsp+13F0h] [rbp+12F0h]
  __int16 v166; // [rsp+13F8h] [rbp+12F8h] BYREF

  v5 = this;
  v84 = (CSREngine *)this;
  v117 = 0x80000000;
  v116 = &v118;
  v118 = 0;
  v115 = &CQuickStringW<100>::`vftable';
  v165 = 0x80000000;
  v164 = &v166;
  v166 = 0;
  v163 = &CQuickStringW<100>::`vftable';
  v161 = 0x80000000;
  v160 = &v162;
  v162 = 0;
  v159 = &CQuickStringW<100>::`vftable';
  v113 = 0x80000000;
  v112 = &v114;
  v114 = 0;
  v111 = &CQuickStringW<100>::`vftable';
  v157 = 0x80000000;
  v156 = &v158;
  v158 = 0;
  v155 = &CQuickStringW<100>::`vftable';
  v153 = 0x80000000;
  v152 = &v154;
  v154 = 0;
  v151 = &CQuickStringW<100>::`vftable';
  v109 = 0x80000000;
  v108 = (unsigned __int16 *)&v110;
  v110 = 0;
  v107 = &CQuickStringW<100>::`vftable';
  v149 = 0x80000000;
  v148 = &v150;
  v150 = 0;
  v147 = &CQuickStringW<100>::`vftable';
  v145 = 0x80000000;
  v144 = &v146;
  v146 = 0;
  v143 = &CQuickStringW<100>::`vftable';
  v105 = 0x80000000;
  v104 = (unsigned __int16 *)&v106;
  v106 = 0;
  v103 = &CQuickStringW<100>::`vftable';
  v141 = 0x80000000;
  v140 = &v142;
  v142 = 0;
  v139 = &CQuickStringW<100>::`vftable';
  v137 = 0x80000000;
  v136 = &v138;
  v138 = 0;
  v135 = &CQuickStringW<100>::`vftable';
  v101 = 0x80000000;
  v100 = &v102;
  v102 = 0;
  v99 = &CQuickStringW<100>::`vftable';
  v133 = 0x80000000;
  v132 = &v134;
  v134 = 0;
  v131 = &CQuickStringW<100>::`vftable';
  v129 = 0x80000000;
  v128 = &v130;
  v130 = 0;
  v127 = &CQuickStringW<100>::`vftable';
  v97 = 0x80000000;
  v96 = &v98;
  v98 = 0;
  v95 = &CQuickStringW<100>::`vftable';
  v125 = 0x80000000;
  v124 = &v126;
  v126 = 0;
  v123 = &CQuickStringW<100>::`vftable';
  v121 = 0x80000000;
  v120 = &v122;
  v122 = 0;
  v119 = &CQuickStringW<100>::`vftable';
  v89 = 0x80000000;
  Src = &v90;
  v90 = 0;
  v87 = &CQuickStringW<100>::`vftable';
  v93 = 0x80000000;
  v92 = &v94;
  v94 = 0;
  v91 = &CQuickStringW<100>::`vftable';
  pv = 0;
  v76 = 0;
  *(&v85.ulRequestAltCount + 1) = 0;
  memset(&v85.cbResultExtra + 1, 0, 20);
  v62 = 0;
  v75 = 0;
  memset_0(v86, 0, 0xB8u);
  v6 = 0;
  v65 = 0;
  v7 = 0;
  v64 = 0;
  v82 = 0;
  v77 = a2[1];
  v85.ulStartElement = v77;
  v78 = a2[2];
  v85.cElements = v78;
  v85.ulRequestAltCount = a2[3];
  v8 = a2[4];
  v85.cbResultExtra = v8;
  v9 = a2[5];
  v67 = a2[6];
  v66 = a2[7];
  v73 = a2[8];
  v10 = (struct LATTICE_HEADER *)(a2 + 9);
  v83 = a2 + 9;
  v85.pvResultExtra = a2 + 9;
  v80 = 0;
  v79 = 0;
  if ( CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v80) < 0 )
    goto LABEL_27;
  v11 = (char *)v10 + ((v73 + 7) & 0xFFFFFFF8) + ((v8 + 7) & 0xFFFFFFF8);
  v12 = *(unsigned int *)v11;
  if ( (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v80 + 64LL))(v80, v11) < 0 )
  {
LABEL_26:
    v7 = v64;
LABEL_27:
    v14 = v65;
    goto LABEL_28;
  }
  v13 = v80;
  v69 = (ISpPhrase *)v80;
  v80 = 0;
  v85.pPhrase = v69;
  if ( ((int (__fastcall *)(LPVOID, LPVOID *))v69->lpVtbl->GetPhrase)(v13, &pv) < 0
    || CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v79) < 0
    || (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v79 + 64LL))(v79, &v11[v12]) < 0 )
  {
    goto LABEL_25;
  }
  v14 = v79;
  v65 = v79;
  v79 = 0;
  if ( (*(int (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v65 + 24LL))(v65, &v76) >= 0 )
  {
    v63 = 0;
    v68 = 0;
    v15 = -1;
    if ( !v8 )
    {
      v83 = 0;
      v61 = 1;
      v20 = 0;
      goto LABEL_39;
    }
    ReconstructInternalPointers((struct LATTICE *)v86, v10);
    if ( (int)BuildElementArrays(&v64, &v82, &v75, (struct LATTICE *)v86) >= 0 )
    {
      v61 = 0;
      v16 = 0;
      if ( v75 )
      {
        while ( v64[v16] == v16 )
        {
          if ( ++v16 >= v75 )
            goto LABEL_14;
        }
        v61 = 1;
      }
LABEL_14:
      v81 = (struct _GUID)*((_OWORD *)v10 + 1);
      RecentReco = CHistory::FindRecentReco(v5[119], &v81);
      v20 = RecentReco;
      if ( RecentReco )
        v21 = *((_QWORD *)RecentReco + 5);
      else
        v21 = 0;
      if ( (int)MarkWildCardsAndCancelRecos(&v85, v19, v18, v21) < 0 )
        goto LABEL_25;
      if ( v20 )
      {
        v22 = *((_QWORD *)v20 + 5);
        if ( v22 )
        {
          v63 = *(_BYTE *)(v22 + 552);
          if ( v63 )
          {
            v23 = (unsigned __int16 *)(v22 + 40);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
            if ( v24 )
              v68 = v23;
          }
        }
      }
LABEL_39:
      v28 = v76;
      if ( *((_DWORD *)v76 + 16) )
      {
        do
        {
          CQuickStringW<100>::Append(
            (CQuickStringTBase *)&v87,
            *(_WORD **)(56LL * (unsigned int)v6 + *((_QWORD *)v28 + 13) + 24));
          LODWORD(v6) = (_DWORD)v6 + 1;
          if ( (unsigned int)v6 < *((_DWORD *)pv + 16) )
            CQuickStringW<100>::Append((CQuickStringTBase *)&v87, L" ");
          v28 = v76;
        }
        while ( (unsigned int)v6 < *((_DWORD *)v76 + 16) );
      }
      v29 = *((_DWORD *)v28 + 16);
      if ( v77 + v78 < v29 )
        v29 = v77 + v78;
      v30 = v77;
      if ( v77 < v29 )
      {
        while ( 1 )
        {
          CQuickStringW<100>::Append((CQuickStringTBase *)&v91, *(_WORD **)(56LL * v30++ + *((_QWORD *)v28 + 13) + 24));
          if ( v30 >= v29 )
            break;
          CQuickStringW<100>::Append((CQuickStringTBase *)&v91, L" ");
          v28 = v76;
        }
      }
      if ( (v93 & 0x7FFFFFFF) != 0 )
        (*((void (__fastcall **)(CHistory **, _QWORD, __int16 *, _QWORD, _QWORD, int, int))*v5 + 33))(
          v5,
          0,
          v92,
          v93 & 0x7FFFFFFF,
          0,
          1,
          3);
      v31 = 2;
      if ( v20 && (v89 & 0x7FFFFFFF) != 0 )
      {
        if ( *((_QWORD *)v20 + 10) )
          CSpDynamicString::_free((struct CRecentReco *)((char *)v20 + 80));
        CSpDynamicString::operator=((struct CRecentReco *)((char *)v20 + 80), Src);
      }
      else if ( (v89 & 0x7FFFFFFF) != 0 )
      {
        (*((void (__fastcall **)(CHistory **, _QWORD, void *))*v5 + 33))(v5, 0, Src);
      }
      v32 = -1;
      v73 = -1;
      v33 = v66;
      if ( v67 != 1 || v66 != 1 || !*((_BYTE *)v5 + 424) )
        goto LABEL_88;
      if ( (int)ExtractElementStrings(-2, (__int64)pv, v9, (__int64)&v115, (__int64)&v163, (__int64)&v159) >= 0
        && (int)ExtractElementStrings(-1, (__int64)pv, v9, (__int64)&v111, (__int64)&v155, (__int64)&v151) >= 0
        && (int)ExtractElementStrings(0, (__int64)pv, v9, (__int64)&v107, (__int64)&v147, (__int64)&v143) >= 0
        && (int)ExtractElementStrings(0, (__int64)v76, v9, (__int64)&v103, (__int64)&v139, (__int64)&v135) >= 0
        && (int)ExtractElementStrings(1, (__int64)pv, v9, (__int64)&v99, (__int64)&v131, (__int64)&v127) >= 0
        && (int)ExtractElementStrings(2, (__int64)pv, v9, (__int64)&v95, (__int64)&v123, (__int64)&v119) >= 0 )
      {
        if ( !v63 )
        {
LABEL_87:
          v33 = v66;
LABEL_88:
          LODWORD(v74) = v83[4];
          v70 = v83[9];
          v67 = v83[13];
          if ( v62 )
            v31 = 6;
          LODWORD(v68) = v31;
          if ( v20 )
          {
            v32 = 0;
            do
            {
              v32 += *((_DWORD *)v20 + 18);
              v20 = (struct CRecentReco *)*((_QWORD *)v20 + 3);
            }
            while ( v20 );
            v73 = v32;
          }
          v38 = 0;
          v39 = 0;
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v72 = 0;
          if ( !v61 )
          {
            v72 = v75;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v44 = v75;
              if ( v75 > 0x10 )
                v44 = 16;
              if ( (unsigned int)i >= v44 )
                break;
              v45 = 1 << (15 - i);
              if ( (unsigned int)i >= v77 && (unsigned int)i < v77 + v78 )
                v41 |= v45;
              v46 = v82[i];
              if ( (*((_BYTE *)v46 + 8) & 0x10) != 0 )
                v40 |= v45;
              if ( (*((_DWORD *)v46 + 2) & 0x200) != 0 )
                v39 |= v45;
              v47 = *((_DWORD *)pv + 28);
              if ( v47 )
              {
                v48 = 0;
                v49 = *((_QWORD *)pv + 15);
                while ( 1 )
                {
                  v50 = *(_DWORD *)(v49 + 24 * v48 + 16);
                  if ( (unsigned int)i >= v50 && (unsigned int)i < *(_DWORD *)(v49 + 24 * v48 + 20) + v50 )
                    break;
                  v48 = (unsigned int)(v48 + 1);
                  if ( (unsigned int)v48 >= v47 )
                    goto LABEL_113;
                }
                v38 |= v45;
              }
LABEL_113:
              ;
            }
            v5 = (CHistory **)v84;
            v32 = v73;
            v42 = v72;
            v33 = v66;
          }
          CSREngine::LogSQMEvent(
            (CSREngine *)v5,
            0x73Du,
            9u,
            (unsigned int)v74,
            v70,
            v67,
            v32,
            (unsigned __int16)v40 | (v41 << 16),
            (unsigned __int16)v38 | (v39 << 16),
            v42 << 16,
            v85.ulRequestAltCount << 16,
            (unsigned int)v68 | (v33 << 16));
          v51 = L"  CacheUnigramUpdated";
          if ( !v62 )
            v51 = &word_18010FB50;
          LODWORD(v60) = v66;
          LODWORD(v59) = v85.ulRequestAltCount;
          LODWORD(v58) = v72;
          LODWORD(v57) = v38;
          LODWORD(v56) = v39;
          LODWORD(v55) = v40;
          LODWORD(v54) = v41;
          v53[0] = v32;
          LODWORD(ppv) = v67;
          TraceTag(
            (struct CDebugTag *)&g_tagAlternates,
            L"Commit  Reco %08x  LatticeSize %d  SymbolsSize %d  HistoryDepth %d\n"
             "  Range %04x  SLM %04x  TB %04x  Replace %04x  Elements %d  Requested %d  NewElements %d%s\n",
            (unsigned int)v74,
            v70,
            ppv,
            *(_QWORD *)v53,
            v54,
            v55,
            v56,
            v57,
            v58,
            v59,
            v60,
            v51);
          goto LABEL_25;
        }
        v74 = 0;
        if ( CSREngine::LookupLMATopic((CSREngine *)v5, v68, &v74) >= 0 )
        {
          v34 = v74;
          v35 = (**(__int64 (__fastcall ***)(struct CSRTopicSLM *))v74)(v74);
          if ( !v35 )
            goto LABEL_86;
          v67 = -1;
          v70 = -1;
          v72 = -1;
          if ( (v117 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v68, *((_QWORD *)v5[17] + 57));
            v67 = LwidFromElementStrings((_DWORD)v116, (_DWORD)v164, (_DWORD)v160, (unsigned int)&v68, v35);
          }
          if ( (v113 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v68, *((_QWORD *)v5[17] + 57));
            v70 = LwidFromElementStrings((_DWORD)v112, (_DWORD)v156, (_DWORD)v152, (unsigned int)&v68, v35);
          }
          ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v68, *((_QWORD *)v5[17] + 57));
          LODWORD(v68) = LwidFromElementStrings((_DWORD)v108, (_DWORD)v148, (_DWORD)v144, (unsigned int)&v68, v35);
          ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v74, *((_QWORD *)v5[17] + 57));
          LODWORD(v74) = LwidFromElementStrings((_DWORD)v104, (_DWORD)v140, (_DWORD)v136, (unsigned int)&v74, v35);
          if ( (v101 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v72, *((_QWORD *)v5[17] + 57));
            v72 = LwidFromElementStrings((_DWORD)v100, (_DWORD)v132, (_DWORD)v128, (unsigned int)&v72, v35);
          }
          if ( (v97 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v81, *((_QWORD *)v5[17] + 57));
            v36 = LwidFromElementStrings((_DWORD)v96, (_DWORD)v124, (_DWORD)v120, (unsigned int)&v81, v35);
          }
          else
          {
            v36 = -1;
          }
          v37 = -1;
          do
            ++v37;
          while ( v104[v37] );
          if ( v37 > 0xA )
            LODWORD(v37) = 10;
          do
            ++v15;
          while ( v108[v15] );
          if ( v15 > 0xA )
            LODWORD(v15) = 10;
          if ( CSREngine::AdaptFromCorrection(
                 (CSREngine *)v5,
                 v67,
                 v70,
                 (unsigned int)v68,
                 (unsigned int)v74,
                 v72,
                 v36,
                 v108,
                 v15,
                 v104,
                 v37,
                 v34,
                 &v62) >= 0 )
          {
LABEL_86:
            v31 = 2;
            goto LABEL_87;
          }
        }
      }
LABEL_25:
      v6 = v69;
      goto LABEL_26;
    }
  }
  v6 = v69;
  v7 = v64;
LABEL_28:
  if ( v6 )
    ((void (__fastcall *)(ISpPhrase *))v6->lpVtbl->Release)(v6);
  CoTaskMemFree(pv);
  if ( v14 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  CoTaskMemFree(v76);
  if ( v7 )
    operator delete(v7);
  if ( v82 )
    operator delete(v82);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v79, v25);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v80, v26);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v91);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v87);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v119);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v123);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v95);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v127);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v131);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v99);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v135);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v139);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v103);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v143);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v147);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v107);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v151);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v155);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v111);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v159);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v163);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v115);
  return 0;
}

```

## disassembly

```asm
0x180007eec  mov     [rsp-8+arg_10], rbx
0x180007ef1  push    rbp
0x180007ef2  push    rsi
0x180007ef3  push    rdi
0x180007ef4  push    r12
0x180007ef6  push    r13
0x180007ef8  push    r14
0x180007efa  push    r15
0x180007efc  lea     rbp, [rsp-13E0h]
0x180007f04  mov     eax, 14E0h
0x180007f09  call    _alloca_probe
0x180007f0e  sub     rsp, rax
0x180007f11  mov     rax, cs:__security_cookie
0x180007f18  xor     rax, rsp
0x180007f1b  mov     [rbp+1410h+var_40], rax
0x180007f22  mov     rbx, rdx
0x180007f25  mov     rdi, rcx
0x180007f28  mov     [rbp+1410h+var_1400], rcx
0x180007f2c  mov     edx, 80000000h
0x180007f31  mov     [rbp+1410h+var_C60], edx
0x180007f37  lea     rax, [rbp+1410h+var_C58]
0x180007f3e  mov     [rbp+1410h+var_C68], rax
0x180007f45  xor     esi, esi
0x180007f47  mov     [rbp+1410h+var_C58], si
0x180007f4e  lea     rcx, ??_7?$CQuickStringW@$0GE@@@6B@; const CQuickStringW<100>::`vftable'
0x180007f55  mov     [rbp+1410h+var_C70], rcx
0x180007f5c  mov     [rbp+1410h+var_120], edx
0x180007f62  lea     rax, [rbp+1410h+var_118]
0x180007f69  mov     [rbp+1410h+var_128], rax
0x180007f70  mov     [rbp+1410h+var_118], si
0x180007f77  mov     [rbp+1410h+var_130], rcx
0x180007f7e  mov     [rbp+1410h+var_210], edx
0x180007f84  lea     rax, [rbp+1410h+var_208]
0x180007f8b  mov     [rbp+1410h+var_218], rax
0x180007f92  mov     [rbp+1410h+var_208], si
0x180007f99  mov     [rbp+1410h+var_220], rcx
0x180007fa0  mov     [rbp+1410h+var_D50], edx
0x180007fa6  lea     rax, [rbp+1410h+var_D48]
0x180007fad  mov     [rbp+1410h+var_D58], rax
0x180007fb4  mov     [rbp+1410h+var_D48], si
0x180007fbb  mov     [rbp+1410h+var_D60], rcx
0x180007fc2  mov     [rbp+1410h+var_300], edx
0x180007fc8  lea     rax, [rbp+1410h+var_2F8]
0x180007fcf  mov     [rbp+1410h+var_308], rax
0x180007fd6  mov     [rbp+1410h+var_2F8], si
0x180007fdd  mov     [rbp+1410h+var_310], rcx
0x180007fe4  mov     [rbp+1410h+var_3F0], edx
0x180007fea  lea     rax, [rbp+1410h+var_3E8]
0x180007ff1  mov     [rbp+1410h+var_3F8], rax
0x180007ff8  mov     [rbp+1410h+var_3E8], si
0x180007fff  mov     [rbp+1410h+var_400], rcx
0x180008006  mov     [rbp+1410h+var_E40], edx
0x18000800c  lea     rax, [rbp+1410h+var_E38]
0x180008013  mov     [rbp+1410h+var_E48], rax
0x18000801a  mov     [rbp+1410h+var_E38], si
0x180008021  mov     [rbp+1410h+var_E50], rcx
0x180008028  mov     [rbp+1410h+var_4E0], edx
0x18000802e  lea     rax, [rbp+1410h+var_4D8]
0x180008035  mov     [rbp+1410h+var_4E8], rax
0x18000803c  mov     [rbp+1410h+var_4D8], si
0x180008043  mov     [rbp+1410h+var_4F0], rcx
0x18000804a  mov     [rbp+1410h+var_5D0], edx
0x180008050  lea     rax, [rbp+1410h+var_5C8]
0x180008057  mov     [rbp+1410h+var_5D8], rax
0x18000805e  mov     [rbp+1410h+var_5C8], si
0x180008065  mov     [rbp+1410h+var_5E0], rcx
0x18000806c  mov     [rbp+1410h+var_F30], edx
0x180008072  lea     rax, [rbp+1410h+var_F28]
0x180008079  mov     [rbp+1410h+var_F38], rax
0x180008080  mov     [rbp+1410h+var_F28], si
0x180008087  mov     [rbp+1410h+var_F40], rcx
0x18000808e  mov     [rbp+1410h+var_6C0], edx
0x180008094  lea     rax, [rbp+1410h+var_6B8]
0x18000809b  mov     [rbp+1410h+var_6C8], rax
0x1800080a2  mov     [rbp+1410h+var_6B8], si
0x1800080a9  mov     [rbp+1410h+var_6D0], rcx
0x1800080b0  mov     [rbp+1410h+var_7B0], edx
0x1800080b6  lea     rax, [rbp+1410h+var_7A8]
0x1800080bd  mov     [rbp+1410h+var_7B8], rax
0x1800080c4  mov     [rbp+1410h+var_7A8], si
0x1800080cb  mov     [rbp+1410h+var_7C0], rcx
0x1800080d2  mov     [rbp+1410h+var_1020], edx
0x1800080d8  lea     rax, [rbp+1410h+var_1018]
0x1800080df  mov     [rbp+1410h+var_1028], rax
0x1800080e6  mov     [rbp+1410h+var_1018], si
0x1800080ed  mov     [rbp+1410h+var_1030], rcx
0x1800080f4  mov     [rbp+1410h+var_8A0], edx
0x1800080fa  lea     rax, [rbp+1410h+var_898]
0x180008101  mov     [rbp+1410h+var_8A8], rax
0x180008108  mov     [rbp+1410h+var_898], si
0x18000810f  mov     [rbp+1410h+var_8B0], rcx
0x180008116  mov     [rbp+1410h+var_990], edx
0x18000811c  lea     rax, [rbp+1410h+var_988]
0x180008123  mov     [rbp+1410h+var_998], rax
0x18000812a  mov     [rbp+1410h+var_988], si
0x180008131  mov     [rbp+1410h+var_9A0], rcx
0x180008138  mov     [rbp+1410h+var_1110], edx
0x18000813e  lea     rax, [rbp+1410h+var_1108]
0x180008145  mov     [rbp+1410h+var_1118], rax
0x18000814c  mov     [rbp+1410h+var_1108], si
0x180008153  mov     [rbp+1410h+var_1120], rcx
0x18000815a  mov     [rbp+1410h+var_A80], edx
0x180008160  lea     rax, [rbp+1410h+var_A78]
0x180008167  mov     [rbp+1410h+var_A88], rax
0x18000816e  mov     [rbp+1410h+var_A78], si
0x180008175  mov     [rbp+1410h+var_A90], rcx
0x18000817c  mov     [rbp+1410h+var_B70], edx
0x180008182  lea     rax, [rbp+1410h+var_B68]
0x180008189  mov     [rbp+1410h+var_B78], rax
0x180008190  mov     [rbp+1410h+var_B68], si
0x180008197  mov     [rbp+1410h+var_B80], rcx
0x18000819e  mov     [rbp+1410h+var_12F0], edx
0x1800081a4  lea     rax, [rbp+1410h+var_12E8]
0x1800081ab  mov     [rbp+1410h+Src], rax
0x1800081b2  mov     [rbp+1410h+var_12E8], si
0x1800081b9  mov     [rbp+1410h+var_1300], rcx
0x1800081c0  mov     [rbp+1410h+var_1200], edx
0x1800081c6  lea     rax, [rbp+1410h+var_11F8]
0x1800081cd  mov     [rbp+1410h+var_1208], rax
0x1800081d4  mov     [rbp+1410h+var_11F8], si
0x1800081db  mov     [rbp+1410h+var_1210], rcx
0x1800081e2  mov     [rbp+1410h+pv], rsi
0x1800081e6  mov     [rbp+1410h+var_1440], rsi
0x1800081ea  mov     dword ptr [rbp+1410h+var_13F8+0Ch], esi
0x1800081ed  xorps   xmm0, xmm0
0x1800081f0  movdqu  xmmword ptr [rbp+1410h+var_13F8+1Ch], xmm0
0x1800081f5  mov     dword ptr [rbp+1410h+var_13F8.pRecoContext+4], esi
0x1800081f8  mov     [rsp+1510h+var_149F], sil
0x1800081fd  mov     [rbp+1410h+var_1448], esi
0x180008200  xor     edx, edx; Val
0x180008202  mov     r8d, 0B8h; Size
0x180008208  lea     rcx, [rbp+1410h+var_13C0]; void *
0x18000820c  call    memset_0
0x180008211  mov     r14d, esi
0x180008214  mov     [rbp+1410h+var_1490], rsi
0x180008218  mov     r12d, esi
0x18000821b  mov     [rsp+1510h+var_1498], rsi
0x180008220  mov     [rbp+1410h+var_1410], rsi
0x180008224  mov     eax, [rbx+4]
0x180008227  mov     [rbp+1410h+var_1438], eax
0x18000822a  mov     [rbp+1410h+var_13F8.ulStartElement], eax
0x18000822d  mov     eax, [rbx+8]
0x180008230  mov     [rbp+1410h+var_1434], eax
0x180008233  mov     [rbp+1410h+var_13F8.cElements], eax
0x180008236  mov     eax, [rbx+0Ch]
0x180008239  mov     [rbp+1410h+var_13F8.ulRequestAltCount], eax
0x18000823c  mov     esi, [rbx+10h]
0x18000823f  mov     [rbp+1410h+var_13F8.cbResultExtra], esi
0x180008242  mov     r13d, [rbx+14h]
0x180008246  mov     eax, [rbx+18h]
0x180008249  mov     [rbp+1410h+var_1484], eax
0x18000824c  mov     eax, [rbx+1Ch]
0x18000824f  mov     [rbp+1410h+var_1488], eax
0x180008252  mov     eax, [rbx+20h]
0x180008255  mov     [rbp+1410h+var_1458], eax
0x180008258  lea     r15, [rbx+24h]
0x18000825c  mov     [rbp+1410h+var_1408], r15
0x180008260  mov     [rbp+1410h+var_13F8.pvResultExtra], r15
0x180008264  xor     ebx, ebx
0x180008266  mov     [rbp+1410h+var_1428], rbx
0x18000826a  mov     [rbp+1410h+var_1430], rbx
0x18000826e  lea     rax, [rbp+1410h+var_1428]
0x180008272  mov     [rsp+1510h+ppv], rax; ppv
0x180008277  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x18000827e  xor     edx, edx; pUnkOuter
0x180008280  lea     r8d, [r12+17h]; dwClsContext
0x180008285  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x18000828c  call    cs:__imp_CoCreateInstance
0x180008292  test    eax, eax
0x180008294  js      loc_180008466
0x18000829a  mov     eax, [rbp+1410h+var_1458]
0x18000829d  add     eax, 7
0x1800082a0  mov     edx, 0FFFFFFF8h
0x1800082a5  and     rax, rdx
0x1800082a8  lea     ebx, [rsi+7]
0x1800082ab  and     rbx, rdx
0x1800082ae  add     rax, r15
0x1800082b1  add     rbx, rax
0x1800082b4  mov     r12d, [rbx]
0x1800082b7  mov     rcx, [rbp+1410h+var_1428]
0x1800082bb  mov     rax, [rcx]
0x1800082be  mov     rdx, rbx
0x1800082c1  mov     rax, [rax+40h]
0x1800082c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ca  test    eax, eax
0x1800082cc  js      loc_180008461
0x1800082d2  mov     rcx, [rbp+1410h+var_1428]
0x1800082d6  mov     [rbp+1410h+var_1478], rcx
0x1800082da  mov     [rbp+1410h+var_1428], r14
0x1800082de  mov     [rbp+1410h+var_13F8.pPhrase], rcx
0x1800082e2  mov     rax, [rcx]
0x1800082e5  lea     rdx, [rbp+1410h+pv]
0x1800082e9  mov     rax, [rax+18h]
0x1800082ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f2  test    eax, eax
0x1800082f4  js      loc_18000845D
0x1800082fa  lea     rax, [rbp+1410h+var_1430]
0x1800082fe  mov     [rsp+1510h+ppv], rax; ppv
0x180008303  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x18000830a  xor     edx, edx; pUnkOuter
0x18000830c  lea     r8d, [r14+17h]; dwClsContext
0x180008310  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x180008317  call    cs:__imp_CoCreateInstance
0x18000831d  test    eax, eax
0x18000831f  js      loc_18000845D
0x180008325  mov     rcx, [rbp+1410h+var_1430]
0x180008329  mov     rax, [rcx]
0x18000832c  lea     rdx, [rbx+r12]
0x180008330  mov     rax, [rax+40h]
0x180008334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008339  test    eax, eax
0x18000833b  js      loc_18000845D
0x180008341  mov     rbx, [rbp+1410h+var_1430]
0x180008345  mov     [rbp+1410h+var_1490], rbx
0x180008349  mov     [rbp+1410h+var_1430], r14
0x18000834d  mov     rax, [rbx]
0x180008350  lea     rdx, [rbp+1410h+var_1440]
0x180008354  mov     rcx, rbx
0x180008357  mov     rax, [rax+18h]
0x18000835b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008360  test    eax, eax
0x180008362  js      loc_180008605
0x180008368  mov     [rsp+1510h+var_149E], r14b
0x18000836d  mov     [rbp+1410h+var_1480], r14
0x180008371  or      r12, 0FFFFFFFFFFFFFFFFh
0x180008375  test    esi, esi
0x180008377  jz      loc_180008613
0x18000837d  mov     rdx, r15; struct LATTICE_HEADER *
0x180008380  lea     rcx, [rbp+1410h+var_13C0]; struct LATTICE *
0x180008384  call    ?ReconstructInternalPointers@@YAXPEAULATTICE@@PEAULATTICE_HEADER@@@Z; ReconstructInternalPointers(LATTICE *,LATTICE_HEADER *)
0x180008389  lea     r9, [rbp+1410h+var_13C0]; struct LATTICE *
0x18000838d  lea     r8, [rbp+1410h+var_1448]; unsigned int *
0x180008391  lea     rdx, [rbp+1410h+var_1410]; struct LATTICE_NODE ***
0x180008395  lea     rcx, [rsp+1510h+var_1498]; int **
0x18000839a  call    ?BuildElementArrays@@YAJPEAPEAHPEAPEAPEAULATTICE_NODE@@PEAKPEAULATTICE@@@Z; BuildElementArrays(int * *,LATTICE_NODE * * *,ulong *,LATTICE *)
0x18000839f  test    eax, eax
0x1800083a1  js      loc_180008605
0x1800083a7  mov     [rsp+1510h+var_14A0], r14b
0x1800083ac  mov     ecx, r14d
0x1800083af  lea     esi, [r14+1]
0x1800083b3  mov     r8d, [rbp+1410h+var_1448]
0x1800083b7  mov     r10, [rsp+1510h+var_1498]
0x1800083bc  test    r8d, r8d
0x1800083bf  jz      short loc_1800083D7
0x1800083c1  mov     eax, ecx
0x1800083c3  cmp     [r10+rax*4], ecx
0x1800083c7  jnz     short loc_1800083D2
0x1800083c9  add     ecx, esi
0x1800083cb  cmp     ecx, r8d
0x1800083ce  jb      short loc_1800083C1
0x1800083d0  jmp     short loc_1800083D7
0x1800083d2  mov     [rsp+1510h+var_14A0], sil
0x1800083d7  movups  xmm0, xmmword ptr [r15+10h]
0x1800083dc  movdqu  xmmword ptr [rbp+1410h+var_1420.Data1], xmm0
0x1800083e1  lea     rdx, [rbp+1410h+var_1420]; struct _GUID
0x1800083e5  mov     rcx, [rdi+3B8h]; this
0x1800083ec  call    ?FindRecentReco@CHistory@@QEAAPEAVCRecentReco@@U_GUID@@@Z; CHistory::FindRecentReco(_GUID)
0x1800083f1  mov     rbx, rax
0x1800083f4  test    rax, rax
0x1800083f7  jz      short loc_1800083FF
0x1800083f9  mov     r9, [rax+28h]
0x1800083fd  jmp     short loc_180008402
0x1800083ff  mov     r9, r14; struct CStreamPair *
0x180008402  mov     rdx, r10; int *
0x180008405  lea     rcx, [rbp+1410h+var_13F8]; struct tagSPPHRASEALTREQUEST *
0x180008409  call    ?MarkWildCardsAndCancelRecos@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAHKPEAVCStreamPair@@@Z; MarkWildCardsAndCancelRecos(tagSPPHRASEALTREQUEST *,int *,ulong,CStreamPair *)
0x18000840e  test    eax, eax
0x180008410  js      short loc_18000845D
0x180008412  test    rbx, rbx
0x180008415  jz      loc_180008624
0x18000841b  mov     rax, [rbx+28h]
0x18000841f  test    rax, rax
0x180008422  jz      loc_180008624
0x180008428  mov     cl, [rax+228h]
0x18000842e  mov     [rsp+1510h+var_149E], cl
0x180008432  test    cl, cl
0x180008434  jz      loc_180008624
0x18000843a  lea     rcx, [rax+28h]
0x18000843e  mov     rax, r12
0x180008441  inc     rax
0x180008444  cmp     [rcx+rax*2], r14w
0x180008449  jnz     short loc_180008441
0x18000844b  test    rax, rax
0x18000844e  jz      loc_180008624
0x180008454  mov     [rbp+1410h+var_1480], rcx
0x180008458  jmp     loc_180008624
0x18000845d  mov     r14, [rbp+1410h+var_1478]
0x180008461  mov     r12, [rsp+1510h+var_1498]
0x180008466  mov     rbx, [rbp+1410h+var_1490]
0x18000846a  test    r14, r14
0x18000846d  jz      short loc_18000847E
0x18000846f  mov     rax, [r14]
0x180008472  mov     rcx, r14
0x180008475  mov     rax, [rax+10h]
0x180008479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000847e  mov     rcx, [rbp+1410h+pv]; pv
0x180008482  call    cs:__imp_CoTaskMemFree
0x180008488  test    rbx, rbx
0x18000848b  jz      short loc_18000849C
0x18000848d  mov     rax, [rbx]
  ... truncated ...
```
