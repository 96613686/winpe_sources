# CBlbBackupAsync::BackupToMedia(_GUID *,ushort * *,ulong,CBlbMediaBackupContext *,CBlbMediaBackupContext *,uchar *,long *)

- ea: `0x1400170c8`
- end: `0x140019618`
- name: `?BackupToMedia@CBlbBackupAsync@@AEAAJPEAU_GUID@@PEAPEAGKPEAVCBlbMediaBackupContext@@2PEAEPEAJ@Z`
- size: `9552`
- prototype: `__int64 __usercall@<rax>(CBlbBackupAsync *__hidden this@<rcx>, struct _GUID *@<rdx>, unsigned __int16 **@<r8>, unsigned int@<r9d>, struct CBlbMediaBackupContext *, struct CBlbMediaBackupContext *, unsigned __int8 *, int *)`
- caller_count: `1`
- callee_count: `64`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002f0d4`

## callees

- `0x1400020d0`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bcbc`
- `0x14000be04`
- `0x140010a08`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140014384`
- `0x140015ad8`
- `0x1400167f4`
- `0x1400170c8`
- `0x140020e24`
- `0x140022ed0`
- `0x140026c8c`
- `0x14002bfa8`
- `0x14002c674`
- `0x14002cbe8`
- `0x14002e4e0`
- `0x14002f98c`
- `0x140030644`
- `0x140033b94`
- `0x140034c2c`
- `0x140035180`
- `0x140036d4c`
- `0x1400371b0`
- `0x140037268`
- `0x1400372a8`
- `0x1400377d0`
- `0x1400389c0`
- `0x140039ec0`
- `0x14003bcd0`
- `0x14003c434`
- `0x14003c480`
- `0x14003c69c`
- `0x14003c6dc`
- `0x14003c884`
- `0x14003cb70`
- `0x14003d318`
- `0x14008863c`
- `0x140088ba4`
- `0x14008e8e8`
- `0x14008fed0`
- `0x1400be8b0`
- `0x1400bf178`
- `0x1400bf574`
- `0x1400bf788`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140017fde`
- `ADVAPI32!RegOpenKeyExW` at `0x140017fde`
- `ADVAPI32!RegCloseKey` at `0x1400180d0`
- `ADVAPI32!RegCloseKey` at `0x1400180d0`
- `ADVAPI32!RegQueryValueExW` at `0x140018019`
- `ADVAPI32!RegQueryValueExW` at `0x140018019`
- `KERNEL32!FlushFileBuffers` at `0x1400186c2`
- `KERNEL32!FlushFileBuffers` at `0x1400186c2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400177cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140017860`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140018410`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400189b2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400177cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140017860`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140018410`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400189b2`
- `KERNEL32!LocalFree` at `0x14001727f`
- `KERNEL32!LocalFree` at `0x140017d8c`
- `KERNEL32!LocalFree` at `0x14001727f`
- `KERNEL32!LocalFree` at `0x140017d8c`
- `KERNEL32!CloseHandle` at `0x140017a1d`
- `KERNEL32!CloseHandle` at `0x140018776`
- `KERNEL32!CloseHandle` at `0x140017a1d`
- `KERNEL32!CloseHandle` at `0x140018776`
- `KERNEL32!GetLastError` at `0x140017a27`
- `KERNEL32!GetLastError` at `0x1400186cc`
- `KERNEL32!GetLastError` at `0x140018780`
- `KERNEL32!GetLastError` at `0x140017a27`
- `KERNEL32!GetLastError` at `0x1400186cc`
- `KERNEL32!GetLastError` at `0x140018780`
- `KERNEL32!LeaveCriticalSection` at `0x140018aff`
- `KERNEL32!LeaveCriticalSection` at `0x140019096`
- `KERNEL32!LeaveCriticalSection` at `0x1400190cf`
- `KERNEL32!LeaveCriticalSection` at `0x140018aff`
- `KERNEL32!LeaveCriticalSection` at `0x140019096`
- `KERNEL32!LeaveCriticalSection` at `0x1400190cf`
- `KERNEL32!EnterCriticalSection` at `0x140018a6a`
- `KERNEL32!EnterCriticalSection` at `0x140019070`
- `KERNEL32!EnterCriticalSection` at `0x140019081`
- `KERNEL32!EnterCriticalSection` at `0x140018a6a`
- `KERNEL32!EnterCriticalSection` at `0x140019070`
- `KERNEL32!EnterCriticalSection` at `0x140019081`
- `msvcrt!_wcsicmp` at `0x1400174ed`
- `msvcrt!_wcsicmp` at `0x1400174ed`
- `ole32!CoTaskMemAlloc` at `0x1400173da`
- `ole32!CoTaskMemAlloc` at `0x14001740a`
- `ole32!CoTaskMemAlloc` at `0x1400173da`
- `ole32!CoTaskMemAlloc` at `0x14001740a`
- `ole32!CoTaskMemFree` at `0x1400172a6`
- `ole32!CoTaskMemFree` at `0x1400172b8`
- `ole32!CoTaskMemFree` at `0x1400172ca`
- `ole32!CoTaskMemFree` at `0x1400172dc`
- `ole32!CoTaskMemFree` at `0x14001757f`
- `ole32!CoTaskMemFree` at `0x140017ed2`
- `ole32!CoTaskMemFree` at `0x14001955f`
- `ole32!CoTaskMemFree` at `0x1400172a6`
- `ole32!CoTaskMemFree` at `0x1400172b8`
- `ole32!CoTaskMemFree` at `0x1400172ca`
- `ole32!CoTaskMemFree` at `0x1400172dc`
- `ole32!CoTaskMemFree` at `0x14001757f`
- `ole32!CoTaskMemFree` at `0x140017ed2`
- `ole32!CoTaskMemFree` at `0x14001955f`
- `OLEAUT32!__imp_SysFreeString` at `0x14001917f`
- `OLEAUT32!__imp_SysFreeString` at `0x14001917f`
- `RPCRT4!UuidCreate` at `0x140017496`
- `RPCRT4!UuidCreate` at `0x140017496`
- `VirtDisk!DetachVirtualDisk` at `0x1400179d9`
- `VirtDisk!DetachVirtualDisk` at `0x14001873f`
- `VirtDisk!DetachVirtualDisk` at `0x1400179d9`
- `VirtDisk!DetachVirtualDisk` at `0x14001873f`

## string_xrefs

