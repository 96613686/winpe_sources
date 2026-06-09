# LocaleMetaDataWriter::BuildLocaleTable(wmi::AutoRef<ExternalEvtxFile>,tag_RpcInfo &)

- ea: `0x18008e3b8`
- end: `0x18008f896`
- name: `?BuildLocaleTable@LocaleMetaDataWriter@@QEAAXV?$AutoRef@VExternalEvtxFile@@@wmi@@AEAUtag_RpcInfo@@@Z`
- size: `5342`
- prototype: ``
- caller_count: `1`
- callee_count: `61`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18008e22c`

## callees

- `0x18000347c`
- `0x180003d9c`
- `0x180003de0`
- `0x180004980`
- `0x18000bf10`
- `0x1800121f8`
- `0x1800137b8`
- `0x180014bd0`
- `0x180016250`
- `0x180017b60`
- `0x180019d28`
- `0x18001c320`
- `0x18001c600`
- `0x18001d820`
- `0x18001ec50`
- `0x18002afa8`
- `0x18002d204`
- `0x18002d6dc`
- `0x18002dcc0`
- `0x18002de70`
- `0x18002e468`
- `0x18003404c`
- `0x1800363fc`
- `0x18003bb1c`
- `0x18003c0b4`
- `0x18003d19c`
- `0x180043b10`
- `0x180043c94`
- `0x18004879c`
- `0x180069c00`
- `0x18006da88`
- `0x1800743ec`
- `0x18007feac`
- `0x18008e3b8`
- `0x18008f89c`
- `0x18008fac0`
- `0x18008faf0`
- `0x18008fc4c`
- `0x18008fc70`
- `0x18008fd10`
- `0x18008fd34`
- `0x18008fd5c`
- `0x180090734`
- `0x1800909cc`
- `0x180090ab0`
- `0x180090b3c`
- `0x180090b98`
- `0x180090be4`
- `0x180092008`
- `0x180095350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed79`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008ed5a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008ed5a`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e6a7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e7b8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e8c6`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e6a7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e7b8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e8c6`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18008e5f0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18008e5f0`
- `RPCRT4!RpcImpersonateClient` at `0x18008e549`
- `RPCRT4!RpcImpersonateClient` at `0x18008ecb4`
- `RPCRT4!RpcImpersonateClient` at `0x18008f2b9`
- `RPCRT4!RpcImpersonateClient` at `0x18008e549`
- `RPCRT4!RpcImpersonateClient` at `0x18008ecb4`
- `RPCRT4!RpcImpersonateClient` at `0x18008f2b9`
- `RPCRT4!RpcRevertToSelf` at `0x18008e9de`
- `RPCRT4!RpcRevertToSelf` at `0x18008ee30`
- `RPCRT4!RpcRevertToSelf` at `0x18008f38c`
- `RPCRT4!RpcRevertToSelf` at `0x18008e9de`
- `RPCRT4!RpcRevertToSelf` at `0x18008ee30`
- `RPCRT4!RpcRevertToSelf` at `0x18008f38c`

## string_xrefs

- `0x18008ea48`: `<dummy path>`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall LocaleMetaDataWriter::BuildLocaleTable(__int64 a1, wmi::RefBase **a2, __int64 a3)
{
  __int64 v4; // r13
  struct LocaleMessageTable *v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // edi
  DWORD LastError; // ebx
  DWORD v9; // ebx
  __int64 v10; // rax
  RecordCache *v11; // rdi
  unsigned __int64 v12; // rdx
  bool v13; // r8
  DWORD v14; // ebx
  __int64 v15; // rax
  RecordCache *v16; // rdi
  unsigned __int64 v17; // rdx
  bool v18; // r8
  DWORD v19; // ebx
  __int64 v20; // rax
  unsigned __int64 v21; // rdx
  bool v22; // r8
  bool v23; // r9
  EvtxFileQueryResult **v24; // rax
  EvtxFileQueryResult *v25; // rdi
  unsigned int i; // ebx
  BinXmlReader *v27; // rax
  RecordCache *v28; // r15
  unsigned int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // r8
  __int64 v32; // r9
  DWORD v33; // ebx
  _QWORD *v34; // rdi
  _QWORD *v35; // rax
  _QWORD *v36; // rbx
  wmi::RefBase **v37; // rbx
  BinXmlReader *CurrentRecordReader; // rbx
  __int64 *v39; // r13
  unsigned int v40; // ecx
  unsigned int v41; // r9d
  unsigned int v42; // r8d
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  void **v46; // r12
  char *v47; // rbx
  char *v48; // r15
  __int64 v49; // rax
  unsigned int v50; // eax
  unsigned int v51; // r15d
  PublisherMetadata *v52; // rax
  PublisherMetadata *v53; // rax
  unsigned __int64 v54; // r15
  int v55; // eax
  unsigned __int64 v56; // r15
  __int64 v57; // rax
  struct BinXmlReader *v58; // rbx
  __int64 v59; // rdx
  __int64 v60; // r8
  unsigned __int64 v61; // [rsp+48h] [rbp-C00h] BYREF
  BinXmlReader *v62; // [rsp+50h] [rbp-BF8h]
  __int128 v63; // [rsp+60h] [rbp-BE8h] BYREF
  volatile signed __int32 *v64; // [rsp+70h] [rbp-BD8h] BYREF
  RecordCache *v65; // [rsp+78h] [rbp-BD0h]
  RecordCache *v66; // [rsp+80h] [rbp-BC8h]
  RecordCache *v67; // [rsp+88h] [rbp-BC0h] BYREF
  RecordCache *v68; // [rsp+90h] [rbp-BB8h] BYREF
  RecordCache *v69; // [rsp+98h] [rbp-BB0h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-BA8h]
  RecordCache *v71; // [rsp+A8h] [rbp-BA0h]
  RecordCache *v72; // [rsp+B0h] [rbp-B98h]
  __int64 v73; // [rsp+B8h] [rbp-B90h]
  __int64 v74; // [rsp+C0h] [rbp-B88h] BYREF
  PublisherMetadata *v75; // [rsp+C8h] [rbp-B80h]
  __int64 *v76; // [rsp+D0h] [rbp-B78h] BYREF
  _QWORD v77[2]; // [rsp+D8h] [rbp-B70h] BYREF
  __int64 v78; // [rsp+E8h] [rbp-B60h]
  char v79; // [rsp+F0h] [rbp-B58h]
  char *v80; // [rsp+F8h] [rbp-B50h]
  wmi::RefBase **v81; // [rsp+100h] [rbp-B48h]
  const struct OperationControl **v82; // [rsp+108h] [rbp-B40h] BYREF
  struct LocaleMessageTable *v83[2]; // [rsp+110h] [rbp-B38h] BYREF
  __int64 v84; // [rsp+120h] [rbp-B28h]
  wmi::RefBase **v85; // [rsp+130h] [rbp-B18h]
  __int64 v86; // [rsp+138h] [rbp-B10h]
  _QWORD v87[2]; // [rsp+140h] [rbp-B08h] BYREF
  void *v88; // [rsp+150h] [rbp-AF8h]
  __int64 v89; // [rsp+158h] [rbp-AF0h]
  void **v90; // [rsp+160h] [rbp-AE8h] BYREF
  __int64 v91; // [rsp+168h] [rbp-AE0h]
  __int64 v92; // [rsp+170h] [rbp-AD8h]
  char v93; // [rsp+178h] [rbp-AD0h]
  void **v94; // [rsp+180h] [rbp-AC8h] BYREF
  __int64 *v95; // [rsp+188h] [rbp-AC0h]
  __int64 v96; // [rsp+190h] [rbp-AB8h]
  char v97; // [rsp+198h] [rbp-AB0h]
  __int128 v98; // [rsp+1A0h] [rbp-AA8h] BYREF
  _WORD *v99; // [rsp+1B0h] [rbp-A98h] BYREF
  _WORD *v100; // [rsp+1B8h] [rbp-A90h]
  _BYTE v101[32]; // [rsp+1D0h] [rbp-A78h] BYREF
  _QWORD v102[4]; // [rsp+1F0h] [rbp-A58h] BYREF
  unsigned __int16 *v103; // [rsp+210h] [rbp-A38h]
  _QWORD pExceptionObject[3]; // [rsp+218h] [rbp-A30h] BYREF
  unsigned int v105; // [rsp+230h] [rbp-A18h]
  __int64 v106; // [rsp+234h] [rbp-A14h]
  char v107; // [rsp+23Ch] [rbp-A0Ch]
  _QWORD v108[3]; // [rsp+240h] [rbp-A08h] BYREF
  unsigned int v109; // [rsp+258h] [rbp-9F0h]
  __int64 v110; // [rsp+25Ch] [rbp-9ECh]
  char v111; // [rsp+264h] [rbp-9E4h]
  _QWORD v112[3]; // [rsp+268h] [rbp-9E0h] BYREF
  unsigned int v113; // [rsp+280h] [rbp-9C8h]
  __int64 v114; // [rsp+284h] [rbp-9C4h]
  char v115; // [rsp+28Ch] [rbp-9BCh]
  __int64 v116; // [rsp+290h] [rbp-9B8h]
  __int64 v117; // [rsp+298h] [rbp-9B0h]
  _QWORD v118[2]; // [rsp+2A0h] [rbp-9A8h] BYREF
  _QWORD v119[2]; // [rsp+2B0h] [rbp-998h] BYREF
  __int128 v120; // [rsp+2C0h] [rbp-988h] BYREF
  __int64 v121; // [rsp+2D0h] [rbp-978h]
  DWORD v122; // [rsp+2D8h] [rbp-970h]
  int v123; // [rsp+2DCh] [rbp-96Ch]
  int v124; // [rsp+2E0h] [rbp-968h]
  __int128 v125; // [rsp+2E8h] [rbp-960h] BYREF
  __int64 v126; // [rsp+2F8h] [rbp-950h]
  DWORD v127; // [rsp+300h] [rbp-948h]
  int v128; // [rsp+304h] [rbp-944h]
  int v129; // [rsp+308h] [rbp-940h]
  __int128 v130; // [rsp+310h] [rbp-938h] BYREF
  __int64 v131; // [rsp+320h] [rbp-928h]
  DWORD v132; // [rsp+328h] [rbp-920h]
  int v133; // [rsp+32Ch] [rbp-91Ch]
  int v134; // [rsp+330h] [rbp-918h]
  __int128 v135; // [rsp+338h] [rbp-910h] BYREF
  __int64 v136; // [rsp+348h] [rbp-900h]
  DWORD v137; // [rsp+350h] [rbp-8F8h]
  int v138; // [rsp+354h] [rbp-8F4h]
  int v139; // [rsp+358h] [rbp-8F0h]
  __int128 v140; // [rsp+360h] [rbp-8E8h] BYREF
  __int64 v141; // [rsp+370h] [rbp-8D8h]
  DWORD v142; // [rsp+378h] [rbp-8D0h]
  int v143; // [rsp+37Ch] [rbp-8CCh]
  int v144; // [rsp+380h] [rbp-8C8h]
  __int128 v145; // [rsp+388h] [rbp-8C0h] BYREF
  __int64 v146; // [rsp+398h] [rbp-8B0h]
  int v147; // [rsp+3A0h] [rbp-8A8h]
  int v148; // [rsp+3A4h] [rbp-8A4h]
  int v149; // [rsp+3A8h] [rbp-8A0h]
  __int128 v150; // [rsp+3B0h] [rbp-898h] BYREF
  __int64 v151; // [rsp+3C0h] [rbp-888h]
  int v152; // [rsp+3C8h] [rbp-880h]
  int v153; // [rsp+3CCh] [rbp-87Ch]
  int v154; // [rsp+3D0h] [rbp-878h]
  __int128 v155; // [rsp+3D8h] [rbp-870h] BYREF
  __int64 v156; // [rsp+3E8h] [rbp-860h]
  int v157; // [rsp+3F0h] [rbp-858h]
  int v158; // [rsp+3F4h] [rbp-854h]
  int v159; // [rsp+3F8h] [rbp-850h]
  __int128 v160; // [rsp+400h] [rbp-848h] BYREF
  __int64 v161; // [rsp+410h] [rbp-838h]
  int v162; // [rsp+418h] [rbp-830h]
  int v163; // [rsp+41Ch] [rbp-82Ch]
  int v164; // [rsp+420h] [rbp-828h]
  _BYTE v165[24]; // [rsp+428h] [rbp-820h] BYREF
  EvtException *v166; // [rsp+440h] [rbp-808h] BYREF
  _BYTE v167[32]; // [rsp+448h] [rbp-800h] BYREF
  char v168; // [rsp+468h] [rbp-7E0h] BYREF
  _BYTE v169[144]; // [rsp+480h] [rbp-7C8h] BYREF
  _BYTE v170[144]; // [rsp+510h] [rbp-738h] BYREF
  _BYTE v171[352]; // [rsp+5A0h] [rbp-6A8h] BYREF
  __int128 v172; // [rsp+700h] [rbp-548h]
  _BYTE v173[192]; // [rsp+710h] [rbp-538h] BYREF
  __int128 v174; // [rsp+7D0h] [rbp-478h] BYREF
  WCHAR TempFileName[68]; // [rsp+7E0h] [rbp-468h] BYREF
  bool v176; // [rsp+868h] [rbp-3E0h]
  WCHAR PathName[264]; // [rsp+9F0h] [rbp-258h] BYREF

  v73 = a3;
  v81 = a2;
  v4 = a1;
  v70 = a1;
  v84 = a1;
  v85 = a2;
  v86 = a3;
  v90 = &Buffer::`vftable';
  v91 = 0;
  v92 = 0;
  v93 = 1;
  Buffer::SetSize((Buffer *)&v90, 0);
  HIDWORD(v92) = 0;
  v94 = &Buffer::`vftable';
  v95 = 0;
  v96 = 0;
  v97 = 1;
  Buffer::SetSize((Buffer *)&v94, 0);
  HIDWORD(v96) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v99);
  LocalePublisherTable::LocalePublisherTable((LocalePublisherTable *)v171);
  v102[0] = 0;
  v102[1] = 0;
  utl::make_unique<LocaleMessageTable,,0>(v83);
  utl::make_unique<RecordCache,,0>(&v67);
  utl::make_unique<RecordCache,,0>(&v68);
  utl::make_unique<RecordCache,,0>(&v69);
  v5 = v83[0];
  if ( !v83[0] || (v71 = v67) == 0 || (v72 = v68) == 0 || (v65 = v69) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
    }
    v160 = 0;
    v161 = 0;
    v162 = 14;
    v163 = -1;
    v164 = 688;
    throw (EvtException *)&v160;
  }
  v6 = RpcImpersonateClient(0);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v6);
    }
    pExceptionObject[0] = &word_1800EC961;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v105 = v7;
    v106 = -1;
    v107 = 0;
    throw (EvtException *)pExceptionObject;
  }
  if ( !(unsigned int)GetTempPath2W(260, PathName) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, LastError);
    }
    v120 = 0;
    v121 = 0;
    v122 = LastError;
    v123 = -1;
    v124 = 706;
    throw (EvtException *)&v120;
  }
  if ( !GetTempFileNameW(PathName, L"MSG", 0, TempFileName) )
  {
    v9 = GetLastError();
    if ( !v9 )
      v9 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v9);
    }
    v125 = 0;
    v126 = 0;
    v127 = v9;
    v128 = -1;
    v129 = 711;
    throw (EvtException *)&v125;
  }
  v10 = -1;
  do
    ++v10;
  while ( TempFileName[v10] );
  *(_QWORD *)&v63 = TempFileName;
  *((_QWORD *)&v63 + 1) = v10;
  MakeOrThrowOOM(v77);
  v11 = v72;
  RecordCache::OpenFile(v72);
  RecordCache::SyncFileHeader(v11, v12, v13);
  *(_QWORD *)v5 = v11;
  if ( !GetTempFileNameW(PathName, L"PUB", 0, TempFileName) )
  {
    v14 = GetLastError();
    if ( !v14 )
      v14 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v14);
    }
    v130 = 0;
    v131 = 0;
    v132 = v14;
    v133 = -1;
    v134 = 721;
    throw (EvtException *)&v130;
  }
  v15 = -1;
  do
    ++v15;
  while ( TempFileName[v15] );
  *(_QWORD *)&v63 = TempFileName;
  *((_QWORD *)&v63 + 1) = v15;
  MakeOrThrowOOM(v77);
  v16 = v71;
  RecordCache::OpenFile(v71);
  RecordCache::SyncFileHeader(v16, v17, v18);
  if ( !GetTempFileNameW(PathName, L"EVT", 0, TempFileName) )
  {
    v19 = GetLastError();
    if ( !v19 )
      v19 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v19);
    }
    v135 = 0;
    v136 = 0;
    v137 = v19;
    v138 = -1;
    v139 = 729;
    throw (EvtException *)&v135;
  }
  v20 = -1;
  do
    ++v20;
  while ( TempFileName[v20] );
  *(_QWORD *)&v63 = TempFileName;
  *((_QWORD *)&v63 + 1) = v20;
  MakeOrThrowOOM(v77);
  RecordCache::OpenFile(v65);
  RecordCache::SyncFileHeader(v65, v21, v22);
  LocalePublisherTable::Open((LocalePublisherTable *)v171, v16, v5, v23);
  v102[2] = v65;
  v102[3] = v5;
  RpcRevertToSelf();
  v103 = (unsigned __int16 *)(v4 + 504);
  EventRendering::GetWinmetaPublisherMetadata(&v61, *(unsigned int *)(v4 + 504));
  v66 = (RecordCache *)v61;
  if ( v61 )
    _InterlockedAdd((volatile signed __int32 *)(v61 + 8), 1u);
  LocalePublisherTableWriter::NewPublisherRecord((LocalePublisherTable::_PublisherRecord *)v171);
  wmi::AutoRef<PublisherMetadata>::Release(&v61);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(v87);
  QueryXmlParser::QueryXmlParser((QueryXmlParser *)v173);
  v66 = 0;
  v82 = (const struct OperationControl **)(v4 + 512);
  v24 = (EvtxFileQueryResult **)ExternalEvtxFile::Query(
                                  *a2,
                                  &v76,
                                  *(_QWORD *)(v4 + 512),
                                  (char *)v88 + 56,
                                  &unk_180111698);
  v25 = *v24;
  *v24 = 0;
  v66 = v25;
  wmi::AutoRef<PublisherMetadata>::Release(&v76);
  BinXmlExtractor::BinXmlExtractor((BinXmlExtractor *)v170, MessageRenderExtractorCallbackIndexed);
  for ( i = 0; i < 0x12; ++i )
  {
    v98 = *(_OWORD *)&(&off_1800DF250)[3 * (int)i];
    BinXmlExtractor::AddPath((unsigned int)v170, (unsigned int)&v98, i, 0, (&off_1800DF250)[3 * (int)i + 1]);
  }
  BinXmlExtractor::BinXmlExtractor((BinXmlExtractor *)v169, MessageRenderExtractorCallbackIncremental);
  *(_QWORD *)&v63 = L"/Event/EventData/Data";
  *((_QWORD *)&v63 + 1) = 21;
  BinXmlExtractor::AddPath((unsigned int)v169, (unsigned int)&v63, 0, 0, 0);
  *(_QWORD *)&v63 = L"/Event/UserData";
  *((_QWORD *)&v63 + 1) = 15;
  BinXmlExtractor::AddPath((unsigned int)v169, (unsigned int)&v63, 1, 1, 0);
  while ( 1 )
  {
    CheckCancellation(*v82);
    if ( !EvtxFileQueryResult::NextRecord(v25) )
      break;
    if ( *((_BYTE *)v25 + 68) )
    {
      CurrentRecordReader = EvtxFileQueryResult::GetCurrentRecordReader(v25);
      v62 = CurrentRecordReader;
      Buffer::SetCurrentIndex((Buffer *)&v94, 0);
      Buffer::SetCurrentIndex((Buffer *)&v90, 0);
      BinXmlExtractor::Process((BinXmlExtractor *)v170, CurrentRecordReader, &v90);
      v39 = v95;
      v40 = v96;
      v41 = (unsigned int)v96 >> 4;
      v42 = 0;
      if ( (unsigned int)v96 >> 4 )
      {
        do
        {
          v43 = 2LL * v42;
          if ( HIDWORD(v39[v43 + 1]) == 1
            || HIDWORD(v39[v43 + 1]) == 2
            || HIDWORD(v39[v43 + 1]) == 14
            || HIDWORD(v39[v43 + 1]) == 15
            || (unsigned int)(HIDWORD(v39[v43 + 1]) - 18) <= 1 )
          {
            v39[v43] += v91;
          }
          ++v42;
        }
        while ( v42 < v41 );
        v40 = v96;
        v39 = v95;
      }
      v61 = v40;
      v76 = v39;
      v44 = *v39;
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)(v44 + 2 * v45) );
      *(_QWORD *)&v63 = *v39;
      *((_QWORD *)&v63 + 1) = v45;
      v46 = (void **)(v70 + 520);
      *(_QWORD *)&v174 = v70 + 520;
      v47 = (char *)(v70 + 520);
      if ( *(_QWORD *)(v70 + 536) != v70 + 520 )
      {
        v48 = (char *)*v46;
        do
        {
          if ( (unsigned __int8)tlx::istring_less_ordinal::operator()<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                                  v44,
                                  v48 + 24,
                                  &v63) )
          {
            v49 = 16;
          }
          else
          {
            v47 = v48;
            v49 = 8;
          }
          v48 = *(char **)&v48[v49];
        }
        while ( v48 != (char *)&utl::_TreeSentinel );
        LODWORD(v46) = v174;
        v80 = v47;
        if ( v47 == (char *)v174 )
          goto LABEL_123;
        if ( !(unsigned __int8)tlx::istring_less_ordinal::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t,wchar_t,0>(
                                 v44,
                                 &v63,
                                 v47 + 24) )
        {
          v54 = v61;
          goto LABEL_144;
        }
      }
      v80 = v47;
LABEL_123:
      v64 = 0;
      try
      {
        v50 = RpcImpersonateClient(0);
        v51 = v50;
        if ( v50 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v50);
          }
          v112[0] = &word_1800EC961;
          v112[1] = 0;
          v112[2] = 0;
          v113 = v51;
          v114 = -1;
          v115 = 0;
          throw (EvtException *)v112;
        }
        v116 = *v39;
        v117 = *((unsigned int *)v39 + 2);
        PublisherConfigReader::PublisherConfigReader((PublisherConfigReader *)TempFileName);
        RpcRevertToSelf();
        v52 = (PublisherMetadata *)operator new(0x180u);
        v75 = v52;
        if ( v52 )
          v53 = PublisherMetadata::PublisherMetadata(
                  v52,
                  (const struct PublisherConfigReader *)TempFileName,
                  *v103,
                  v176);
        else
          v53 = 0;
        wmi::AutoRef<EventSession>::operator=(&v64, v53);
        v75 = (PublisherMetadata *)v64;
        if ( v64 )
          _InterlockedAdd(v64 + 2, 1u);
        LocalePublisherTableWriter::NewPublisherRecord((LocalePublisherTable::_PublisherRecord *)v171);
        PublisherConfigReader::~PublisherConfigReader((PublisherConfigReader *)TempFileName);
      }
      catch ( EvtException *v166 )
      {
        if ( *((_DWORD *)v166 + 6) )
          wmi::AutoRef<PublisherMetadata>::Release(&v64);
        v71 = v67;
        v72 = v68;
        v65 = v69;
        v25 = v66;
        LODWORD(v47) = (_DWORD)v80;
        v39 = v76;
        v70 = v84;
        v81 = v85;
        v73 = v86;
        LODWORD(v46) = v174;
      }
      v54 = v61;
      v174 = v63;
      v55 = MakeOrThrowOOM(v167);
      v47 = *(char **)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>>(
                        (_DWORD)v46,
                        (unsigned int)&v168,
                        (_DWORD)v47,
                        v55,
                        (__int64)&v64);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v167);
      if ( !v47 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
        }
        v155 = 0;
        v156 = 0;
        v157 = 14;
        v158 = -1;
        v159 = 845;
        throw (EvtException *)&v155;
      }
      wmi::AutoRef<PublisherMetadata>::Release(&v64);
LABEL_144:
      v56 = v54 >> 4;
      v57 = *((_QWORD *)v47 + 7);
      v74 = v57;
      if ( v57 )
      {
        _InterlockedAdd((volatile signed __int32 *)(v57 + 8), 1u);
        v57 = v74;
      }
      if ( v57 )
      {
        v174 = 0;
        LODWORD(v64) = 0;
        v119[0] = v39;
        v119[1] = v56;
        GetEventDescriptor(v119, &v174, &v64);
        try
        {
          v77[0] = &Buffer::`vftable';
          v77[1] = 0;
          v78 = 0;
          v79 = 1;
          Buffer::SetSize((Buffer *)v77, 0);
          HIDWORD(v78) = 0;
          v58 = v62;
          BinXmlReader::Reset(v62);
          BinXmlExtractor::Process((BinXmlExtractor *)v169, v58, v77);
          utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v165);
          v118[0] = v59;
          v118[1] = v60;
          ConvertVariantsToStrings(v118, v165);
          v100 = v99;
          *v99 = 0;
          EventRendering::GetEventDescription(
            (unsigned int)&v74,
            (unsigned int)&v174,
            -1,
            (unsigned int)v165,
            1,
            (__int64)&v99,
            v73);
          utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(v165);
          Buffer::~Buffer((Buffer *)v77);
        }
        catch ( EvtException )
        {
          v100 = v99;
          *v99 = 0;
          v71 = v67;
          v72 = v68;
          v65 = v69;
          v25 = v66;
          v39 = v76;
          v70 = v84;
          v81 = v85;
          v73 = v86;
        }
        *(_QWORD *)&v98 = v99;
        *((_QWORD *)&v98 + 1) = v100 - v99;
        LocaleEventTableWriter::NewEvent(v102, v39[20], &v98);
        wmi::AutoRef<PublisherMetadata>::Release(&v74);
      }
      else
      {
        wmi::AutoRef<PublisherMetadata>::Release(&v74);
      }
      v4 = v70;
    }
  }
  v172 = 0;
  v27 = (BinXmlReader *)MIDL_user_allocate(0x460u);
  v62 = v27;
  if ( v27 )
    v28 = SectionCache::SectionCache(v27);
  else
    v28 = 0;
  v82 = (const struct OperationControl **)v28;
  if ( !v28 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
    }
    v150 = 0;
    v151 = 0;
    v152 = 14;
    v153 = -1;
    v154 = 900;
    throw (EvtException *)&v150;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v101);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v101)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           v101,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v101)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           v101,
                           46)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v101) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
    }
    v145 = 0;
    v146 = 0;
    v147 = 14;
    v148 = -1;
    v149 = 910;
    throw (EvtException *)&v145;
  }
  v29 = RpcImpersonateClient(0);
  v30 = v29;
  if ( v29 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v29);
    }
    v108[0] = &word_1800EC961;
    v108[1] = 0;
    v108[2] = 0;
    v109 = v30;
    v110 = -1;
    v111 = 0;
    throw (EvtException *)v108;
  }
  if ( !CreateDirectoryW(*(LPCWSTR *)v4, 0) && GetLastError() != 183 )
  {
    v33 = GetLastError();
    if ( !v33 )
      v33 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v33);
    }
    v140 = 0;
    v141 = 0;
    v142 = v33;
    v143 = -1;
    v144 = 923;
    throw (EvtException *)&v140;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    v102,
    v101,
    v31,
    v32);
  RecordCache::OpenFile(v28);
  RpcRevertToSelf();
  v67 = 0;
  v61 = (unsigned __int64)v71;
  SectionCache::AddSection(v28, L"PUB", &v61);
  v69 = 0;
  v61 = (unsigned __int64)v65;
  SectionCache::AddSection(v28, L"EVT", &v61);
  v68 = 0;
  v61 = (unsigned __int64)v72;
  SectionCache::AddSection(v28, L"MSG", &v61);
  SectionCache::BuildFile(v28);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v101);
  utl::unique_ptr<SectionCache,utl::default_delete<SectionCache>>::~unique_ptr<SectionCache,utl::default_delete<SectionCache>>(&v82);
  BinXmlExtractor::~BinXmlExtractor((BinXmlExtractor *)v169);
  BinXmlExtractor::~BinXmlExtractor((BinXmlExtractor *)v170);
  if ( v25 )
    wmi::RefBase::Release(v25);
  QueryXmlParser::~QueryXmlParser((QueryXmlParser *)v173);
  v34 = v88;
  if ( v88 == v87 )
    goto LABEL_89;
  while ( 2 )
  {
    v35 = (_QWORD *)v34[1];
    if ( v35 != (_QWORD *)&utl::_TreeSentinel )
    {
LABEL_87:
      v34 = v35;
      continue;
    }
    break;
  }
