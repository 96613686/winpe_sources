# FailoverReplicationTracker::ProcessIncomingInitialReplica(FailoverReplicationOperation *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x14027e40c`
- end: `0x14027ef19`
- name: `?ProcessIncomingInitialReplica@FailoverReplicationTracker@@AEAAXPEAVFailoverReplicationOperation@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z`
- size: `2829`
- prototype: `__int64 __fastcall(FailoverReplicationTracker *this, struct FailoverReplicationOperation *)`
- caller_count: `2`
- callee_count: `41`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1400f8194`
- `0x1402a6e50`

## callees

- `0x14001993c`
- `0x140022640`
- `0x1400341d8`
- `0x14004bf10`
- `0x14004f3c4`
- `0x14005c630`
- `0x14008fc80`
- `0x14009d144`
- `0x1400acf04`
- `0x1400b4590`
- `0x1400e2008`
- `0x1400ee990`
- `0x1400f3b08`
- `0x1400f682c`
- `0x1400fc774`
- `0x140157f28`
- `0x1401586a4`
- `0x14017902c`
- `0x1401879a4`
- `0x140188e18`
- `0x1401a56b4`
- `0x1401a5e40`
- `0x1401ee588`
- `0x14021e064`
- `0x1402407a4`
- `0x14024d020`
- `0x14027dd14`
- `0x14027e13c`
- `0x14027e240`
- `0x14027e2dc`
- `0x14027e40c`
- `0x14027fedc`
- `0x140280020`
- `0x140281220`
- `0x1402c3f84`
- `0x1404828e0`
- `0x1404835a0`
- `0x1404ad2b8`
- `0x1404ad2e4`
- `0x140524fe4`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14027e74e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14027e74e`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027ed1b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027ed45`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027edb7`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027ede1`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027ed1b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027ed45`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027edb7`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x14027ede1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14027ee55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14027ee55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e92d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027e92d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14027ed76`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14027ee0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14027ed76`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14027ee0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14027ee24`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14027ee41`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14027ee24`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14027ee41`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14027e677`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14027e6eb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14027e677`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14027e6eb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14027ebeb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14027ebeb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14027e7c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14027e7c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14027ebc2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14027ebc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall FailoverReplicationTracker::ProcessIncomingInitialReplica(
        FailoverReplicationTracker *this,
        struct FailoverReplicationOperation *a2,
        _QWORD *a3,
        __int64 a4)
{
  const WCHAR ***v4; // r14
  __m128i si128; // xmm6
  unsigned __int64 v8; // r12
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r11
  __int64 (__fastcall *v14)(__int64, __int128 *, _QWORD, __int64); // r10
  int v15; // eax
  unsigned __int64 v16; // r15
  __int64 v17; // rdi
  __int64 v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rbx
  _QWORD *v21; // rax
  int VhdType; // eax
  _QWORD *v23; // rax
  LPWSTR *v24; // rcx
  LPWSTR *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r15
  LPWSTR *v29; // rcx
  LPWSTR *v30; // rax
  __int64 v31; // rdx
  LPWSTR *v32; // rdx
  LPWSTR *v33; // rcx
  LPWSTR *v34; // rdx
  _QWORD *v35; // rcx
  const unsigned __int16 *v36; // rdx
  LPCWSTR *v37; // rcx
  LPCWSTR *v38; // rcx
  LPCWSTR *v39; // rax
  __int128 *v40; // rax
  LPCWSTR *v41; // rax
  __int64 v42; // rdx
  const WCHAR **v43; // rdx
  __int64 v44; // rdi
  _QWORD *v45; // rax
  signed int LastError; // eax
  unsigned int v47; // edi
  unsigned __int64 v48; // rbx
  const WCHAR **v49; // rdx
  _QWORD *v50; // rdi
  const WCHAR **v51; // r8
  __int64 v52; // rdx
  int v53; // eax
  const WCHAR **i; // rbx
  const WCHAR *v55; // rcx
  DWORD FileAttributesW; // eax
  const char *v57; // r9
  DWORD v58; // eax
  const WCHAR *v59; // rcx
  const char *v60; // r9
  int v61; // eax
  int v62; // eax
  unsigned int v63; // edx
  int v64; // eax
  __int64 v65; // rax
  DWORD v66; // ecx
  __int64 v67; // rax
  char v68; // al
  const char *v69; // r9
  __int64 v70; // rax
  DWORD v71; // edi
  __int64 v72; // rax
  char v73; // al
  unsigned int Value; // ebx
  const WCHAR *v75; // rcx
  const WCHAR *v76; // rax
  int v77; // eax
  unsigned int v79; // [rsp+28h] [rbp-E0h]
  __int64 v80; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD *v82; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v83[2]; // [rsp+60h] [rbp-A8h] BYREF
  char *v84; // [rsp+70h] [rbp-98h] BYREF
  char v85; // [rsp+78h] [rbp-90h]
  __int64 v86; // [rsp+80h] [rbp-88h] BYREF
  char v87[16]; // [rsp+90h] [rbp-78h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v89; // [rsp+B0h] [rbp-58h]
  __int128 v90; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v91; // [rsp+D0h] [rbp-38h]
  LPWSTR pszPath[3]; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int64 v93; // [rsp+F8h] [rbp-10h]
  __int128 v94; // [rsp+100h] [rbp-8h] BYREF
  __int128 v95; // [rsp+110h] [rbp+8h] BYREF
  __int128 v96; // [rsp+120h] [rbp+18h] BYREF
  __int64 v97; // [rsp+130h] [rbp+28h]
  LPWSTR Src[3]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int64 v99; // [rsp+150h] [rbp+48h]
  _BYTE v100[208]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v4 = (const WCHAR ***)a4;
  v80 = a4;
  v82 = a3;
  v90 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v91 = si128;
  v8 = 0;
  LOWORD(v90) = 0;
  v9 = *((_QWORD *)this + 677) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 677) + 8LL) + 12LL);
  v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
  v10 = *((_QWORD *)this + 677);
  v11 = *(int *)(*(_QWORD *)(v10 + 8) + 12LL);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(v11 + v10 + 8) + 8LL))(v11 + v10 + 8, &v90);
  v96 = 0;
  v97 = 0;
  v83[0] = VirtualHardDiskReference::ExcludeSharedVhdFilter;
  v12 = std::function<bool (VirtualHardDiskReference const &)>::function<bool (VirtualHardDiskReference const &)>(
          Src,
          v83);
  v15 = v14(v13 + 8, &v96, 0, v12);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF5C,
      (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
      (const char *)(unsigned int)v15,
      v79);
  v94 = 0;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(&v94);
  v16 = 0;
  v17 = v96;
  if ( 0xD37A6F4DE9BD37A7uLL * ((__int64)(*((_QWORD *)&v96 + 1) - v96) >> 3) )
  {
    v18 = v96;
    do
    {
      v19 = (_QWORD *)std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                        &v94,
                        &v84,
                        184 * v16 + v18 + 64);
      std::wstring::operator=(*v19 + 64LL, 184 * v16++ + v17);
      v17 = v96;
      v18 = v96;
    }
    while ( v16 < 0xD37A6F4DE9BD37A7uLL * ((__int64)(*((_QWORD *)&v96 + 1) - v96) >> 3) );
    v4 = (const WCHAR ***)v80;
  }
  v95 = 0;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(&v95);
  v20 = **((_QWORD **)a2 + 43);
  v83[0] = v20;
  while ( v20 != *((_QWORD *)a2 + 43) )
  {
    v21 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                      &v94,
                      &v84,
                      v20 + 32);
    if ( *v21 == (_QWORD)v94 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
      {
        v79 = v81;
        VmlDebugTraceWithError(16800, &off_1409153C0, 2147778746LL);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF8D,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)0x800480BALL,
        v79);
    }
    LODWORD(v80) = 0;
    VhdType = AvhdUtilities::GetVhdType(*(_QWORD *)(v20 + 72) - 32LL, 0, &v80);
    if ( VhdType < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF95,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)(unsigned int)VhdType,
        v79);
    if ( (_DWORD)v80 == 4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF98,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)0xD,
        v79);
    v23 = (_QWORD *)std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                      &v94,
                      &v86,
                      v20 + 32);
    std::wstring::wstring(pszPath, *v23 + 64LL);
    v24 = pszPath;
    if ( v93 > 7 )
      v24 = (LPWSTR *)pszPath[0];
    if ( !PathRemoveFileSpecW((LPWSTR)v24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF9E,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)0x8000FFFFLL,
        v79);
    v25 = pszPath;
    if ( v93 > 7 )
      v25 = (LPWSTR *)pszPath[0];
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v25 + v26) );
    std::wstring::resize(pszPath);
    while ( 1 )
    {
      v27 = *(_QWORD *)(v20 + 64);
      if ( v8 >= (*(_QWORD *)(v20 + 72) - v27) >> 5 )
        break;
      v28 = 32 * v8;
      std::wstring::wstring(Src, v27 + 32 * v8);
      v29 = Src;
      if ( v99 > 7 )
        v29 = (LPWSTR *)Src[0];
      if ( !PathRemoveFileSpecW((LPWSTR)v29) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFA7,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
          (const char *)0x8000FFFFLL,
          v79);
      v30 = Src;
      if ( v99 > 7 )
        v30 = (LPWSTR *)Src[0];
      v31 = -1;
      do
        ++v31;
      while ( *((_WORD *)v30 + v31) );
      std::wstring::resize(Src);
      if ( *((_DWORD *)this + 1030) == 3 )
      {
        v32 = pszPath;
        if ( v93 > 7 )
          v32 = (LPWSTR *)pszPath[0];
        v33 = Src;
        if ( v99 > 7 )
          v33 = (LPWSTR *)Src[0];
        if ( (unsigned int)_o__wcsicmp(v33, v32) )
        {
          *(_OWORD *)lpFileName = 0;
          v89 = si128;
          LOWORD(lpFileName[0]) = 0;
          v34 = pszPath;
          if ( v93 > 7 )
            v34 = (LPWSTR *)pszPath[0];
          v35 = (_QWORD *)(v28 + *(_QWORD *)(v20 + 64));
          if ( v35[3] > 7u )
            v35 = (_QWORD *)*v35;
          FrUtilities::ConstructTargetFilePath(v35, v34, lpFileName);
          v37 = lpFileName;
          if ( v89.m128i_i64[1] > 7uLL )
            v37 = (LPCWSTR *)lpFileName[0];
          if ( (unsigned int)VmmsPathUtilities::FileExists((VmmsPathUtilities *)v37, v36) )
          {
            v38 = lpFileName;
            if ( v89.m128i_i64[1] > 7uLL )
              v38 = (LPCWSTR *)lpFileName[0];
            if ( !DeleteFileW((LPCWSTR)v38) )
            {
              LastError = GetLastError();
              v47 = LastError;
              if ( LastError > 0 )
                v47 = (unsigned __int16)LastError | 0x80070000;
              if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
              {
                v79 = v81;
                VmlDebugTraceWithError(16800, &off_1408BB000, v47);
              }
              std::vector<std::wstring>::clear(v4);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xFD3,
                (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
                (const char *)v47,
                v79);
            }
            v39 = lpFileName;
            if ( v89.m128i_i64[1] > 7uLL )
              v39 = (LPCWSTR *)lpFileName[0];
            v80 = (__int64)v39;
            v40 = &v90;
            if ( v91.m128i_i64[1] > 7uLL )
              v40 = (__int128 *)v90;
            v83[1] = v40;
            VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *>(
              &MSVM_VMMS_FR_ENGINE_OFFLINE_IR_DELETE_FILE_WARNING,
              1u,
              (__int64)&v81,
              (__int64)&v80);
            if ( (unsigned int)VmlIsDebugTraceEnabled(33186) )
            {
              v41 = lpFileName;
              if ( v89.m128i_i64[1] > 7uLL )
                LODWORD(v41) = lpFileName[0];
              v79 = (unsigned int)v41;
              VmlDebugTraceEx(33186, &off_1409153D8);
            }
          }
          v42 = v82[1];
          if ( v42 == v82[2] )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v82, v42, v28 + *(_QWORD *)(v20 + 64));
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(
              v82,
              v28 + *(_QWORD *)(v20 + 64));
          v43 = v4[1];
          if ( v43 == v4[2] )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v4, v43, lpFileName);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v4, lpFileName);
          std::wstring::operator=(v28 + *(_QWORD *)(v20 + 64), lpFileName);
          std::wstring::_Tidy_deallocate(lpFileName);
        }
      }
      if ( v8 )
      {
        v44 = v28 + *(_QWORD *)(v20 + 64);
        v45 = (_QWORD *)std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                          &v95,
                          v87,
                          v44 - 32);
        std::wstring::operator=(*v45 + 64LL, v44);
      }
      std::wstring::_Tidy_deallocate(Src);
      ++v8;
    }
    std::wstring::_Tidy_deallocate(pszPath);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>>>,std::_Iterator_base0>::operator++(v83);
    v20 = v83[0];
    v8 = 0;
  }
  if ( *v4 != v4[1] )
  {
    memset_0(v100, 0, 0xC8u);
    VmmsFileCopier::VmmsFileCopier((VmmsFileCopier *)v100, *((struct IVmTask **)a2 + 123), 0x64u);
    v48 = 0;
    v49 = *v4;
    if ( ((char *)v4[1] - (char *)*v4) >> 5 )
    {
      v50 = v82;
      do
      {
        v51 = &v49[4 * v48];
        if ( (unsigned __int64)v51[3] > 7 )
          v51 = (const WCHAR **)*v51;
        v52 = 32 * v48 + *v50;
        if ( *(_QWORD *)(v52 + 24) > 7u )
          v52 = *(_QWORD *)v52;
        VmmsFileCopier::AddFileToCopy(
          (VmmsFileCopier *)v100,
          (const unsigned __int16 *)v52,
          (const unsigned __int16 *)v51,
          1);
        ++v48;
        v49 = *v4;
      }
      while ( v48 < ((char *)v4[1] - (char *)*v4) >> 5 );
    }
    if ( !(unsigned int)VmmsFileCopier::CheckForLowDiskSpace((VmmsFileCopier *)v100) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1007,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)0x70,
        v79);
    v53 = VmmsFileCopier::CopyFiles((VmmsFileCopier *)v100);
    if ( v53 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100A,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)(unsigned int)v53,
        v79);
    GetVmTaskResult(*((struct IVmTask **)a2 + 123));
    for ( i = *v4; i != v4[1]; i += 4 )
    {
      if ( (unsigned __int64)i[3] <= 7 )
        v55 = (const WCHAR *)i;
      else
        v55 = *i;
      FileAttributesW = GetFileAttributesW(v55);
      if ( FileAttributesW == -1 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1015,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
          v57);
      if ( (FileAttributesW & 1) != 0 )
      {
        v58 = FileAttributesW & 0xFFFFFFFE;
        v59 = (unsigned __int64)i[3] <= 7 ? (const WCHAR *)i : *i;
        if ( !SetFileAttributesW(v59, v58) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x101D,
            (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
            v60);
      }
    }
    VmmsFileCopier::~VmmsFileCopier((VmmsFileCopier *)v100);
  }
  if ( *((_DWORD *)a2 + 94) )
  {
    if ( *((_DWORD *)this + 1030) != 3 )
    {
      v61 = FrUtilities::ReplaceHostOnlyKvpItems(
              *((struct IVmmsRealizedVirtualMachine **)this + 677),
              (struct FailoverReplicationOperation *)((char *)a2 + 368));
      if ( v61 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x102A,
          (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
          (const char *)(unsigned int)v61,
          v79);
    }
  }
  v62 = FailoverReplicationTracker::ApplySecureVmSettings(this, a2);
  if ( v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x102E,
      (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
      (const char *)(unsigned int)v62,
      v79);
  v63 = *((_DWORD *)this + 1233);
  if ( v63 != *((_DWORD *)a2 + 95) )
  {
    v64 = FailoverReplicationTracker::LogAndReInitializeMonitoringCounters(this, v63);
    if ( v64 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1033,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)(unsigned int)v64,
        v79);
    if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
      VmlDebugTraceEx(49568, &off_1409153F0);
    v65 = __RTtypeid(this);
    if ( (unsigned __int8)type_info::operator==(v65, &FailoverReplicationTracker `RTTI Type Descriptor') )
    {
      v66 = FailoverReplicationTracker::gm_FrTlsIndex;
    }
    else
    {
      v67 = __RTtypeid(this);
      v68 = type_info::operator==(v67, &ExtendedReplicationTracker `RTTI Type Descriptor');
      v66 = SharedReplicationTracker::gm_SrTlsIndex;
      if ( v68 )
        v66 = ExtendedReplicationTracker::gm_ErTlsIndex;
    }
    if ( ((unsigned __int8)TlsGetValue(v66) & 1) == 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1039,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        v69);
    Vml::VmSlimReaderWriterLock::AcquireExclusive((FailoverReplicationTracker *)((char *)this + 4984));
    v84 = (char *)this + 4984;
    v85 = 1;
    v70 = __RTtypeid(this);
    if ( (unsigned __int8)type_info::operator==(v70, &FailoverReplicationTracker `RTTI Type Descriptor') )
    {
      v71 = FailoverReplicationTracker::gm_FrTlsIndex;
    }
    else
    {
      v72 = __RTtypeid(this);
      v73 = type_info::operator==(v72, &ExtendedReplicationTracker `RTTI Type Descriptor');
      v71 = SharedReplicationTracker::gm_SrTlsIndex;
      if ( v73 )
        v71 = ExtendedReplicationTracker::gm_ErTlsIndex;
    }
    Value = (unsigned int)TlsGetValue(v71);
    TlsSetValue(v71, (LPVOID)(Value | 8LL));
    *((_DWORD *)this + 1233) = *((_DWORD *)a2 + 95);
    TlsSetValue(v71, (LPVOID)Value);
    *((_DWORD *)this + 1248) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 623);
  }
  v75 = (const WCHAR *)v95;
  v76 = *(const WCHAR **)v95;
  v82 = *(_QWORD **)v95;
  while ( v76 != v75 )
  {
    v77 = AvhdUtilities::SetParentPath(v76 + 16, v76 + 32);
    if ( v77 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1045,
        (unsigned int)"onecore\\vm\\vmms\\fr\\lib\\failoverreplicationtrackerstatemachinehelpers.cpp",
        (const char *)(unsigned int)v77,
        v79);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>>>,std::_Iterator_base0>::operator++(&v82);
    v75 = (const WCHAR *)v95;
    v76 = (const WCHAR *)v82;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    &v95,
    &v95);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    &v94,
    &v94);
  std::vector<VirtualHardDiskReference>::_Tidy(&v96);
  return std::wstring::_Tidy_deallocate(&v90);
}

```

## disassembly

```asm
0x14027e40c  mov     rax, rsp
0x14027e40f  push    rbp
0x14027e410  push    rbx
0x14027e411  push    rsi
0x14027e412  push    rdi
0x14027e413  push    r12
0x14027e415  push    r13
0x14027e417  push    r14
0x14027e419  push    r15
0x14027e41b  lea     rbp, [rax-1A8h]
0x14027e422  sub     rsp, 268h
0x14027e429  movaps  xmmword ptr [rax-58h], xmm6
0x14027e42d  mov     rax, cs:__security_cookie
0x14027e434  xor     rax, rsp
0x14027e437  mov     [rbp+1A0h+var_60], rax
0x14027e43e  mov     r14, r9
0x14027e441  mov     [rsp+2A0h+var_260], r9
0x14027e446  mov     [rsp+2A0h+var_250], r8
0x14027e44b  mov     r13, rdx
0x14027e44e  mov     rsi, rcx
0x14027e451  xorps   xmm0, xmm0
0x14027e454  movups  [rbp+1A0h+var_1E8], xmm0
0x14027e458  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14027e460  movdqu  [rbp+1A0h+var_1D8], xmm6
0x14027e465  xor     r12d, r12d
0x14027e468  mov     word ptr [rbp+1A0h+var_1E8], r12w
0x14027e46d  mov     rdx, [rcx+1528h]
0x14027e474  mov     rax, [rdx+8]
0x14027e478  movsxd  rcx, dword ptr [rax+0Ch]
0x14027e47c  add     rdx, 8
0x14027e480  add     rcx, rdx
0x14027e483  mov     rax, [rcx]
0x14027e486  mov     rax, [rax+20h]
0x14027e48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027e48f  mov     [rsp+2A0h+var_258], rax
0x14027e494  mov     r8, [rsi+1528h]
0x14027e49b  mov     rcx, [r8+8]
0x14027e49f  movsxd  r9, dword ptr [rcx+0Ch]
0x14027e4a3  mov     rcx, [r9+r8+8]
0x14027e4a8  mov     rax, [rcx+8]
0x14027e4ac  lea     rdx, [rbp+1A0h+var_1E8]
0x14027e4b0  lea     rcx, [r8+8]
0x14027e4b4  add     rcx, r9
0x14027e4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027e4bc  xorps   xmm1, xmm1
0x14027e4bf  movdqu  [rbp+1A0h+var_188], xmm1
0x14027e4c4  mov     [rbp+1A0h+var_178], r12
0x14027e4c8  mov     rdx, [rsi+1528h]
0x14027e4cf  mov     rax, [rdx+8]
0x14027e4d3  movsxd  r11, dword ptr [rax+0Ch]
0x14027e4d7  add     r11, rdx
0x14027e4da  mov     rax, [r11+8]
0x14027e4de  mov     r10, [rax+180h]
0x14027e4e5  lea     rax, ?ExcludeSharedVhdFilter@VirtualHardDiskReference@@SA_NAEBV1@@Z; VirtualHardDiskReference::ExcludeSharedVhdFilter(VirtualHardDiskReference const &)
0x14027e4ec  mov     [rsp+2A0h+var_248], rax
0x14027e4f1  lea     rdx, [rsp+2A0h+var_248]
0x14027e4f6  lea     rcx, [rbp+1A0h+Src]
0x14027e4fa  call    ??$?0P6A_NAEBVVirtualHardDiskReference@@@Z$0A@@?$function@$$A6A_NAEBVVirtualHardDiskReference@@@Z@std@@QEAA@$$QEAP6A_NAEBVVirtualHardDiskReference@@@Z@Z; std::function<bool (VirtualHardDiskReference const &)>::function<bool (VirtualHardDiskReference const &)>(bool (*&&)(VirtualHardDiskReference const &))
0x14027e4ff  mov     r9, rax
0x14027e502  xor     r8d, r8d
0x14027e505  lea     rdx, [rbp+1A0h+var_188]
0x14027e509  lea     rcx, [r11+8]
0x14027e50d  mov     rax, r10
0x14027e510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027e515  mov     rcx, [rbp+1A8h]; this
0x14027e51c  test    eax, eax
0x14027e51e  jns     short loc_14027E535
0x14027e520  mov     r9d, eax; char *
0x14027e523  lea     r8, aOnecoreVmVmmsF_35; "onecore\\vm\\vmms\\fr\\lib\\failoverrep"...
0x14027e52a  mov     edx, 0F5Ch; void *
0x14027e52f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14027e535  xorps   xmm0, xmm0
0x14027e538  movups  [rbp+1A0h+var_1A8], xmm0
0x14027e53c  lea     rcx, [rbp+1A0h+var_1A8]
0x14027e540  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x14027e545  nop
0x14027e546  mov     r15, r12
0x14027e549  mov     rdi, qword ptr [rbp+1A0h+var_188]
0x14027e54d  mov     rax, qword ptr [rbp+1A0h+var_188+8]
0x14027e551  sub     rax, rdi
0x14027e554  sar     rax, 3
0x14027e558  mov     rcx, 0D37A6F4DE9BD37A7h
0x14027e562  imul    rax, rcx
0x14027e566  test    rax, rax
0x14027e569  jz      short loc_14027E5C7
0x14027e56b  mov     rcx, rdi
0x14027e56e  mov     r14, 0D37A6F4DE9BD37A7h
0x14027e578  imul    rbx, r15, 0B8h
0x14027e57f  lea     r8, [rcx+40h]
0x14027e583  add     r8, rbx
0x14027e586  lea     rdx, [rsp+2A0h+var_238]
0x14027e58b  lea     rcx, [rbp+1A0h+var_1A8]
0x14027e58f  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x14027e594  lea     rdx, [rbx+rdi]
0x14027e598  mov     rcx, [rax]
0x14027e59b  add     rcx, 40h ; '@'
0x14027e59f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14027e5a4  inc     r15
0x14027e5a7  mov     rdi, qword ptr [rbp+1A0h+var_188]
0x14027e5ab  mov     rcx, rdi
0x14027e5ae  mov     rax, qword ptr [rbp+1A0h+var_188+8]
0x14027e5b2  sub     rax, rdi
0x14027e5b5  sar     rax, 3
0x14027e5b9  imul    rax, r14
0x14027e5bd  cmp     r15, rax
0x14027e5c0  jb      short loc_14027E578
0x14027e5c2  mov     r14, [rsp+2A0h+var_260]
0x14027e5c7  xorps   xmm0, xmm0
0x14027e5ca  movups  [rbp+1A0h+var_198], xmm0
0x14027e5ce  lea     rcx, [rbp+1A0h+var_198]
0x14027e5d2  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x14027e5d7  nop
0x14027e5d8  mov     rbx, [r13+158h]
0x14027e5df  mov     rbx, [rbx]
0x14027e5e2  mov     [rsp+2A0h+var_248], rbx
0x14027e5e7  cmp     rbx, [r13+158h]
0x14027e5ee  jz      loc_14027EAAD
0x14027e5f4  lea     r8, [rbx+20h]
0x14027e5f8  lea     rdx, [rsp+2A0h+var_238]
0x14027e5fd  lea     rcx, [rbp+1A0h+var_1A8]
0x14027e601  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x14027e606  mov     rcx, qword ptr [rbp+1A0h+var_1A8]
0x14027e60a  cmp     [rax], rcx
0x14027e60d  jz      loc_14027EA53
0x14027e613  mov     dword ptr [rsp+2A0h+var_260], r12d
0x14027e618  mov     rcx, [rbx+48h]
0x14027e61c  sub     rcx, 20h ; ' '
0x14027e620  lea     r8, [rsp+2A0h+var_260]
0x14027e625  xor     edx, edx
0x14027e627  call    ?GetVhdType@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEAK@Z; AvhdUtilities::GetVhdType(std::wstring const &,int,ulong &)
0x14027e62c  mov     rcx, [rbp+1A8h]; this
0x14027e633  test    eax, eax
0x14027e635  js      loc_14027EA3E
0x14027e63b  cmp     dword ptr [rsp+2A0h+var_260], 4
0x14027e640  jz      loc_14027EA1F
0x14027e646  lea     r8, [rbx+20h]
0x14027e64a  lea     rdx, [rsp+78h]
0x14027e64f  lea     rcx, [rbp+1A0h+var_1A8]
0x14027e653  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x14027e658  mov     rdx, [rax]
0x14027e65b  add     rdx, 40h ; '@'
0x14027e65f  lea     rcx, [rbp+1A0h+pszPath]
0x14027e663  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14027e668  nop
0x14027e669  lea     rcx, [rbp+1A0h+pszPath]
0x14027e66d  cmp     [rbp+1A0h+var_1B0], 7
0x14027e672  cmova   rcx, [rbp+1A0h+pszPath]; pszPath
0x14027e677  call    cs:__imp_PathRemoveFileSpecW
0x14027e67e  nop     dword ptr [rax+rax+00h]
0x14027e683  test    eax, eax
0x14027e685  jz      loc_14027EA00
0x14027e68b  lea     rax, [rbp+1A0h+pszPath]
0x14027e68f  cmp     [rbp+1A0h+var_1B0], 7
0x14027e694  cmova   rax, [rbp+1A0h+pszPath]
0x14027e699  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14027e69d  inc     rdx
0x14027e6a0  cmp     [rax+rdx*2], r12w
0x14027e6a5  jnz     short loc_14027E69D
0x14027e6a7  lea     rcx, [rbp+1A0h+pszPath]; Src
0x14027e6ab  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14027e6b0  mov     rcx, [rbx+40h]
0x14027e6b4  mov     rax, [rbx+48h]
0x14027e6b8  sub     rax, rcx
0x14027e6bb  sar     rax, 5
0x14027e6bf  cmp     r12, rax
0x14027e6c2  jnb     loc_14027E90D
0x14027e6c8  mov     r15, r12
0x14027e6cb  shl     r15, 5
0x14027e6cf  lea     rdx, [rcx+r15]
0x14027e6d3  lea     rcx, [rbp+1A0h+Src]
0x14027e6d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14027e6dc  nop
0x14027e6dd  lea     rcx, [rbp+1A0h+Src]
0x14027e6e1  cmp     [rbp+1A0h+var_158], 7
0x14027e6e6  cmova   rcx, [rbp+1A0h+Src]; pszPath
0x14027e6eb  call    cs:__imp_PathRemoveFileSpecW
0x14027e6f2  nop     dword ptr [rax+rax+00h]
0x14027e6f7  xor     edi, edi
0x14027e6f9  test    eax, eax
0x14027e6fb  jz      loc_14027E9E1
0x14027e701  lea     rax, [rbp+1A0h+Src]
0x14027e705  cmp     [rbp+1A0h+var_158], 7
0x14027e70a  cmova   rax, [rbp+1A0h+Src]
0x14027e70f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14027e713  inc     rdx
0x14027e716  cmp     [rax+rdx*2], di
0x14027e71a  jnz     short loc_14027E713
0x14027e71c  lea     rcx, [rbp+1A0h+Src]; Src
0x14027e720  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14027e725  cmp     dword ptr [rsi+1018h], 3
0x14027e72c  jnz     loc_14027E8CF
0x14027e732  lea     rdx, [rbp+1A0h+pszPath]
0x14027e736  cmp     [rbp+1A0h+var_1B0], 7
0x14027e73b  cmova   rdx, [rbp+1A0h+pszPath]
0x14027e740  lea     rcx, [rbp+1A0h+Src]
0x14027e744  cmp     [rbp+1A0h+var_158], 7
0x14027e749  cmova   rcx, [rbp+1A0h+Src]
0x14027e74e  call    cs:__imp__o__wcsicmp
0x14027e755  nop     dword ptr [rax+rax+00h]
0x14027e75a  test    eax, eax
0x14027e75c  jz      loc_14027E8CF
0x14027e762  xorps   xmm0, xmm0
0x14027e765  movups  xmmword ptr [rbp+1A0h+lpFileName], xmm0
0x14027e769  movdqu  [rbp+1A0h+var_1F8], xmm6
0x14027e76e  mov     word ptr [rbp+1A0h+lpFileName], di
0x14027e772  lea     rdx, [rbp+1A0h+pszPath]
0x14027e776  cmp     [rbp+1A0h+var_1B0], 7
0x14027e77b  cmova   rdx, [rbp+1A0h+pszPath]
0x14027e780  mov     rcx, [rbx+40h]
0x14027e784  add     rcx, r15
0x14027e787  cmp     qword ptr [rcx+18h], 7
0x14027e78c  jbe     short loc_14027E791
0x14027e78e  mov     rcx, [rcx]
0x14027e791  lea     r8, [rbp+1A0h+lpFileName]
0x14027e795  call    ?ConstructTargetFilePath@FrUtilities@@SAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FrUtilities::ConstructTargetFilePath(ushort const *,ushort const *,std::wstring &)
0x14027e79a  lea     rcx, [rbp+1A0h+lpFileName]
0x14027e79e  cmp     qword ptr [rbp+1A0h+var_1F8+8], 7
0x14027e7a3  cmova   rcx, [rbp+1A0h+lpFileName]; this
0x14027e7a8  call    ?FileExists@VmmsPathUtilities@@YAHPEBG@Z; VmmsPathUtilities::FileExists(ushort const *)
0x14027e7ad  test    eax, eax
0x14027e7af  jz      loc_14027E86C
0x14027e7b5  lea     rcx, [rbp+1A0h+lpFileName]
0x14027e7b9  cmp     qword ptr [rbp+1A0h+var_1F8+8], 7
0x14027e7be  cmova   rcx, [rbp+1A0h+lpFileName]; lpFileName
0x14027e7c3  call    cs:__imp_DeleteFileW
0x14027e7ca  nop     dword ptr [rax+rax+00h]
0x14027e7cf  test    eax, eax
0x14027e7d1  jz      loc_14027E92D
0x14027e7d7  lea     rax, [rbp+1A0h+lpFileName]
0x14027e7db  cmp     qword ptr [rbp+1A0h+var_1F8+8], 7
0x14027e7e0  cmova   rax, [rbp+1A0h+lpFileName]
0x14027e7e5  mov     [rsp+2A0h+var_260], rax
0x14027e7ea  lea     rax, [rbp+1A0h+var_1E8]
0x14027e7ee  cmp     qword ptr [rbp+1A0h+var_1D8+8], 7
0x14027e7f3  cmova   rax, qword ptr [rbp+1A0h+var_1E8]
0x14027e7f8  mov     [rsp+2A0h+var_240], rax
0x14027e7fd  lea     rax, [rsp+2A0h+var_260]
0x14027e802  mov     [rsp+2A0h+var_278], rax; __int64
0x14027e807  lea     rax, [rsp+2A0h+var_258]
0x14027e80c  mov     [rsp+2A0h+var_280], rax; __int64
0x14027e811  lea     r9, [rsp+2A0h+var_240]
0x14027e816  mov     edx, 1; unsigned int
0x14027e81b  lea     rcx, MSVM_VMMS_FR_ENGINE_OFFLINE_IR_DELETE_FILE_WARNING; EventDescriptor
0x14027e822  call    ??$VmEventWrite@PEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG22@Z; VmEventWrite<ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&,ushort const * &&)
0x14027e827  mov     ecx, 81A2h
0x14027e82c  call    VmlIsDebugTraceEnabled
0x14027e831  test    eax, eax
0x14027e833  jz      short loc_14027E86C
0x14027e835  lea     rax, [rbp+1A0h+lpFileName]
0x14027e839  cmp     qword ptr [rbp+1A0h+var_1F8+8], 7
0x14027e83e  cmova   rax, [rbp+1A0h+lpFileName]
0x14027e843  lea     r8, [rbp+1A0h+var_1E8]
0x14027e847  cmp     qword ptr [rbp+1A0h+var_1D8+8], 7
0x14027e84c  cmova   r8, qword ptr [rbp+1A0h+var_1E8]
0x14027e851  mov     [rsp+2A0h+var_280], rax
0x14027e856  mov     r9, [rsp+2A0h+var_258]
0x14027e85b  lea     rdx, off_1409153D8; "%ws::%ws Offline Initial Replicaion del"...
0x14027e862  mov     ecx, 81A2h
0x14027e867  call    VmlDebugTraceEx
0x14027e86c  mov     r8, [rbx+40h]
0x14027e870  add     r8, r15
0x14027e873  mov     rax, [rsp+2A0h+var_250]
0x14027e878  mov     rdx, [rax+8]
0x14027e87c  mov     rcx, rax
0x14027e87f  cmp     rdx, [rax+10h]
0x14027e883  jz      short loc_14027E88F
0x14027e885  mov     rdx, r8
0x14027e888  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x14027e88d  jmp     short loc_14027E894
0x14027e88f  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x14027e894  mov     rdx, [r14+8]
0x14027e898  mov     rcx, r14
0x14027e89b  cmp     rdx, [r14+10h]
0x14027e89f  jz      short loc_14027E8AC
0x14027e8a1  lea     rdx, [rbp+1A0h+lpFileName]
0x14027e8a5  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x14027e8aa  jmp     short loc_14027E8B5
0x14027e8ac  lea     r8, [rbp+1A0h+lpFileName]
0x14027e8b0  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x14027e8b5  mov     rcx, [rbx+40h]
0x14027e8b9  add     rcx, r15
0x14027e8bc  lea     rdx, [rbp+1A0h+lpFileName]
0x14027e8c0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14027e8c5  nop
0x14027e8c6  lea     rcx, [rbp+1A0h+lpFileName]
0x14027e8ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14027e8cf  test    r12, r12
0x14027e8d2  jz      short loc_14027E8FC
0x14027e8d4  mov     rdi, [rbx+40h]
0x14027e8d8  add     rdi, r15
0x14027e8db  lea     r8, [rdi-20h]
0x14027e8df  lea     rdx, [rbp+1A0h+var_218]
0x14027e8e3  lea     rcx, [rbp+1A0h+var_198]
0x14027e8e7  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x14027e8ec  mov     rcx, [rax]
0x14027e8ef  add     rcx, 40h ; '@'
0x14027e8f3  mov     rdx, rdi
0x14027e8f6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14027e8fb  nop
0x14027e8fc  lea     rcx, [rbp+1A0h+Src]
  ... truncated ...
```
