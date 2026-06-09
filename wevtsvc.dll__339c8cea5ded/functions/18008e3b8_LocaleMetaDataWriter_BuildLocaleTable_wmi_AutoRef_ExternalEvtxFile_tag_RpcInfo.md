# LocaleMetaDataWriter::BuildLocaleTable(wmi::AutoRef<ExternalEvtxFile>,tag_RpcInfo &)

- ea: `0x18008e3b8`
- end: `0x18008f896`
- name: `?BuildLocaleTable@LocaleMetaDataWriter@@QEAAXV?$AutoRef@VExternalEvtxFile@@@wmi@@AEAUtag_RpcInfo@@@Z`
- size: `5342`
- prototype: `void __fastcall(LPCWSTR *, wmi::RefBase **, __int64)`
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
// Hidden C++ exception states: #wind=2
void __fastcall LocaleMetaDataWriter::BuildLocaleTable(LPCWSTR *a1, wmi::RefBase **a2, __int64 a3)
{
  LPCWSTR *v4; // r13
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
  DWORD v31; // ebx
  _QWORD *v32; // rdi
  void **v33; // rax
  _QWORD *v34; // rbx
  wmi::RefBase **v35; // rbx
  BinXmlReader *CurrentRecordReader; // rbx
  __int64 *v37; // r13
  unsigned int v38; // ecx
  unsigned int v39; // r9d
  unsigned int v40; // r8d
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  void ***v44; // r12
  void **v45; // rbx
  void **v46; // r15
  __int64 v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // r15d
  PublisherMetadata *v50; // rax
  PublisherMetadata *v51; // rax
  unsigned __int64 v52; // r15
  int v53; // eax
  unsigned __int64 v54; // r15
  volatile signed __int32 *v55; // rax
  struct BinXmlReader *v56; // rbx
  __int64 v57; // rdx
  __int64 v58; // r8
  unsigned __int64 v59; // [rsp+48h] [rbp-C00h] BYREF
  BinXmlReader *v60; // [rsp+50h] [rbp-BF8h]
  __int128 v61; // [rsp+60h] [rbp-BE8h] BYREF
  volatile signed __int32 *v62; // [rsp+70h] [rbp-BD8h] BYREF
  RecordCache *v63; // [rsp+78h] [rbp-BD0h]
  RecordCache *v64; // [rsp+80h] [rbp-BC8h]
  RecordCache *v65; // [rsp+88h] [rbp-BC0h] BYREF
  RecordCache *v66; // [rsp+90h] [rbp-BB8h] BYREF
  RecordCache *v67; // [rsp+98h] [rbp-BB0h] BYREF
  LPCWSTR *v68; // [rsp+A0h] [rbp-BA8h]
  RecordCache *v69; // [rsp+A8h] [rbp-BA0h]
  RecordCache *v70; // [rsp+B0h] [rbp-B98h]
  __int64 v71; // [rsp+B8h] [rbp-B90h]
  volatile signed __int32 *v72; // [rsp+C0h] [rbp-B88h] BYREF
  PublisherMetadata *v73; // [rsp+C8h] [rbp-B80h]
  __int64 *v74; // [rsp+D0h] [rbp-B78h] BYREF
  _QWORD v75[2]; // [rsp+D8h] [rbp-B70h] BYREF
  __int64 v76; // [rsp+E8h] [rbp-B60h]
  char v77; // [rsp+F0h] [rbp-B58h]
  void **v78; // [rsp+F8h] [rbp-B50h]
  wmi::RefBase **v79; // [rsp+100h] [rbp-B48h]
  const struct OperationControl **v80; // [rsp+108h] [rbp-B40h] BYREF
  struct LocaleMessageTable *v81[2]; // [rsp+110h] [rbp-B38h] BYREF
  LPCWSTR *v82; // [rsp+120h] [rbp-B28h]
  wmi::RefBase **v83; // [rsp+130h] [rbp-B18h]
  __int64 v84; // [rsp+138h] [rbp-B10h]
  _QWORD v85[2]; // [rsp+140h] [rbp-B08h] BYREF
  void *v86; // [rsp+150h] [rbp-AF8h]
  __int64 v87; // [rsp+158h] [rbp-AF0h]
  void **v88; // [rsp+160h] [rbp-AE8h] BYREF
  __int64 v89; // [rsp+168h] [rbp-AE0h]
  __int64 v90; // [rsp+170h] [rbp-AD8h]
  char v91; // [rsp+178h] [rbp-AD0h]
  void **v92; // [rsp+180h] [rbp-AC8h] BYREF
  __int64 *v93; // [rsp+188h] [rbp-AC0h]
  __int64 v94; // [rsp+190h] [rbp-AB8h]
  char v95; // [rsp+198h] [rbp-AB0h]
  __int128 v96; // [rsp+1A0h] [rbp-AA8h] BYREF
  _WORD *v97; // [rsp+1B0h] [rbp-A98h] BYREF
  _WORD *v98; // [rsp+1B8h] [rbp-A90h]
  _BYTE v99[32]; // [rsp+1D0h] [rbp-A78h] BYREF
  _QWORD v100[4]; // [rsp+1F0h] [rbp-A58h] BYREF
  unsigned __int16 *v101; // [rsp+210h] [rbp-A38h]
  _QWORD pExceptionObject[3]; // [rsp+218h] [rbp-A30h] BYREF
  unsigned int v103; // [rsp+230h] [rbp-A18h]
  __int64 v104; // [rsp+234h] [rbp-A14h]
  char v105; // [rsp+23Ch] [rbp-A0Ch]
  _QWORD v106[3]; // [rsp+240h] [rbp-A08h] BYREF
  unsigned int v107; // [rsp+258h] [rbp-9F0h]
  __int64 v108; // [rsp+25Ch] [rbp-9ECh]
  char v109; // [rsp+264h] [rbp-9E4h]
  _QWORD v110[3]; // [rsp+268h] [rbp-9E0h] BYREF
  unsigned int v111; // [rsp+280h] [rbp-9C8h]
  __int64 v112; // [rsp+284h] [rbp-9C4h]
  char v113; // [rsp+28Ch] [rbp-9BCh]
  __int64 v114; // [rsp+290h] [rbp-9B8h]
  __int64 v115; // [rsp+298h] [rbp-9B0h]
  _QWORD v116[2]; // [rsp+2A0h] [rbp-9A8h] BYREF
  _QWORD v117[2]; // [rsp+2B0h] [rbp-998h] BYREF
  __int128 v118; // [rsp+2C0h] [rbp-988h] BYREF
  __int64 v119; // [rsp+2D0h] [rbp-978h]
  DWORD v120; // [rsp+2D8h] [rbp-970h]
  int v121; // [rsp+2DCh] [rbp-96Ch]
  int v122; // [rsp+2E0h] [rbp-968h]
  __int128 v123; // [rsp+2E8h] [rbp-960h] BYREF
  __int64 v124; // [rsp+2F8h] [rbp-950h]
  DWORD v125; // [rsp+300h] [rbp-948h]
  int v126; // [rsp+304h] [rbp-944h]
  int v127; // [rsp+308h] [rbp-940h]
  __int128 v128; // [rsp+310h] [rbp-938h] BYREF
  __int64 v129; // [rsp+320h] [rbp-928h]
  DWORD v130; // [rsp+328h] [rbp-920h]
  int v131; // [rsp+32Ch] [rbp-91Ch]
  int v132; // [rsp+330h] [rbp-918h]
  __int128 v133; // [rsp+338h] [rbp-910h] BYREF
  __int64 v134; // [rsp+348h] [rbp-900h]
  DWORD v135; // [rsp+350h] [rbp-8F8h]
  int v136; // [rsp+354h] [rbp-8F4h]
  int v137; // [rsp+358h] [rbp-8F0h]
  __int128 v138; // [rsp+360h] [rbp-8E8h] BYREF
  __int64 v139; // [rsp+370h] [rbp-8D8h]
  DWORD v140; // [rsp+378h] [rbp-8D0h]
  int v141; // [rsp+37Ch] [rbp-8CCh]
  int v142; // [rsp+380h] [rbp-8C8h]
  __int128 v143; // [rsp+388h] [rbp-8C0h] BYREF
  __int64 v144; // [rsp+398h] [rbp-8B0h]
  int v145; // [rsp+3A0h] [rbp-8A8h]
  int v146; // [rsp+3A4h] [rbp-8A4h]
  int v147; // [rsp+3A8h] [rbp-8A0h]
  __int128 v148; // [rsp+3B0h] [rbp-898h] BYREF
  __int64 v149; // [rsp+3C0h] [rbp-888h]
  int v150; // [rsp+3C8h] [rbp-880h]
  int v151; // [rsp+3CCh] [rbp-87Ch]
  int v152; // [rsp+3D0h] [rbp-878h]
  __int128 v153; // [rsp+3D8h] [rbp-870h] BYREF
  __int64 v154; // [rsp+3E8h] [rbp-860h]
  int v155; // [rsp+3F0h] [rbp-858h]
  int v156; // [rsp+3F4h] [rbp-854h]
  int v157; // [rsp+3F8h] [rbp-850h]
  __int128 v158; // [rsp+400h] [rbp-848h] BYREF
  __int64 v159; // [rsp+410h] [rbp-838h]
  int v160; // [rsp+418h] [rbp-830h]
  int v161; // [rsp+41Ch] [rbp-82Ch]
  int v162; // [rsp+420h] [rbp-828h]
  _BYTE v163[24]; // [rsp+428h] [rbp-820h] BYREF
  EvtException *v164; // [rsp+440h] [rbp-808h] BYREF
  _BYTE v165[32]; // [rsp+448h] [rbp-800h] BYREF
  char v166; // [rsp+468h] [rbp-7E0h] BYREF
  _BYTE v167[144]; // [rsp+480h] [rbp-7C8h] BYREF
  _BYTE v168[144]; // [rsp+510h] [rbp-738h] BYREF
  _BYTE v169[352]; // [rsp+5A0h] [rbp-6A8h] BYREF
  __int128 v170; // [rsp+700h] [rbp-548h]
  _BYTE v171[192]; // [rsp+710h] [rbp-538h] BYREF
  __int128 v172; // [rsp+7D0h] [rbp-478h] BYREF
  WCHAR TempFileName[68]; // [rsp+7E0h] [rbp-468h] BYREF
  bool v174; // [rsp+868h] [rbp-3E0h]
  WCHAR PathName[264]; // [rsp+9F0h] [rbp-258h] BYREF

  v71 = a3;
  v79 = a2;
  v4 = a1;
  v68 = a1;
  v82 = a1;
  v83 = a2;
  v84 = a3;
  v88 = &Buffer::`vftable';
  v89 = 0;
  v90 = 0;
  v91 = 1;
  Buffer::SetSize((Buffer *)&v88, 0);
  HIDWORD(v90) = 0;
  v92 = &Buffer::`vftable';
  v93 = 0;
  v94 = 0;
  v95 = 1;
  Buffer::SetSize((Buffer *)&v92, 0);
  HIDWORD(v94) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v97);
  LocalePublisherTable::LocalePublisherTable((LocalePublisherTable *)v169);
  v100[0] = 0;
  v100[1] = 0;
  utl::make_unique<LocaleMessageTable,,0>(v81);
  utl::make_unique<RecordCache,,0>(&v65);
  utl::make_unique<RecordCache,,0>(&v66);
  utl::make_unique<RecordCache,,0>(&v67);
  v5 = v81[0];
  if ( !v81[0] || (v69 = v65) == 0 || (v70 = v66) == 0 || (v63 = v67) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
    }
    v158 = 0;
    v159 = 0;
    v160 = 14;
    v161 = -1;
    v162 = 688;
    throw (EvtException *)&v158;
  }
  v6 = RpcImpersonateClient(0);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v6);
    }
    pExceptionObject[0] = &byte_1800EC961;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v103 = v7;
    v104 = -1;
    v105 = 0;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, LastError);
    }
    v118 = 0;
    v119 = 0;
    v120 = LastError;
    v121 = -1;
    v122 = 706;
    throw (EvtException *)&v118;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v9);
    }
    v123 = 0;
    v124 = 0;
    v125 = v9;
    v126 = -1;
    v127 = 711;
    throw (EvtException *)&v123;
  }
  v10 = -1;
  do
    ++v10;
  while ( TempFileName[v10] );
  *(_QWORD *)&v61 = TempFileName;
  *((_QWORD *)&v61 + 1) = v10;
  MakeOrThrowOOM(v75);
  v11 = v70;
  ((void (__fastcall *)(RecordCache *))RecordCache::OpenFile)(v70);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v14);
    }
    v128 = 0;
    v129 = 0;
    v130 = v14;
    v131 = -1;
    v132 = 721;
    throw (EvtException *)&v128;
  }
  v15 = -1;
  do
    ++v15;
  while ( TempFileName[v15] );
  *(_QWORD *)&v61 = TempFileName;
  *((_QWORD *)&v61 + 1) = v15;
  MakeOrThrowOOM(v75);
  v16 = v69;
  ((void (__fastcall *)(RecordCache *))RecordCache::OpenFile)(v69);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v19);
    }
    v133 = 0;
    v134 = 0;
    v135 = v19;
    v136 = -1;
    v137 = 729;
    throw (EvtException *)&v133;
  }
  v20 = -1;
  do
    ++v20;
  while ( TempFileName[v20] );
  *(_QWORD *)&v61 = TempFileName;
  *((_QWORD *)&v61 + 1) = v20;
  MakeOrThrowOOM(v75);
  ((void (__fastcall *)(RecordCache *))RecordCache::OpenFile)(v63);
  RecordCache::SyncFileHeader(v63, v21, v22);
  LocalePublisherTable::Open((LocalePublisherTable *)v169, v16, v5, v23);
  v100[2] = v63;
  v100[3] = v5;
  RpcRevertToSelf();
  v101 = (unsigned __int16 *)(v4 + 63);
  EventRendering::GetWinmetaPublisherMetadata(&v59, *((unsigned int *)v4 + 126));
  v64 = (RecordCache *)v59;
  if ( v59 )
    _InterlockedAdd((volatile signed __int32 *)(v59 + 8), 1u);
  LocalePublisherTableWriter::NewPublisherRecord((LocalePublisherTable::_PublisherRecord *)v169);
  wmi::AutoRef<PublisherMetadata>::Release(&v59);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>(v85);
  ((void (__fastcall *)(QueryXmlParser *))QueryXmlParser::QueryXmlParser)((QueryXmlParser *)v171);
  v64 = 0;
  v80 = (const struct OperationControl **)(v4 + 64);
  v24 = (EvtxFileQueryResult **)ExternalEvtxFile::Query(*a2, &v74, v4[64], (char *)v86 + 56, &qword_180111698);
  v25 = *v24;
  *v24 = 0;
  v64 = v25;
  wmi::AutoRef<PublisherMetadata>::Release(&v74);
  BinXmlExtractor::BinXmlExtractor((BinXmlExtractor *)v168, MessageRenderExtractorCallbackIndexed);
  for ( i = 0; i < 0x12; ++i )
  {
    v96 = *(_OWORD *)&(&off_1800DF250)[3 * (int)i];
    BinXmlExtractor::AddPath((int)v168, (int)&v96, i, 0, (int)(&off_1800DF250)[3 * (int)i + 1]);
  }
  BinXmlExtractor::BinXmlExtractor((BinXmlExtractor *)v167, MessageRenderExtractorCallbackIncremental);
  *(_QWORD *)&v61 = L"/Event/EventData/Data";
  *((_QWORD *)&v61 + 1) = 21;
  BinXmlExtractor::AddPath((int)v167, (int)&v61, 0, 0, 0);
  *(_QWORD *)&v61 = L"/Event/UserData";
  *((_QWORD *)&v61 + 1) = 15;
  BinXmlExtractor::AddPath((int)v167, (int)&v61, 1, 1, 0);
  while ( 1 )
  {
    CheckCancellation(*v80);
    if ( !EvtxFileQueryResult::NextRecord(v25) )
      break;
    if ( *((_BYTE *)v25 + 68) )
    {
      CurrentRecordReader = EvtxFileQueryResult::GetCurrentRecordReader(v25);
      v60 = CurrentRecordReader;
      Buffer::SetCurrentIndex((Buffer *)&v92, 0);
      Buffer::SetCurrentIndex((Buffer *)&v88, 0);
      ((void (__stdcall *)(BinXmlExtractor *, struct BinXmlReader *, void *))BinXmlExtractor::Process)(
        (BinXmlExtractor *)v168,
        CurrentRecordReader,
        &v88);
      v37 = v93;
      v38 = v94;
      v39 = (unsigned int)v94 >> 4;
      v40 = 0;
      if ( (unsigned int)v94 >> 4 )
      {
        do
        {
          v41 = 2LL * v40;
          if ( HIDWORD(v37[v41 + 1]) == 1
            || HIDWORD(v37[v41 + 1]) == 2
            || HIDWORD(v37[v41 + 1]) == 14
            || HIDWORD(v37[v41 + 1]) == 15
            || (unsigned int)(HIDWORD(v37[v41 + 1]) - 18) <= 1 )
          {
            v37[v41] += v89;
          }
          ++v40;
        }
        while ( v40 < v39 );
        v38 = v94;
        v37 = v93;
      }
      v59 = v38;
      v74 = v37;
      v42 = *v37;
      v43 = -1;
      do
        ++v43;
      while ( *(_WORD *)(v42 + 2 * v43) );
      *(_QWORD *)&v61 = *v37;
      *((_QWORD *)&v61 + 1) = v43;
      v44 = (void ***)(v68 + 65);
      *(_QWORD *)&v172 = v68 + 65;
      v45 = (void **)(v68 + 65);
      if ( v68[67] != (LPCWSTR)(v68 + 65) )
      {
        v46 = *v44;
        do
        {
          if ( (unsigned __int8)tlx::istring_less_ordinal::operator()<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                                  v42,
                                  v46 + 3,
                                  &v61) )
          {
            v47 = 2;
          }
          else
          {
            v45 = v46;
            v47 = 1;
          }
          v46 = (void **)v46[v47];
        }
        while ( v46 != &utl::_TreeSentinel );
        LODWORD(v44) = v172;
        v78 = v45;
        if ( v45 == (void **)v172 )
          goto LABEL_123;
        if ( !(unsigned __int8)tlx::istring_less_ordinal::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t,wchar_t,0>(
                                 v42,
                                 &v61,
                                 v45 + 3) )
        {
          v52 = v59;
          goto LABEL_144;
        }
      }
      v78 = v45;
LABEL_123:
      v62 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v48 = RpcImpersonateClient(0);
        v49 = v48;
        if ( v48 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v48);
          }
          v110[0] = &byte_1800EC961;
          v110[1] = 0;
          v110[2] = 0;
          v111 = v49;
          v112 = -1;
          v113 = 0;
          throw (EvtException *)v110;
        }
        v114 = *v37;
        v115 = *((unsigned int *)v37 + 2);
        PublisherConfigReader::PublisherConfigReader((PublisherConfigReader *)TempFileName);
        RpcRevertToSelf();
        v50 = (PublisherMetadata *)operator new(0x180u);
        v73 = v50;
        if ( v50 )
          v51 = PublisherMetadata::PublisherMetadata(
                  v50,
                  (const struct PublisherConfigReader *)TempFileName,
                  *v101,
                  v174);
        else
          v51 = 0;
        wmi::AutoRef<EventSession>::operator=(&v62, v51);
        v73 = (PublisherMetadata *)v62;
        if ( v62 )
          _InterlockedAdd(v62 + 2, 1u);
        LocalePublisherTableWriter::NewPublisherRecord((LocalePublisherTable::_PublisherRecord *)v169);
        PublisherConfigReader::~PublisherConfigReader((PublisherConfigReader *)TempFileName);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &EvtException `RTTI Type Descriptor', &v164) )
        {
          if ( *((_DWORD *)v164 + 6) )
            wmi::AutoRef<PublisherMetadata>::Release(&v62);
          v69 = v65;
          v70 = v66;
          v63 = v67;
          v25 = v64;
          LODWORD(v45) = (_DWORD)v78;
          v37 = v74;
          v68 = v82;
          v79 = v83;
          v71 = v84;
          LODWORD(v44) = v172;
          __eh34_try_continuation(0, &EvtException `RTTI Type Descriptor', &loc_18008F42C);
        }
      }
      v52 = v59;
      v172 = v61;
      v53 = MakeOrThrowOOM(v165);
      v45 = *(void ***)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,wmi::AutoRef<PublisherMetadata>>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wmi::AutoRef<PublisherMetadata>>(
                         (int)v44,
                         (int)&v166,
                         (int)v45,
                         v53,
                         (__int64)&v62);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v165);
      if ( !v45 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
        }
        v153 = 0;
        v154 = 0;
        v155 = 14;
        v156 = -1;
        v157 = 845;
        throw (EvtException *)&v153;
      }
      wmi::AutoRef<PublisherMetadata>::Release(&v62);
