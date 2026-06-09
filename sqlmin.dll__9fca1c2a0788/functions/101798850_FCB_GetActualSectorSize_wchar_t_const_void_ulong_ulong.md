# FCB::GetActualSectorSize(wchar_t const *,void *,ulong &,ulong *)

- ea: `0x101798850`
- end: `0x1017999f0`
- name: `?GetActualSectorSize@FCB@@SAHPEB_WPEAXAEAKPEAK@Z`
- size: `4512`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeMountPoint, void *, LPDWORD lpBytesPerSector, unsigned int *)`
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1004724a0`
- `0x101f82710`
- `0x101fc8320`
- `0x101ffbb00`
- `0x102062ab0`

## callees

- `0x100401490`
- `0x10042d300`
- `0x10045e0a0`
- `0x10061fb80`
- `0x1017611a0`
- `0x101761910`
- `0x101761990`
- `0x101797a30`
- `0x101797e80`
- `0x101798590`
- `0x101798850`
- `0x101801aa0`
- `0x101a45380`
- `0x1023aecb0`
- `0x1023aee60`
- `0x1023af450`

## import_xrefs

- `KERNEL32!SetLastError` at `0x101799032`
- `KERNEL32!SetLastError` at `0x101799876`
- `KERNEL32!SetLastError` at `0x101799032`
- `KERNEL32!SetLastError` at `0x101799876`
- `KERNEL32!GetVolumePathNameW` at `0x101798c5b`
- `KERNEL32!GetVolumePathNameW` at `0x101798c5b`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x101798e07`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x101798e07`
- `KERNEL32!GetFileType` at `0x10179904f`
- `KERNEL32!GetFileType` at `0x10179904f`
- `KERNEL32!CloseHandle` at `0x10179911e`
- `KERNEL32!CloseHandle` at `0x101799215`
- `KERNEL32!CloseHandle` at `0x10179955a`
- `KERNEL32!CloseHandle` at `0x101799651`
- `KERNEL32!CloseHandle` at `0x10179911e`
- `KERNEL32!CloseHandle` at `0x101799215`
- `KERNEL32!CloseHandle` at `0x10179955a`
- `KERNEL32!CloseHandle` at `0x101799651`
- `KERNEL32!GetLastError` at `0x101798b32`
- `KERNEL32!GetLastError` at `0x101798c63`
- `KERNEL32!GetLastError` at `0x101798e0f`
- `KERNEL32!GetLastError` at `0x101799012`
- `KERNEL32!GetLastError` at `0x101799038`
- `KERNEL32!GetLastError` at `0x101799243`
- `KERNEL32!GetLastError` at `0x10179987c`
- `KERNEL32!GetLastError` at `0x101798b32`
- `KERNEL32!GetLastError` at `0x101798c63`
- `KERNEL32!GetLastError` at `0x101798e0f`
- `KERNEL32!GetLastError` at `0x101799012`
- `KERNEL32!GetLastError` at `0x101799038`
- `KERNEL32!GetLastError` at `0x101799243`
- `KERNEL32!GetLastError` at `0x10179987c`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1017988bc`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1017988bc`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1017988d9`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1017988d9`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101798b01`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1017989fc`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1017989fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10179896d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017999e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10179896d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017999e4`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101798b08`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101798b08`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798be3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798c2e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798cc2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798d0e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798e6d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798eb8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017990b0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017990fb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017992ae`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017992f9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179936a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017993b5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179945f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017994aa`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017995a5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017995f0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017996e0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179972b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017997a7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017997f2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017998d2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179991d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798be3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798c2e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798cc2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798d0e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798e6d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101798eb8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017990b0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017990fb`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017992ae`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017992f9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179936a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017993b5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179945f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017994aa`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017995a5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017995f0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017996e0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179972b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017997a7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017997f2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1017998d2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10179991d`
- `sqldk!SystemThread_TlsIndex` at `0x1017989bd`
- `sqldk!SystemThread_TlsIndex` at `0x101798a11`
- `sqldk!SystemThread_TlsIndex` at `0x101798bb4`
- `sqldk!SystemThread_TlsIndex` at `0x101798bff`
- `sqldk!SystemThread_TlsIndex` at `0x101798c92`
- `sqldk!SystemThread_TlsIndex` at `0x101798cde`
- `sqldk!SystemThread_TlsIndex` at `0x101798e3e`
- `sqldk!SystemThread_TlsIndex` at `0x101798e89`
- `sqldk!SystemThread_TlsIndex` at `0x101799081`
- `sqldk!SystemThread_TlsIndex` at `0x1017990cc`
- `sqldk!SystemThread_TlsIndex` at `0x10179927f`
- `sqldk!SystemThread_TlsIndex` at `0x1017992ca`
- `sqldk!SystemThread_TlsIndex` at `0x10179933b`
- `sqldk!SystemThread_TlsIndex` at `0x101799386`
- `sqldk!SystemThread_TlsIndex` at `0x101799430`
- `sqldk!SystemThread_TlsIndex` at `0x10179947b`
- `sqldk!SystemThread_TlsIndex` at `0x101799576`
- `sqldk!SystemThread_TlsIndex` at `0x1017995c1`
- `sqldk!SystemThread_TlsIndex` at `0x1017996b1`
- `sqldk!SystemThread_TlsIndex` at `0x1017996fc`
- `sqldk!SystemThread_TlsIndex` at `0x101799778`
- `sqldk!SystemThread_TlsIndex` at `0x1017997c3`
- `sqldk!SystemThread_TlsIndex` at `0x1017998a3`
- `sqldk!SystemThread_TlsIndex` at `0x1017998ee`
- `sqldk!SystemThread_TlsOffset` at `0x1017989c6`
- `sqldk!SystemThread_TlsOffset` at `0x101798a1a`
- `sqldk!SystemThread_TlsOffset` at `0x101798bbd`
- `sqldk!SystemThread_TlsOffset` at `0x101798c08`
- `sqldk!SystemThread_TlsOffset` at `0x101798c9b`
- `sqldk!SystemThread_TlsOffset` at `0x101798ce7`
- `sqldk!SystemThread_TlsOffset` at `0x101798e47`
- `sqldk!SystemThread_TlsOffset` at `0x101798e92`
- `sqldk!SystemThread_TlsOffset` at `0x10179908a`
- `sqldk!SystemThread_TlsOffset` at `0x1017990d5`
- `sqldk!SystemThread_TlsOffset` at `0x101799288`
- `sqldk!SystemThread_TlsOffset` at `0x1017992d3`
- `sqldk!SystemThread_TlsOffset` at `0x101799344`
- `sqldk!SystemThread_TlsOffset` at `0x10179938f`
- `sqldk!SystemThread_TlsOffset` at `0x101799439`
- `sqldk!SystemThread_TlsOffset` at `0x101799484`
- `sqldk!SystemThread_TlsOffset` at `0x10179957f`
- `sqldk!SystemThread_TlsOffset` at `0x1017995ca`
- `sqldk!SystemThread_TlsOffset` at `0x1017996ba`
- `sqldk!SystemThread_TlsOffset` at `0x101799705`
- `sqldk!SystemThread_TlsOffset` at `0x101799781`
- `sqldk!SystemThread_TlsOffset` at `0x1017997cc`
- `sqldk!SystemThread_TlsOffset` at `0x1017998ac`
- `sqldk!SystemThread_TlsOffset` at `0x1017998f7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017989df`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101798a35`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1017989df`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101798a35`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x101799008`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x101799008`

