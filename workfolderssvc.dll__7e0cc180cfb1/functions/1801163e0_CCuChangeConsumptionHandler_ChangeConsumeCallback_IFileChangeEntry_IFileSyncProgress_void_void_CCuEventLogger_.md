# CCuChangeConsumptionHandler::ChangeConsumeCallback(IFileChangeEntry *,IFileSyncProgress *,void *,void *,CCuEventLogger *,bool *,IFileSyncItemMetadata *,bool,ISyncFileSystemInterface *)

- ea: `0x1801163e0`
- end: `0x180118a2a`
- name: `?ChangeConsumeCallback@CCuChangeConsumptionHandler@@CAJPEAUIFileChangeEntry@@PEAUIFileSyncProgress@@PEAX2PEAVCCuEventLogger@@PEA_NPEAUIFileSyncItemMetadata@@_NPEAUISyncFileSystemInterface@@@Z`
- size: `9802`
- prototype: `static int(struct IFileChangeEntry *, struct IFileSyncProgress *, void *, void *, struct CCuEventLogger *, bool *, struct IFileSyncItemMetadata *, bool, struct ISyncFileSystemInterface *)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180120a9c`

## callees

- `0x180002ab0`
- `0x18000430d`
- `0x180006f5c`
- `0x180007de8`
- `0x180007e10`
- `0x180008080`
- `0x180009158`
- `0x1800091ac`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180035564`
- `0x18004af44`
- `0x18004b814`
- `0x180058d2c`
- `0x180058d44`
- `0x180058d88`
- `0x18006a410`
- `0x180080b60`
- `0x180083ed0`
- `0x180083ee4`
- `0x180083ef4`
- `0x18009c93c`
- `0x1800a0c30`
- `0x1800bb748`
- `0x180111420`
- `0x180115154`
- `0x180115170`
- `0x18011624c`
- `0x1801162ac`
- `0x18011637c`
- `0x1801163e0`
- `0x180119198`
- `0x1801194f0`
- `0x180119a80`
- `0x180119ac0`
- `0x18011acd0`
- `0x18011ad44`
- `0x18011adcc`
- `0x18011ae94`
- `0x18011af94`
- `0x18011b0d8`
- `0x18011e428`
- `0x18011e708`
- `0x18011ede8`
- `0x18012100c`
- `0x18012122c`
- `0x1801214ec`
- `0x180121654`
- `0x1801217bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011809e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011809e`
- `KERNEL32!CompareFileTime` at `0x18011771d`
- `KERNEL32!CompareFileTime` at `0x18011771d`
- `ntdll!NtClose` at `0x180116d74`
- `ntdll!NtClose` at `0x180116d74`

## pseudocode

```c
__int64 __fastcall CCuChangeConsumptionHandler::ChangeConsumeCallback(
        struct IFileChangeEntry *a1,
        struct IFileSyncProgress *a2,
        struct CCuCallbackHandlerContext::CallbackContext *a3,
        struct CCuChangeEntryContext *a4,
        struct CCuEventLogger *a5,
        bool *a6,
        struct IFileSyncItemMetadata *a7,
        bool a8,
        struct ISyncFileSystemInterface *a9)
{
  char *v12; // rax
  bool v13; // r9
  __int16 v14; // ax
  __int64 v15; // rcx
  __int64 (__fastcall *v16)(struct IFileChangeEntry *, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  char v19; // bl
  __int64 v20; // rax
  unsigned __int16 *v21; // r13
  __int16 v22; // ax
  __int64 *v23; // rcx
  struct CCuCallbackHandlerContext::CallbackContext *v24; // rbx
  __int64 v25; // rax
  int v26; // edi
  unsigned __int16 *v27; // rcx
  bool v28; // zf
  struct ISyncFileSystemInterface *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rbx
  const unsigned __int16 *v33; // rax
  unsigned int v34; // ebx
  unsigned int v35; // eax
  int v36; // eax
  bool v37; // sf
  __int64 v38; // rax
  __int16 v39; // ax
  const unsigned __int16 *v40; // rax
  const WCHAR *v41; // r10
  PCWSTR v42; // rax
  int v43; // edx
  int v44; // ecx
  unsigned int v45; // eax
  struct IFileSyncReplicaMetadata *v46; // r12
  int FileMetadataByNativeFileID; // eax
  __int16 v48; // ax
  __int16 v49; // ax
  struct CNtfsBaseFileConcurrencyBlob *v50; // rdx
  _OWORD *v51; // rax
  char v52; // di
  unsigned __int16 *v53; // rbx
  int v54; // eax
  unsigned int v55; // edx
  __int64 v56; // r8
  const unsigned __int16 *v57; // rbx
  int v58; // eax
  __int16 v59; // ax
  int v60; // eax
  __int16 v61; // ax
  __int16 v62; // ax
  __int16 v63; // ax
  int v64; // ecx
  struct CCuCallbackHandlerContext::CallbackContext *v65; // r12
  struct CCuEventLogger *v66; // r15
  unsigned __int16 *v67; // rcx
  int v68; // r8d
  CCuEventLogger *v69; // rcx
  __int64 v70; // rax
  char v71; // al
  char v72; // al
  struct ISyncFileSystemInterface *v73; // r15
  unsigned int v74; // ebx
  bool *v75; // r13
  BOOL v76; // esi
  struct _FILE_ID_128 *v77; // rax
  struct IFileSyncReplicaMetadata *v78; // rdi
  const unsigned __int16 *v79; // rbx
  __int64 (__fastcall *v80)(struct IFileSyncReplicaMetadata *, BOOL, bool, __int128 *); // rbx
  char v81; // al
  __int16 v82; // ax
  __int64 v83; // rbx
  __int64 v84; // rax
  _QWORD *v85; // rcx
  __int64 v86; // rdx
  int v87; // edi
  struct _FILE_ID_128 *v88; // rax
  struct IFileSyncReplicaMetadata *v89; // rdi
  __int64 v90; // rax
  int Item; // eax
  struct _FILE_ID_128 v92; // xmm6
  __int64 v93; // rax
  const unsigned __int16 *v94; // rbx
  char v95; // bl
  PVOID *v96; // rcx
  int v97; // eax
  struct ISyncFileSystemInterface *v98; // r14
  __int16 v99; // ax
  struct CNtfsBaseFileConcurrencyBlob *v100; // rdx
  int v101; // esi
  unsigned int v102; // ecx
  unsigned int v103; // ebx
  unsigned int v104; // ebx
  int FileInfoFromParentEnumeration; // [rsp+78h] [rbp-90h] BYREF
  __int16 v107; // [rsp+7Ch] [rbp-8Ch]
  __int16 v108; // [rsp+7Eh] [rbp-8Ah]
  struct IFileInfoFromDisk *v109; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v110; // [rsp+A0h] [rbp-68h] BYREF
  struct IFileSyncItemMetadata *v111; // [rsp+A8h] [rbp-60h] BYREF
  bool v112; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v113; // [rsp+B8h] [rbp-50h] BYREF
  struct IFileSyncItemMetadata *v114; // [rsp+C0h] [rbp-48h] BYREF
  bool v115; // [rsp+C8h] [rbp-40h] BYREF
  bool v116; // [rsp+C9h] [rbp-3Fh] BYREF
  bool v117; // [rsp+CAh] [rbp-3Eh] BYREF
  bool v118; // [rsp+CBh] [rbp-3Dh] BYREF
  bool v119; // [rsp+CCh] [rbp-3Ch] BYREF
  bool v120; // [rsp+CDh] [rbp-3Bh] BYREF
  bool v121; // [rsp+CEh] [rbp-3Ah] BYREF
  char v122; // [rsp+CFh] [rbp-39h] BYREF
  bool v123; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v124[7]; // [rsp+D1h] [rbp-37h] BYREF
  __int64 v125; // [rsp+D8h] [rbp-30h] BYREF
  unsigned int v126; // [rsp+E0h] [rbp-28h] BYREF
  struct CCuEventLogger *v127; // [rsp+E8h] [rbp-20h]
  __int64 v128; // [rsp+F0h] [rbp-18h] BYREF
  int v129; // [rsp+F8h] [rbp-10h] BYREF
  struct ISyncFileSystemInterface *v130; // [rsp+100h] [rbp-8h]
  __int64 v131; // [rsp+108h] [rbp+0h] BYREF
  struct CCuCallbackHandlerContext::CallbackContext *v132; // [rsp+110h] [rbp+8h]
  struct _FILE_ID_128 v133; // [rsp+118h] [rbp+10h] BYREF
  struct IFileSyncReplicaMetadata *v134; // [rsp+128h] [rbp+20h]
  __int64 v135; // [rsp+130h] [rbp+28h] BYREF
  __int64 v136; // [rsp+138h] [rbp+30h] BYREF
  __int64 v137; // [rsp+140h] [rbp+38h] BYREF
  __int64 v138; // [rsp+148h] [rbp+40h] BYREF
  int v139; // [rsp+150h] [rbp+48h] BYREF
  unsigned int v140; // [rsp+154h] [rbp+4Ch] BYREF
  PCWSTR SourceString; // [rsp+158h] [rbp+50h] BYREF
  __int64 v142; // [rsp+160h] [rbp+58h] BYREF
  int v143; // [rsp+168h] [rbp+60h] BYREF
  unsigned int v144; // [rsp+16Ch] [rbp+64h] BYREF
  int v145; // [rsp+170h] [rbp+68h] BYREF
  unsigned int v146; // [rsp+174h] [rbp+6Ch] BYREF
  unsigned int v147; // [rsp+178h] [rbp+70h] BYREF
  unsigned int v148; // [rsp+17Ch] [rbp+74h] BYREF
  unsigned __int16 *v149; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v150[8]; // [rsp+188h] [rbp+80h] BYREF
  __int64 v151; // [rsp+190h] [rbp+88h] BYREF
  __int64 v152; // [rsp+198h] [rbp+90h] BYREF
  int v153; // [rsp+1A0h] [rbp+98h] BYREF
  unsigned int v154; // [rsp+1A4h] [rbp+9Ch] BYREF
  __int64 v155; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v156; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v157; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 *v158; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v159; // [rsp+1C8h] [rbp+C0h] BYREF
  HANDLE Handle; // [rsp+1D0h] [rbp+C8h] BYREF
  FILETIME FileTime1; // [rsp+1D8h] [rbp+D0h] BYREF
  bool *v162; // [rsp+1E0h] [rbp+D8h]
  struct _FILE_ID_128 v163; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v164; // [rsp+1F8h] [rbp+F0h] BYREF
  struct IFileInfoFromDisk *v165; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v166; // [rsp+208h] [rbp+100h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v167; // [rsp+210h] [rbp+108h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v168; // [rsp+218h] [rbp+110h] BYREF
  FILETIME FileTime2; // [rsp+220h] [rbp+118h] BYREF
  __int64 v170; // [rsp+228h] [rbp+120h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v171; // [rsp+230h] [rbp+128h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v172; // [rsp+238h] [rbp+130h] BYREF
  __int128 Buf2; // [rsp+240h] [rbp+138h] BYREF
  struct _FILE_ID_128 Buf1; // [rsp+258h] [rbp+150h] BYREF
  struct _FILE_ID_128 v175; // [rsp+268h] [rbp+160h] BYREF
  char v176[16]; // [rsp+278h] [rbp+170h] BYREF
  __int64 v177; // [rsp+288h] [rbp+180h]
  struct _FILE_ID_128 v178; // [rsp+298h] [rbp+190h] BYREF
  struct _FILE_ID_128 v179; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int128 v180; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v181; // [rsp+2C8h] [rbp+1C0h]
  struct _FILE_ID_128 v182; // [rsp+2D0h] [rbp+1C8h] BYREF
  __int128 v183; // [rsp+2E0h] [rbp+1D8h] BYREF
  __int64 v184; // [rsp+2F0h] [rbp+1E8h]
  struct _FILE_ID_128 v185; // [rsp+2F8h] [rbp+1F0h] BYREF
  struct _FILE_ID_128 v186; // [rsp+308h] [rbp+200h] BYREF
  struct _FILE_ID_128 v187; // [rsp+318h] [rbp+210h] BYREF
  GUID v188; // [rsp+328h] [rbp+220h] BYREF
  _BYTE v189[16]; // [rsp+338h] [rbp+230h] BYREF
  _BYTE v190[16]; // [rsp+348h] [rbp+240h] BYREF
  _BYTE v191[16]; // [rsp+358h] [rbp+250h] BYREF
  _BYTE v192[16]; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v193[16]; // [rsp+378h] [rbp+270h] BYREF
  _BYTE v194[16]; // [rsp+388h] [rbp+280h] BYREF
  _BYTE v195[16]; // [rsp+398h] [rbp+290h] BYREF
  _BYTE v196[16]; // [rsp+3A8h] [rbp+2A0h] BYREF
  _BYTE v197[16]; // [rsp+3B8h] [rbp+2B0h] BYREF

  v127 = a5;
  v162 = a6;
  v130 = a9;
  v132 = a3;
  v12 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 68) >= 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
      v12 = (char *)WPP_GLOBAL_Control;
    }
  }
  if ( v12[68] < 0 && (unsigned __int8)v12[65] >= 6u )
  {
    v13 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v13 = 0;
LABEL_9:
  CEcsFunctionTracer::CEcsFunctionTracer(
    (CEcsFunctionTracer *)&FileInfoFromParentEnumeration,
    "CCuChangeConsumptionHandler::ChangeConsumeCallback",
    0x1D1u,
    v13);
  v110 = 0;
  v188 = GUID_NULL;
  v113 = 0;
  Buf2 = 0;
  v175 = 0;
  Buf1 = 0;
  v178 = 0;
  ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&v109);
  v137 = 0;
  v129 = 0;
  ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v114);
  v184 = 0;
  v183 = 0;
  EcsZeroOut<bool>(a6);
  v14 = 492;
  if ( !a1 )
    goto LABEL_397;
  v107 = 492;
  v14 = 493;
  if ( !a3 || (v107 = 493, v14 = 494, !a4) || (v107 = 494, v14 = 495, !a5) || (v107 = 495, v14 = 496, !a6) )
  {
LABEL_397:
    FileInfoFromParentEnumeration = -2147024809;
    goto LABEL_398;
  }
  FileInfoFromParentEnumeration = 0;
  v107 = 496;
  v134 = *(struct IFileSyncReplicaMetadata **)a3;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, GUID *))(*(_QWORD *)v134 + 32LL))(
                                    v134,
                                    &v188);
  v14 = 506;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 506;
  v15 = *((_QWORD *)a3 + 1);
  if ( v15 )
  {
    FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 48LL))(v15);
    v14 = 510;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v107 = 510;
  }
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, unsigned int *))(*(_QWORD *)a1 + 56LL))(
                                    a1,
                                    &v110);
  v14 = 513;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 513;
  v16 = *(__int64 (__fastcall **)(struct IFileChangeEntry *, __int64))(*(_QWORD *)a1 + 24LL);
  v17 = ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::operator&(&v113);
  v18 = v16(a1, v17);
  v19 = 0;
  FileInfoFromParentEnumeration = v18;
  if ( v18 < 0 )
  {
    v108 = 514;
    goto LABEL_399;
  }
  v107 = 514;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, struct _FILE_ID_128 *))(*(_QWORD *)a1 + 32LL))(
                                    a1,
                                    &Buf1);
  v14 = 516;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 516;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, struct _FILE_ID_128 *))(*(_QWORD *)a1 + 80LL))(
                                    a1,
                                    &v175);
  v14 = 517;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 517;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, struct _FILE_ID_128 *))(*(_QWORD *)a1 + 40LL))(
                                    a1,
                                    &v178);
  v14 = 518;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 518;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, __int64 *))(*(_QWORD *)a1 + 64LL))(
                                    a1,
                                    &v137);
  v14 = 520;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 520;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, int *))(*(_QWORD *)a1 + 48LL))(
                                    a1,
                                    &v129);
  v14 = 521;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v107 = 521;
  v20 = *(_QWORD *)Buf1.Identifier - *((_QWORD *)a3 + 5);
  if ( *(_QWORD *)Buf1.Identifier == *((_QWORD *)a3 + 5) )
    v20 = *(_QWORD *)&Buf1.Identifier[8] - *((_QWORD *)a3 + 6);
  v112 = v20 == 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 68) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_iiiiiiiDDS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      19,
      (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
      *(_DWORD *)&v178.Identifier[8],
      v178.Identifier[0],
      Buf1.Identifier[8],
      Buf1.Identifier[0],
      v175.Identifier[8],
      v175.Identifier[0],
      v137,
      v110,
      v129,
      (__int64)v113);
  }
  v21 = (unsigned __int16 *)&Format;
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    v166 = 0;
    if ( a9 )
    {
      v164 = 0;
      v158 = 0;
      FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(a9, &v158);
      v22 = 555;
      if ( FileInfoFromParentEnumeration < 0 )
      {
        v23 = (__int64 *)&v158;
LABEL_36:
        v108 = v22;
LABEL_37:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(v23);
        goto LABEL_399;
      }
      v24 = v132;
      v107 = 555;
      v25 = *v158;
      v163 = Buf1;
      v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct _FILE_ID_128 *, __int64 *))(v25 + 32))(
              v158,
              *((_QWORD *)v132 + 8),
              &v163,
              &v164);
      ATL::CComPtrBase<IFileInfoFromDisk>::Attach(&v109, v164);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v158);
    }
    else
    {
      v165 = 0;
      v24 = v132;
      v163 = Buf1;
      v26 = CNtfsFileInfoFromDisk::CreateInstance(*((void **)v132 + 8), &v163, &v165);
      ATL::CComPtrBase<IFileInfoFromDisk>::Attach(&v109, v165);
    }
    if ( v26 == -1073741790 )
    {
      if ( (v129 & 0x10) == 0 )
      {
        v27 = (unsigned __int16 *)&Format;
        if ( v113 )
          v27 = v113;
        CCuEventLogger::LogEvent(v127, -2147024891, 0, 0, (__int64)v27, 0);
        v28 = memcmp_0(&v178, &Buf2, 0x10u) == 0;
        v14 = 574;
        if ( v28 )
          goto LABEL_54;
        v107 = 574;
        FileInfoFromParentEnumeration = 0;
        v29 = v130;
        v163 = Buf1;
        v133 = v178;
        FileInfoFromParentEnumeration = CCuChangeConsumptionHandler::GetFileInfoFromParentEnumeration(
                                          &v133,
                                          &v163,
                                          v24,
                                          v127,
                                          v130,
                                          &v109);
        v14 = 581;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 581;
        (*(void (__fastcall **)(struct IFileInfoFromDisk *, __int64))(*(_QWORD *)v109 + 80LL))(v109, v137);
        v28 = ((*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 32LL))(v109) & 0x10) == 0;
        v14 = 584;
        if ( !v28 )
          goto LABEL_54;
        FileInfoFromParentEnumeration = 0;
        v107 = 584;
        if ( !v113 )
        {
          v30 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109);
          v31 = -1;
          do
            ++v31;
          while ( *(_WORD *)(v30 + 2 * v31) );
          v32 = v31 + 1;
          v28 = (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::Allocate(&v113, v31 + 1) == 0;
          v14 = 590;
          if ( v28 )
          {
            FileInfoFromParentEnumeration = -2147024882;
            goto LABEL_398;
          }
          FileInfoFromParentEnumeration = 0;
          v107 = 590;
          v33 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109);
          FileInfoFromParentEnumeration = StringCchCopyW(v113, v32, v33);
          v14 = 593;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_398;
          v107 = 593;
          (*(void (__fastcall **)(struct IFileInfoFromDisk *, unsigned __int16 *))(*(_QWORD *)v109 + 136LL))(v109, v113);
        }
