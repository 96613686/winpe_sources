# CDecoder::AttachPhraseBuilder(CPhrase *,LATTICE *,bool)

- ea: `0x180076ba8`
- end: `0x1800777cc`
- name: `?AttachPhraseBuilder@CDecoder@@QEAAJPEAVCPhrase@@PEAULATTICE@@_N@Z`
- size: `3108`
- prototype: `__int64 __fastcall(CDecoder *__hidden this, struct CPhrase *, struct LATTICE *, bool)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008433c`

## callees

- `0x180002470`
- `0x180002aac`
- `0x180002db8`
- `0x1800034b0`
- `0x1800040b8`
- `0x18000614c`
- `0x180006abc`
- `0x180007378`
- `0x18004c4d8`
- `0x18004e0a8`
- `0x180052960`
- `0x1800765d0`
- `0x180076ba8`
- `0x1800791b4`
- `0x180079f78`
- `0x18007a7a8`
- `0x18007ac88`
- `0x18007cefc`
- `0x1800c77ac`
- `0x1800c77d8`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180077143`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18007716e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180077199`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180077143`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18007716e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180077199`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800776a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800776a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDecoder::AttachPhraseBuilder(CDecoder *this, struct CPhrase *a2, struct LATTICE *a3, char a4)
{
  _BYTE *v7; // rdx
  unsigned int v8; // r9d
  struct SPPATHENTRY *v9; // r12
  unsigned int v10; // r15d
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  struct SPPHRASEELEMENT *v13; // rsi
  HRESULT inited; // ebx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdi
  int v18; // esi
  int v19; // eax
  unsigned int v20; // r10d
  int v21; // edx
  int v22; // r9d
  unsigned __int16 v23; // r11
  unsigned int v24; // eax
  __int64 v25; // rdi
  _BYTE *v26; // r8
  __int64 v27; // rdi
  unsigned int v28; // esi
  __int64 v29; // rdx
  _BYTE *v30; // r11
  __int64 v31; // rsi
  __int64 v32; // r12
  struct SPPHRASEELEMENT *v33; // rdi
  unsigned int v34; // eax
  CDecoder *v35; // rcx
  __int16 v36; // r9
  struct SPPHRASEELEMENT *v37; // rdi
  __int64 v38; // rdx
  BSTR v39; // rax
  __int64 v40; // rdx
  BSTR v41; // rax
  __int64 v42; // rdx
  BSTR v43; // rax
  unsigned int v44; // edi
  __int64 v45; // rcx
  _BYTE *v46; // rdx
  __int64 v47; // r8
  int v48; // edx
  int v49; // r10d
  unsigned __int64 v50; // rdx
  ULONG v51; // r9d
  ULONG v52; // edx
  struct SPPHRASEELEMENT *v53; // r8
  __int64 v54; // rax
  __int64 v55; // rdx
  int v56; // edi
  BOOL v57; // esi
  ULONGLONG v58; // r12
  int v59; // ecx
  struct ISpPhraseBuilder *v60; // rax
  unsigned int i; // edi
  LPVOID *ppv; // [rsp+20h] [rbp-F0h]
  bool v64; // [rsp+30h] [rbp-E0h]
  char v65; // [rsp+90h] [rbp-80h]
  struct SPPHRASEELEMENT *v66; // [rsp+98h] [rbp-78h] BYREF
  char v67; // [rsp+A0h] [rbp-70h]
  char v68; // [rsp+A1h] [rbp-6Fh]
  unsigned int v69; // [rsp+A4h] [rbp-6Ch]
  struct SPPATHENTRY *v70; // [rsp+A8h] [rbp-68h]
  int v71; // [rsp+B0h] [rbp-60h]
  unsigned int v72; // [rsp+B4h] [rbp-5Ch]
  __int16 v73[2]; // [rsp+B8h] [rbp-58h] BYREF
  unsigned int v74; // [rsp+BCh] [rbp-54h]
  unsigned int v75; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v76; // [rsp+C8h] [rbp-48h] BYREF
  int v77; // [rsp+D0h] [rbp-40h]
  unsigned int v78; // [rsp+D4h] [rbp-3Ch]
  struct IMSASRLocaleHandler *v79; // [rsp+D8h] [rbp-38h]
  _BYTE *v80; // [rsp+E0h] [rbp-30h]
  ULONGLONG v81; // [rsp+E8h] [rbp-28h]
  struct CHeap *v82; // [rsp+F0h] [rbp-20h] BYREF
  void *v83; // [rsp+F8h] [rbp-18h] BYREF
  unsigned int v84[2]; // [rsp+100h] [rbp-10h] BYREF
  unsigned int v85; // [rsp+108h] [rbp-8h]
  struct PATH_TRANSITION *v86; // [rsp+110h] [rbp+0h]
  struct SPPATHENTRY *v87; // [rsp+118h] [rbp+8h] BYREF
  struct ISpPhraseBuilder *v88; // [rsp+120h] [rbp+10h] BYREF
  __int64 v89; // [rsp+128h] [rbp+18h] BYREF
  int v90; // [rsp+130h] [rbp+20h]
  struct CPhrase *v91; // [rsp+138h] [rbp+28h]
  __int64 v92; // [rsp+140h] [rbp+30h]
  __int64 v93; // [rsp+148h] [rbp+38h] BYREF
  struct SPPARSEINFO v94; // [rsp+150h] [rbp+40h] BYREF
  int v95; // [rsp+1A0h] [rbp+90h] BYREF
  __int16 v96; // [rsp+1A4h] [rbp+94h]
  ULONGLONG v97; // [rsp+1B8h] [rbp+A8h]
  int v98; // [rsp+1C0h] [rbp+B0h]
  unsigned int v99; // [rsp+1E0h] [rbp+D0h]
  struct SPPHRASEELEMENT *v100; // [rsp+208h] [rbp+F8h]
  GUID v101; // [rsp+220h] [rbp+110h]
  GUID v102; // [rsp+270h] [rbp+160h] BYREF
  void **v103; // [rsp+280h] [rbp+170h] BYREF
  OLECHAR *strIn; // [rsp+288h] [rbp+178h]
  unsigned int v105; // [rsp+290h] [rbp+180h]
  __int16 v106; // [rsp+298h] [rbp+188h] BYREF
  void **v107; // [rsp+370h] [rbp+260h] BYREF
  OLECHAR *v108; // [rsp+378h] [rbp+268h]
  unsigned int v109; // [rsp+380h] [rbp+270h]
  __int16 v110; // [rsp+388h] [rbp+278h] BYREF
  void **v111; // [rsp+460h] [rbp+350h] BYREF
  OLECHAR *v112; // [rsp+468h] [rbp+358h]
  unsigned int v113; // [rsp+470h] [rbp+360h]
  __int16 v114; // [rsp+478h] [rbp+368h] BYREF

  v68 = a4;
  v91 = a2;
  v7 = (_BYTE *)*((_QWORD *)a2 + 104);
  v80 = v7;
  v8 = *((_DWORD *)a2 + 212);
  v85 = v8;
  v88 = 0;
  v79 = *(struct IMSASRLocaleHandler **)(*((_QWORD *)this + 10) + 456LL);
  v113 = 0x80000000;
  v112 = (OLECHAR *)&v114;
  v114 = 0;
  v111 = &CQuickStringW<384>::`vftable';
  v109 = 0x80000000;
  v108 = (OLECHAR *)&v110;
  v110 = 0;
  v107 = &CQuickStringW<100>::`vftable';
  v82 = (struct CHeap *)&g_heap;
  v86 = 0;
  v83 = 0;
  *(_QWORD *)v84 = 0;
  v93 = 0;
  v89 = 0;
  v105 = 0x80000000;
  strIn = (OLECHAR *)&v106;
  v106 = 0;
  v103 = &CQuickStringW<100>::`vftable';
  v9 = 0;
  v70 = 0;
  v87 = 0;
  v10 = 0;
  v11 = 0;
  if ( !v8 )
    goto LABEL_122;
  do
  {
    v12 = v10 + 1;
    if ( (*v7 & 3) != 2 )
      v12 = v10;
    v10 = v12;
    ++v11;
    v7 += 8;
  }
  while ( v11 < v8 );
  if ( !v12 )
  {
LABEL_122:
    inited = 1;
    goto LABEL_123;
  }
  v13 = (struct SPPHRASEELEMENT *)CWinHeap::Alloc(*((CWinHeap **)this + 9), 56LL * v12, 1);
  v66 = v13;
  if ( !v13 )
  {
    inited = -2147024882;
    goto LABEL_123;
  }
  v102 = 0;
  v73[0] = 0;
  inited = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int16 *))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL) + 88LL))(
             *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
             &v102,
             v73);
  if ( inited < 0 )
    goto LABEL_118;
  v16 = *((_QWORD *)this + 65);
  v76 = *(_QWORD *)(v16 + 120);
  v17 = *(unsigned int *)(v16 + 132);
  v75 = *(_DWORD *)(v16 + 128);
  v18 = *(_DWORD *)(v16 + 984);
  v19 = *(_DWORD *)(v16 + 988) + 10;
  if ( v19 >= *((_DWORD *)a3 + 29) + 1 )
    v19 = *((_DWORD *)a3 + 29) + 1;
  v90 = v19;
  if ( (*((_BYTE *)a3 + 60) & 3) != 0 )
  {
    LOBYTE(v15) = 0;
    v65 = 0;
    v67 = 1;
    if ( v68 )
    {
      inited = (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, __int64, __int64 *, _QWORD))(*(_QWORD *)v79 + 112LL))(
                 v79,
                 4096,
                 &v89,
                 0);
      if ( inited < 0 )
      {
LABEL_99:
        v13 = v66;
        goto LABEL_118;
      }
      LOBYTE(v15) = 0;
    }
  }
  else
  {
    LOBYTE(v15) = 1;
    v65 = 1;
    v67 = 0;
  }
  v20 = 0;
  v72 = 0;
  v21 = 0;
  v69 = 0;
  v92 = v17;
  v81 = v76 + v17 * (v18 + v75);
  if ( (_BYTE)v15 )
    *((_DWORD *)a3 + 18) = 0;
  v22 = -1;
  v74 = -1;
  v77 = -1;
  v23 = -1;
  v71 = 0xFFFF;
  v24 = 0;
  v78 = 0;
  while ( 1 )
  {
    v25 = v24;
    v26 = v80;
    if ( (_BYTE)v15 && (v80[8 * v24] & 1) != 0 )
    {
      v15 = 5LL * *(unsigned __int16 *)&v80[8 * v24 + 2];
      v27 = *(unsigned int *)(*((_QWORD *)a3 + 19) + 40LL * *(unsigned __int16 *)&v80[8 * v24 + 2] + 4);
      if ( *(_DWORD *)(*((_QWORD *)a3 + 22) + 4 * v27) )
      {
        while ( 1 )
        {
          v28 = v20 + 1;
          inited = EnsureArrayVoid(&v83, 0x10u, v20 + 1, v84, v84[1], v82, v64);
          if ( inited < 0 )
            goto LABEL_84;
          v29 = 2LL * v72;
          v30 = v83;
          v86 = (struct PATH_TRANSITION *)v83;
          v15 = *(unsigned int *)(*((_QWORD *)a3 + 22) + 4 * v27);
          *((_QWORD *)v83 + v29) = v15;
          v30[8 * v29 + 8] = 0;
          v20 = v28;
          v72 = v28;
          v27 = (unsigned int)(v27 + 1);
          if ( !*(_DWORD *)(*((_QWORD *)a3 + 22) + 4 * v27) )
          {
            v21 = v69;
            goto LABEL_25;
          }
        }
      }
      goto LABEL_81;
    }
    v31 = 116LL * *(unsigned __int16 *)&v80[8 * v24 + 2];
    v32 = *((_QWORD *)a3 + 18);
    if ( (v80[8 * v24] & 4) != 0 )
    {
      if ( *(_DWORD *)(v31 + v32 + 96) == -1 )
      {
        if ( v22 == -1 )
          goto LABEL_81;
      }
      else
      {
        v74 = *(_DWORD *)(v31 + v32 + 96);
      }
      if ( (*(_DWORD *)(v31 + v32 + 8) & 0x220) == 0x20 )
      {
        if ( (v80[8 * v24] & 0x10) == 0 )
        {
          if ( v23 == 0xFFFF )
          {
            v23 = *(_WORD *)(v31 + v32 + 4);
            v71 = v23;
          }
          goto LABEL_81;
        }
        v33 = v66;
        inited = CDecoder::InitElementBSTRs(
                   (CDecoder *)v15,
                   &v66[v21],
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 21) + 2LL * *(unsigned int *)(v31 + v32 + 12)),
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 21) + 2LL * *(unsigned int *)(v31 + v32 + 16)),
                   v79);
        if ( inited < 0 )
        {
          v13 = v66;
          goto LABEL_117;
        }
        LOBYTE(v15) = v65;
        v21 = v69;
        v26 = v80;
        v23 = v71;
        goto LABEL_63;
      }
      if ( (v80[8 * v24] & 8) != 0 )
      {
        v77 = *(_DWORD *)(v31 + v32 + 20);
        v113 &= 0x80000000;
        *v112 = 0;
        v105 &= 0x80000000;
        *strIn = 0;
        if ( (*(_DWORD *)(v31 + v32 + 8) & 0x100) != 0 )
        {
          v109 &= 0x80000000;
          *v108 = 0;
        }
      }
      v34 = *(_DWORD *)(v31 + v32 + 16);
      if ( v34 )
      {
        CQuickStringW<384>::Append(&v111, *((_QWORD *)a3 + 21) + 2LL * v34);
        v26 = v80;
      }
      if ( (*(_DWORD *)(v31 + v32 + 8) & 0x100) != 0 )
      {
        if ( (v26[8 * v25] & 8) == 0 )
        {
          inited = CQuickStringW<100>::Append(&v107, L" ");
          if ( inited < 0 )
            goto LABEL_84;
        }
        memset(&v94, 0, 56);
        inited = CDecoder::InitElementBSTRs(
                   (CDecoder *)*(unsigned int *)(v31 + v32 + 12),
                   (struct SPPHRASEELEMENT *)&v94,
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 21) + 2LL * *(unsigned int *)(v31 + v32 + 12)),
                   0,
                   v79);
        if ( inited < 0 )
          goto LABEL_84;
        inited = CQuickStringW<100>::Append(&v107, *(_QWORD *)&v94.ulAudioSize);
        FreeElementBSTRs((struct SPPHRASEELEMENT *)&v94);
        if ( inited < 0 )
          goto LABEL_84;
        v26 = v80;
      }
      if ( (v26[8 * v25] & 0x10) == 0 )
      {
        v21 = v69;
        v23 = v71;
        goto LABEL_81;
      }
      inited = CQuickStringTBase::Append(
                 (CQuickStringTBase *)&v103,
                 (void *)(*((_QWORD *)a3 + 21) + 2LL * v77),
                 *(_DWORD *)(v31 + v32 + 20) + *(_DWORD *)(v31 + v32 + 24) - v77,
                 0x64u,
                 (unsigned __int64)ppv);
      if ( inited < 0 )
        goto LABEL_84;
      TraceTag((struct CDebugTag *)&g_tagLatticeTB, L">>> add word:  [%s]\n", strIn, 0);
      v37 = &v66[v69];
      if ( (*(_DWORD *)(v31 + v32 + 8) & 0x100) != 0 )
      {
        v38 = -1;
        do
          ++v38;
        while ( strIn[v38] != v36 );
        v39 = SysAllocStringLen(strIn, v38);
        v37->pszDisplayText = v39;
        if ( !v39 )
          goto LABEL_83;
        v40 = -1;
        do
          ++v40;
        while ( v108[v40] );
        v41 = SysAllocStringLen(v108, v40);
        v37->pszLexicalForm = v41;
        if ( !v41 )
          goto LABEL_83;
        v42 = -1;
        do
          ++v42;
        while ( v112[v42] );
        v43 = SysAllocStringLen(v112, v42);
        v37->pszPronunciation = v43;
        if ( !v43 )
        {
LABEL_83:
          inited = -2147024882;
LABEL_84:
          v13 = v66;
          goto LABEL_117;
        }
      }
      else
      {
        inited = CDecoder::InitElementBSTRs(v35, &v66[v69], strIn, v112, v79);
        if ( inited < 0 )
          goto LABEL_84;
      }
      LOBYTE(v15) = v65;
      v21 = v69;
      v26 = v80;
      v23 = v71;
    }
    v33 = v66;
LABEL_63:
    if ( (v26[8 * v78] & 2) != 0 )
    {
      if ( (v26[8 * v78] & 4) == 0 )
      {
        if ( (_BYTE)v15 )
        {
          v74 = *(_DWORD *)(v31 + v32 + 96);
          if ( v74 == -1 )
          {
            inited = -2147024809;
            goto LABEL_84;
          }
        }
        inited = CDecoder::InitElementBSTRs(
                   (CDecoder *)v15,
                   &v33[v21],
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 21) + 2LL * *(unsigned int *)(v31 + v32 + 12)),
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 21) + 2LL * *(unsigned int *)(v31 + v32 + 16)),
                   v79);
        if ( inited < 0 )
          goto LABEL_84;
      }
      if ( v65 )
      {
        v44 = v72 + 1;
        inited = EnsureArrayVoid(&v83, 0x10u, v72 + 1, v84, v84[1], v82, v64);
        if ( inited < 0 )
          goto LABEL_84;
        v45 = 2LL * v72;
        v46 = v83;
        v86 = (struct PATH_TRANSITION *)v83;
        *((_QWORD *)v83 + v45) = v74;
        v46[8 * v45 + 8] = 1;
        v72 = v44;
        v74 = -1;
        v77 = -1;
      }
      if ( (*((_BYTE *)a3 + 60) & 8) != 0 || *((_BYTE *)this + 2595) )
      {
        v51 = 0;
        v52 = 0;
      }
      else
      {
        if ( (_WORD)v71 == 0xFFFF || (*(_DWORD *)(v31 + v32 + 8) & 0x220) != 0x20 )
        {
          v47 = *((_QWORD *)this + 65);
          v48 = *(_DWORD *)(v47 + 128) + *(__int16 *)(v31 + v32 + 4);
        }
        else
        {
          v47 = *((_QWORD *)this + 65);
          v48 = (__int16)v71 + *(_DWORD *)(v47 + 128);
          v71 = -1;
        }
        v49 = *((_DWORD *)a3 + 28);
        v50 = *(_QWORD *)(v47 + 120) + *(unsigned int *)(v47 + 132) * (unsigned __int64)(unsigned int)(v49 + v48);
        v51 = *(_DWORD *)(v47 + 120)
            + *(_DWORD *)(v47 + 132) * (v49 + *(_DWORD *)(v47 + 128) + *(__int16 *)(v31 + v32 + 6))
            - v50;
        v52 = v50 - v81;
      }
      v53 = v66;
      v15 = 56LL * v69;
      *(ULONG *)((char *)&v66->ulAudioStreamOffset + v15) = v52;
      *(ULONG *)((char *)&v53->ulAudioSizeBytes + v15) = v51;
      *(&v53->RequiredConfidence + v15) = (int)(*(_DWORD *)(v31 + v32 + 92) << 30) >> 30;
      *(&v53->ActualConfidence + v15) = 0;
      *(float *)((char *)&v53->SREngineConfidence + v15) = 0.64999998;
      *(_QWORD *)((char *)&v53->ulAudioTimeOffset + v15) = 0;
      *(&v53->bDisplayAttributes + v15) = 2;
      v21 = ++v69;
LABEL_25:
      v23 = v71;
    }
LABEL_81:
    v24 = v78 + 1;
    v78 = v24;
    if ( v24 >= v85 )
      break;
    LOBYTE(v15) = v65;
    v22 = v74;
    v20 = v72;
  }
  if ( v21 != v10 )
    goto LABEL_84;
  v54 = *((_QWORD *)this + 65);
  if ( (*(_DWORD *)(v54 + 1048) & 0x7FFFFFFF) != 0 )
    v55 = *(_QWORD *)(v54 + 1040);
  else
    v55 = 0;
  v13 = v66;
  inited = (*(__int64 (__fastcall **)(struct IMSASRLocaleHandler *, __int64, _QWORD, _QWORD, _DWORD, _DWORD, struct SPPHRASEELEMENT *, unsigned int, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v79 + 120LL))(
             v79,
             v55,
             0,
             *(unsigned int *)(v54 + 1104),
             *(_DWORD *)(v54 + 1108),
             0,
             v66,
             v10,
             0,
             0,
             0,
             0,
             0,
             0,
             0,
             0,
             0);
  if ( inited >= 0 )
  {
    v56 = v76 + v92 * (v75 + v90);
    if ( !v65 )
    {
      v58 = v81;
      goto LABEL_101;
    }
    v75 = 0;
    ATL::CComQIPtr<ISpSREngineCFGParser,&__s_GUID const _GUID_fa3cc7da_67d3_4f7a_93aa_5822b086c8ea>::CComQIPtr<ISpSREngineCFGParser,&__s_GUID const _GUID_fa3cc7da_67d3_4f7a_93aa_5822b086c8ea>(
      &v76,
      *(_QWORD *)(*((_QWORD *)this + 288) + 80LL));
    v57 = v76 != 0;
    ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v76);
    inited = CDecoder::CreatePathEntries(this, v66, v10, !v57, v86, v72, &v87, &v75);
    if ( inited < 0 )
    {
      v9 = v87;
      goto LABEL_99;
    }
    *(_QWORD *)&v94.cbSize = 80;
    *(&v94.ulSREnginePrivateDataSize + 1) = 0;
    *(&v94.fHypothesis + 1) = 0;
    v94.hRule = (SPRULEHANDLE)*((_QWORD *)v91 + 387);
    if ( (*((_BYTE *)a3 + 60) & 8) != 0 )
    {
      v94.ullAudioStreamPosition = 0;
      v94.ulAudioSize = 0;
      v58 = v81;
    }
    else
    {
      v58 = v81;
      v94.ullAudioStreamPosition = v81;
      v94.ulAudioSize = v56 - v81;
    }
    v94.cTransitions = v75;
    v94.fHypothesis = (*((unsigned __int8 *)a3 + 64) >> 1) & 1;
    v94.SREngineID = v102;
    v94.ulSREnginePrivateDataSize = 0;
    v94.pSREnginePrivateData = 0;
    v70 = v87;
    v94.pPath = v87;
    inited = CCFGLM::ParseFromTransitions(*((CCFGLM **)this + 288), &v94, v57, &v88);
    v13 = v66;
    if ( inited >= 0 )
    {
LABEL_101:
      if ( v67 )
      {
        if ( v68 )
        {
          v59 = v89;
          v76 = v89;
          if ( v89 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 8LL))(v89);
          CDecoder::MergePronStrings(v59, (_DWORD)v13, v10, (_DWORD)v79, (__int64)&v76);
        }
        memset_0(&v95, 0, 0xC8u);
        v95 = 160;
        if ( (*((_BYTE *)a3 + 60) & 8) != 0 || *((_BYTE *)this + 2595) )
        {
          v97 = 0;
          v98 = 0;
        }
        else
        {
          v97 = v58;
          v98 = v56 - v58;
        }
        v99 = v10;
        v96 = v73[0];
        v101 = v102;
        v100 = v13;
        v66 = 0;
        inited = CoCreateInstance(
                   &CLSID_SpPhraseBuilder,
                   0,
                   0x17u,
                   &GUID_88a3342a_0bed_4834_922b_88d43173162f,
                   (LPVOID *)&v66);
        if ( inited < 0
          || (inited = (*(__int64 (__fastcall **)(struct SPPHRASEELEMENT *, int *))(*(_QWORD *)&v66->ulAudioTimeOffset
                                                                                  + 56LL))(
                         v66,
                         &v95),
              inited < 0)
          || (inited = CDecoder::SetSLMGrammarInfo(
                         this,
                         (struct SPGRAMMARHANDLE__ *)*((unsigned int *)a3 + 18),
                         (struct ISpPhraseBuilder *)v66),
              inited < 0) )
        {
          ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v66);
          goto LABEL_117;
        }
        v60 = (struct ISpPhraseBuilder *)v66;
        v66 = 0;
        v88 = v60;
        ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v66);
      }
      *((_QWORD *)v91 + 3) = v88;
    }
  }
LABEL_117:
  v9 = v70;
LABEL_118:
  for ( i = 0; i < v10; ++i )
    FreeElementBSTRs(&v13[i]);
  CWinHeap::Free(*((CWinHeap **)this + 9), v13);
  if ( v9 )
    CWinHeap::Free(*((CWinHeap **)this + 9), v9);
LABEL_123:
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v103);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v89);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v93);
  CGrowableArrayVoid::~CGrowableArrayVoid((CGrowableArrayVoid *)&v82);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v107);
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v111);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180076ba8  mov     [rsp-8+arg_18], rbx
0x180076bad  push    rbp
0x180076bae  push    rsi
0x180076baf  push    rdi
0x180076bb0  push    r12
0x180076bb2  push    r13
0x180076bb4  push    r14
0x180076bb6  push    r15
0x180076bb8  lea     rbp, [rsp-680h]
0x180076bc0  sub     rsp, 790h
0x180076bc7  mov     rax, cs:__security_cookie
0x180076bce  xor     rax, rsp
0x180076bd1  mov     [rbp+6B0h+var_40], rax
0x180076bd8  mov     [rbp+6B0h+var_71F], r9b
0x180076bdc  mov     r13, r8
0x180076bdf  mov     rax, rdx
0x180076be2  mov     [rbp+6B0h+var_688], rdx
0x180076be6  mov     r14, rcx
0x180076be9  mov     rdx, [rdx+340h]
0x180076bf0  mov     [rbp+6B0h+var_6E0], rdx
0x180076bf4  mov     r9d, [rax+350h]
0x180076bfb  mov     [rbp+6B0h+var_6B8], r9d
0x180076bff  xor     ebx, ebx
0x180076c01  mov     [rbp+6B0h+var_6A0], rbx
0x180076c05  mov     rax, [rcx+50h]
0x180076c09  mov     rax, [rax+1C8h]
0x180076c10  mov     [rbp+6B0h+var_6E8], rax
0x180076c14  mov     r8d, 80000000h
0x180076c1a  mov     [rbp+6B0h+var_350], r8d
0x180076c21  lea     rax, [rbp+6B0h+var_348]
0x180076c28  mov     [rbp+6B0h+var_358], rax
0x180076c2f  mov     [rbp+6B0h+var_348], bx
0x180076c36  lea     rax, ??_7?$CQuickStringW@$0BIA@@@6B@; const CQuickStringW<384>::`vftable'
0x180076c3d  mov     [rbp+6B0h+var_360], rax
0x180076c44  mov     [rbp+6B0h+var_440], r8d
0x180076c4b  lea     rax, [rbp+6B0h+var_438]
0x180076c52  mov     [rbp+6B0h+var_448], rax
0x180076c59  mov     [rbp+6B0h+var_438], bx
0x180076c60  lea     rcx, ??_7?$CQuickStringW@$0GE@@@6B@; const CQuickStringW<100>::`vftable'
0x180076c67  mov     [rbp+6B0h+var_450], rcx
0x180076c6e  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x180076c75  mov     [rbp+6B0h+var_6D0], rax
0x180076c79  mov     [rbp+6B0h+var_6B0], rbx
0x180076c7d  mov     [rbp+6B0h+var_6C8], rbx
0x180076c81  mov     qword ptr [rbp+6B0h+var_6C0], rbx
0x180076c85  mov     [rbp+6B0h+var_678], rbx
0x180076c89  mov     [rbp+6B0h+var_698], rbx
0x180076c8d  mov     [rbp+6B0h+var_530], r8d
0x180076c94  lea     rax, [rbp+6B0h+var_528]
0x180076c9b  mov     [rbp+6B0h+strIn], rax
0x180076ca2  mov     [rbp+6B0h+var_528], bx
0x180076ca9  mov     [rbp+6B0h+var_540], rcx
0x180076cb0  mov     r12d, ebx
0x180076cb3  mov     [rbp+6B0h+var_718], rbx
0x180076cb7  mov     [rbp+6B0h+var_6A8], rbx
0x180076cbb  mov     r15d, ebx
0x180076cbe  mov     r8d, ebx
0x180076cc1  test    r9d, r9d
0x180076cc4  jz      loc_180077757
0x180076cca  mov     al, [rdx]
0x180076ccc  and     al, 3
0x180076cce  lea     ecx, [r15+1]
0x180076cd2  cmp     al, 2
0x180076cd4  cmovnz  ecx, r15d
0x180076cd8  mov     r15d, ecx
0x180076cdb  inc     r8d
0x180076cde  lea     rdx, [rdx+8]
0x180076ce2  cmp     r8d, r9d
0x180076ce5  jb      short loc_180076CCA
0x180076ce7  test    ecx, ecx
0x180076ce9  jz      loc_180077757
0x180076cef  imul    rdx, r15, 38h ; '8'; unsigned __int64
0x180076cf3  mov     r8b, 1; bool
0x180076cf6  mov     rcx, [r14+48h]; this
0x180076cfa  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x180076cff  mov     rsi, rax
0x180076d02  mov     [rbp+6B0h+var_728], rax
0x180076d06  test    rax, rax
0x180076d09  jnz     short loc_180076D15
0x180076d0b  mov     ebx, 8007000Eh
0x180076d10  jmp     loc_18007775C
0x180076d15  xorps   xmm0, xmm0
0x180076d18  movups  [rbp+6B0h+var_550], xmm0
0x180076d1f  mov     [rbp+6B0h+var_708], bx
0x180076d23  mov     rax, [r14+50h]
0x180076d27  mov     rcx, [rax+10h]
0x180076d2b  mov     rax, [rcx]
0x180076d2e  lea     r8, [rbp+6B0h+var_708]
0x180076d32  lea     rdx, [rbp+6B0h+var_550]
0x180076d39  mov     rax, [rax+58h]
0x180076d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d42  mov     ebx, eax
0x180076d44  xor     r9d, r9d
0x180076d47  test    eax, eax
0x180076d49  js      loc_180077718
0x180076d4f  mov     r8, [r14+208h]
0x180076d56  mov     rax, [r8+78h]
0x180076d5a  mov     [rbp+6B0h+var_6F8], rax
0x180076d5e  mov     edi, [r8+84h]
0x180076d65  mov     eax, [r8+80h]
0x180076d6c  mov     [rbp+6B0h+var_700], eax
0x180076d6f  mov     esi, [r8+3D8h]
0x180076d76  mov     edx, [r13+74h]
0x180076d7a  inc     edx
0x180076d7c  mov     eax, [r8+3DCh]
0x180076d83  add     eax, 0Ah
0x180076d86  cmp     eax, edx
0x180076d88  cmovge  eax, edx
0x180076d8b  mov     [rbp+6B0h+var_690], eax
0x180076d8e  test    byte ptr [r13+3Ch], 3
0x180076d93  jnz     short loc_180076DA0
0x180076d95  mov     cl, 1
0x180076d97  mov     [rbp+6B0h+var_730], cl
0x180076d9a  mov     [rbp+6B0h+var_720], r9b
0x180076d9e  jmp     short loc_180076DD9
0x180076da0  mov     cl, r9b
0x180076da3  mov     [rbp+6B0h+var_730], cl
0x180076da6  mov     [rbp+6B0h+var_720], 1
0x180076daa  cmp     [rbp+6B0h+var_71F], r9b
0x180076dae  jz      short loc_180076DD9
0x180076db0  mov     rcx, [rbp+6B0h+var_6E8]
0x180076db4  mov     rax, [rcx]
0x180076db7  lea     r8, [rbp+6B0h+var_698]
0x180076dbb  mov     edx, 1000h
0x180076dc0  mov     rax, [rax+70h]
0x180076dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076dc9  mov     ebx, eax
0x180076dcb  xor     r9d, r9d
0x180076dce  test    eax, eax
0x180076dd0  js      loc_1800775BB
0x180076dd6  mov     cl, r9b; this
0x180076dd9  mov     r10d, r9d
0x180076ddc  mov     [rbp+6B0h+var_70C], r9d
0x180076de0  mov     edx, r9d
0x180076de3  mov     [rbp+6B0h+var_71C], edx
0x180076de6  mov     [rbp+6B0h+var_680], rdi
0x180076dea  mov     r12d, [rbp+6B0h+var_700]
0x180076dee  add     r12d, esi
0x180076df1  imul    r12, rdi
0x180076df5  add     r12, [rbp+6B0h+var_6F8]
0x180076df9  mov     [rbp+6B0h+var_6D8], r12
0x180076dfd  xor     r12d, r12d
0x180076e00  test    cl, cl
0x180076e02  jz      short loc_180076E08
0x180076e04  mov     [r13+48h], r12d
0x180076e08  or      r9d, 0FFFFFFFFh
0x180076e0c  mov     [rbp+6B0h+var_704], r9d
0x180076e10  or      rax, 0FFFFFFFFFFFFFFFFh
0x180076e14  mov     [rbp+6B0h+var_6F0], eax
0x180076e17  movzx   r11d, ax
0x180076e1b  mov     [rbp+6B0h+var_710], r11d
0x180076e1f  mov     eax, r12d
0x180076e22  mov     [rbp+6B0h+var_6EC], eax
0x180076e25  mov     edi, eax
0x180076e27  mov     r8, [rbp+6B0h+var_6E0]
0x180076e2b  test    cl, cl
0x180076e2d  jz      loc_180076ED9
0x180076e33  test    byte ptr [r8+rdi*8], 1
0x180076e38  jz      loc_180076ED9
0x180076e3e  movzx   eax, word ptr [r8+rdi*8+2]
0x180076e44  lea     rcx, [rax+rax*4]
0x180076e48  mov     rax, [r13+98h]
0x180076e4f  mov     edi, [rax+rcx*8+4]
0x180076e53  mov     rax, [r13+0B0h]
0x180076e5a  cmp     [rax+rdi*4], r12d
0x180076e5e  jz      loc_1800773BB
0x180076e64  lea     esi, [r10+1]
0x180076e68  mov     rax, [rbp+6B0h+var_6D0]
0x180076e6c  mov     [rsp+7C0h+var_798], rax; struct CHeap *
0x180076e71  mov     eax, [rbp+6B0h+var_6C0+4]
0x180076e74  mov     dword ptr [rsp+7C0h+ppv], eax; unsigned int
0x180076e78  lea     r9, [rbp+6B0h+var_6C0]; unsigned int *
0x180076e7c  mov     r8d, esi; unsigned int
0x180076e7f  mov     edx, 10h; unsigned __int64
0x180076e84  lea     rcx, [rbp+6B0h+var_6C8]; void **
0x180076e88  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x180076e8d  mov     ebx, eax
0x180076e8f  test    eax, eax
0x180076e91  js      loc_1800773DD
0x180076e97  mov     edx, [rbp+6B0h+var_70C]
0x180076e9a  add     rdx, rdx
0x180076e9d  mov     r11, [rbp+6B0h+var_6C8]
0x180076ea1  mov     [rbp+6B0h+var_6B0], r11
0x180076ea5  mov     rax, [r13+0B0h]
0x180076eac  mov     ecx, [rax+rdi*4]
0x180076eaf  mov     [r11+rdx*8], rcx
0x180076eb3  mov     [r11+rdx*8+8], r12b
0x180076eb8  mov     r10d, esi
0x180076ebb  mov     [rbp+6B0h+var_70C], esi
0x180076ebe  inc     edi
0x180076ec0  mov     rax, [r13+0B0h]
0x180076ec7  cmp     [rax+rdi*4], r12d
0x180076ecb  jnz     short loc_180076E64
0x180076ecd  mov     edx, [rbp+6B0h+var_71C]
0x180076ed0  mov     r11d, [rbp+6B0h+var_710]
0x180076ed4  jmp     loc_1800773BB
0x180076ed9  movzx   eax, word ptr [r8+rdi*8+2]
0x180076edf  imul    rsi, rax, 74h ; 't'
0x180076ee3  mov     r12, [r13+90h]
0x180076eea  test    byte ptr [r8+rdi*8], 4
0x180076eef  jz      loc_1800771ED
0x180076ef5  or      eax, 0FFFFFFFFh
0x180076ef8  cmp     [rsi+r12+60h], eax
0x180076efd  jz      short loc_180076F09
0x180076eff  mov     eax, [rsi+r12+60h]
0x180076f04  mov     [rbp+6B0h+var_704], eax
0x180076f07  jmp     short loc_180076F12
0x180076f09  cmp     r9d, eax
0x180076f0c  jz      loc_1800773B8
0x180076f12  mov     eax, [rsi+r12+8]
0x180076f17  and     eax, 220h
0x180076f1c  cmp     eax, 20h ; ' '
0x180076f1f  jnz     short loc_180076F99
0x180076f21  test    byte ptr [r8+rdi*8], 10h
0x180076f26  jnz     short loc_180076F45
0x180076f28  or      rax, 0FFFFFFFFFFFFFFFFh
0x180076f2c  cmp     r11w, ax
0x180076f30  jnz     loc_1800773B8
0x180076f36  movzx   r11d, word ptr [rsi+r12+4]
0x180076f3c  mov     [rbp+6B0h+var_710], r11d
0x180076f40  jmp     loc_1800773B8
0x180076f45  mov     r8, [r13+0A8h]
0x180076f4c  mov     eax, edx
0x180076f4e  imul    rdx, rax, 38h ; '8'
0x180076f52  mov     rdi, [rbp+6B0h+var_728]
0x180076f56  add     rdx, rdi; struct SPPHRASEELEMENT *
0x180076f59  mov     eax, [rsi+r12+10h]
0x180076f5e  lea     r9, [r8+rax*2]; unsigned __int16 *
0x180076f62  mov     eax, [rsi+r12+0Ch]
0x180076f67  lea     r8, [r8+rax*2]; unsigned __int16 *
0x180076f6b  mov     rax, [rbp+6B0h+var_6E8]
0x180076f6f  mov     [rsp+7C0h+ppv], rax; struct IMSASRLocaleHandler *
0x180076f74  call    ?InitElementBSTRs@CDecoder@@QEAAJPEAUSPPHRASEELEMENT@@PEBG1PEAUIMSASRLocaleHandler@@@Z; CDecoder::InitElementBSTRs(SPPHRASEELEMENT *,ushort const *,ushort const *,IMSASRLocaleHandler *)
0x180076f79  mov     ebx, eax
0x180076f7b  xor     r10d, r10d
0x180076f7e  test    eax, eax
0x180076f80  js      loc_180077711
0x180076f86  mov     cl, [rbp+6B0h+var_730]
0x180076f89  mov     edx, [rbp+6B0h+var_71C]
0x180076f8c  mov     r8, [rbp+6B0h+var_6E0]
0x180076f90  mov     r11d, [rbp+6B0h+var_710]
0x180076f94  jmp     loc_1800771F4
0x180076f99  test    byte ptr [r8+rdi*8], 8
0x180076f9e  jz      short loc_180076FEE
0x180076fa0  mov     eax, [rsi+r12+14h]
0x180076fa5  mov     [rbp+6B0h+var_6F0], eax
0x180076fa8  mov     r9d, 80000000h
0x180076fae  and     [rbp+6B0h+var_350], r9d
0x180076fb5  xor     edx, edx
0x180076fb7  mov     rax, [rbp+6B0h+var_358]
0x180076fbe  mov     [rax], dx
0x180076fc1  and     [rbp+6B0h+var_530], r9d
0x180076fc8  mov     rax, [rbp+6B0h+strIn]
0x180076fcf  mov     [rax], dx
0x180076fd2  test    dword ptr [rsi+r12+8], 100h
0x180076fdb  jz      short loc_180076FEE
0x180076fdd  and     [rbp+6B0h+var_440], r9d
0x180076fe4  mov     rax, [rbp+6B0h+var_448]
0x180076feb  mov     [rax], dx
0x180076fee  mov     eax, [rsi+r12+10h]
0x180076ff3  test    eax, eax
0x180076ff5  jz      short loc_180077014
0x180076ff7  mov     ecx, eax
0x180076ff9  mov     rax, [r13+0A8h]
0x180077000  lea     rdx, [rax+rcx*2]
0x180077004  lea     rcx, [rbp+6B0h+var_360]
0x18007700b  call    ?Append@?$CQuickStringW@$0BIA@@@QEAAJQEBG@Z; CQuickStringW<384>::Append(ushort const * const)
0x180077010  mov     r8, [rbp+6B0h+var_6E0]
0x180077014  test    dword ptr [rsi+r12+8], 100h
0x18007701d  jz      loc_1800770B2
0x180077023  test    byte ptr [r8+rdi*8], 8
0x180077028  jnz     short loc_180077047
0x18007702a  lea     rdx, strIn; " "
0x180077031  lea     rcx, [rbp+6B0h+var_450]
0x180077038  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x18007703d  mov     ebx, eax
0x18007703f  test    eax, eax
0x180077041  js      loc_1800773DD
0x180077047  xorps   xmm0, xmm0
0x18007704a  xor     eax, eax
0x18007704c  movups  xmmword ptr [rbp+6B0h+var_670.ulAudioTimeOffset], xmm0
0x180077050  movups  xmmword ptr [rbp+6B0h+var_670.ulRetainedStreamOffset], xmm0
0x180077054  movups  xmmword ptr [rbp+6B0h+var_670.pszLexicalForm], xmm0
0x180077058  mov     qword ptr [rbp+6B0h+var_670.bDisplayAttributes], rax
0x18007705c  mov     ecx, [rsi+r12+0Ch]; this
0x180077061  mov     rax, [r13+0A8h]
0x180077068  lea     r8, [rax+rcx*2]; unsigned __int16 *
0x18007706c  mov     rax, [rbp+6B0h+var_6E8]
0x180077070  mov     [rsp+7C0h+ppv], rax; unsigned __int64
0x180077075  xor     r9d, r9d; unsigned __int16 *
0x180077078  lea     rdx, [rbp+6B0h+var_670]; struct SPPHRASEELEMENT *
0x18007707c  call    ?InitElementBSTRs@CDecoder@@QEAAJPEAUSPPHRASEELEMENT@@PEBG1PEAUIMSASRLocaleHandler@@@Z; CDecoder::InitElementBSTRs(SPPHRASEELEMENT *,ushort const *,ushort const *,IMSASRLocaleHandler *)
0x180077081  mov     ebx, eax
0x180077083  test    eax, eax
0x180077085  js      loc_1800773DD
0x18007708b  mov     rdx, [rbp+6B0h+var_670.pszDisplayText]
0x18007708f  lea     rcx, [rbp+6B0h+var_450]
0x180077096  call    ?Append@?$CQuickStringW@$0GE@@@QEAAJQEBG@Z; CQuickStringW<100>::Append(ushort const * const)
0x18007709b  mov     ebx, eax
0x18007709d  lea     rcx, [rbp+6B0h+var_670]; struct SPPHRASEELEMENT *
  ... truncated ...
```