LABEL_83:
  v35 = (_QWORD *)v34[2];
  if ( v35 != (_QWORD *)&utl::_TreeSentinel )
    goto LABEL_87;
  while ( 1 )
  {
    v36 = v34;
    v34 = (_QWORD *)(*v34 & 0xFFFFFFFFFFFFFFFEuLL);
    utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<unsigned long,QueryNode,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,QueryNode>>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<unsigned long,QueryNode,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,QueryNode>>>>(v36 + 3);
    operator delete(v36);
    if ( v34 == v87 )
      break;
    if ( (_UNKNOWN *)v34[1] != &utl::_TreeSentinel )
    {
      v34[1] = &utl::_TreeSentinel;
      goto LABEL_83;
    }
  }
  v87[0] = v87;
  v87[1] = v87;
  v88 = v87;
  v89 = 0;
LABEL_89:
  utl::unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>::~unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>(&v69);
  utl::unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>::~unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>(&v68);
  utl::unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>::~unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>(&v67);
  utl::unique_ptr<LocaleMessageTable,utl::default_delete<LocaleMessageTable>>::~unique_ptr<LocaleMessageTable,utl::default_delete<LocaleMessageTable>>(v83);
  LocalePublisherTable::~LocalePublisherTable((LocalePublisherTable *)v171);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v99);
  VariantValues::~VariantValues((VariantValues *)&v90);
  v37 = v81;
  if ( *v81 )
    wmi::RefBase::Release(*v81);
  *v37 = 0;
}