LABEL_57:
        v115 = 0;
        v154 = 0;
        FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                          (char *)a4 + 256,
                                          &Buf1,
                                          &v154);
        v14 = 608;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 608;
        v34 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 88LL))(v109);
        v35 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 32LL))(v109);
        v36 = CCuFileSystemOperations::CheckFileAgainstReparsePoint(v35, v34, v29, &v115);
        v19 = 0;
        FileInfoFromParentEnumeration = v36;
        v37 = v36 < 0;
        v14 = 613;
        if ( v37 )
          goto LABEL_398;
        v107 = 613;
        if ( v115 )
        {
          CCuEventLogger::LogEvent(v127, -2134375935, 0, 0, (__int64)v113, 0);
          v14 = 617;
          FileInfoFromParentEnumeration = -2134375935;
          goto LABEL_398;
        }
        if ( (*(unsigned int (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 96LL))(v109) != 1 )
        {
          CCuEventLogger::LogEvent(v127, -2134375934, 0, 0, (__int64)v113, 0);
          v14 = 626;
          FileInfoFromParentEnumeration = -2134375934;
          goto LABEL_398;
        }
        if ( !v137 )
          v137 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 72LL))(v109);
        v38 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 72LL))(v109);
        if ( v137 != v38 )
        {
          if ( (v129 & 0x10) != 0
            && v113
            && (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 128LL))(v109) )
          {
            CEcsMemPtr<unsigned short,0>::CEcsMemPtr<unsigned short,0>(&SourceString);
            CEcsMemPtr<unsigned short,0>::CEcsMemPtr<unsigned short,0>(&v149);
            FileInfoFromParentEnumeration = CPathUtilities::GetNormalizedNtPath(
                                              v113,
                                              (unsigned __int16 **)&SourceString);
            v39 = 649;
            if ( FileInfoFromParentEnumeration < 0
              || (v107 = 649,
                  v40 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 128LL))(v109),
                  FileInfoFromParentEnumeration = CPathUtilities::GetNormalizedNtPath(v40, &v149),
                  v39 = 650,
                  FileInfoFromParentEnumeration < 0) )
            {
              v108 = v39;
              CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v149);
              CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
              goto LABEL_399;
            }
            v41 = SourceString;
            v107 = 650;
            v42 = SourceString;
            do
            {
              v43 = *(PCWSTR)((char *)v42 + (char *)v149 - (char *)SourceString);
              v44 = *v42 - v43;
              if ( v44 )
                break;
              ++v42;
            }
            while ( v43 );
            if ( !v44 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((char *)WPP_GLOBAL_Control + 68) < 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  20,
                  &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                  v113);
                v41 = SourceString;
              }
              Handle = 0;
              v45 = CCuFileSystemOperations::OpenFile(&Handle, 0x100021u, v41, 0, 0x21u);
              if ( (int)HRESULTFromNTSTATUS(v45) >= 0 )
              {
                if ( NtClose(Handle) < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 68) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
                }
                Handle = 0;
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && *((char *)WPP_GLOBAL_Control + 68) < 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
              }
            }
            CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v149);
            CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
          }
          FileInfoFromParentEnumeration = -2134375931;
          v14 = 682;
          goto LABEL_398;
        }
        if ( !a7 )
        {
          v46 = v134;
          FileMetadataByNativeFileID = CCuDBOperations::FindFileMetadataByNativeFileID(v134, &Buf1, &v114);
          if ( FileMetadataByNativeFileID >= 0 )
          {
            v128 = 0;
            FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v114, &v128);
            v48 = 693;
            if ( FileInfoFromParentEnumeration < 0
              || (v107 = 693,
                  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v128 + 32LL))(
                                                    v128,
                                                    &v166),
                  v48 = 694,
                  FileInfoFromParentEnumeration < 0) )
            {
              v108 = v48;
LABEL_97:
              v23 = &v128;
              goto LABEL_37;
            }
            v107 = 694;
            if ( v137 == v166 )
            {
              ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v131);
              ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v136);
              v153 = 0;
              if ( v29 )
              {
                v167 = 0;
                FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct ISyncFileSystemInterface *, struct IFileInfoFromDisk *, struct CNtfsBaseFileConcurrencyBlob **))(*(_QWORD *)v29 + 72LL))(
                                                  v29,
                                                  v109,
                                                  &v167);
                v49 = 707;
                if ( FileInfoFromParentEnumeration < 0 )
                {
LABEL_102:
                  v108 = v49;
LABEL_103:
                  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v136);
                  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v131);
                  goto LABEL_97;
                }
                v50 = v167;
              }
              else
              {
                v168 = 0;
                FileInfoFromParentEnumeration = CNtfsBaseFileConcurrencyBlob::CreateInstance(v109, &v168);
                v49 = 713;
                if ( FileInfoFromParentEnumeration < 0 )
                  goto LABEL_102;
                v50 = v168;
              }
              v107 = v49;
              ATL::CComPtrBase<IFileConcurrencyBlob>::Attach(&v131, v50);
              FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v114 + 184LL))(
                                                v114,
                                                &v136);
              v49 = 717;
              if ( FileInfoFromParentEnumeration < 0 )
                goto LABEL_102;
              v107 = 717;
              FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v131 + 24LL))(
                                                v131,
                                                v136,
                                                &v153);
              v49 = 720;
              if ( FileInfoFromParentEnumeration < 0 )
                goto LABEL_102;
              v107 = 720;
              if ( !v153 )
              {
                FileInfoFromParentEnumeration = 0;
                v107 = 726;
                goto LABEL_103;
              }
              ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v136);
              ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v131);
            }
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v128);
            goto LABEL_120;
          }
          if ( FileMetadataByNativeFileID != -2147216764 )
          {
            FileInfoFromParentEnumeration = FileMetadataByNativeFileID;
            v14 = 732;
            goto LABEL_398;
          }
          v14 = 732;