## string_xrefs

- `0x101799931`: `FCB::GetActualSectorSize: Failed on CreateFile: Error (%d) on volume %ls`
- `0x101798ecf`: `FCB::GetActualSectorSize: Failed on GetVolumeNameForVolumeMountPoint: Error (%d) on mountPoint %ls.`
- `0x101798d25`: `FCB::GetActualSectorSize: Failed on GetVolumePathName:             Error (%d) on file %ls.`
- `0x1017993c5`: `FCB::GetActualSectorSize with AlignmentDescriptor: GetPhysicalSectorSize failed with error = %d!`
- `0x10179930e`: `Using FileSystemEffectivePhysicalBytesPerSectorForAtomicity of %d on volume %ls, instead of alignmentDescriptor.BytesPerPhysicalSector of %d`
- `0x101799024`: `[FileSysMgr::DBCreateFileW]: File handle %d is opened for file path %ls. Error_no: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall FCB::GetActualSectorSize(
        LPCWSTR lpszVolumeMountPoint,
        void *a2,
        LPDWORD lpBytesPerSector,
        unsigned int *a4)
{
  __int64 v8; // r14
  __int64 v9; // rbx
  CDefaultCollation *v10; // rax
  __int64 v11; // rdx
  WCHAR *v12; // rcx
  WCHAR v13; // ax
  WCHAR *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdx
  unsigned int RawActualSectorSize; // ebx
  int PhysicalSectorSize; // ebx
  DWORD LastError; // eax
  __int64 v24; // rdx
  struct CSessionTraceFlags *v25; // rcx
  __int64 v26; // rax
  struct CSessionTraceFlags *v27; // rcx
  BOOL VolumePathNameW; // ebx
  DWORD v29; // eax
  __int64 v30; // r8
  struct CSessionTraceFlags *v31; // rcx
  __int64 v32; // rax
  struct CSessionTraceFlags *v33; // rcx
  BOOL VolumeNameForVolumeMountPointW; // ebx
  DWORD v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rdx
  struct CSessionTraceFlags *v38; // rcx
  __int64 v39; // rdx
  struct CSessionTraceFlags *v40; // rcx
  __int64 v41; // r9
  WCHAR *v42; // rax
  unsigned __int64 v43; // r15
  struct IFileSystemHandler *v44; // rax
  void *v45; // r15
  __int64 v46; // rbx
  DWORD v47; // eax
  DWORD FileType; // ebx
  __int64 v49; // rax
  struct CSessionTraceFlags *v50; // rcx
  __int64 v51; // rax
  struct CSessionTraceFlags *v52; // rcx
  __int64 v53; // r8
  int v54; // ebx
  DWORD v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rax
  struct CSessionTraceFlags *v58; // rcx
  __int64 v59; // rdx
  struct CSessionTraceFlags *v60; // rcx
  __int64 v61; // rdx
  struct CSessionTraceFlags *v62; // rcx
  __int64 v63; // rdx
  struct CSessionTraceFlags *v64; // rcx
  __int64 v65; // rdx
  struct CSessionTraceFlags *v66; // rcx
  __int64 v67; // rdx
  struct CSessionTraceFlags *v68; // rcx
  unsigned int v69; // ebx
  unsigned int v70; // ebx
  __int64 v71; // rax
  struct CSessionTraceFlags *v72; // rcx
  __int64 v73; // rdx
  struct CSessionTraceFlags *v74; // rcx
  __int64 v75; // rdx
  __int64 v76; // rax
  struct CSessionTraceFlags *v77; // rcx
  __int64 v78; // rdx
  struct CSessionTraceFlags *v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // rax
  struct CSessionTraceFlags *v82; // rcx
  __int64 v83; // rdx
  struct CSessionTraceFlags *v84; // rcx
  __int64 v85; // rdx
  struct CSessionTraceFlags *v86; // rcx
  __int64 v87; // rdx
  struct CSessionTraceFlags *v88; // rcx
  unsigned int *v89; // [rsp+28h] [rbp-D8h]
  unsigned int *v90; // [rsp+30h] [rbp-D0h]
  DWORD v91; // [rsp+50h] [rbp-B0h]
  DWORD v92; // [rsp+50h] [rbp-B0h]
  DWORD v93; // [rsp+50h] [rbp-B0h]
  unsigned int v94; // [rsp+50h] [rbp-B0h]
  DWORD v95; // [rsp+50h] [rbp-B0h]
  unsigned int v96[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v97; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v98; // [rsp+64h] [rbp-9Ch]
  DWORD v99; // [rsp+68h] [rbp-98h]
  unsigned int v100; // [rsp+6Ch] [rbp-94h] BYREF
  int v101; // [rsp+70h] [rbp-90h] BYREF
  __int64 v102; // [rsp+78h] [rbp-88h]
  int v103; // [rsp+80h] [rbp-80h] BYREF
  int v104; // [rsp+84h] [rbp-7Ch]
  __int64 v105; // [rsp+88h] [rbp-78h]
  int v106; // [rsp+90h] [rbp-70h] BYREF
  __int64 v107; // [rsp+98h] [rbp-68h]
  __int64 v108; // [rsp+A0h] [rbp-60h]
  __int64 v109; // [rsp+A8h] [rbp-58h]
  __int64 v110; // [rsp+B0h] [rbp-50h]
  bool v111; // [rsp+C0h] [rbp-40h]
  DWORD v112; // [rsp+D0h] [rbp-30h]
  __int64 v113; // [rsp+D8h] [rbp-28h]
  __int128 v114; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v115; // [rsp+F0h] [rbp-10h]
  int v116; // [rsp+F8h] [rbp-8h]
  int v117; // [rsp+100h] [rbp+0h] BYREF
  __int64 v118; // [rsp+104h] [rbp+4h]
  _BYTE v119[20]; // [rsp+110h] [rbp+10h] BYREF
  DWORD v120; // [rsp+124h] [rbp+24h]
  WCHAR szVolumeName[264]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR szFileName[264]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+550h] [rbp+450h] BYREF
  wchar_t v124[264]; // [rsp+760h] [rbp+660h] BYREF

  v113 = -2;
  v97 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( lpszVolumeMountPoint[v9] );
  v10 = (CDefaultCollation *)CDefaultCollation::PDCServer();
  if ( CDefaultCollation::FEqIgnoreCaseW(v10, L"NUL", 6u, lpszVolumeMountPoint, 2 * v9) )
    goto LABEL_239;
  v11 = 261;
  v12 = szFileName;
  do
  {
    if ( v11 == -2147483385 )
      break;
    v13 = *(WCHAR *)((char *)v12 + (char *)lpszVolumeMountPoint - (char *)szFileName);
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
  if ( !v11 )
  {
    _mm_lfence();
    ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dfs\\manager\\fcb.cpp", 14380, -2147024774);
  }
  if ( (byte_10317AC61 & 1) != 0 )
  {
LABEL_239:
    *lpBytesPerSector = 4096;
    return 1;
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v101, 1);
  *(_QWORD *)v96 = &v103;
  v106 = 536871473;
  v107 = 0;
  v109 = 0;
  v108 = 0;
  v110 = 0;
  v111 = 0;
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v17 = *(_QWORD *)(v16 + 600);
  if ( v17 )
    v111 = (unsigned int)SOS_Task::PushWait(v17, &v106) == 0;
  v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v19 = *(_QWORD *)(v18 + 256);
  if ( !v19 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v19 = *(_QWORD *)(v18 + 256);
  }
  v105 = v19;
  v104 = (*(_DWORD *)(v19 + 800) >> 11) & 1;
  if ( v104 || (*(_BYTE *)(v19 + 800) & 4) == 0 )
  {
    v103 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 608) + 8LL))(*(_QWORD *)(v19 + 608));
  }
  else
  {
    v103 = 0;
  }
  if ( (unsigned int)ChkRawNameWithConvert(lpszVolumeMountPoint, v124) )
  {
    RawActualSectorSize = FCB::GetRawActualSectorSize(v124, a2, lpBytesPerSector, a4);
    *(_QWORD *)v96 = &v103;
    if ( v103 )
    {
      if ( v104 )
        *(_DWORD *)(v105 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
          *(_QWORD *)(v105 + 608),
          v105,
          1);
    }
LABEL_30:
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
    *(_DWORD *)(v102 + 616) &= ~v101;
    return RawActualSectorSize;
  }
  if ( !OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
    goto LABEL_49;
  v112 = 0;
  PhysicalSectorSize = GetPhysicalSectorSize(szFileName);
  LastError = GetLastError();
  v91 = LastError;
  if ( !PhysicalSectorSize )
  {
    if ( (byte_10317AC62 & 4) != 0 )
    {
LABEL_48:
      traceprint(L"FCB::GetActualSectorSize: GetPhysicalSectorSize failed with error = %d!", LastError);
      goto LABEL_49;
    }
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( *(_QWORD *)v24
      && (v25 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v24 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v25, 0x712u)
      || (byte_10317AC64 & 1) != 0
      || (v26 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset)) != 0
      && (v27 = **(struct CSessionTraceFlags ***)(v26 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v27, 0x720u) )
    {
      LastError = v91;
      goto LABEL_48;
    }
LABEL_49:
    VolumePathNameW = GetVolumePathNameW(szFileName, szVolumePathName, 0x105u);
    v29 = GetLastError();
    v92 = v29;
    if ( !VolumePathNameW )
    {
      if ( a4 )
        *a4 = v29;
      if ( (byte_10317AC62 & 4) == 0 )
      {
        v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( (!*(_QWORD *)v30
           || (v31 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v30 + 56LL)) == 0
           || !CSessionTraceFlags::CheckSessionTraceInternal(v31, 0x712u))
          && (byte_10317AC64 & 1) == 0 )
        {
          v32 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset);
          if ( !v32
            || (v33 = **(struct CSessionTraceFlags ***)(v32 + 56)) == 0
            || !CSessionTraceFlags::CheckSessionTraceInternal(v33, 0x720u) )
          {
LABEL_62:
            RawActualSectorSize = GetNonVolumeSectorSize(szFileName, lpBytesPerSector);
            *(_QWORD *)v96 = &v103;
            if ( v103 )
            {
              if ( v104 )
                *(_DWORD *)(v105 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                  *(_QWORD *)(v105 + 608),
                  v105,
                  1);
            }
            goto LABEL_30;
          }
        }
        v29 = v92;
      }
      traceprint(
        L"FCB::GetActualSectorSize: Failed on GetVolumePathName:             Error (%d) on file %ls.",
        v29,
        szFileName);
      goto LABEL_62;
    }
    if ( (unsigned int)FileMgr::IsFilePathOnNetworkShare(szVolumePathName) )
    {
      RawActualSectorSize = GetNonVolumeSectorSize(szFileName, lpBytesPerSector);
      *(_QWORD *)v96 = &v103;
      if ( v103 )
      {
        if ( v104 )
          *(_DWORD *)(v105 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
            *(_QWORD *)(v105 + 608),
            v105,
            1);
      }
      goto LABEL_30;
    }
    VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x105u);
    v35 = GetLastError();
    v93 = v35;
    if ( !VolumeNameForVolumeMountPointW )
    {
      if ( a4 )
        *a4 = v35;
      if ( (byte_10317AC62 & 4) == 0 )
      {
        v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( (!*(_QWORD *)v37
           || (v38 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v37 + 56LL)) == 0
           || !CSessionTraceFlags::CheckSessionTraceInternal(v38, 0x712u))
          && (byte_10317AC64 & 1) == 0 )
        {
          v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( !*(_QWORD *)v39
            || (v40 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v39 + 56LL)) == 0
            || !CSessionTraceFlags::CheckSessionTraceInternal(v40, 0x720u) )
          {
LABEL_86:
            *lpBytesPerSector = 4096;
            *(_QWORD *)v96 = &v103;
            if ( v103 )
            {
              if ( v104 )
                *(_DWORD *)(v105 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                  *(_QWORD *)(v105 + 608),
                  v105,
                  1);
            }
LABEL_90:
            SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
LABEL_91:
            *(_DWORD *)(v102 + 616) &= ~v101;
            return 0;
          }
        }
        v35 = v93;
      }
      traceprint(
        L"FCB::GetActualSectorSize: Failed on GetVolumeNameForVolumeMountPoint: Error (%d) on mountPoint %ls.",
        v35,
        szVolumePathName);
      goto LABEL_86;
    }
    v41 = 261;
    v42 = szVolumeName;
    do
    {
      if ( !*v42 )
        break;
      ++v42;
      --v41;
    }
    while ( v41 );
    if ( v41 )
    {
      v43 = 2 * (261 - v41) - 2;
      if ( v43 < 0x20A )
      {
        *(WCHAR *)((char *)szVolumeName + v43) = 0;
        v44 = DBGetHandlerForPath(szVolumeName, 0);
        if ( v44 )
        {
          v45 = (void *)(*(__int64 (__fastcall **)(struct IFileSystemHandler *, WCHAR *, __int64))(*(_QWORD *)v44 + 40LL))(
                          v44,
                          szVolumeName,
                          128);
          if ( (unsigned int)FileMgr::IsFilePathOnNetworkShare(szVolumeName) )
          {
            do
              ++v8;
            while ( *(&RootPathName + v8) );
            if ( (unsigned int)v8 > 8 && !wcsncmp(&RootPathName, szVolumeName, (unsigned int)v8) )
            {
              v46 = GetLastError();
              LogSystemMetadata(
                L"[FileSysMgr::DBCreateFileW]: File handle %d is opened for file path %ls. Error_no: %d",
                v45,
                szVolumeName,
                v46);
              SetLastError(v46);
            }
          }
          v47 = GetLastError();
          v94 = v47;
          if ( v45 != (void *)-1LL )
          {
            FileType = GetFileType(v45);
            if ( FileType != 1 )
            {
              if ( a4 )
                *a4 = -2147467259;
              if ( (byte_10317AC62 & 4) != 0
                || (v49 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset)) != 0
                && (v50 = **(struct CSessionTraceFlags ***)(v49 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v50, 0x712u)
                || (byte_10317AC64 & 1) != 0
                || (v51 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset)) != 0
                && (v52 = **(struct CSessionTraceFlags ***)(v51 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v52, 0x720u) )
              {
                traceprint(
                  L"FCB::GetActualSectorSize: Failed on FILE_TYPE_DISK: on file %ls, type = %d.",
                  szVolumePathName,
                  FileType);
              }
              CloseHandle(v45);
              *lpBytesPerSector = 4096;
              *(_QWORD *)v96 = &v103;
              if ( v103 )
              {
                if ( v104 )
                  *(_DWORD *)(v105 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                    *(_QWORD *)(v105 + 608),
                    v105,
                    1);
              }
              goto LABEL_90;
            }
            v100 = 28;
            v114 = 0;
            v115 = 0;
            v116 = 0;
            v118 = 0;
            v117 = 6;
            if ( (unsigned int)DoDevIoCtlOut(v45, 0x2D1400u, &v117, 0xCu, &v114, &v100, &v97) )
            {
              if ( a4 )
                *a4 = v97;
              v53 = v100;
              if ( DWORD1(v114) >= 0x18 && (unsigned int)v114 >= 0x1C && HIDWORD(v115) && v100 >= 0x18 )
              {
                *lpBytesPerSector = HIDWORD(v115);
                CloseHandle(v45);
                if ( (qword_10317ABEC & 0x40000) != 0 )
                {
                  v98 = 0;
                  v54 = GetPhysicalSectorSize(szFileName);
                  v55 = GetLastError();
                  v95 = v55;
                  if ( v54 )
                  {
                    v56 = v98;
                    if ( !v98 || *lpBytesPerSector <= v98 )
                      goto LABEL_153;
                    if ( (byte_10317AC62 & 4) == 0 )
                    {
                      v57 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset);
                      if ( (!v57
                         || (v58 = **(struct CSessionTraceFlags ***)(v57 + 56)) == 0
                         || !CSessionTraceFlags::CheckSessionTraceInternal(v58, 0x712u))
                        && (byte_10317AC64 & 1) == 0 )
                      {
                        v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset;
                        if ( !*(_QWORD *)v59 )
                          goto LABEL_142;
                        v60 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v59 + 56LL);
                        if ( !v60 || !CSessionTraceFlags::CheckSessionTraceInternal(v60, 0x720u) )
                          goto LABEL_142;
                      }
                      v56 = v98;
                    }
                    traceprint(
                      L"Using FileSystemEffectivePhysicalBytesPerSectorForAtomicity of %d on volume %ls, instead of alignm"
                       "entDescriptor.BytesPerPhysicalSector of %d",
                      v56,
                      szVolumeName,
                      *lpBytesPerSector);
LABEL_142:
                    *lpBytesPerSector = v98;
                    goto LABEL_153;
                  }
                  if ( (byte_10317AC62 & 4) == 0 )
                  {
                    v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    if ( (!*(_QWORD *)v61
                       || (v62 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v61 + 56LL)) == 0
                       || !CSessionTraceFlags::CheckSessionTraceInternal(v62, 0x712u))
                      && (byte_10317AC64 & 1) == 0 )
                    {
                      v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset;
                      if ( !*(_QWORD *)v63 )
                        goto LABEL_153;
                      v64 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v63 + 56LL);
                      if ( !v64 || !CSessionTraceFlags::CheckSessionTraceInternal(v64, 0x720u) )
                        goto LABEL_153;
                    }
                    v55 = v95;
                  }
                  traceprint(
                    L"FCB::GetActualSectorSize with AlignmentDescriptor: GetPhysicalSectorSize failed with error = %d!",
                    v55);
                }
LABEL_153:
                *(_QWORD *)v96 = &v103;
                if ( v103 )
                {
                  if ( v104 )
                    *(_DWORD *)(v105 + 800) |= 0x800u;
                  else
                    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                      *(_QWORD *)(v105 + 608),
                      v105,
                      1);
                }
                SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
                goto LABEL_38;
              }
              if ( (byte_10317AC62 & 4) != 0 )
                goto LABEL_167;
              v65 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              if ( *(_QWORD *)v65
                && (v66 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v65 + 56LL)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v66, 0x712u)
                || (byte_10317AC64 & 1) != 0
                || (v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset,
                    *(_QWORD *)v67)
                && (v68 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v67 + 56LL)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v68, 0x720u) )
              {
                v53 = v100;
LABEL_167:
                traceprint(
                  L"FCB::GetActualSectorSize: IOCTL_STORAGE_QUERY_PROPERTY succeeded on volume %ls but values did not vali"
                   "date. Returned Bytes %d, Size %ld, Version %ld, SectorBytes %d.",
                  szVolumeName,
                  v53);
              }
            }
            v96[0] = 24;
            if ( !(unsigned int)DoDevIoCtlOut(v45, 0x70000u, 0, 0, v119, v96, &v97) )
              goto LABEL_172;
            v69 = v96[0];
            if ( v96[0] != 24 )
            {
              if ( !IsKnownNoise(0x70000u) )
                log_unlocalized_systemmetadata(
                  L"DeviceIoControl: bytes returned incorrect: got %d, expected %d\n",
                  v69,
                  24);
LABEL_172:
              v70 = v97;
              if ( a4 )
                *a4 = v97;
              *lpBytesPerSector = 4096;
              CloseHandle(v45);
              if ( (byte_10317AC62 & 4) == 0 )
              {
                v71 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset);
                if ( (!v71
                   || (v72 = **(struct CSessionTraceFlags ***)(v71 + 56)) == 0
                   || !CSessionTraceFlags::CheckSessionTraceInternal(v72, 0x712u))
                  && (byte_10317AC64 & 1) == 0 )
                {
                  v73 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  if ( !*(_QWORD *)v73 )
                    goto LABEL_184;
                  v74 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v73 + 56LL);
                  if ( !v74 || !CSessionTraceFlags::CheckSessionTraceInternal(v74, 0x720u) )
                    goto LABEL_184;
                }
                v70 = v97;
              }
              traceprint(
                L"FCB::GetActualSectorSize: IOCTL_DISK_GET_DRIVE_GEOMETRY failed on volume %ls with error = %d",
                szVolumeName,
                v70);
LABEL_184:
              *(_QWORD *)v96 = &v103;
              if ( v103 )
              {
                if ( v104 )
                  *(_DWORD *)(v105 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                    *(_QWORD *)(v105 + 608),
                    v105,
                    1);
              }
              SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
              goto LABEL_91;
            }
            *lpBytesPerSector = v120;
            CloseHandle(v45);
            if ( (qword_10317ABEC & 0x40000) != 0 )
            {
              v99 = 0;
              if ( (unsigned int)GetPhysicalSectorSize(szFileName) )
              {
                v75 = v99;
                if ( !v99 || *lpBytesPerSector <= v99 )
                  goto LABEL_214;
                if ( (byte_10317AC62 & 4) == 0 )
                {
                  v76 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset);
                  if ( (!v76
                     || (v77 = **(struct CSessionTraceFlags ***)(v76 + 56)) == 0
                     || !CSessionTraceFlags::CheckSessionTraceInternal(v77, 0x712u))
                    && (byte_10317AC64 & 1) == 0 )
                  {
                    v78 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    if ( !*(_QWORD *)v78 )
                      goto LABEL_201;
                    v79 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v78 + 56LL);
                    if ( !v79 || !CSessionTraceFlags::CheckSessionTraceInternal(v79, 0x720u) )
                      goto LABEL_201;
                  }
                  v75 = v99;
                }
                traceprint(
                  L"Using FileSystemEffectivePhysicalBytesPerSectorForAtomicity of %d on volume %ls, instead of volumeGeom"
                   "etry.BytesPerSector of %d",
                  v75,
                  szVolumeName,
                  *lpBytesPerSector);
LABEL_201:
                *lpBytesPerSector = v99;
                goto LABEL_214;
              }
              v80 = v94;
              if ( a4 )
                *a4 = v94;
              if ( (byte_10317AC62 & 4) == 0 )
              {
                v81 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset);
                if ( (!v81
                   || (v82 = **(struct CSessionTraceFlags ***)(v81 + 56)) == 0
                   || !CSessionTraceFlags::CheckSessionTraceInternal(v82, 0x712u))
                  && (byte_10317AC64 & 1) == 0 )
                {
                  v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  if ( !*(_QWORD *)v83 )
                    goto LABEL_214;
                  v84 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v83 + 56LL);
                  if ( !v84 || !CSessionTraceFlags::CheckSessionTraceInternal(v84, 0x720u) )
                    goto LABEL_214;
                }
                v80 = v94;
              }
              traceprint(
                L"FCB::GetActualSectorSize with VolumeGeometry: GetPhysicalSectorSize failed with error = %d!",
                v80);
            }
LABEL_214:
            *(_QWORD *)v96 = &v103;
            if ( v103 )
            {
              if ( v104 )
                *(_DWORD *)(v105 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                  *(_QWORD *)(v105 + 608),
                  v105,
                  1);
            }
            SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
            goto LABEL_38;
          }
        }
        else
        {
          SetLastError(0x32u);
          v47 = GetLastError();
          v94 = v47;
        }
        if ( a4 )
          *a4 = v47;
        if ( (byte_10317AC62 & 4) == 0 )
        {
          v85 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( (!*(_QWORD *)v85
             || (v86 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v85 + 56LL)) == 0
             || !CSessionTraceFlags::CheckSessionTraceInternal(v86, 0x712u))
            && (byte_10317AC64 & 1) == 0 )
          {
            v87 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( !*(_QWORD *)v87
              || (v88 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v87 + 56LL)) == 0
              || !CSessionTraceFlags::CheckSessionTraceInternal(v88, 0x720u) )
            {
LABEL_234:
              *lpBytesPerSector = 4096;
              *(_QWORD *)v96 = &v103;
              if ( v103 )
              {
                if ( v104 )
                  *(_DWORD *)(v105 + 800) |= 0x800u;
                else
                  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
                    *(_QWORD *)(v105 + 608),
                    v105,
                    1);
              }
              goto LABEL_90;
            }
          }
          v47 = v94;
        }
        traceprint(L"FCB::GetActualSectorSize: Failed on CreateFile: Error (%d) on volume %ls", v47, szVolumeName);
        goto LABEL_234;
      }
    }
    else
    {
      _mm_lfence();
      LODWORD(v90) = -2147024809;
      LODWORD(v89) = 14504;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\storeng\\dfs\\manager\\fcb.cpp", v89, v90);
    }
    _report_rangecheckfailure(v36);
  }
  *lpBytesPerSector = v112;
  *(_QWORD *)v96 = &v103;
  if ( v103 )
  {
    if ( v104 )
      *(_DWORD *)(v105 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
        *(_QWORD *)(v105 + 608),
        v105,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
LABEL_38:
  *(_DWORD *)(v102 + 616) &= ~v101;
  return 1;
}

```

