# StretchCodeGenerator::GenerateCode(long,StretchCodeGenScriptGroupType,long,unsigned __int64,wchar_t *,bool)

- ea: `0x101e6c010`
- end: `0x101e6d07c`
- name: `?GenerateCode@StretchCodeGenerator@@QEAAXJW4StretchCodeGenScriptGroupType@@J_KPEA_W_N@Z`
- size: `4204`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x101e69600`
- `0x101e699b0`
- `0x101e69d60`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004076a0`
- `0x100430d60`
- `0x10071db70`
- `0x100a2e200`
- `0x100a2e560`
- `0x100a2ea70`
- `0x101e6b8d0`
- `0x101e6b9c0`
- `0x101e6bb30`
- `0x101e6c010`
- `0x101e6d090`
- `0x101e6d490`
- `0x101e6d980`
- `0x101e6dc10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x101e6c3ff`
- `KERNEL32!GetLastError` at `0x101e6c5c6`
- `KERNEL32!GetLastError` at `0x101e6c633`
- `KERNEL32!GetLastError` at `0x101e6c3ff`
- `KERNEL32!GetLastError` at `0x101e6c5c6`
- `KERNEL32!GetLastError` at `0x101e6c633`
- `KERNEL32!CloseHandle` at `0x101e6ca65`
- `KERNEL32!CloseHandle` at `0x101e6ca65`
- `KERNEL32!QueryPerformanceCounter` at `0x101e6cc6c`
- `KERNEL32!QueryPerformanceCounter` at `0x101e6cca5`
- `KERNEL32!QueryPerformanceCounter` at `0x101e6cc6c`
- `KERNEL32!QueryPerformanceCounter` at `0x101e6cca5`
- `KERNEL32!CreateFileW` at `0x101e6c5ad`
- `KERNEL32!CreateFileW` at `0x101e6c5ad`
- `KERNEL32!WriteFile` at `0x101e6c629`
- `KERNEL32!WriteFile` at `0x101e6c629`
- `KERNEL32!DeleteFileW` at `0x101e6c3ef`
- `KERNEL32!DeleteFileW` at `0x101e6cff3`
- `KERNEL32!DeleteFileW` at `0x101e6c3ef`
- `KERNEL32!DeleteFileW` at `0x101e6cff3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e6c25d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101e6c79d`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101e6ccd8`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e6cc5c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e6cc95`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101e6cccc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c0a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c212`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c257`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c299`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c69f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c74b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c9c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c0a2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c212`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c257`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c299`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c69f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c74b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101e6c9c3`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c41b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c5dd`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c64a`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c9f2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6cdfc`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c41b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c5dd`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c64a`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6c9f2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101e6cdfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c14a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c2d5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c443`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c603`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c672`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c82f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c8a7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c930`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c9a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6ca1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6cb90`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6d010`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c14a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c2d5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c443`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c603`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c672`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c82f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c8a7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c930`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6c9a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6ca1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6cb90`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101e6d010`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c7db`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c850`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c8db`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c951`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6cb2f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c7db`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c850`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c8db`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6c951`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101e6cb2f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101e6c36d`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101e6c512`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101e6c36d`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101e6c512`
- `sqldk!SystemThread_TlsIndex` at `0x101e6c32c`
- `sqldk!SystemThread_TlsIndex` at `0x101e6c382`
- `sqldk!SystemThread_TlsIndex` at `0x101e6c4d1`
- `sqldk!SystemThread_TlsIndex` at `0x101e6c527`
- `sqldk!SystemThread_TlsOffset` at `0x101e6c335`
- `sqldk!SystemThread_TlsOffset` at `0x101e6c38b`
- `sqldk!SystemThread_TlsOffset` at `0x101e6c4da`
- `sqldk!SystemThread_TlsOffset` at `0x101e6c530`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c350`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c3a6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c4f5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c54b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c350`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c3a6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c4f5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101e6c54b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e6ca2a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e6d024`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e6ca2a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101e6d024`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall StretchCodeGenerator::GenerateCode(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        _WORD *a6,
        char a7)
{
  __int64 v11; // rdx
  _WORD *v12; // rcx
  __int16 v13; // ax
  _WORD *v14; // rax
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rdx
  DWORD LastError; // eax
  DWORD v29; // ebx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rdx
  int *FileW; // r15
  DWORD v36; // ebx
  DWORD v37; // ebx
  int v38; // esi
  unsigned int v39; // r12d
  unsigned int v40; // r14d
  __m128i *p_si128; // rsi
  const wchar_t **v42; // r13
  struct IMemObj **v43; // rdx
  struct IMemObj *v44; // rdi
  const wchar_t *v45; // rax
  unsigned int v46; // ebx
  int v47; // eax
  unsigned int v48; // edi
  int v49; // eax
  signed int v50; // eax
  signed int v51; // ebx
  const char *v52; // r9
  __int64 v53; // rcx
  __int64 v54; // rax
  unsigned __int64 v55; // rbx
  unsigned __int64 v56; // rax
  struct IMemObj **v57; // r12
  wchar_t *v58; // r15
  int v59; // eax
  __int64 v60; // rax
  CSbTransportMgr *QuadPart; // rbx
  signed int v62; // edi
  CSbTransportMgr *v63; // rcx
  unsigned __int64 v64; // rcx
  unsigned __int64 v65; // rcx
  _BYTE *v66; // r14
  char v67; // si
  __int64 v68; // rbx
  __int64 v69; // rdi
  int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rax
  int v73; // eax
  _BYTE *v74; // r10
  __int64 v75; // rdx
  _WORD *v76; // rcx
  __int64 v77; // r8
  __int16 v78; // ax
  _WORD *v79; // rax
  int dwCreationDispositionc; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-E0h]
  int dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v89; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IMemObj **v91; // [rsp+50h] [rbp-B0h]
  struct IMemObj *v92; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v93; // [rsp+60h] [rbp-A0h]
  _WORD *v94; // [rsp+68h] [rbp-98h]
  _BYTE v95[8]; // [rsp+70h] [rbp-90h] BYREF
  struct IMemObj *v96; // [rsp+78h] [rbp-88h]
  __int64 v97; // [rsp+80h] [rbp-80h]
  wchar_t *v98; // [rsp+88h] [rbp-78h]
  int *v99; // [rsp+90h] [rbp-70h]
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-68h] BYREF
  LARGE_INTEGER v101; // [rsp+A0h] [rbp-60h] BYREF
  int *v102; // [rsp+A8h] [rbp-58h]
  int v103; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v104; // [rsp+B8h] [rbp-48h]
  int v105; // [rsp+C0h] [rbp-40h] BYREF
  int v106; // [rsp+C4h] [rbp-3Ch]
  __int64 v107; // [rsp+C8h] [rbp-38h]
  int v108; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v109; // [rsp+D8h] [rbp-28h]
  __int64 v110; // [rsp+E0h] [rbp-20h]
  __int64 v111; // [rsp+E8h] [rbp-18h]
  __int64 v112; // [rsp+F0h] [rbp-10h]
  bool v113; // [rsp+100h] [rbp+0h]
  int v114; // [rsp+110h] [rbp+10h] BYREF
  __int64 v115; // [rsp+118h] [rbp+18h]
  int v116; // [rsp+120h] [rbp+20h] BYREF
  int v117; // [rsp+124h] [rbp+24h]
  __int64 v118; // [rsp+128h] [rbp+28h]
  int v119; // [rsp+130h] [rbp+30h] BYREF
  __int64 v120; // [rsp+138h] [rbp+38h]
  __int64 v121; // [rsp+140h] [rbp+40h]
  __int64 v122; // [rsp+148h] [rbp+48h]
  __int64 v123; // [rsp+150h] [rbp+50h]
  bool v124; // [rsp+160h] [rbp+60h]
  __int128 v125; // [rsp+170h] [rbp+70h] BYREF
  int v126; // [rsp+180h] [rbp+80h]
  struct IMemObj **v127; // [rsp+188h] [rbp+88h]
  struct IMemObj *v128; // [rsp+190h] [rbp+90h]
  __int64 v129; // [rsp+1A0h] [rbp+A0h]
  wchar_t *v130; // [rsp+1A8h] [rbp+A8h]
  _BYTE v131[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v132; // [rsp+1B8h] [rbp+B8h]
  int v133; // [rsp+1C0h] [rbp+C0h]
  _DWORD **v134; // [rsp+1C8h] [rbp+C8h]
  char *v135; // [rsp+1D0h] [rbp+D0h]
  __int64 v136; // [rsp+1D8h] [rbp+D8h]
  _DWORD *v137; // [rsp+1E0h] [rbp+E0h] BYREF
  int v138; // [rsp+1E8h] [rbp+E8h]
  int v139; // [rsp+1ECh] [rbp+ECh]
  __int64 v140; // [rsp+1F0h] [rbp+F0h]
  int v141; // [rsp+1F8h] [rbp+F8h]
  int v142; // [rsp+1FCh] [rbp+FCh]
  char v143; // [rsp+200h] [rbp+100h] BYREF
  __int64 v144; // [rsp+400h] [rbp+300h]
  __int64 v145; // [rsp+408h] [rbp+308h]
  _DWORD v146[4]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v147[8]; // [rsp+420h] [rbp+320h] BYREF
  int v148; // [rsp+428h] [rbp+328h]
  int v149; // [rsp+430h] [rbp+330h]
  _DWORD **v150; // [rsp+438h] [rbp+338h]
  char *v151; // [rsp+440h] [rbp+340h]
  __int64 v152; // [rsp+448h] [rbp+348h]
  _DWORD *v153; // [rsp+450h] [rbp+350h] BYREF
  int v154; // [rsp+458h] [rbp+358h]
  int v155; // [rsp+45Ch] [rbp+35Ch]
  const wchar_t *v156; // [rsp+460h] [rbp+360h]
  int v157; // [rsp+468h] [rbp+368h]
  int v158; // [rsp+46Ch] [rbp+36Ch]
  char v159; // [rsp+470h] [rbp+370h] BYREF
  __int64 v160; // [rsp+670h] [rbp+570h]
  __int64 v161; // [rsp+678h] [rbp+578h]
  _DWORD v162[2]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int64 v163; // [rsp+688h] [rbp+588h]
  _BYTE v164[8]; // [rsp+6A0h] [rbp+5A0h] BYREF
  int v165; // [rsp+6A8h] [rbp+5A8h]
  int v166; // [rsp+6B0h] [rbp+5B0h]
  _DWORD **v167; // [rsp+6B8h] [rbp+5B8h]
  char *v168; // [rsp+6C0h] [rbp+5C0h]
  __int64 v169; // [rsp+6C8h] [rbp+5C8h]
  _DWORD *v170; // [rsp+6D0h] [rbp+5D0h] BYREF
  int v171; // [rsp+6D8h] [rbp+5D8h]
  int v172; // [rsp+6DCh] [rbp+5DCh]
  WCHAR *v173; // [rsp+6E0h] [rbp+5E0h]
  int v174; // [rsp+6E8h] [rbp+5E8h]
  int v175; // [rsp+6ECh] [rbp+5ECh]
  char v176; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v177; // [rsp+8F0h] [rbp+7F0h]
  __int64 v178; // [rsp+8F8h] [rbp+7F8h]
  _DWORD v179[4]; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v180[4096]; // [rsp+910h] [rbp+810h] BYREF
  _BYTE v181[4096]; // [rsp+1910h] [rbp+1810h] BYREF
  _BYTE v182[4096]; // [rsp+2910h] [rbp+2810h] BYREF
  _BYTE v183[4096]; // [rsp+3910h] [rbp+3810h] BYREF
  _BYTE v184[4096]; // [rsp+4910h] [rbp+4810h] BYREF
  __m128i si128; // [rsp+5910h] [rbp+5810h] BYREF
  int v186; // [rsp+5920h] [rbp+5820h]
  int v187; // [rsp+5924h] [rbp+5824h]
  wchar_t FileName[264]; // [rsp+5930h] [rbp+5830h] BYREF
  WCHAR CurrentDirectory[264]; // [rsp+5B40h] [rbp+5A40h] BYREF
  wchar_t v190[264]; // [rsp+5D50h] [rbp+5C50h] BYREF

  v129 = -2;
  v93 = a3;
  v91 = (struct IMemObj **)a1;
  v94 = a6;
  if ( !*(_QWORD *)a1 )
    utassert_fail(1u, "nullptr != m_pmo", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegen.cpp\"", 268, 0);
  if ( (unsigned __int64)(a5 - 1) > 0x7FFFFFFE )
  {
    v15 = -2147024809;
    if ( a5 )
      *a6 = 0;
    goto LABEL_14;
  }
  v11 = a5;
  v12 = a6;
  do
  {
    if ( !(v11 + 2147483646 - a5) )
      break;
    v13 = *(_WORD *)((char *)v12 + (char *)&szPassword - (char *)a6);
    if ( !v13 )
      break;
    *v12++ = v13;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  v15 = -2147024774;
  if ( !v11 )
  {
LABEL_14:
    _mm_lfence();
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\stretch\\src\\codegen.cpp", 274, v15);
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(**(_QWORD **)(a1 + 8) + 56LL))(
          *(_QWORD *)(a1 + 8),
          *(unsigned int *)(a1 + 16),
          0,
          0,
          0,
          0);
  LOBYTE(dwFlagsAndAttributesa) = 1;
  LOBYTE(dwCreationDispositionc) = 0;
  LOBYTE(v17) = 1;
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, int, _DWORD, _DWORD))(*(_QWORD *)v16 + 120LL))(
          v16,
          a2,
          v17,
          0,
          dwCreationDispositionc,
          dwFlagsAndAttributesa,
          0,
          0);
  v19 = v18;
  if ( !a7 && !a3 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 120LL))(v18);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 960LL))(v20);
  }
  v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 120LL))(v19);
  v92 = (struct IMemObj *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 912LL))(v21);
  v89 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 1688LL))(v16, &v89) )
    utassert_fail(1u, "dbIsStretched", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegen.cpp\"", 294, 0);
  LOBYTE(v22) = 1;
  if ( !(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v16 + 1696LL))(v16, v89, 0, v22) )
    utassert_fail(1u, "nullptr != imstrdbRemote", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegen.cpp\"", 297, 0);
  if ( !(**(unsigned __int8 (__fastcall ***)(struct IServerConfiguration *, WCHAR *, __int64))s_pServerConf)(
          s_pServerConf,
          CurrentDirectory,
          522) )
    utassert_fail(1u, "result", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegen.cpp\"", 305, 0);
  if ( !GetStretchDatabaseCodeGenDir(*(_DWORD *)(a1 + 16), L"Stretch", 0x104u, v190, 1) )
    ex_raise(148, 16, 16, 1);
  StretchCodeGenerator::GetCodeGenMessageFilePath((StretchCodeGenerator *)a1, a2, 0x105u, FileName);
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v103, 1);
  v99 = &v105;
  v108 = 536871473;
  v109 = 0;
  v111 = 0;
  v110 = 0;
  v112 = 0;
  v113 = 0;
  v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v24 = *(_QWORD *)(v23 + 256);
  if ( !v24 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v24 = *(_QWORD *)(v23 + 256);
  }
  v25 = *(_QWORD *)(v24 + 600);
  if ( v25 )
    v113 = (unsigned int)SOS_Task::PushWait(v25, &v108) == 0;
  v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v27 = *(_QWORD *)(v26 + 256);
  if ( !v27 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v27 = *(_QWORD *)(v26 + 256);
  }
  v107 = v27;
  v106 = (*(_DWORD *)(v27 + 800) >> 11) & 1;
  if ( v106 || (*(_BYTE *)(v27 + 800) & 4) == 0 )
  {
    v105 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v27 + 608) + 8LL))(*(_QWORD *)(v27 + 608));
  }
  else
  {
    v105 = 0;
  }
  if ( !DeleteFileW(FileName) )
  {
    LastError = GetLastError();
    v29 = LastError;
    if ( LastError != 2 )
    {
      GetOSErrString(LastError, (struct ErrorStringHolder *)v180, 0, 0);
      dwCreationDisposition[0] = v29;
      ex_raise(148, 15, 16, 2, *(_QWORD *)dwCreationDisposition, v180);
    }
  }
  v99 = &v105;
  if ( v105 )
  {
    if ( v106 )
      *(_DWORD *)(v107 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v107 + 608) + 16LL))(
        *(_QWORD *)(v107 + 608),
        v107,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v108);
  *(_DWORD *)(v104 + 616) &= ~v103;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v114, 1);
  v99 = &v116;
  v119 = 536871473;
  v120 = 0;
  v122 = 0;
  v121 = 0;
  v123 = 0;
  v124 = 0;
  v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v31 = *(_QWORD *)(v30 + 256);
  if ( !v31 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v31 = *(_QWORD *)(v30 + 256);
  }
  v32 = *(_QWORD *)(v31 + 600);
  if ( v32 )
    v124 = (unsigned int)SOS_Task::PushWait(v32, &v119) == 0;
  v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v34 = *(_QWORD *)(v33 + 256);
  if ( !v34 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v34 = *(_QWORD *)(v33 + 256);
  }
  v118 = v34;
  v117 = (*(_DWORD *)(v34 + 800) >> 11) & 1;
  if ( v117 || (*(_BYTE *)(v34 + 800) & 4) == 0 )
  {
    v116 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v34 + 608) + 8LL))(*(_QWORD *)(v34 + 608));
  }
  else
  {
    v116 = 0;
  }
  FileW = (int *)CreateFileW(FileName, 0x40000000u, 2u, 0, 1u, 0, 0);
  v102 = FileW;
  if ( FileW == (int *)-1LL )
  {
    v36 = GetLastError();
    GetOSErrString(v36, (struct ErrorStringHolder *)v181, 0, 0);
    dwCreationDispositiona[0] = v36;
    ex_raise(148, 15, 16, 3, *(_QWORD *)dwCreationDispositiona, v181);
  }
  Buffer = -257;
  NumberOfBytesWritten = 0;
  if ( !WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
  {
    v37 = GetLastError();
    GetOSErrString(v37, (struct ErrorStringHolder *)v182, 0, 0);
    dwCreationDispositionb[0] = v37;
    ex_raise(148, 15, 16, 4, *(_QWORD *)dwCreationDispositionb, v182);
  }
  if ( NumberOfBytesWritten != 2 )
    utassert_fail(
      1u,
      "cbWritten == ARRAYSIZE(pbBomUTF16le)",
      "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegen.cpp\"",
      378,
      0);
  v38 = a4 - 5;
  if ( v38 && (unsigned int)(v38 - 1) <= 1 )
    v39 = 7;
  else
    v39 = 5;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v186 = 8;
  v187 = 10;
  v40 = 0;
  p_si128 = &si128;
  v42 = (const wchar_t **)v92;
  do
  {
    v43 = v91;
    v44 = *v91;
    if ( !*v91 )
    {
      utassert_fail(1u, "nullptr != pmo", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegenmsg.cpp\"", 144, 0);
      v43 = v91;
    }
    v98 = 0;
    v97 = 12;
    v96 = v44;
    LODWORD(v97) = p_si128->m128i_i32[0];
    switch ( (int)v97 )
    {
      case 1:
        v45 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *, struct IMemObj **, SID *, const char *))(*(_QWORD *)s_pServerConf + 256LL))(
                                 s_pServerConf,
                                 v43,
                                 &CXplOp_ParameterSensitivePredicate::m_szName,
                                 "Invalid switch value");
        StretchCodeGenMessage::GeneratePayload((StretchCodeGenMessage *)v95, v45);
        break;
      case 2:
        v46 = *((_DWORD *)v43 + 4);
        v98 = (wchar_t *)operator new[](0x16u, v44, "Sql\\Ntdbms\\stretch\\inc\\codegenmsg.h", 272, 3u);
        v47 = StringCchPrintfW(v98, 0xBu, L"%u", v46);
        if ( v47 < 0 )
          goto LABEL_76;
        break;
      case 3:
        v98 = (wchar_t *)operator new[](0x16u, v44, "Sql\\Ntdbms\\stretch\\inc\\codegenmsg.h", 272, 3u);
        v48 = a2;
        v49 = StringCchPrintfW(v98, 0xBu, L"%u", a2);
        if ( v49 < 0 )
        {
          _mm_lfence();
          LODWORD(hTemplateFile) = v49;
          dwFlagsAndAttributes[0] = 278;
          ex_raise(
            4,
            7,
            16,
            1,
            "Sql\\Ntdbms\\stretch\\inc\\codegenmsg.h",
            *(_QWORD *)dwFlagsAndAttributes,
            hTemplateFile);
        }
        goto LABEL_79;
      case 4:
        StretchCodeGenMessage::GeneratePayload((StretchCodeGenMessage *)v95, *v42);
        break;
      case 8:
        v98 = (wchar_t *)operator new[](0x16u, v44, "Sql\\Ntdbms\\stretch\\inc\\codegenmsg.h", 272, 3u);
        v47 = StringCchPrintfW(v98, 0xBu, L"%u", v93);
        if ( v47 < 0 )
          goto LABEL_76;
        break;
      case 10:
        v98 = (wchar_t *)operator new[](0x16u, v44, "Sql\\Ntdbms\\stretch\\inc\\codegenmsg.h", 272, 3u);
        v47 = StringCchPrintfW(v98, 0xBu, L"%u", v39);
        if ( v47 < 0 )
        {
LABEL_76:
          _mm_lfence();
          LODWORD(hTemplateFile) = v47;
          dwFlagsAndAttributes[0] = 278;
          ex_raise(
            4,
            7,
            16,
            1,
            "Sql\\Ntdbms\\stretch\\inc\\codegenmsg.h",
            *(_QWORD *)dwFlagsAndAttributes,
            hTemplateFile);
        }
        break;
      default:
        utassert_fail(1u, "FALSE", "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\codegen.cpp\"", 461, "Invalid switch value");
        break;
    }
    v48 = a2;
