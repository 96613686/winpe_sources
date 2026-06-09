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
  __int64 v11; // r9
  wchar_t **v12; // rdx
  signed int LogFileHandle; // esi
  WCHAR *v14; // rcx
  LPWSTR *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // r12
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r9
  const char *v23; // r9
  LPWSTR **v24; // rbx
  __int64 v25; // r9
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rax
  LPWSTR *v29; // rax
  wchar_t **v30; // rdx
  __int128 *v31; // r9
  __int64 v32; // rsi
  LPWSTR *v33; // r8
  int v34; // eax
  LPWSTR *v35; // rax
  __int128 *v36; // r9
  __int64 v37; // r9
  __int128 *v38; // rcx
  LPWSTR *v39; // rax
  __int128 *v40; // r8
  __int128 *v41; // r8
  __int128 *v42; // rcx
  unsigned __int16 *v43; // rax
  __int128 *v44; // r8
  __m256i *p_FsInformation; // r8
  __int128 *v46; // rcx
  __int128 *v47; // rax
  LPWSTR *v48; // rax
  __int128 *v49; // r9
  int IsFileOnSMBShare; // esi
  int v51; // eax
  LPWSTR *v52; // rcx
  unsigned __int16 *v53; // rax
  __int128 *v54; // r8
  int v55; // esi
  signed int LastError; // eax
  __int64 v57; // r9
  const WCHAR *v58; // rcx
  HANDLE FileW; // rsi
  signed int v60; // eax
  LPCWSTR v61; // rax
  wchar_t **v62; // rdx
  __int128 *v63; // r9
  __int128 *v64; // r8
  const WCHAR *v65; // rcx
  signed int v66; // eax
  LPCWSTR v67; // r9
  __int64 v68; // rcx
  unsigned __int64 *v69; // r14
  unsigned __int16 *v70; // rax
  wchar_t **v71; // rdx
  __int128 *v72; // r9
  unsigned __int64 v73; // rcx
  LPCWSTR v74; // rdx
  unsigned int *v75; // rcx
  __int128 *v76; // r8
  __int128 *v77; // r8
  signed int v78; // eax
  __int128 *v79; // r9
  __int128 *v80; // r8
  LPCWSTR v81; // rax
  __int128 *v82; // r8
  __int128 *v83; // r9
  signed int v84; // eax
  __int128 *v85; // r9
  BOOL v86; // esi
  signed int v87; // eax
  unsigned int v88; // esi
  unsigned __int16 *v89; // rax
  __int128 *v90; // r9
  __int64 v91; // rcx
  unsigned __int64 v92; // rcx
  LPWSTR *v93; // rax
  unsigned int *v94; // rcx
  __int128 *v95; // r8
  __int128 *v96; // r8
  signed int v97; // eax
  wchar_t **v98; // rdx
  __int64 v99; // rcx
  __int128 *v100; // r8
  __int128 *v101; // r8
  __int128 *v102; // r9
  unsigned __int16 *v103; // rbx
  unsigned __int16 *v104; // rax
  __int128 *v105; // rax
  __int128 *v106; // r8
  const EVENT_DESCRIPTOR *FrEventDescriptorFromErrorCode; // rax
  __int128 *v108; // rcx
  unsigned __int16 *v109; // rax
  LPWSTR *v110; // rax
  __int128 *v111; // r8
  signed int v112; // eax
  unsigned int v113; // ebx
  LPCWSTR v114; // rax
  signed int v115; // eax
  unsigned int v116; // ebx
  unsigned __int16 *v117; // rax
  signed int v118; // eax
  unsigned int v119; // ebx
  __int64 v120; // r9
  unsigned int v121; // ebx
  Vml *v122; // r15
  __int64 v123; // r14
  int v124; // eax
  __int128 *v125; // r8
  unsigned int *dwCreationDisposition; // [rsp+20h] [rbp-588h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-580h]
  LPWSTR **v129; // [rsp+58h] [rbp-550h]
  __int64 v130; // [rsp+60h] [rbp-548h] BYREF
  unsigned __int16 *v131; // [rsp+68h] [rbp-540h]
  LPCWSTR v132; // [rsp+70h] [rbp-538h]
  const WCHAR **v133; // [rsp+78h] [rbp-530h]
  __int64 v134; // [rsp+80h] [rbp-528h]
  int *v135; // [rsp+88h] [rbp-520h] BYREF
  unsigned __int16 *v136; // [rsp+90h] [rbp-518h]
  __int64 v137; // [rsp+98h] [rbp-510h] BYREF
  Vml *Pointer; // [rsp+A0h] [rbp-508h]
  __int64 v139[2]; // [rsp+B0h] [rbp-4F8h] BYREF
  HANDLE v140; // [rsp+C0h] [rbp-4E8h]
  LPCWSTR v141; // [rsp+C8h] [rbp-4E0h]
  LPWSTR *v142; // [rsp+D0h] [rbp-4D8h]
  unsigned __int64 *v143; // [rsp+D8h] [rbp-4D0h]
  __int64 v144; // [rsp+E0h] [rbp-4C8h]
  __int64 v145; // [rsp+E8h] [rbp-4C0h] BYREF
  __int64 v146; // [rsp+F0h] [rbp-4B8h]
  LPWSTR **v147; // [rsp+F8h] [rbp-4B0h]
  __int64 v148; // [rsp+100h] [rbp-4A8h]
  __int64 v149; // [rsp+108h] [rbp-4A0h]
  GUID Buf1; // [rsp+110h] [rbp-498h] BYREF
  HANDLE hObject; // [rsp+120h] [rbp-488h]
  __int64 v152; // [rsp+128h] [rbp-480h] BYREF
  __int128 v153; // [rsp+130h] [rbp-478h]
  HANDLE hHandle; // [rsp+140h] [rbp-468h]
  DWORD v155; // [rsp+148h] [rbp-460h]
  GUID v156; // [rsp+14Ch] [rbp-45Ch] BYREF
  int v157; // [rsp+15Ch] [rbp-44Ch]
  HANDLE v158; // [rsp+160h] [rbp-448h] BYREF
  _BYTE v159[32]; // [rsp+168h] [rbp-440h] BYREF
  BOOL v160; // [rsp+188h] [rbp-420h]
  __int128 v161; // [rsp+190h] [rbp-418h] BYREF
  __m128i v162; // [rsp+1A0h] [rbp-408h]
  int v163; // [rsp+1B0h] [rbp-3F8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1B8h] [rbp-3F0h] BYREF
  LPWSTR pszPath[2]; // [rsp+1C8h] [rbp-3E0h] BYREF
  __m128i v166; // [rsp+1D8h] [rbp-3D0h]
  int v167; // [rsp+1E8h] [rbp-3C0h] BYREF
  __m256i FsInformation; // [rsp+1F0h] [rbp-3B8h] BYREF
  __int128 v169; // [rsp+210h] [rbp-398h] BYREF
  __int64 v170; // [rsp+220h] [rbp-388h]
  __int128 v171; // [rsp+228h] [rbp-380h] BYREF
  __int64 v172; // [rsp+238h] [rbp-370h]
  unsigned __int64 v173; // [rsp+240h] [rbp-368h]
  struct IUnknown v174; // [rsp+248h] [rbp-360h] BYREF
  __int128 v175; // [rsp+250h] [rbp-358h] BYREF
  __int64 v176; // [rsp+260h] [rbp-348h]
  unsigned __int64 v177; // [rsp+268h] [rbp-340h]
  __int128 Src; // [rsp+270h] [rbp-338h] BYREF
  __m128i si128; // [rsp+280h] [rbp-328h]
  __int64 v180; // [rsp+290h] [rbp-318h] BYREF
  _BYTE v181[152]; // [rsp+2A0h] [rbp-308h] BYREF
  __int64 v182; // [rsp+338h] [rbp-270h]
  __int64 v183; // [rsp+340h] [rbp-268h]
  unsigned int v184[8]; // [rsp+520h] [rbp-88h] BYREF
  unsigned __int16 v185[16]; // [rsp+540h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+0h]

  Pointer = a4;
  v129 = a2;
  v134 = a1;
  v141 = lpFileName;
  v133 = (const WCHAR **)lpFileName;
  v147 = a2;
  v131 = a5;
  v144 = a1;
  v8 = (LPWSTR *)a2;
  v142 = (LPWSTR *)a2;
  v148 = a3;
  IoStatusBlock.Pointer = a4;
  v9 = lpFileName;
  v132 = lpFileName;
  v143 = a7;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  v175 = 0;
  v176 = 0;
  v177 = 7;
  LOWORD(v175) = 0;
  v171 = 0;
  v172 = 0;
  v173 = 7;
  LOWORD(v171) = 0;
  *(_OWORD *)pszPath = 0;
  v166 = si128;
  LOWORD(pszPath[0]) = 0;
  v180 = 0;
  hObject = (HANDLE)-1LL;
  v167 = 0;
  v152 = 0;
  v153 = 0;
  hHandle = (HANDLE)-1LL;
  v155 = 0;
  v156 = GUID_NULL;
  v157 = -2147467259;
  _APPLY_DISK_PARAMETERS::_APPLY_DISK_PARAMETERS((_APPLY_DISK_PARAMETERS *)&v158);
  v169 = 0;
  v170 = 0;
  v130 = -1;
  Buf1 = GUID_NULL;
  v145 = 0;
  LODWORD(v174.lpVtbl) = 0;
  v136 = a5 + 12;
  if ( *((_QWORD *)a5 + 3) <= 7u )
    v10 = a5;
  else
    v10 = *(const unsigned __int16 **)a5;
  if ( (unsigned int)GetVhdExtensionInfo(v10, 0, 0, 0, 0) )
  {
    if ( !v134 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
      {
        v12 = &off_140907A18;
        goto LABEL_10;
      }
LABEL_14:
      LogFileHandle = -2147024809;
      goto LABEL_351;
    }
    if ( !Pointer )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
      {
        v12 = &off_140907A30;
        goto LABEL_10;
      }
      goto LABEL_14;
    }
    v140 = (HANDLE)-1LL;
    v146 = -1;
    std::wstring::operator=(pszPath);
    v14 = (WCHAR *)pszPath;
    if ( v166.m128i_i64[1] > 7uLL )
      v14 = pszPath[0];
    PathStripPathW(v14);
    v15 = pszPath;
    if ( v166.m128i_i64[1] > 7uLL )
      v15 = (LPWSTR *)pszPath[0];
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    std::wstring::resize(pszPath);
    v161 = 0;
    v162 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v161) = 0;
    v17 = v134;
    v139[0] = v134 + 8;
    v149 = v134 + 8;
    v18 = v134 + *(int *)(*(_QWORD *)(v134 + 8) + 12LL) + 8LL;
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
    v137 = v19;
    v20 = *(int *)(*(_QWORD *)(v134 + 8) + 12LL) + v134 + 8;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v20 + 8LL))(v20, &v161);
    v135 = &v167;
    v21 = Vml::VmComMultiInstanceObject<FrApplyTaskEventsSink>::CreateInstance<int *>(&v135);
    Vml::VmComPtr<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>::Attach<Vml::VmComEnum<IEnumConnectionPoints,IConnectionPoint *,Vml::VmComPtr<IConnectionPoint>,std::vector<Vml::VmComPtr<IConnectionPoint>>>>(
      &v145,
      v21);
    if ( !v145 )
    {
      LogFileHandle = -2147418113;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        VmlDebugTraceWithError(16800, &off_140907A00, 2147549183LL, v22, dwCreationDisposition);
      goto LABEL_272;
    }
    try
    {
      Vml::VmComEventConnect(
        Pointer,
        (struct IUnknown *)&IID_IVmTaskEvents,
        (const struct _GUID *)((v145 + 24) & -(__int64)(v145 != 0)),
        &v174,
        dwCreationDisposition);
    }
    catch ( ... )
    {
      LODWORD(v135) = wil::details::in1diag3::Log_CaughtException(
                        retaddr,
                        (void *)0x2583,
                        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\frctutilities.cpp",
                        v23);
      LogFileHandle = (int)v135;
      if ( (int)v135 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          VmlDebugTraceWithError(16800, &off_140907AF0, (unsigned int)LogFileHandle, v25, dwCreationDisposition);
        v140 = (HANDLE)v146;
        v129 = v147;
        v134 = v144;
        v8 = v142;
        Pointer = (Vml *)IoStatusBlock.Pointer;
        goto LABEL_272;
      }
      v140 = (HANDLE)v146;
      v24 = v147;
      v129 = v147;
      v17 = v144;
      v134 = v144;
      v8 = (LPWSTR *)v147;
      Pointer = (Vml *)IoStatusBlock.Pointer;
      v9 = v132;
      v19 = v137;
LABEL_30:
      memset_0(v181, 0, 0x280u);
      FrCtLogParser::FrCtLogParser((FrCtLogParser *)v181);
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 240LL))(v17);
      v27 = L"F09261A9-577A-462C-8BE3-F8A20E170A6A";
      if ( v26 < 3 )
        v27 = L"00000000-0000-0000-0000-000000000000";
      std::wstring::wstring(&FsInformation, v27);
      v28 = std::wstring::wstring(v184, v8);
      LogFileHandle = FrCtApi::GetLogFileHandle(v28, &v130, 1);
      if ( LogFileHandle < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          if ( (unsigned __int64)v8[3] <= 7 )
            v29 = v8;
          else
            v29 = *v24;
          v30 = &off_1408C0848;
LABEL_38:
          *(_QWORD *)dwFlagsAndAttributes = v29;
          v31 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v31 = (__int128 *)v161;
          VmlDebugTraceWithError(16800, v30, (unsigned int)LogFileHandle, v31, v19);
          goto LABEL_57;
        }
        goto LABEL_57;
      }
      if ( *((_QWORD *)&v169 + 1) == v170 )
      {
        std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(
          &v169,
          *((_QWORD *)&v169 + 1),
          &v130);
        v32 = v130;
      }
      else
      {
        v32 = v130;
        **((_QWORD **)&v169 + 1) = v130;
        *((_QWORD *)&v169 + 1) += 8LL;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        if ( (unsigned __int64)v8[3] <= 7 )
          v33 = v8;
        else
          v33 = *v129;
        VmlDebugTraceEx(49568, &off_1408C0830, v33, v32);
      }
      v34 = FrCtLogParser::Initialize(v181, &v169, 0);
      LogFileHandle = v34;
      if ( v34 < 0 )
      {
        if ( (unsigned int)FrCtLogParser::IsLogFileHeaderValidationError(v34) )
        {
          LogFileHandle = -2147188548;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v35 = pszPath;
            if ( v166.m128i_i64[1] > 7uLL )
              v35 = (LPWSTR *)pszPath[0];
            v36 = &v161;
            if ( v162.m128i_i64[1] > 7uLL )
              v36 = (__int128 *)v161;
            *(_QWORD *)dwFlagsAndAttributes = v35;
            VmlDebugTraceWithError(16800, &off_1408C0740, 2147778748LL, v36, v137);
          }
        }
        else if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          VmlDebugTraceWithError(16800, &off_140907AC0, (unsigned int)LogFileHandle, v37, dwCreationDisposition);
        }
        goto LABEL_57;
      }
      IoStatusBlock = *(_IO_STATUS_BLOCK *)(v182 + 76);
      Vml::VmGuid::ToString((struct _GUID *)&IoStatusBlock, &Src);
      IoStatusBlock = *(_IO_STATUS_BLOCK *)(v182 + 60);
      Vml::VmGuid::ToString((struct _GUID *)&IoStatusBlock, &v175);
      LogFileHandle = FrCtLogApplier::GetLogGuidFromRepository(v134, v148, &v171);
      if ( LogFileHandle < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          v29 = pszPath;
          if ( v166.m128i_i64[1] > 7uLL )
            v29 = (LPWSTR *)pszPath[0];
          v30 = &off_140907AD8;
          goto LABEL_38;
        }