## disassembly

```asm
0x101798850  push    rbp
0x101798852  push    rbx
0x101798853  push    rsi
0x101798854  push    rdi
0x101798855  push    r12
0x101798857  push    r13
0x101798859  push    r14
0x10179885b  push    r15
0x10179885d  lea     rbp, [rsp-888h]
0x101798865  sub     rsp, 988h
0x10179886c  mov     [rbp+8C0h+var_8E8], 0FFFFFFFFFFFFFFFEh
0x101798874  mov     rax, cs:__security_cookie
0x10179887b  xor     rax, rsp
0x10179887e  mov     [rbp+8C0h+var_50], rax
0x101798885  mov     rdi, r9
0x101798888  mov     rsi, r8
0x10179888b  mov     r13, rdx
0x10179888e  mov     r12, rcx
0x101798891  xor     eax, eax
0x101798893  mov     [rsp+9C0h+var_960], eax
0x101798897  test    r9, r9
0x10179889a  jz      short loc_10179889F
0x10179889c  mov     [r9], eax
0x10179889f  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1017988a6  mov     rbx, r14
0x1017988a9  nop     dword ptr [rax+00000000h]
0x1017988b0  inc     rbx
0x1017988b3  cmp     [rcx+rbx*2], ax
0x1017988b7  jnz     short loc_1017988B0
0x1017988b9  add     rbx, rbx
0x1017988bc  call    cs:__imp_?PDCServer@CDefaultCollation@@SAPEAV1@XZ; CDefaultCollation::PDCServer(void)
0x1017988c2  mov     rcx, rax
0x1017988c5  mov     dword ptr [rsp+9C0h+var_9A0], ebx
0x1017988c9  mov     r9, r12
0x1017988cc  mov     r8d, 6
0x1017988d2  lea     rdx, aNul; "NUL"
0x1017988d9  call    cs:__imp_?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z; CDefaultCollation::FEqIgnoreCaseW(wchar_t const *,ulong,wchar_t const *,ulong)
0x1017988df  test    al, al
0x1017988e1  jnz     loc_10179998B
0x1017988e7  mov     r15d, 105h
0x1017988ed  mov     edx, r15d
0x1017988f0  lea     rcx, [rbp+8C0h+szFileName]
0x1017988f7  lea     rax, [rbp+8C0h+szFileName]
0x1017988fe  mov     r8, r12
0x101798901  sub     r8, rax
0x101798904  lea     rax, [rdx+7FFFFEF9h]
0x10179890b  test    rax, rax
0x10179890e  jz      short loc_101798927
0x101798910  movzx   eax, word ptr [r8+rcx]
0x101798915  test    ax, ax
0x101798918  jz      short loc_101798927
0x10179891a  mov     [rcx], ax
0x10179891d  add     rcx, 2
0x101798921  sub     rdx, 1
0x101798925  jnz     short loc_101798904
0x101798927  lea     rax, [rcx-2]
0x10179892b  test    rdx, rdx
0x10179892e  cmovnz  rax, rcx
0x101798932  xor     ebx, ebx
0x101798934  mov     [rax], bx
0x101798937  mov     eax, 8007007Ah
0x10179893c  test    rdx, rdx
0x10179893f  cmovnz  eax, ebx
0x101798942  lea     rcx, aSqlNtdbmsStore_133; "sql\\ntdbms\\storeng\\dfs\\manager\\fcb"...
0x101798949  jnz     short loc_101798973
0x10179894b  lfence
0x10179894e  mov     dword ptr [rsp+9C0h+var_990], eax
0x101798952  mov     dword ptr [rsp+9C0h+var_998], 382Ch
0x10179895a  mov     [rsp+9C0h+var_9A0], rcx
0x10179895f  lea     edx, [rbx+7]
0x101798962  lea     ecx, [rbx+4]
0x101798965  lea     r9d, [rbx+1]
0x101798969  lea     r8d, [rbx+10h]
0x10179896d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101798973  test    cs:byte_10317AC61, 1
0x10179897a  jnz     loc_10179998B
0x101798980  mov     edx, 1
0x101798985  lea     rcx, [rsp+9C0h+var_950]
0x10179898a  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10179898f  nop
0x101798990  lea     rax, [rbp+8C0h+var_940]
0x101798994  mov     qword ptr [rsp+9C0h+var_968], rax
0x101798999  mov     [rbp+8C0h+var_930], 20000231h
0x1017989a0  mov     [rbp+8C0h+var_928], rbx
0x1017989a4  mov     [rbp+8C0h+var_918], rbx
0x1017989a8  mov     [rbp+8C0h+var_920], rbx
0x1017989ac  mov     [rbp+8C0h+var_910], rbx
0x1017989b0  mov     [rbp+8C0h+var_900], 0
0x1017989b4  mov     rdx, gs:58h
0x1017989bd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1017989c4  mov     ecx, [rax]
0x1017989c6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1017989cd  mov     ebx, [rax]
0x1017989cf  add     rbx, [rdx+rcx*8]
0x1017989d3  mov     rcx, [rbx+100h]
0x1017989da  test    rcx, rcx
0x1017989dd  jnz     short loc_1017989EC
0x1017989df  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1017989e5  mov     rcx, [rbx+100h]
0x1017989ec  mov     rcx, [rcx+258h]
0x1017989f3  test    rcx, rcx
0x1017989f6  jz      short loc_101798A08
0x1017989f8  lea     rdx, [rbp+8C0h+var_930]
0x1017989fc  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x101798a02  test    eax, eax
0x101798a04  setz    [rbp+8C0h+var_900]
0x101798a08  mov     rdx, gs:58h
0x101798a11  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101798a18  mov     ecx, [rax]
0x101798a1a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101798a21  mov     ebx, [rax]
0x101798a23  add     rbx, [rdx+rcx*8]
0x101798a27  mov     rdx, [rbx+100h]
0x101798a2e  test    rdx, rdx
0x101798a31  jnz     short loc_101798A42
0x101798a33  xor     ecx, ecx
0x101798a35  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101798a3b  mov     rdx, [rbx+100h]
0x101798a42  mov     [rbp+8C0h+var_938], rdx
0x101798a46  mov     eax, [rdx+320h]
0x101798a4c  shr     eax, 0Bh
0x101798a4f  and     eax, 1
0x101798a52  mov     [rbp+8C0h+var_93C], eax
0x101798a55  jnz     short loc_101798A67
0x101798a57  test    byte ptr [rdx+320h], 4
0x101798a5e  jz      short loc_101798A67
0x101798a60  xor     eax, eax
0x101798a62  mov     [rbp+8C0h+var_940], eax
0x101798a65  jmp     short loc_101798A7C
0x101798a67  mov     [rbp+8C0h+var_940], 1
0x101798a6e  mov     rcx, [rdx+260h]
0x101798a75  mov     rax, [rcx]
0x101798a78  call    qword ptr [rax+8]
0x101798a7b  nop
0x101798a7c  lea     rdx, [rbp+8C0h+var_260]; wchar_t *
0x101798a83  mov     rcx, r12; lpszVolumeMountPoint
0x101798a86  call    ?ChkRawNameWithConvert@@YAHPEB_WPEA_W@Z; ChkRawNameWithConvert(wchar_t const *,wchar_t *)
0x101798a8b  test    eax, eax
0x101798a8d  jz      short loc_101798B01
0x101798a8f  mov     r9, rdi; unsigned int *
0x101798a92  mov     r8, rsi; unsigned int *
0x101798a95  mov     rdx, r13; void *
0x101798a98  lea     rcx, [rbp+8C0h+var_260]; wchar_t *
0x101798a9f  call    ?GetRawActualSectorSize@FCB@@CAHPEB_WPEAXAEAKPEAK@Z; FCB::GetRawActualSectorSize(wchar_t const *,void *,ulong &,ulong *)
0x101798aa4  mov     ebx, eax
0x101798aa6  lea     rax, [rbp+8C0h+var_940]
0x101798aaa  mov     qword ptr [rsp+9C0h+var_968], rax
0x101798aaf  cmp     [rbp+8C0h+var_940], 0
0x101798ab3  jz      short loc_101798ADF
0x101798ab5  mov     rdx, [rbp+8C0h+var_938]
0x101798ab9  mov     rcx, [rdx+260h]
0x101798ac0  cmp     [rbp+8C0h+var_93C], 0
0x101798ac4  jz      short loc_101798AD2
0x101798ac6  or      dword ptr [rdx+320h], 800h
0x101798ad0  jmp     short loc_101798ADF
0x101798ad2  mov     rax, [rcx]
0x101798ad5  mov     r8d, 1
0x101798adb  call    qword ptr [rax+10h]
0x101798ade  nop
0x101798adf  lea     rcx, [rbp+8C0h+var_930]; this
0x101798ae3  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x101798ae8  nop
0x101798ae9  mov     rcx, [rsp+9C0h+var_948]
0x101798aee  mov     eax, [rsp+9C0h+var_950]
0x101798af2  not     eax
0x101798af4  and     [rcx+268h], eax
0x101798afa  mov     eax, ebx
0x101798afc  jmp     loc_101799996
0x101798b01  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x101798b08  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x101798b0e  xor     r12d, r12d
0x101798b11  test    al, al
0x101798b13  jz      loc_101798C4A
0x101798b19  mov     [rbp+8C0h+var_8F0], r12d
0x101798b1d  mov     r8, rdi
0x101798b20  lea     rdx, [rbp+8C0h+var_8F0]
0x101798b24  lea     rcx, [rbp+8C0h+szFileName]; FullPath
0x101798b2b  call    GetPhysicalSectorSize
0x101798b30  mov     ebx, eax
0x101798b32  call    cs:__imp_GetLastError
0x101798b38  mov     [rsp+9C0h+var_970], eax
0x101798b3c  test    ebx, ebx
0x101798b3e  jz      short loc_101798B9E
0x101798b40  mov     eax, [rbp+8C0h+var_8F0]
0x101798b43  mov     [rsi], eax
0x101798b45  lea     rax, [rbp+8C0h+var_940]
0x101798b49  mov     qword ptr [rsp+9C0h+var_968], rax
0x101798b4e  cmp     [rbp+8C0h+var_940], r12d
0x101798b52  jz      short loc_101798B7E
0x101798b54  mov     rdx, [rbp+8C0h+var_938]
0x101798b58  mov     rcx, [rdx+260h]
0x101798b5f  cmp     [rbp+8C0h+var_93C], r12d
0x101798b63  jz      short loc_101798B71
0x101798b65  or      dword ptr [rdx+320h], 800h
0x101798b6f  jmp     short loc_101798B7E
0x101798b71  mov     rax, [rcx]
0x101798b74  mov     r8d, 1
0x101798b7a  call    qword ptr [rax+10h]
0x101798b7d  nop
0x101798b7e  lea     rcx, [rbp+8C0h+var_930]; this
0x101798b82  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x101798b87  nop
0x101798b88  mov     rcx, [rsp+9C0h+var_948]
0x101798b8d  mov     eax, [rsp+9C0h+var_950]
0x101798b91  not     eax
0x101798b93  and     [rcx+268h], eax
0x101798b99  jmp     loc_101799991
0x101798b9e  test    cs:byte_10317AC62, 4
0x101798ba5  jnz     loc_101798C3C
0x101798bab  mov     r8, gs:58h
0x101798bb4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101798bbb  mov     ecx, [rax]
0x101798bbd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101798bc4  mov     edx, [rax]
0x101798bc6  add     rdx, [r8+rcx*8]
0x101798bca  mov     rax, [rdx]
0x101798bcd  test    rax, rax
0x101798bd0  jz      short loc_101798BED
0x101798bd2  mov     rax, [rax+38h]
0x101798bd6  mov     rcx, [rax]
0x101798bd9  test    rcx, rcx
0x101798bdc  jz      short loc_101798BED
0x101798bde  mov     edx, 712h
0x101798be3  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101798be9  test    eax, eax
0x101798beb  jnz     short loc_101798C38
0x101798bed  test    cs:byte_10317AC64, 1
0x101798bf4  jnz     short loc_101798C38
0x101798bf6  mov     r8, gs:58h
0x101798bff  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101798c06  mov     ecx, [rax]
0x101798c08  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101798c0f  mov     edx, [rax]
0x101798c11  add     rdx, [r8+rcx*8]
0x101798c15  mov     rax, [rdx]
0x101798c18  test    rax, rax
0x101798c1b  jz      short loc_101798C4A
0x101798c1d  mov     rax, [rax+38h]
0x101798c21  mov     rcx, [rax]
0x101798c24  test    rcx, rcx
0x101798c27  jz      short loc_101798C4A
0x101798c29  mov     edx, 720h
0x101798c2e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101798c34  test    eax, eax
0x101798c36  jz      short loc_101798C4A
0x101798c38  mov     eax, [rsp+9C0h+var_970]
0x101798c3c  mov     edx, eax
0x101798c3e  lea     rcx, aFcbGetactualse_3; "FCB::GetActualSectorSize: GetPhysicalSe"...
0x101798c45  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x101798c4a  mov     r8d, r15d; cchBufferLength
0x101798c4d  lea     rdx, [rbp+8C0h+szVolumePathName]; lpszVolumePathName
0x101798c54  lea     rcx, [rbp+8C0h+szFileName]; lpszFileName
0x101798c5b  call    cs:__imp_GetVolumePathNameW
0x101798c61  mov     ebx, eax
0x101798c63  call    cs:__imp_GetLastError
0x101798c69  mov     [rsp+9C0h+var_970], eax
0x101798c6d  test    ebx, ebx
0x101798c6f  jnz     loc_101798D8D
0x101798c75  test    rdi, rdi
0x101798c78  jz      short loc_101798C7C
0x101798c7a  mov     [rdi], eax
0x101798c7c  test    cs:byte_10317AC62, 4
0x101798c83  jnz     loc_101798D1C
0x101798c89  mov     r9, gs:58h
0x101798c92  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101798c99  mov     ecx, [rax]
0x101798c9b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101798ca2  mov     r8d, [rax]
0x101798ca5  add     r8, [r9+rcx*8]
0x101798ca9  mov     rax, [r8]
0x101798cac  test    rax, rax
0x101798caf  jz      short loc_101798CCC
0x101798cb1  mov     rax, [rax+38h]
0x101798cb5  mov     rcx, [rax]
0x101798cb8  test    rcx, rcx
0x101798cbb  jz      short loc_101798CCC
0x101798cbd  mov     edx, 712h
0x101798cc2  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101798cc8  test    eax, eax
0x101798cca  jnz     short loc_101798D18
0x101798ccc  test    cs:byte_10317AC64, 1
0x101798cd3  jnz     short loc_101798D18
0x101798cd5  mov     r9, gs:58h
0x101798cde  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101798ce5  mov     ecx, [rax]
0x101798ce7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101798cee  mov     r8d, [rax]
0x101798cf1  add     r8, [r9+rcx*8]
0x101798cf5  mov     rax, [r8]
0x101798cf8  test    rax, rax
0x101798cfb  jz      short loc_101798D31
0x101798cfd  mov     rax, [rax+38h]
0x101798d01  mov     rcx, [rax]
0x101798d04  test    rcx, rcx
0x101798d07  jz      short loc_101798D31
0x101798d09  mov     edx, 720h
0x101798d0e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x101798d14  test    eax, eax
0x101798d16  jz      short loc_101798D31
0x101798d18  mov     eax, [rsp+9C0h+var_970]
  ... truncated ...
```
