# FInterrogateLogin(SNI_Conn *,int *,AutoHANDLE &,int *,CSECCertificate &,wchar_t *,ulong &,uchar *,ulong &,wchar_t *,ulong &,wchar_t *,ulong &,bool *)

- ea: `0x1005597d0`
- end: `0x100559a43`
- name: `?FInterrogateLogin@@YAHPEAVSNI_Conn@@PEAHAEAVAutoHANDLE@@1AEAVCSECCertificate@@PEA_WAEAKPEAE54545PEA_N@Z`
- size: `627`
- prototype: `__int64 __fastcall(struct SNI_Conn *, int *, struct AutoHANDLE *, int *, struct CSECCertificate *, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *, wchar_t *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x100556ce0`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401400`
- `0x100401433`
- `0x100403080`
- `0x1004076a0`
- `0x10041e190`
- `0x100430960`
- `0x100430d60`
- `0x1005597d0`
- `0x100559a50`
- `0x10058c1a0`
- `0x100754350`
- `0x100a23310`
- `0x1014bb3b0`
- `0x1014c1760`
- `0x10151c240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10058c15e`
- `KERNEL32!GetLastError` at `0x101453b2b`
- `KERNEL32!GetLastError` at `0x101453ddc`
- `KERNEL32!GetLastError` at `0x101454266`
- `KERNEL32!GetLastError` at `0x1014542c2`
- `KERNEL32!GetLastError` at `0x10058c15e`
- `KERNEL32!GetLastError` at `0x101453b2b`
- `KERNEL32!GetLastError` at `0x101453ddc`
- `KERNEL32!GetLastError` at `0x101454266`
- `KERNEL32!GetLastError` at `0x1014542c2`
- `KERNEL32!CloseHandle` at `0x10058ad0c`
- `KERNEL32!CloseHandle` at `0x10058ad0c`
- `KERNEL32!QueryPerformanceCounter` at `0x10058b65b`
- `KERNEL32!QueryPerformanceCounter` at `0x10058b727`
- `KERNEL32!QueryPerformanceCounter` at `0x1014538ae`
- `KERNEL32!QueryPerformanceCounter` at `0x1014538bb`
- `KERNEL32!QueryPerformanceCounter` at `0x101453a54`
- `KERNEL32!QueryPerformanceCounter` at `0x101453a7d`
- `KERNEL32!QueryPerformanceCounter` at `0x101453abb`
- `KERNEL32!QueryPerformanceCounter` at `0x101453ae9`
- `KERNEL32!QueryPerformanceCounter` at `0x101453c1f`
- `KERNEL32!QueryPerformanceCounter` at `0x101453c4d`
- `KERNEL32!QueryPerformanceCounter` at `0x101453eab`
- `KERNEL32!QueryPerformanceCounter` at `0x101453ed9`
- `KERNEL32!QueryPerformanceCounter` at `0x10145420b`
- `KERNEL32!QueryPerformanceCounter` at `0x101454239`
- `KERNEL32!QueryPerformanceCounter` at `0x10058b65b`
- `KERNEL32!QueryPerformanceCounter` at `0x10058b727`
- `KERNEL32!QueryPerformanceCounter` at `0x1014538ae`
- `KERNEL32!QueryPerformanceCounter` at `0x1014538bb`
- `KERNEL32!QueryPerformanceCounter` at `0x101453a54`
- `KERNEL32!QueryPerformanceCounter` at `0x101453a7d`
- `KERNEL32!QueryPerformanceCounter` at `0x101453abb`
- `KERNEL32!QueryPerformanceCounter` at `0x101453ae9`
- `KERNEL32!QueryPerformanceCounter` at `0x101453c1f`
- `KERNEL32!QueryPerformanceCounter` at `0x101453c4d`
- `KERNEL32!QueryPerformanceCounter` at `0x101453eab`
- `KERNEL32!QueryPerformanceCounter` at `0x101453ed9`
- `KERNEL32!QueryPerformanceCounter` at `0x10145420b`
- `KERNEL32!QueryPerformanceCounter` at `0x101454239`
- `KERNEL32!GetCurrentThread` at `0x10058c0ab`
- `KERNEL32!GetCurrentThread` at `0x10058c0ab`
- `ADVAPI32!DuplicateTokenEx` at `0x10058b5b6`
- `ADVAPI32!DuplicateTokenEx` at `0x1014542b4`
- `ADVAPI32!DuplicateTokenEx` at `0x10058b5b6`
- `ADVAPI32!DuplicateTokenEx` at `0x1014542b4`
- `ADVAPI32!LookupAccountSidW` at `0x101453dcf`
- `ADVAPI32!LookupAccountSidW` at `0x101453dcf`
- `ADVAPI32!GetLengthSid` at `0x10058b534`
- `ADVAPI32!GetLengthSid` at `0x10058b534`
- `ADVAPI32!GetTokenInformation` at `0x10058c0fc`
- `ADVAPI32!GetTokenInformation` at `0x10058c14d`
- `ADVAPI32!GetTokenInformation` at `0x10058c0fc`
- `ADVAPI32!GetTokenInformation` at `0x10058c14d`
- `ADVAPI32!OpenThreadToken` at `0x10058c0c3`
- `ADVAPI32!OpenThreadToken` at `0x10058c0c3`
- `secforwarder!CertNameToStrW` at `0x1014539fb`
- `secforwarder!CertNameToStrW` at `0x1014539fb`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1005599b8`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10058ab08`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10058b683`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10058b74f`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1005599bf`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10058ab0f`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1005599bf`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10058ab0f`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10058b46d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101453f24`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10058b46d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101453f24`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101453f0f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101453f0f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10058abea`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10058b2af`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101453d1b`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101454029`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10058abea`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10058b2af`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101453d1b`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101454029`
- `sqldk!SystemThread_TlsIndex` at `0x100559895`
- `sqldk!SystemThread_TlsIndex` at `0x10058aba8`
- `sqldk!SystemThread_TlsIndex` at `0x10058ac02`
- `sqldk!SystemThread_TlsIndex` at `0x10058b276`
- `sqldk!SystemThread_TlsIndex` at `0x10058b2c7`
- `sqldk!SystemThread_TlsIndex` at `0x101453cd7`
- `sqldk!SystemThread_TlsIndex` at `0x101453d33`
- `sqldk!SystemThread_TlsIndex` at `0x101453fe5`
- `sqldk!SystemThread_TlsIndex` at `0x101454041`
- `sqldk!SystemThread_TlsOffset` at `0x10055989e`
- `sqldk!SystemThread_TlsOffset` at `0x10058abb1`
- `sqldk!SystemThread_TlsOffset` at `0x10058ac0b`
- `sqldk!SystemThread_TlsOffset` at `0x10058b27f`
- `sqldk!SystemThread_TlsOffset` at `0x10058b2d0`
- `sqldk!SystemThread_TlsOffset` at `0x101453ce0`
- `sqldk!SystemThread_TlsOffset` at `0x101453d3c`
- `sqldk!SystemThread_TlsOffset` at `0x101453fee`
- `sqldk!SystemThread_TlsOffset` at `0x10145404a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10058abca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10058ac26`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453af7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453b0c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453cfb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453d57`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101454009`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101454065`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10058abca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10058ac26`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453af7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453b0c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453cfb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101453d57`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101454009`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101454065`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145398b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014539c2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10145398b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014539c2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101453f5b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101453f84`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101453f5b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101453f84`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101453f6a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101453f6a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10058ac99`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10058ac99`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x101453f42`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x101453f42`