LABEL_57:
        std::wstring::_Tidy_deallocate(&FsInformation);
        FrCtLogParser::~FrCtLogParser((FrCtLogParser *)v181);
        goto LABEL_272;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        v38 = &v171;
        if ( v173 > 7 )
          v38 = (__int128 *)v171;
        v39 = pszPath;
        if ( v166.m128i_i64[1] > 7uLL )
          v39 = (LPWSTR *)pszPath[0];
        v40 = &v161;
        if ( v162.m128i_i64[1] > 7uLL )
          v40 = (__int128 *)v161;
        *(_QWORD *)dwFlagsAndAttributes = v38;
        dwCreationDisposition = (unsigned int *)v39;
        VmlDebugTraceEx(49568, &off_140907AA8, v40, v19);
      }
      v41 = &v175;
      if ( v177 > 7 )
        v41 = (__int128 *)v175;
      v42 = &v171;
      if ( v173 > 7 )
        v42 = (__int128 *)v171;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v42, v172, v41, v176) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          if ( *(_QWORD *)v136 <= 7u )
            v43 = a5;
          else
            v43 = *(unsigned __int16 **)v131;
          v44 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v44 = (__int128 *)v161;
          dwCreationDisposition = (unsigned int *)v43;
          VmlDebugTraceEx(49568, &off_1408C0800, v44, v19);
        }