- `0x140017fbc`: `SYSTEM\CurrentControlSet\Services\wbengine`
- `0x140018067`: `SYSTEM\CurrentControlSet\Services\wbengine`
- `0x1400180a6`: `SYSTEM\CurrentControlSet\Services\wbengine`
- `0x1400171e9`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001775e`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400181cf`: `base\stor\blb\engine\service\backup.cpp`
- `0x140018ced`: `base\stor\blb\engine\service\backup.cpp`
- `0x140018fbf`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001900e`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019109`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019531`: `base\stor\blb\engine\service\backup.cpp`
- `0x140017752`: `COMPACT(m_ulFeatures) || !m_rules.m_bExcludeAudio && !m_rules.m_bExcludeVideo`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::BackupToMedia(
        CBlbBackupAsync *this,
        struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        struct CBlbMediaBackupContext *a5,
        struct CBlbMediaBackupContext *a6,
        unsigned __int8 *a7,
        int *a8)
{
  struct CBlbMediaBackupContext *v9; // r13
  struct CBlbMediaBackupContext *v10; // rsi
  CBlbBackupAsync *v11; // r12
  unsigned __int16 *v12; // r15
  void *v13; // r14
  int *v14; // rax
  int IsClientSKU; // edi
  unsigned __int8 *v16; // rbx
  int v17; // r8d
  PVOID *v18; // rcx
  const char *v19; // rax
  SIZE_T v20; // rbx
  void *v21; // rax
  unsigned int v22; // ebx
  void *v23; // rax
  int v24; // r13d
  __int64 v25; // r8
  unsigned int v26; // r15d
  _DWORD *v27; // r15
  CBlbVolumeBackupContext *v28; // rbx
  const wchar_t *v29; // r14
  __int64 v30; // r8
  int appended; // r14d
  CBlbVolumeBackupContext *v32; // r15
  __int64 v33; // rdx
  unsigned int v34; // ebx
  PVOID *v35; // rcx
  const unsigned __int16 *v36; // rcx
  UUID *v37; // rcx
  UUID v38; // xmm0
  struct CBlbMediaBackupContext *v39; // rdx
  _BYTE *v40; // rdi
  bool v41; // zf
  unsigned __int16 *v42; // rbx
  int v43; // r8d
  int v44; // edx
  unsigned int v45; // ebx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  _QWORD *v49; // rcx
  int v50; // edx
  __int64 v51; // rcx
  unsigned __int16 *v52; // rdi
  HANDLE v53; // rbx
  int v54; // eax
  int v55; // eax
  _QWORD *v56; // rbx
  HLOCAL v57; // rcx
  int v58; // edx
  _QWORD *v59; // rdi
  void *v60; // r14
  unsigned int BackupPointer; // edi
  struct CBlbMediaBackupContext *v62; // r8
  CBlbVolumeBackupContext *v63; // rdi
  int v64; // edi
  char v65; // di
  LSTATUS Value; // eax
  PVOID *v67; // rcx
  unsigned __int64 v68; // rsi
  unsigned __int64 v69; // rax
  unsigned int v70; // eax
  char v71; // bl
  __int64 v72; // rdx
  __int64 v73; // rdx
  unsigned __int8 v74; // r13
  LPVOID v75; // rbx
  PVOID *v76; // rcx
  void *ImpersonationToken; // rax
  _OWORD *v78; // rdi
  unsigned int v79; // r12d
  const WCHAR *v80; // rsi
  bool v81; // bl
  int VhdInfo; // eax
  int v83; // eax
  int v84; // ebx
  HANDLE v85; // rsi
  __int64 v86; // rdx
  char v87; // r8
  char v88; // r9
  char v89; // al
  char v90; // r10
  char v91; // r11
  char v92; // bl
  char v93; // di
  char v94; // si
  __int16 v95; // r14
  CBlbBackupAsync *v96; // rbx
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  int v100; // eax
  int v101; // eax
  unsigned __int16 *v102; // rbx
  int IncrementalBackupFileSize; // eax
  int v104; // eax
  int v105; // eax
  UUID *v106; // rcx
  UUID v107; // xmm0
  int v108; // eax
  CBlbVolumeBackupContext *v109; // rbx
  struct _RTL_CRITICAL_SECTION *v110; // rcx
  ATL::CComBSTR *v111; // rax
  int v112; // eax
  unsigned __int16 *v113; // rbx
  int *v114; // rcx
  int v115; // eax
  unsigned int v116; // esi
  unsigned int v117; // ebx
  __int64 v118; // rcx
  __int64 v119; // r8
  char *v120; // r14
  struct _GUID *v121; // rdx
  __int64 v122; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  char phkResulta; // [rsp+20h] [rbp-E0h]
  int v126; // [rsp+30h] [rbp-D0h]
  char *v127; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v128; // [rsp+70h] [rbp-90h]
  _DWORD v129[3]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int8 v130[8]; // [rsp+80h] [rbp-80h] BYREF
  CBlbVolumeBackupContext *v131; // [rsp+88h] [rbp-78h]
  char v132; // [rsp+90h] [rbp-70h] BYREF
  __int16 v133; // [rsp+91h] [rbp-6Fh] BYREF
  int v134; // [rsp+94h] [rbp-6Ch]
  int v135; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 v136; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int8 v137[3]; // [rsp+9Dh] [rbp-63h] BYREF
  struct CBlbMediaBackupContext *v138; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v139; // [rsp+A8h] [rbp-58h]
  void *Source1; // [rsp+B0h] [rbp-50h]
  unsigned int v141; // [rsp+B8h] [rbp-48h]
  struct CBlbMediaBackupContext *v142; // [rsp+C0h] [rbp-40h]
  CBlbBackupAsync *v143; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v144; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v146; // [rsp+E0h] [rbp-20h] BYREF
  int v147; // [rsp+E8h] [rbp-18h]
  __int64 v148; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v149; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v150; // [rsp+100h] [rbp+0h] BYREF
  PCWSTR Path; // [rsp+108h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v153; // [rsp+118h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+120h] [rbp+20h]
  HANDLE VirtualDiskHandle; // [rsp+128h] [rbp+28h] BYREF
  LPVOID v156; // [rsp+130h] [rbp+30h]
  DWORD cbData[2]; // [rsp+138h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 **v159; // [rsp+148h] [rbp+48h]
  __int64 v160; // [rsp+150h] [rbp+50h]
  __int64 v161; // [rsp+158h] [rbp+58h] BYREF
  __int64 v162; // [rsp+160h] [rbp+60h]
  __int64 v163; // [rsp+168h] [rbp+68h]
  unsigned __int64 v164; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v165; // [rsp+178h] [rbp+78h] BYREF
  __int64 v166; // [rsp+180h] [rbp+80h]
  __int64 v167; // [rsp+188h] [rbp+88h]
  int *v168; // [rsp+190h] [rbp+90h]
  struct _GUID *v169; // [rsp+198h] [rbp+98h]
  BSTR bstrString; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _GET_VIRTUAL_DISK_INFO VirtualDiskInfo; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v172[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  UUID Uuid; // [rsp+1E0h] [rbp+E0h] BYREF

  v9 = a5;
  v10 = a6;
  v11 = this;
  v168 = a8;
  v147 = 0;
  v12 = 0;
  v135 = 0;
  v13 = 0;
  v153 = 0;
  v156 = 0;
  pv = 0;
  v144 = 0;
  Source1 = 0;
  hMem = 0;
  v161 = 0;
  v150 = 0;
  v149 = 0;
  v129[0] = 0;
  Path = 0;
  v164 = 0;
  v146 = 0;
  v133 = 0;
  v132 = 0;
  v137[0] = 0;
  v130[2] = 0;
  v165 = 0;
  VirtualDiskHandle = 0;
  v141 = a4;
  v159 = a3;
  v169 = a2;
  v143 = this;
  v142 = a5;
  v138 = a6;
  v139 = a7;
  Uuid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 508, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( a4 != *((_DWORD *)v11 + 92) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2EF8u, "cVolumeName == m_cVolume");
  v14 = v168;
  *a7 = 0;
  *v14 = 0;
  CBlbAsync::LockedIncrement((CBlbBackupAsync *)((char *)v11 + 24), (unsigned int *)v11 + 56);
  *((_DWORD *)a6 + 4) = *((_DWORD *)v11 + 56);
  IsClientSKU = BlbutilIsClientSKU(v137);
  if ( IsClientSKU < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 509, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    goto LABEL_12;
  }
  IsClientSKU = BlbutilAppendString(*((const unsigned __int16 **)v11 + 43), L"\\", &v153);
  if ( IsClientSKU < 0 )
  {
LABEL_12:
    v16 = v139;
    goto LABEL_13;
  }
  v20 = 16LL * v141;
  v21 = CoTaskMemAlloc(v20);
  v156 = v21;
  if ( !v21 || (memset_0(v21, 0, v20), v22 = 16 * v141, v23 = CoTaskMemAlloc(16 * v141), (pv = v23) == 0) )
  {
    IsClientSKU = -2147024882;
    goto LABEL_12;
  }
  v24 = 0;
  v160 = 0;
  memset_0(v23, 0, v22);
  while ( 1 )
  {
    while ( 1 )
    {
      v25 = *((unsigned int *)v10 + 2);
      v26 = v141;
      if ( (unsigned int)v25 >= v141 )
        goto LABEL_502;
      v128 = 0;
      v27 = (_DWORD *)((char *)v11 + 372);
      v130[1] = 0;
      v24 &= -((_BYTE)v13 != 0);
      v134 = v24;
      v130[3] = 0;
      v131 = (CBlbVolumeBackupContext *)(*((_QWORD *)v11 + 27) + 368 * v25);
      v28 = v131;
      v29 = v159[v25];
      *(_QWORD *)&v129[1] = v29;
      CBlbAsync::LockedSet((CBlbBackupAsync *)((char *)v11 + 24), (unsigned int *)v11 + 93, v25);
      UuidCreate(&Uuid);
      if ( (*((_BYTE *)v28 + 84) & 1) == 0 )
      {
        v33 = *((_QWORD *)v11 + 54);
        v34 = 0;
        if ( *(_DWORD *)(v33 + 80) )
        {
          do
          {
            v160 = *(_QWORD *)(v33 + 88) + 56LL * v34;
            if ( !_wcsicmp(*(const wchar_t **)(v160 + 16), v29) )
              break;
            v33 = *((_QWORD *)v11 + 54);
            ++v34;
          }
          while ( v34 < *(_DWORD *)(v33 + 80) );
          v10 = v138;
        }
        if ( v34 != *(_DWORD *)(*((_QWORD *)v11 + 54) + 80LL) )
        {
          if ( v144 )
          {
            CoTaskMemFree(v144);
            v144 = 0;
          }
          v36 = *(const unsigned __int16 **)(v160 + 24);
          if ( !v36 )
          {
            v35 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v29);
              v35 = (PVOID *)WPP_GLOBAL_Control;
            }
            appended = -2139619296;
            v130[1] = 1;
            goto LABEL_72;
          }
          appended = BlbutilRemoveTrailingBackslash(v36, &v144);
          if ( appended < 0 )
            goto LABEL_125;
          v28 = v131;
          goto LABEL_75;
        }
        v32 = v131;
        appended = *((_DWORD *)v131 + 8);
        if ( appended >= 0 )
        {
          appended = -2139619296;
          v35 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_63;
          }
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            510,
            &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            *(_QWORD *)&v129[1]);
        }
        v35 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
        v130[1] = 1;
        goto LABEL_127;
      }
      appended = BlbutilRemoveTrailingBackslash(v159[*((unsigned int *)v10 + 2)], &v144);
      if ( appended < 0 )
      {
        v32 = v28;
LABEL_126:
        v35 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_127;
      }
LABEL_75:
      if ( (*((_BYTE *)v28 + 84) & 0x40) == 0 )
        break;
      IsClientSKU = CBlbBackupAsync::BackupFilesToMediaForVolume(v11, v28);
      if ( IsClientSKU < 0 )
        goto LABEL_517;
      CBlbAsync::LockedIncrement((CBlbBackupAsync *)((char *)v11 + 24), (unsigned int *)v11 + 57);
      v37 = (UUID *)v156;
      v38 = Uuid;
      *((_DWORD *)v10 + 3) = *((_DWORD *)v11 + 57);
      v37[*v27] = v38;
LABEL_78:
      ++*((_DWORD *)v10 + 2);
      LOBYTE(v13) = v130[3];
    }
    if ( (*((_BYTE *)v28 + 84) & 8) == 0 )
    {
      if ( (*((_BYTE *)v28 + 84) & 0x20) == 0 )
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\backup.cpp",
          0x2F94u,
          "VOLUME_HAS_SYSTEMSTATE(pVolCtxt->m_dwVolumeFlags)");
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v111 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)((char *)v28 + 68));
        v147 |= 1u;
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          512,
          &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *(_QWORD *)v111);
      }
      if ( (v147 & 1) != 0 )
      {
        v147 &= ~1u;
        SysFreeString(bstrString);
      }
      goto LABEL_78;
    }
    CBlbBackupAsync::SetState(v11, 8);
    v39 = v142;
    *((_DWORD *)v10 + 11) = 8;
    if ( *((_DWORD *)v10 + 2) != *((_DWORD *)v39 + 2) || !*((_QWORD *)v39 + 6) )
    {
      if ( Source1 && Source1 != *((void **)v10 + 6) && Source1 != *((void **)v39 + 6) )
        BlbimgFreeContext(Source1);
      v41 = (*((_BYTE *)v28 + 84) & 1) == 0;
      Source1 = 0;
      v148 = 0;
      if ( !v41 )
      {
        appended = CBlbBackupAsync::PrepareForESPBackupOperation(v11);
        if ( appended < 0 )
        {
          v35 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 513, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            goto LABEL_93;
          }
LABEL_72:
          v32 = v131;
          goto LABEL_127;
        }
      }
      CBlbBackupAsync::UpdateBytes(v11, 0, 0);
      if ( (*((_BYTE *)v11 + 340) & 0x10) == 0 && (*((_BYTE *)v11 + 380) || *((_BYTE *)v11 + 381)) )
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\backup.cpp",
          0x2FCEu,
          "COMPACT(m_ulFeatures) || !m_rules.m_bExcludeAudio && !m_rules.m_bExcludeVideo");
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        v42 = v144;
      }
      else
      {
        v42 = v144;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            514,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            v129[1],
            (__int64)v144);
      }
      GetSystemTimeAsFileTime((LPFILETIME)(*((_QWORD *)v11 + 27) + 140LL + 368LL * (unsigned int)*v27));
      v44 = *((_DWORD *)v11 + 85);
      if ( (v44 & 2) != 0 )
      {
        v45 = BlbimgPrepareForBackup(
                v42,
                (int)phkResult,
                (int)v11,
                v126,
                (__int64)&v161,
                (__int64)&v148,
                (__int64)&v149,
                (__int64)&v150,
                (__int64)v129);
      }
      else
      {
        LOBYTE(v44) = *((_BYTE *)v11 + 380);
        LOBYTE(v43) = *((_BYTE *)v11 + 381);
        v45 = BlbimgPrepareForReplication(
                (_DWORD)v42,
                v44,
                v43,
                0,
                (__int64)BlbPrepareForBackupCallback,
                (__int64)v11,
                v126,
                0,
                (__int64)&v161,
                (__int64)&v148,
                (__int64)&v149,
                (__int64)&v150,
                (__int64)&v165,
                (__int64)v129);
        if ( !v45 )
        {
          v40 = (_BYTE *)v148;
          Source1 = (void *)v148;
          if ( !v148 )
            BlbAssert("base\\stor\\blb\\blbimg\\blbimg.cxx", 0x1FABu, "ReplicationContext != NULL");
          if ( v40[184] )
          {
            CBlbVolumeBackupContext::SetVolumeVolumeFlags(v131, 0x2000);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 515, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 516, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
LABEL_106:
          GetSystemTimeAsFileTime((LPFILETIME)(*((_QWORD *)v11 + 27) + 148LL + 368LL * (unsigned int)*v27));
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v46 = *((_QWORD *)v11 + 27);
            v47 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v48 = 368LL * (unsigned int)*v27;
            v163 = *(_QWORD *)(v48 + v46 + 140);
            v162 = *(_QWORD *)(v48 + v46 + 148);
            WPP_SF_q(v47, 517, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, (v162 - v163) / 0x2710uLL);
          }
          CBlbBackupAsync::UpdateBytes(v11, v150, v149);
          *((_QWORD *)v10 + 4) = v149;
          *((_QWORD *)v10 + 3) = v150;
          if ( !v45 )
          {
            v28 = v131;
            v39 = v142;
            goto LABEL_180;
          }
          if ( v45 == 1 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v11 + 3) + 16LL))((__int64)v11 + 24) )
              appended = -2139618969;
            goto LABEL_125;
          }
          if ( v45 != 4 )
          {
            switch ( v45 )
            {
              case 5u:
                goto LABEL_164;
              case 6u:
                goto LABEL_167;
              case 7u:
LABEL_164:
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_SLd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    519,
                    (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                    v129[1],
                    v45,
                    v129[0]);
                }
                appended = BlbTranslateBlbimgError(v45, v129[0], &v135);
                v128 = 1;
                goto LABEL_125;
            }
            if ( v45 != 22 && v45 != 31 )
            {
              v49 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_123;
              }
              v50 = 520;
              goto LABEL_122;
            }
          }
LABEL_167:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SLd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              518,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              v129[1],
              v45,
              v129[0]);
          }
          v54 = BlbTranslateBlbimgError(v45, v129[0], &v135);
          v32 = v131;
          appended = v54;
          if ( (*((_BYTE *)v131 + 84) & 1) == 0
            && (int)CBlbBackupAsync::IsSourceSnapshotDeleted(v144, &v130[2]) >= 0
            && !v130[2] )
          {
            appended = -2139618967;
          }
          v130[1] = 1;
          goto LABEL_126;
        }
      }
      v40 = (_BYTE *)v148;
      Source1 = (void *)v148;
      goto LABEL_106;
    }
    v40 = (_BYTE *)*((_QWORD *)v39 + 6);
    Source1 = v40;
LABEL_180:
    *((_QWORD *)v10 + 6) = v40;
    v55 = *((_DWORD *)v39 + 2);
    if ( *((_DWORD *)v10 + 2) != v55 )
      goto LABEL_188;
    if ( !*((_QWORD *)v39 + 6) && (*((_BYTE *)v28 + 84) & 1) == 0 )
      *((_QWORD *)v39 + 6) = v40;
    if ( *((_DWORD *)v10 + 2) == v55 )
    {
      v56 = (_QWORD *)((char *)v39 + 56);
      v57 = (HLOCAL)*((_QWORD *)v39 + 7);
      if ( v57 )
      {
        v58 = *((_DWORD *)v39 + 16);
        hMem = v57;
LABEL_203:
        v60 = Source1;
        goto LABEL_204;
      }
      v59 = (_QWORD *)((char *)v39 + 56);
    }
    else
    {
LABEL_188:
      v59 = (_QWORD *)((char *)v39 + 56);
    }
    if ( !hMem || hMem == *((HLOCAL *)v10 + 7) )
    {
      v56 = v59;
    }
    else
    {
      v56 = (_QWORD *)((char *)v39 + 56);
      if ( hMem != *((HLOCAL *)v39 + 7) )
        LocalFree(hMem);
    }
    v57 = 0;
    v58 = 0;
    v41 = (*((_BYTE *)v11 + 340) & 2) == 0;
    hMem = 0;
    *(_DWORD *)Data = 0;
    if ( v41 )
    {
      v56 = v59;
      goto LABEL_203;
    }
    v60 = Source1;
    BackupPointer = BlbimgQueryBackupPointer(Source1);
    if ( BackupPointer )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          v129[1],
          BackupPointer,
          v129[0]);
      }
      v51 = BackupPointer;
      goto LABEL_124;
    }
    v57 = hMem;
    v58 = *(_DWORD *)Data;
LABEL_204:
    v62 = v142;
    v63 = v131;
    *((_QWORD *)v10 + 7) = v57;
    *((_DWORD *)v10 + 16) = v58;
    if ( *((_DWORD *)v10 + 2) == *((_DWORD *)v62 + 2) && !*v56 && (*((_BYTE *)v63 + 84) & 1) == 0 )
    {
      *v56 = v57;
      *((_DWORD *)v62 + 16) = v58;
    }
    CBlbBackupAsync::SetState(v11, 9);
    CBlbMediaBackupContext::SetState(v10, 9);
    if ( (*((_BYTE *)v11 + 340) & 2) != 0 )
    {
      v45 = BlbimgSetBackupPointer(v60, hMem);
      if ( v45 )
      {
        v49 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_123;
        }
        v50 = 522;
LABEL_122:
        WPP_SF_SLd(v49[2], v50, (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v129[1], v45, v129[0]);
LABEL_123:
        v51 = v45;
LABEL_124:
        appended = BlbTranslateBlbimgError(v51, v129[0], &v135);
LABEL_125:
        v32 = v131;
        goto LABEL_126;
      }
    }
    if ( Path )
    {
      CoTaskMemFree((LPVOID)Path);
      Path = 0;
    }
    appended = BlbAppendBagFile(
                 *((unsigned __int16 **)v11 + 59),
                 (UUID *)((char *)v63 + 68),
                 *((_DWORD *)v63 + 21),
                 L".vhdx",
                 (unsigned __int16 **)&Path);
    if ( appended < 0 )
      goto LABEL_125;
    CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v11 + 40));
    v64 = (int)Path;
    appended = CBlbBackupAsync::DeleteBackupFileIfCompressed(v11, (unsigned __int16 *)Path);
    if ( appended < 0 )
    {
      v128 = 1;
      v35 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          523,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          v64,
          appended);
LABEL_93:
        v35 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_72;
    }
    IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)v11 + 40), 0);
    if ( IsClientSKU < 0 )
      goto LABEL_517;
    appended = BlbQueryFileSystemSpace(v153, &v164, &v146);
    LODWORD(v148) = appended;
    hKey = 0;
    v65 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\wbengine", 0, 1u, &hKey) )
    {
      *(_DWORD *)Data = 0;
      cbData[0] = 4;
      Value = RegQueryValueExW(hKey, L"FreeSpace", 0, 0, Data, cbData);
      v67 = (PVOID *)WPP_GLOBAL_Control;
      if ( Value )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
          v68 = v146;
LABEL_238:
          RegCloseKey(hKey);
          v35 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_244;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            524,
            &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            L"SYSTEM\\CurrentControlSet\\Services\\wbengine");
          v67 = (PVOID *)WPP_GLOBAL_Control;
        }
        v68 = v146;
      }
      else
      {
        v68 = v146;
        v69 = (unsigned __int64)*(unsigned int *)Data << 20;
        if ( v69 && v69 < v146 )
        {
          v68 = (unsigned __int64)*(unsigned int *)Data << 20;
          v146 = v68;
          v65 = 1;
        }
      }
      if ( v67 != &WPP_GLOBAL_Control && (*((_BYTE *)v67 + 28) & 1) != 0 && *((_BYTE *)v67 + 25) >= 4u )
        WPP_SF_qS(
          (unsigned int)v67[2],
          525,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          v68,
          (__int64)L"SYSTEM\\CurrentControlSet\\Services\\wbengine");
      goto LABEL_238;
    }
    v35 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        526,
        &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        L"SYSTEM\\CurrentControlSet\\Services\\wbengine");
      v35 = (PVOID *)WPP_GLOBAL_Control;
    }
    v68 = v146;
LABEL_244:
    if ( appended < 0 )
    {
      v128 = 1;
LABEL_246:
      v10 = v138;
      goto LABEL_72;
    }
    if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 1) != 0 && *((_BYTE *)v35 + 25) >= 4u )
      WPP_SF_qq(v35[2], 527, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v164, v68);
    CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v11 + 40));
    if ( (*((_BYTE *)v11 + 340) & 2) == 0 )
      goto LABEL_283;
    v30 = (__int64)v138;
    v70 = *((_DWORD *)v138 + 3);
    if ( v70 == *((_DWORD *)v142 + 3) )
    {
      v71 = 1;
      v35 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_264;
      }
      v72 = 528;
    }
    else
    {
      if ( v70 <= *((_DWORD *)v142 + 3) )
      {
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\backup.cpp",
          0x30F7u,
          "pMediaCtxt->m_ulBagCount > pInitialMediaCtxt->m_ulBagCount");
        v30 = (__int64)v138;
      }
      v71 = 0;
      v35 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_264;
      }
      v70 = *(_DWORD *)(v30 + 12);
      v72 = 529;
    }
    LODWORD(phkResult) = v70;
    WPP_SF_dd(v35[2], v72, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    v35 = (PVOID *)WPP_GLOBAL_Control;
LABEL_264:
    if ( v68 <= 0x1400000 )
    {
      v128 = 1;
      appended = v71 != 0 ? -2139619212 : -2139619280;
      if ( v35 == &WPP_GLOBAL_Control || (*((_BYTE *)v35 + 28) & 1) == 0 || *((_BYTE *)v35 + 25) < 3u )
        goto LABEL_246;
      v73 = 530;
      goto LABEL_269;
    }
    if ( !v65 )
    {
      v30 = 0x40000000;
      if ( v68 <= 0x40000000 )
      {
        if ( v71 )
        {
          appended = -2139619200;
          v128 = 1;
          if ( v35 == &WPP_GLOBAL_Control || (*((_BYTE *)v35 + 28) & 1) == 0 || *((_BYTE *)v35 + 25) < 3u )
            goto LABEL_246;
          WPP_SF_qq(v35[2], 531, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v68, 0x40000000);
          goto LABEL_270;
        }
      }
    }
    v68 -= 20971520LL;
    v146 = v68;
    if ( v68 <= 0x1100000 )
    {
      v128 = 1;
      appended = v71 != 0 ? -2139619212 : -2139619280;
      if ( v35 == &WPP_GLOBAL_Control || (*((_BYTE *)v35 + 28) & 1) == 0 || *((_BYTE *)v35 + 25) < 3u )
        goto LABEL_246;
      v73 = 532;
LABEL_269:
      WPP_SF_q(v35[2], v73, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v68);
LABEL_270:
      v35 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_246;
    }
LABEL_283:
    v41 = (*((_BYTE *)v11 + 340) & 4) == 0;
    v74 = 1;
    v75 = pv;
    v136 = 1;
    if ( !v41 )
    {
      IsClientSKU = CBlbBackupAsync::IsForceFullNeededForCurrentBag(
                      v11,
                      v169,
                      &v136,
                      (unsigned __int8 *)pv + (unsigned int)(16 * *v27));
      if ( IsClientSKU < 0 )
        goto LABEL_516;
      v74 = v136;
    }
    v130[0] = v74;
    CBlbBackupAsync::UpdateBytes(v11, 0, 0);
    v76 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 533, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v68);
        v76 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v76 != &WPP_GLOBAL_Control && (*((_BYTE *)v76 + 28) & 1) != 0 && *((_BYTE *)v76 + 25) >= 4u )
        WPP_SF_S(v76[2], 534, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, *(_QWORD *)&v129[1]);
    }
    GetSystemTimeAsFileTime((LPFILETIME)(*((_QWORD *)v11 + 27) + 156LL + 368LL * (unsigned int)*v27));
    if ( (*((_BYTE *)v11 + 340) & 2) != 0 )
    {
      ImpersonationToken = CBlbImpersonationHelper::GetImpersonationToken((CBlbBackupAsync *)((char *)v11 + 40));
      v78 = Source1;
      v79 = BlbimgWriteBackup(
              Source1,
              (int)BlbPrepareForBackupCallback,
              (__int64)v11,
              (__int64)ImpersonationToken,
              (__int64)v130,
              (__int64)&v133,
              (__int64)v75 + (unsigned int)(16 * *((_DWORD *)v11 + 93)),
              (__int64)&v149,
              (__int64)&v150,
              (__int64)v129,
              (__int64)&v132);
      goto LABEL_349;
    }
    memset(&VirtualDiskInfo, 0, sizeof(VirtualDiskInfo));
    *(_QWORD *)cbData = 0;
    if ( v130[0] )
    {
      v80 = Path;
    }
    else
    {
      IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)v11 + 40), 0);
      if ( IsClientSKU < 0 )
        goto LABEL_516;
      v80 = Path;
      v81 = FileExists((unsigned __int16 *)Path);
      CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v11 + 40));
      if ( v81 )
      {
        VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_IDENTIFIER;
        VhdInfo = CBlbVhd::GetVhdInfo((CBlbBackupAsync *)((char *)v11 + 40), v80, &VirtualDiskInfo);
        if ( VhdInfo < 0 )
        {
          v35 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              535,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              (_DWORD)v80,
              VhdInfo);
            v35 = (PVOID *)WPP_GLOBAL_Control;
          }
          v24 = v134;
          goto LABEL_246;
        }
      }
    }
    v32 = v131;
    v83 = CBlbBackupAsync::PrepareTargetVolumesForBlocks(v11, v131, v165, (__int64 *)cbData);
    if ( v83 < 0 )
    {
      v24 = v134;
      appended = v83;
      v10 = v138;
      goto LABEL_126;
    }
    IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)v11 + 40), 0);
    if ( IsClientSKU < 0 )
    {
LABEL_516:
      v10 = v138;
      goto LABEL_517;
    }
    v84 = CBlbVhdHelper::OpenVhdForOfflineWrite(v80, &VirtualDiskHandle);
    CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v11 + 40));
    if ( v84 < 0 )
    {
      v35 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          536,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v80,
          v84);
        v35 = (PVOID *)WPP_GLOBAL_Control;
      }
      appended = v84;
      goto LABEL_315;
    }
    v85 = VirtualDiskHandle;
    v78 = Source1;
    v127 = (char *)pv + (unsigned int)(16 * *((_DWORD *)v11 + 93));
    *(_OWORD *)v172 = *(_OWORD *)&VirtualDiskInfo.Size.VirtualSize;
    v79 = BlbimgPerformReplication(
            Source1,
            (__int64)v130,
            (__int64)v172,
            *(__int64 *)cbData,
            (__int64)VirtualDiskHandle,
            (__int64)v127,
            (__int64)&v149,
            (__int64)&v150,
            (__int64)&v132,
            (__int64)v129);
    if ( !v79 )
    {
      if ( !FlushFileBuffers(v85) )
      {
        v129[0] = GetLastError();
        v35 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v86 = 537;
LABEL_322:
          WPP_SF_d(v35[2], v86, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          v35 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_323;
        }
        goto LABEL_323;
      }
      v129[0] = DetachVirtualDisk(v85, DETACH_VIRTUAL_DISK_FLAG_NONE, 0);
      if ( v129[0] )
      {
        v35 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v86 = 538;
          goto LABEL_322;
        }
LABEL_323:
        if ( v129[0] > 0 )
          appended = LOWORD(v129[0]) | 0x80070000;
        else
          appended = v129[0];
        v11 = v143;
LABEL_315:
        v24 = v134;
        v10 = v138;
        goto LABEL_127;
      }
      if ( !CloseHandle(v85) )
      {
        v129[0] = GetLastError();
        v35 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v86 = 539;
          goto LABEL_322;
        }
        goto LABEL_323;
      }
      VirtualDiskHandle = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v87 = *((_BYTE *)v32 + 326);
      v88 = *((_BYTE *)v32 + 325);
      v89 = *((_BYTE *)v32 + 327);
      v90 = *((_BYTE *)v32 + 324);
      v91 = *((_BYTE *)v32 + 323);
      v92 = *((_BYTE *)v32 + 322);
      v93 = *((_BYTE *)v32 + 321);
      v94 = *((_BYTE *)v32 + 320);
      v95 = *((_WORD *)v32 + 159);
      phkResulta = *((_WORD *)v32 + 158);
      v32 = v131;
      WPP_SF_DDDDDDDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        540,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        *((_DWORD *)v131 + 78),
        phkResulta,
        v95,
        v94,
        v93,
        v92,
        v91,
        v90,
        v88,
        v87,
        v89);
      v78 = Source1;
    }
    if ( !v78 )
      BlbAssert("base\\stor\\blb\\blbimg\\blbimg.cxx", 0x1FA0u, "ReplicationContext != NULL");
    *(_OWORD *)((char *)v32 + 328) = v78[3];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDDDDDDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        541,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        *((_DWORD *)v131 + 82),
        *((_WORD *)v32 + 166),
        *((_WORD *)v32 + 167),
        *((_BYTE *)v32 + 336),
        *((_BYTE *)v32 + 337),
        *((_BYTE *)v32 + 338),
        *((_BYTE *)v32 + 339),
        *((_BYTE *)v32 + 340),
        *((_BYTE *)v32 + 341),
        *((_BYTE *)v32 + 342),
        *((_BYTE *)v32 + 343));
      v78 = Source1;
    }
    appended = v148;
    LOBYTE(v133) = 1;
LABEL_349:
    v96 = v143;
    GetSystemTimeAsFileTime((LPFILETIME)(*((_QWORD *)v143 + 27) + 164LL + 368LL * *((unsigned int *)v143 + 93)));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v97 = *((_QWORD *)v96 + 27);
      v98 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v99 = 368LL * *((unsigned int *)v96 + 93);
      v167 = *(_QWORD *)(v99 + v97 + 156);
      v166 = *(_QWORD *)(v99 + v97 + 164);
      WPP_SF_q(v98, 542, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, (v166 - v167) / 0x2710uLL);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v96 + 88));
    v32 = v131;
    if ( v132 )
    {
      *((_BYTE *)v131 + 132) = 1;
      if ( !v130[0] )
        CBlbVolumeBackupContext::SetVolumeVolumeFlags(v32, 16);
    }
    if ( !v74 && v130[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 543, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      *((_QWORD *)v32 + 15) = *((_QWORD *)v96 + 49);
      *((_DWORD *)v32 + 32) = 0;
    }
    HIBYTE(v133) = 1;
    CBlbBackupAsync::UpdateBytes(v96, v150, v149);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v96 + 88));
    v10 = v138;
    *((_QWORD *)v138 + 4) = v149;
    *((_QWORD *)v10 + 3) = v150;
    switch ( v79 )
    {
      case 0u:
        v24 = v134;
LABEL_432:
        v11 = v143;
        CBlbAsync::LockedIncrement((CBlbBackupAsync *)((char *)v143 + 24), (unsigned int *)v32 + 4);
        *((_DWORD *)v10 + 10) = *((_DWORD *)v32 + 4);
        CBlbAsync::LockedIncrement((CBlbBackupAsync *)((char *)v11 + 24), (unsigned int *)v11 + 57);
        v106 = (UUID *)v156;
        v107 = Uuid;
        *((_DWORD *)v10 + 3) = *((_DWORD *)v11 + 57);
        v106[*((unsigned int *)v11 + 93)] = v107;
        if ( (*((_BYTE *)v11 + 340) & 2) == 0 )
        {
          v108 = CBlbVolumeBackupContext::PerformVHDCompaction(v32);
          if ( v108 < 0 )
          {
            CBlbVolumeBackupContext::SetResult(v32, -2139618991, v108);
            goto LABEL_126;
          }
        }
        if ( !(_BYTE)v133 )
        {
          if ( *((HLOCAL *)v10 + 7) != hMem )
            BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3288u, "pMediaCtxt->m_pBackupPtr == pBackupPtr");
          *((_QWORD *)v10 + 7) = 0;
          appended = -2139619280;
          *((_DWORD *)v10 + 16) = 0;
          v128 = 1;
          goto LABEL_126;
        }
        v131 = 0;
        if ( (unsigned int)BlbimgQueryUnreadableSize(v78) )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3296u, "r1 == BlbimgSuccess");
        v109 = v131;
        if ( v131 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v52 = *(unsigned __int16 **)&v129[1];
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              552,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              (_DWORD)v131,
              *(__int64 *)&v129[1]);
        }
        else
        {
          v52 = *(unsigned __int16 **)&v129[1];
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
        EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v32 + 26) + 88LL));
        v110 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v32 + 26) + 88LL);
        *((_QWORD *)v32 + 5) = v109;
        LeaveCriticalSection(v110);
        if ( (__int64)v109 > 0 )
          CBlbVolumeBackupContext::SetResult(v32, -2139619203, 0);
        CBlbVolumeBackupContext::SetState(v32, 14);
        CBlbMediaBackupContext::SetState(v10, 14);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
        if ( (*((_BYTE *)v11 + 340) & 2) == 0 )
          CBlbBackupAsync::DismountVHD(v11, v32);
        goto LABEL_451;
      case 1u:
        v11 = v96;
        appended = -2139618969;
        if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v96 + 3) + 16LL))((__int64)v96 + 24) )
          appended = *((_DWORD *)v96 + 8);
        v24 = v134;
        goto LABEL_126;
      case 4u:
LABEL_417:
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v52 = *(unsigned __int16 **)&v129[1];
        }
        else
        {
          v52 = *(unsigned __int16 **)&v129[1];
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_SLd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              544,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              v129[1],
              v79,
              v129[0]);
        }
        appended = BlbTranslateBlbimgError(v79, v129[0], &v135);
        if ( (*((_BYTE *)v32 + 84) & 1) == 0
          && (int)CBlbBackupAsync::IsSourceSnapshotDeleted(v144, &v130[2]) >= 0
          && !v130[2] )
        {
          appended = -2139618967;
        }
        v130[1] = 1;
LABEL_427:
        v24 = v134;
        v11 = v96;
        v35 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_128;
      case 5u:
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v52 = *(unsigned __int16 **)&v129[1];
        }
        else
        {
          v52 = *(unsigned __int16 **)&v129[1];
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_SLd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              545,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              v129[1],
              5,
              v129[0]);
        }
        v105 = BlbTranslateBlbimgError(5, v129[0], &v135);
        appended = v105;
        if ( !v135 )
        {
          v135 = v105;
          appended = -2139618970;
        }
        v128 = 1;
        goto LABEL_427;
      case 6u:
        goto LABEL_417;
    }
    if ( v79 != 7 )
    {
      if ( v79 == 20 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            546,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            v129[1],
            20,
            v129[0]);
        }
        v100 = BlbTranslateBlbimgError(20, v129[0], &v135);
        v128 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            551,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            v129[1],
            v79,
            v129[0]);
        }
        v100 = BlbTranslateBlbimgError(v79, v129[0], &v135);
      }
      v24 = v134;
      appended = v100;
      v11 = v96;
      goto LABEL_126;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SLd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        547,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        v129[1],
        7,
        v129[0]);
    }
    v101 = BlbTranslateBlbimgError(7, v129[0], &v135);
    HIBYTE(v133) = 0;
    appended = v101;
    if ( v101 != -2139619286 )
    {
      v24 = v134;
      if ( v101 < 0 )
        goto LABEL_406;
      goto LABEL_432;
    }
    if ( v129[0] != 112 )
    {
      v24 = v134;
LABEL_406:
      v11 = v143;
LABEL_407:
      v35 = (PVOID *)WPP_GLOBAL_Control;
LABEL_408:
      v128 = 1;
LABEL_127:
      v52 = *(unsigned __int16 **)&v129[1];
      goto LABEL_128;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v102 = v153;
    }
    else
    {
      v102 = v153;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 548, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v153);
    }
    v131 = 0;
    LODWORD(v148) = 0;
    v24 = v134;
    if ( v134 )
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3233u, "iNumVolumeRepeats == 0");
    IncrementalBackupFileSize = BlbimgGetIncrementalBackupFileSize(v78);
    v11 = v143;
    if ( IncrementalBackupFileSize )
      goto LABEL_407;
    v104 = CBlbBackupAsync::ReclaimTargetSpace(v143, (__int64)v131);
    if ( v104 < 0 )
    {
      v35 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(phkResult) = v104;
        WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v30, v131);
        goto LABEL_407;
      }
      goto LABEL_408;
    }
    appended = 0;
    v130[3] = 1;
    ++v24;
    v35 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_127;
    }
    v52 = *(unsigned __int16 **)&v129[1];
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      549,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      v129[1],
      (__int64)v102);
LABEL_451:
    v35 = (PVOID *)WPP_GLOBAL_Control;
LABEL_128:
    v53 = VirtualDiskHandle;
    if ( VirtualDiskHandle )
    {
      if ( DetachVirtualDisk(VirtualDiskHandle, DETACH_VIRTUAL_DISK_FLAG_NONE, 0)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 553, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      if ( !CloseHandle(v53) )
      {
        GetLastError();
        v35 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_140;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 554, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      v35 = (PVOID *)WPP_GLOBAL_Control;
LABEL_140:
      VirtualDiskHandle = 0;
    }
    if ( appended == -2139619280 || appended == -2139619286 && v129[0] == 112 )
      break;
LABEL_469:
    v113 = v52;
    if ( *((_QWORD *)v32 + 11) )
      v113 = (unsigned __int16 *)*((_QWORD *)v32 + 11);
    if ( appended >= 0 )
    {
      if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 1) != 0 && *((_BYTE *)v35 + 25) >= 4u )
        WPP_SF_S(v35[2], 560, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v52);
      if ( (int)CBlbBackupAsync::WriteVolumeBackupResultToLog(v11, v113, 1u, 0) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          561,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          v129[1],
          appended);
      }
    }
    else
    {
      CBlbMediaBackupContext::SetState(v10, 12);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          558,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v52,
          appended);
      }
      if ( (int)CBlbBackupAsync::WriteVolumeBackupResultToLog(v11, v113, 0, appended) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          559,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          v129[1],
          appended);
      }
      CBlbVolumeBackupContext::SetAborted(v32, appended, v135);
      if ( !v130[1] || v137[0] && *((_BYTE *)v32 + 104) )
      {
        IsClientSKU = appended;
        v16 = v139;
        v114 = v168;
        *v139 = v128;
        *v114 = v135;
LABEL_518:
        v9 = v142;
        goto LABEL_519;
      }
    }
    LOBYTE(v13) = v130[3];
    if ( !v130[3] )
      ++*((_DWORD *)v10 + 2);
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)v10 + 4) = 0;
    *((_DWORD *)v10 + 10) = 0;
    *((_DWORD *)v10 + 11) = 15;
    *((_QWORD *)v10 + 6) = 0;
    *((_QWORD *)v10 + 7) = 0;
    *((_DWORD *)v10 + 16) = 0;
  }
  if ( (*((_BYTE *)v11 + 340) & 2) == 0
    && (int)CBlbVolumeBackupContext::PerformVHDCompaction(v32) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 555, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  phkResult = (PHKEY)PublishBackupTargetFullEvent;
  v112 = BlbPublishVolumeEvent(*((_QWORD *)v11 + 43), *((unsigned int *)v11 + 84), v30, *((_QWORD *)v11 + 49));
  if ( v112 >= 0 )
  {
LABEL_465:
    v35 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v35 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        556,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        *((_QWORD *)v11 + 43),
        *((_QWORD *)v11 + 44),
        v112);
      goto LABEL_465;
    }
  }
  if ( appended != -2139619280 || (*((_BYTE *)v11 + 340) & 2) == 0 || *((_DWORD *)v10 + 3) <= *((_DWORD *)v142 + 3) )
    goto LABEL_469;
  CBlbMediaBackupContext::SetState(v10, 4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 557, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v52);
  }
  v26 = v141;
LABEL_502:
  IsClientSKU = CBlbBackupAsync::WriteBackupMetadata(v11, v139);
  if ( IsClientSKU < 0 )
  {
LABEL_517:
    v16 = v139;
    goto LABEL_518;
  }
  v115 = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)v11 + 40), 0);
  v9 = v142;
  IsClientSKU = v115;
  if ( v115 >= 0 )
  {
    v116 = *((_DWORD *)v142 + 3);
    v117 = 0;
    v118 = *(_QWORD *)GUID_NULL.Data4;
    v119 = *(_QWORD *)&GUID_NULL.Data1;
    v120 = (char *)v156;
    while ( v117 < v26 )
    {
      v121 = (struct _GUID *)&v120[16 * v117];
      v122 = *(_QWORD *)&v121->Data1 - v119;
      if ( *(_QWORD *)&v121->Data1 == v119 )
        v122 = *(_QWORD *)v121->Data4 - v118;
      if ( v122 )
      {
        IsClientSKU = CBlbBackupAsync::AddBagToLocalCatalog(
                        v11,
                        v121,
                        v116,
                        (struct _GUID *)(*((_QWORD *)v11 + 27) + 368LL * v117 + 68),
                        *(_DWORD *)(*((_QWORD *)v11 + 27) + 368LL * v117 + 84),
                        v169,
                        (unsigned __int8 *)pv + 16 * v117,
                        (struct _FILETIME *)(*((_QWORD *)v11 + 27) + 368LL * v117 + 120),
                        *(_DWORD *)(*((_QWORD *)v11 + 27) + 368LL * v117 + 128));
        if ( IsClientSKU < 0 )
          goto LABEL_514;
        v118 = *(_QWORD *)GUID_NULL.Data4;
        ++v116;
        v119 = *(_QWORD *)&GUID_NULL.Data1;
      }
      ++v117;
    }
    if ( v116 != *((_DWORD *)v138 + 3) )
    {
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3367u, "j == pMediaCtxt->m_ulBagCount");
LABEL_514:
      v10 = v138;
      goto LABEL_515;
    }
    v10 = v138;
  }
LABEL_515:
  v16 = v139;
LABEL_519:
  if ( Path )
    CoTaskMemFree((LPVOID)Path);
  v13 = Source1;
  v12 = v144;
LABEL_13:
  if ( hMem && hMem != *((HLOCAL *)v10 + 7) && hMem != *((HLOCAL *)v9 + 7) )
    LocalFree(hMem);
  if ( v13 && v13 != *((void **)v10 + 6) && v13 != *((void **)v9 + 6) )
    BlbimgFreeContext(v13);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v156 )
    CoTaskMemFree(v156);
  if ( v153 )
    CoTaskMemFree(v153);
  CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v11 + 40));
  if ( IsClientSKU >= 0 )
    goto LABEL_529;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = (const char *)&qword_14013EAA0;
    if ( !*v16 )
      v19 = "no";
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"no", v17, IsClientSKU, (__int64)v19);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( HIBYTE(v133) || (*((_BYTE *)v11 + 340) & 4) == 0 )
    goto LABEL_530;
  if ( (int)CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)v11 + 40), 0) >= 0 )
  {
    if ( (int)CBlbBackupAsync::RevertBackupSetDirectory(v11) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 564, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v11 + 40));
LABEL_529:
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_530;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 563, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      goto LABEL_529;
    }
LABEL_530:
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 4u )
      WPP_SF_(v18[2], 565, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x1400170c8  push    rbp
0x1400170ca  push    rbx
0x1400170cb  push    rsi
0x1400170cc  push    rdi
0x1400170cd  push    r12
0x1400170cf  push    r13
0x1400170d1  push    r14
0x1400170d3  push    r15
0x1400170d5  lea     rbp, [rsp-108h]
0x1400170dd  sub     rsp, 208h
0x1400170e4  mov     rax, cs:__security_cookie
0x1400170eb  xor     rax, rsp
0x1400170ee  mov     [rbp+140h+var_50], rax
0x1400170f5  mov     rax, [rbp+140h+arg_38]
0x1400170fc  mov     ebx, r9d
0x1400170ff  mov     r13, [rbp+140h+arg_20]
0x140017106  xorps   xmm0, xmm0
0x140017109  mov     rsi, [rbp+140h+arg_28]
0x140017110  mov     r12, rcx
0x140017113  mov     rdi, [rbp+140h+arg_30]
0x14001711a  mov     [rbp+140h+var_B0], rax
0x140017121  xor     eax, eax
0x140017123  mov     [rbp+140h+var_158], eax
0x140017126  mov     r15d, eax
0x140017129  mov     [rbp+140h+var_1A8], eax
0x14001712c  mov     r14d, eax
0x14001712f  mov     [rbp+140h+var_128], rax
0x140017133  mov     [rbp+140h+var_110], rax
0x140017137  mov     [rbp+140h+pv], rax
0x14001713b  mov     [rbp+140h+var_170], rax
0x14001713f  mov     [rbp+140h+Source1], rax
0x140017143  mov     [rbp+140h+hMem], rax
0x140017147  mov     [rbp+140h+var_E8], rax
0x14001714b  mov     [rbp+140h+var_140], rax
0x14001714f  mov     [rbp+140h+var_148], rax
0x140017153  mov     dword ptr [rsp+240h+var_1CC], eax
0x140017157  mov     [rbp+140h+Path], rax
0x14001715b  mov     [rbp+140h+var_D0], rax
0x14001715f  mov     [rbp+140h+var_160], rax
0x140017163  mov     byte ptr [rbp+140h+var_1B0+2], al
0x140017166  mov     byte ptr [rbp+140h+var_1B0+1], al
0x140017169  mov     byte ptr [rbp+140h+var_1B0], al
0x14001716c  mov     [rbp+140h+var_1A3], al
0x14001716f  mov     [rbp+140h+var_1C0+2], al
0x140017172  mov     [rbp+140h+var_C8], rax
0x140017176  mov     [rbp+140h+VirtualDiskHandle], rax
0x14001717a  mov     [rbp+140h+var_188], ebx
0x14001717d  mov     [rbp+140h+var_F8], r8
0x140017181  mov     [rbp+140h+var_A8], rdx
0x140017188  mov     [rbp+140h+var_178], rcx
0x14001718c  mov     [rbp+140h+var_180], r13
0x140017190  mov     [rbp+140h+var_1A0], rsi
0x140017194  mov     [rbp+140h+var_198], rdi
0x140017198  movups  xmmword ptr [rbp+140h+Uuid.Data1], xmm0
0x14001719f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171a6  lea     rax, WPP_GLOBAL_Control
0x1400171ad  cmp     rcx, rax
0x1400171b0  jz      short loc_1400171D3
0x1400171b2  test    byte ptr [rcx+1Ch], 1
0x1400171b6  jz      short loc_1400171D3
0x1400171b8  cmp     byte ptr [rcx+19h], 4
0x1400171bc  jb      short loc_1400171D3
0x1400171be  mov     rcx, [rcx+10h]
0x1400171c2  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400171c9  mov     edx, 1FCh
0x1400171ce  call    WPP_SF_
0x1400171d3  cmp     ebx, [r12+170h]
0x1400171db  jz      short loc_1400171F5
0x1400171dd  lea     r8, aCvolumenameMCv; "cVolumeName == m_cVolume"
0x1400171e4  mov     edx, 2EF8h; unsigned int
0x1400171e9  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400171f0  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400171f5  mov     rax, [rbp+140h+var_B0]
0x1400171fc  lea     rbx, [r12+0E0h]
0x140017204  mov     [rdi], r14b
0x140017207  lea     rcx, [r12+18h]; this
0x14001720c  mov     rdx, rbx; unsigned int *
0x14001720f  mov     [rax], r14d
0x140017212  call    ?LockedIncrement@CBlbAsync@@QEAAXAEAK@Z; CBlbAsync::LockedIncrement(ulong &)
0x140017217  mov     eax, [rbx]
0x140017219  lea     rcx, [rbp+140h+var_1A3]; unsigned __int8 *
0x14001721d  mov     [rsi+10h], eax
0x140017220  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x140017225  mov     edi, eax
0x140017227  test    eax, eax
0x140017229  jns     loc_1400173AE
0x14001722f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017236  lea     rax, WPP_GLOBAL_Control
0x14001723d  cmp     rcx, rax
0x140017240  jz      short loc_140017266
0x140017242  test    byte ptr [rcx+1Ch], 1
0x140017246  jz      short loc_140017266
0x140017248  cmp     byte ptr [rcx+19h], 2
0x14001724c  jb      short loc_140017266
0x14001724e  mov     rcx, [rcx+10h]
0x140017252  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140017259  mov     edx, 1FDh
0x14001725e  mov     r9d, edi
0x140017261  call    WPP_SF_d
0x140017266  mov     rbx, [rbp+140h+var_198]
0x14001726a  mov     rcx, [rbp+140h+hMem]; hMem
0x14001726e  test    rcx, rcx
0x140017271  jz      short loc_140017285
0x140017273  cmp     rcx, [rsi+38h]
0x140017277  jz      short loc_140017285
0x140017279  cmp     rcx, [r13+38h]
0x14001727d  jz      short loc_140017285
0x14001727f  call    cs:__imp_LocalFree
0x140017285  test    r14, r14
0x140017288  jz      short loc_14001729E
0x14001728a  cmp     r14, [rsi+30h]
0x14001728e  jz      short loc_14001729E
0x140017290  cmp     r14, [r13+30h]
0x140017294  jz      short loc_14001729E
0x140017296  mov     rcx, r14; hMem
0x140017299  call    BlbimgFreeContext
0x14001729e  test    r15, r15
0x1400172a1  jz      short loc_1400172AC
0x1400172a3  mov     rcx, r15; pv
0x1400172a6  call    cs:__imp_CoTaskMemFree
0x1400172ac  mov     rax, [rbp+140h+pv]
0x1400172b0  test    rax, rax
0x1400172b3  jz      short loc_1400172BE
0x1400172b5  mov     rcx, rax; pv
0x1400172b8  call    cs:__imp_CoTaskMemFree
0x1400172be  mov     rax, [rbp+140h+var_110]
0x1400172c2  test    rax, rax
0x1400172c5  jz      short loc_1400172D0
0x1400172c7  mov     rcx, rax; pv
0x1400172ca  call    cs:__imp_CoTaskMemFree
0x1400172d0  mov     rax, [rbp+140h+var_128]
0x1400172d4  test    rax, rax
0x1400172d7  jz      short loc_1400172E2
0x1400172d9  mov     rcx, rax; pv
0x1400172dc  call    cs:__imp_CoTaskMemFree
0x1400172e2  lea     rcx, [r12+28h]; this
0x1400172e7  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x1400172ec  test    edi, edi
0x1400172ee  jns     loc_1400195BF
0x1400172f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172fb  lea     rsi, WPP_GLOBAL_Control
0x140017302  cmp     rcx, rsi
0x140017305  jz      short loc_140017340
0x140017307  test    byte ptr [rcx+1Ch], 1
0x14001730b  jz      short loc_140017340
0x14001730d  cmp     byte ptr [rcx+19h], 2
0x140017311  jb      short loc_140017340
0x140017313  cmp     byte ptr [rbx], 0
0x140017316  lea     rdx, aNo; "no"
0x14001731d  mov     rcx, [rcx+10h]
0x140017321  lea     rax, qword_14013EAA0
0x140017328  cmovz   rax, rdx
0x14001732c  mov     r9d, edi
0x14001732f  mov     [rsp+240h+phkResult], rax
0x140017334  call    WPP_SF_Ls
0x140017339  mov     rcx, cs:WPP_GLOBAL_Control
0x140017340  cmp     byte ptr [rbp+140h+var_1B0+2], 0
0x140017344  jnz     loc_1400195CD
0x14001734a  test    byte ptr [r12+154h], 4
0x140017353  jz      loc_1400195CD
0x140017359  lea     rcx, [r12+28h]; this
0x14001735e  xor     edx, edx; unsigned __int8
0x140017360  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140017365  test    eax, eax
0x140017367  jns     loc_140019577
0x14001736d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017374  cmp     rcx, rsi
0x140017377  jz      loc_1400195F3
0x14001737d  test    byte ptr [rcx+1Ch], 1
0x140017381  jz      loc_1400195CD
0x140017387  cmp     byte ptr [rcx+19h], 2
0x14001738b  jb      loc_1400195CD
0x140017391  mov     rcx, [rcx+10h]
0x140017395  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001739c  mov     edx, 233h
0x1400173a1  mov     r9d, eax
0x1400173a4  call    WPP_SF_d
0x1400173a9  jmp     loc_1400195C6
0x1400173ae  mov     rcx, [r12+158h]; unsigned __int16 *
0x1400173b6  lea     r8, [rbp+140h+var_128]; unsigned __int16 **
0x1400173ba  lea     rdx, asc_14013C090; "\\"
0x1400173c1  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400173c6  mov     edi, eax
0x1400173c8  test    eax, eax
0x1400173ca  js      loc_140017266
0x1400173d0  mov     ebx, [rbp+140h+var_188]
0x1400173d3  shl     rbx, 4
0x1400173d7  mov     rcx, rbx; cb
0x1400173da  call    cs:__imp_CoTaskMemAlloc
0x1400173e0  mov     [rbp+140h+var_110], rax
0x1400173e4  test    rax, rax
0x1400173e7  jnz     short loc_1400173F3
0x1400173e9  mov     edi, 8007000Eh
0x1400173ee  jmp     loc_140017266
0x1400173f3  mov     r8, rbx; Size
0x1400173f6  xor     edx, edx; Val
0x1400173f8  mov     rcx, rax; void *
0x1400173fb  call    memset_0
0x140017400  mov     eax, [rbp+140h+var_188]
0x140017403  shl     eax, 4
0x140017406  mov     ecx, eax; cb
0x140017408  mov     ebx, eax
0x14001740a  call    cs:__imp_CoTaskMemAlloc
0x140017410  mov     [rbp+140h+pv], rax
0x140017414  test    rax, rax
0x140017417  jz      short loc_1400173E9
0x140017419  xor     r13d, r13d
0x14001741c  mov     [rbp+140h+var_F0], r14
0x140017420  mov     r8d, ebx; Size
0x140017423  xor     edx, edx; Val
0x140017425  mov     rcx, rax; void *
0x140017428  call    memset_0
0x14001742d  mov     r8d, [rsi+8]; unsigned int
0x140017431  mov     r15d, [rbp+140h+var_188]
0x140017435  cmp     r8d, r15d
0x140017438  jnb     loc_140019432
0x14001743e  neg     r14b
0x140017441  mov     [rsp+240h+var_1D0], 0
0x140017446  lea     r15, [r12+174h]
0x14001744e  mov     [rbp+140h+var_1C0+1], 0
0x140017452  sbb     eax, eax
0x140017454  lea     rcx, [r12+18h]; this
0x140017459  and     eax, r13d
0x14001745c  mov     rdx, r15; unsigned int *
0x14001745f  mov     r13d, eax
0x140017462  mov     dword ptr [rbp+140h+var_1B0+4], eax
0x140017465  xor     al, al
0x140017467  imul    rbx, r8, 170h
0x14001746e  mov     [rbp+140h+var_1C0+3], al
0x140017471  mov     rax, [rbp+140h+var_F8]
0x140017475  add     rbx, [r12+0D8h]
0x14001747d  mov     [rbp+140h+var_1B8], rbx
0x140017481  mov     r14, [rax+r8*8]
0x140017485  mov     qword ptr [rsp+240h+var_1CC+4], r14
0x14001748a  call    ?LockedSet@CBlbAsync@@QEAAXAEAKK@Z; CBlbAsync::LockedSet(ulong &,ulong)
0x14001748f  lea     rcx, [rbp+140h+Uuid]; Uuid
0x140017496  call    cs:__imp_UuidCreate
0x14001749c  test    byte ptr [rbx+54h], 1
0x1400174a0  jz      short loc_1400174C9
0x1400174a2  mov     ecx, [rsi+8]
0x1400174a5  lea     rdx, [rbp+140h+var_170]; unsigned __int16 **
0x1400174a9  mov     rax, [rbp+140h+var_F8]
0x1400174ad  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x1400174b1  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x1400174b6  mov     r14d, eax
0x1400174b9  test    eax, eax
0x1400174bb  jns     loc_140017601
0x1400174c1  mov     r15, rbx
0x1400174c4  jmp     loc_1400179B8
0x1400174c9  mov     rdx, [r12+1B0h]
0x1400174d1  xor     ebx, ebx
0x1400174d3  cmp     [rdx+50h], ebx
0x1400174d6  jbe     short loc_14001750A
0x1400174d8  mov     eax, ebx
0x1400174da  imul    rsi, rax, 38h ; '8'
0x1400174de  add     rsi, [rdx+58h]
0x1400174e2  mov     rdx, r14; String2
0x1400174e5  mov     [rbp+140h+var_F0], rsi
0x1400174e9  mov     rcx, [rsi+10h]; String1
0x1400174ed  call    cs:__imp__wcsicmp
0x1400174f3  test    eax, eax
0x1400174f5  jz      short loc_140017506
0x1400174f7  mov     rdx, [r12+1B0h]
0x1400174ff  inc     ebx
0x140017501  cmp     ebx, [rdx+50h]
0x140017504  jb      short loc_1400174D8
0x140017506  mov     rsi, [rbp+140h+var_1A0]
0x14001750a  mov     rax, [r12+1B0h]
0x140017512  cmp     ebx, [rax+50h]
0x140017515  jnz     short loc_140017573
0x140017517  mov     r15, [rbp+140h+var_1B8]
0x14001751b  mov     r14d, [r15+20h]
0x14001751f  test    r14d, r14d
0x140017522  js      short loc_140017563
0x140017524  mov     r14d, 80780020h
0x14001752a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017531  lea     rax, WPP_GLOBAL_Control
0x140017538  cmp     rcx, rax
0x14001753b  jz      short loc_14001756A
0x14001753d  test    byte ptr [rcx+1Ch], 1
0x140017541  jz      short loc_14001756A
0x140017543  cmp     byte ptr [rcx+19h], 2
0x140017547  jb      short loc_14001756A
0x140017549  mov     r9, qword ptr [rsp+240h+var_1CC+4]
0x14001754e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140017555  mov     rcx, [rcx+10h]
0x140017559  mov     edx, 1FEh
0x14001755e  call    WPP_SF_S
0x140017563  mov     rcx, cs:WPP_GLOBAL_Control
0x14001756a  mov     [rbp+140h+var_1C0+1], 1
0x14001756e  jmp     loc_1400179BF
0x140017573  mov     rax, [rbp+140h+var_170]
0x140017577  test    rax, rax
0x14001757a  jz      short loc_14001758B
0x14001757c  mov     rcx, rax; pv
0x14001757f  call    cs:__imp_CoTaskMemFree
0x140017585  xor     eax, eax
0x140017587  mov     [rbp+140h+var_170], rax
0x14001758b  mov     rax, [rbp+140h+var_F0]
0x14001758f  mov     rcx, [rax+18h]; unsigned __int16 *
  ... truncated ...
```