```

## disassembly

```asm
0x18008e3b8  mov     r11, rsp
0x18008e3bb  push    rbx
0x18008e3bc  push    rsi
0x18008e3bd  push    rdi
0x18008e3be  push    r12
0x18008e3c0  push    r13
0x18008e3c2  push    r14
0x18008e3c4  push    r15
0x18008e3c6  sub     rsp, 0C10h
0x18008e3cd  mov     rax, cs:__security_cookie
0x18008e3d4  xor     rax, rsp
0x18008e3d7  mov     [rsp+0C48h+var_48], rax
0x18008e3df  mov     r12, r8
0x18008e3e2  mov     [rsp+0C48h+var_B90], r8
0x18008e3ea  mov     r15, rdx
0x18008e3ed  mov     [r11-0B48h], rdx
0x18008e3f4  mov     r13, rcx
0x18008e3f7  mov     [rsp+0C48h+var_BA8], rcx
0x18008e3ff  mov     [rsp+0C48h+var_B28], rcx
0x18008e407  mov     [r11-0B18h], rdx
0x18008e40e  mov     [rsp+0C48h+var_B10], r8
0x18008e416  xor     esi, esi
0x18008e418  lea     rbx, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18008e41f  mov     [r11-0AE8h], rbx
0x18008e426  mov     [r11-0AE0h], rsi
0x18008e42d  mov     [r11-0AD8h], rsi
0x18008e434  lea     r14d, [rsi+1]
0x18008e438  mov     [r11-0AD0h], r14b
0x18008e43f  xor     edx, edx; unsigned int
0x18008e441  lea     rcx, [r11-0AE8h]; this
0x18008e448  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18008e44d  mov     [rsp+0C48h+var_AD4], esi
0x18008e454  mov     [rsp+0C48h+var_AC8], rbx
0x18008e45c  mov     [rsp+0C48h+var_AC0], rsi
0x18008e464  mov     [rsp+0C48h+var_AB8], rsi
0x18008e46c  mov     [rsp+0C48h+var_AB0], r14b
0x18008e474  xor     edx, edx; unsigned int
0x18008e476  lea     rcx, [rsp+0C48h+var_AC8]; this
0x18008e47e  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18008e483  mov     dword ptr [rsp+0C48h+var_AB8+4], esi
0x18008e48a  lea     rcx, [rsp+0C48h+var_A98]; void *
0x18008e492  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008e497  nop
0x18008e498  lea     rcx, [rsp+0C48h+var_6A8]; this
0x18008e4a0  call    ??0LocalePublisherTable@@QEAA@XZ; LocalePublisherTable::LocalePublisherTable(void)
0x18008e4a5  nop
0x18008e4a6  mov     [rsp+0C48h+var_A58], rsi
0x18008e4ae  mov     [rsp+0C48h+var_A50], rsi
0x18008e4b6  lea     rcx, [rsp+0C48h+var_B38]
0x18008e4be  call    ??$make_unique@VLocaleMessageTable@@$$V$0A@@utl@@YA?AV?$unique_ptr@VLocaleMessageTable@@U?$default_delete@VLocaleMessageTable@@@utl@@@0@XZ; utl::make_unique<LocaleMessageTable,,0>(void)
0x18008e4c3  nop
0x18008e4c4  lea     rcx, [rsp+0C48h+var_BC0]
0x18008e4cc  call    ??$make_unique@VRecordCache@@$$V$0A@@utl@@YA?AV?$unique_ptr@VRecordCache@@U?$default_delete@VRecordCache@@@utl@@@0@XZ; utl::make_unique<RecordCache,,0>(void)
0x18008e4d1  nop
0x18008e4d2  lea     rcx, [rsp+0C48h+var_BB8]
0x18008e4da  call    ??$make_unique@VRecordCache@@$$V$0A@@utl@@YA?AV?$unique_ptr@VRecordCache@@U?$default_delete@VRecordCache@@@utl@@@0@XZ; utl::make_unique<RecordCache,,0>(void)
0x18008e4df  nop
0x18008e4e0  lea     rcx, [rsp+0C48h+var_BB0]
0x18008e4e8  call    ??$make_unique@VRecordCache@@$$V$0A@@utl@@YA?AV?$unique_ptr@VRecordCache@@U?$default_delete@VRecordCache@@@utl@@@0@XZ; utl::make_unique<RecordCache,,0>(void)
0x18008e4ed  nop
0x18008e4ee  mov     rbx, [rsp+0C48h+var_B38]
0x18008e4f6  test    rbx, rbx
0x18008e4f9  jz      loc_18008F814
0x18008e4ff  mov     rax, [rsp+0C48h+var_BC0]
0x18008e507  mov     [rsp+0C48h+var_BA0], rax
0x18008e50f  test    rax, rax
0x18008e512  jz      loc_18008F814
0x18008e518  mov     rax, [rsp+0C48h+var_BB8]
0x18008e520  mov     [rsp+0C48h+var_B98], rax
0x18008e528  test    rax, rax
0x18008e52b  jz      loc_18008F814
0x18008e531  mov     rax, [rsp+0C48h+var_BB0]
0x18008e539  mov     [rsp+0C48h+var_BD0], rax
0x18008e53e  test    rax, rax
0x18008e541  jz      loc_18008F814
0x18008e547  xor     ecx, ecx; BindingHandle
0x18008e549  call    cs:__imp_RpcImpersonateClient
0x18008e54f  mov     edi, eax
0x18008e551  test    eax, eax
0x18008e553  jz      loc_18008E5DE
0x18008e559  lea     rcx, WPP_GLOBAL_Control
0x18008e560  mov     r10, cs:WPP_GLOBAL_Control
0x18008e567  cmp     r10, rcx
0x18008e56a  jz      short loc_18008E58F
0x18008e56c  test    [r10+1Ch], r14b
0x18008e570  jz      short loc_18008E58F
0x18008e572  cmp     byte ptr [r10+19h], 2
0x18008e577  jb      short loc_18008E58F
0x18008e579  lea     edx, [rsi+10h]
0x18008e57c  mov     r9d, eax
0x18008e57f  lea     r8, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids
0x18008e586  mov     rcx, [r10+10h]
0x18008e58a  call    WPP_SF_d
0x18008e58f  lea     rax, word_1800EC961
0x18008e596  mov     [rsp+0C48h+pExceptionObject], rax
0x18008e59e  mov     [rsp+0C48h+var_A28], rsi
0x18008e5a6  mov     [rsp+0C48h+var_A20], rsi
0x18008e5ae  mov     [rsp+0C48h+var_A18], edi
0x18008e5b5  mov     [rsp+0C48h+var_A14], 0FFFFFFFFFFFFFFFFh
0x18008e5c1  mov     [rsp+0C48h+var_A0C], sil
0x18008e5c9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008e5d0  lea     rcx, [rsp+0C48h+pExceptionObject]; pExceptionObject
0x18008e5d8  call    _CxxThrowException_0
0x18008e5de  mov     [rsp+0C48h+var_C07], r14b
0x18008e5e3  lea     rdx, [rsp+0C48h+PathName]
0x18008e5eb  mov     ecx, 104h
0x18008e5f0  call    cs:__imp_GetTempPath2W
0x18008e5f6  test    eax, eax
0x18008e5f8  jnz     loc_18008E68D
0x18008e5fe  call    cs:__imp_GetLastError
0x18008e604  mov     ebx, eax
0x18008e606  mov     ecx, 507h
0x18008e60b  test    eax, eax
0x18008e60d  cmovz   ebx, ecx
0x18008e610  lea     rcx, WPP_GLOBAL_Control
0x18008e617  mov     rax, cs:WPP_GLOBAL_Control
0x18008e61e  cmp     rax, rcx
0x18008e621  jz      short loc_18008E647
0x18008e623  test    [rax+1Ch], r14b
0x18008e627  jz      short loc_18008E647
0x18008e629  cmp     byte ptr [rax+19h], 2
0x18008e62d  jb      short loc_18008E647
0x18008e62f  mov     edx, 11h
0x18008e634  mov     r9d, ebx
0x18008e637  lea     r8, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids
0x18008e63e  mov     rcx, [rax+10h]
0x18008e642  call    WPP_SF_d
0x18008e647  xorps   xmm0, xmm0
0x18008e64a  movdqu  [rsp+0C48h+var_988], xmm0
0x18008e653  mov     [rsp+0C48h+var_978], rsi
0x18008e65b  mov     [rsp+0C48h+var_970], ebx
0x18008e662  mov     [rsp+0C48h+var_96C], 0FFFFFFFFh
0x18008e66d  mov     [rsp+0C48h+var_968], 2C2h
0x18008e678  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008e67f  lea     rcx, [rsp+0C48h+var_988]; pExceptionObject
0x18008e687  call    _CxxThrowException_0
0x18008e68d  lea     r9, [rsp+0C48h+TempFileName]; lpTempFileName
0x18008e695  xor     r8d, r8d; uUnique
0x18008e698  lea     rdx, PrefixString; "MSG"
0x18008e69f  lea     rcx, [rsp+0C48h+PathName]; lpPathName
0x18008e6a7  call    cs:__imp_GetTempFileNameW
0x18008e6ad  test    eax, eax
0x18008e6af  jnz     loc_18008E744
0x18008e6b5  call    cs:__imp_GetLastError
0x18008e6bb  mov     ebx, eax
0x18008e6bd  mov     ecx, 507h
0x18008e6c2  test    eax, eax
0x18008e6c4  cmovz   ebx, ecx
0x18008e6c7  lea     rcx, WPP_GLOBAL_Control
0x18008e6ce  mov     rax, cs:WPP_GLOBAL_Control
0x18008e6d5  cmp     rax, rcx
0x18008e6d8  jz      short loc_18008E6FE
0x18008e6da  test    [rax+1Ch], r14b
0x18008e6de  jz      short loc_18008E6FE
0x18008e6e0  cmp     byte ptr [rax+19h], 2
0x18008e6e4  jb      short loc_18008E6FE
0x18008e6e6  mov     edx, 12h
0x18008e6eb  mov     r9d, ebx
0x18008e6ee  lea     r8, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids
0x18008e6f5  mov     rcx, [rax+10h]
0x18008e6f9  call    WPP_SF_d
0x18008e6fe  xorps   xmm0, xmm0
0x18008e701  movdqu  [rsp+0C48h+var_960], xmm0
0x18008e70a  mov     [rsp+0C48h+var_950], rsi
0x18008e712  mov     [rsp+0C48h+var_948], ebx
0x18008e719  mov     [rsp+0C48h+var_944], 0FFFFFFFFh
0x18008e724  mov     [rsp+0C48h+var_940], 2C7h
0x18008e72f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008e736  lea     rcx, [rsp+0C48h+var_960]; pExceptionObject
0x18008e73e  call    _CxxThrowException_0
0x18008e744  lea     rcx, [rsp+0C48h+TempFileName]
0x18008e74c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e750  inc     rax
0x18008e753  cmp     [rcx+rax*2], si
0x18008e757  jnz     short loc_18008E750
0x18008e759  lea     rcx, [rsp+0C48h+TempFileName]
0x18008e761  mov     qword ptr [rsp+0C48h+var_BE8], rcx
0x18008e766  mov     qword ptr [rsp+0C48h+var_BE8+8], rax
0x18008e76b  lea     rdx, [rsp+0C48h+var_BE8]
0x18008e770  lea     rcx, [rsp+0C48h+var_B70]
0x18008e778  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18008e77d  mov     r9b, r14b
0x18008e780  mov     rdx, rax
0x18008e783  mov     rdi, [rsp+0C48h+var_B98]
0x18008e78b  mov     rcx, rdi; this
0x18008e78e  call    ?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z; RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)
0x18008e793  mov     rcx, rdi; this
0x18008e796  call    ?SyncFileHeader@RecordCache@@QEAAX_K_N@Z; RecordCache::SyncFileHeader(unsigned __int64,bool)
0x18008e79b  mov     [rbx], rdi
0x18008e79e  lea     r9, [rsp+0C48h+TempFileName]; lpTempFileName
0x18008e7a6  xor     r8d, r8d; uUnique
0x18008e7a9  lea     rdx, aPub; "PUB"
0x18008e7b0  lea     rcx, [rsp+0C48h+PathName]; lpPathName
0x18008e7b8  call    cs:__imp_GetTempFileNameW
0x18008e7be  test    eax, eax
0x18008e7c0  jnz     loc_18008E855
0x18008e7c6  call    cs:__imp_GetLastError
0x18008e7cc  mov     ebx, eax
0x18008e7ce  mov     ecx, 507h
0x18008e7d3  test    eax, eax
0x18008e7d5  cmovz   ebx, ecx
0x18008e7d8  lea     rcx, WPP_GLOBAL_Control
0x18008e7df  mov     rax, cs:WPP_GLOBAL_Control
0x18008e7e6  cmp     rax, rcx
0x18008e7e9  jz      short loc_18008E80F
0x18008e7eb  test    [rax+1Ch], r14b
0x18008e7ef  jz      short loc_18008E80F
0x18008e7f1  cmp     byte ptr [rax+19h], 2
0x18008e7f5  jb      short loc_18008E80F
0x18008e7f7  mov     edx, 13h
0x18008e7fc  mov     r9d, ebx
0x18008e7ff  lea     r8, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids
0x18008e806  mov     rcx, [rax+10h]
0x18008e80a  call    WPP_SF_d
0x18008e80f  xorps   xmm0, xmm0
0x18008e812  movdqu  [rsp+0C48h+var_938], xmm0
0x18008e81b  mov     [rsp+0C48h+var_928], rsi
0x18008e823  mov     [rsp+0C48h+var_920], ebx
0x18008e82a  mov     [rsp+0C48h+var_91C], 0FFFFFFFFh
0x18008e835  mov     [rsp+0C48h+var_918], 2D1h
0x18008e840  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008e847  lea     rcx, [rsp+0C48h+var_938]; pExceptionObject
0x18008e84f  call    _CxxThrowException_0
0x18008e855  lea     rcx, [rsp+0C48h+TempFileName]
0x18008e85d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e861  inc     rax
0x18008e864  cmp     [rcx+rax*2], si
0x18008e868  jnz     short loc_18008E861
0x18008e86a  lea     rcx, [rsp+0C48h+TempFileName]
0x18008e872  mov     qword ptr [rsp+0C48h+var_BE8], rcx
0x18008e877  mov     qword ptr [rsp+0C48h+var_BE8+8], rax
0x18008e87c  lea     rdx, [rsp+0C48h+var_BE8]
0x18008e881  lea     rcx, [rsp+0C48h+var_B70]
0x18008e889  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18008e88e  mov     r9b, r14b
0x18008e891  mov     rdx, rax
0x18008e894  mov     rdi, [rsp+0C48h+var_BA0]
0x18008e89c  mov     rcx, rdi; this
0x18008e89f  call    ?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z; RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)
0x18008e8a4  mov     rcx, rdi; this
0x18008e8a7  call    ?SyncFileHeader@RecordCache@@QEAAX_K_N@Z; RecordCache::SyncFileHeader(unsigned __int64,bool)
0x18008e8ac  lea     r9, [rsp+0C48h+TempFileName]; lpTempFileName
0x18008e8b4  xor     r8d, r8d; uUnique
0x18008e8b7  lea     rdx, aEvt; "EVT"
0x18008e8be  lea     rcx, [rsp+0C48h+PathName]; lpPathName
0x18008e8c6  call    cs:__imp_GetTempFileNameW
0x18008e8cc  test    eax, eax
0x18008e8ce  jnz     loc_18008E963
0x18008e8d4  call    cs:__imp_GetLastError
0x18008e8da  mov     ebx, eax
0x18008e8dc  mov     ecx, 507h
0x18008e8e1  test    eax, eax
0x18008e8e3  cmovz   ebx, ecx
0x18008e8e6  lea     rcx, WPP_GLOBAL_Control
0x18008e8ed  mov     rax, cs:WPP_GLOBAL_Control
0x18008e8f4  cmp     rax, rcx
0x18008e8f7  jz      short loc_18008E91D
0x18008e8f9  test    [rax+1Ch], r14b
0x18008e8fd  jz      short loc_18008E91D
0x18008e8ff  cmp     byte ptr [rax+19h], 2
0x18008e903  jb      short loc_18008E91D
0x18008e905  mov     edx, 14h
0x18008e90a  mov     r9d, ebx
0x18008e90d  lea     r8, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids
0x18008e914  mov     rcx, [rax+10h]
0x18008e918  call    WPP_SF_d
0x18008e91d  xorps   xmm0, xmm0
0x18008e920  movdqu  [rsp+0C48h+var_910], xmm0
0x18008e929  mov     [rsp+0C48h+var_900], rsi
0x18008e931  mov     [rsp+0C48h+var_8F8], ebx
0x18008e938  mov     [rsp+0C48h+var_8F4], 0FFFFFFFFh
0x18008e943  mov     [rsp+0C48h+var_8F0], 2D9h
0x18008e94e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18008e955  lea     rcx, [rsp+0C48h+var_910]; pExceptionObject
0x18008e95d  call    _CxxThrowException_0
0x18008e963  lea     rcx, [rsp+0C48h+TempFileName]
0x18008e96b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e96f  inc     rax
0x18008e972  cmp     [rcx+rax*2], si
0x18008e976  jnz     short loc_18008E96F
0x18008e978  lea     rcx, [rsp+0C48h+TempFileName]
0x18008e980  mov     qword ptr [rsp+0C48h+var_BE8], rcx
0x18008e985  mov     qword ptr [rsp+0C48h+var_BE8+8], rax
0x18008e98a  lea     rdx, [rsp+0C48h+var_BE8]
0x18008e98f  lea     rcx, [rsp+0C48h+var_B70]
0x18008e997  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18008e99c  mov     r9b, r14b
0x18008e99f  mov     rdx, rax
0x18008e9a2  mov     rcx, [rsp+0C48h+var_BD0]; this
0x18008e9a7  call    ?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z; RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)
0x18008e9ac  mov     rcx, [rsp+0C48h+var_BD0]; this
0x18008e9b1  call    ?SyncFileHeader@RecordCache@@QEAAX_K_N@Z; RecordCache::SyncFileHeader(unsigned __int64,bool)
0x18008e9b6  mov     r8, rbx; struct LocaleMessageTable *
0x18008e9b9  mov     rdx, rdi; struct RecordCache *
0x18008e9bc  lea     rcx, [rsp+0C48h+var_6A8]; this
0x18008e9c4  call    ?Open@LocalePublisherTable@@QEAAXPEAVRecordCache@@PEAVLocaleMessageTable@@_N@Z; LocalePublisherTable::Open(RecordCache *,LocaleMessageTable *,bool)
0x18008e9c9  mov     rax, [rsp+0C48h+var_BD0]
0x18008e9ce  mov     [rsp+0C48h+var_A48], rax
0x18008e9d6  mov     [rsp+0C48h+var_A40], rbx
0x18008e9de  call    cs:__imp_RpcRevertToSelf
  ... truncated ...
```