LABEL_311:
        std::wstring::_Tidy_deallocate(&FsInformation);
        FrCtLogParser::~FrCtLogParser((FrCtLogParser *)v181);
        goto LABEL_312;
      }
      if ( (unsigned __int8)std::operator!=<unsigned short>(&v171, &Src) )
      {
        p_FsInformation = &FsInformation;
        if ( FsInformation.m256i_i64[3] > 7uLL )
          p_FsInformation = (__m256i *)FsInformation.m256i_i64[0];
        v46 = &v171;
        if ( v173 > 7 )
          v46 = (__int128 *)v171;
        if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                 v46,
                                 v172,
                                 p_FsInformation,
                                 FsInformation.m256i_i64[2])
          || (unsigned int)FrCtLogApplier::IsFirstLogFileParentIdCheckEnabled() )
        {
          v47 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v47 = (__int128 *)v161;
          v139[0] = (__int64)v47;
          VmEventWrite<unsigned short const *,unsigned short const *>(
            &MSVM_VMMS_FR_LOGFILE_INVALID_SEQUENCE_ID,
            0xDu,
            (__int64)&v137);
          LogFileHandle = -2147188548;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v48 = pszPath;
            if ( v166.m128i_i64[1] > 7uLL )
              v48 = (LPWSTR *)pszPath[0];
            v49 = &v161;
            if ( v162.m128i_i64[1] > 7uLL )
              v49 = (__int128 *)v161;
            *(_QWORD *)dwFlagsAndAttributes = v48;
            VmlDebugTraceWithError(16800, &off_140907988, 2147778748LL, v49, v137);
          }
          goto LABEL_57;
        }
      }
      if ( !((v183 - v182) >> 12) || !*(_QWORD *)(v182 + 96) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          if ( (unsigned __int64)v8[3] > 7 )
            v8 = *v129;
          v111 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v111 = (__int128 *)v161;
          dwCreationDisposition = (unsigned int *)v8;
          VmlDebugTraceEx(49568, &off_1408C0728, v111, v19);
        }
        goto LABEL_311;
      }
      std::wstring::_Tidy_deallocate(&FsInformation);
      FrCtLogParser::~FrCtLogParser((FrCtLogParser *)v181);
      LODWORD(v130) = 0;
      IsFileOnSMBShare = FrUtilities::IsFileOnSMBShare(a5, &v130);
      v51 = v130;
      if ( IsFileOnSMBShare < 0 )
        v51 = 0;
      LODWORD(v130) = v51;
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        if ( (unsigned __int64)v8[3] <= 7 )
          v52 = v8;
        else
          v52 = *v129;
        if ( *(_QWORD *)v136 <= 7u )
          v53 = a5;
        else
          v53 = *(unsigned __int16 **)v131;
        v54 = &v161;
        if ( v162.m128i_i64[1] > 7uLL )
          v54 = (__int128 *)v161;
        v55 = v130;
        *(_QWORD *)dwFlagsAndAttributes = v52;
        dwCreationDisposition = (unsigned int *)v53;
        VmlDebugTraceEx(49568, &off_1408C08F0, v54, v19);
      }
      else
      {
        v55 = v130;
      }
      *((_QWORD *)&v153 + 1) = &v167;
      LODWORD(v152) = 20971520;
      HIDWORD(v152) = v55 != 0 ? 32 : 256;
      *(_QWORD *)&v153 = &v180;
      v157 = -2147467259;
      hHandle = CreateEventW(0, 1, 0, 0);
      if ( !hHandle )
      {
        LastError = GetLastError();
        LogFileHandle = LastError;
        if ( LastError > 0 )
          LogFileHandle = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          VmlDebugTraceWithError(16800, &off_140907970, (unsigned int)LogFileHandle, v57, dwCreationDisposition);
        goto LABEL_215;
      }
      if ( !v141 )
      {
LABEL_208:
        v156 = GUID_NULL;
        v157 = -2147467259;
        if ( !ResetEvent(hHandle) )
        {
          v84 = GetLastError();
          LogFileHandle = v84;
          if ( v84 > 0 )
            LogFileHandle = (unsigned __int16)v84 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v85 = &v161;
            if ( v162.m128i_i64[1] > 7uLL )
              v85 = (__int128 *)v161;
            VmlDebugTraceWithError(16800, &off_1409079A0, (unsigned int)LogFileHandle, v85, v19);
          }
          goto LABEL_215;
        }
        v86 = 0;
        LODWORD(v135) = 0;
        if ( hObject != (HANDLE)-1LL && !CloseHandle(hObject) )
        {
          v87 = GetLastError();
          v88 = v87;
          if ( v87 > 0 )
            v88 = (unsigned __int16)v87 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            if ( *(_QWORD *)v136 <= 7u )
              HIDWORD(v89) = HIDWORD(a5);
            else
              v89 = *(unsigned __int16 **)v131;
            v90 = &v161;
            if ( v162.m128i_i64[1] > 7uLL )
              v90 = (__int128 *)v161;
            dwFlagsAndAttributes[1] = HIDWORD(v89);
            VmlDebugTraceWithError(16800, &off_1408C06B0, v88, v90, v19);
          }
          v86 = (int)v135;
        }
        if ( !(_DWORD)v130 )
        {
          LODWORD(v135) = 1;
          FrCtUtilities::GetVhdAlignment(a5);
          v86 = (_DWORD)v135 != 0;
        }
        v91 = v134 + 8 + *(int *)(*(_QWORD *)v139[0] + 12LL);
        *(_OWORD *)v139 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 24LL))(v91);
        dwFlagsAndAttributes[0] = a8;
        LogFileHandle = FrCtUtilities::OpenApplyDiskHandle(v139, a5, v143, v86);
        if ( LogFileHandle < 0 )
        {
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_272;
          if ( *(_QWORD *)v136 <= 7u )
            v70 = a5;
          else
            v70 = *(unsigned __int16 **)v131;
          v71 = &off_1408C08C0;
          goto LABEL_164;
        }
        v92 = *v143;
        if ( !*v143 )
          v92 = v143[1] - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v160 = v92 != 0;
        v158 = hObject;
        std::wstring::operator=(v159);
        LogFileHandle = FrCtUtilities::ApplyLogsToVirtualDisk(&v169, &v158, &v152);
        if ( LogFileHandle < 0 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            v93 = pszPath;
            if ( v166.m128i_i64[1] > 7uLL )
              v93 = (LPWSTR *)pszPath[0];
            if ( (unsigned __int64)v8[3] <= 7 )
              v94 = (unsigned int *)v8;
            else
              v94 = (unsigned int *)*v129;
            v95 = &v161;
            if ( v162.m128i_i64[1] > 7uLL )
              v95 = (__int128 *)v161;
            *(_QWORD *)dwFlagsAndAttributes = v93;
            dwCreationDisposition = v94;
            VmlDebugTraceEx(16800, &off_1408C0770, v95, v19);
          }
          goto LABEL_272;
        }
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          v96 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v96 = (__int128 *)v161;
          LODWORD(dwCreationDisposition) = v155;
          VmlDebugTraceEx(49568, &off_140907910, v96, v19);
        }
        if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
        {
          v97 = GetLastError();
          LogFileHandle = v97;
          if ( v97 > 0 )
            LogFileHandle = (unsigned __int16)v97 | 0x80070000;
          if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
            goto LABEL_263;
          LODWORD(dwCreationDisposition) = LogFileHandle;
          v98 = &off_1409078F8;
          v99 = 16800;
        }
        else
        {
          LogFileHandle = v157;
          if ( !(unsigned int)VmlIsDebugTraceEnabled(49568) )
          {
LABEL_263:
            if ( LogFileHandle >= 0 )
            {
              if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
              {
                v101 = &v161;
                if ( v162.m128i_i64[1] > 7uLL )
                  v101 = (__int128 *)v161;
                LODWORD(dwCreationDisposition) = v155;
                VmlDebugTraceEx(49568, &off_1408C08A8, v101, v19);
              }
LABEL_312:
              FrCtApi::CloseAndClearLogFileHandles(&v169);
              if ( v140 != (HANDLE)-1LL && !CloseHandle(v140) )
              {
                v112 = GetLastError();
                v113 = v112;
                if ( v112 > 0 )
                  v113 = (unsigned __int16)v112 | 0x80070000;
                if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                {
                  v114 = v132;
                  if ( *((_QWORD *)v132 + 3) > 7u )
                    v114 = *(LPCWSTR *)v132;
                  VmlDebugTraceWithError(16800, &off_1408C0860, v113, v114, dwCreationDisposition);
                }
              }
              if ( hObject != (HANDLE)-1LL && !CloseHandle(hObject) )
              {
                v115 = GetLastError();
                v116 = v115;
                if ( v115 > 0 )
                  v116 = (unsigned __int16)v115 | 0x80070000;
                if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                {
                  if ( *(_QWORD *)v136 <= 7u )
                    v117 = a5;
                  else
                    v117 = *(unsigned __int16 **)v131;
                  VmlDebugTraceWithError(16800, &off_1408C07A0, v116, v117, dwCreationDisposition);
                }
              }
              if ( hHandle != (HANDLE)-1LL && !CloseHandle(hHandle) )
              {
                v118 = GetLastError();
                v119 = v118;
                if ( v118 > 0 )
                  v119 = (unsigned __int16)v118 | 0x80070000;
                if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
                  VmlDebugTraceWithError(16800, &off_140907940, v119, v120, dwCreationDisposition);
              }
              v163 = 0;
              if ( LogFileHandle < 0 )
                goto LABEL_350;
              v121 = 0;
              v122 = Pointer;
              v123 = v134;
              do
              {
                LogFileHandle = (*(__int64 (__fastcall **)(Vml *, int *))(*(_QWORD *)v122 + 336LL))(v122, &v163);
                v124 = v163;
                if ( LogFileHandle >= 0 && !v163 )
                {
                  LogFileHandle = FrCtLogApplier::WriteLogGuidToRepository(v123, &v175, v148);
                  v124 = v163;
                }
                ++v121;
              }
              while ( v121 < 3 && LogFileHandle == -2147023436 && !v124 );
              if ( v124 )
              {
                LogFileHandle = -2147213311;
              }
              else if ( LogFileHandle >= 0 )
              {
LABEL_350:
                CompleteTask<IVmmsVirtualMachineObject *>(
                  *(int *)(*(_QWORD *)v149 + 12LL) + v134 + 8,
                  Pointer,
                  (unsigned int)LogFileHandle,
                  0);
                std::wstring::_Tidy_deallocate(&v161);
                goto LABEL_351;
              }
              if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
              {
                v125 = &v161;
                if ( v162.m128i_i64[1] > 7uLL )
                  v125 = (__int128 *)v161;
                VmlDebugTraceEx(16800, &off_140907928, v125, v137);
              }
              goto LABEL_350;
            }
            if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
            {
              v102 = &v161;
              if ( v162.m128i_i64[1] > 7uLL )
                v102 = (__int128 *)v161;
              dwFlagsAndAttributes[0] = v155;
              VmlDebugTraceWithError(16800, &off_1408C0818, (unsigned int)LogFileHandle, v102, v19);
            }
LABEL_272:
            _snwprintf_s<16>(
              v184,
              16,
              L"%%%%%u",
              LogFileHandle & 0xEFFFFFFF,
              dwCreationDisposition,
              *(_QWORD *)dwFlagsAndAttributes);
            _snwprintf_s<16>(v185, 16, L"0x%08X", LogFileHandle & 0xEFFFFFFF);
            if ( LogFileHandle == -2147188481 )
            {
              v103 = v136;
              if ( *(_QWORD *)v136 <= 7u )
                v104 = a5;
              else
                v104 = *(unsigned __int16 **)v131;
              v139[0] = (__int64)v104;
              v105 = &v161;
              if ( v162.m128i_i64[1] > 7uLL )
                v105 = (__int128 *)v161;
              IoStatusBlock.Pointer = v105;
              VmEventWrite<unsigned short const * &,unsigned short const * &,unsigned short (&)[16],unsigned short (&)[16],unsigned short const * const &>(
                &MSVM_VMMS_FR_LOGFILE_DISK_OFFSET_MISMATCH,
                0xDu,
                (__int64)&v137,
                v184,
                v185,
                (__int64)v139);
            }
            else
            {
              if ( LogFileHandle == -2147213311 )
              {
                std::wstring::wstring(&FsInformation, L"ApplyLog");
                if ( v141 )
                  std::wstring::append(&FsInformation, L" and GenerateUndoLog");
                if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
                {
                  v106 = &v161;
                  if ( v162.m128i_i64[1] > 7uLL )
                    v106 = (__int128 *)v161;
                  VmlDebugTraceEx(49568, &off_140907958, v106, v137);
                }
                std::wstring::_Tidy_deallocate(&FsInformation);
              }
              v103 = v136;
            }
            FrEventDescriptorFromErrorCode = GetFrEventDescriptorFromErrorCode(LogFileHandle);
            if ( FrEventDescriptorFromErrorCode )
            {
              v108 = &v161;
              if ( v162.m128i_i64[1] > 7uLL )
                v108 = (__int128 *)v161;
              v139[0] = (__int64)v108;
              VmEventWrite<unsigned short const *,unsigned short const *>(
                FrEventDescriptorFromErrorCode,
                0xDu,
                (__int64)&v137);
            }
            else
            {
              if ( *(_QWORD *)v103 <= 7u )
                v109 = a5;
              else
                v109 = *(unsigned __int16 **)v131;
              v139[0] = (__int64)v109;
              if ( (unsigned __int64)v8[3] > 7 )
                v8 = *v129;
              IoStatusBlock.Pointer = v8;
              v110 = (LPWSTR *)&v161;
              if ( v162.m128i_i64[1] > 7uLL )
                v110 = (LPWSTR *)v161;
              v142 = v110;
              VmEventWrite<unsigned short const *,unsigned short const * &,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
                &MSVM_VMMS_FR_CTAPI_APPLY_LOGFILE_ERROR,
                0xDu,
                (__int64)&v137,
                v184,
                v185,
                (__int64)&IoStatusBlock,
                (__int64)v139);
            }
            if ( (unsigned int)FrCtLogParser::IsLogFileHeaderValidationError(LogFileHandle) )
              LogFileHandle = -2147188548;
            if ( v141 && memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
            {
              *(GUID *)v139 = Buf1;
              FrCtUtilities::RemoveSmartBitmap(v139);
            }
            goto LABEL_312;
          }
          LODWORD(dwCreationDisposition) = v155;
          v98 = &off_1409078E0;
          v99 = 49568;
        }
        v100 = &v161;
        if ( v162.m128i_i64[1] > 7uLL )
          v100 = (__int128 *)v161;
        VmlDebugTraceEx(v99, v98, v100, v19);
        goto LABEL_263;
      }
      if ( *((_QWORD *)v9 + 3) <= 7u )
        v58 = v9;
      else
        v58 = *v133;
      FileW = CreateFileW(v58, 0xC0000000, 1u, 0, 3u, 0xC0000000, 0);
      v140 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v60 = GetLastError();
        LogFileHandle = v60;
        if ( v60 > 0 )
          LogFileHandle = (unsigned __int16)v60 | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          if ( *((_QWORD *)v132 + 3) <= 7u )
            v61 = v132;
          else
            v61 = *(LPCWSTR *)v132;
          v62 = &off_1408C0788;