LABEL_119:
          v107 = v14;
          FileInfoFromParentEnumeration = 0;
LABEL_120:
          if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator!=(&v114, 0) )
          {
            FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int128 *))(*(_QWORD *)v114 + 48LL))(
                                              v114,
                                              &v183);
            v14 = 750;
            if ( FileInfoFromParentEnumeration < 0 )
              goto LABEL_398;
            v107 = 750;
          }
          if ( v112 )
            (*(void (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 120LL))(v109);
          v51 = (_OWORD *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(
                            v109,
                            v189);
          *(_OWORD *)(*((_QWORD *)a4 + 20) + 16LL * v154) = *v51;
          goto LABEL_135;
        }
        v186 = 0;
        ATL::CComPtr<IFileSyncItemMetadata>::operator=(&v114, a7);
        FileInfoFromParentEnumeration = CCuDBOperations::GetNativeFileID(v114, &v186);
        v14 = 744;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 744;
        v28 = memcmp_0(&v186, &Buf1, 0x10u) == 0;
        v14 = 745;
        if ( v28 )
        {
          v46 = v134;
          goto LABEL_119;
        }
LABEL_54:
        FileInfoFromParentEnumeration = -2147418113;
        goto LABEL_398;
      }
    }
    else
    {
      v19 = 0;
      if ( v26 >= 0 )
      {
        v29 = v130;
        goto LABEL_57;
      }
      if ( v26 == -1073741738 )
      {
        FileInfoFromParentEnumeration = -2134375931;
        v14 = 763;
        goto LABEL_398;
      }
      if ( v26 == -1073741811 )
      {
        v46 = v134;
        v52 = 1;
        goto LABEL_151;
      }
    }
    v53 = (unsigned __int16 *)&Format;
    if ( v113 )
      v53 = v113;
    v54 = HRESULTFromNTSTATUS((unsigned int)v26);
    CCuEventLogger::LogEvent(v127, v54, 0, 0, (__int64)v53, 0);
    v19 = 0;
    FileInfoFromParentEnumeration = HRESULTFromNTSTATUS((unsigned int)v26);
    v14 = 777;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v107 = 777;
  }
  v46 = v134;
