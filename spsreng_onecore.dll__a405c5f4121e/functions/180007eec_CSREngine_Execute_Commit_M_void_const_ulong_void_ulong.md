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
  struct CStreamPair *v21; // r9
  __int64 v22; // rax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rax
  LPVOID v26; // rdx
  unsigned int v27; // r14d
  ULONG v28; // r15d
  int v29; // r15d
  unsigned int v30; // r14d
  int v31; // r8d
  struct CSRTopicSLM *v32; // r13
  __int64 v33; // r15
  unsigned int v34; // r8d
  unsigned __int64 v35; // rcx
  int v36; // ebx
  int v37; // r15d
  int v38; // r13d
  int v39; // r12d
  unsigned int v40; // ecx
  __int64 i; // rdx
  unsigned int v42; // eax
  int v43; // r8d
  struct LATTICE_NODE *v44; // rcx
  unsigned int v45; // r10d
  __int64 v46; // r9
  __int64 v47; // r11
  unsigned int v48; // ecx
  const wchar_t *v49; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v51[2]; // [rsp+28h] [rbp-D8h]
  __int64 v52; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v53; // [rsp+38h] [rbp-C8h]
  __int64 v54; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v55; // [rsp+48h] [rbp-B8h]
  __int64 v56; // [rsp+50h] [rbp-B0h]
  struct CSRTopicSLM *v57; // [rsp+58h] [rbp-A8h]
  bool *v58; // [rsp+60h] [rbp-A0h]
  char v59; // [rsp+70h] [rbp-90h]
  bool v60; // [rsp+71h] [rbp-8Fh] BYREF
  char v61; // [rsp+72h] [rbp-8Eh]
  int *v62; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v63; // [rsp+80h] [rbp-80h]
  int v64; // [rsp+88h] [rbp-78h]
  unsigned int v65; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v66; // [rsp+90h] [rbp-70h] BYREF
  ISpPhrase *v67; // [rsp+98h] [rbp-68h]
  unsigned int v68; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B8h] [rbp-48h]
  struct CSRTopicSLM *v72; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v73; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v74; // [rsp+D0h] [rbp-30h] BYREF
  ULONG v75; // [rsp+D8h] [rbp-28h]
  ULONG v76; // [rsp+DCh] [rbp-24h]
  LPVOID v77; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v78; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID v79; // [rsp+F0h] [rbp-10h] BYREF
  struct LATTICE_NODE **v80; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v81; // [rsp+108h] [rbp+8h]
  CSREngine *v82; // [rsp+110h] [rbp+10h]
  tagSPPHRASEALTREQUEST v83; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v84[192]; // [rsp+150h] [rbp+50h] BYREF
  void **v85; // [rsp+210h] [rbp+110h] BYREF
  void *Src; // [rsp+218h] [rbp+118h]
  unsigned int v87; // [rsp+220h] [rbp+120h]
  __int16 v88; // [rsp+228h] [rbp+128h] BYREF
  void **v89; // [rsp+300h] [rbp+200h] BYREF
  __int16 *v90; // [rsp+308h] [rbp+208h]
  unsigned int v91; // [rsp+310h] [rbp+210h]
  __int16 v92; // [rsp+318h] [rbp+218h] BYREF
  void **v93; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int16 *v94; // [rsp+3F8h] [rbp+2F8h]
  unsigned int v95; // [rsp+400h] [rbp+300h]
  __int16 v96; // [rsp+408h] [rbp+308h] BYREF
  void **v97; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int16 *v98; // [rsp+4E8h] [rbp+3E8h]
  unsigned int v99; // [rsp+4F0h] [rbp+3F0h]
  __int16 v100; // [rsp+4F8h] [rbp+3F8h] BYREF
  void **v101; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 *v102; // [rsp+5D8h] [rbp+4D8h]
  unsigned int v103; // [rsp+5E0h] [rbp+4E0h]
  __int16 v104; // [rsp+5E8h] [rbp+4E8h] BYREF
  void **v105; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 *v106; // [rsp+6C8h] [rbp+5C8h]
  unsigned int v107; // [rsp+6D0h] [rbp+5D0h]
  __int16 v108; // [rsp+6D8h] [rbp+5D8h] BYREF
  void **v109; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int16 *v110; // [rsp+7B8h] [rbp+6B8h]
  unsigned int v111; // [rsp+7C0h] [rbp+6C0h]
  __int16 v112; // [rsp+7C8h] [rbp+6C8h] BYREF
  void **v113; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int16 *v114; // [rsp+8A8h] [rbp+7A8h]
  unsigned int v115; // [rsp+8B0h] [rbp+7B0h]
  __int16 v116; // [rsp+8B8h] [rbp+7B8h] BYREF
  void **v117; // [rsp+990h] [rbp+890h] BYREF
  __int16 *v118; // [rsp+998h] [rbp+898h]
  unsigned int v119; // [rsp+9A0h] [rbp+8A0h]
  __int16 v120; // [rsp+9A8h] [rbp+8A8h] BYREF
  void **v121; // [rsp+A80h] [rbp+980h] BYREF
  __int16 *v122; // [rsp+A88h] [rbp+988h]
  unsigned int v123; // [rsp+A90h] [rbp+990h]
  __int16 v124; // [rsp+A98h] [rbp+998h] BYREF
  void **v125; // [rsp+B70h] [rbp+A70h] BYREF
  __int16 *v126; // [rsp+B78h] [rbp+A78h]
  unsigned int v127; // [rsp+B80h] [rbp+A80h]
  __int16 v128; // [rsp+B88h] [rbp+A88h] BYREF
  void **v129; // [rsp+C60h] [rbp+B60h] BYREF
  __int16 *v130; // [rsp+C68h] [rbp+B68h]
  unsigned int v131; // [rsp+C70h] [rbp+B70h]
  __int16 v132; // [rsp+C78h] [rbp+B78h] BYREF
  void **v133; // [rsp+D50h] [rbp+C50h] BYREF
  __int16 *v134; // [rsp+D58h] [rbp+C58h]
  unsigned int v135; // [rsp+D60h] [rbp+C60h]
  __int16 v136; // [rsp+D68h] [rbp+C68h] BYREF
  void **v137; // [rsp+E40h] [rbp+D40h] BYREF
  __int16 *v138; // [rsp+E48h] [rbp+D48h]
  unsigned int v139; // [rsp+E50h] [rbp+D50h]
  __int16 v140; // [rsp+E58h] [rbp+D58h] BYREF
  void **v141; // [rsp+F30h] [rbp+E30h] BYREF
  __int16 *v142; // [rsp+F38h] [rbp+E38h]
  unsigned int v143; // [rsp+F40h] [rbp+E40h]
  __int16 v144; // [rsp+F48h] [rbp+E48h] BYREF
  void **v145; // [rsp+1020h] [rbp+F20h] BYREF
  __int16 *v146; // [rsp+1028h] [rbp+F28h]
  unsigned int v147; // [rsp+1030h] [rbp+F30h]
  __int16 v148; // [rsp+1038h] [rbp+F38h] BYREF
  void **v149; // [rsp+1110h] [rbp+1010h] BYREF
  __int16 *v150; // [rsp+1118h] [rbp+1018h]
  unsigned int v151; // [rsp+1120h] [rbp+1020h]
  __int16 v152; // [rsp+1128h] [rbp+1028h] BYREF
  void **v153; // [rsp+1200h] [rbp+1100h] BYREF
  __int16 *v154; // [rsp+1208h] [rbp+1108h]
  unsigned int v155; // [rsp+1210h] [rbp+1110h]
  __int16 v156; // [rsp+1218h] [rbp+1118h] BYREF
  void **v157; // [rsp+12F0h] [rbp+11F0h] BYREF
  __int16 *v158; // [rsp+12F8h] [rbp+11F8h]
  unsigned int v159; // [rsp+1300h] [rbp+1200h]
  __int16 v160; // [rsp+1308h] [rbp+1208h] BYREF
  void **v161; // [rsp+13E0h] [rbp+12E0h] BYREF
  __int16 *v162; // [rsp+13E8h] [rbp+12E8h]
  unsigned int v163; // [rsp+13F0h] [rbp+12F0h]
  __int16 v164; // [rsp+13F8h] [rbp+12F8h] BYREF

  v5 = this;
  v82 = (CSREngine *)this;
  v115 = 0x80000000;
  v114 = &v116;
  v116 = 0;
  v113 = &CQuickStringW<100>::`vftable';
  v163 = 0x80000000;
  v162 = &v164;
  v164 = 0;
  v161 = &CQuickStringW<100>::`vftable';
  v159 = 0x80000000;
  v158 = &v160;
  v160 = 0;
  v157 = &CQuickStringW<100>::`vftable';
  v111 = 0x80000000;
  v110 = &v112;
  v112 = 0;
  v109 = &CQuickStringW<100>::`vftable';
  v155 = 0x80000000;
  v154 = &v156;
  v156 = 0;
  v153 = &CQuickStringW<100>::`vftable';
  v151 = 0x80000000;
  v150 = &v152;
  v152 = 0;
  v149 = &CQuickStringW<100>::`vftable';
  v107 = 0x80000000;
  v106 = (unsigned __int16 *)&v108;
  v108 = 0;
  v105 = &CQuickStringW<100>::`vftable';
  v147 = 0x80000000;
  v146 = &v148;
  v148 = 0;
  v145 = &CQuickStringW<100>::`vftable';
  v143 = 0x80000000;
  v142 = &v144;
  v144 = 0;
  v141 = &CQuickStringW<100>::`vftable';
  v103 = 0x80000000;
  v102 = (unsigned __int16 *)&v104;
  v104 = 0;
  v101 = &CQuickStringW<100>::`vftable';
  v139 = 0x80000000;
  v138 = &v140;
  v140 = 0;
  v137 = &CQuickStringW<100>::`vftable';
  v135 = 0x80000000;
  v134 = &v136;
  v136 = 0;
  v133 = &CQuickStringW<100>::`vftable';
  v99 = 0x80000000;
  v98 = &v100;
  v100 = 0;
  v97 = &CQuickStringW<100>::`vftable';
  v131 = 0x80000000;
  v130 = &v132;
  v132 = 0;
  v129 = &CQuickStringW<100>::`vftable';
  v127 = 0x80000000;
  v126 = &v128;
  v128 = 0;
  v125 = &CQuickStringW<100>::`vftable';
  v95 = 0x80000000;
  v94 = &v96;
  v96 = 0;
  v93 = &CQuickStringW<100>::`vftable';
  v123 = 0x80000000;
  v122 = &v124;
  v124 = 0;
  v121 = &CQuickStringW<100>::`vftable';
  v119 = 0x80000000;
  v118 = &v120;
  v120 = 0;
  v117 = &CQuickStringW<100>::`vftable';
  v87 = 0x80000000;
  Src = &v88;
  v88 = 0;
  v85 = &CQuickStringW<100>::`vftable';
  v91 = 0x80000000;
  v90 = &v92;
  v92 = 0;
  v89 = &CQuickStringW<100>::`vftable';
  pv = 0;
  v74 = 0;
  *(&v83.ulRequestAltCount + 1) = 0;
  memset(&v83.cbResultExtra + 1, 0, 20);
  v60 = 0;
  v73 = 0;
  memset_0(v84, 0, 0xB8u);
  v6 = 0;
  v63 = 0;
  v7 = 0;
  v62 = 0;
  v80 = 0;
  v75 = a2[1];
  v83.ulStartElement = v75;
  v76 = a2[2];
  v83.cElements = v76;
  v83.ulRequestAltCount = a2[3];
  v8 = a2[4];
  v83.cbResultExtra = v8;
  v9 = a2[5];
  v65 = a2[6];
  v64 = a2[7];
  v71 = a2[8];
  v10 = (struct LATTICE_HEADER *)(a2 + 9);
  v81 = a2 + 9;
  v83.pvResultExtra = a2 + 9;
  v78 = 0;
  v77 = 0;
  if ( CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v78) < 0 )
    goto LABEL_27;
  v11 = (char *)v10 + ((v71 + 7) & 0xFFFFFFF8) + ((v8 + 7) & 0xFFFFFFF8);
  v12 = *(unsigned int *)v11;
  if ( (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v78 + 64LL))(v78, v11) < 0 )
  {
LABEL_26:
    v7 = v62;
LABEL_27:
    v14 = v63;
    goto LABEL_28;
  }
  v13 = v78;
  v67 = (ISpPhrase *)v78;
  v78 = 0;
  v83.pPhrase = v67;
  if ( ((int (__fastcall *)(LPVOID, LPVOID *))v67->lpVtbl->GetPhrase)(v13, &pv) < 0
    || CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v77) < 0
    || (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v77 + 64LL))(v77, &v11[v12]) < 0 )
  {
    goto LABEL_25;
  }
  v14 = v77;
  v63 = v77;
  v77 = 0;
  if ( (*(int (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v63 + 24LL))(v63, &v74) >= 0 )
  {
    v61 = 0;
    v66 = 0;
    v15 = -1;
    if ( !v8 )
    {
      v81 = 0;
      v59 = 1;
      v20 = 0;
      goto LABEL_39;
    }
    ReconstructInternalPointers((struct LATTICE *)v84, v10);
    if ( (int)BuildElementArrays(&v62, &v80, &v73, (struct LATTICE *)v84) >= 0 )
    {
      v59 = 0;
      v16 = 0;
      if ( v73 )
      {
        while ( v62[v16] == v16 )
        {
          if ( ++v16 >= v73 )
            goto LABEL_14;
        }
        v59 = 1;
      }
LABEL_14:
      v79 = (struct _GUID)*((_OWORD *)v10 + 1);
      RecentReco = CHistory::FindRecentReco(v5[119], &v79);
      v20 = RecentReco;
      if ( RecentReco )
        v21 = (struct CStreamPair *)*((_QWORD *)RecentReco + 5);
      else
        v21 = 0;
      if ( (int)MarkWildCardsAndCancelRecos(&v83, v19, v18, v21) < 0 )
        goto LABEL_25;
      if ( v20 )
      {
        v22 = *((_QWORD *)v20 + 5);
        if ( v22 )
        {
          v61 = *(_BYTE *)(v22 + 552);
          if ( v61 )
          {
            v23 = (unsigned __int16 *)(v22 + 40);
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
            if ( v24 )
              v66 = v23;
          }
        }
      }
LABEL_39:
      v26 = v74;
      if ( *((_DWORD *)v74 + 16) )
      {
        do
        {
          CQuickStringW<100>::Append(&v85, *(_QWORD *)(56LL * (unsigned int)v6 + *((_QWORD *)v26 + 13) + 24));
          LODWORD(v6) = (_DWORD)v6 + 1;
          if ( (unsigned int)v6 < *((_DWORD *)pv + 16) )
            CQuickStringW<100>::Append(&v85, L" ");
          v26 = v74;
        }
        while ( (unsigned int)v6 < *((_DWORD *)v74 + 16) );
      }
      v27 = *((_DWORD *)v26 + 16);
      if ( v75 + v76 < v27 )
        v27 = v75 + v76;
      v28 = v75;
      if ( v75 < v27 )
      {
        while ( 1 )
        {
          CQuickStringW<100>::Append(&v89, *(_QWORD *)(56LL * v28++ + *((_QWORD *)v26 + 13) + 24));
          if ( v28 >= v27 )
            break;
          CQuickStringW<100>::Append(&v89, L" ");
          v26 = v74;
        }
      }
      if ( (v91 & 0x7FFFFFFF) != 0 )
        (*((void (__fastcall **)(CHistory **, _QWORD, __int16 *, _QWORD, _QWORD, int, int))*v5 + 33))(
          v5,
          0,
          v90,
          v91 & 0x7FFFFFFF,
          0,
          1,
          3);
      v29 = 2;
      if ( v20 && (v87 & 0x7FFFFFFF) != 0 )
      {
        if ( *((_QWORD *)v20 + 10) )
          CSpDynamicString::_free((struct CRecentReco *)((char *)v20 + 80));
        CSpDynamicString::operator=((struct CRecentReco *)((char *)v20 + 80), Src);
      }
      else if ( (v87 & 0x7FFFFFFF) != 0 )
      {
        (*((void (__fastcall **)(CHistory **, _QWORD, void *))*v5 + 33))(v5, 0, Src);
      }
      v30 = -1;
      v71 = -1;
      v31 = v64;
      if ( v65 != 1 || v64 != 1 || !*((_BYTE *)v5 + 424) )
        goto LABEL_88;
      if ( (int)ExtractElementStrings(-2, (_DWORD)pv, v9, (unsigned int)&v113, (__int64)&v161, (__int64)&v157) >= 0
        && (int)ExtractElementStrings(-1, (_DWORD)pv, v9, (unsigned int)&v109, (__int64)&v153, (__int64)&v149) >= 0
        && (int)ExtractElementStrings(0, (_DWORD)pv, v9, (unsigned int)&v105, (__int64)&v145, (__int64)&v141) >= 0
        && (int)ExtractElementStrings(0, (_DWORD)v74, v9, (unsigned int)&v101, (__int64)&v137, (__int64)&v133) >= 0
        && (int)ExtractElementStrings(1, (_DWORD)pv, v9, (unsigned int)&v97, (__int64)&v129, (__int64)&v125) >= 0
        && (int)ExtractElementStrings(2, (_DWORD)pv, v9, (unsigned int)&v93, (__int64)&v121, (__int64)&v117) >= 0 )
      {
        if ( !v61 )
        {
LABEL_87:
          v31 = v64;
LABEL_88:
          LODWORD(v72) = v81[4];
          v68 = v81[9];
          v65 = v81[13];
          if ( v60 )
            v29 = 6;
          LODWORD(v66) = v29;
          if ( v20 )
          {
            v30 = 0;
            do
            {
              v30 += *((_DWORD *)v20 + 18);
              v20 = (struct CRecentReco *)*((_QWORD *)v20 + 3);
            }
            while ( v20 );
            v71 = v30;
          }
          v36 = 0;
          v37 = 0;
          v38 = 0;
          v39 = 0;
          v40 = 0;
          v70 = 0;
          if ( !v59 )
          {
            v70 = v73;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v42 = v73;
              if ( v73 > 0x10 )
                v42 = 16;
              if ( (unsigned int)i >= v42 )
                break;
              v43 = 1 << (15 - i);
              if ( (unsigned int)i >= v75 && (unsigned int)i < v75 + v76 )
                v39 |= v43;
              v44 = v80[i];
              if ( (*((_BYTE *)v44 + 8) & 0x10) != 0 )
                v38 |= v43;
              if ( (*((_DWORD *)v44 + 2) & 0x200) != 0 )
                v37 |= v43;
              v45 = *((_DWORD *)pv + 28);
              if ( v45 )
              {
                v46 = 0;
                v47 = *((_QWORD *)pv + 15);
                while ( 1 )
                {
                  v48 = *(_DWORD *)(v47 + 24 * v46 + 16);
                  if ( (unsigned int)i >= v48 && (unsigned int)i < *(_DWORD *)(v47 + 24 * v46 + 20) + v48 )
                    break;
                  v46 = (unsigned int)(v46 + 1);
                  if ( (unsigned int)v46 >= v45 )
                    goto LABEL_113;
                }
                v36 |= v43;
              }
LABEL_113:
              ;
            }
            v5 = (CHistory **)v82;
            v30 = v71;
            v40 = v70;
            v31 = v64;
          }
          CSREngine::LogSQMEvent(
            (CSREngine *)v5,
            0x73Du,
            9u,
            (unsigned int)v72,
            v68,
            v65,
            v30,
            (unsigned __int16)v38 | (v39 << 16),
            (unsigned __int16)v36 | (v37 << 16),
            v40 << 16,
            v83.ulRequestAltCount << 16,
            (unsigned int)v66 | (v31 << 16));
          v49 = L"  CacheUnigramUpdated";
          if ( !v60 )
            v49 = &word_18010FB50;
          LODWORD(v58) = v64;
          LODWORD(v57) = v83.ulRequestAltCount;
          LODWORD(v56) = v70;
          LODWORD(v55) = v36;
          LODWORD(v54) = v37;
          LODWORD(v53) = v38;
          LODWORD(v52) = v39;
          v51[0] = v30;
          LODWORD(ppv) = v65;
          TraceTag(
            (struct CDebugTag *)&g_tagAlternates,
            L"Commit  Reco %08x  LatticeSize %d  SymbolsSize %d  HistoryDepth %d\n"
             "  Range %04x  SLM %04x  TB %04x  Replace %04x  Elements %d  Requested %d  NewElements %d%s\n",
            (unsigned int)v72,
            v68,
            ppv,
            *(_QWORD *)v51,
            v52,
            v53,
            v54,
            v55,
            v56,
            v57,
            v58,
            v49);
          goto LABEL_25;
        }
        v72 = 0;
        if ( CSREngine::LookupLMATopic((CSREngine *)v5, v66, &v72) >= 0 )
        {
          v32 = v72;
          v33 = (**(__int64 (__fastcall ***)(struct CSRTopicSLM *))v72)(v72);
          if ( !v33 )
            goto LABEL_86;
          v65 = -1;
          v68 = -1;
          v70 = -1;
          if ( (v115 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v66, *((_QWORD *)v5[17] + 57));
            v65 = LwidFromElementStrings((_DWORD)v114, (_DWORD)v162, (_DWORD)v158, (unsigned int)&v66, v33);
          }
          if ( (v111 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v66, *((_QWORD *)v5[17] + 57));
            v68 = LwidFromElementStrings((_DWORD)v110, (_DWORD)v154, (_DWORD)v150, (unsigned int)&v66, v33);
          }
          ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v66, *((_QWORD *)v5[17] + 57));
          LODWORD(v66) = LwidFromElementStrings((_DWORD)v106, (_DWORD)v146, (_DWORD)v142, (unsigned int)&v66, v33);
          ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v72, *((_QWORD *)v5[17] + 57));
          LODWORD(v72) = LwidFromElementStrings((_DWORD)v102, (_DWORD)v138, (_DWORD)v134, (unsigned int)&v72, v33);
          if ( (v99 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v70, *((_QWORD *)v5[17] + 57));
            v70 = LwidFromElementStrings((_DWORD)v98, (_DWORD)v130, (_DWORD)v126, (unsigned int)&v70, v33);
          }
          if ( (v95 & 0x7FFFFFFF) != 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v79, *((_QWORD *)v5[17] + 57));
            v34 = LwidFromElementStrings((_DWORD)v94, (_DWORD)v122, (_DWORD)v118, (unsigned int)&v79, v33);
          }
          else
          {
            v34 = -1;
          }
          v35 = -1;
          do
            ++v35;
          while ( v102[v35] );
          if ( v35 > 0xA )
            LODWORD(v35) = 10;
          do
            ++v15;
          while ( v106[v15] );
          if ( v15 > 0xA )
            LODWORD(v15) = 10;
          if ( CSREngine::AdaptFromCorrection(
                 (CSREngine *)v5,
                 v65,
                 v68,
                 (unsigned int)v66,
                 (unsigned int)v72,
                 v70,
                 v34,
                 v106,
                 v15,
                 v102,
                 v35,
                 v32,
                 &v60) >= 0 )
          {
LABEL_86:
            v29 = 2;
            goto LABEL_87;
          }
        }
      }
LABEL_25:
      v6 = v67;
      goto LABEL_26;
    }
  }
  v6 = v67;
  v7 = v62;
LABEL_28:
  if ( v6 )
    ((void (__fastcall *)(ISpPhrase *))v6->lpVtbl->Release)(v6);
  CoTaskMemFree(pv);
  if ( v14 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  CoTaskMemFree(v74);
  if ( v7 )
    operator delete(v7);
  if ( v80 )
    operator delete(v80);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v77);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v78);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v89);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v85);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v117);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v121);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v93);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v125);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v129);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v97);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v133);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v137);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v101);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v141);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v145);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v105);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v149);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v153);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v109);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v157);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v161);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v113);
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