## string_xrefs

- `0x101453ef4`: `sql\ntdbms\msql\security\src\seclogin.cpp`
- `0x10058c17b`: `GetTokenInformation`
- `0x101453e88`: `LookupAccountSid`
- `0x101454283`: `DuplicateTokenEx`
- `0x1014542df`: `DuplicateTokenEx`
- `0x101453b48`: `OpenThreadToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
_BOOL8 __fastcall FInterrogateLogin(
        struct SNI_Conn *a1,
        int *a2,
        struct AutoHANDLE *a3,
        int *a4,
        struct CSECCertificate *a5,
        wchar_t *a6,
        unsigned int *a7,
        unsigned __int8 *a8,
        unsigned int *a9,
        wchar_t *a10,
        unsigned int *a11,
        wchar_t *a12,
        unsigned int *a13,
        bool *a14)
{
  __int64 v15; // r15
  BOOL v16; // r12d
  __int64 v17; // rax
  int v18; // edx
  bool v19; // r13
  int v20; // ecx
  BOOL v21; // r14d
  __int64 v22; // rax
  __int64 v23; // rdi
  char v24; // si
  LONGLONG v25; // r15
  LONGLONG v26; // r14
  char v27; // r13
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rdx
  char *v34; // r8
  __int64 v35; // rsi
  __int64 v36; // rdi
  LPWSTR v37; // rdi
  __int64 v38; // rdx
  void *v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rbx
  __int64 v44; // rdx
  __int64 v45; // rax
  unsigned int v46; // eax
  unsigned int v47; // eax
  __int64 v48; // rdi
  __int64 v49; // rax
  LONGLONG v50; // rsi
  void *v51; // rbx
  LPWSTR v52; // r13
  LONGLONG v53; // rdi
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v55; // eax
  unsigned __int64 v56; // r13
  __int64 v57; // rbx
  __int16 v58; // bx
  size_t v59; // r8
  const void *const *v60; // rbx
  DWORD LengthSid; // eax
  unsigned int v62; // r8d
  LONGLONG v63; // rbx
  LONGLONG v64; // rdx
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // rax
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // rax
  unsigned __int64 v69; // rax
  unsigned __int64 v70; // rax
  LONGLONG v71; // rdx
  HANDLE CurrentThread; // rax
  unsigned __int64 v73; // r9
  __int64 v74; // rcx
  unsigned __int64 v75; // rcx
  void *v76; // rsp
  void *v77; // rsp
  DWORD v78; // eax
  __int64 v79; // rax
  __int64 v80; // r8
  DWORD LastError; // eax
  PSID *v82; // rdi
  __int64 v83; // rbx
  __int64 v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rbx
  __int64 v87; // rdx
  __crt_locale_pointers *v88; // rax
  __int64 v89; // rbx
  __int64 v90; // rax
  __int64 v91; // rcx
  __int64 v92; // rbx
  __int64 v93; // rdx
  unsigned int *v94; // rbx
  int v95; // eax
  DWORD v96; // eax
  DWORD v97; // eax
  PHANDLE phNewToken; // [rsp+28h] [rbp-18h]
  PSID_NAME_USE peUse; // [rsp+30h] [rbp-10h]
  char TokenInformation; // [rsp+40h] [rbp+0h] BYREF
  char v101; // [rsp+41h] [rbp+1h]
  int v102; // [rsp+44h] [rbp+4h]
  BOOL v103; // [rsp+48h] [rbp+8h]
  unsigned int v104; // [rsp+4Ch] [rbp+Ch]
  unsigned int v105; // [rsp+50h] [rbp+10h]
  void *Destination; // [rsp+58h] [rbp+18h]
  LPWSTR ReferencedDomainName; // [rsp+60h] [rbp+20h]
  HANDLE hObject; // [rsp+68h] [rbp+28h]
  PSID pSid; // [rsp+70h] [rbp+30h]
  int *v110; // [rsp+78h] [rbp+38h]
  int *v111; // [rsp+80h] [rbp+40h]
  PSID *p_TokenInformation; // [rsp+88h] [rbp+48h]
  bool *v113; // [rsp+90h] [rbp+50h]
  struct CSession *v114; // [rsp+98h] [rbp+58h]
  unsigned int *v115; // [rsp+A0h] [rbp+60h]
  LPWSTR psz; // [rsp+A8h] [rbp+68h]
  unsigned int *v117; // [rsp+B0h] [rbp+70h]
  unsigned int *v118; // [rsp+B8h] [rbp+78h]
  int *v119; // [rsp+C0h] [rbp+80h]
  int *v120; // [rsp+C8h] [rbp+88h]
  BYTE *v121; // [rsp+D0h] [rbp+90h] BYREF
  DWORD v122; // [rsp+D8h] [rbp+98h]
  wchar_t *String1; // [rsp+E0h] [rbp+A0h]
  LARGE_INTEGER v124; // [rsp+E8h] [rbp+A8h] BYREF
  struct AutoHANDLE *v125; // [rsp+F0h] [rbp+B0h]
  int *v126; // [rsp+F8h] [rbp+B8h]
  LARGE_INTEGER PerformanceCount; // [rsp+100h] [rbp+C0h] BYREF
  LARGE_INTEGER v128; // [rsp+110h] [rbp+D0h] BYREF
  LARGE_INTEGER v129; // [rsp+118h] [rbp+D8h] BYREF
  LARGE_INTEGER v130; // [rsp+120h] [rbp+E0h] BYREF
  LARGE_INTEGER v131; // [rsp+128h] [rbp+E8h] BYREF
  unsigned int *v132; // [rsp+130h] [rbp+F0h]
  LARGE_INTEGER v133; // [rsp+138h] [rbp+F8h] BYREF
  __int64 v134; // [rsp+140h] [rbp+100h]
  LONGLONG v135; // [rsp+148h] [rbp+108h]
  _BYTE v136[24]; // [rsp+150h] [rbp+110h] BYREF
  void *v137; // [rsp+168h] [rbp+128h]
  _BYTE v138[24]; // [rsp+178h] [rbp+138h] BYREF
  void *v139; // [rsp+190h] [rbp+150h]
  DWORD ReturnLength; // [rsp+1A0h] [rbp+160h] BYREF
  void *v141; // [rsp+1A8h] [rbp+168h] BYREF
  HANDLE hExistingToken; // [rsp+1B0h] [rbp+170h] BYREF
  __int64 v143; // [rsp+1B8h] [rbp+178h] BYREF
  void *Source; // [rsp+1C0h] [rbp+180h] BYREF
  struct _CRYPTOAPI_BLOB pName; // [rsp+1C8h] [rbp+188h] BYREF
  __int64 v146; // [rsp+1D8h] [rbp+198h] BYREF
  LARGE_INTEGER v147; // [rsp+1E8h] [rbp+1A8h] BYREF
  DWORD cchName; // [rsp+1F0h] [rbp+1B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+1F4h] [rbp+1B4h] BYREF
  int v150; // [rsp+1F8h] [rbp+1B8h] BYREF
  int v151; // [rsp+200h] [rbp+1C0h] BYREF
  __int64 v152; // [rsp+208h] [rbp+1C8h]
  int v153; // [rsp+210h] [rbp+1D0h] BYREF
  int v154; // [rsp+214h] [rbp+1D4h]
  __int64 v155; // [rsp+218h] [rbp+1D8h]
  int v156; // [rsp+220h] [rbp+1E0h] BYREF
  __int64 v157; // [rsp+228h] [rbp+1E8h]
  __int64 v158; // [rsp+230h] [rbp+1F0h]
  __int64 v159; // [rsp+238h] [rbp+1F8h]
  __int64 v160; // [rsp+240h] [rbp+200h]
  bool v161; // [rsp+250h] [rbp+210h]
  int v162; // [rsp+260h] [rbp+220h] BYREF
  __int64 v163; // [rsp+268h] [rbp+228h]
  int v164; // [rsp+270h] [rbp+230h] BYREF
  int v165; // [rsp+274h] [rbp+234h]
  __int64 v166; // [rsp+278h] [rbp+238h]
  int v167; // [rsp+280h] [rbp+240h] BYREF
  __int64 v168; // [rsp+288h] [rbp+248h]
  __int64 v169; // [rsp+290h] [rbp+250h]
  __int64 v170; // [rsp+298h] [rbp+258h]
  __int64 v171; // [rsp+2A0h] [rbp+260h]
  bool v172; // [rsp+2B0h] [rbp+270h]
  enum _SID_NAME_USE v173; // [rsp+2C0h] [rbp+280h] BYREF
  LARGE_INTEGER v174; // [rsp+2C8h] [rbp+288h] BYREF
  _BYTE v175[16]; // [rsp+2D0h] [rbp+290h] BYREF
  int v176; // [rsp+2E0h] [rbp+2A0h] BYREF
  __int64 v177; // [rsp+2E8h] [rbp+2A8h]
  int v178; // [rsp+2F0h] [rbp+2B0h] BYREF
  int v179; // [rsp+2F4h] [rbp+2B4h]
  __int64 v180; // [rsp+2F8h] [rbp+2B8h]
  int v181; // [rsp+300h] [rbp+2C0h] BYREF
  __int64 v182; // [rsp+308h] [rbp+2C8h]
  __int64 v183; // [rsp+310h] [rbp+2D0h]
  __int64 v184; // [rsp+318h] [rbp+2D8h]
  __int64 v185; // [rsp+320h] [rbp+2E0h]
  bool v186; // [rsp+330h] [rbp+2F0h]
  int v187; // [rsp+340h] [rbp+300h] BYREF
  __int64 v188; // [rsp+348h] [rbp+308h]
  int v189; // [rsp+350h] [rbp+310h] BYREF
  int v190; // [rsp+354h] [rbp+314h]
  __int64 v191; // [rsp+358h] [rbp+318h]
  int v192; // [rsp+360h] [rbp+320h] BYREF
  __int64 v193; // [rsp+368h] [rbp+328h]
  __int64 v194; // [rsp+370h] [rbp+330h]
  __int64 v195; // [rsp+378h] [rbp+338h]
  __int64 v196; // [rsp+380h] [rbp+340h]
  bool v197; // [rsp+390h] [rbp+350h]
  _BYTE v198[8]; // [rsp+3A0h] [rbp+360h] BYREF
  int v199; // [rsp+3A8h] [rbp+368h]
  int v200; // [rsp+3B0h] [rbp+370h]
  _QWORD *v201; // [rsp+3B8h] [rbp+378h]
  char *v202; // [rsp+3C0h] [rbp+380h]
  __int64 v203; // [rsp+3C8h] [rbp+388h]
  _QWORD v204[2]; // [rsp+3D0h] [rbp+390h] BYREF
  char v205; // [rsp+3E0h] [rbp+3A0h] BYREF
  __int64 v206; // [rsp+5F0h] [rbp+5B0h]
  __int64 v207; // [rsp+5F8h] [rbp+5B8h]
  unsigned __int64 v208; // [rsp+600h] [rbp+5C0h] BYREF
  unsigned __int64 v209; // [rsp+608h] [rbp+5C8h]
  unsigned __int64 v210; // [rsp+610h] [rbp+5D0h]
  unsigned __int64 v211; // [rsp+618h] [rbp+5D8h]
  unsigned __int64 v212; // [rsp+620h] [rbp+5E0h]
  unsigned __int64 v213; // [rsp+628h] [rbp+5E8h]
  unsigned __int64 v214; // [rsp+630h] [rbp+5F0h]
  wchar_t Src[264]; // [rsp+640h] [rbp+600h] BYREF

  v134 = -2;
  v125 = a3;
  v126 = a2;
  psz = a6;
  v115 = a7;
  pSid = a8;
  v118 = a9;
  Destination = a10;
  v132 = a11;
  ReferencedDomainName = a12;
  v117 = a13;
  v113 = a14;
  v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 72LL);
  v114 = (struct CSession *)v15;
  v16 = 1;
  v103 = 1;
  hExistingToken = (HANDLE)-1LL;
  hObject = 0;
  p_TokenInformation = 0;
  ReturnLength = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  v17 = *(_QWORD *)(v15 + 192);
  v18 = 2 * *(unsigned __int16 *)(v17 + 42);
  v105 = v18;
  String1 = (wchar_t *)(v17 + *(unsigned __int16 *)(v17 + 40));
  v143 = 0;
  LODWORD(v141) = 0;
  v104 = 0;
  v19 = 0;
  TokenInformation = 0;
  if ( (WORD2(qword_102EDC9FC) & 0x1000) != 0 )
  {
    TokenInformation = 1;
    QueryPerformanceCounter(&v174);
    QueryPerformanceCounter(&v147);
    v18 = v105;
  }
  v20 = *(_DWORD *)(v15 + 400);
  v21 = (v20 & 0x8000) != 0 || !v18 && (v20 & 0x100000) == 0;
  v102 = v21;
  if ( *(_DWORD *)(qword_102ECFB00 + 11744) == 1 && !v21 && (v20 & 0x7000) != 0x2000 )
  {
    if ( (v20 & 0x100000) != 0 || (*((_BYTE *)qword_102ECFB10 + 582) & 0x10) == 0 )
    {
      if ( (*(_BYTE *)(v15 + 270) & 4) == 0 )
        goto LABEL_192;
    }
    else if ( (*(_BYTE *)(v15 + 270) & 4) == 0 )
    {
      v21 = 1;
      v102 = 1;
    }
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 96) + 16LL))(*(_QWORD *)(v15 + 96));
  v23 = v22;
  if ( v22 && *(_DWORD *)(*(_QWORD *)(v22 + 520) + 20LL) )
  {
    if ( (*(_DWORD *)(v15 + 400) & 0x8000) != 0 )
      goto LABEL_192;
    v79 = *(_QWORD *)(v15 + 192);
    if ( *(_WORD *)(v79 + 42) || *(_WORD *)(v79 + 46) )
      goto LABEL_192;
    v80 = *(_QWORD *)(v23 + 1032);
    if ( !v80 )
    {
      CSECErrorRingBufferManager::StoreRecord(
        L"QueryContextAttributes",
        L"FInterrogateLogin",
        6u,
        CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
        0);
      v16 = 0;
      goto LABEL_17;
    }
    CSECCertificate::InitFromCertContext(a5, v136, v80, 1);
    if ( v137 )
      operator delete[](v137);
    v121 = 0;
    v122 = 0;
    CSECCertificate::GetSubject(a5, v138, &v121);
    if ( v139 )
      operator delete[](v139);
    pName.cbData = v122;
    pName.pbData = v121;
    *v115 = 2 * CertNameToStrW(1u, &pName, 1u, psz, 0x80u) - 2;
    *a4 = 1;
    v21 = 0;
    v102 = 0;
  }
  v24 = TokenInformation;
  if ( TokenInformation )
  {
    QueryPerformanceCounter(&v129);
    v25 = v129.QuadPart - v147.QuadPart;
    if ( v129.QuadPart < (unsigned __int64)v147.QuadPart )
      v25 = 0;
    QueryPerformanceCounter(&v147);
  }
  else
  {
    v25 = (LONGLONG)v120;
  }
  if ( v21 && OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    if ( v23 && !(unsigned int)SNIGetInfo(*(_QWORD *)(v23 + 448), 35, &v143) && v143 )
    {
      Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v176, 1);
      v120 = &v178;
      v181 = 536871406;
      v182 = 0;
      v184 = 0;
      v183 = 0;
      v185 = 0;
      v186 = 0;
      v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v30 = *(_QWORD *)(v29 + 256);
      if ( !v30 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v30 = *(_QWORD *)(v29 + 256);
      }
      v31 = *(_QWORD *)(v30 + 600);
      if ( v31 )
        v186 = (unsigned int)SOS_Task::PushWait(v31, &v181) == 0;
      v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v33 = *(_QWORD *)(v32 + 256);
      if ( !v33 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v33 = *(_QWORD *)(v32 + 256);
      }
      v180 = v33;
      v179 = (*(_DWORD *)(v33 + 800) >> 11) & 1;
      if ( v179 || (*(_BYTE *)(v33 + 800) & 4) == 0 )
      {
        v178 = 1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v33 + 608) + 8LL))(*(_QWORD *)(v33 + 608));
      }
      else
      {
        v178 = 0;
      }
      if ( !(unsigned int)CSecForwarderLookup::QueryContextAttributesW(v143, 12, &v146) )
        v19 = _wcsicmp(*(const wchar_t **)(v146 + 16), L"ntlm") == 0;
      v120 = &v178;
      if ( v178 )
      {
        if ( v179 )
          *(_DWORD *)(v180 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v180 + 608) + 16LL))(
            *(_QWORD *)(v180 + 608),
            v180,
            1);
      }
      SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v181);
      *(_DWORD *)(v177 + 616) &= ~v176;
      goto LABEL_12;
    }
LABEL_192:
    v16 = 0;
    goto LABEL_17;
  }
LABEL_12:
  if ( v24 )
  {
    QueryPerformanceCounter(&v130);
    v26 = v130.QuadPart - v147.QuadPart;
    if ( v130.QuadPart < (unsigned __int64)v147.QuadPart )
      v26 = 0;
    QueryPerformanceCounter(&v147);
  }
  else
  {
    v26 = (LONGLONG)v111;
  }
  if ( !OsInfo::IsLinux(SOS_OS_OsInfo) || v19 )
  {
    v27 = 0;
    v101 = 0;
    *v113 = 0;
    if ( (unsigned int)intnl_impersonate_client(v114) != 1 )
    {
      v16 = v102 == 0;
      goto LABEL_17;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xAu, 1, &hExistingToken) )
    {
      LastError = GetLastError();
      CSECErrorRingBufferManager::StoreRecord(
        L"OpenThreadToken",
        L"FInterrogateLogin",
        LastError,
        CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
        0);
      intnl_revert_to_self(v114, 1);
      v16 = v102 == 0;
      goto LABEL_17;
    }
    intnl_revert_to_self(v114, 1);
    hObject = hExistingToken;
    GetTokenInformation(hExistingToken, TokenUser, 0, 0, &ReturnLength);
    v73 = ReturnLength + 1;
    v74 = v73 + 15;
    if ( v73 + 15 <= v73 )
      v74 = 0xFFFFFFFFFFFFFF0LL;
    v75 = v74 & 0xFFFFFFFFFFFFFFF0uLL;
    v76 = alloca(v75);
    v77 = alloca(v75);
    p_TokenInformation = (PSID *)&TokenInformation;
    v103 = GetTokenInformation(hExistingToken, TokenUser, &TokenInformation, v73, &ReturnLength);
    if ( !v103 )
    {
      v78 = GetLastError();
      CSECErrorRingBufferManager::StoreRecord(
        L"GetTokenInformation",
        L"FInterrogateLogin",
        v78,
        CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
        0);
      v16 = v102 == 0;
      goto LABEL_17;
    }
  }
  else
  {
    v27 = 1;
    v101 = 1;
    *v113 = 1;
  }
  if ( (*((_BYTE *)qword_102ECFB10 + 1207) & 8) == 0
    && v23
    && !(unsigned int)SNIGetInfo(*(_QWORD *)(v23 + 448), 31, &v150)
    && v150
    && !(unsigned int)SNIGetInfo(*(_QWORD *)(v23 + 448), 35, &v143)
    && v143 )
  {
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v151, 1);
    v111 = &v153;
    v156 = 536871406;
    v157 = 0;
    v159 = 0;
    v158 = 0;
    v160 = 0;
    v161 = 0;
    v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v41 = *(_QWORD *)(v40 + 256);
    if ( !v41 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v41 = *(_QWORD *)(v40 + 256);
    }
    v42 = *(_QWORD *)(v41 + 600);
    if ( v42 )
      v161 = (unsigned int)SOS_Task::PushWait(v42, &v156) == 0;
    v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v44 = *(_QWORD *)(v43 + 256);
    if ( !v44 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v44 = *(_QWORD *)(v43 + 256);
    }
    v155 = v44;
    v154 = (*(_DWORD *)(v44 + 800) >> 11) & 1;
    if ( !v154 && (*(_BYTE *)(v44 + 800) & 4) != 0 )
    {
      v153 = 0;
    }
    else
    {
      v153 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v44 + 608) + 8LL))(*(_QWORD *)(v44 + 608));
    }
    if ( (unsigned int)CSecForwarderLookup::QueryContextAttributesW(v143, 1, &Source) )
    {
      if ( v27 )
      {
        v111 = &v153;
        if ( v153 )
        {
          if ( v154 )
            *(_DWORD *)(v155 + 800) |= 0x800u;
          else
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v155 + 608) + 16LL))(
              *(_QWORD *)(v155 + 608),
              v155,
              1);
        }
        SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v156);
        *(_DWORD *)(v152 + 616) &= ~v151;
        v16 = 0;
        goto LABEL_17;
      }
    }
    else
    {
      v39 = Source;
      v45 = -1;
      do
        ++v45;
      while ( *((_WORD *)Source + v45) );
      v46 = 2 * v45;
      if ( Source )
      {
        if ( v46 )
        {
          v38 = 0;
          v47 = v46 >> 1;
          v48 = v47;
          if ( v47 )
          {
            v49 = 0;
            while ( *((_WORD *)Source + v49) != 92 )
            {
              v38 = (unsigned int)(v38 + 1);
              if ( ++v49 >= v48 )
                goto LABEL_72;
            }
            v34 = (char *)Source + 2 * (int)v38;
            if ( v34 )
            {
              v35 = (2LL * (int)v38) >> 1;
              v36 = (unsigned int)(v48 - v35 - 1);
              if ( (unsigned int)v36 >= 0x80 || (unsigned int)v35 >= 0x80 )
              {
                v103 = 0;
                v104 = 122;
              }
              else
              {
                _mm_lfence();
                memcpy_s(Destination, 2 * v36, v34 + 2, 2 * v36);
                *((_WORD *)Destination + v36) = 0;
                cchName = v36;
                v37 = ReferencedDomainName;
                memcpy_s(ReferencedDomainName, 2LL * (unsigned int)v35, Source, 2LL * (unsigned int)v35);
                v37[(unsigned int)v35] = 0;
                cchReferencedDomainName = v35;
                v39 = Source;
              }
              LODWORD(v141) = 1;
              v24 = TokenInformation;
            }
          }
        }
      }
LABEL_72:
      CSecForwarderLookup::FreeContextBuffer(v39, v38);
    }
    v111 = &v153;
    if ( v153 )
    {
      if ( v154 )
        *(_DWORD *)(v155 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v155 + 608) + 16LL))(
          *(_QWORD *)(v155 + 608),
          v155,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v156);
    *(_DWORD *)(v152 + 616) &= ~v151;
  }
  if ( v24 )
  {
    QueryPerformanceCounter(&v131);
    v50 = v131.QuadPart - v147.QuadPart;
    if ( v131.QuadPart < (unsigned __int64)v147.QuadPart )
      v50 = 0;
    QueryPerformanceCounter(&v147);
  }
  else
  {
    v50 = (LONGLONG)v119;
  }
  if ( (_DWORD)v141 || v27 || (v82 = p_TokenInformation) == 0 )
  {
    v51 = Destination;
    v52 = ReferencedDomainName;
  }
  else
  {
    cchReferencedDomainName = 129;
    cchName = 129;
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v187, 1);
    v119 = &v189;
    v192 = 536871412;
    v193 = 0;
    v195 = 0;
    v194 = 0;
    v196 = 0;
    v197 = 0;
    v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v84 = *(_QWORD *)(v83 + 256);
    if ( !v84 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v84 = *(_QWORD *)(v83 + 256);
    }
    v85 = *(_QWORD *)(v84 + 600);
    if ( v85 )
      v197 = (unsigned int)SOS_Task::PushWait(v85, &v192) == 0;
    v86 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v87 = *(_QWORD *)(v86 + 256);
    if ( !v87 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v87 = *(_QWORD *)(v86 + 256);
    }
    v191 = v87;
    v190 = (*(_DWORD *)(v87 + 800) >> 11) & 1;
    if ( v190 || (*(_BYTE *)(v87 + 800) & 4) == 0 )
    {
      v189 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v87 + 608) + 8LL))(*(_QWORD *)(v87 + 608));
    }
    else
    {
      v189 = 0;
    }
    v52 = ReferencedDomainName;
    v51 = Destination;
    v103 = LookupAccountSidW(
             0,
             *v82,
             (LPWSTR)Destination,
             &cchName,
             ReferencedDomainName,
             &cchReferencedDomainName,
             &v173);
    if ( !v103 )
      v104 = GetLastError();
    v119 = &v189;
    if ( v189 )
    {
      if ( v190 )
        *(_DWORD *)(v191 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v191 + 608) + 16LL))(
          *(_QWORD *)(v191 + 608),
          v191,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v192);
    *(_DWORD *)(v188 + 616) &= ~v187;
  }
  if ( !v103 )
  {
    CSECErrorRingBufferManager::StoreRecord(
      L"LookupAccountSid",
      L"FInterrogateLogin",
      v104,
      CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
      0);
    v16 = v102 == 0;
    goto LABEL_17;
  }
  *v132 = 2 * cchName;
  *v117 = 2 * cchReferencedDomainName;
  if ( TokenInformation )
  {
    QueryPerformanceCounter(&v133);
    v53 = v133.QuadPart - v147.QuadPart;
    if ( v133.QuadPart < (unsigned __int64)v147.QuadPart )
      v53 = 0;
    QueryPerformanceCounter(&v147);
  }
  else
  {
    v53 = (LONGLONG)v110;
  }
  if ( v102 )
  {
    DefaultLocale = GetDefaultLocale();
    v55 = StringCchPrintf_lW(Src, 0x102u, L"%ls\\%ls", DefaultLocale, v52, v51);
    if ( v55 < 0 )
    {
      _mm_lfence();
      LODWORD(peUse) = v55;
      LODWORD(phNewToken) = 2640;
      ex_raise(4, 7, 16, 1, "sql\\ntdbms\\msql\\security\\src\\seclogin.cpp", phNewToken, peUse);
    }
    v56 = -1;
    v57 = -1;
    do
      ++v57;
    while ( Src[v57] );
    v58 = 2 * v57;
    if ( (*((_DWORD *)v114 + 100) & 0x7000) == 0x2000 )
    {
      if ( v105 != v58 )
        goto LABEL_192;
      v88 = GetDefaultLocale();
      if ( _wcsnicmp_l(String1, Src, (unsigned __int64)v105 >> 1, v88) )
        goto LABEL_192;
    }
    *v115 = v58;
    v59 = (unsigned int)v58;
    if ( !v58 )
      goto LABEL_94;
    if ( psz )
    {
      if ( v59 <= 0x100 )
      {
        memmove(psz, Src, v59);
LABEL_94:
        if ( v101 )
        {
          Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v162, 1);
          v110 = &v164;
          v167 = 536872347;
          v168 = 0;
          v170 = 0;
          v169 = 0;
          v171 = 0;
          v172 = 0;
          v89 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v90 = *(_QWORD *)(v89 + 256);
          if ( !v90 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v90 = *(_QWORD *)(v89 + 256);
          }
          v91 = *(_QWORD *)(v90 + 600);
          if ( v91 )
            v172 = (unsigned int)SOS_Task::PushWait(v91, &v167) == 0;
          v92 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v93 = *(_QWORD *)(v92 + 256);
          if ( !v93 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v93 = *(_QWORD *)(v92 + 256);
          }
          v166 = v93;
          v165 = (*(_DWORD *)(v93 + 800) >> 11) & 1;
          if ( v165 || (*(_BYTE *)(v93 + 800) & 4) == 0 )
          {
            v164 = 1;
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v93 + 608) + 8LL))(*(_QWORD *)(v93 + 608));
          }
          else
          {
            v164 = 0;
          }
          ReturnLength = 85;
          v94 = v117;
          v95 = CSecForwarderLookup::LookupAccountNameW(0, Src, pSid, &ReturnLength, ReferencedDomainName, v117, v175);
          *v118 = ReturnLength;
          if ( !v95 )
          {
            v110 = &v164;
            if ( v164 )
            {
              if ( v165 )
                *(_DWORD *)(v166 + 800) |= 0x800u;
              else
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v166 + 608) + 16LL))(
                  *(_QWORD *)(v166 + 608),
                  v166,
                  1);
            }
            SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v167);
            *(_DWORD *)(v163 + 616) &= ~v162;
            v16 = 0;
            goto LABEL_17;
          }
          *v94 = 2 * *v94 - 2;
          v110 = &v164;
          if ( v164 )
          {
            if ( v165 )
              *(_DWORD *)(v166 + 800) |= 0x800u;
            else
              (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v166 + 608) + 16LL))(
                *(_QWORD *)(v166 + 608),
                v166,
                1);
          }
          SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v167);
          *(_DWORD *)(v163 + 616) &= ~v162;
        }
        else
        {
          v60 = (const void *const *)p_TokenInformation;
          LengthSid = GetLengthSid(*p_TokenInformation);
          ReturnLength = LengthSid;
          *v118 = LengthSid;
          memcpy_s(pSid, 0x55u, *v60, LengthSid);
        }
        if ( TokenInformation )
        {
          QueryPerformanceCounter(&v124);
          v63 = v124.QuadPart - v147.QuadPart;
          if ( v124.QuadPart < (unsigned __int64)v147.QuadPart )
            v63 = 0;
          QueryPerformanceCounter(&v147);
        }
        else
        {
          v63 = v135;
        }
        if ( *(_DWORD *)(qword_102ECFB00 + 14548)
          && (unsigned int)FIsValidLoginForUserInstance(hExistingToken, pSid, v62, 1) )
        {
          goto LABEL_224;
        }
        if ( !v101 )
        {
          v141 = 0;
          if ( !DuplicateTokenEx(hExistingToken, 0xBu, 0, SecurityImpersonation, TokenPrimary, &v141) )
          {
            v96 = GetLastError();
            CSECErrorRingBufferManager::StoreRecord(
              L"DuplicateTokenEx",
              L"FInterrogateLogin",
              v96,
              CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
              0);
            if ( !DuplicateTokenEx(hExistingToken, 0xBu, 0, SecurityIdentification, TokenImpersonation, &v141) )
            {
              v97 = GetLastError();
              CSECErrorRingBufferManager::StoreRecord(
                L"DuplicateTokenEx",
                L"FInterrogateLogin",
                v97,
                CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
                0);
LABEL_224:
              v16 = 0;
              goto LABEL_17;
            }
          }
          *(_QWORD *)v125 = v141;
        }
        *v126 = 1;
        if ( (WORD2(qword_102EDC9FC) & 0x1000) != 0 )
        {
          v199 = 0x10000;
          v200 = 0;
          v201 = v204;
          v202 = &v205;
          v206 = 0;
          v203 = 0;
          v207 = 0;
          v204[0] = &v208;
          v204[1] = 56;
          if ( TokenInformation )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v64 = PerformanceCount.QuadPart - v174.QuadPart;
            if ( PerformanceCount.QuadPart < (unsigned __int64)v174.QuadPart )
              v64 = 0;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v64 == -1 )
                v65 = -1;
              else
                v65 = (unsigned __int64)(1000000 * v64) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v65 = 0;
            }
            v208 = v65;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v25 == -1 )
                v66 = -1;
              else
                v66 = (unsigned __int64)(1000000 * v25) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v66 = 0;
            }
            v209 = v66;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v26 == -1 )
                v67 = -1;
              else
                v67 = (unsigned __int64)(1000000 * v26) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v67 = 0;
            }
            v210 = v67;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v50 == -1 )
                v68 = -1;
              else
                v68 = (unsigned __int64)(1000000 * v50) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v68 = 0;
            }
            v211 = v68;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v53 == -1 )
                v69 = -1;
              else
                v69 = (unsigned __int64)(1000000 * v53) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v69 = 0;
            }
            v212 = v69;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v63 == -1 )
                v70 = -1;
              else
                v70 = (unsigned __int64)(1000000 * v63) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v70 = 0;
            }
            v213 = v70;
            QueryPerformanceCounter(&v128);
            v71 = v128.QuadPart - v147.QuadPart;
            if ( v128.QuadPart < (unsigned __int64)v147.QuadPart )
              v71 = 0;
            if ( Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
            {
              if ( v71 != -1 )
                v56 = (unsigned __int64)(1000000 * v71) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
            }
            else
            {
              v56 = 0;
            }
          }
          else
          {
            v208 = 0;
            v209 = 0;
            v210 = 0;
            v211 = 0;
            v212 = 0;
            v213 = 0;
            v56 = 0;
          }
          v214 = v56;
          XeSqlPkg::security_authentication_perf_interrogate_login::Publish((XeSqlPkg::security_authentication_perf_interrogate_login *)v198);
        }
        goto LABEL_17;
      }
      memset_0(psz, 0, 0x100u);
      *_errno() = 34;
    }
    else
    {
      *_errno() = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_94;
  }
LABEL_17:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  hObject = 0;
  return v16;
}

```