LABEL_79:
    v50 = StretchCodeGenMessage::Write((StretchCodeGenMessage *)v95, FileW);
    v51 = v50;
    if ( v50 < 0 )
    {
      _mm_lfence();
      GetOSErrString(v50, (struct ErrorStringHolder *)v183, 0, 0);
      dwCreationDispositionb[0] = v51;
      ex_raise(148, 15, 16, 5, *(_QWORD *)dwCreationDispositionb, v183);
    }
    if ( v98 )
      operator delete[](v98);
    ++v40;
    p_si128 = (__m128i *)((char *)p_si128 + 4);
    v52 = "Invalid switch value";
  }
  while ( v40 < 6 );
  if ( FileW )
    CloseHandle(FileW);
  v102 = &v116;
  if ( v116 )
  {
    if ( v117 )
      *(_DWORD *)(v118 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64, const char *))(**(_QWORD **)(v118 + 608) + 16LL))(
        *(_QWORD *)(v118 + 608),
        v118,
        1,
        v52);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v119);
  *(_DWORD *)(v115 + 616) &= ~v114;
  v53 = -1;
  do
    ++v53;
  while ( CurrentDirectory[v53] );
  v54 = -1;
  do
    ++v54;
  while ( FileName[v54] );
  v55 = (int)v53 + 30 + (int)v54;
  v56 = 2 * v55;
  if ( !is_mul_ok(v55, 2u) )
    v56 = -1;
  v57 = v91;
  v58 = (wchar_t *)operator new[](v56, *v91, "sql\\ntdbms\\stretch\\src\\codegen.cpp", 504, 3u);
  v91 = (struct IMemObj **)v58;
  v130 = v58;
  v59 = StringCchPrintfW(v58, v55, L"\"%s\\StretchCodeGen.exe\" \"%s\"", CurrentDirectory, FileName);
  if ( v59 < 0 )
  {
    _mm_lfence();
    LODWORD(hTemplateFile) = v59;
    dwFlagsAndAttributes[0] = 513;
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\stretch\\src\\codegen.cpp", *(_QWORD *)dwFlagsAndAttributes, hTemplateFile);
  }
  if ( (dword_102EDCA10 & 1) != 0 )
  {
    v165 = 0x20000;
    v166 = 0;
    v167 = &v170;
    v168 = &v176;
    v177 = 0;
    v169 = 0;
    v178 = 0;
    v170 = v179;
    v171 = 16;
    v172 = 1;
    v179[0] = *((_DWORD *)v57 + 4);
    v179[1] = v48;
    v60 = -1;
    do
      ++v60;
    while ( FileName[v60] );
    v173 = FileName;
    v174 = 2 * v60;
    v175 = 2;
    XeSqlPkg::stretch_codegen_start::Publish((XeSqlPkg::stretch_codegen_start *)v164);
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  v62 = InvokeCodeGenerator(CurrentDirectory, v58, *v57);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v101);
    v63 = (CSbTransportMgr *)v101.QuadPart;
  }
  else
  {
    v63 = MEMORY[0x7FFE0008];
  }
  if ( v63 < QuadPart )
  {
    v64 = 0;
  }
  else
  {
    v64 = v63 - QuadPart;
    if ( v64 == -1 )
      goto LABEL_115;
  }
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v64 = 1000 * v64 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
  else
    v64 /= 0x2710u;