LABEL_135:
  v52 = 0;
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) && (v110 & 0x409) != 0 )
  {
    v140 = 0;
    v116 = 0;
    v182 = 0;
    FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                      (char *)a4 + 256,
                                      &Buf1,
                                      &v140);
    v14 = 796;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v107 = 796;
    v55 = 0;
    v56 = *((_QWORD *)a4 + 28);
    while ( (unsigned __int64)v55 < *(_QWORD *)(32LL * v140 + v56 + 8) )
    {
      if ( !*(_BYTE *)(*(unsigned int *)(*(_QWORD *)(v56 + 32LL * v140) + 4LL * v55) + *((_QWORD *)a4 + 4)) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v113);
        }
        FileInfoFromParentEnumeration = -2134375930;
        v14 = 803;
        goto LABEL_398;
      }
      ++v55;
    }
    v57 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109);
    v133 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109
                                                                                                  + 112LL))(
                                     v109,
                                     v190);
    v58 = CCuDBOperations::ItemExist(&v133, v57, v46, &v116, &v182);
    v19 = 0;
    FileInfoFromParentEnumeration = v58;
    v37 = v58 < 0;
    v14 = 807;
    if ( v37 )
      goto LABEL_398;
    v107 = 807;
    if ( v116 && memcmp_0(&v182, &Buf1, 0x10u) )
      *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v140) = v182;
  }
LABEL_151:
  if ( (v110 & 0x202) != 0 )
  {
    ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v111);
    v177 = 0;
    v59 = 851;
    *(_OWORD *)v176 = 0;
    if ( v112 )
    {
      FileInfoFromParentEnumeration = -2134375932;
    }
    else
    {
      FileInfoFromParentEnumeration = 0;
      v107 = 851;
      v60 = CCuDBOperations::FindFileMetadataByNativeFileID(v46, &v175, &v111);
      if ( v60 >= 0 )
      {
        v125 = 0;
        v139 = 0;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, char *))(*(_QWORD *)v111 + 48LL))(
                                          v111,
                                          v176);
        v61 = 860;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v107 = 860;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, int *))(*(_QWORD *)v111 + 64LL))(
                                          v111,
                                          &v139);
        v61 = 862;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v107 = 862;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v111, &v125);
        v61 = 864;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v107 = 864;
        if ( (v139 & 0x10) == 0 )
        {
          if ( (v110 & 9) == 0 || !memcmp_0(&Buf1, &v175, 0x10u) || v52 )
            goto LABEL_221;
          FileTime1 = 0;
          (*(void (__fastcall **)(struct IFileInfoFromDisk *, FILETIME *))(*(_QWORD *)v109 + 40LL))(v109, &FileTime2);
          FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, FILETIME *))(*(_QWORD *)v111 + 80LL))(
                                            v111,
                                            &FileTime1);
          v61 = 960;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_155;
          v107 = 960;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_ii)(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              26,
              &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
              FileTime1,
              FileTime2);
          }
          if ( CompareFileTime(&FileTime1, &FileTime2)
            || ((*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 32LL))(v109) & 0x10) != 0 )
          {
LABEL_221:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 68) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_i_guid_iiS(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                29,
                (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                *(_DWORD *)v176,
                (__int64)&v176[8],
                v175.Identifier[8],
                v175.Identifier[0],
                (__int64)v113);
            }
            v65 = v132;
            FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v111, v132, 0);
            v61 = 1046;
            if ( FileInfoFromParentEnumeration >= 0 )
            {
              v69 = v127;
              v68 = 5;
              goto LABEL_225;
            }
            goto LABEL_155;
          }
          v118 = 0;
          v133 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(
                                           v109,
                                           v197);
          FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v133, v46, &v118);
          v61 = 975;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_155;
          v107 = 975;
          v61 = 976;
          if ( v118 )
          {
            FileInfoFromParentEnumeration = 0;
            v107 = 976;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 68) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              v70 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109);
              WPP_SF_iiSiii_guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                v175.Identifier[0],
                v70,
                Buf1.Identifier[8],
                Buf1.Identifier[0],
                v176[0],
                (__int64)&v176[8]);
            }
            v71 = ATL::CComPtrBase<IFileSyncItemMetadata>::operator!=(&v114, 0);
            v65 = v132;
            if ( v71 )
            {
              FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v114, v132, 0);
              v61 = 991;
              if ( FileInfoFromParentEnumeration < 0 )
                goto LABEL_155;
              v107 = 991;
            }
            FileInfoFromParentEnumeration = CCuCallbackHandlerContext::PrepareChangeVersion(v65);
            v61 = 994;
            if ( FileInfoFromParentEnumeration >= 0 )
            {
              v107 = 994;
              v72 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 32LL))(v109);
              v73 = v130;
              v74 = 22;
              if ( (v72 & 0x17) == (v139 & 0x17) )
                v74 = 6;
              if ( v130 )
              {
                v159 = 0;
                FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v130, &v159);
                if ( FileInfoFromParentEnumeration < 0 )
                {
                  v108 = 1012;
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v159);
                  goto LABEL_156;
                }
                v107 = 1012;
                if ( (*(int (__fastcall **)(__int64, struct IFileInfoFromDisk *))(*(_QWORD *)v159 + 72LL))(v159, v109) < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 68) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
                }
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v159);
              }
              FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, _QWORD, __int64))(*(_QWORD *)v125 + 40LL))(
                                                v125,
                                                v109,
                                                v74,
                                                (__int64)v65 + 24);
              v61 = 1026;
              if ( FileInfoFromParentEnumeration >= 0 )
              {
                v107 = 1026;
                FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *))(*(_QWORD *)v111 + 160LL))(v111);
                v61 = 1028;
                if ( FileInfoFromParentEnumeration >= 0 )
                {
                  v107 = 1028;
                  CCuEventLogger::LogEvent(v127, 0, 4, 0, (__int64)v113, (__int64)v176);
                  v19 = 1;
LABEL_229:
                  if ( !memcmp_0(&Buf1, &v175, 0x10u) )
                    ATL::CComPtrBase<IFileConcurrencyBlob>::Release(&v114);
                  v75 = v162;
                  *v162 = 1;
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v125);
                  goto LABEL_234;
                }
              }
            }
            goto LABEL_155;
          }
LABEL_184:
          FileInfoFromParentEnumeration = -2134375930;
LABEL_155:
          v108 = v61;