## disassembly

```asm
0x1005597d0  push    rbp
0x1005597d2  push    rsi
0x1005597d3  push    rdi
0x1005597d4  push    r12
0x1005597d6  push    r13
0x1005597d8  push    r14
0x1005597da  push    r15
0x1005597dc  sub     rsp, 860h
0x1005597e3  lea     rbp, [rsp+40h]
0x1005597e8  mov     [rbp+850h+var_750], 0FFFFFFFFFFFFFFFEh
0x1005597f3  mov     [rbp+850h+arg_0], rbx
0x1005597fa  mov     rax, cs:__security_cookie
0x100559801  xor     rax, rbp
0x100559804  mov     [rbp+850h+var_40], rax
0x10055980b  mov     rsi, r9
0x10055980e  mov     [rbp+850h+var_7A0], r8
0x100559815  mov     [rbp+850h+var_798], rdx
0x10055981c  mov     rax, [rbp+850h+arg_28]
0x100559823  mov     [rbp+850h+psz], rax
0x100559827  mov     rbx, [rbp+850h+arg_20]
0x10055982e  mov     rax, [rbp+850h+arg_30]
0x100559835  mov     [rbp+850h+var_7F0], rax
0x100559839  mov     rax, [rbp+850h+arg_38]
0x100559840  mov     [rbp+850h+pSid], rax
0x100559844  mov     rax, [rbp+850h+arg_40]
0x10055984b  mov     [rbp+850h+var_7D8], rax
0x10055984f  mov     rax, [rbp+850h+arg_48]
0x100559856  mov     [rbp+850h+Destination], rax
0x10055985a  mov     rax, [rbp+850h+arg_50]
0x100559861  mov     [rbp+850h+var_760], rax
0x100559868  mov     rax, [rbp+850h+arg_58]
0x10055986f  mov     [rbp+850h+ReferencedDomainName], rax
0x100559873  mov     rax, [rbp+850h+arg_60]
0x10055987a  mov     [rbp+850h+var_7E0], rax
0x10055987e  mov     rax, [rbp+850h+arg_68]
0x100559885  mov     [rbp+850h+var_800], rax
0x100559889  xor     r8d, r8d
0x10055988c  mov     rdx, gs:58h
0x100559895  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10055989c  mov     ecx, [rax]
0x10055989e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005598a5  mov     eax, [rax]
0x1005598a7  add     rax, [rdx+rcx*8]
0x1005598ab  mov     rax, [rax]
0x1005598ae  mov     r15, [rax+48h]
0x1005598b2  mov     [rbp+850h+var_7F8], r15
0x1005598b6  mov     r12d, 1
0x1005598bc  mov     [rbp+850h+var_848], r12d
0x1005598c0  mov     [rbp+850h+hExistingToken], 0FFFFFFFFFFFFFFFFh
0x1005598cb  mov     [rbp+850h+hObject], r8
0x1005598cf  mov     [rbp+850h+var_808], r8
0x1005598d3  mov     [rbp+850h+ReturnLength], r8d
0x1005598da  mov     [rbp+850h+cchName], r8d
0x1005598e1  mov     [rbp+850h+cchReferencedDomainName], r8d
0x1005598e8  mov     rax, [r15+0C0h]
0x1005598ef  movzx   edx, word ptr [rax+2Ah]
0x1005598f3  add     edx, edx
0x1005598f5  mov     [rbp+850h+var_840], edx
0x1005598f8  movzx   ecx, word ptr [rax+28h]
0x1005598fc  add     rcx, rax
0x1005598ff  mov     [rbp+850h+String1], rcx
0x100559906  mov     [rbp+850h+var_6D8], r8
0x10055990d  mov     dword ptr [rbp+850h+var_6E8], r8d
0x100559914  mov     [rbp+850h+var_844], r8d
0x100559918  xor     r13b, r13b
0x10055991b  mov     [rbp+850h+TokenInformation], r13b
0x10055991f  test    dword ptr cs:qword_102EDC9FC+4, 1000h
0x100559929  jnz     loc_1014538A3
0x10055992f  mov     ecx, [r15+190h]
0x100559936  mov     eax, ecx
0x100559938  shr     eax, 0Fh
0x10055993b  test    al, 1
0x10055993d  jnz     loc_10058AAFF
0x100559943  test    edx, edx
0x100559945  jz      loc_10058AAF2
0x10055994b  mov     r14d, r8d
0x10055994e  jmp     short loc_100559951
0x100559951  mov     [rbp+850h+var_84C], r14d
0x100559955  mov     rax, cs:qword_102ECFB00
0x10055995c  cmp     dword ptr [rax+2DE0h], 1
0x100559963  jz      loc_1014538CD
0x100559969  mov     rcx, [r15+60h]
0x10055996d  mov     rax, [rcx]
0x100559970  call    qword ptr [rax+10h]
0x100559973  mov     rdi, rax
0x100559976  test    rax, rax
0x100559979  jz      short loc_10055998C
0x10055997b  mov     rax, [rax+208h]
0x100559982  cmp     dword ptr [rax+14h], 0
0x100559986  jnz     loc_10145392E
0x10055998c  xor     ebx, ebx
0x10055998e  movzx   esi, [rbp+850h+TokenInformation]
0x100559992  test    sil, sil
0x100559995  jnz     loc_101453A4D
0x10055999b  mov     r15, [rbp+850h+var_7C8]
0x1005599a2  test    r14d, r14d
0x1005599a5  jnz     loc_10058AB08
0x1005599ab  test    sil, sil
0x1005599ae  jnz     loc_101453AB4
0x1005599b4  mov     r14, [rbp+850h+var_810]
0x1005599b8  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x1005599bf  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x1005599c5  test    al, al
0x1005599c7  jnz     loc_10058B197
0x1005599cd  xor     r13b, r13b
0x1005599d0  mov     [rbp+850h+var_84F], r13b
0x1005599d4  mov     rax, [rbp+850h+var_800]
0x1005599d8  mov     [rax], r13b
0x1005599db  mov     rbx, [rbp+850h+var_7F8]
0x1005599df  mov     rcx, rbx; struct CSession *
0x1005599e2  call    ?intnl_impersonate_client@@YAHPEAVCSession@@@Z; intnl_impersonate_client(CSession *)
0x1005599e7  cmp     eax, 1
0x1005599ea  jz      loc_10058C0AB
0x1005599f0  xor     eax, eax
0x1005599f2  mov     r12d, eax
0x1005599f5  cmp     [rbp+850h+var_84C], eax
0x1005599f8  setz    r12b
0x1005599fc  jmp     short loc_1005599FF
0x1005599ff  xor     eax, eax
0x100559a01  mov     rcx, [rbp+850h+hObject]; hObject
0x100559a05  lea     rdx, [rcx-1]
0x100559a09  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x100559a0d  jbe     loc_10058AD0C
0x100559a13  mov     [rbp+850h+hObject], rax
0x100559a17  mov     eax, r12d
0x100559a1a  mov     rcx, [rbp+850h+var_40]
0x100559a21  xor     rcx, rbp; StackCookie
0x100559a24  call    __security_check_cookie
0x100559a29  mov     rbx, [rbp+850h+arg_0]
0x100559a30  lea     rsp, [rbp+820h]
0x100559a37  pop     r15
0x100559a39  pop     r14
0x100559a3b  pop     r13
0x100559a3d  pop     r12
0x100559a3f  pop     rdi
0x100559a40  pop     rsi
0x100559a41  pop     rbp
0x100559a42  retn
0x10058aaf2  mov     eax, ecx
0x10058aaf4  shr     eax, 14h
0x10058aaf7  test    al, 1
0x10058aaf9  jnz     loc_10055994B
0x10058aaff  mov     r14d, r12d
0x10058ab02  jmp     loc_100559951
0x10058ab08  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10058ab0f  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x10058ab15  test    al, al
0x10058ab17  jz      loc_1005599AB
0x10058ab1d  test    rdi, rdi
0x10058ab20  jz      loc_101453F50
0x10058ab26  lea     r8, [rbp+850h+var_6D8]
0x10058ab2d  mov     edx, 23h ; '#'
0x10058ab32  mov     rcx, [rdi+1C0h]
0x10058ab39  call    SNIGetInfo
0x10058ab3e  test    eax, eax
0x10058ab40  jnz     loc_101453F50
0x10058ab46  cmp     [rbp+850h+var_6D8], 0
0x10058ab4e  jz      loc_101453F50
0x10058ab54  mov     edx, r12d
0x10058ab57  lea     rcx, [rbp+850h+var_5B0]
0x10058ab5e  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10058ab63  nop
0x10058ab64  lea     rax, [rbp+850h+var_5A0]
0x10058ab6b  mov     [rbp+850h+var_7C8], rax
0x10058ab72  mov     [rbp+850h+var_590], 200001EEh
0x10058ab7c  mov     [rbp+850h+var_588], rbx
0x10058ab83  mov     [rbp+850h+var_578], rbx
0x10058ab8a  mov     [rbp+850h+var_580], rbx
0x10058ab91  mov     [rbp+850h+var_570], rbx
0x10058ab98  mov     [rbp+850h+var_560], 0
0x10058ab9f  mov     rdx, gs:58h
0x10058aba8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10058abaf  mov     ecx, [rax]
0x10058abb1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10058abb8  mov     ebx, [rax]
0x10058abba  add     rbx, [rdx+rcx*8]
0x10058abbe  mov     rcx, [rbx+100h]
0x10058abc5  test    rcx, rcx
0x10058abc8  jnz     short loc_10058ABD7
0x10058abca  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10058abd0  mov     rcx, [rbx+100h]
0x10058abd7  mov     rcx, [rcx+258h]
0x10058abde  test    rcx, rcx
0x10058abe1  jz      short loc_10058ABF9
0x10058abe3  lea     rdx, [rbp+850h+var_590]
0x10058abea  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10058abf0  test    eax, eax
0x10058abf2  setz    [rbp+850h+var_560]
0x10058abf9  mov     rdx, gs:58h
0x10058ac02  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10058ac09  mov     ecx, [rax]
0x10058ac0b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10058ac12  mov     ebx, [rax]
0x10058ac14  add     rbx, [rdx+rcx*8]
0x10058ac18  mov     rdx, [rbx+100h]
0x10058ac1f  test    rdx, rdx
0x10058ac22  jnz     short loc_10058AC33
0x10058ac24  xor     ecx, ecx
0x10058ac26  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10058ac2c  mov     rdx, [rbx+100h]
0x10058ac33  mov     [rbp+850h+var_598], rdx
0x10058ac3a  mov     eax, [rdx+320h]
0x10058ac40  shr     eax, 0Bh
0x10058ac43  and     eax, 1
0x10058ac46  mov     [rbp+850h+var_59C], eax
0x10058ac4c  jnz     loc_101453A89
0x10058ac52  test    byte ptr [rdx+320h], 4
0x10058ac59  jz      loc_101453A89
0x10058ac5f  xor     ecx, ecx
0x10058ac61  mov     [rbp+850h+var_5A0], ecx
0x10058ac67  jmp     short loc_10058AC6A
0x10058ac6a  lea     r8, [rbp+850h+var_6B8]
0x10058ac71  mov     edx, 0Ch
0x10058ac76  mov     rcx, [rbp+850h+var_6D8]
0x10058ac7d  call    cs:?QueryContextAttributesW@CSecForwarderLookup@@2P6AJPEAU_SecHandle@@KPEAX@ZEA; long (*CSecForwarderLookup::QueryContextAttributesW)(_SecHandle *,ulong,void *)
0x10058ac83  test    eax, eax
0x10058ac85  jnz     short loc_10058ACA5
0x10058ac87  lea     rdx, aNtlm; "ntlm"
0x10058ac8e  mov     rcx, [rbp+850h+var_6B8]
0x10058ac95  mov     rcx, [rcx+10h]; String1
0x10058ac99  call    cs:__imp__wcsicmp
0x10058ac9f  test    eax, eax
0x10058aca1  setz    r13b
0x10058aca5  lea     rax, [rbp+850h+var_5A0]
0x10058acac  mov     [rbp+850h+var_7C8], rax
0x10058acb3  cmp     [rbp+850h+var_5A0], 0
0x10058acba  jz      short loc_10058ACE4
0x10058acbc  mov     rdx, [rbp+850h+var_598]
0x10058acc3  mov     rcx, [rdx+260h]
0x10058acca  cmp     [rbp+850h+var_59C], 0
0x10058acd1  jz      loc_101453AA4
0x10058acd7  or      dword ptr [rdx+320h], 800h
0x10058ace1  jmp     short loc_10058ACE4
0x10058ace4  lea     rcx, [rbp+850h+var_590]; this
0x10058aceb  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x10058acf0  nop
0x10058acf1  mov     ecx, [rbp+850h+var_5B0]
0x10058acf7  not     ecx
0x10058acf9  mov     rax, [rbp+850h+var_5A8]
0x10058ad00  and     [rax+268h], ecx
0x10058ad06  jmp     loc_1005599AB
0x10058ad0c  call    cs:__imp_CloseHandle
0x10058ad12  xor     eax, eax
0x10058ad14  jmp     loc_100559A13
0x10058b0f2  movsxd  rax, edx
0x10058b0f5  lea     r8, [rcx+rax*2]
0x10058b0f9  test    r8, r8
0x10058b0fc  jz      loc_10058B39C
0x10058b102  mov     rsi, r8
0x10058b105  sub     rsi, rcx
0x10058b108  sar     rsi, 1
0x10058b10b  sub     edi, esi
0x10058b10d  dec     edi
0x10058b10f  cmp     edi, 80h
0x10058b115  jnb     loc_101453B7F
0x10058b11b  cmp     esi, 80h
0x10058b121  jnb     loc_101453B7F
0x10058b127  lfence
0x10058b12a  lea     rbx, [rdi+rdi]
0x10058b12e  add     r8, 2; Source
0x10058b132  mov     r9, rbx; SourceSize
0x10058b135  mov     rdx, rbx; DestinationSize
0x10058b138  mov     rcx, [rbp+850h+Destination]; Destination
0x10058b13c  call    memcpy_s
0x10058b141  mov     rax, [rbp+850h+Destination]
0x10058b145  xor     ecx, ecx
0x10058b147  mov     [rbx+rax], cx
0x10058b14b  mov     [rbp+850h+cchName], edi
0x10058b151  mov     eax, esi
0x10058b153  lea     rbx, [rax+rax]
0x10058b157  mov     r9, rbx; SourceSize
0x10058b15a  mov     r8, [rbp+850h+Source]; Source
0x10058b161  mov     rdx, rbx; DestinationSize
0x10058b164  mov     rdi, [rbp+850h+ReferencedDomainName]
0x10058b168  mov     rcx, rdi; Destination
0x10058b16b  call    memcpy_s
0x10058b170  xor     eax, eax
0x10058b172  mov     [rbx+rdi], ax
0x10058b176  mov     [rbp+850h+cchReferencedDomainName], esi
0x10058b17c  mov     rcx, [rbp+850h+Source]
0x10058b183  jmp     short loc_10058B186
0x10058b186  mov     dword ptr [rbp+850h+var_6E8], r12d
0x10058b18d  movzx   esi, [rbp+850h+TokenInformation]
0x10058b191  jmp     loc_10058B39C
0x10058b197  test    r13b, r13b
0x10058b19a  jnz     loc_1005599CD
0x10058b1a0  mov     r13b, 1
0x10058b1a3  mov     [rbp+850h+var_84F], r13b
0x10058b1a7  mov     rax, [rbp+850h+var_800]
0x10058b1ab  mov     [rax], r13b
0x10058b1ae  mov     rax, cs:qword_102ECFB10
0x10058b1b5  test    byte ptr [rax+4B7h], 8
0x10058b1bc  jnz     loc_10058B405
0x10058b1c2  test    rdi, rdi
0x10058b1c5  jz      loc_10058B405
0x10058b1cb  lea     r8, [rbp+850h+var_698]
0x10058b1d2  mov     edx, 1Fh
0x10058b1d7  mov     rcx, [rdi+1C0h]
0x10058b1de  call    SNIGetInfo
0x10058b1e3  test    eax, eax
  ... truncated ...
```