LABEL_144:
      v54 = v52 >> 4;
      v55 = (volatile signed __int32 *)v45[7];
      v72 = v55;
      if ( v55 )
      {
        _InterlockedAdd(v55 + 2, 1u);
        v55 = v72;
      }
      if ( v55 )
      {
        v172 = 0;
        LODWORD(v62) = 0;
        v117[0] = v37;
        v117[1] = v54;
        GetEventDescriptor(v117, &v172, &v62);
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          v75[0] = &Buffer::`vftable';
          v75[1] = 0;
          v76 = 0;
          v77 = 1;
          Buffer::SetSize((Buffer *)v75, 0);
          HIDWORD(v76) = 0;
          v56 = v60;
          BinXmlReader::Reset(v60);
          ((void (__stdcall *)(BinXmlExtractor *, struct BinXmlReader *, void *))BinXmlExtractor::Process)(
            (BinXmlExtractor *)v167,
            v56,
            v75);
          utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v163);
          v116[0] = v57;
          v116[1] = v58;
          ConvertVariantsToStrings(v116, v163);
          v98 = v97;
          *v97 = 0;
          EventRendering::GetEventDescription((int)&v72, (int)&v172, -1, (int)v163, 1, (__int64)&v97, v71);
          utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(v163);
          Buffer::~Buffer((Buffer *)v75);
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &EvtException `RTTI Type Descriptor', 0) )
          {
            v98 = v97;
            *v97 = 0;
            v69 = v65;
            v70 = v66;
            v63 = v67;
            v25 = v64;
            v37 = v74;
            v68 = v82;
            v79 = v83;
            v71 = v84;
            __eh34_try_continuation(2, &EvtException `RTTI Type Descriptor', &loc_18008F745);
          }
        }
        *(_QWORD *)&v96 = v97;
        *((_QWORD *)&v96 + 1) = v98 - v97;
        LocaleEventTableWriter::NewEvent(v100, v37[20], &v96);
        wmi::AutoRef<PublisherMetadata>::Release(&v72);
      }
      else
      {
        wmi::AutoRef<PublisherMetadata>::Release(&v72);
      }
      v4 = v68;
    }
  }
  v170 = 0;
  v27 = (BinXmlReader *)MIDL_user_allocate(0x460u);
  v60 = v27;
  if ( v27 )
    v28 = SectionCache::SectionCache(v27);
  else
    v28 = 0;
  v80 = (const struct OperationControl **)v28;
  if ( !v28 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
    }
    v148 = 0;
    v149 = 0;
    v150 = 14;
    v151 = -1;
    v152 = 900;
    throw (EvtException *)&v148;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v99);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v99,
                           *v4,
                           v4[1] - *v4)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           v99,
                           92)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v99)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           v99,
                           46)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v99) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, 14);
    }
    v143 = 0;
    v144 = 0;
    v145 = 14;
    v146 = -1;
    v147 = 910;
    throw (EvtException *)&v143;
  }
  v29 = RpcImpersonateClient(0);
  v30 = v29;
  if ( v29 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v29);
    }
    v106[0] = &byte_1800EC961;
    v106[1] = 0;
    v106[2] = 0;
    v107 = v30;
    v108 = -1;
    v109 = 0;
    throw (EvtException *)v106;
  }
  if ( !CreateDirectoryW(*v4, 0) && GetLastError() != 183 )
  {
    v31 = GetLastError();
    if ( !v31 )
      v31 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_a3f39844e62535b7e3ab5e50b55dad4b_Traceguids, v31);
    }
    v138 = 0;
    v139 = 0;
    v140 = v31;
    v141 = -1;
    v142 = 923;
    throw (EvtException *)&v138;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
    v100,
    v99);
  ((void (__fastcall *)(RecordCache *))RecordCache::OpenFile)(v28);
  RpcRevertToSelf();
  v65 = 0;
  v59 = (unsigned __int64)v69;
  SectionCache::AddSection(v28, L"PUB", &v59);
  v67 = 0;
  v59 = (unsigned __int64)v63;
  SectionCache::AddSection(v28, L"EVT", &v59);
  v66 = 0;
  v59 = (unsigned __int64)v70;
  SectionCache::AddSection(v28, L"MSG", &v59);
  SectionCache::BuildFile((RTL_SRWLOCK *)v28);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v99);
  utl::unique_ptr<SectionCache,utl::default_delete<SectionCache>>::~unique_ptr<SectionCache,utl::default_delete<SectionCache>>(&v80);
  BinXmlExtractor::~BinXmlExtractor((BinXmlExtractor *)v167);
  BinXmlExtractor::~BinXmlExtractor((BinXmlExtractor *)v168);
  if ( v25 )
    wmi::RefBase::Release(v25);
  QueryXmlParser::~QueryXmlParser((QueryXmlParser *)v171);
  v32 = v86;
  if ( v86 == v85 )
    goto LABEL_89;
  while ( 2 )
  {
    v33 = (void **)v32[1];
    if ( v33 != &utl::_TreeSentinel )
    {
LABEL_87:
      v32 = v33;
      continue;
    }
    break;
  }
LABEL_83:
  v33 = (void **)v32[2];
  if ( v33 != &utl::_TreeSentinel )
    goto LABEL_87;
  while ( 1 )
  {
    v34 = v32;
    v32 = (_QWORD *)(*v32 & 0xFFFFFFFFFFFFFFFEuLL);
    utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<unsigned long,QueryNode,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,QueryNode>>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::map<unsigned long,QueryNode,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,QueryNode>>>>(v34 + 3);
    operator delete(v34);
    if ( v32 == v85 )
      break;
    if ( (void **)v32[1] != &utl::_TreeSentinel )
    {
      v32[1] = &utl::_TreeSentinel;
      goto LABEL_83;
    }
  }
  v85[0] = v85;
  v85[1] = v85;
  v86 = v85;
  v87 = 0;
LABEL_89:
  utl::unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>::~unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>(&v67);
  utl::unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>::~unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>(&v66);
  utl::unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>::~unique_ptr<CXPathExpression,utl::default_delete<CXPathExpression>>(&v65);
  utl::unique_ptr<LocaleMessageTable,utl::default_delete<LocaleMessageTable>>::~unique_ptr<LocaleMessageTable,utl::default_delete<LocaleMessageTable>>(v81);
  LocalePublisherTable::~LocalePublisherTable((LocalePublisherTable *)v169);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v97);
  VariantValues::~VariantValues((VariantValues *)&v88);
  v35 = v79;
  if ( *v79 )
    wmi::RefBase::Release(*v79);
  *v35 = 0;
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
0x18008e58f  lea     rax, byte_1800EC961
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