LABEL_156:
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v125);
LABEL_238:
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v111);
          goto LABEL_399;
        }
        v62 = v110;
        if ( (v110 & 2) != 0 )
        {
          v142 = 0;
          ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(v150);
          FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v111 + 280LL))(
                                            v111,
                                            &v142);
          v63 = 905;
          if ( FileInfoFromParentEnumeration >= 0 )
          {
            v107 = 905;
            v64 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v142 + 24LL))(v142, v150);
            FileInfoFromParentEnumeration = v64;
            v63 = 906;
            if ( v64 >= 0 )
            {
              v107 = 906;
              v63 = 907;
              if ( v64 == 1 )
              {
                FileInfoFromParentEnumeration = 0;
                v107 = 907;
                ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(v150);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v142);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 68) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                {
                  WPP_SF_i_guid_iiS(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    24,
                    (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                    *(_DWORD *)v176,
                    (__int64)&v176[8],
                    v175.Identifier[8],
                    v175.Identifier[0],
                    (__int64)v113);
                }
                v65 = v132;
                FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v111, v132, 0);
                v61 = 914;
                if ( FileInfoFromParentEnumeration < 0 )
                  goto LABEL_155;
                v66 = v127;
                v67 = (unsigned __int16 *)&Format;
                v107 = 914;
                if ( v113 )
                  v67 = v113;
                CCuEventLogger::LogEvent(v127, 0, 2, 0, (__int64)v67, (__int64)v176);
                v62 = v110;
                goto LABEL_175;
              }
              FileInfoFromParentEnumeration = -2134375930;
            }
          }
          v108 = v63;
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(v150);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v142);
          goto LABEL_156;
        }
        v65 = v132;
        v66 = v127;
LABEL_175:
        if ( (v62 & 0x200) == 0 )
        {
LABEL_228:
          v73 = v130;
          goto LABEL_229;
        }
        v117 = 0;
        FileInfoFromParentEnumeration = CCuChangeConsumptionHandler::DescendantAppearInNotAppliedChangeEntries(
                                          v111,
                                          a4,
                                          &v117);
        v61 = 925;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v107 = 925;
        v61 = 926;
        if ( !v117 )
        {
          FileInfoFromParentEnumeration = 0;
          v107 = 926;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_i_guid_iiS(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              25,
              (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
              *(_DWORD *)v176,
              (__int64)&v176[8],
              v175.Identifier[8],
              v175.Identifier[0],
              (__int64)v113);
          }
          FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v111, v65, 1);
          v61 = 935;
          if ( FileInfoFromParentEnumeration >= 0 )
          {
            v68 = 3;
            v69 = v66;
LABEL_225:
            v107 = v61;
            if ( v113 )
              v21 = v113;
            CCuEventLogger::LogEvent(v69, 0, v68, 0, (__int64)v21, (__int64)v176);
            goto LABEL_228;
          }
          goto LABEL_155;
        }
        goto LABEL_184;
      }
      if ( v60 == -2147216764 )
      {
        v65 = v132;
        v75 = v162;
        FileInfoFromParentEnumeration = 0;
        v73 = v130;
        v107 = 1069;
LABEL_234:
        ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v111);
        goto LABEL_240;
      }
      FileInfoFromParentEnumeration = v60;
      v59 = 1069;
    }
    v108 = v59;
    goto LABEL_238;
  }
  v73 = v130;
  v65 = v132;
  v75 = v162;
LABEL_240:
  if ( v52 )
  {
    v143 = 0;
    FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, int *))(*(_QWORD *)a1 + 48LL))(
                                      a1,
                                      &v143);
    v14 = 1088;
    if ( FileInfoFromParentEnumeration >= 0 )
    {
      v107 = 1088;
      if ( (v143 & 0x10) == 0 && (v110 & 1) != 0 )
      {
        FileInfoFromParentEnumeration = 0;
        v107 = 1096;
        goto LABEL_399;
      }
      FileInfoFromParentEnumeration = -2134375931;
      v14 = 1101;
    }
    goto LABEL_398;
  }
  if ( (v110 & 0x408) == 8 && (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v114, 0) )
    v110 |= 0x400u;
  if ( !v19 )
  {
    if ( (v110 & 0x401) != 0 )
    {
      v144 = 0;
      FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                        (char *)a4 + 256,
                                        &Buf1,
                                        &v144);
      v14 = 1138;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v107 = 1138;
      if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v114, 0) )
      {
        v76 = v112;
        if ( v112 )
        {
          v78 = v134;
        }
        else
        {
          v119 = 0;
          v187 = 0;
          v77 = (struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(
                                         v109,
                                         v191);
          v78 = v134;
          v133 = *v77;
          FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v133, v134, &v119);
          v14 = 1156;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_398;
          v107 = 1156;
          v14 = 1157;
          if ( !v119 )
          {
            FileInfoFromParentEnumeration = -2134375930;
            goto LABEL_398;
          }
          FileInfoFromParentEnumeration = 0;
          v107 = 1157;
          v120 = 0;
          v79 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109);
          v133 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(
                                           v109,
                                           v192);
          FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v133, v79, v78, &v120, &v187);
          v14 = 1160;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_398;
          v107 = 1160;
          if ( v120 )
          {
            *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v144) = v187;
            FileInfoFromParentEnumeration = -2134375930;
            v14 = 1165;
            goto LABEL_398;
          }
        }
        v181 = 0;
        v180 = 0;
        FileInfoFromParentEnumeration = CCuCallbackHandlerContext::PrepareChangeVersion(v65);
        v14 = 1173;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 1173;
        v80 = *(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, BOOL, bool, __int128 *))(*(_QWORD *)v78
                                                                                                  + 176LL);
        v81 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 32LL))(v109);
        FileInfoFromParentEnumeration = v80(v78, v76, (v81 & 0x10) != 0, &v180);
        v14 = 1177;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 1177;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_i_guid_ii(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            30,
            (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
            v180,
            (__int64)&v180 + 8);
        }
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, __int128 *, struct IFileSyncItemMetadata **))(*(_QWORD *)v78 + 192LL))(
                                          v78,
                                          &v180,
                                          &v114);
        v14 = 1183;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 1183;
        if ( v73 )
        {
          v155 = 0;
          FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v73, &v155);
          v22 = 1190;
          if ( FileInfoFromParentEnumeration < 0 )
          {
            v23 = &v155;
            goto LABEL_36;
          }
          v107 = 1190;
          if ( (*(int (__fastcall **)(__int64, struct IFileInfoFromDisk *))(*(_QWORD *)v155 + 72LL))(v155, v109) < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
          }
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v155);
        }
        v151 = 0;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v114, &v151);
        if ( FileInfoFromParentEnumeration < 0 )
        {
          v108 = 1204;
          v23 = &v151;
          goto LABEL_37;
        }
        v107 = 1204;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, __int64, __int64))(*(_QWORD *)v151 + 40LL))(
                                          v151,
                                          v109,
                                          1,
                                          (__int64)v65 + 24);
        v23 = &v151;
        v82 = 1207;
        if ( FileInfoFromParentEnumeration >= 0 )
        {
          v107 = 1207;
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v151);
          FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *))(*(_QWORD *)v114 + 160LL))(v114);
          v14 = 1211;
          if ( FileInfoFromParentEnumeration >= 0 )
          {
            v107 = 1211;
            CCuEventLogger::LogEvent(v127, 0, 7, 0, (__int64)v113, (__int64)&v180);
            *v75 = 1;
            goto LABEL_399;
          }
          goto LABEL_398;
        }
LABEL_279:
        v108 = v82;
        goto LABEL_37;
      }
      v185 = 0;
      v170 = 0;
      FileInfoFromParentEnumeration = CCuDBOperations::GetNativeParentFileID(v114, &v185);
      v14 = 1224;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v107 = 1224;
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v114 + 56LL))(
                                        v114,
                                        &v170);
      v14 = 1225;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v107 = 1225;
      v133 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(
                                       v109,
                                       v193);
      if ( memcmp_0(&v133, &v185, 0x10u)
        || (v83 = v170,
            v84 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109),
            (unsigned int)_o__wcsicmp(v84, v83)) )
      {
        v110 = v110 & 0xFFFFFBF6 | 8;
        goto LABEL_297;
      }
      if ( (v110 & 0x400) != 0 )
      {
        v85 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          v86 = 32;
LABEL_291:
          WPP_SF_(v85[7], v86, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
        }
      }
      else
      {
        v85 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          v86 = 33;
          goto LABEL_291;
        }
      }
    }
