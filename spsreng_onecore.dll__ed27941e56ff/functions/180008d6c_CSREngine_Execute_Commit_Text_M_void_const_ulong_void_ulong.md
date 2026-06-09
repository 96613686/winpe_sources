# CSREngine::Execute_Commit_Text_M(void const *,ulong,void * *,ulong *)

- ea: `0x180008d6c`
- end: `0x180009cca`
- name: `?Execute_Commit_Text_M@CSREngine@@QEAAJPEBXKPEAPEAXPEAK@Z`
- size: `3934`
- prototype: `__int64 __fastcall(CSREngine *this, _DWORD *, __int64, void **)`
- caller_count: `1`
- callee_count: `24`
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
- `0x1800073b4`
- `0x180008d6c`
- `0x18000a540`
- `0x18000dbe0`
- `0x18000dd54`
- `0x18001cc40`
- `0x18007350c`
- `0x180082988`
- `0x1800835e8`
- `0x180083838`
- `0x180083a54`
- `0x1800c77ac`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800090c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009706`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800090c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009706`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ba7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008dbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008dbe`

## string_xrefs

- `0x180009ac9`: `  CacheUnigramUpdated`
- `0x180009b2b`: `CommitText  Reco %08x  LatticeSize %d  SymbolsSize %d  HistoryDepth %d\n  Range %04x  SLM %04x  TB %04x  Replace %04x  Elements %d  OOV %04x  NewElements %d%s%s%s%s\n`

## pseudocode

```c
__int64 __fastcall CSREngine::Execute_Commit_Text_M(CSREngine *this, _DWORD *a2, __int64 a3, void **a4)
{
  CSREngine *v5; // r14
  int *v6; // r13
  LPVOID v7; // r12
  ULONG v8; // edi
  struct LATTICE_HEADER *v9; // r15
  char *v10; // rbx
  __int64 v11; // rsi
  unsigned __int64 v12; // r12
  int v13; // eax
  ULONG v14; // edi
  unsigned int v15; // ecx
  struct CRecentReco *RecentReco; // rax
  unsigned int v17; // r8d
  struct CRecentReco *v18; // rsi
  struct CStreamPair *v19; // r9
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // r9d
  unsigned int v24; // r15d
  ULONG v25; // r14d
  ULONG v26; // r15d
  ULONG v27; // edi
  struct CSRTopicSLM *v28; // rdi
  __int64 v29; // r13
  __int64 v30; // r8
  unsigned int v31; // edi
  char v32; // al
  unsigned int v33; // r8d
  unsigned __int64 v34; // rcx
  int v35; // r8d
  unsigned int v36; // edx
  int v37; // esi
  int v38; // r12d
  unsigned int v39; // r11d
  unsigned int v40; // r10d
  unsigned int v41; // edi
  unsigned int v42; // ecx
  __int64 v43; // rax
  unsigned int v44; // eax
  int v45; // r9d
  struct LATTICE_NODE *v46; // rcx
  unsigned int v47; // r10d
  __int64 v48; // r11
  unsigned int v49; // ecx
  unsigned int v50; // r13d
  const wchar_t *v51; // r10
  const wchar_t *v52; // rdx
  const wchar_t *v53; // rcx
  const wchar_t *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-F0h]
  unsigned int v59[2]; // [rsp+28h] [rbp-E8h]
  __int64 v60; // [rsp+30h] [rbp-E0h]
  unsigned __int16 *v61; // [rsp+38h] [rbp-D8h]
  __int64 v62; // [rsp+40h] [rbp-D0h]
  unsigned __int16 *v63; // [rsp+48h] [rbp-C8h]
  __int64 v64; // [rsp+50h] [rbp-C0h]
  struct CSRTopicSLM *v65; // [rsp+58h] [rbp-B8h]
  bool *v66; // [rsp+60h] [rbp-B0h]
  char v67; // [rsp+90h] [rbp-80h]
  char v68; // [rsp+91h] [rbp-7Fh]
  unsigned __int8 v69; // [rsp+92h] [rbp-7Eh]
  bool v70; // [rsp+93h] [rbp-7Dh] BYREF
  unsigned __int16 *v71; // [rsp+98h] [rbp-78h] BYREF
  char v72; // [rsp+A0h] [rbp-70h]
  void *v73; // [rsp+A8h] [rbp-68h] BYREF
  unsigned int v74; // [rsp+B0h] [rbp-60h]
  unsigned int v75; // [rsp+B4h] [rbp-5Ch]
  unsigned int v76; // [rsp+B8h] [rbp-58h]
  ISpPhrase *v77; // [rsp+C0h] [rbp-50h]
  unsigned int v78; // [rsp+C8h] [rbp-48h]
  LPVOID v79; // [rsp+D0h] [rbp-40h] BYREF
  ULONG v80; // [rsp+D8h] [rbp-38h]
  unsigned int v81; // [rsp+DCh] [rbp-34h]
  struct CSRTopicSLM *v82; // [rsp+E0h] [rbp-30h] BYREF
  int v83; // [rsp+E8h] [rbp-28h]
  int v84; // [rsp+ECh] [rbp-24h]
  unsigned int v85; // [rsp+F0h] [rbp-20h] BYREF
  ULONG v86; // [rsp+F4h] [rbp-1Ch]
  int v87; // [rsp+F8h] [rbp-18h]
  unsigned int v88[2]; // [rsp+100h] [rbp-10h]
  LPVOID v89; // [rsp+108h] [rbp-8h] BYREF
  struct IUnknown *v90; // [rsp+110h] [rbp+0h] BYREF
  __int64 v91; // [rsp+118h] [rbp+8h]
  struct LATTICE_NODE **v92; // [rsp+120h] [rbp+10h] BYREF
  CSREngine *v93; // [rsp+128h] [rbp+18h]
  unsigned int v94; // [rsp+130h] [rbp+20h] BYREF
  __int64 v95; // [rsp+134h] [rbp+24h]
  int v96; // [rsp+13Ch] [rbp+2Ch]
  _QWORD *v97; // [rsp+140h] [rbp+30h]
  __int128 v98; // [rsp+148h] [rbp+38h]
  LPVOID pv; // [rsp+158h] [rbp+48h]
  struct _GUID v100; // [rsp+160h] [rbp+50h] BYREF
  struct tagSPPHRASEALTREQUEST v101; // [rsp+170h] [rbp+60h] BYREF
  _BYTE v102[192]; // [rsp+1A0h] [rbp+90h] BYREF
  void **v103; // [rsp+260h] [rbp+150h] BYREF
  unsigned __int16 *v104; // [rsp+268h] [rbp+158h]
  unsigned int v105; // [rsp+270h] [rbp+160h]
  __int16 v106; // [rsp+278h] [rbp+168h] BYREF
  void **v107; // [rsp+350h] [rbp+240h] BYREF
  void *Src; // [rsp+358h] [rbp+248h]
  unsigned int v109; // [rsp+360h] [rbp+250h]
  __int16 v110; // [rsp+368h] [rbp+258h] BYREF
  void **v111; // [rsp+440h] [rbp+330h] BYREF
  __int16 *v112; // [rsp+448h] [rbp+338h]
  unsigned int v113; // [rsp+450h] [rbp+340h]
  __int16 v114; // [rsp+458h] [rbp+348h] BYREF
  void **v115; // [rsp+530h] [rbp+420h] BYREF
  __int16 *v116; // [rsp+538h] [rbp+428h]
  unsigned int v117; // [rsp+540h] [rbp+430h]
  __int16 v118; // [rsp+548h] [rbp+438h] BYREF
  void **v119; // [rsp+620h] [rbp+510h] BYREF
  unsigned __int16 *v120; // [rsp+628h] [rbp+518h]
  unsigned int v121; // [rsp+630h] [rbp+520h]
  __int16 v122; // [rsp+638h] [rbp+528h] BYREF
  void **v123; // [rsp+710h] [rbp+600h] BYREF
  __int16 *v124; // [rsp+718h] [rbp+608h]
  unsigned int v125; // [rsp+720h] [rbp+610h]
  __int16 v126; // [rsp+728h] [rbp+618h] BYREF
  void **v127; // [rsp+800h] [rbp+6F0h] BYREF
  __int16 *v128; // [rsp+808h] [rbp+6F8h]
  unsigned int v129; // [rsp+810h] [rbp+700h]
  __int16 v130; // [rsp+818h] [rbp+708h] BYREF
  void **v131; // [rsp+8F0h] [rbp+7E0h] BYREF
  __int16 *v132; // [rsp+8F8h] [rbp+7E8h]
  unsigned int v133; // [rsp+900h] [rbp+7F0h]
  __int16 v134; // [rsp+908h] [rbp+7F8h] BYREF
  void **v135; // [rsp+9E0h] [rbp+8D0h] BYREF
  __int16 *v136; // [rsp+9E8h] [rbp+8D8h]
  unsigned int v137; // [rsp+9F0h] [rbp+8E0h]
  __int16 v138; // [rsp+9F8h] [rbp+8E8h] BYREF
  void **v139; // [rsp+AD0h] [rbp+9C0h] BYREF
  __int16 *v140; // [rsp+AD8h] [rbp+9C8h]
  unsigned int v141; // [rsp+AE0h] [rbp+9D0h]
  __int16 v142; // [rsp+AE8h] [rbp+9D8h] BYREF
  void **v143; // [rsp+BC0h] [rbp+AB0h] BYREF
  __int16 *v144; // [rsp+BC8h] [rbp+AB8h]
  unsigned int v145; // [rsp+BD0h] [rbp+AC0h]
  __int16 v146; // [rsp+BD8h] [rbp+AC8h] BYREF
  void **v147; // [rsp+CB0h] [rbp+BA0h] BYREF
  __int16 *v148; // [rsp+CB8h] [rbp+BA8h]
  unsigned int v149; // [rsp+CC0h] [rbp+BB0h]
  __int16 v150; // [rsp+CC8h] [rbp+BB8h] BYREF
  void **v151; // [rsp+DA0h] [rbp+C90h] BYREF
  __int16 *v152; // [rsp+DA8h] [rbp+C98h]
  unsigned int v153; // [rsp+DB0h] [rbp+CA0h]
  __int16 v154; // [rsp+DB8h] [rbp+CA8h] BYREF
  void **v155; // [rsp+E90h] [rbp+D80h] BYREF
  __int16 *v156; // [rsp+E98h] [rbp+D88h]
  unsigned int v157; // [rsp+EA0h] [rbp+D90h]
  __int16 v158; // [rsp+EA8h] [rbp+D98h] BYREF
  void **v159; // [rsp+F80h] [rbp+E70h] BYREF
  __int16 *v160; // [rsp+F88h] [rbp+E78h]
  unsigned int v161; // [rsp+F90h] [rbp+E80h]
  __int16 v162; // [rsp+F98h] [rbp+E88h] BYREF
  void **v163; // [rsp+1070h] [rbp+F60h] BYREF
  __int16 *v164; // [rsp+1078h] [rbp+F68h]
  unsigned int v165; // [rsp+1080h] [rbp+F70h]
  __int16 v166; // [rsp+1088h] [rbp+F78h] BYREF
  void **v167; // [rsp+1160h] [rbp+1050h] BYREF
  __int16 *v168; // [rsp+1168h] [rbp+1058h]
  unsigned int v169; // [rsp+1170h] [rbp+1060h]
  __int16 v170; // [rsp+1178h] [rbp+1068h] BYREF

  v5 = this;
  v93 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 600LL));
  v129 = 0x80000000;
  v128 = &v130;
  v130 = 0;
  v127 = &CQuickStringW<100>::`vftable';
  v169 = 0x80000000;
  v168 = &v170;
  v170 = 0;
  v167 = &CQuickStringW<100>::`vftable';
  v165 = 0x80000000;
  v164 = &v166;
  v166 = 0;
  v163 = &CQuickStringW<100>::`vftable';
  v125 = 0x80000000;
  v124 = &v126;
  v126 = 0;
  v123 = &CQuickStringW<100>::`vftable';
  v161 = 0x80000000;
  v160 = &v162;
  v162 = 0;
  v159 = &CQuickStringW<100>::`vftable';
  v157 = 0x80000000;
  v156 = &v158;
  v158 = 0;
  v155 = &CQuickStringW<100>::`vftable';
  v121 = 0x80000000;
  v120 = (unsigned __int16 *)&v122;
  v122 = 0;
  v119 = &CQuickStringW<100>::`vftable';
  v153 = 0x80000000;
  v152 = &v154;
  v154 = 0;
  v151 = &CQuickStringW<100>::`vftable';
  v149 = 0x80000000;
  v148 = &v150;
  v150 = 0;
  v147 = &CQuickStringW<100>::`vftable';
  v105 = 0x80000000;
  v104 = (unsigned __int16 *)&v106;
  v106 = 0;
  v103 = &CQuickStringW<100>::`vftable';
  v117 = 0x80000000;
  v116 = &v118;
  v118 = 0;
  v115 = &CQuickStringW<100>::`vftable';
  v145 = 0x80000000;
  v144 = &v146;
  v146 = 0;
  v143 = &CQuickStringW<100>::`vftable';
  v141 = 0x80000000;
  v140 = &v142;
  v142 = 0;
  v139 = &CQuickStringW<100>::`vftable';
  v113 = 0x80000000;
  v112 = &v114;
  v114 = 0;
  v111 = &CQuickStringW<100>::`vftable';
  v137 = 0x80000000;
  v136 = &v138;
  v138 = 0;
  v135 = &CQuickStringW<100>::`vftable';
  v133 = 0x80000000;
  v132 = &v134;
  v134 = 0;
  v131 = &CQuickStringW<100>::`vftable';
  v109 = 0x80000000;
  Src = &v110;
  v110 = 0;
  v107 = &CQuickStringW<100>::`vftable';
  v90 = 0;
  v95 = 0;
  v96 = 0;
  v98 = 0;
  pv = 0;
  v94 = 0;
  v97 = 0;
  v6 = 0;
  v73 = 0;
  v92 = 0;
  v79 = 0;
  *(&v101.ulRequestAltCount + 1) = 0;
  memset(&v101.cbResultExtra + 1, 0, 20);
  v70 = 0;
  v85 = 0;
  memset_0(v102, 0, 0xB8u);
  v7 = 0;
  v86 = a2[1];
  v101.ulStartElement = v86;
  v80 = a2[2];
  v101.cElements = v80;
  v101.ulRequestAltCount = a2[3];
  v8 = a2[4];
  v101.cbResultExtra = v8;
  v83 = a2[5];
  v9 = (struct LATTICE_HEADER *)(a2 + 6);
  *(_QWORD *)v88 = a2 + 6;
  v101.pvResultExtra = a2 + 6;
  v89 = 0;
  if ( CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v89) >= 0 )
  {
    v10 = (char *)v9 + ((v8 + 7) & 0xFFFFFFF8);
    v11 = *(unsigned int *)v10;
    if ( (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v89 + 64LL))(v89, v10) >= 0 )
    {
      v7 = v89;
      v77 = (ISpPhrase *)v89;
      v89 = 0;
      v101.pPhrase = v77;
      if ( ((int (__fastcall *)(ISpPhrase *, LPVOID *))v77->lpVtbl->GetPhrase)(v77, &v79) >= 0 )
      {
        v72 = 0;
        v71 = 0;
        CQuickStringW<100>::Append(&v103, &v10[v11]);
        v12 = -1;
        if ( v8 )
        {
          ReconstructInternalPointers((struct LATTICE *)v102, v9);
          v13 = BuildElementArrays((int **)&v73, &v92, &v85, (struct LATTICE *)v102);
          v14 = 0;
          v6 = (int *)v73;
          if ( v13 < 0 )
            goto LABEL_22;
          v68 = 0;
          v15 = 0;
          if ( v85 )
          {
            while ( *((_DWORD *)v73 + v15) == v15 )
            {
              if ( ++v15 >= v85 )
                goto LABEL_11;
            }
            v68 = 1;
          }
LABEL_11:
          v100 = (struct _GUID)*((_OWORD *)v9 + 1);
          RecentReco = CHistory::FindRecentReco(*((CHistory **)v5 + 119), &v100);
          v18 = RecentReco;
          v19 = RecentReco ? (struct CStreamPair *)*((_QWORD *)RecentReco + 5) : 0LL;
          if ( (int)MarkWildCardsAndCancelRecos(&v101, v6, v17, v19) < 0 )
          {
LABEL_22:
            v7 = v77;
            goto LABEL_131;
          }
          if ( v18 )
          {
            v20 = *((_QWORD *)v18 + 5);
            if ( v20 )
            {
              v72 = *(_BYTE *)(v20 + 552);
              if ( v72 )
              {
                v21 = (unsigned __int16 *)(v20 + 40);
                v22 = -1;
                do
                  ++v22;
                while ( v21[v22] );
                if ( v22 )
                  v71 = v21;
              }
            }
          }
        }
        else
        {
          v14 = 0;
          *(_QWORD *)v88 = 0;
          v68 = 1;
          v18 = 0;
        }
        v91 = 0;
        v67 = 0;
        v84 = 0;
        v23 = v105;
        v24 = -1;
        v87 = -1;
        if ( (v105 & 0x7FFFFFFF) == 0 )
        {
          v69 = 1;
LABEL_90:
          v83 &= 2u;
          v35 = (v70 ? 4 : 0) | (v67 != 0 ? 8 : 0) | (32 * v69) | (v83 != 0 ? 0x10 : 0);
          LODWORD(v82) = v35;
          v36 = 0;
          if ( v18 )
          {
            v24 = 0;
            do
            {
              v24 += *((_DWORD *)v18 + 18);
              v18 = (struct CRecentReco *)*((_QWORD *)v18 + 3);
            }
            while ( v18 );
            v87 = v24;
          }
          v37 = 0;
          v38 = 0;
          v39 = 0;
          v75 = 0;
          v40 = 0;
          v76 = 0;
          v41 = 0;
          v42 = 0;
          v74 = 0;
          v43 = *(_QWORD *)v88;
          if ( *(_QWORD *)v88 )
          {
            v88[0] = *(_DWORD *)(*(_QWORD *)v88 + 16LL);
            v81 = *(_DWORD *)(v43 + 36);
            v78 = *(_DWORD *)(v43 + 52);
            v42 = 0;
          }
          else
          {
            v78 = 0;
            v88[0] = 0;
            v81 = 0;
          }
          if ( !v68 )
          {
            v74 = v85;
            while ( 1 )
            {
              v44 = v85;
              if ( v85 > 0x10 )
                v44 = 16;
              if ( v36 >= v44 )
                break;
              v45 = 1 << (15 - v36);
              if ( v36 >= v86 && v36 < v86 + v80 )
              {
                v40 |= v45;
                v76 = v40;
              }
              v46 = v92[v36];
              if ( (*((_BYTE *)v46 + 8) & 0x10) != 0 )
              {
                v39 |= v45;
                v75 = v39;
              }
              if ( (*((_DWORD *)v46 + 2) & 0x200) != 0 )
                v38 |= v45;
              if ( *((_DWORD *)v79 + 28) )
              {
                v47 = 0;
                v48 = *((_QWORD *)v79 + 15);
                while ( 1 )
                {
                  v49 = *(_DWORD *)(v48 + 24LL * v47 + 16);
                  if ( v36 >= v49 && v36 < *(_DWORD *)(v48 + 24LL * v47 + 20) + v49 )
                    break;
                  if ( ++v47 >= *((_DWORD *)v79 + 28) )
                    goto LABEL_116;
                }
                v37 |= v45;
LABEL_116:
                v39 = v75;
                v40 = v76;
              }
              ++v36;
            }
            v41 = 0;
            if ( v91 )
              v41 = v94;
            v5 = v93;
            v35 = (int)v82;
            v24 = v87;
            v42 = v74;
          }
          v50 = v81;
          CSREngine::LogSQMEvent(
            v5,
            0x73Du,
            9u,
            v88[0],
            v81,
            v78,
            v24,
            (unsigned __int16)v39 | (v40 << 16),
            (unsigned __int16)v37 | (v38 << 16),
            (unsigned __int16)v84 | (v42 << 16),
            0,
            v35 | (v41 << 16));
          v51 = L"  UndoOperation";
          if ( !v69 )
            v51 = &word_18010FB50;
          v52 = L"  DefiniteCorrection";
          if ( !v83 )
            v52 = &word_18010FB50;
          v53 = L"  AddedWordToLexicon";
          if ( !v67 )
            v53 = &word_18010FB50;
          v54 = L"  CacheUnigramUpdated";
          if ( !v70 )
            v54 = &word_18010FB50;
          LODWORD(v66) = v41;
          LODWORD(v65) = v84;
          LODWORD(v64) = v74;
          LODWORD(v63) = v37;
          LODWORD(v62) = v38;
          LODWORD(v61) = v75;
          LODWORD(v60) = v76;
          v59[0] = v24;
          LODWORD(ppv) = v78;
          TraceTag(
            (struct CDebugTag *)&g_tagAlternates,
            L"CommitText  Reco %08x  LatticeSize %d  SymbolsSize %d  HistoryDepth %d\n"
             "  Range %04x  SLM %04x  TB %04x  Replace %04x  Elements %d  OOV %04x  NewElements %d%s%s%s%s\n",
            v88[0],
            v50,
            ppv,
            *(_QWORD *)v59,
            v60,
            v61,
            v62,
            v63,
            v64,
            v65,
            v66,
            v54,
            v53,
            v52,
            v51);
          goto LABEL_130;
        }
        if ( *((_DWORD *)v79 + 16) )
        {
          v25 = v86;
          v26 = v80;
          do
          {
            if ( v14 == v25 )
            {
              CQuickStringW<100>::Append(&v107, v104);
              if ( v26 )
                v14 = v26 + v14 - 1;
            }
            else
            {
              CQuickStringW<100>::Append(&v107, *(_QWORD *)(56LL * v14 + *((_QWORD *)v79 + 13) + 24));
            }
            if ( ++v14 < *((_DWORD *)v79 + 16) )
              CQuickStringW<100>::Append(&v107, L" ");
          }
          while ( v14 < *((_DWORD *)v79 + 16) );
          v23 = v105;
          v5 = v93;
          v24 = -1;
        }
        if ( (v23 & 0x7FFFFFFF) != 0 )
          (*(void (__fastcall **)(CSREngine *, _QWORD, unsigned __int16 *))(*(_QWORD *)v5 + 264LL))(v5, 0, v104);
        if ( v18 && (v109 & 0x7FFFFFFF) != 0 )
        {
          if ( *((_QWORD *)v18 + 10) )
            CSpDynamicString::_free((struct CRecentReco *)((char *)v18 + 80));
          CSpDynamicString::operator=((struct CRecentReco *)((char *)v18 + 80), Src);
        }
        else if ( (v109 & 0x7FFFFFFF) != 0 )
        {
          (*(void (__fastcall **)(CSREngine *, _QWORD, void *))(*(_QWORD *)v5 + 264LL))(v5, 0, Src);
        }
        v27 = v86;
        if ( (int)ExtractElementStrings(-2, (_DWORD)v79, v86, (unsigned int)&v127, (__int64)&v167, (__int64)&v163) >= 0
          && (int)ExtractElementStrings(-1, (_DWORD)v79, v27, (unsigned int)&v123, (__int64)&v159, (__int64)&v155) >= 0
          && (int)ExtractElementStrings(1, (_DWORD)v79, v27, (unsigned int)&v115, (__int64)&v143, (__int64)&v139) >= 0
          && (int)ExtractElementStrings(2, (_DWORD)v79, v27, (unsigned int)&v111, (__int64)&v135, (__int64)&v131) >= 0 )
        {
          if ( v80 == 1
            && (int)ExtractElementStrings(0, (_DWORD)v79, v27, (unsigned int)&v119, (__int64)&v151, (__int64)&v147) < 0 )
          {
            goto LABEL_51;
          }
          v69 = 0;
          if ( !v72 )
            goto LABEL_90;
          v82 = 0;
          if ( CSREngine::LookupLMATopic(v5, v71, &v82) < 0 )
            goto LABEL_51;
          v28 = v82;
          v29 = (**(__int64 (__fastcall ***)(struct CSRTopicSLM *))v82)(v82);
          v91 = v29;
          if ( !v29 )
            goto LABEL_90;
          v30 = v105;
          LODWORD(v30) = v105 & 0x7FFFFFFF;
          if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, __int64, _QWORD, unsigned int *))(**(_QWORD **)(*((_QWORD *)v5 + 17) + 456LL)
                                                                                                  + 80LL))(
                 *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL),
                 v104,
                 v30,
                 0,
                 &v94) >= 0 )
          {
            v81 = -1;
            v74 = -1;
            v75 = -1;
            v76 = -1;
            v78 = -1;
            if ( v80 == 1 && v94 == 1 )
            {
              if ( (v129 & 0x7FFFFFFF) != 0 )
              {
                ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
                  &v71,
                  *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
                v81 = LwidFromElementStrings((_DWORD)v128, (_DWORD)v168, (_DWORD)v164, (unsigned int)&v71, v29);
              }
              if ( (v125 & 0x7FFFFFFF) != 0 )
              {
                ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
                  &v71,
                  *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
                v74 = LwidFromElementStrings((_DWORD)v124, (_DWORD)v160, (_DWORD)v156, (unsigned int)&v71, v29);
              }
              ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
                &v71,
                *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
              v75 = LwidFromElementStrings((_DWORD)v120, (_DWORD)v152, (_DWORD)v148, (unsigned int)&v71, v29);
              if ( (v117 & 0x7FFFFFFF) != 0 )
              {
                ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
                  &v71,
                  *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
                v76 = LwidFromElementStrings((_DWORD)v116, (_DWORD)v144, (_DWORD)v140, (unsigned int)&v71, v29);
              }
              if ( (v113 & 0x7FFFFFFF) != 0 )
              {
                ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
                  &v71,
                  *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
                v78 = LwidFromElementStrings((_DWORD)v112, (_DWORD)v136, (_DWORD)v132, (unsigned int)&v71, v29);
              }
            }
            if ( (v83 & 1) != 0 )
            {
              v31 = 0;
              if ( v90 )
                ATL::AtlComPtrAssign(&v90, 0);
              if ( CoCreateInstance(
                     &CLSID_SpLexicon,
                     0,
                     0x17u,
                     &GUID_da41a7c2_5383_4db2_916b_6c1719e3db58,
                     (LPVOID *)&v90) < 0 )
                goto LABEL_51;
              if ( v94 )
              {
                do
                {
                  ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
                    &v71,
                    *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
                  if ( (unsigned int)LwidFromElementStrings(v97[v31], 0, 0, (unsigned int)&v71, v29) == -1 )
                  {
                    if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD, _QWORD))v90->lpVtbl[1].AddRef)(
                           v90,
                           v97[v31],
                           *((unsigned __int16 *)v5 + 128),
                           0,
                           0) < 0 )
                      goto LABEL_130;
                    v32 = 1;
                    v67 = 1;
                    if ( v31 < 0x10 )
                    {
                      v84 |= 1 << (15 - v31);
                      v32 = 1;
                    }
                  }
                  else
                  {
                    v32 = v67;
                  }
                  ++v31;
                }
                while ( v31 < v94 );
                if ( v32 && (int)CDecoder::search_sync(*(CDecoder **)(*((_QWORD *)v5 + 17) + 64LL)) < 0 )
                  goto LABEL_51;
              }
              v28 = v82;
            }
            if ( v80 != 1 || v94 != 1 )
              goto LABEL_90;
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(
              &v82,
              *(_QWORD *)(*((_QWORD *)v5 + 17) + 456LL));
            v33 = LwidFromElementStrings(*v97, 0, 0, (unsigned int)&v82, v29);
            v34 = -1;
            do
              ++v34;
            while ( v104[v34] );
            if ( v34 > 0xA )
              LODWORD(v34) = 10;
            do
              ++v12;
            while ( v120[v12] );
            if ( v12 > 0xA )
              LODWORD(v12) = 10;
            if ( CSREngine::AdaptFromCorrection(v5, v81, v74, v75, v33, v76, v78, v120, v12, v104, v34, v28, &v70) >= 0 )
              goto LABEL_90;
LABEL_51:
            v7 = v77;
            v6 = (int *)v73;
            goto LABEL_131;
          }
        }
LABEL_130:
        v6 = (int *)v73;
        v7 = v77;
      }
    }
  }
LABEL_131:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  CoTaskMemFree(v79);
  if ( v6 )
    operator delete(v6);
  if ( v92 )
    operator delete(v92);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(*((_QWORD *)v5 + 17) + 64LL) + 600LL));
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v89, v55);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v90, v56);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v107);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v131);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v135);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v111);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v139);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v143);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v115);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v103);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v147);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v151);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v119);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v155);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v159);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v123);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v163);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v167);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v127);
  return 0;
}

```