LABEL_132:
          *(_QWORD *)dwFlagsAndAttributes = v61;
          v63 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v63 = (__int128 *)v161;
          VmlDebugTraceWithError(16800, v62, (unsigned int)LogFileHandle, v63, v19);
          goto LABEL_215;
        }
        goto LABEL_215;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        v64 = &v161;
        if ( v162.m128i_i64[1] > 7uLL )
          v64 = (__int128 *)v161;
        *(_QWORD *)dwFlagsAndAttributes = FileW;
        VmlDebugTraceEx(49568, &off_1408C0758, v64, v19);
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
        v65 = *((_QWORD *)v9 + 3) <= 7u ? v9 : *v133;
        v140 = CreateFileW(v65, 0xC0000000, 1u, 0, 3u, 0x60000000u, 0);
        if ( v140 == (HANDLE)-1LL )
        {
          v66 = GetLastError();
          LogFileHandle = v66;
          if ( v66 > 0 )
            LogFileHandle = (unsigned __int16)v66 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            if ( *((_QWORD *)v132 + 3) <= 7u )
              v61 = v132;
            else
              v61 = *(LPCWSTR *)v132;
            v62 = &off_1408C08D8;
            goto LABEL_132;
          }
LABEL_215:
          if ( LogFileHandle >= 0 )
            goto LABEL_312;
          goto LABEL_272;
        }
      }
      LogFileHandle = FrCtUtilities::ExtractGuidFromLogFileName(v9, &v156);
      if ( LogFileHandle < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          if ( *((_QWORD *)v132 + 3) <= 7u )
            v67 = v132;
          else
            v67 = *(LPCWSTR *)v132;
          VmlDebugTraceWithError(16800, &off_1408C0890, (unsigned int)LogFileHandle, v67, dwCreationDisposition);
        }
        goto LABEL_272;
      }
      Buf1 = v156;
      v68 = v134 + 8 + *(int *)(*(_QWORD *)v139[0] + 12LL);
      IoStatusBlock = *(_IO_STATUS_BLOCK *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 24LL))(v68);
      dwFlagsAndAttributes[0] = a8;
      v69 = v143;
      LogFileHandle = FrCtUtilities::OpenApplyDiskHandle(&IoStatusBlock, a5, v143, 0);
      if ( LogFileHandle < 0 )
      {
        if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
          goto LABEL_272;
        if ( *(_QWORD *)v136 <= 7u )
          v70 = a5;
        else
          v70 = *(unsigned __int16 **)v131;
        v71 = &off_1408C07E8;
LABEL_164:
        *(_QWORD *)dwFlagsAndAttributes = v70;
        v72 = &v161;
        if ( v162.m128i_i64[1] > 7uLL )
          v72 = (__int128 *)v161;
        VmlDebugTraceWithError(16800, v71, (unsigned int)LogFileHandle, v72, v19);
        goto LABEL_272;
      }
      v73 = *v69;
      if ( !*v69 )
        v73 = v69[1] - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v160 = v73 != 0;
      v158 = hObject;
      std::wstring::operator=(v159);
      LogFileHandle = FrCtUtilities::GenerateUndoLog(
                        *(void **)v169,
                        v140,
                        (struct _APPLY_DISK_PARAMETERS *)&v158,
                        (struct _APPLY_LOG_PARAMETERS *)&v152);
      if ( LogFileHandle < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          v74 = v132;
          if ( *((_QWORD *)v132 + 3) > 7u )
            v74 = *(LPCWSTR *)v132;
          if ( (unsigned __int64)v8[3] <= 7 )
            v75 = (unsigned int *)v8;
          else
            v75 = (unsigned int *)*v129;
          v76 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v76 = (__int128 *)v161;
          *(_QWORD *)dwFlagsAndAttributes = v74;
          dwCreationDisposition = v75;
          VmlDebugTraceEx(16800, &off_1408C07D0, v76, v19);
        }
        goto LABEL_272;
      }
      if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      {
        v77 = &v161;
        if ( v162.m128i_i64[1] > 7uLL )
          v77 = (__int128 *)v161;
        LODWORD(dwCreationDisposition) = v155;
        VmlDebugTraceEx(49568, &off_1409079D0, v77, v19);
      }
      if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
      {
        v78 = GetLastError();
        LogFileHandle = v78;
        if ( v78 > 0 )
          LogFileHandle = (unsigned __int16)v78 | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
        {
          v79 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v79 = (__int128 *)v161;
          VmlDebugTraceWithError(16800, &off_1409079B8, (unsigned int)LogFileHandle, v79, v19);
        }
      }
      else
      {
        LogFileHandle = v157;
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          v80 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v80 = (__int128 *)v161;
          LODWORD(dwCreationDisposition) = v155;
          VmlDebugTraceEx(49568, &off_1409079E8, v80, v19);
        }
        if ( LogFileHandle < 0 )
          goto LABEL_204;
        LogFileHandle = (*(__int64 (__fastcall **)(Vml *, __int64))(*(_QWORD *)Pointer + 80LL))(Pointer, 50);
      }
      if ( LogFileHandle >= 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          if ( *((_QWORD *)v132 + 3) <= 7u )
            v81 = v132;
          else
            v81 = *(LPCWSTR *)v132;
          v82 = &v161;
          if ( v162.m128i_i64[1] > 7uLL )
            v82 = (__int128 *)v161;
          *(_QWORD *)dwFlagsAndAttributes = v81;
          LODWORD(dwCreationDisposition) = v155;
          VmlDebugTraceEx(49568, &off_1408C0878, v82, v19);
        }
        goto LABEL_208;
      }
LABEL_204:
      if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
        goto LABEL_272;
      v83 = &v161;
      if ( v162.m128i_i64[1] > 7uLL )
        v83 = (__int128 *)v161;
      dwFlagsAndAttributes[0] = v155;
      VmlDebugTraceWithError(16800, &off_1408C07B8, (unsigned int)LogFileHandle, v83, v19);
      goto LABEL_215;
    }
    v24 = v129;
    goto LABEL_30;
  }
  if ( !(unsigned int)VmlIsDebugTraceEnabled(16800) )
    goto LABEL_14;
  v12 = &off_140907A60;
LABEL_10:
  LogFileHandle = -2147024809;
  VmlDebugTraceWithError(16800, v12, 2147942487LL, v11, dwCreationDisposition);
LABEL_351:
  Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v145);
  std::vector<void *>::_Tidy(&v169);
  std::wstring::_Tidy_deallocate(v159);
  std::wstring::_Tidy_deallocate(pszPath);
  std::wstring::_Tidy_deallocate(&v171);
  std::wstring::_Tidy_deallocate(&v175);
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
