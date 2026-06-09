# FrCtLogApplier::ApplyChangeTrackingLogToVirtualDisk(IVmmsRealizedVirtualMachine *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IVmTask *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *,Vml::VmGuid const &,int)

- ea: `0x140392c44`
- end: `0x140394a76`
- name: `?ApplyChangeTrackingLogToVirtualDisk@FrCtLogApplier@@SAJPEAUIVmmsRealizedVirtualMachine@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1PEAUIVmTask@@1PEBV34@AEBVVmGuid@Vml@@H@Z`
- size: `7730`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 *, LPCWSTR lpFileName, __int64, int)`
- caller_count: `2`
- callee_count: `47`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140184b8c`
- `0x1403cbc80`

## callees

- `0x14001993c`
- `0x140022640`
- `0x140032594`
- `0x1400341d8`
- `0x1400342a0`
- `0x1400423f0`
- `0x140043dc8`
- `0x14004bf10`
- `0x14004f3c4`
- `0x14004f830`
- `0x14005c630`
- `0x140073cd0`
- `0x1400fc48c`
- `0x1400ff4bc`
- `0x1401879a4`
- `0x1401a73b4`
- `0x1401be65c`
- `0x1401ddfbc`
- `0x140213084`
- `0x1402acfe8`
- `0x1402ad2ac`
- `0x14030dd8c`
- `0x140320368`
- `0x140392b2c`
- `0x140392bec`
- `0x140392c44`
- `0x140394a7c`
- `0x140394ec0`
- `0x14039553c`
- `0x1404828e0`
- `0x1404835a0`
- `0x140486529`
- `0x1404a4e18`
- `0x14050896c`
- `0x14050b174`
- `0x14050c094`
- `0x14050c354`
- `0x14050cb90`
- `0x14050d34c`
- `0x14050d430`
- `0x14050d894`
- `0x14050ea74`
- `0x140528568`
- `0x140529bb4`
- `0x140597760`
- `0x14059a54c`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140393f83`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140393f83`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140393830`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140393830`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140393d74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1403942b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140393d74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1403942b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403938ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140394022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403942c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14039479f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140394807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14039487d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403938ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140393f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140394022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403942c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14039479f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140394807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14039487d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140393a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140394012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14039478f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403947f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14039486d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140393a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140394012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14039478f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1403947f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14039486d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x140392ef3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x140392ef3`
- `ntdll!NtQueryVolumeInformationFile` at `0x1403939fd`
- `ntdll!NtQueryVolumeInformationFile` at `0x1403939fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1403938d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140393a65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1403938d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140393a65`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FrCtLogApplier::ApplyChangeTrackingLogToVirtualDisk(
        __int64 a1,
        LPWSTR **a2,
        __int64 a3,
        Vml *a4,
        unsigned __int16 *a5,
        WCHAR *lpFileName,
        unsigned __int64 *a7,
        int a8)
{
  LPWSTR *v8; // r13
  LPCWSTR v9; // r14
  const unsigned __int16 *v10; // rcx
  wchar_t **v11; // rdx
  signed int LogFileHandle; // esi
  WCHAR *v13; // rcx
  LPWSTR *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rax
  const char *v21; // r9
  LPWSTR **v22; // rbx
  int v23; // eax
  const unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  LPWSTR *v26; // rax
  wchar_t **v27; // rdx
  int v28; // eax
  LPWSTR *v29; // rax
  __int128 *v30; // rcx
  LPWSTR *v31; // rax
  __int128 *v32; // r8
  __int128 *v33; // rcx
  __m256i *p_FsInformation; // r8
  __int128 *v35; // rcx
  __int128 *v36; // rax
  LPWSTR *v37; // rax
  int IsFileOnSMBShare; // esi
  int v39; // eax
  LPWSTR *v40; // rcx
  unsigned __int16 *v41; // rax
  int v42; // esi
  signed int LastError; // eax
  const WCHAR *v44; // rcx
  HANDLE FileW; // rsi
  signed int v46; // eax
  LPCWSTR v47; // rax
  wchar_t **v48; // rdx
  const WCHAR *v49; // rcx
  signed int v50; // eax
  __int64 v51; // rcx
  unsigned __int64 *v52; // r14
  unsigned __int16 *v53; // rax
  wchar_t **v54; // rdx
  unsigned __int64 v55; // rcx
  LPCWSTR v56; // rdx
  unsigned int *v57; // rcx
  signed int v58; // eax
  LPCWSTR v59; // rax
  signed int v60; // eax
  BOOL v61; // esi
  signed int v62; // eax
  unsigned int v63; // esi
  unsigned __int16 *v64; // rax
  __int64 v65; // rcx
  unsigned __int64 v66; // rcx
  LPWSTR *v67; // rax
  unsigned int *v68; // rcx
  signed int v69; // eax
  wchar_t **v70; // rdx
  __int64 v71; // rcx
  unsigned __int16 *v72; // rbx
  unsigned __int16 *v73; // rax
  __int128 *v74; // rax
  const EVENT_DESCRIPTOR *FrEventDescriptorFromErrorCode; // rax
  __int128 *v76; // rcx
  unsigned __int16 *v77; // rax
  LPWSTR *v78; // rax
  signed int v79; // eax
  unsigned int v80; // ebx
  signed int v81; // eax
  unsigned int v82; // ebx
  signed int v83; // eax
  unsigned int v84; // ebx
  unsigned int v85; // ebx
  Vml *v86; // r15
  __int64 v87; // r14
  int v88; // eax
  unsigned int *dwCreationDisposition; // [rsp+20h] [rbp-588h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-580h]
  LPWSTR **v92; // [rsp+58h] [rbp-550h]
  __int64 v93; // [rsp+60h] [rbp-548h] BYREF
  unsigned __int16 *v94; // [rsp+68h] [rbp-540h]
  LPCWSTR v95; // [rsp+70h] [rbp-538h]
  const WCHAR **v96; // [rsp+78h] [rbp-530h]
  __int64 v97; // [rsp+80h] [rbp-528h]
  int *v98; // [rsp+88h] [rbp-520h] BYREF
  unsigned __int16 *v99; // [rsp+90h] [rbp-518h]
  __int64 v100; // [rsp+98h] [rbp-510h] BYREF
  Vml *Pointer; // [rsp+A0h] [rbp-508h]
  __int64 v102[2]; // [rsp+B0h] [rbp-4F8h] BYREF
  HANDLE v103; // [rsp+C0h] [rbp-4E8h]
  LPCWSTR v104; // [rsp+C8h] [rbp-4E0h]
  LPWSTR *v105; // [rsp+D0h] [rbp-4D8h]
  unsigned __int64 *v106; // [rsp+D8h] [rbp-4D0h]
  __int64 v107; // [rsp+E0h] [rbp-4C8h]
  __int64 v108; // [rsp+E8h] [rbp-4C0h] BYREF
  __int64 v109; // [rsp+F0h] [rbp-4B8h]
  LPWSTR **v110; // [rsp+F8h] [rbp-4B0h]
  __int64 v111; // [rsp+100h] [rbp-4A8h]
  __int64 v112; // [rsp+108h] [rbp-4A0h]
  GUID Buf1; // [rsp+110h] [rbp-498h] BYREF
  HANDLE hObject; // [rsp+120h] [rbp-488h]
  __int64 v115; // [rsp+128h] [rbp-480h] BYREF
  __int128 v116; // [rsp+130h] [rbp-478h]
  HANDLE hHandle; // [rsp+140h] [rbp-468h]
  DWORD v118; // [rsp+148h] [rbp-460h]
  GUID v119; // [rsp+14Ch] [rbp-45Ch] BYREF
  int v120; // [rsp+15Ch] [rbp-44Ch]
  HANDLE v121; // [rsp+160h] [rbp-448h] BYREF
  _BYTE v122[32]; // [rsp+168h] [rbp-440h] BYREF
  BOOL v123; // [rsp+188h] [rbp-420h]
  __int128 v124; // [rsp+190h] [rbp-418h] BYREF
  __m128i v125; // [rsp+1A0h] [rbp-408h]
  int v126; // [rsp+1B0h] [rbp-3F8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1B8h] [rbp-3F0h] BYREF
  LPWSTR pszPath[2]; // [rsp+1C8h] [rbp-3E0h] BYREF
  __m128i v129; // [rsp+1D8h] [rbp-3D0h]
  int v130; // [rsp+1E8h] [rbp-3C0h] BYREF
  __m256i FsInformation; // [rsp+1F0h] [rbp-3B8h] BYREF
  __int128 v132; // [rsp+210h] [rbp-398h] BYREF
  __int64 v133; // [rsp+220h] [rbp-388h]
  __int128 v134; // [rsp+228h] [rbp-380h] BYREF
  __int64 v135; // [rsp+238h] [rbp-370h]
  unsigned __int64 v136; // [rsp+240h] [rbp-368h]
  struct IUnknown v137; // [rsp+248h] [rbp-360h] BYREF
  __int128 v138; // [rsp+250h] [rbp-358h] BYREF
  __int64 v139; // [rsp+260h] [rbp-348h]
  unsigned __int64 v140; // [rsp+268h] [rbp-340h]
  __int128 Src; // [rsp+270h] [rbp-338h] BYREF
  __m128i si128; // [rsp+280h] [rbp-328h]
  __int64 v143; // [rsp+290h] [rbp-318h] BYREF
  _BYTE v144[152]; // [rsp+2A0h] [rbp-308h] BYREF
  __int64 v145; // [rsp+338h] [rbp-270h]
  __int64 v146; // [rsp+340h] [rbp-268h]
  unsigned int v147[8]; // [rsp+520h] [rbp-88h] BYREF
  unsigned __int16 v148[16]; // [rsp+540h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+0h]

  Pointer = a4;
  v92 = a2;
  v97 = a1;
  v104 = lpFileName;
  v96 = (const WCHAR **)lpFileName;
  v110 = a2;
  v94 = a5;
  v107 = a1;
  v8 = (LPWSTR *)a2;
  v105 = (LPWSTR *)a2;
  v111 = a3;
  IoStatusBlock.Pointer = a4;
  v9 = lpFileName;
  v95 = lpFileName;
  v106 = a7;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v138 = 0;
  v139 = 0;
  v140 = 7;
  LOWORD(v138) = 0;
  v134 = 0;
  v135 = 0;
  v136 = 7;
  LOWORD(v134) = 0;
  *(_OWORD *)pszPath = 0;
  v129 = si128;
  LOWORD(pszPath[0]) = 0;
  v143 = 0;
  hObject = (HANDLE)-1LL;
  v130 = 0;
  v115 = 0;
  v116 = 0;
  hHandle = (HANDLE)-1LL;
  v118 = 0;
  v119 = GUID_NULL;
  v120 = -2147467259;
  _APPLY_DISK_PARAMETERS::_APPLY_DISK_PARAMETERS((_APPLY_DISK_PARAMETERS *)&v121);
  v132 = 0;
  v133 = 0;
  v93 = -1;
  Buf1 = GUID_NULL;
  v108 = 0;
  LODWORD(v137.lpVtbl) = 0;
  v99 = a5 + 12;
  if ( *((_QWORD *)a5 + 3) <= 7u )
    v10 = a5;
  else
    v10 = *(const unsigned __int16 **)a5;
  if ( (unsigned int)GetVhdExtensionInfo(v10, 0, 0, 0, 0) )
  {
    if ( !v97 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
      {
        v11 = &off_140907A18;
        goto LABEL_10;
      }
LABEL_14:
      LogFileHandle = -2147024809;
      goto LABEL_285;
    }
    if ( !Pointer )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
      {
        v11 = &off_140907A30;
        goto LABEL_10;
      }
      goto LABEL_14;
    }
    v103 = (HANDLE)-1LL;
    v109 = -1;
    std::wstring::operator=(pszPath, a5);
    v13 = (WCHAR *)pszPath;
    if ( v129.m128i_i64[1] > 7uLL )
      v13 = pszPath[0];
    PathStripPathW(v13);
    v14 = pszPath;
    if ( v129.m128i_i64[1] > 7uLL )
      v14 = (LPWSTR *)pszPath[0];
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    std::wstring::resize(pszPath);
    v124 = 0;
    v125 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v124) = 0;
    v16 = v97;
    v102[0] = v97 + 8;
    v112 = v97 + 8;
    v17 = v97 + *(int *)(*(_QWORD *)(v97 + 8) + 12LL) + 8LL;
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
    v100 = v18;
    v19 = *(int *)(*(_QWORD *)(v97 + 8) + 12LL) + v97 + 8;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 8LL))(v19, &v124);
    v98 = &v130;
    v20 = Vml::VmComMultiInstanceObject<FrApplyTaskEventsSink>::CreateInstance<int *>(&v98);
    Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
      &v108,
      v20);
    if ( !v108 )
    {
      LogFileHandle = -2147418113;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        VmlDebugTraceWithError(16800, &off_140907A00, 2147549183LL);
      goto LABEL_219;
    }
    try
    {
      Vml::VmComEventConnect(
        Pointer,
        (struct IUnknown *)&IID_IVmTaskEvents,
        (const struct _GUID *)((v108 + 24) & -(__int64)(v108 != 0)),
        &v137,
        dwCreationDisposition);
    }
    catch ( ... )
    {
      LODWORD(v98) = wil::details::in1diag3::Log_CaughtException(
                       retaddr,
                       (void *)0x2583,
                       (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\frctutilities.cpp",
                       v21);
      LogFileHandle = (int)v98;
      if ( (int)v98 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          VmlDebugTraceWithError(16800, &off_140907AF0, (unsigned int)LogFileHandle);
        v103 = (HANDLE)v109;
        v92 = v110;
        v97 = v107;
        v8 = v105;
        Pointer = (Vml *)IoStatusBlock.Pointer;
        goto LABEL_219;
      }
      v103 = (HANDLE)v109;
      v22 = v110;
      v92 = v110;
      v16 = v107;
      v97 = v107;
      v8 = (LPWSTR *)v110;
      Pointer = (Vml *)IoStatusBlock.Pointer;
      v9 = v95;
      v18 = v100;
LABEL_30:
      memset_0(v144, 0, 0x280u);
      FrCtLogParser::FrCtLogParser((FrCtLogParser *)v144);
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 240LL))(v16);
      v24 = L"F09261A9-577A-462C-8BE3-F8A20E170A6A";
      if ( v23 < 3 )
        v24 = L"00000000-0000-0000-0000-000000000000";
      std::wstring::wstring(&FsInformation, v24);
      v25 = std::wstring::wstring(v147, v8);
      LogFileHandle = FrCtApi::GetLogFileHandle(v25, &v93, 1);
      if ( LogFileHandle < 0 )
      {
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
LABEL_50:
          std::wstring::_Tidy_deallocate(&FsInformation);
          FrCtLogParser::~FrCtLogParser((FrCtLogParser *)v144);
          goto LABEL_219;
        }
        if ( (unsigned __int64)v8[3] <= 7 )
          v26 = v8;
        else
          v26 = *v22;
        v27 = &off_1408C0848;
LABEL_38:
        *(_QWORD *)dwFlagsAndAttributes = v26;
        dwCreationDisposition = (unsigned int *)v18;
        VmlDebugTraceWithError(16800, v27, (unsigned int)LogFileHandle);
        goto LABEL_50;
      }
      if ( *((_QWORD *)&v132 + 1) == v133 )
      {
        std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(
          &v132,
          *((_QWORD *)&v132 + 1),
          &v93);
      }
      else
      {
        **((_QWORD **)&v132 + 1) = v93;
        *((_QWORD *)&v132 + 1) += 8LL;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        VmlDebugTraceEx(49568, &off_1408C0830);
      v28 = FrCtLogParser::Initialize(v144, &v132, 0);
      LogFileHandle = v28;
      if ( v28 < 0 )
      {
        if ( (unsigned int)FrCtLogParser::IsLogFileHeaderValidationError(v28) )
        {
          LogFileHandle = -2147188548;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v29 = pszPath;
            if ( v129.m128i_i64[1] > 7uLL )
              v29 = (LPWSTR *)pszPath[0];
            *(_QWORD *)dwFlagsAndAttributes = v29;
            dwCreationDisposition = (unsigned int *)v100;
            VmlDebugTraceWithError(16800, &off_1408C0740, 2147778748LL);
          }
        }
        else if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          VmlDebugTraceWithError(16800, &off_140907AC0, (unsigned int)LogFileHandle);
        }
        goto LABEL_50;
      }
      IoStatusBlock = *(_IO_STATUS_BLOCK *)(v145 + 76);
      Vml::VmGuid::ToString((struct _GUID *)&IoStatusBlock, &Src);
      IoStatusBlock = *(_IO_STATUS_BLOCK *)(v145 + 60);
      Vml::VmGuid::ToString((struct _GUID *)&IoStatusBlock, &v138);
      LogFileHandle = FrCtLogApplier::GetLogGuidFromRepository(v97, v111, &v134);
      if ( LogFileHandle < 0 )
      {
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
          goto LABEL_50;
        v26 = pszPath;
        if ( v129.m128i_i64[1] > 7uLL )
          v26 = (LPWSTR *)pszPath[0];
        v27 = &off_140907AD8;
        goto LABEL_38;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        v30 = &v134;
        if ( v136 > 7 )
          v30 = (__int128 *)v134;
        v31 = pszPath;
        if ( v129.m128i_i64[1] > 7uLL )
          v31 = (LPWSTR *)pszPath[0];
        *(_QWORD *)dwFlagsAndAttributes = v30;
        dwCreationDisposition = (unsigned int *)v31;
        VmlDebugTraceEx(49568, &off_140907AA8);
      }
      v32 = &v138;
      if ( v140 > 7 )
        v32 = (__int128 *)v138;
      v33 = &v134;
      if ( v136 > 7 )
        v33 = (__int128 *)v134;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v33, v135, v32, v139) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
          VmlDebugTraceEx(49568, &off_1408C0800);
LABEL_252:
        std::wstring::_Tidy_deallocate(&FsInformation);
        FrCtLogParser::~FrCtLogParser((FrCtLogParser *)v144);
        goto LABEL_253;
      }
      if ( (unsigned __int8)std::operator!=<unsigned short>(&v134, &Src) )
      {
        p_FsInformation = &FsInformation;
        if ( FsInformation.m256i_i64[3] > 7uLL )
          p_FsInformation = (__m256i *)FsInformation.m256i_i64[0];
        v35 = &v134;
        if ( v136 > 7 )
          v35 = (__int128 *)v134;
        if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                 v35,
                                 v135,
                                 p_FsInformation,
                                 FsInformation.m256i_i64[2])
          || (unsigned int)FrCtLogApplier::IsFirstLogFileParentIdCheckEnabled() )
        {
          v36 = &v124;
          if ( v125.m128i_i64[1] > 7uLL )
            v36 = (__int128 *)v124;
          v102[0] = (__int64)v36;
          VmEventWrite<unsigned short const *,unsigned short const *>(
            &MSVM_VMMS_FR_LOGFILE_INVALID_SEQUENCE_ID,
            0xDu,
            (__int64)&v100);
          LogFileHandle = -2147188548;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v37 = pszPath;
            if ( v129.m128i_i64[1] > 7uLL )
              v37 = (LPWSTR *)pszPath[0];
            *(_QWORD *)dwFlagsAndAttributes = v37;
            dwCreationDisposition = (unsigned int *)v100;
            VmlDebugTraceWithError(16800, &off_140907988, 2147778748LL);
          }
          goto LABEL_50;
        }
      }
      if ( !((v146 - v145) >> 12) || !*(_QWORD *)(v145 + 96) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
          VmlDebugTraceEx(49568, &off_1408C0728);
        goto LABEL_252;
      }
      std::wstring::_Tidy_deallocate(&FsInformation);
      FrCtLogParser::~FrCtLogParser((FrCtLogParser *)v144);
      LODWORD(v93) = 0;
      IsFileOnSMBShare = FrUtilities::IsFileOnSMBShare(a5, &v93);
      v39 = v93;
      if ( IsFileOnSMBShare < 0 )
        v39 = 0;
      LODWORD(v93) = v39;
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        if ( (unsigned __int64)v8[3] <= 7 )
          v40 = v8;
        else
          v40 = *v92;
        if ( *(_QWORD *)v99 <= 7u )
          v41 = a5;
        else
          v41 = *(unsigned __int16 **)v94;
        v42 = v93;
        *(_QWORD *)dwFlagsAndAttributes = v40;
        dwCreationDisposition = (unsigned int *)v41;
        VmlDebugTraceEx(49568, &off_1408C08F0);
      }
      else
      {
        v42 = v93;
      }
      *((_QWORD *)&v116 + 1) = &v130;
      LODWORD(v115) = 20971520;
      HIDWORD(v115) = v42 != 0 ? 32 : 256;
      *(_QWORD *)&v116 = &v143;
      v120 = -2147467259;
      hHandle = CreateEventW(0, 1, 0, 0);
      if ( !hHandle )
      {
        LastError = GetLastError();
        LogFileHandle = LastError;
        if ( LastError > 0 )
          LogFileHandle = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          VmlDebugTraceWithError(16800, &off_140907970, (unsigned int)LogFileHandle);
        goto LABEL_174;
      }
      if ( !v104 )
      {
LABEL_169:
        v119 = GUID_NULL;
        v120 = -2147467259;
        if ( !ResetEvent(hHandle) )
        {
          v60 = GetLastError();
          LogFileHandle = v60;
          if ( v60 > 0 )
            LogFileHandle = (unsigned __int16)v60 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            dwCreationDisposition = (unsigned int *)v18;
            VmlDebugTraceWithError(16800, &off_1409079A0, (unsigned int)LogFileHandle);
          }
          goto LABEL_174;
        }
        v61 = 0;
        LODWORD(v98) = 0;
        if ( hObject != (HANDLE)-1LL && !CloseHandle(hObject) )
        {
          v62 = GetLastError();
          v63 = v62;
          if ( v62 > 0 )
            v63 = (unsigned __int16)v62 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            if ( *(_QWORD *)v99 <= 7u )
              HIDWORD(v64) = HIDWORD(a5);
            else
              v64 = *(unsigned __int16 **)v94;
            dwFlagsAndAttributes[1] = HIDWORD(v64);
            dwCreationDisposition = (unsigned int *)v18;
            VmlDebugTraceWithError(16800, &off_1408C06B0, v63);
          }
          v61 = (int)v98;
        }
        if ( !(_DWORD)v93 )
        {
          LODWORD(v98) = 1;
          FrCtUtilities::GetVhdAlignment(a5);
          v61 = (_DWORD)v98 != 0;
        }
        v65 = v97 + 8 + *(int *)(*(_QWORD *)v102[0] + 12LL);
        *(_OWORD *)v102 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 24LL))(v65);
        dwFlagsAndAttributes[0] = a8;
        LogFileHandle = FrCtUtilities::OpenApplyDiskHandle(v102, a5, v106, v61);
        if ( LogFileHandle < 0 )
        {
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_219;
          if ( *(_QWORD *)v99 <= 7u )
            v53 = a5;
          else
            v53 = *(unsigned __int16 **)v94;
          v54 = &off_1408C08C0;
          goto LABEL_139;
        }
        v66 = *v106;
        if ( !*v106 )
          v66 = v106[1] - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v123 = v66 != 0;
        v121 = hObject;
        std::wstring::operator=(v122, a5);
        LogFileHandle = FrCtUtilities::ApplyLogsToVirtualDisk(&v132, &v121, &v115);
        if ( LogFileHandle < 0 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v67 = pszPath;
            if ( v129.m128i_i64[1] > 7uLL )
              v67 = (LPWSTR *)pszPath[0];
            if ( (unsigned __int64)v8[3] <= 7 )
              v68 = (unsigned int *)v8;
            else
              v68 = (unsigned int *)*v92;
            *(_QWORD *)dwFlagsAndAttributes = v67;
            dwCreationDisposition = v68;
            VmlDebugTraceEx(16800, &off_1408C0770);
          }
          goto LABEL_219;
        }
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          LODWORD(dwCreationDisposition) = v118;
          VmlDebugTraceEx(49568, &off_140907910);
        }
        if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
        {
          v69 = GetLastError();
          LogFileHandle = v69;
          if ( v69 > 0 )
            LogFileHandle = (unsigned __int16)v69 | 0x80070000;
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_214;
          LODWORD(dwCreationDisposition) = LogFileHandle;
          v70 = &off_1409078F8;
          v71 = 16800;
        }
        else
        {
          LogFileHandle = v120;
          if ( !(unsigned int)VmlIsDebugTraceEnabled(49568) )
          {
LABEL_214:
            if ( LogFileHandle >= 0 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
                VmlDebugTraceEx(49568, &off_1408C08A8);
LABEL_253:
              FrCtApi::CloseAndClearLogFileHandles(&v132);
              if ( v103 != (HANDLE)-1LL && !CloseHandle(v103) )
              {
                v79 = GetLastError();
                v80 = v79;
                if ( v79 > 0 )
                  v80 = (unsigned __int16)v79 | 0x80070000;
                if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                  VmlDebugTraceWithError(16800, &off_1408C0860, v80);
              }
              if ( hObject != (HANDLE)-1LL && !CloseHandle(hObject) )
              {
                v81 = GetLastError();
                v82 = v81;
                if ( v81 > 0 )
                  v82 = (unsigned __int16)v81 | 0x80070000;
                if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                  VmlDebugTraceWithError(16800, &off_1408C07A0, v82);
              }
              if ( hHandle != (HANDLE)-1LL && !CloseHandle(hHandle) )
              {
                v83 = GetLastError();
                v84 = v83;
                if ( v83 > 0 )
                  v84 = (unsigned __int16)v83 | 0x80070000;
                if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                  VmlDebugTraceWithError(16800, &off_140907940, v84);
              }
              v126 = 0;
              if ( LogFileHandle < 0 )
                goto LABEL_284;
              v85 = 0;
              v86 = Pointer;
              v87 = v97;
              do
              {
                LogFileHandle = (*(__int64 (__fastcall **)(Vml *, int *))(*(_QWORD *)v86 + 336LL))(v86, &v126);
                v88 = v126;
                if ( LogFileHandle >= 0 && !v126 )
                {
                  LogFileHandle = FrCtLogApplier::WriteLogGuidToRepository(v87, &v138, v111);
                  v88 = v126;
                }
                ++v85;
              }
              while ( v85 < 3 && LogFileHandle == -2147023436 && !v88 );
              if ( v88 )
              {
                LogFileHandle = -2147213311;
              }
              else if ( LogFileHandle >= 0 )
              {
LABEL_284:
                CompleteTask<IVmmsVirtualMachineObject *>(
                  *(int *)(*(_QWORD *)v112 + 12LL) + v97 + 8,
                  Pointer,
                  (unsigned int)LogFileHandle,
                  0);
                std::wstring::_Tidy_deallocate(&v124);
                goto LABEL_285;
              }
              if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                VmlDebugTraceEx(16800, &off_140907928);
              goto LABEL_284;
            }
            if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
            {
              dwFlagsAndAttributes[0] = v118;
              dwCreationDisposition = (unsigned int *)v18;
              VmlDebugTraceWithError(16800, &off_1408C0818, (unsigned int)LogFileHandle);
            }
LABEL_219:
            _snwprintf_s<16>(
              v147,
              16,
              L"%%%%%u",
              LogFileHandle & 0xEFFFFFFF,
              dwCreationDisposition,
              *(_QWORD *)dwFlagsAndAttributes);
            _snwprintf_s<16>(v148, 16, L"0x%08X", LogFileHandle & 0xEFFFFFFF);
            if ( LogFileHandle == -2147188481 )
            {
              v72 = v99;
              if ( *(_QWORD *)v99 <= 7u )
                v73 = a5;
              else
                v73 = *(unsigned __int16 **)v94;
              v102[0] = (__int64)v73;
              v74 = &v124;
              if ( v125.m128i_i64[1] > 7uLL )
                v74 = (__int128 *)v124;
              IoStatusBlock.Pointer = v74;
              VmEventWrite<unsigned short const * &,unsigned short const * &,unsigned short (&)[16],unsigned short (&)[16],unsigned short const * const &>(
                &MSVM_VMMS_FR_LOGFILE_DISK_OFFSET_MISMATCH,
                0xDu,
                (__int64)&v100,
                v147,
                v148,
                (__int64)v102);
            }
            else
            {
              if ( LogFileHandle == -2147213311 )
              {
                std::wstring::wstring(&FsInformation, L"ApplyLog");
                if ( v104 )
                  std::wstring::append(&FsInformation, L" and GenerateUndoLog");
                if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
                  VmlDebugTraceEx(49568, &off_140907958);
                std::wstring::_Tidy_deallocate(&FsInformation);
              }
              v72 = v99;
            }
            FrEventDescriptorFromErrorCode = GetFrEventDescriptorFromErrorCode(LogFileHandle);
            if ( FrEventDescriptorFromErrorCode )
            {
              v76 = &v124;
              if ( v125.m128i_i64[1] > 7uLL )
                v76 = (__int128 *)v124;
              v102[0] = (__int64)v76;
              VmEventWrite<unsigned short const *,unsigned short const *>(
                FrEventDescriptorFromErrorCode,
                0xDu,
                (__int64)&v100);
            }
            else
            {
              if ( *(_QWORD *)v72 <= 7u )
                v77 = a5;
              else
                v77 = *(unsigned __int16 **)v94;
              v102[0] = (__int64)v77;
              if ( (unsigned __int64)v8[3] > 7 )
                v8 = *v92;
              IoStatusBlock.Pointer = v8;
              v78 = (LPWSTR *)&v124;
              if ( v125.m128i_i64[1] > 7uLL )
                v78 = (LPWSTR *)v124;
              v105 = v78;
              VmEventWrite<unsigned short const *,unsigned short const * &,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
                &MSVM_VMMS_FR_CTAPI_APPLY_LOGFILE_ERROR,
                0xDu,
                (__int64)&v100,
                v147,
                v148,
                (__int64)&IoStatusBlock,
                (__int64)v102);
            }
            if ( (unsigned int)FrCtLogParser::IsLogFileHeaderValidationError(LogFileHandle) )
              LogFileHandle = -2147188548;
            if ( v104 && memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
            {
              *(GUID *)v102 = Buf1;
              FrCtUtilities::RemoveSmartBitmap(v102);
            }
            goto LABEL_253;
          }
          LODWORD(dwCreationDisposition) = v118;
          v70 = &off_1409078E0;
          v71 = 49568;
        }
        VmlDebugTraceEx(v71, v70);
        goto LABEL_214;
      }
      if ( *((_QWORD *)v9 + 3) <= 7u )
        v44 = v9;
      else
        v44 = *v96;
      FileW = CreateFileW(v44, 0xC0000000, 1u, 0, 3u, 0xC0000000, 0);
      v103 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v46 = GetLastError();
        LogFileHandle = v46;
        if ( v46 > 0 )
          LogFileHandle = (unsigned __int16)v46 | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          if ( *((_QWORD *)v95 + 3) <= 7u )
            v47 = v95;
          else
            v47 = *(LPCWSTR *)v95;
          v48 = &off_1408C0788;
LABEL_114:
          *(_QWORD *)dwFlagsAndAttributes = v47;
          dwCreationDisposition = (unsigned int *)v18;
          VmlDebugTraceWithError(16800, v48, (unsigned int)LogFileHandle);
          goto LABEL_174;
        }
        goto LABEL_174;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        *(_QWORD *)dwFlagsAndAttributes = FileW;
        VmlDebugTraceEx(49568, &off_1408C0758);
      }
      IoStatusBlock = 0;
      memset(&FsInformation, 0, 28);
      if ( NtQueryVolumeInformationFile(
             FileW,
             &IoStatusBlock,
             &FsInformation,
             0x1Cu,
             FileFsMaximumInformation|FileFsVolumeInformation) >= 0
        && FsInformation.m256i_i32[0] == 512 )
      {
        CloseHandle(FileW);
        v49 = *((_QWORD *)v9 + 3) <= 7u ? v9 : *v96;
        v103 = CreateFileW(v49, 0xC0000000, 1u, 0, 3u, 0x60000000u, 0);
        if ( v103 == (HANDLE)-1LL )
        {
          v50 = GetLastError();
          LogFileHandle = v50;
          if ( v50 > 0 )
            LogFileHandle = (unsigned __int16)v50 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            if ( *((_QWORD *)v95 + 3) <= 7u )
              v47 = v95;
            else
              v47 = *(LPCWSTR *)v95;
            v48 = &off_1408C08D8;
            goto LABEL_114;
          }
LABEL_174:
          if ( LogFileHandle >= 0 )
            goto LABEL_253;
          goto LABEL_219;
        }
      }
      LogFileHandle = FrCtUtilities::ExtractGuidFromLogFileName(v9, &v119);
      if ( LogFileHandle < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          VmlDebugTraceWithError(16800, &off_1408C0890, (unsigned int)LogFileHandle);
        goto LABEL_219;
      }
      Buf1 = v119;
      v51 = v97 + 8 + *(int *)(*(_QWORD *)v102[0] + 12LL);
      IoStatusBlock = *(_IO_STATUS_BLOCK *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 24LL))(v51);
      dwFlagsAndAttributes[0] = a8;
      v52 = v106;
      LogFileHandle = FrCtUtilities::OpenApplyDiskHandle(&IoStatusBlock, a5, v106, 0);
      if ( LogFileHandle < 0 )
      {
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
          goto LABEL_219;
        if ( *(_QWORD *)v99 <= 7u )
          v53 = a5;
        else
          v53 = *(unsigned __int16 **)v94;
        v54 = &off_1408C07E8;
LABEL_139:
        *(_QWORD *)dwFlagsAndAttributes = v53;
        dwCreationDisposition = (unsigned int *)v18;
        VmlDebugTraceWithError(16800, v54, (unsigned int)LogFileHandle);
        goto LABEL_219;
      }
      v55 = *v52;
      if ( !*v52 )
        v55 = v52[1] - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v123 = v55 != 0;
      v121 = hObject;
      std::wstring::operator=(v122, a5);
      LogFileHandle = FrCtUtilities::GenerateUndoLog(
                        *(void **)v132,
                        v103,
                        (struct _APPLY_DISK_PARAMETERS *)&v121,
                        (struct _APPLY_LOG_PARAMETERS *)&v115);
      if ( LogFileHandle < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          v56 = v95;
          if ( *((_QWORD *)v95 + 3) > 7u )
            v56 = *(LPCWSTR *)v95;
          if ( (unsigned __int64)v8[3] <= 7 )
            v57 = (unsigned int *)v8;
          else
            v57 = (unsigned int *)*v92;
          *(_QWORD *)dwFlagsAndAttributes = v56;
          dwCreationDisposition = v57;
          VmlDebugTraceEx(16800, &off_1408C07D0);
        }
        goto LABEL_219;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        LODWORD(dwCreationDisposition) = v118;
        VmlDebugTraceEx(49568, &off_1409079D0);
      }
      if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
      {
        v58 = GetLastError();
        LogFileHandle = v58;
        if ( v58 > 0 )
          LogFileHandle = (unsigned __int16)v58 | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          dwCreationDisposition = (unsigned int *)v18;
          VmlDebugTraceWithError(16800, &off_1409079B8, (unsigned int)LogFileHandle);
        }
      }
      else
      {
        LogFileHandle = v120;
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          LODWORD(dwCreationDisposition) = v118;
          VmlDebugTraceEx(49568, &off_1409079E8);
        }
        if ( LogFileHandle < 0 )
          goto LABEL_167;
        LogFileHandle = (*(__int64 (__fastcall **)(Vml *, __int64))(*(_QWORD *)Pointer + 80LL))(Pointer, 50);
      }
      if ( LogFileHandle >= 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          if ( *((_QWORD *)v95 + 3) <= 7u )
            v59 = v95;
          else
            v59 = *(LPCWSTR *)v95;
          *(_QWORD *)dwFlagsAndAttributes = v59;
          LODWORD(dwCreationDisposition) = v118;
          VmlDebugTraceEx(49568, &off_1408C0878);
        }
        goto LABEL_169;
      }
LABEL_167:
      if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
        goto LABEL_219;
      dwFlagsAndAttributes[0] = v118;
      dwCreationDisposition = (unsigned int *)v18;
      VmlDebugTraceWithError(16800, &off_1408C07B8, (unsigned int)LogFileHandle);
      goto LABEL_174;
    }
    v22 = v92;
    goto LABEL_30;
  }
  if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
    goto LABEL_14;
  v11 = &off_140907A60;
LABEL_10:
  LogFileHandle = -2147024809;
  VmlDebugTraceWithError(16800, v11, 2147942487LL);
LABEL_285:
  Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v108);
  std::vector<void *>::_Tidy(&v132);
  std::wstring::_Tidy_deallocate(v122);
  std::wstring::_Tidy_deallocate(pszPath);
  std::wstring::_Tidy_deallocate(&v134);
  std::wstring::_Tidy_deallocate(&v138);
  std::wstring::_Tidy_deallocate(&Src);
  return (unsigned int)LogFileHandle;
}

```