## disassembly

```asm
0x180008d6c  mov     [rsp-8+arg_10], rbx
0x180008d71  push    rbp
0x180008d72  push    rsi
0x180008d73  push    rdi
0x180008d74  push    r12
0x180008d76  push    r13
0x180008d78  push    r14
0x180008d7a  push    r15
0x180008d7c  lea     rbp, [rsp-1150h]
0x180008d84  mov     eax, 1260h
0x180008d89  call    _alloca_probe
0x180008d8e  sub     rsp, rax
0x180008d91  mov     rax, cs:__security_cookie
0x180008d98  xor     rax, rsp
0x180008d9b  mov     [rbp+1180h+var_40], rax
0x180008da2  mov     rbx, rdx
0x180008da5  mov     r14, rcx
0x180008da8  mov     [rbp+1180h+var_1168], rcx
0x180008dac  mov     rax, [rcx+88h]
0x180008db3  mov     rcx, [rax+40h]
0x180008db7  add     rcx, 258h; lpCriticalSection
0x180008dbe  call    cs:__imp_EnterCriticalSection
0x180008dc4  mov     edx, 80000000h
0x180008dc9  mov     [rbp+1180h+var_A80], edx
0x180008dcf  lea     rax, [rbp+1180h+var_A78]
0x180008dd6  mov     [rbp+1180h+var_A88], rax
0x180008ddd  xor     edi, edi
0x180008ddf  mov     [rbp+1180h+var_A78], di
0x180008de6  lea     rcx, ??_7?$CQuickStringW@$0GE@@@6B@; const CQuickStringW<100>::`vftable'
0x180008ded  mov     [rbp+1180h+var_A90], rcx
0x180008df4  mov     [rbp+1180h+var_120], edx
0x180008dfa  lea     rax, [rbp+1180h+var_118]
0x180008e01  mov     [rbp+1180h+var_128], rax
0x180008e08  mov     [rbp+1180h+var_118], di
0x180008e0f  mov     [rbp+1180h+var_130], rcx
0x180008e16  mov     [rbp+1180h+var_210], edx
0x180008e1c  lea     rax, [rbp+1180h+var_208]
0x180008e23  mov     [rbp+1180h+var_218], rax
0x180008e2a  mov     [rbp+1180h+var_208], di
0x180008e31  mov     [rbp+1180h+var_220], rcx
0x180008e38  mov     [rbp+1180h+var_B70], edx
0x180008e3e  lea     rax, [rbp+1180h+var_B68]
0x180008e45  mov     [rbp+1180h+var_B78], rax
0x180008e4c  mov     [rbp+1180h+var_B68], di
0x180008e53  mov     [rbp+1180h+var_B80], rcx
0x180008e5a  mov     [rbp+1180h+var_300], edx
0x180008e60  lea     rax, [rbp+1180h+var_2F8]
0x180008e67  mov     [rbp+1180h+var_308], rax
0x180008e6e  mov     [rbp+1180h+var_2F8], di
0x180008e75  mov     [rbp+1180h+var_310], rcx
0x180008e7c  mov     [rbp+1180h+var_3F0], edx
0x180008e82  lea     rax, [rbp+1180h+var_3E8]
0x180008e89  mov     [rbp+1180h+var_3F8], rax
0x180008e90  mov     [rbp+1180h+var_3E8], di
0x180008e97  mov     [rbp+1180h+var_400], rcx
0x180008e9e  mov     [rbp+1180h+var_C60], edx
0x180008ea4  lea     rax, [rbp+1180h+var_C58]
0x180008eab  mov     [rbp+1180h+var_C68], rax
0x180008eb2  mov     [rbp+1180h+var_C58], di
0x180008eb9  mov     [rbp+1180h+var_C70], rcx
0x180008ec0  mov     [rbp+1180h+var_4E0], edx
0x180008ec6  lea     rax, [rbp+1180h+var_4D8]
0x180008ecd  mov     [rbp+1180h+var_4E8], rax
0x180008ed4  mov     [rbp+1180h+var_4D8], di
0x180008edb  mov     [rbp+1180h+var_4F0], rcx
0x180008ee2  mov     [rbp+1180h+var_5D0], edx
0x180008ee8  lea     rax, [rbp+1180h+var_5C8]
0x180008eef  mov     [rbp+1180h+var_5D8], rax
0x180008ef6  mov     [rbp+1180h+var_5C8], di
0x180008efd  mov     [rbp+1180h+var_5E0], rcx
0x180008f04  mov     [rbp+1180h+var_1020], edx
0x180008f0a  lea     rax, [rbp+1180h+var_1018]
0x180008f11  mov     [rbp+1180h+var_1028], rax
0x180008f18  mov     [rbp+1180h+var_1018], di
0x180008f1f  mov     [rbp+1180h+var_1030], rcx
0x180008f26  mov     [rbp+1180h+var_D50], edx
0x180008f2c  lea     rax, [rbp+1180h+var_D48]
0x180008f33  mov     [rbp+1180h+var_D58], rax
0x180008f3a  mov     [rbp+1180h+var_D48], di
0x180008f41  mov     [rbp+1180h+var_D60], rcx
0x180008f48  mov     [rbp+1180h+var_6C0], edx
0x180008f4e  lea     rax, [rbp+1180h+var_6B8]
0x180008f55  mov     [rbp+1180h+var_6C8], rax
0x180008f5c  mov     [rbp+1180h+var_6B8], di
0x180008f63  mov     [rbp+1180h+var_6D0], rcx
0x180008f6a  mov     [rbp+1180h+var_7B0], edx
0x180008f70  lea     rax, [rbp+1180h+var_7A8]
0x180008f77  mov     [rbp+1180h+var_7B8], rax
0x180008f7e  mov     [rbp+1180h+var_7A8], di
0x180008f85  mov     [rbp+1180h+var_7C0], rcx
0x180008f8c  mov     [rbp+1180h+var_E40], edx
0x180008f92  lea     rax, [rbp+1180h+var_E38]
0x180008f99  mov     [rbp+1180h+var_E48], rax
0x180008fa0  mov     [rbp+1180h+var_E38], di
0x180008fa7  mov     [rbp+1180h+var_E50], rcx
0x180008fae  mov     [rbp+1180h+var_8A0], edx
0x180008fb4  lea     rax, [rbp+1180h+var_898]
0x180008fbb  mov     [rbp+1180h+var_8A8], rax
0x180008fc2  mov     [rbp+1180h+var_898], di
0x180008fc9  mov     [rbp+1180h+var_8B0], rcx
0x180008fd0  mov     [rbp+1180h+var_990], edx
0x180008fd6  lea     rax, [rbp+1180h+var_988]
0x180008fdd  mov     [rbp+1180h+var_998], rax
0x180008fe4  mov     [rbp+1180h+var_988], di
0x180008feb  mov     [rbp+1180h+var_9A0], rcx
0x180008ff2  mov     [rbp+1180h+var_F30], edx
0x180008ff8  lea     rax, [rbp+1180h+var_F28]
0x180008fff  mov     [rbp+1180h+Src], rax
0x180009006  mov     [rbp+1180h+var_F28], di
0x18000900d  mov     [rbp+1180h+var_F40], rcx
0x180009014  mov     [rbp+1180h+var_1180], rdi
0x180009018  mov     [rbp+1180h+var_115C], rdi
0x18000901c  mov     [rbp+1180h+var_1154], edi
0x18000901f  xorps   xmm0, xmm0
0x180009022  movdqu  [rbp+1180h+var_1148], xmm0
0x180009027  mov     [rbp+1180h+pv], rdi
0x18000902b  mov     [rbp+1180h+var_1160], edi
0x18000902e  mov     [rbp+1180h+var_1150], rdi
0x180009032  mov     r13d, edi
0x180009035  mov     [rbp+1180h+var_11E8], rdi
0x180009039  mov     [rbp+1180h+var_1170], rdi
0x18000903d  mov     [rbp+1180h+var_11C0], rdi
0x180009041  mov     dword ptr [rbp+1180h+var_1120+0Ch], edi
0x180009044  movdqu  xmmword ptr [rbp+1180h+var_1120+1Ch], xmm0
0x180009049  mov     dword ptr [rbp+1180h+var_1120.pRecoContext+4], edi
0x18000904f  mov     [rbp+1180h+var_11FD], dil
0x180009053  mov     [rbp+1180h+var_11A0], edi
0x180009056  xor     edx, edx; Val
0x180009058  mov     r8d, 0B8h; Size
0x18000905e  lea     rcx, [rbp+1180h+var_10F0]; void *
0x180009065  call    memset_0
0x18000906a  mov     r12d, edi
0x18000906d  mov     eax, [rbx+4]
0x180009070  mov     [rbp+1180h+var_119C], eax
0x180009073  mov     [rbp+1180h+var_1120.ulStartElement], eax
0x180009076  mov     eax, [rbx+8]
0x180009079  mov     [rbp+1180h+var_11B8], eax
0x18000907c  mov     [rbp+1180h+var_1120.cElements], eax
0x18000907f  mov     eax, [rbx+0Ch]
0x180009082  mov     [rbp+1180h+var_1120.ulRequestAltCount], eax
0x180009085  mov     edi, [rbx+10h]
0x180009088  mov     [rbp+1180h+var_1120.cbResultExtra], edi
0x18000908b  mov     eax, [rbx+14h]
0x18000908e  mov     [rbp+1180h+var_11A8], eax
0x180009091  lea     r15, [rbx+18h]
0x180009095  mov     qword ptr [rbp+1180h+var_1190], r15
0x180009099  mov     [rbp+1180h+var_1120.pvResultExtra], r15
0x18000909d  xor     ebx, ebx
0x18000909f  mov     [rbp+1180h+var_1188], rbx
0x1800090a3  lea     rax, [rbp+1180h+var_1188]
0x1800090a7  mov     [rsp+1290h+ppv], rax; ppv
0x1800090ac  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x1800090b3  xor     edx, edx; pUnkOuter
0x1800090b5  lea     r8d, [r12+17h]; dwClsContext
0x1800090ba  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x1800090c1  call    cs:__imp_CoCreateInstance
0x1800090c7  test    eax, eax
0x1800090c9  js      loc_180009B46
0x1800090cf  lea     ebx, [rdi+7]
0x1800090d2  mov     ecx, 0FFFFFFF8h
0x1800090d7  and     rbx, rcx
0x1800090da  add     rbx, r15
0x1800090dd  mov     esi, [rbx]
0x1800090df  mov     rcx, [rbp+1180h+var_1188]
0x1800090e3  mov     rax, [rcx]
0x1800090e6  mov     rdx, rbx
0x1800090e9  mov     rax, [rax+40h]
0x1800090ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f2  xor     ecx, ecx
0x1800090f4  test    eax, eax
0x1800090f6  js      loc_180009B46
0x1800090fc  mov     r12, [rbp+1180h+var_1188]
0x180009100  mov     [rbp+1180h+var_11D0], r12
0x180009104  mov     [rbp+1180h+var_1188], rcx
0x180009108  mov     [rbp+1180h+var_1120.pPhrase], r12
0x18000910f  mov     rax, [r12]
0x180009113  lea     rdx, [rbp+1180h+var_11C0]
0x180009117  mov     rcx, r12
0x18000911a  mov     rax, [rax+18h]
0x18000911e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009123  xor     ecx, ecx
0x180009125  test    eax, eax
0x180009127  js      loc_180009B46
0x18000912d  mov     [rbp+1180h+var_11F0], cl
0x180009130  mov     [rbp+1180h+var_11F8], rcx
0x180009134  lea     rdx, [rbx+rsi]
0x180009138  lea     rcx, [rbp+1180h+var_1030]
0x18000913f  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x180009144  or      r12, 0FFFFFFFFFFFFFFFFh
0x180009148  test    edi, edi
0x18000914a  jz      loc_180009229
0x180009150  mov     rdx, r15; struct LATTICE_HEADER *
0x180009153  lea     rcx, [rbp+1180h+var_10F0]; struct LATTICE *
0x18000915a  call    ?ReconstructInternalPointers@@YAXPEAULATTICE@@PEAULATTICE_HEADER@@@Z; ReconstructInternalPointers(LATTICE *,LATTICE_HEADER *)
0x18000915f  lea     r9, [rbp+1180h+var_10F0]; struct LATTICE *
0x180009166  lea     r8, [rbp+1180h+var_11A0]; unsigned int *
0x18000916a  lea     rdx, [rbp+1180h+var_1170]; struct LATTICE_NODE ***
0x18000916e  lea     rcx, [rbp+1180h+var_11E8]; int **
0x180009172  call    ?BuildElementArrays@@YAJPEAPEAHPEAPEAPEAULATTICE_NODE@@PEAKPEAULATTICE@@@Z; BuildElementArrays(int * *,LATTICE_NODE * * *,ulong *,LATTICE *)
0x180009177  xor     edi, edi
0x180009179  mov     r13, [rbp+1180h+var_11E8]
0x18000917d  test    eax, eax
0x18000917f  js      loc_180009220
0x180009185  mov     [rbp+1180h+var_11FF], dil
0x180009189  mov     ecx, edi
0x18000918b  lea     ebx, [rdi+1]
0x18000918e  mov     r8d, [rbp+1180h+var_11A0]
0x180009192  test    r8d, r8d
0x180009195  jz      short loc_1800091AC
0x180009197  mov     eax, ecx
0x180009199  cmp     [r13+rax*4+0], ecx
0x18000919e  jnz     short loc_1800091A9
0x1800091a0  add     ecx, ebx
0x1800091a2  cmp     ecx, r8d
0x1800091a5  jb      short loc_180009197
0x1800091a7  jmp     short loc_1800091AC
0x1800091a9  mov     [rbp+1180h+var_11FF], bl
0x1800091ac  movups  xmm0, xmmword ptr [r15+10h]
0x1800091b1  movdqu  xmmword ptr [rbp+1180h+var_1130.Data1], xmm0
0x1800091b6  lea     rdx, [rbp+1180h+var_1130]; struct _GUID
0x1800091ba  mov     rcx, [r14+3B8h]; this
0x1800091c1  call    ?FindRecentReco@CHistory@@QEAAPEAVCRecentReco@@U_GUID@@@Z; CHistory::FindRecentReco(_GUID)
0x1800091c6  mov     rsi, rax
0x1800091c9  test    rax, rax
0x1800091cc  jz      short loc_1800091D4
0x1800091ce  mov     r9, [rax+28h]
0x1800091d2  jmp     short loc_1800091D7
0x1800091d4  mov     r9, rdi; struct CStreamPair *
0x1800091d7  mov     rdx, r13; int *
0x1800091da  lea     rcx, [rbp+1180h+var_1120]; struct tagSPPHRASEALTREQUEST *
0x1800091de  call    ?MarkWildCardsAndCancelRecos@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAHKPEAVCStreamPair@@@Z; MarkWildCardsAndCancelRecos(tagSPPHRASEALTREQUEST *,int *,ulong,CStreamPair *)
0x1800091e3  test    eax, eax
0x1800091e5  js      short loc_180009220
0x1800091e7  test    rsi, rsi
0x1800091ea  jz      short loc_180009237
0x1800091ec  mov     rax, [rsi+28h]
0x1800091f0  test    rax, rax
0x1800091f3  jz      short loc_180009237
0x1800091f5  mov     r13b, [rax+228h]
0x1800091fc  mov     [rbp+1180h+var_11F0], r13b
0x180009200  test    r13b, r13b
0x180009203  jz      short loc_180009237
0x180009205  lea     rcx, [rax+28h]
0x180009209  mov     rax, r12
0x18000920c  inc     rax
0x18000920f  cmp     [rcx+rax*2], di
0x180009213  jnz     short loc_18000920C
0x180009215  test    rax, rax
0x180009218  jz      short loc_180009237
0x18000921a  mov     [rbp+1180h+var_11F8], rcx
0x18000921e  jmp     short loc_180009237
0x180009220  mov     r12, [rbp+1180h+var_11D0]
0x180009224  jmp     loc_180009B48
0x180009229  xor     edi, edi
0x18000922b  mov     qword ptr [rbp+1180h+var_1190], rdi
0x18000922f  lea     ebx, [rdi+1]
0x180009232  mov     [rbp+1180h+var_11FF], bl
0x180009235  mov     esi, edi
0x180009237  mov     [rbp+1180h+var_1178], rdi
0x18000923b  mov     [rbp+1180h+var_1200], dil
0x18000923f  mov     [rbp+1180h+var_11A4], edi
0x180009242  mov     r9d, [rbp+1180h+var_1020]
0x180009249  or      r15d, 0FFFFFFFFh
0x18000924d  mov     [rbp+1180h+var_1198], r15d
0x180009251  mov     edx, 7FFFFFFFh
0x180009256  test    edx, r9d
0x180009259  jnz     short loc_180009263
0x18000925b  mov     [rbp+1180h+var_11FE], bl
0x18000925e  jmp     loc_1800098AC
0x180009263  mov     rax, [rbp+1180h+var_11C0]
0x180009267  cmp     dword ptr [rax+40h], 0
0x18000926b  jbe     loc_1800092F7
0x180009271  mov     r14d, [rbp+1180h+var_119C]
0x180009275  mov     r15d, [rbp+1180h+var_11B8]
0x180009279  cmp     edi, r14d
0x18000927c  jnz     short loc_18000929D
0x18000927e  mov     rdx, [rbp+1180h+var_1028]
0x180009285  lea     rcx, [rbp+1180h+var_F40]
0x18000928c  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x180009291  test    r15d, r15d
0x180009294  jz      short loc_1800092BC
0x180009296  dec     edi
0x180009298  add     edi, r15d
0x18000929b  jmp     short loc_1800092BC
0x18000929d  mov     eax, edi
0x18000929f  imul    rcx, rax, 38h ; '8'
0x1800092a3  mov     rax, [rbp+1180h+var_11C0]
0x1800092a7  mov     rdx, [rax+68h]
0x1800092ab  mov     rdx, [rcx+rdx+18h]
0x1800092b0  lea     rcx, [rbp+1180h+var_F40]
0x1800092b7  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800092bc  inc     edi
0x1800092be  mov     rax, [rbp+1180h+var_11C0]
0x1800092c2  cmp     edi, [rax+40h]
0x1800092c5  jnb     short loc_1800092DA
0x1800092c7  lea     rdx, strIn; " "
0x1800092ce  lea     rcx, [rbp+1180h+var_F40]
0x1800092d5  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x1800092da  mov     rax, [rbp+1180h+var_11C0]
0x1800092de  cmp     edi, [rax+40h]
  ... truncated ...
```