LABEL_297:
    v87 = 0;
    if ( (v110 & 8) == 0 || (v110 & 0x400) != 0 )
    {
LABEL_344:
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        goto LABEL_399;
      if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v114, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 37, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v113);
        }
        FileInfoFromParentEnumeration = -2134375931;
        v14 = 1428;
        goto LABEL_398;
      }
      v126 = 0;
      ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v138);
      ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v135);
      v98 = v130;
      if ( v130 )
      {
        v171 = 0;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct ISyncFileSystemInterface *, struct IFileInfoFromDisk *, struct CNtfsBaseFileConcurrencyBlob **))(*(_QWORD *)v130 + 72LL))(
                                          v130,
                                          v109,
                                          &v171);
        v99 = 1441;
        if ( FileInfoFromParentEnumeration < 0 )
        {
LABEL_353:
          v108 = v99;
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v135);
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v138);
          goto LABEL_399;
        }
        v100 = v171;
      }
      else
      {
        v172 = 0;
        FileInfoFromParentEnumeration = CNtfsBaseFileConcurrencyBlob::CreateInstance(v109, &v172);
        v99 = 1447;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_353;
        v100 = v172;
      }
      v107 = v99;
      ATL::CComPtrBase<IFileConcurrencyBlob>::Attach(&v135, v100);
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v114 + 184LL))(
                                        v114,
                                        &v138);
      v99 = 1451;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_353;
      v107 = 1451;
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v138
                                                                                                  + 24LL))(
                                        v138,
                                        v135,
                                        &v126);
      v99 = 1454;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_353;
      v101 = 0;
      v107 = 1454;
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v135);
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v138);
      v102 = v126;
      if ( (v126 & 0x20000) != 0 || (v110 & 0x10) != 0 )
      {
        v124[0] = 0;
        if ( !v98 )
          goto LABEL_370;
        v156 = 0;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v98, &v156);
        v22 = 1471;
        if ( FileInfoFromParentEnumeration < 0 )
        {
          v23 = &v156;
          goto LABEL_36;
        }
        v107 = 1471;
        if ( (*(int (__fastcall **)(__int64, struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v156 + 64LL))(
               v156,
               v109,
               v124) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
        }
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v156);
        v102 = v126;
        if ( !v124[0] )
LABEL_370:
          v101 = 4;
      }
      v103 = v101 | 0x10;
      if ( (v102 & 0x10000) == 0 )
        v103 = v101;
      if ( (v102 & 0x300000) != 0 )
      {
        v14 = 1503;
        if ( !v87 )
          goto LABEL_314;
        FileInfoFromParentEnumeration = 0;
        v103 |= 8u;
        v107 = 1503;
      }
      if ( (v102 & 0xFFFF0004) != 0 || v103 )
      {
        FileInfoFromParentEnumeration = CCuCallbackHandlerContext::PrepareChangeVersion(v65);
        v14 = 1512;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 1512;
        v103 |= 2u;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 68) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_i_guid_iiD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          39,
          (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
          v183,
          (__int64)&v183 + 8);
      }
      v152 = 0;
      FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v114, &v152);
      if ( FileInfoFromParentEnumeration < 0 )
      {
        v108 = 1539;
        v23 = &v152;
        goto LABEL_37;
      }
      v107 = 1539;
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, _QWORD, __int64))(*(_QWORD *)v152 + 40LL))(
                                        v152,
                                        v109,
                                        v103,
                                        (__int64)v65 + 24);
      v23 = &v152;
      v82 = 1542;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_279;
      v107 = 1542;
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v152);
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *))(*(_QWORD *)v114 + 160LL))(v114);
      v14 = 1545;
      if ( FileInfoFromParentEnumeration >= 0 )
      {
        v107 = 1545;
        CCuEventLogger::LogEvent(v127, 0, 8, v103, (__int64)v113, (__int64)&v183);
        *v75 = 1;
        if ( !v98 )
          goto LABEL_399;
        v157 = 0;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v98, &v157);
        if ( FileInfoFromParentEnumeration >= 0 )
        {
          v107 = 1558;
          if ( (*(int (__fastcall **)(__int64, _QWORD, struct IFileInfoFromDisk *, _QWORD))(*(_QWORD *)v157 + 56LL))(
                 v157,
                 v126,
                 v109,
                 0) < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
          }
        }
        else
        {
          v108 = 1558;
        }
        v23 = &v157;
        goto LABEL_37;
      }
LABEL_398:
      v108 = v14;
      goto LABEL_399;
    }
    if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v114, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 68) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v113);
      }
      FileInfoFromParentEnumeration = -2134375931;
      v14 = 1288;
      goto LABEL_398;
    }
    v145 = 0;
    FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, int *))(*(_QWORD *)v114 + 40LL))(
                                      v114,
                                      &v145);
    v14 = 1295;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v107 = 1295;
    v14 = 1296;
    if ( v145 )
      goto LABEL_314;
    FileInfoFromParentEnumeration = 0;
    v107 = 1296;
    v179 = 0;
    v121 = 0;
    v88 = (struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(
                                   v109,
                                   v194);
    v89 = v134;
    v133 = *v88;
    FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v133, v134, &v121);
    v14 = 1312;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v107 = 1312;
    if ( !v121 )
    {
      v146 = 0;
      v90 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109 + 112LL))(v109, v195);
      Item = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
               (char *)a4 + 256,
               v90,
               &v146);
      if ( Item < 0 )
      {
        if ( Item != -2147319765 )
        {
          FileInfoFromParentEnumeration = Item;
          v14 = 1347;
          goto LABEL_398;
        }
        v14 = 1347;
      }
      else
      {
        v92 = *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v146);
        v93 = *((_QWORD *)a4 + 4);
        v133 = v92;
        if ( *(_BYTE *)(v146 + v93) || !memcmp_0(&v133, &Buf2, 0x10u) )
          goto LABEL_318;
        v163 = Buf1;
        v122 = 0;
        v133 = v92;
        FileInfoFromParentEnumeration = CCuDBOperations::IsDescendant(&v163, &v133, v89, &v122, 0);
        v14 = 1341;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v107 = 1341;
        v14 = 1342;
        if ( v122 )
        {
LABEL_314:
          FileInfoFromParentEnumeration = -2134375932;
          goto LABEL_398;
        }
      }
      v107 = v14;
LABEL_318:
      FileInfoFromParentEnumeration = -2134375930;
      v14 = 1350;
      goto LABEL_398;
    }
    v123 = 0;
    v94 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v109 + 104LL))(v109);
    v133 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v109
                                                                                                  + 112LL))(
                                     v109,
                                     v196);
    FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v133, v94, v89, &v123, &v179);
    v14 = 1354;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v95 = 0;
    v107 = 1354;
    if ( v123 )
    {
      if ( memcmp_0(&v179, &Buf1, 0x10u) )
      {
        v147 = 0;
        v148 = 0;
        FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                          (char *)a4 + 256,
                                          &Buf1,
                                          &v147);
        v14 = 1372;
        if ( FileInfoFromParentEnumeration >= 0 )
        {
          v107 = 1372;
          *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v147) = v179;
          v97 = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                  (char *)a4 + 256,
                  &v179,
                  &v148);
          if ( v97 < 0 )
          {
            if ( v97 != -2147319765 )
            {
              FileInfoFromParentEnumeration = v97;
              v14 = 1388;
              goto LABEL_398;
            }
            v107 = 1388;
          }
          else
          {
            *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 16) + 16LL * v148) = Buf1;
          }
          FileInfoFromParentEnumeration = -2134375930;
          v14 = 1391;
        }
        goto LABEL_398;
      }
      v95 = 1;
      v96 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 68) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
      {
        goto LABEL_328;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
    }
    v96 = (PVOID *)WPP_GLOBAL_Control;
LABEL_328:
    if ( a8 )
    {
      FileInfoFromParentEnumeration = CCuChangeConsumptionHandler::MoveUnderDescendantCheck(v109, v89, a4);
      v14 = 1401;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v96 = (PVOID *)WPP_GLOBAL_Control;
      v107 = 1401;
    }
    v87 = 0;
    if ( !v95 )
    {
      if ( v96 != &WPP_GLOBAL_Control && *((char *)v96 + 68) < 0 && *((_BYTE *)v96 + 65) >= 4u )
        WPP_SF_qii(
          v96[7],
          36,
          &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
          v114,
          *(_QWORD *)&Buf1.Identifier[8],
          *(_QWORD *)Buf1.Identifier);
      v87 = 1;
    }
    goto LABEL_344;
  }
LABEL_399:
  v104 = FileInfoFromParentEnumeration;
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v114);
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v109);
  ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::~CHeapPtr<unsigned short,ATL::CComAllocator>(&v113);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&FileInfoFromParentEnumeration);
  return v104;
}