## disassembly

```asm
0x140392c44  mov     r11, rsp
0x140392c47  push    rbx
0x140392c48  push    rsi
0x140392c49  push    rdi
0x140392c4a  push    r12
0x140392c4c  push    r13
0x140392c4e  push    r14
0x140392c50  push    r15
0x140392c52  sub     rsp, 570h
0x140392c59  mov     rax, cs:__security_cookie
0x140392c60  xor     rax, rsp
0x140392c63  mov     [rsp+5A8h+var_48], rax
0x140392c6b  mov     [rsp+5A8h+var_508], r9
0x140392c73  mov     rax, rdx
0x140392c76  mov     [rsp+5A8h+var_550], rdx
0x140392c7b  mov     rdx, rcx
0x140392c7e  mov     [rsp+5A8h+var_528], rcx
0x140392c86  mov     rcx, [rsp+5A8h+lpFileName]
0x140392c8e  mov     [rsp+5A8h+var_4E0], rcx
0x140392c96  mov     [rsp+5A8h+var_530], rcx
0x140392c9b  mov     [rsp+5A8h+var_4B0], rax
0x140392ca3  mov     r12, [rsp+5A8h+arg_20]
0x140392cab  mov     [rsp+5A8h+var_540], r12
0x140392cb0  mov     [rsp+5A8h+var_4C8], rdx
0x140392cb8  mov     r13, rax
0x140392cbb  mov     [rsp+5A8h+var_4D8], rax
0x140392cc3  mov     [rsp+5A8h+var_4A8], r8
0x140392ccb  mov     qword ptr [rsp+5A8h+IoStatusBlock], r9
0x140392cd3  mov     [rsp+5A8h+Path], r12
0x140392cd8  mov     r14, rcx
0x140392cdb  mov     [rsp+5A8h+var_538], rcx
0x140392ce0  mov     rbx, [rsp+5A8h+arg_30]
0x140392ce8  mov     [rsp+5A8h+var_4D0], rbx
0x140392cf0  xorps   xmm0, xmm0
0x140392cf3  movups  [rsp+5A8h+Src], xmm0
0x140392cfb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140392d03  movdqu  [rsp+5A8h+var_328], xmm1
0x140392d0c  xor     edi, edi
0x140392d0e  mov     word ptr [rsp+5A8h+Src], di
0x140392d16  movups  [rsp+5A8h+var_358], xmm0
0x140392d1e  mov     [r11-348h], rdi
0x140392d25  lea     r15d, [rdi+7]
0x140392d29  mov     [r11-340h], r15
0x140392d30  mov     word ptr [rsp+5A8h+var_358], di
0x140392d38  movups  [rsp+5A8h+var_380], xmm0
0x140392d40  mov     [r11-370h], rdi
0x140392d47  mov     [r11-368h], r15
0x140392d4e  mov     word ptr [rsp+5A8h+var_380], di
0x140392d56  movups  xmmword ptr [rsp+5A8h+pszPath], xmm0
0x140392d5e  movdqu  [rsp+5A8h+var_3D0], xmm1
0x140392d67  mov     word ptr [rsp+5A8h+pszPath], di
0x140392d6f  mov     [r11-318h], rdi
0x140392d76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140392d7a  mov     [r11-488h], rbx
0x140392d81  mov     [rsp+5A8h+var_3C0], edi
0x140392d88  mov     [r11-480h], rdi
0x140392d8f  movdqu  [rsp+5A8h+var_478], xmm0
0x140392d98  mov     [r11-468h], rbx
0x140392d9f  mov     [rsp+5A8h+var_460], edi
0x140392da6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140392dad  movdqu  [rsp+5A8h+var_45C], xmm0
0x140392db6  mov     [rsp+5A8h+var_44C], 80004005h
0x140392dc1  lea     rcx, [r11-448h]; this
0x140392dc8  call    ??0_APPLY_DISK_PARAMETERS@@QEAA@XZ; _APPLY_DISK_PARAMETERS::_APPLY_DISK_PARAMETERS(void)
0x140392dcd  nop
0x140392dce  xorps   xmm1, xmm1
0x140392dd1  movdqu  [rsp+5A8h+var_398], xmm1
0x140392dda  mov     [rsp+5A8h+var_388], rdi
0x140392de2  mov     [rsp+5A8h+var_548], rbx
0x140392de7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140392dee  movdqu  [rsp+5A8h+Buf1], xmm0
0x140392df7  mov     [rsp+5A8h+var_4C0], rdi
0x140392dff  mov     dword ptr [rsp+5A8h+var_360.lpVtbl], edi
0x140392e06  lea     rax, [r12+18h]
0x140392e0b  mov     [rsp+5A8h+var_518], rax
0x140392e13  cmp     [rax], r15
0x140392e16  jbe     short loc_140392E1E
0x140392e18  mov     rcx, [r12]
0x140392e1c  jmp     short loc_140392E21
0x140392e1e  mov     rcx, r12; unsigned __int16 *
0x140392e21  mov     qword ptr [rsp+5A8h+dwCreationDisposition], rdi; unsigned int *
0x140392e26  xor     r9d, r9d; unsigned int *
0x140392e29  xor     r8d, r8d; int *
0x140392e2c  xor     edx, edx; enum _VHD_FORMAT *
0x140392e2e  call    ?GetVhdExtensionInfo@@YAHPEBGPEAW4_VHD_FORMAT@@PEAHPEAK2@Z; GetVhdExtensionInfo(ushort const *,_VHD_FORMAT *,int *,ulong *,int *)
0x140392e33  test    eax, eax
0x140392e35  jnz     short loc_140392E52
0x140392e37  mov     r14d, 41A0h
0x140392e3d  mov     ecx, r14d
0x140392e40  call    VmlIsDebugTraceEnabled
0x140392e45  test    eax, eax
0x140392e47  jz      short loc_140392EB0
0x140392e49  lea     rdx, off_140907A60; "Invalid vhd file extension"
0x140392e50  jmp     short loc_140392E76
0x140392e52  cmp     [rsp+5A8h+var_528], 0
0x140392e5b  jnz     short loc_140392E8B
0x140392e5d  mov     r14d, 41A0h
0x140392e63  mov     ecx, r14d
0x140392e66  call    VmlIsDebugTraceEnabled
0x140392e6b  test    eax, eax
0x140392e6d  jz      short loc_140392EB0
0x140392e6f  lea     rdx, off_140907A18; "Invalid VM Argument"
0x140392e76  mov     esi, 80070057h
0x140392e7b  mov     r8d, esi
0x140392e7e  mov     ecx, r14d
0x140392e81  call    VmlDebugTraceWithError
0x140392e86  jmp     loc_1403949EF
0x140392e8b  cmp     [rsp+5A8h+var_508], rdi
0x140392e93  jnz     short loc_140392EBA
0x140392e95  mov     r14d, 41A0h
0x140392e9b  mov     ecx, r14d
0x140392e9e  call    VmlIsDebugTraceEnabled
0x140392ea3  test    eax, eax
0x140392ea5  jz      short loc_140392EB0
0x140392ea7  lea     rdx, off_140907A30; "Invalid task argument"
0x140392eae  jmp     short loc_140392E76
0x140392eb0  mov     esi, 80070057h
0x140392eb5  jmp     loc_1403949EF
0x140392eba  mov     [rsp+5A8h+var_4E8], rbx
0x140392ec2  mov     [rsp+5A8h+var_4B8], rbx
0x140392eca  mov     rdx, r12
0x140392ecd  lea     rcx, [rsp+5A8h+pszPath]
0x140392ed5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140392eda  lea     rcx, [rsp+5A8h+pszPath]
0x140392ee2  cmp     qword ptr [rsp+5A8h+var_3D0+8], r15
0x140392eea  cmova   rcx, [rsp+5A8h+pszPath]; pszPath
0x140392ef3  call    cs:__imp_PathStripPathW
0x140392efa  nop     dword ptr [rax+rax+00h]
0x140392eff  lea     rax, [rsp+5A8h+pszPath]
0x140392f07  cmp     qword ptr [rsp+5A8h+var_3D0+8], r15
0x140392f0f  cmova   rax, [rsp+5A8h+pszPath]
0x140392f18  mov     rdx, rbx
0x140392f1b  inc     rdx
0x140392f1e  cmp     [rax+rdx*2], di
0x140392f22  jnz     short loc_140392F1B
0x140392f24  lea     rcx, [rsp+5A8h+pszPath]; Src
0x140392f2c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140392f31  xorps   xmm0, xmm0
0x140392f34  movups  [rsp+5A8h+var_418], xmm0
0x140392f3c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140392f44  movdqu  [rsp+5A8h+var_408], xmm1
0x140392f4d  mov     word ptr [rsp+5A8h+var_418], di
0x140392f55  mov     rsi, [rsp+5A8h+var_528]
0x140392f5d  lea     rbx, [rsi+8]
0x140392f61  mov     [rsp+5A8h+var_4F8], rbx
0x140392f69  mov     [rsp+5A8h+var_4A0], rbx
0x140392f71  mov     rax, [rbx]
0x140392f74  movsxd  rcx, dword ptr [rax+0Ch]
0x140392f78  add     rcx, 8
0x140392f7c  add     rcx, rsi
0x140392f7f  mov     rax, [rcx]
0x140392f82  mov     rax, [rax+20h]
0x140392f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140392f8b  mov     r12, rax
0x140392f8e  mov     [rsp+5A8h+var_510], rax
0x140392f96  mov     rcx, [rbx]
0x140392f99  movsxd  rdx, dword ptr [rcx+0Ch]
0x140392f9d  lea     rcx, [rsi+8]
0x140392fa1  add     rcx, rdx
0x140392fa4  mov     rdx, [rcx]
0x140392fa7  mov     rax, [rdx+8]
0x140392fab  lea     rdx, [rsp+5A8h+var_418]
0x140392fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140392fb8  lea     rax, [rsp+5A8h+var_3C0]
0x140392fc0  mov     [rsp+5A8h+var_520], rax
0x140392fc8  lea     rcx, [rsp+5A8h+var_520]
0x140392fd0  call    ??$CreateInstance@PEAH@?$VmComMultiInstanceObject@VFrApplyTaskEventsSink@@@Vml@@SAPEAVFrApplyTaskEventsSink@@$$QEAPEAH@Z; Vml::VmComMultiInstanceObject<FrApplyTaskEventsSink>::CreateInstance<int *>(int * &&)
0x140392fd5  mov     rdx, rax
0x140392fd8  lea     rcx, [rsp+5A8h+var_4C0]
0x140392fe0  call    ??$Attach@V?$VmComEnum@UIEnumConnectionPoints@@PEAUIConnectionPoint@@V?$VmComPtr@UIConnectionPoint@@@Vml@@V?$vector@V?$VmComPtr@UIConnectionPoint@@@Vml@@V?$allocator@V?$VmComPtr@UIConnectionPoint@@@Vml@@@std@@@std@@@Vml@@@?$VmComPtr@V?$VmComEnum@UIEnumConnectionPoints@@PEAUIConnectionPoint@@V?$VmComPtr@UIConnectionPoint@@@Vml@@V?$vector@V?$VmComPtr@UIConnectionPoint@@@Vml@@V?$allocator@V?$VmComPtr@UIConnectionPoint@@@Vml@@@std@@@std@@@Vml@@@Vml@@QEAAXPEAV?$VmComEnum@UIEnumConnectionPoints@@PEAUIConnectionPoint@@V?$VmComPtr@UIConnectionPoint@@@Vml@@V?$vector@V?$VmComPtr@UIConnectionPoint@@@Vml@@V?$allocator@V?$VmComPtr@UIConnectionPoint@@@Vml@@@std@@@std@@@1@@Z; Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>> *)
0x140392fe5  mov     rax, [rsp+5A8h+var_4C0]
0x140392fed  test    rax, rax
0x140392ff0  jnz     short loc_140393024
0x140392ff2  mov     esi, 8000FFFFh
0x140392ff7  mov     r14d, 41A0h
0x140392ffd  mov     ecx, r14d
0x140393000  call    VmlIsDebugTraceEnabled
0x140393005  test    eax, eax
0x140393007  jz      loc_140394405
0x14039300d  mov     r8d, esi
0x140393010  lea     rdx, off_140907A00; "Unable to create FrApplyTaskEventsSink"
0x140393017  mov     ecx, r14d
0x14039301a  call    VmlDebugTraceWithError
0x14039301f  jmp     loc_140394405
0x140393024  lea     rcx, [rax+18h]
0x140393028  neg     rax
0x14039302b  sbb     r8, r8
0x14039302e  and     r8, rcx; struct _GUID *
0x140393031  lea     r9, [rsp+5A8h+var_360]; struct IUnknown *
0x140393039  lea     rdx, IID_IVmTaskEvents; struct IUnknown *
0x140393040  mov     rcx, [rsp+5A8h+var_508]; this
0x140393048  call    ?VmComEventConnect@Vml@@YAXPEAUIUnknown@@AEBU_GUID@@0PEAK@Z; Vml::VmComEventConnect(IUnknown *,_GUID const &,IUnknown *,ulong *)
0x14039304d  nop
0x14039304e  mov     rbx, [rsp+5A8h+var_550]
0x140393053  jmp     loc_14039312C
0x140393058  mov     esi, dword ptr [rsp+5A8h+var_520]
0x14039305f  xor     edi, edi
0x140393061  test    esi, esi
0x140393063  jns     short loc_1403930D9
0x140393065  mov     r14d, 41A0h
0x14039306b  mov     ecx, r14d
0x14039306e  call    VmlIsDebugTraceEnabled
0x140393073  test    eax, eax
0x140393075  jz      short loc_140393089
0x140393077  mov     r8d, esi
0x14039307a  lea     rdx, off_140907AF0; "Unable to create FrApplyTaskEventsSink"
0x140393081  mov     ecx, r14d
0x140393084  call    VmlDebugTraceWithError
0x140393089  mov     r15d, 7
0x14039308f  mov     rdx, [rsp+5A8h+var_4B8]
0x140393097  mov     [rsp+5A8h+var_4E8], rdx
0x14039309f  mov     rax, [rsp+5A8h+var_4B0]
0x1403930a7  mov     [rsp+5A8h+var_550], rax
0x1403930ac  mov     rax, [rsp+5A8h+var_4C8]
0x1403930b4  mov     [rsp+5A8h+var_528], rax
0x1403930bc  mov     r13, [rsp+5A8h+var_4D8]
0x1403930c4  mov     rax, qword ptr [rsp+5A8h+IoStatusBlock]
0x1403930cc  mov     [rsp+5A8h+var_508], rax
0x1403930d4  jmp     loc_140394405
0x1403930d9  mov     r15d, 7
0x1403930df  mov     rdx, [rsp+5A8h+var_4B8]
0x1403930e7  mov     [rsp+5A8h+var_4E8], rdx
0x1403930ef  mov     rbx, [rsp+5A8h+var_4B0]
0x1403930f7  mov     [rsp+5A8h+var_550], rbx
0x1403930fc  mov     rsi, [rsp+5A8h+var_4C8]
0x140393104  mov     [rsp+5A8h+var_528], rsi
0x14039310c  mov     r13, rbx
0x14039310f  mov     rax, qword ptr [rsp+5A8h+IoStatusBlock]
0x140393117  mov     [rsp+5A8h+var_508], rax
0x14039311f  mov     r14, [rsp+5A8h+var_538]
0x140393124  mov     r12, [rsp+5A8h+var_510]
0x14039312c  xor     edx, edx; Val
0x14039312e  mov     r8d, 280h; Size
0x140393134  lea     rcx, [rsp+5A8h+var_308]; void *
0x14039313c  call    memset_0
0x140393141  lea     rcx, [rsp+5A8h+var_308]; this
0x140393149  call    ??0FrCtLogParser@@QEAA@XZ; FrCtLogParser::FrCtLogParser(void)
0x14039314e  nop
0x14039314f  mov     rax, [rsi]
0x140393152  mov     rcx, rsi
0x140393155  mov     rax, [rax+0F0h]
0x14039315c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140393161  lea     rcx, a00000000000000_0; "00000000-0000-0000-0000-000000000000"
0x140393168  lea     rdx, aF09261a9577a46; "F09261A9-577A-462C-8BE3-F8A20E170A6A"
0x14039316f  cmp     eax, 3
0x140393172  cmovl   rdx, rcx
0x140393176  lea     rcx, [rsp+5A8h+FsInformation]
0x14039317e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140393183  nop
0x140393184  mov     rdx, r13
0x140393187  lea     rcx, [rsp+5A8h+var_88]
0x14039318f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140393194  mov     r8d, 1
0x14039319a  lea     rdx, [rsp+5A8h+var_548]
0x14039319f  mov     rcx, rax
0x1403931a2  call    ?GetLogFileHandle@FrCtApi@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAPEAXH@Z; FrCtApi::GetLogFileHandle(std::wstring,void * &,int)
0x1403931a7  mov     esi, eax
0x1403931a9  test    eax, eax
0x1403931ab  jns     short loc_140393223
0x1403931ad  mov     r14d, 41A0h
0x1403931b3  mov     ecx, r14d
0x1403931b6  call    VmlIsDebugTraceEnabled
0x1403931bb  test    eax, eax
0x1403931bd  jz      short loc_140393203
0x1403931bf  cmp     [r13+18h], r15
0x1403931c3  jbe     short loc_1403931CA
0x1403931c5  mov     rax, [rbx]
0x1403931c8  jmp     short loc_1403931CD
0x1403931ca  mov     rax, r13
0x1403931cd  lea     rdx, off_1408C0848; "%ws::%ws Failed to open file LogFilePat"...
0x1403931d4  mov     qword ptr [rsp+5A8h+dwFlagsAndAttributes], rax
0x1403931d9  lea     r9, [rsp+5A8h+var_418]
0x1403931e1  cmp     qword ptr [rsp+5A8h+var_408+8], r15
0x1403931e9  mov     r8d, esi
0x1403931ec  mov     qword ptr [rsp+5A8h+dwCreationDisposition], r12
0x1403931f1  cmova   r9, qword ptr [rsp+5A8h+var_418]
0x1403931fa  mov     ecx, r14d
0x1403931fd  call    VmlDebugTraceWithError
0x140393202  nop
0x140393203  lea     rcx, [rsp+5A8h+FsInformation]
0x14039320b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140393210  nop
0x140393211  lea     rcx, [rsp+5A8h+var_308]; this
0x140393219  call    ??1FrCtLogParser@@UEAA@XZ; FrCtLogParser::~FrCtLogParser(void)
0x14039321e  jmp     loc_140394405
0x140393223  mov     rdx, qword ptr [rsp+5A8h+var_398+8]
0x14039322b  cmp     rdx, [rsp+5A8h+var_388]
0x140393233  jz      short loc_140393248
0x140393235  mov     rsi, [rsp+5A8h+var_548]
0x14039323a  mov     [rdx], rsi
0x14039323d  add     qword ptr [rsp+5A8h+var_398+8], 8
0x140393246  jmp     short loc_14039325F
0x140393248  lea     r8, [rsp+5A8h+var_548]
0x14039324d  lea     rcx, [rsp+5A8h+var_398]
0x140393255  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x14039325a  mov     rsi, [rsp+5A8h+var_548]
0x14039325f  mov     ebx, 0C1A0h
0x140393264  mov     ecx, ebx
0x140393266  call    VmlIsDebugTraceEnabled
0x14039326b  test    eax, eax
  ... truncated ...
```