LABEL_115:
  v65 = v64 / 0x3E8;
  if ( (dword_102EDCA0C & 0x4000000) != 0 )
  {
    v148 = 0x20000;
    v149 = 0;
    v150 = &v153;
    v151 = &v159;
    v160 = 0;
    v152 = 0;
    v161 = 0;
    v153 = v162;
    v154 = 24;
    v155 = 1;
    v162[0] = *((_DWORD *)v57 + 4);
    v162[1] = a2;
    v163 = v65;
    v156 = L"code generation";
    v157 = 30;
    v158 = 3;
    XeSqlPkg::stretch_table_provisioning_step_completed::Publish((XeSqlPkg::stretch_table_provisioning_step_completed *)v147);
  }
  if ( v62 < 0 )
  {
    _mm_lfence();
    GetOSErrString(v62, (struct ErrorStringHolder *)v184, 0, 0);
    v66 = v184;
    v67 = 0;
    v92 = *v57;
    v125 = 0;
    v126 = 0;
    v127 = &v92;
    v128 = v92;
    if ( (int)StretchCodeGenerator::GetCodeGenMessagesForObject(v57, a2, &v125) >= 0 )
    {
      v68 = v125;
      if ( (_QWORD)v125 )
      {
        while ( 1 )
        {
          v69 = *(_QWORD *)(v68 + 16);
          v70 = *(_DWORD *)(v69 + 16);
          if ( v70 != 5 )
            goto LABEL_128;
          if ( (dword_102EDCA0C & 0x20000000) != 0 )
            break;
LABEL_141:
          v68 = *(_QWORD *)(v68 + 8);
          if ( !v68 )
          {
            v58 = (wchar_t *)v91;
            goto LABEL_143;
          }
        }
        v132 = 0x20000;
        v133 = 0;
        v134 = &v137;
        v135 = &v143;
        v144 = 0;
        v136 = 0;
        v145 = 0;
        v137 = v146;
        v138 = 16;
        v139 = 1;
        v140 = 0;
        v141 = 0;
        v142 = 2;
        v146[0] = *((_DWORD *)v57 + 4);
        v146[1] = a2;
        v71 = *(_QWORD *)(v69 + 24);
        if ( v71 )
        {
          v72 = -1;
          do
            ++v72;
          while ( *(_WORD *)(v71 + 2 * v72) );
          v73 = 2 * v72;
        }
        else
        {
          v73 = 0;
        }
        v140 = *(_QWORD *)(v69 + 24);
        v141 = v73;
        XeSqlPkg::stretch_codegen_errorlog::Publish((XeSqlPkg::stretch_codegen_errorlog *)v131);
        v70 = *(_DWORD *)(v69 + 16);
LABEL_128:
        if ( v70 == 6 )
        {
          v74 = v94;
          if ( (unsigned __int64)(a5 - 1) > 0x7FFFFFFE )
          {
            if ( a5 )
              *v94 = 0;
          }
          else
          {
            v75 = a5;
            v76 = v94;
            v77 = *(_QWORD *)(v69 + 24) - (_QWORD)v94;
            do
            {
              if ( !(2147483646 - a5 + v75) )
                break;
              v78 = *(_WORD *)((char *)v76 + v77);
              if ( !v78 )
                break;
              *v76++ = v78;
              --v75;
            }
            while ( v75 );
            v79 = v76 - 1;
            if ( v75 )
              v79 = v76;
            *v79 = 0;
          }
          if ( !v67 )
          {
            v66 = v74;
            v67 = 1;
          }
        }
        goto LABEL_141;
      }
    }
LABEL_143:
    DeleteFileW(FileName);
    ex_raise(148, 14, 16, 11, v66);
    CTGListBase<StretchCodeGenMessage *,CFnD_Ptr<StretchCodeGenMessage>,CMemObjAlloc<0>>::~CTGListBase<StretchCodeGenMessage *,CFnD_Ptr<StretchCodeGenMessage>,CMemObjAlloc<0>>(&v125);
  }
  operator delete[](v58);
}