```

## disassembly

```asm
0x1801163e0  mov     rax, rsp
0x1801163e3  mov     [rax+10h], rbx
0x1801163e7  push    rbp
0x1801163e8  push    rsi
0x1801163e9  push    rdi
0x1801163ea  push    r12
0x1801163ec  push    r13
0x1801163ee  push    r14
0x1801163f0  push    r15
0x1801163f2  lea     rbp, [rax-318h]
0x1801163f9  sub     rsp, 3E0h
0x180116400  movaps  xmmword ptr [rax-48h], xmm6
0x180116404  mov     rax, cs:__security_cookie
0x18011640b  xor     rax, rsp
0x18011640e  mov     [rbp+310h+var_50], rax
0x180116415  mov     rbx, [rbp+310h+arg_20]
0x18011641c  mov     r14, r9
0x18011641f  mov     r15, [rbp+310h+arg_28]
0x180116426  mov     r13, r8
0x180116429  mov     rdi, [rbp+310h+arg_40]
0x180116430  mov     rsi, rcx
0x180116433  mov     r12, [rbp+310h+arg_30]
0x18011643a  mov     [rbp+310h+var_330], rbx
0x18011643e  mov     [rbp+310h+var_238], r15
0x180116445  mov     [rbp+310h+var_318], rdi
0x180116449  mov     [rbp+310h+var_308], r8
0x18011644d  mov     rax, cs:WPP_GLOBAL_Control
0x180116454  lea     rcx, WPP_GLOBAL_Control
0x18011645b  mov     edx, 6
0x180116460  cmp     rax, rcx
0x180116463  jz      short loc_180116491
0x180116465  test    byte ptr [rax+44h], 80h
0x180116469  jz      short loc_1801164A1
0x18011646b  cmp     [rax+41h], dl
0x18011646e  jb      short loc_180116491
0x180116470  mov     rcx, [rax+38h]
0x180116474  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x18011647b  mov     edx, 12h
0x180116480  call    WPP_SF_
0x180116485  mov     rax, cs:WPP_GLOBAL_Control
0x18011648c  mov     edx, 6
0x180116491  test    byte ptr [rax+44h], 80h
0x180116495  jz      short loc_1801164A1
0x180116497  cmp     [rax+41h], dl
0x18011649a  jb      short loc_1801164A1
0x18011649c  mov     r9b, 1
0x18011649f  jmp     short loc_1801164A4
0x1801164a1  xor     r9d, r9d; bool
0x1801164a4  mov     r8d, 1D1h; unsigned __int16
0x1801164aa  lea     rdx, aCcuchangeconsu_5; "CCuChangeConsumptionHandler::ChangeCons"...
0x1801164b1  lea     rcx, [rsp+410h+var_3A0]; this
0x1801164b6  call    ??0CEcsFunctionTracer@@QEAA@PEBDG_N@Z; CEcsFunctionTracer::CEcsFunctionTracer(char const *,ushort,bool)
0x1801164bb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801164c2  xor     eax, eax
0x1801164c4  lea     rcx, [rbp+310h+var_380]
0x1801164c8  xorps   xmm1, xmm1
0x1801164cb  mov     [rbp+310h+var_378], eax
0x1801164ce  movdqu  [rbp+310h+var_F0], xmm0
0x1801164d6  mov     [rbp+310h+var_360], rax
0x1801164da  xor     edx, edx
0x1801164dc  xorps   xmm0, xmm0
0x1801164df  movups  [rbp+310h+Buf2], xmm0
0x1801164e6  movups  xmmword ptr [rbp+310h+var_1B0.Identifier], xmm0
0x1801164ed  movups  [rbp+310h+Buf1], xmm1
0x1801164f4  movups  [rbp+310h+var_180], xmm1
0x1801164fb  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x180116500  xor     eax, eax
0x180116502  lea     rcx, [rbp+310h+var_358]
0x180116506  mov     [rbp+310h+var_2D8], rax
0x18011650a  mov     [rbp+310h+var_320], eax
0x18011650d  call    ??0?$CComPtr@UIFileConcurrencyBlob@@@ATL@@QEAA@XZ; ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(void)
0x180116512  xorps   xmm0, xmm0
0x180116515  xor     eax, eax
0x180116517  mov     rcx, r15
0x18011651a  mov     [rbp+310h+var_128], rax
0x180116521  movups  [rbp+310h+var_138], xmm0
0x180116528  call    ??$EcsZeroOut@_N@@YAXPEA_N@Z; EcsZeroOut<bool>(bool *)
0x18011652d  xor     ecx, ecx
0x18011652f  mov     eax, 1ECh
0x180116534  test    rsi, rsi
0x180116537  jz      loc_1801189C3
0x18011653d  mov     [rsp+410h+var_39C], ax
0x180116542  mov     eax, 1EDh
0x180116547  test    r13, r13
0x18011654a  jz      loc_1801189C3
0x180116550  mov     [rsp+410h+var_39C], ax
0x180116555  mov     eax, 1EEh
0x18011655a  test    r14, r14
0x18011655d  jz      loc_1801189C3
0x180116563  mov     [rsp+410h+var_39C], ax
0x180116568  mov     eax, 1EFh
0x18011656d  test    rbx, rbx
0x180116570  jz      loc_1801189C3
0x180116576  mov     [rsp+410h+var_39C], ax
0x18011657b  mov     eax, 1F0h
0x180116580  test    r15, r15
0x180116583  jz      loc_1801189C3
0x180116589  mov     [rsp+410h+var_3A0], ecx
0x18011658d  lea     rdx, [rbp+310h+var_F0]
0x180116594  mov     [rsp+410h+var_39C], ax
0x180116599  mov     rcx, [r13+0]
0x18011659d  mov     [rbp+310h+var_2F0], rcx
0x1801165a1  mov     rax, [rcx]
0x1801165a4  mov     rax, [rax+20h]
0x1801165a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801165ad  mov     [rsp+410h+var_3A0], eax
0x1801165b1  test    eax, eax
0x1801165b3  mov     eax, 1FAh
0x1801165b8  js      loc_1801189CB
0x1801165be  mov     [rsp+410h+var_39C], ax
0x1801165c3  mov     rcx, [r13+8]
0x1801165c7  test    rcx, rcx
0x1801165ca  jz      short loc_1801165EE
0x1801165cc  mov     rax, [rcx]
0x1801165cf  mov     rax, [rax+30h]
0x1801165d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801165d8  mov     [rsp+410h+var_3A0], eax
0x1801165dc  test    eax, eax
0x1801165de  mov     eax, 1FEh
0x1801165e3  js      loc_1801189CB
0x1801165e9  mov     [rsp+410h+var_39C], ax
0x1801165ee  mov     rax, [rsi]
0x1801165f1  lea     rdx, [rbp+310h+var_378]
0x1801165f5  mov     rcx, rsi
0x1801165f8  mov     rax, [rax+38h]
0x1801165fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116601  mov     [rsp+410h+var_3A0], eax
0x180116605  test    eax, eax
0x180116607  mov     eax, 201h
0x18011660c  js      loc_1801189CB
0x180116612  mov     [rsp+410h+var_39C], ax
0x180116617  lea     rcx, [rbp+310h+var_360]
0x18011661b  mov     rax, [rsi]
0x18011661e  mov     rbx, [rax+18h]
0x180116622  call    ??I?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAAPEAPEAGXZ; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::operator&(void)
0x180116627  mov     rdx, rax
0x18011662a  mov     rcx, rsi
0x18011662d  mov     rax, rbx
0x180116630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116635  xor     ebx, ebx
0x180116637  mov     [rsp+410h+var_3A0], eax
0x18011663b  mov     r15d, 202h
0x180116641  test    eax, eax
0x180116643  jns     short loc_180116650
0x180116645  mov     [rsp+410h+var_39A], r15w
0x18011664b  jmp     loc_1801189D0
0x180116650  mov     [rsp+410h+var_39C], r15w
0x180116656  lea     rdx, [rbp+310h+Buf1]
0x18011665d  mov     rax, [rsi]
0x180116660  mov     rcx, rsi
0x180116663  mov     rax, [rax+20h]
0x180116667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011666c  mov     [rsp+410h+var_3A0], eax
0x180116670  test    eax, eax
0x180116672  mov     eax, 204h
0x180116677  js      loc_1801189CB
0x18011667d  mov     [rsp+410h+var_39C], ax
0x180116682  lea     rdx, [rbp+310h+var_1B0]
0x180116689  mov     rax, [rsi]
0x18011668c  mov     rcx, rsi
0x18011668f  mov     rax, [rax+50h]
0x180116693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116698  mov     [rsp+410h+var_3A0], eax
0x18011669c  test    eax, eax
0x18011669e  mov     eax, 205h
0x1801166a3  js      loc_1801189CB
0x1801166a9  mov     [rsp+410h+var_39C], ax
0x1801166ae  lea     rdx, [rbp+310h+var_180]
0x1801166b5  mov     rax, [rsi]
0x1801166b8  mov     rcx, rsi
0x1801166bb  mov     rax, [rax+28h]
0x1801166bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801166c4  mov     [rsp+410h+var_3A0], eax
0x1801166c8  test    eax, eax
0x1801166ca  mov     eax, 206h
0x1801166cf  js      loc_1801189CB
0x1801166d5  mov     [rsp+410h+var_39C], ax
0x1801166da  lea     rdx, [rbp+310h+var_2D8]
0x1801166de  mov     rax, [rsi]
0x1801166e1  mov     rcx, rsi
0x1801166e4  mov     rax, [rax+40h]
0x1801166e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801166ed  mov     [rsp+410h+var_3A0], eax
0x1801166f1  test    eax, eax
0x1801166f3  mov     eax, 208h
0x1801166f8  js      loc_1801189CB
0x1801166fe  mov     [rsp+410h+var_39C], ax
0x180116703  lea     rdx, [rbp+310h+var_320]
0x180116707  mov     rax, [rsi]
0x18011670a  mov     rcx, rsi
0x18011670d  mov     rax, [rax+30h]
0x180116711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116716  mov     [rsp+410h+var_3A0], eax
0x18011671a  test    eax, eax
0x18011671c  mov     eax, 209h
0x180116721  js      loc_1801189CB
0x180116727  mov     r9, qword ptr [rbp+310h+Buf1]
0x18011672e  mov     r8, qword ptr [rbp+310h+Buf1+8]
0x180116735  mov     [rsp+410h+var_39C], ax
0x18011673a  mov     rax, r9
0x18011673d  sub     rax, [r13+28h]
0x180116741  jnz     short loc_18011674A
0x180116743  mov     rax, r8
0x180116746  sub     rax, [r13+30h]
0x18011674a  test    rax, rax
0x18011674d  setz    [rbp+310h+var_368]
0x180116751  mov     rcx, cs:WPP_GLOBAL_Control
0x180116758  lea     rax, WPP_GLOBAL_Control
0x18011675f  cmp     rcx, rax
0x180116762  jz      short loc_1801167DA
0x180116764  test    byte ptr [rcx+44h], 80h
0x180116768  jz      short loc_1801167DA
0x18011676a  cmp     byte ptr [rcx+41h], 4
0x18011676e  jb      short loc_1801167DA
0x180116770  mov     rax, [rbp+310h+var_360]
0x180116774  mov     edx, 13h
0x180116779  mov     rcx, [rcx+38h]
0x18011677d  mov     [rsp+410h+var_3B0], rax
0x180116782  mov     eax, [rbp+310h+var_320]
0x180116785  mov     dword ptr [rsp+410h+var_3B8], eax
0x180116789  mov     eax, [rbp+310h+var_378]
0x18011678c  mov     [rsp+410h+var_3C0], eax
0x180116790  mov     rax, [rbp+310h+var_2D8]
0x180116794  mov     [rsp+410h+var_3C8], rax
0x180116799  mov     rax, qword ptr [rbp+310h+var_1B0.Identifier]
0x1801167a0  mov     qword ptr [rsp+410h+var_3D0], rax
0x1801167a5  mov     rax, qword ptr [rbp+310h+var_1B0.Identifier+8]
0x1801167ac  mov     qword ptr [rsp+410h+var_3D8], rax
0x1801167b1  mov     rax, qword ptr [rbp+310h+var_180]
0x1801167b8  mov     qword ptr [rsp+410h+var_3E0], r9
0x1801167bd  mov     r9, qword ptr [rbp+310h+var_180+8]
0x1801167c4  mov     [rsp+410h+var_3E8], r8
0x1801167c9  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x1801167d0  mov     [rsp+410h+var_3F0], rax
0x1801167d5  call    WPP_SF_iiiiiiiDDS
0x1801167da  mov     r8d, 10h; Size
0x1801167e0  lea     rdx, [rbp+310h+Buf2]; Buf2
0x1801167e7  lea     rcx, [rbp+310h+Buf1]; Buf1
0x1801167ee  call    memcmp_0
0x1801167f3  lea     r13, Format
0x1801167fa  test    eax, eax
0x1801167fc  jz      loc_180117144
0x180116802  mov     [rbp+310h+var_210], rbx
0x180116809  test    rdi, rdi
0x18011680c  jz      loc_1801168AF
0x180116812  lea     rdx, [rbp+310h+var_258]
0x180116819  mov     [rbp+310h+var_220], rbx
0x180116820  mov     rcx, rdi
0x180116823  mov     [rbp+310h+var_258], rbx
0x18011682a  call    ??$QueryInterface@UIFileSystemExtInterface@@@IUnknown@@QEAAJPEAPEAUIFileSystemExtInterface@@@Z; IUnknown::QueryInterface<IFileSystemExtInterface>(IFileSystemExtInterface * *)
0x18011682f  mov     [rsp+410h+var_3A0], eax
0x180116833  test    eax, eax
0x180116835  mov     eax, 22Bh
0x18011683a  jns     short loc_180116852
0x18011683c  lea     rcx, [rbp+310h+var_258]
0x180116843  mov     [rsp+410h+var_39A], ax
0x180116848  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18011684d  jmp     loc_1801189D0
0x180116852  mov     rcx, [rbp+310h+var_258]
0x180116859  lea     r9, [rbp+310h+var_220]
0x180116860  movaps  xmm0, [rbp+310h+Buf1]
0x180116867  lea     r8, [rbp+310h+var_230]
0x18011686e  mov     rbx, [rbp+310h+var_308]
0x180116872  mov     [rsp+410h+var_39C], ax
0x180116877  mov     rax, [rcx]
0x18011687a  movdqa  xmmword ptr [rbp+310h+var_230.Identifier], xmm0
0x180116882  mov     rdx, [rbx+40h]
0x180116886  mov     rax, [rax+20h]
0x18011688a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011688f  mov     rdx, [rbp+310h+var_220]
0x180116896  lea     rcx, [rbp+310h+var_380]
0x18011689a  mov     edi, eax
0x18011689c  call    ?Attach@?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@QEAAXPEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::Attach(IFileInfoFromDisk *)
0x1801168a1  lea     rcx, [rbp+310h+var_258]
0x1801168a8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1801168ad  jmp     short loc_1801168F2
0x1801168af  movaps  xmm0, [rbp+310h+Buf1]
0x1801168b6  lea     r8, [rbp+310h+var_218]; struct IFileInfoFromDisk **
0x1801168bd  mov     [rbp+310h+var_218], rbx
0x1801168c4  lea     rdx, [rbp+310h+var_230]; struct _FILE_ID_128
0x1801168cb  mov     rbx, [rbp+310h+var_308]
0x1801168cf  movdqa  xmmword ptr [rbp+310h+var_230.Identifier], xmm0
0x1801168d7  mov     rcx, [rbx+40h]; void *
0x1801168db  call    ?CreateInstance@CNtfsFileInfoFromDisk@@SAJPEAXU_FILE_ID_128@@PEAPEAUIFileInfoFromDisk@@@Z; CNtfsFileInfoFromDisk::CreateInstance(void *,_FILE_ID_128,IFileInfoFromDisk * *)
0x1801168e0  mov     rdx, [rbp+310h+var_218]
0x1801168e7  lea     rcx, [rbp+310h+var_380]
0x1801168eb  mov     edi, eax
0x1801168ed  call    ?Attach@?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@QEAAXPEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::Attach(IFileInfoFromDisk *)
0x1801168f2  cmp     edi, 0C0000022h
0x1801168f8  jnz     loc_180116AB0
0x1801168fe  test    byte ptr [rbp+310h+var_320], 10h
0x180116902  jnz     loc_1801170F1
0x180116908  mov     rax, [rbp+310h+var_360]
0x18011690c  xor     edi, edi
0x18011690e  test    rax, rax
0x180116911  mov     [rsp+410h+var_3E8], rdi
0x180116916  mov     rcx, r13
0x180116919  mov     edx, 80070005h
0x18011691e  cmovnz  rcx, rax
0x180116922  xor     r9d, r9d
  ... truncated ...
```