```

## disassembly

```asm
0x101e6c010  push    rbp
0x101e6c012  push    rsi
0x101e6c013  push    rdi
0x101e6c014  push    r12
0x101e6c016  push    r13
0x101e6c018  push    r14
0x101e6c01a  push    r15
0x101e6c01c  lea     rbp, [rsp-5E70h]
0x101e6c024  mov     eax, 5F70h
0x101e6c029  call    _alloca_probe
0x101e6c02e  sub     rsp, rax
0x101e6c031  mov     [rbp+5EA0h+var_5E00], 0FFFFFFFFFFFFFFFEh
0x101e6c03c  mov     [rsp+5FA0h+arg_18], rbx
0x101e6c044  mov     rax, cs:__security_cookie
0x101e6c04b  xor     rax, rsp
0x101e6c04e  mov     [rbp+5EA0h+var_40], rax
0x101e6c055  mov     esi, r9d
0x101e6c058  mov     r15d, r8d
0x101e6c05b  mov     [rsp+5FA0h+var_5F40], r8d
0x101e6c060  mov     r12d, edx
0x101e6c063  mov     [rsp+5FA0h+var_5F60], edx
0x101e6c067  mov     r14, rcx
0x101e6c06a  mov     [rsp+5FA0h+var_5F50], rcx
0x101e6c06f  mov     rbx, [rbp+5EA0h+arg_28]
0x101e6c076  mov     [rsp+5FA0h+var_5F38], rbx
0x101e6c07b  xor     edi, edi
0x101e6c07d  lea     r10d, [rdi+1]
0x101e6c081  cmp     [rcx], rdi
0x101e6c084  jnz     short loc_101E6C0AC
0x101e6c086  mov     qword ptr [rsp+5FA0h+dwCreationDisposition], rdi
0x101e6c08b  mov     r9d, 10Ch
0x101e6c091  lea     r8, aSqlNtdbmsStret_20; "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\co"...
0x101e6c098  lea     rdx, aNullptrMPmo; "nullptr != m_pmo"
0x101e6c09f  mov     ecx, r10d
0x101e6c0a2  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101e6c0a8  lea     r10d, [rdi+1]
0x101e6c0ac  mov     r13, [rbp+5EA0h+arg_20]
0x101e6c0b3  lea     rax, [r13-1]
0x101e6c0b7  lea     r11, aSqlNtdbmsStret_5; "sql\\ntdbms\\stretch\\src\\codegen.cpp"
0x101e6c0be  cmp     rax, 7FFFFFFEh
0x101e6c0c4  ja      short loc_101E6C11A
0x101e6c0c6  mov     rdx, r13
0x101e6c0c9  mov     rcx, rbx
0x101e6c0cc  mov     r8d, 7FFFFFFEh
0x101e6c0d2  sub     r8, r13
0x101e6c0d5  lea     r9, szPassword
0x101e6c0dc  sub     r9, rbx
0x101e6c0df  nop
0x101e6c0e0  lea     rax, [rdx+r8]
0x101e6c0e4  test    rax, rax
0x101e6c0e7  jz      short loc_101E6C100
0x101e6c0e9  movzx   eax, word ptr [r9+rcx]
0x101e6c0ee  test    ax, ax
0x101e6c0f1  jz      short loc_101E6C100
0x101e6c0f3  mov     [rcx], ax
0x101e6c0f6  add     rcx, 2
0x101e6c0fa  sub     rdx, 1
0x101e6c0fe  jnz     short loc_101E6C0E0
0x101e6c100  lea     rax, [rcx-2]
0x101e6c104  test    rdx, rdx
0x101e6c107  cmovnz  rax, rcx
0x101e6c10b  mov     [rax], di
0x101e6c10e  mov     eax, 8007007Ah
0x101e6c113  cmovnz  eax, edi
0x101e6c116  jnz     short loc_101E6C150
0x101e6c118  jmp     short loc_101E6C127
0x101e6c11a  mov     eax, 80070057h
0x101e6c11f  test    r13, r13
0x101e6c122  jz      short loc_101E6C127
0x101e6c124  mov     [rbx], di
0x101e6c127  lfence
0x101e6c12a  mov     dword ptr [rsp+5FA0h+hTemplateFile], eax
0x101e6c12e  mov     [rsp+5FA0h+dwFlagsAndAttributes], 112h
0x101e6c136  mov     qword ptr [rsp+5FA0h+dwCreationDisposition], r11
0x101e6c13b  mov     r9d, r10d
0x101e6c13e  mov     edx, 7
0x101e6c143  lea     ecx, [rdx-3]
0x101e6c146  lea     r8d, [rdx+9]
0x101e6c14a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101e6c150  mov     rcx, [r14+8]
0x101e6c154  mov     rax, [rcx]
0x101e6c157  mov     [rsp+5FA0h+dwFlagsAndAttributes], edi
0x101e6c15b  mov     [rsp+5FA0h+dwCreationDisposition], edi
0x101e6c15f  xor     r9d, r9d
0x101e6c162  xor     r8d, r8d
0x101e6c165  mov     edx, [r14+10h]
0x101e6c169  call    qword ptr [rax+38h]
0x101e6c16c  mov     rbx, rax
0x101e6c16f  mov     r10, [rax]
0x101e6c172  mov     [rsp+5FA0h+var_5F68], edi
0x101e6c176  mov     dword ptr [rsp+5FA0h+hTemplateFile], edi
0x101e6c17a  mov     byte ptr [rsp+5FA0h+dwFlagsAndAttributes], 1
0x101e6c17f  mov     byte ptr [rsp+5FA0h+dwCreationDisposition], dil
0x101e6c184  xor     r9d, r9d
0x101e6c187  mov     r8b, 1
0x101e6c18a  mov     edx, r12d
0x101e6c18d  mov     rcx, rax
0x101e6c190  call    qword ptr [r10+78h]
0x101e6c194  mov     rdi, rax
0x101e6c197  cmp     [rbp+5EA0h+arg_30], 0
0x101e6c19e  jnz     short loc_101E6C1BA
0x101e6c1a0  test    r15d, r15d
0x101e6c1a3  jnz     short loc_101E6C1BA
0x101e6c1a5  mov     rdx, [rax]
0x101e6c1a8  mov     rcx, rax
0x101e6c1ab  call    qword ptr [rdx+78h]
0x101e6c1ae  mov     rdx, [rax]
0x101e6c1b1  mov     rcx, rax
0x101e6c1b4  call    qword ptr [rdx+3C0h]
0x101e6c1ba  mov     rax, [rdi]
0x101e6c1bd  mov     rcx, rdi
0x101e6c1c0  call    qword ptr [rax+78h]
0x101e6c1c3  mov     rdx, [rax]
0x101e6c1c6  mov     rcx, rax
0x101e6c1c9  call    qword ptr [rdx+390h]
0x101e6c1cf  mov     [rsp+5FA0h+var_5F48], rax
0x101e6c1d4  xor     edi, edi
0x101e6c1d6  mov     [rsp+5FA0h+var_5F58], edi
0x101e6c1da  mov     r8, [rbx]
0x101e6c1dd  lea     rdx, [rsp+5FA0h+var_5F58]
0x101e6c1e2  mov     rcx, rbx
0x101e6c1e5  call    qword ptr [r8+698h]
0x101e6c1ec  test    al, al
0x101e6c1ee  jnz     short loc_101E6C21A
0x101e6c1f0  mov     qword ptr [rsp+5FA0h+dwCreationDisposition], rdi
0x101e6c1f5  mov     r9d, 126h
0x101e6c1fb  lea     r8, aSqlNtdbmsStret_20; "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\co"...
0x101e6c202  lea     rdx, aDbisstretched; "dbIsStretched"
0x101e6c209  mov     r15d, 1
0x101e6c20f  mov     ecx, r15d
0x101e6c212  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101e6c218  jmp     short loc_101E6C220
0x101e6c21a  mov     r15d, 1
0x101e6c220  mov     rax, [rbx]
0x101e6c223  mov     r9b, 1
0x101e6c226  xor     r8d, r8d
0x101e6c229  mov     edx, [rsp+5FA0h+var_5F58]
0x101e6c22d  mov     rcx, rbx
0x101e6c230  call    qword ptr [rax+6A0h]
0x101e6c236  test    rax, rax
0x101e6c239  jnz     short loc_101E6C25D
0x101e6c23b  mov     qword ptr [rsp+5FA0h+dwCreationDisposition], rdi
0x101e6c240  mov     r9d, 129h
0x101e6c246  lea     r8, aSqlNtdbmsStret_20; "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\co"...
0x101e6c24d  lea     rdx, aNullptrImstrdb; "nullptr != imstrdbRemote"
0x101e6c254  mov     ecx, r15d
0x101e6c257  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101e6c25d  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x101e6c264  mov     rcx, [rax]
0x101e6c267  mov     rax, [rcx]
0x101e6c26a  mov     r8d, 20Ah
0x101e6c270  lea     rdx, [rbp+5EA0h+CurrentDirectory]
0x101e6c277  call    qword ptr [rax]
0x101e6c279  test    al, al
0x101e6c27b  jnz     short loc_101E6C29F
0x101e6c27d  mov     qword ptr [rsp+5FA0h+dwCreationDisposition], rdi
0x101e6c282  mov     r9d, 131h
0x101e6c288  lea     r8, aSqlNtdbmsStret_20; "\"sql\\\\ntdbms\\\\stretch\\\\src\\\\co"...
0x101e6c28f  lea     rdx, ?szExpression@?6??ChangeState@SendBoxcarCommon@@QEAA_NW4EState@2@0@Z@4QBDB; "result"
0x101e6c296  mov     ecx, r15d
0x101e6c299  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101e6c29f  mov     byte ptr [rsp+5FA0h+dwCreationDisposition], 1; bool
0x101e6c2a4  lea     r9, [rbp+5EA0h+var_250]; wchar_t *
0x101e6c2ab  mov     r8d, 104h; unsigned int
0x101e6c2b1  lea     rdx, aStretch_1; "Stretch"
0x101e6c2b8  mov     ecx, [r14+10h]; unsigned int
0x101e6c2bc  call    ?GetStretchDatabaseCodeGenDir@@YA_NKPEB_WKPEA_W_N@Z; GetStretchDatabaseCodeGenDir(ulong,wchar_t const *,ulong,wchar_t *,bool)
0x101e6c2c1  test    al, al
0x101e6c2c3  jnz     short loc_101E6C2DB
0x101e6c2c5  mov     r9d, r15d
0x101e6c2c8  mov     edx, 10h
0x101e6c2cd  mov     ecx, 94h
0x101e6c2d2  mov     r8d, edx
0x101e6c2d5  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101e6c2db  lea     r9, [rbp+5EA0h+FileName]; wchar_t *
0x101e6c2e2  mov     r8d, 105h; unsigned int
0x101e6c2e8  mov     edx, r12d; int
0x101e6c2eb  mov     rcx, r14; this
0x101e6c2ee  call    ?GetCodeGenMessageFilePath@StretchCodeGenerator@@AEAAXJKQEA_W@Z; StretchCodeGenerator::GetCodeGenMessageFilePath(long,ulong,wchar_t * const)
0x101e6c2f3  mov     edx, r15d
0x101e6c2f6  lea     rcx, [rbp+5EA0h+var_5EF0]
0x101e6c2fa  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x101e6c2ff  nop
0x101e6c300  lea     rax, [rbp+5EA0h+var_5EE0]
0x101e6c304  mov     [rbp+5EA0h+var_5F10], rax
0x101e6c308  mov     [rbp+5EA0h+var_5ED0], 20000231h
0x101e6c30f  mov     [rbp+5EA0h+var_5EC8], rdi
0x101e6c313  mov     [rbp+5EA0h+var_5EB8], rdi
0x101e6c317  mov     [rbp+5EA0h+var_5EC0], rdi
0x101e6c31b  mov     [rbp+5EA0h+var_5EB0], rdi
0x101e6c31f  mov     [rbp+5EA0h+var_5EA0], 0
0x101e6c323  mov     rdx, gs:58h
0x101e6c32c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e6c333  mov     ecx, [rax]
0x101e6c335  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e6c33c  mov     ebx, [rax]
0x101e6c33e  add     rbx, [rdx+rcx*8]
0x101e6c342  mov     rax, [rbx+100h]
0x101e6c349  test    rax, rax
0x101e6c34c  jnz     short loc_101E6C35D
0x101e6c34e  xor     ecx, ecx
0x101e6c350  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101e6c356  mov     rax, [rbx+100h]
0x101e6c35d  mov     rcx, [rax+258h]
0x101e6c364  test    rcx, rcx
0x101e6c367  jz      short loc_101E6C379
0x101e6c369  lea     rdx, [rbp+5EA0h+var_5ED0]
0x101e6c36d  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x101e6c373  test    eax, eax
0x101e6c375  setz    [rbp+5EA0h+var_5EA0]
0x101e6c379  mov     rdx, gs:58h
0x101e6c382  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e6c389  mov     ecx, [rax]
0x101e6c38b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e6c392  mov     ebx, [rax]
0x101e6c394  add     rbx, [rdx+rcx*8]
0x101e6c398  mov     rdx, [rbx+100h]
0x101e6c39f  test    rdx, rdx
0x101e6c3a2  jnz     short loc_101E6C3B3
0x101e6c3a4  xor     ecx, ecx
0x101e6c3a6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101e6c3ac  mov     rdx, [rbx+100h]
0x101e6c3b3  mov     [rbp+5EA0h+var_5ED8], rdx
0x101e6c3b7  mov     eax, [rdx+320h]
0x101e6c3bd  shr     eax, 0Bh
0x101e6c3c0  and     eax, 1
0x101e6c3c3  mov     [rbp+5EA0h+var_5EDC], eax
0x101e6c3c6  jnz     short loc_101E6C3D6
0x101e6c3c8  test    byte ptr [rdx+320h], 4
0x101e6c3cf  jz      short loc_101E6C3D6
0x101e6c3d1  mov     [rbp+5EA0h+var_5EE0], edi
0x101e6c3d4  jmp     short loc_101E6C3E8
0x101e6c3d6  mov     [rbp+5EA0h+var_5EE0], r15d
0x101e6c3da  mov     rcx, [rdx+260h]
0x101e6c3e1  mov     rax, [rcx]
0x101e6c3e4  call    qword ptr [rax+8]
0x101e6c3e7  nop
0x101e6c3e8  lea     rcx, [rbp+5EA0h+FileName]; lpFileName
0x101e6c3ef  call    cs:__imp_DeleteFileW
0x101e6c3f5  mov     r12d, 2
0x101e6c3fb  test    eax, eax
0x101e6c3fd  jnz     short loc_101E6C44A
0x101e6c3ff  call    cs:__imp_GetLastError
0x101e6c405  mov     ebx, eax
0x101e6c407  cmp     eax, r12d
0x101e6c40a  jz      short loc_101E6C44A
0x101e6c40c  xor     r9d, r9d
0x101e6c40f  xor     r8d, r8d
0x101e6c412  lea     rdx, [rbp+5EA0h+var_5690]
0x101e6c419  mov     ecx, eax
0x101e6c41b  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x101e6c421  lea     rax, [rbp+5EA0h+var_5690]
0x101e6c428  mov     qword ptr [rsp+5FA0h+dwFlagsAndAttributes], rax
0x101e6c42d  mov     [rsp+5FA0h+dwCreationDisposition], ebx
0x101e6c431  mov     r9d, r12d
0x101e6c434  lea     edx, [r12+0Dh]
0x101e6c439  mov     ecx, 94h
0x101e6c43e  lea     r8d, [r12+0Eh]
0x101e6c443  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101e6c449  nop
0x101e6c44a  lea     rax, [rbp+5EA0h+var_5EE0]
0x101e6c44e  mov     [rbp+5EA0h+var_5F10], rax
0x101e6c452  cmp     [rbp+5EA0h+var_5EE0], 0
0x101e6c456  jz      short loc_101E6C47F
0x101e6c458  mov     rdx, [rbp+5EA0h+var_5ED8]
0x101e6c45c  mov     rcx, [rdx+260h]
0x101e6c463  cmp     [rbp+5EA0h+var_5EDC], 0
0x101e6c467  jz      short loc_101E6C475
0x101e6c469  or      dword ptr [rdx+320h], 800h
0x101e6c473  jmp     short loc_101E6C47F
0x101e6c475  mov     rax, [rcx]
0x101e6c478  mov     r8d, r15d
0x101e6c47b  call    qword ptr [rax+10h]
0x101e6c47e  nop
0x101e6c47f  lea     rcx, [rbp+5EA0h+var_5ED0]; this
0x101e6c483  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x101e6c488  nop
0x101e6c489  mov     ecx, [rbp+5EA0h+var_5EF0]
0x101e6c48c  not     ecx
0x101e6c48e  mov     rax, [rbp+5EA0h+var_5EE8]
0x101e6c492  and     [rax+268h], ecx
0x101e6c498  mov     edx, r15d
0x101e6c49b  lea     rcx, [rbp+5EA0h+var_5E90]
0x101e6c49f  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x101e6c4a4  nop
0x101e6c4a5  lea     rax, [rbp+5EA0h+var_5E80]
0x101e6c4a9  mov     [rbp+5EA0h+var_5F10], rax
0x101e6c4ad  mov     [rbp+5EA0h+var_5E70], 20000231h
0x101e6c4b4  mov     [rbp+5EA0h+var_5E68], rdi
0x101e6c4b8  mov     [rbp+5EA0h+var_5E58], rdi
0x101e6c4bc  mov     [rbp+5EA0h+var_5E60], rdi
0x101e6c4c0  mov     [rbp+5EA0h+var_5E50], rdi
0x101e6c4c4  mov     [rbp+5EA0h+var_5E40], 0
0x101e6c4c8  mov     rdx, gs:58h
0x101e6c4d1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101e6c4d8  mov     ecx, [rax]
0x101e6c4da  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101e6c4e1  mov     ebx, [rax]
0x101e6c4e3  add     rbx, [rdx+rcx*8]
0x101e6c4e7  mov     rax, [rbx+100h]
  ... truncated ...
```
