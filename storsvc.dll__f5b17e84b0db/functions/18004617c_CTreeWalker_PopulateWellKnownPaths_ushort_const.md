# CTreeWalker::PopulateWellKnownPaths(ushort const *)

- ea: `0x18004617c`
- end: `0x180047dff`
- name: `?PopulateWellKnownPaths@CTreeWalker@@QEAAJPEBG@Z`
- size: `7299`
- prototype: `__int64 __fastcall(CTreeWalker *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040da4`

## callees

- `0x18000d030`
- `0x18000dd8c`
- `0x18000ddb0`
- `0x180012ce0`
- `0x180014a00`
- `0x180019d4c`
- `0x180019d94`
- `0x18001c130`
- `0x18001c208`
- `0x18001c3d8`
- `0x18001dcf4`
- `0x18001ea50`
- `0x18001eae8`
- `0x18001ee68`
- `0x18001f634`
- `0x18001f824`
- `0x18002ce80`
- `0x18003ce8c`
- `0x18003cf58`
- `0x18003d884`
- `0x18003da18`
- `0x18003dd14`
- `0x18003df68`
- `0x18003df84`
- `0x18003e090`
- `0x180041414`
- `0x180042084`
- `0x180042124`
- `0x180042a0c`
- `0x18004617c`
- `0x18004b390`
- `0x18004b588`
- `0x18004bd60`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800465e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800467b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180046cd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180047368`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800465e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800467b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180046cd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180047368`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047767`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047767`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004774a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004774a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047dae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047ba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800479f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800479f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047a05`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047bbb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004644a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004644a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004702d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047d35`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047d60`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004702d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047d35`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047d60`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047a2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047a7d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047a2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047a7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047a51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047a51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047af8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047bb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047af8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047bb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800463b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800463b4`
- `RPCRT4!RpcImpersonateClient` at `0x180046943`
- `RPCRT4!RpcImpersonateClient` at `0x18004706c`
- `RPCRT4!RpcImpersonateClient` at `0x180046943`
- `RPCRT4!RpcImpersonateClient` at `0x18004706c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004686b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004686b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046235`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046728`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046c3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800472bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046235`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046728`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046c3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800472bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800465cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800465cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046609`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180047a93`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180047a93`

## string_xrefs

- `0x180046d89`: `\Temp`
- `0x180046efe`: `\Packages\microsoft.windowscommunicationsapps_8wekyb3d8bbwe\LocalState\LiveComm`
- `0x1800466d8`: `Staged Updates`
- `0x1800478d3`: `\Windows.old.%03d`
- `0x1800477fe`: `PreviousInstallation`
- `0x18004775d`: `GetUSDataFolderPath`
- `0x180047743`: `UNISTORE.DLL`

## pseudocode

```c
__int64 __fastcall CTreeWalker::PopulateWellKnownPaths(CTreeWalker *this, LPCWSTR lpFileName)
{
  __m128i si128; // xmm6
  char v5; // r13
  DWORD v6; // r14d
  HANDLE FileW; // rax
  char *v8; // rdi
  char *v9; // rax
  size_t v10; // rbx
  _DWORD *v11; // rbx
  unsigned int v12; // edi
  int v13; // eax
  const unsigned __int16 (*v14)[45]; // rdx
  LPVOID v15; // rbx
  __int64 v16; // r8
  const unsigned __int16 *v17; // rax
  FOLDER_USAGE *v18; // rax
  __int64 v19; // rax
  unsigned int i; // ebx
  const unsigned __int16 * near *v21; // rdx
  __int64 v22; // r8
  const unsigned __int16 *v23; // rax
  FOLDER_USAGE *v24; // rax
  __int64 v25; // rax
  int v26; // ebx
  const unsigned __int16 * near *v27; // rdx
  __int64 v28; // r8
  const unsigned __int16 *v29; // rax
  FOLDER_USAGE *v30; // rax
  __int64 v31; // rax
  unsigned int j; // ebx
  const unsigned __int16 * near *v33; // rdx
  __int64 v34; // r8
  const unsigned __int16 *v35; // rax
  FOLDER_USAGE *v36; // rax
  __int64 v37; // rax
  unsigned int k; // ebx
  const unsigned __int16 * near *v39; // rdx
  __int64 v40; // r8
  const unsigned __int16 *v41; // rax
  FOLDER_USAGE *v42; // rax
  __int64 v43; // rax
  unsigned int m; // ebx
  const unsigned __int16 * near *v45; // rdx
  __int64 v46; // r8
  const unsigned __int16 *v47; // rax
  FOLDER_USAGE *v48; // rax
  __int64 v49; // rax
  signed int n; // r15d
  unsigned __int64 v51; // rbx
  int v52; // edi
  int v53; // eax
  const unsigned __int16 *v54; // rax
  int FileId; // edi
  __m256i *v56; // rcx
  const unsigned __int16 *v57; // rax
  FOLDER_USAGE *v58; // rax
  __int64 v59; // rax
  const unsigned __int16 *v60; // rax
  FOLDER_USAGE *v61; // rax
  __int64 v62; // rax
  const unsigned __int16 *v63; // rax
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v65; // rax
  FOLDER_USAGE *v66; // rax
  __int64 v67; // rax
  unsigned __int64 v68; // rcx
  FOLDER_USAGE *v69; // rax
  __int64 v70; // rax
  int v71; // ecx
  char IsEnabled; // al
  __int64 v73; // r12
  int v74; // r15d
  int (__fastcall *v75)(LPVOID, _QWORD, __int64 *); // rbx
  __int64 v76; // r14
  __int64 v77; // rdi
  __int64 (__fastcall *v78)(__int64, _QWORD, __int64 *); // rbx
  int v79; // ebx
  wchar_t *v80; // rdx
  __int64 v81; // r8
  const unsigned __int16 *v82; // rax
  FOLDER_USAGE *v83; // rax
  __int64 v84; // rax
  unsigned int ii; // ebx
  wchar_t *v86; // rdx
  __int64 v87; // r8
  const unsigned __int16 *v88; // rax
  FOLDER_USAGE *v89; // rax
  __int64 v90; // rax
  unsigned int v91; // ebx
  const unsigned __int16 * near *v92; // rdx
  __int64 v93; // r8
  const unsigned __int16 *v94; // rax
  FOLDER_USAGE *v95; // rax
  __int64 v96; // rax
  const unsigned __int16 *v97; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FOLDER_USAGE *v100; // rax
  __int64 v101; // rax
  int v102; // ebx
  const unsigned __int16 * near *v103; // rdx
  __int64 v104; // r8
  const unsigned __int16 *v105; // rax
  FOLDER_USAGE *v106; // rax
  __int64 v107; // rax
  int jj; // ebx
  __int64 v109; // r8
  const unsigned __int16 *v110; // rax
  FOLDER_USAGE *v111; // rax
  __int64 v112; // rax
  HANDLE CurrentThread; // rax
  PSID *v114; // rbx
  __int64 v115; // r8
  const unsigned __int16 *v116; // rax
  FOLDER_USAGE *v117; // rax
  __int64 v118; // rax
  unsigned int kk; // ebx
  const unsigned __int16 * near *v120; // rdx
  __int64 v121; // r8
  const unsigned __int16 *v122; // rax
  FOLDER_USAGE *v123; // rax
  __int64 v124; // rax
  unsigned int mm; // ebx
  const unsigned __int16 * near *v126; // rdx
  __int64 v127; // r8
  const unsigned __int16 *v128; // rax
  __int64 v129; // rcx
  __int64 v130; // rcx
  __int64 v132; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v133; // [rsp+50h] [rbp-B8h] BYREF
  char v134; // [rsp+52h] [rbp-B6h]
  LPVOID pv; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID TokenHandle[2]; // [rsp+60h] [rbp-A8h] BYREF
  BSTR bstrString[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v138; // [rsp+80h] [rbp-88h] BYREF
  LPVOID v139; // [rsp+88h] [rbp-80h] BYREF
  __int64 v140; // [rsp+90h] [rbp-78h] BYREF
  __int64 v141; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v142[16]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v143; // [rsp+B0h] [rbp-58h] BYREF
  HANDLE hDevice; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v145; // [rsp+C0h] [rbp-48h] BYREF
  int v146; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v147; // [rsp+D0h] [rbp-38h]
  HSTRING string; // [rsp+D8h] [rbp-30h]
  __int64 v149; // [rsp+E0h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v151[16]; // [rsp+F0h] [rbp-18h] BYREF
  void *lpOutBuffer[2]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v153; // [rsp+110h] [rbp+8h]
  _BYTE v154[80]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v155; // [rsp+168h] [rbp+60h] BYREF
  PSRWLOCK SRWLock; // [rsp+170h] [rbp+68h] BYREF
  __int64 v157; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v158[80]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v159[16]; // [rsp+1D0h] [rbp+C8h] BYREF
  _BYTE v160[16]; // [rsp+1E0h] [rbp+D8h] BYREF
  char v161[16]; // [rsp+1F0h] [rbp+E8h] BYREF
  char v162[16]; // [rsp+200h] [rbp+F8h] BYREF
  char v163[16]; // [rsp+210h] [rbp+108h] BYREF
  _BYTE v164[72]; // [rsp+220h] [rbp+118h] BYREF
  _BYTE v165[72]; // [rsp+268h] [rbp+160h] BYREF
  _BYTE v166[72]; // [rsp+2B0h] [rbp+1A8h] BYREF
  _BYTE v167[80]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE v168[80]; // [rsp+348h] [rbp+240h] BYREF
  _BYTE v169[80]; // [rsp+398h] [rbp+290h] BYREF
  _OWORD v170[2]; // [rsp+3E8h] [rbp+2E0h] BYREF
  int v171; // [rsp+408h] [rbp+300h] BYREF
  __int128 v172; // [rsp+410h] [rbp+308h]
  const wchar_t *v173; // [rsp+420h] [rbp+318h]
  __int64 v174; // [rsp+428h] [rbp+320h]
  __int128 v175; // [rsp+450h] [rbp+348h] BYREF
  __m128i v176; // [rsp+460h] [rbp+358h]
  __m256i v177; // [rsp+470h] [rbp+368h] BYREF
  __int64 v178; // [rsp+490h] [rbp+388h]
  _OWORD v179[2]; // [rsp+498h] [rbp+390h] BYREF
  _OWORD v180[2]; // [rsp+4B8h] [rbp+3B0h] BYREF
  HSTRING v181; // [rsp+4D8h] [rbp+3D0h] BYREF
  unsigned __int16 v182[264]; // [rsp+4F8h] [rbp+3F0h] BYREF

  v141 = (__int64)lpFileName;
  v132 = 0;
  v139 = 0;
  v170[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v170[1] = si128;
  LOWORD(v170[0]) = 0;
  v5 = 0;
  ppv = 0;
  v157 = 0;
  v155 = 0;
  v146 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive((char *)this + 288, &SRWLock);
  if ( CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, &ppv) >= 0
    && (*(int (__fastcall **)(LPVOID, LPCWSTR, int *, __int64 *, __int64 *))(*(_QWORD *)ppv + 200LL))(
         ppv,
         lpFileName,
         &v146,
         &v157,
         &v155) >= 0 )
  {
    v177.m256i_i32[0] = 26;
    *(_OWORD *)&v177.m256i_u64[1] = *(_OWORD *)v177.m256i_i8;
    v177.m256i_i64[3] = (__int64)L"System Restore";
    v178 = v155;
    std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
      this,
      TokenHandle,
      &v177);
  }
  v171 = 1;
  v173 = L"System";
  v174 = 0;
  std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
    this,
    TokenHandle,
    &v171);
  v171 = 30;
  v173 = L"Hard reserve area";
  v174 = 0;
  std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
    this,
    TokenHandle,
    &v171);
  v171 = 31;
  v173 = L"Soft reserve area";
  v174 = 0;
  std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
    this,
    TokenHandle,
    &v171);
  v171 = 32;
  v173 = L"Scratch reserve area";
  v174 = 0;
  std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
    this,
    TokenHandle,
    &v171);
  hDevice = (HANDLE)-1LL;
  *(_OWORD *)lpOutBuffer = 0;
  v153 = 0;
  v6 = 56;
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hDevice,
    FileW);
  if ( hDevice != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      v8 = (char *)lpOutBuffer[1];
      if ( (void *)v6 >= (void *)((char *)lpOutBuffer[1] - (char *)lpOutBuffer[0]) )
      {
        if ( (void *)v6 <= (void *)((char *)lpOutBuffer[1] - (char *)lpOutBuffer[0]) )
          goto LABEL_12;
        if ( v6 > v153 - (unsigned __int64)lpOutBuffer[0] )
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpOutBuffer, v6);
          goto LABEL_12;
        }
        v10 = v6 - (unsigned __int64)((char *)lpOutBuffer[1] - (char *)lpOutBuffer[0]);
        memset_0(lpOutBuffer[1], 0, v10);
        v9 = &v8[v10];
      }
      else
      {
        v9 = (char *)lpOutBuffer[0] + v6;
      }
      lpOutBuffer[1] = v9;
LABEL_12:
      v11 = lpOutBuffer[0];
      v12 = 0;
      if ( DeviceIoControl(hDevice, 0x90414u, 0, 0, lpOutBuffer[0], v6, 0, 0) )
      {
        if ( v11[1] )
        {
          do
          {
            if ( (unsigned int)(v11[6 * v12 + 2] - 1) <= 2 )
            {
              LODWORD(TokenHandle[0]) = v11[6 * v12 + 2];
              TokenHandle[1] = *(LPVOID *)&v11[6 * v12 + 4];
              std::_Tree<std::_Tmap_traits<enum _STORAGE_RESERVE_ID,unsigned __int64,std::less<enum _STORAGE_RESERVE_ID>,std::allocator<std::pair<enum _STORAGE_RESERVE_ID const,unsigned __int64>>,0>>::_Emplace<std::pair<enum _STORAGE_RESERVE_ID const,unsigned __int64>>(
                (char *)this + 248,
                bstrString,
                TokenHandle);
            }
            ++v12;
          }
          while ( v12 < v11[1] );
        }
        break;
      }
      if ( GetLastError() != 234 )
        break;
      v13 = 1;
      if ( v11[1] > 1u )
        v13 = v11[1];
      v6 = 24 * v13 + 8;
    }
  }
  std::vector<unsigned char>::_Tidy(lpOutBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
  v149 = 0;
  Windows::Internal::StringReference::StringReference(&v181, v14);
  v145 = 0;
  v140 = 0;
  v147 = 0;
  v133 = 0;
  string = 0;
  if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(
              v181,
              &v149) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v149 + 88LL))(v149, &v145) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v145 + 48LL))(v145, &v140) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v140 + 56LL))(v140, &v133);
  }
  v171 = 29;
  v173 = L"Staged Updates";
  v174 = 0;
  std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
    this,
    bstrString,
    &v171);
  TokenHandle[0] = 0;
  pv = 0;
  if ( CoCreateInstance(&CLSID_WindowsUpdateAgentInfo, 0, 1u, &GUID_85713fa1_7796_4fa2_be3b_e2d6124dd373, TokenHandle) >= 0 )
  {
    v15 = pv;
    pv = 0;
    if ( TokenHandle[0] )
      (**(void (__fastcall ***)(LPVOID, GUID *, LPVOID *))TokenHandle[0])(
        TokenHandle[0],
        &GUID_ab9032bf_f394_4bb1_b379_bb806cac59ce,
        &pv);
    if ( v15 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
    if ( pv )
    {
      bstrString[0] = 0;
      if ( (*(int (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)pv + 24LL))(pv, bstrString) >= 0
        && !(unsigned int)_o__wcsnicmp((char *)this + 328, bstrString[0], 2) )
      {
        std::wstring::assign(v170, L"\\\\.\\");
        v16 = -1;
        do
          ++v16;
        while ( bstrString[0][v16] );
        std::wstring::_Append<unsigned short>(v170, bstrString[0]);
        v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
        if ( CTreeWalker::QueryFileId(this, v17, &v132) >= 0 )
        {
          v18 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)&v171, -2, 0x1Du, 0);
          v19 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v154, &v132, v18);
          std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
            (char *)this + 64,
            v151,
            v19);
          std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v154);
          FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)&v171);
        }
      }
      SysFreeString(bstrString[0]);
    }
  }
  ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&pv);
  ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(TokenHandle);
  for ( i = 0; i < 4; ++i )
  {
    std::wstring::assign(v170, lpFileName);
    v21 = (&WellKnownUpdateStagingAreas)[i];
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    std::wstring::_Append<unsigned short>(v170, v21);
    v23 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
    if ( CTreeWalker::QueryFileId(this, v23, &v132) >= 0 )
    {
      v24 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)&v171, -2, 0x1Du, 0);
      v25 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v154, &v132, v24);
      std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
        (char *)this + 64,
        v151,
        v25);
      std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v154);
      FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)&v171);
    }
  }
  if ( RpcImpersonateClient(0) < 0 )
    goto LABEL_175;
  v5 = 1;
  v134 = 1;
  v26 = 0;
  do
  {
    std::wstring::assign(v170, lpFileName);
    v27 = (&AppsWellKnownPaths)[v26];
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    std::wstring::_Append<unsigned short>(v170, v27);
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
    if ( CTreeWalker::QueryFileId(this, v29, &v132) >= 0 )
    {
      v30 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)&v171, -2, 7u, 0);
      v31 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v154, &v132, v30);
      std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
        (char *)this + 64,
        v151,
        v31);
      std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v154);
      FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)&v171);
    }
    ++v26;
  }
  while ( !v26 );
  for ( j = 0; j < 4; ++j )
  {
    std::wstring::assign(v170, lpFileName);
    v33 = (&ClassicAppsWellKnownPaths)[j];
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    std::wstring::_Append<unsigned short>(v170, v33);
    v35 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
    if ( CTreeWalker::QueryFileId(this, v35, &v132) >= 0 )
    {
      v36 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)&v171, -2, 0x12u, 0);
      v37 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v154, &v132, v36);
      std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
        (char *)this + 64,
        v151,
        v37);
      std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v154);
      FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)&v171);
    }
  }
  for ( k = 0; k < 8; ++k )
  {
    std::wstring::assign(v170, lpFileName);
    v39 = (&SystemWellKnownPaths)[k];
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    std::wstring::_Append<unsigned short>(v170, v39);
    v41 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
    if ( CTreeWalker::QueryFileId(this, v41, &v132) >= 0 )
    {
      v42 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)&v171, -2, 1u, 0);
      v43 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v154, &v132, v42);
      std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
        (char *)this + 64,
        v151,
        v43);
      std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v154);
      FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)&v171);
    }
  }
  for ( m = 0; m < 0x53; ++m )
  {
    std::wstring::assign(v170, lpFileName);
    v45 = (&DefaultWin32Paths)[m];
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    std::wstring::_Append<unsigned short>(v170, v45);
    v47 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
    if ( CTreeWalker::QueryFileId(this, v47, &v132) >= 0 )
    {
      v48 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)&v171, -2, 1u, 0);
      v49 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v154, &v132, v48);
      std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
        (char *)this + 64,
        v151,
        v49);
      std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v154);
      FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)&v171);
    }
  }
  if ( CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &v139) < 0 )
    goto LABEL_175;
  for ( n = 0; (unsigned int)n < 0xE; ++n )
  {
    TokenHandle[0] = 0;
    pv = 0;
    v51 = 32LL * n;
    if ( (*(int (__fastcall **)(LPVOID, int *, LPVOID *))(*(_QWORD *)v139 + 48LL))(
           v139,
           &dword_1800BF5E4[v51 / 4],
           TokenHandle) < 0 )
      continue;
    v52 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)TokenHandle[0] + 48LL))(
            TokenHandle[0],
            0,
            &pv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)TokenHandle[0] + 16LL))(TokenHandle[0]);
    if ( (unsigned int)_o__wcsnicmp((char *)this + 328, pv, 2) )
    {
      v171 = *(_DWORD *)((char *)&WellKnownUserFolders + v51);
      v173 = (&off_1800BF5F8)[v51 / 8];
      v174 = 0;
      std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
        this,
        v151,
        &v171);
      continue;
    }
    if ( v52 >= 0 )
    {
      v53 = *(_DWORD *)((char *)&WellKnownUserFolders + v51);
      switch ( v53 )
      {
        case 10:
          v175 = 0;
          v176 = si128;
          LOWORD(v175) = 0;
          std::wstring::assign(&v175, pv);
          if ( !memcmp_0(&dword_1800BF5E4[v51 / 4], &FOLDERID_LocalAppData, 0x10u) )
            std::wstring::_Append<unsigned short>(&v175, L"\\Temp");
          v54 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v175);
          FileId = CTreeWalker::QueryFileId(this, v54, &v132);
          v56 = (__m256i *)&v175;
          break;
        case 12:
          v179[0] = 0;
          v179[1] = si128;
          LOWORD(v179[0]) = 0;
          v171 = *(_DWORD *)((char *)&WellKnownUserFolders + v51);
          v172 = *(_OWORD *)&dword_1800BF5E4[v51 / 4];
          v173 = (&off_1800BF5F8)[v51 / 8];
          v174 = 0;
          std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
            this,
            v162,
            &v171);
          std::wstring::assign(v179, pv);
          std::wstring::_Append<unsigned short>(v179, L"\\Microsoft\\Outlook");
          v57 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v179);
          if ( CTreeWalker::QueryFileId(this, v57, &v132) >= 0 )
          {
            v58 = FOLDER_USAGE::FOLDER_USAGE(
                    (FOLDER_USAGE *)v164,
                    -2,
                    *(_DWORD *)((char *)&WellKnownUserFolders + v51),
                    0);
            v59 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v167, &v132, v58);
            std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
              (char *)this + 64,
              v163,
              v59);
            std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v167);
            FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v164);
          }
          std::wstring::assign(v179, pv);
          std::wstring::_Append<unsigned short>(
            v179,
            L"\\Packages\\microsoft.windowscommunicationsapps_8wekyb3d8bbwe\\LocalState\\LiveComm");
          v60 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v179);
          FileId = CTreeWalker::QueryFileId(this, v60, &v132);
          if ( FileId >= 0 )
          {
            v61 = FOLDER_USAGE::FOLDER_USAGE(
                    (FOLDER_USAGE *)v165,
                    -2,
                    *(_DWORD *)((char *)&WellKnownUserFolders + v51),
                    0);
            v62 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v168, &v132, v61);
            std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
              (char *)this + 64,
              v161,
              v62);
            std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v168);
            FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v165);
          }
          v56 = (__m256i *)v179;
          break;
        case 7:
          v180[0] = 0;
          v180[1] = si128;
          LOWORD(v180[0]) = 0;
          std::wstring::assign(v180, pv);
          if ( !memcmp_0(&dword_1800BF5E4[v51 / 4], &FOLDERID_LocalAppData, 0x10u) )
          {
            std::wstring::_Append<unsigned short>(v180, L"\\Packages");
            v63 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v180);
            FileId = CTreeWalker::QueryFileId(this, v63, &v132);
          }
          else
          {
            RevertToSelf();
            std::wstring::_Append<unsigned short>(v180, L"\\windowsapps");
            v64 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v180);
            FileId = CTreeWalker::QueryFileId(this, v64, &v132);
            RpcImpersonateClient(0);
          }
          v56 = (__m256i *)v180;
          break;
        default:
          FileId = CTreeWalker::QueryFileId(this, (const unsigned __int16 *)pv, &v132);
          if ( memcmp_0(&dword_1800BF5E4[v51 / 4], &FOLDERID_Profile, 0x10u) )
          {
LABEL_95:
            CoTaskMemFree(pv);
            if ( FileId >= 0 )
            {
              v68 = 32LL * n;
              v171 = *(_DWORD *)((char *)&WellKnownUserFolders + v68);
              v172 = *(_OWORD *)&dword_1800BF5E4[v68 / 4];
              v173 = (&off_1800BF5F8)[v68 / 8];
              v174 = 0;
              std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
                this,
                v160,
                &v171);
              v69 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, *((_DWORD *)&WellKnownUserFolders + 8 * n), 0);
              v70 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v69);
              std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
                (char *)this + 64,
                v142,
                v70);
              std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
              FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
              v71 = *((_DWORD *)&WellKnownUserFolders + 8 * n);
              if ( v71 == 28 || v71 == 9 )
                std::list<__int64>::_Emplace<__int64>((char *)this + 160, *((_QWORD *)this + 20), &v132);
            }
            continue;
          }
          std::list<__int64>::_Emplace<__int64>((char *)this + 144, *((_QWORD *)this + 18), &v132);
          bstrString[0] = 0;
          std::wstring::wstring(&v177, pv);
          std::wstring::_Append<unsigned short>(&v177, L"\\AppData");
          v65 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v177);
          FileId = CTreeWalker::QueryFileId(this, v65, (__int64 *)bstrString);
          if ( FileId >= 0 )
          {
            v66 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v166, -2, 0x12u, 0);
            v67 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v169, bstrString, v66);
            std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
              (char *)this + 64,
              v159,
              v67);
            std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v169);
            FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v166);
          }
          v56 = &v177;
          break;
      }
      std::wstring::_Tidy_deallocate(v56);
      goto LABEL_95;
    }
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_46956793>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_46956793>::GetImpl'::`2'::impl);
  v73 = v141;
  v5 = 1;
  if ( !IsEnabled )
    goto LABEL_115;
  if ( CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &v139) >= 0 )
  {
    v74 = 0;
    do
    {
      v143 = 0;
      v138 = 0;
      v75 = *(int (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v139 + 48LL);
      v143 = 0;
      v76 = 32LL * v74;
      if ( v75(v139, *(_QWORD *)((char *)&off_1800BF7A8 + v76), &v143) >= 0 )
      {
        v77 = v143;
        v78 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v143 + 48LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v138,
          0);
        v79 = v78(v77, 0, &v138);
        if ( (unsigned int)_o__wcsnicmp((char *)this + 328, v138, 2) )
        {
          v171 = *(_DWORD *)((char *)&WellKnownA9Paths + v76);
          v173 = off_1800BF7B0[4 * v74];
          v174 = 0;
          std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
            this,
            v142,
            &v171);
        }
        else if ( v79 >= 0 )
        {
          if ( *(_DWORD *)((char *)&WellKnownA9Paths + v76) == 33 )
          {
            v175 = 0;
            v176 = si128;
            LOWORD(v175) = 0;
            std::wstring::assign(&v175, v138);
            v80 = off_1800BF7B8[4 * v74];
            v81 = -1;
            do
              ++v81;
            while ( v80[v81] );
            std::wstring::_Append<unsigned short>(&v175, v80);
            v82 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v175);
            v79 = CTreeWalker::QueryFileId(this, v82, &v132);
            std::wstring::_Tidy_deallocate(&v175);
          }
          if ( v79 >= 0 )
          {
            v171 = *(_DWORD *)((char *)&WellKnownA9Paths + v76);
            v172 = *(_OWORD *)*((_QWORD *)&off_1800BF7A8 + 4 * v74);
            v173 = off_1800BF7B0[4 * v74];
            v174 = 0;
            std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
              this,
              v160,
              &v171);
            v83 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, *(_DWORD *)((char *)&WellKnownA9Paths + v76), 0);
            v84 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v83);
            std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
              (char *)this + 64,
              v159,
              v84);
            std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
            FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v138);
      ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&v143);
      ++v74;
    }
    while ( !v74 );
    v73 = v141;
LABEL_115:
    v171 = 0;
    v173 = L"Others";
    v174 = 0;
    std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
      this,
      v142,
      &v171);
    for ( ii = 0; ii < 2; ++ii )
    {
      std::wstring::assign(v170, v73);
      v86 = (&off_1800BF0E8)[2 * (int)ii];
      v87 = -1;
      do
        ++v87;
      while ( v86[v87] );
      std::wstring::_Append<unsigned short>(v170, v86);
      v88 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
      if ( CTreeWalker::QueryFileId(this, v88, &v132) >= 0 )
      {
        v89 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 0, 0);
        v90 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v89);
        std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
          (char *)this + 64,
          v142,
          v90);
        std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
        FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
        if ( v132 != 0x5000000000005LL )
          std::list<__int64>::_Emplace<__int64>((char *)this + 144, *((_QWORD *)this + 18), &v132);
        std::list<__int64>::_Emplace<__int64>((char *)this + 160, *((_QWORD *)this + 20), &v132);
      }
    }
    v91 = 0;
    v5 = v134;
    do
    {
      std::wstring::assign(v170, v73);
      v92 = (&TempWellKnownPaths)[v91];
      v93 = -1;
      do
        ++v93;
      while ( *((_WORD *)v92 + v93) );
      std::wstring::_Append<unsigned short>(v170, v92);
      v94 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
      if ( CTreeWalker::QueryFileId(this, v94, &v132) >= 0 )
      {
        v95 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 0xAu, 0);
        v96 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v95);
        std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
          (char *)this + 64,
          v142,
          v96);
        std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
        FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
      }
      ++v91;
    }
    while ( v91 < 0xE );
    std::wstring::assign(v170, v73);
    std::wstring::_Append<unsigned short>(v170, L"\\Windows\\Memory.dmp");
    v97 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
    if ( CTreeWalker::QueryFileId(this, v97, &v132) >= 0 )
      *((_QWORD *)this + 40) = v132;
    Library = LoadLibraryExW(L"UNISTORE.DLL", 0, 0);
    v141 = (__int64)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetUSDataFolderPath");
      if ( ProcAddress )
      {
        if ( ((int (__fastcall *)(unsigned __int16 *, __int64))ProcAddress)(v182, 260) >= 0
          && CTreeWalker::QueryFileId(this, v182, &v132) >= 0 )
        {
          v100 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 0xCu, 0);
          v101 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v100);
          std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
            (char *)this + 64,
            v142,
            v101);
          std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
          FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v141);
    v171 = 27;
    v173 = L"PreviousInstallation";
    v174 = 0;
    std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
      this,
      v142,
      &v171);
    v102 = 0;
    do
    {
      std::wstring::assign(v170, v73);
      v103 = (&TempWindowsRollbackKnownPaths)[v102];
      v104 = -1;
      do
        ++v104;
      while ( *((_WORD *)v103 + v104) );
      std::wstring::_Append<unsigned short>(v170, v103);
      v105 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
      if ( CTreeWalker::QueryFileId(this, v105, &v132) >= 0 )
      {
        v106 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 0x1Bu, 0);
        v107 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v106);
        std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
          (char *)this + 64,
          v142,
          v107);
        std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
        FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
      }
      ++v102;
    }
    while ( !v102 );
    v177 = *(__m256i *)L"\\Windows.old.%03d";
    LODWORD(v178) = *(_DWORD *)L"d";
    memset_0(v182, 0, 0x208u);
    for ( jj = 0; jj < 10; ++jj )
    {
      if ( StringCchPrintfW(v182, 0x104u, (const unsigned __int16 *)&v177, (unsigned int)jj) >= 0 )
      {
        std::wstring::assign(v170, v73);
        v109 = -1;
        do
          ++v109;
        while ( v182[v109] );
        std::wstring::_Append<unsigned short>(v170, v182);
        v110 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
        if ( CTreeWalker::QueryFileId(this, v110, &v132) >= 0 )
        {
          v111 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 0x1Bu, 0);
          v112 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v111);
          std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
            (char *)this + 64,
            v142,
            v112);
          std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
          FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
        }
      }
    }
    bstrString[0] = 0;
    LODWORD(pv) = 0;
    TokenHandle[0] = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, TokenHandle) )
    {
      if ( !GetTokenInformation(TokenHandle[0], TokenUser, 0, (DWORD)pv, (PDWORD)&pv) && GetLastError() == 122 )
      {
        v114 = (PSID *)LocalAlloc(0x40u, (unsigned int)pv);
        if ( v114 )
        {
          if ( GetTokenInformation(TokenHandle[0], TokenUser, v114, (DWORD)pv, (PDWORD)&pv)
            && ConvertSidToStringSidW(*v114, bstrString)
            && bstrString[0] )
          {
            std::wstring::assign(v170, v73);
            std::wstring::_Append<unsigned short>(v170, L"\\$Recycle.Bin\\");
            v115 = -1;
            do
              ++v115;
            while ( bstrString[0][v115] );
            std::wstring::_Append<unsigned short>(v170, bstrString[0]);
            LocalFree(bstrString[0]);
            v116 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
            if ( CTreeWalker::QueryFileId(this, v116, &v132) >= 0 )
            {
              v171 = 22;
              v173 = L"Recycle";
              v174 = 0;
              std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
                this,
                v142,
                &v171);
              v117 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 0x16u, 0);
              v118 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v117);
              std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
                (char *)this + 64,
                v142,
                v118);
              std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
              FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
            }
          }
          else
          {
            GetLastError();
          }
          LocalFree(v114);
        }
      }
      CloseHandle(TokenHandle[0]);
      v171 = 8;
      v173 = L"Maps data";
      v174 = 0;
      std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(
        this,
        v142,
        &v171);
      for ( kk = 0; kk < 2; ++kk )
      {
        std::wstring::assign(v170, v73);
        v120 = (&MapsDataWellKnownPaths)[kk];
        v121 = -1;
        do
          ++v121;
        while ( *((_WORD *)v120 + v121) );
        std::wstring::_Append<unsigned short>(v170, v120);
        v122 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
        if ( CTreeWalker::QueryFileId(this, v122, &v132) >= 0 )
        {
          v123 = FOLDER_USAGE::FOLDER_USAGE((FOLDER_USAGE *)v154, -2, 8u, 0);
          v124 = std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(v158, &v132, v123);
          std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(
            (char *)this + 64,
            v142,
            v124);
          std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(v158);
          FOLDER_USAGE::~FOLDER_USAGE((FOLDER_USAGE *)v154);
        }
      }
      for ( mm = 0; mm < 6; ++mm )
      {
        std::wstring::assign(v170, v73);
        v126 = (&ExcludedRootFolders)[mm];
        v127 = -1;
        do
          ++v127;
        while ( *((_WORD *)v126 + v127) );
        std::wstring::_Append<unsigned short>(v170, v126);
        v128 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v170);
        if ( CTreeWalker::QueryFileId(this, v128, &v132) >= 0 )
          std::list<__int64>::_Emplace<__int64>((char *)this + 128, *((_QWORD *)this + 16), &v132);
      }
      v141 = 0x5000000000005LL;
      std::list<__int64>::_Emplace<__int64>((char *)this + 144, *((_QWORD *)this + 18), &v141);
      RevertToSelf();
      v5 = 0;
      CTreeWalker::AddDesktopAppFolders(this);
    }
  }
LABEL_175:
  if ( v139 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v139 + 16LL))(v139);
  if ( v5 )
    RevertToSelf();
  v129 = v140;
  if ( v140 )
  {
    v140 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
  }
  v130 = v145;
  if ( v145 )
  {
    v145 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v149);
  if ( SRWLock )
  {
    ReleaseSRWLockExclusive(SRWLock);
    SRWLock = 0;
  }
  ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&ppv);
  std::wstring::_Tidy_deallocate(v170);
  return 0;
}

```

## disassembly

```asm
0x18004617c  mov     rax, rsp
0x18004617f  mov     [rax+18h], rbx
0x180046183  push    rbp
0x180046184  push    rsi
0x180046185  push    rdi
0x180046186  push    r12
0x180046188  push    r13
0x18004618a  push    r14
0x18004618c  push    r15
0x18004618e  lea     rbp, [rax-658h]
0x180046195  sub     rsp, 720h
0x18004619c  movaps  xmmword ptr [rax-48h], xmm6
0x1800461a0  mov     rax, cs:__security_cookie
0x1800461a7  xor     rax, rsp
0x1800461aa  mov     [rbp+650h+var_50], rax
0x1800461b1  mov     r12, rdx
0x1800461b4  mov     [rbp+650h+var_6C0], rdx
0x1800461b8  mov     rsi, rcx
0x1800461bb  xor     edi, edi
0x1800461bd  mov     [rsp+750h+var_710], rdi
0x1800461c2  mov     [rbp+650h+var_6D0], rdi
0x1800461c6  xorps   xmm0, xmm0
0x1800461c9  movups  [rbp+650h+var_370], xmm0
0x1800461d0  xorps   xmm1, xmm1
0x1800461d3  movdqu  [rbp+650h+var_360], xmm1
0x1800461db  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800461e3  movdqu  [rbp+650h+var_360], xmm6
0x1800461eb  mov     word ptr [rbp+650h+var_370], di
0x1800461f2  mov     r13b, dil
0x1800461f5  mov     [rbp+650h+var_670], rdi
0x1800461f9  mov     [rbp+650h+var_5E0], rdi
0x1800461fd  mov     [rbp+650h+var_5F0], rdi
0x180046201  mov     [rbp+650h+var_690], edi
0x180046204  add     rcx, 120h
0x18004620b  lea     rdx, [rbp+650h+SRWLock]
0x18004620f  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockExclusive@Details@234@XZ; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(void)
0x180046214  nop
0x180046215  lea     rax, [rbp+650h+var_670]
0x180046219  mov     [rsp+750h+ppv], rax; ppv
0x18004621e  lea     r9, IID_ISharedProtectionPoints; riid
0x180046225  lea     r15d, [rdi+1]
0x180046229  mov     r8d, r15d; dwClsContext
0x18004622c  xor     edx, edx; pUnkOuter
0x18004622e  lea     rcx, CLSID_SPP; rclsid
0x180046235  call    cs:__imp_CoCreateInstance
0x18004623b  test    eax, eax
0x18004623d  js      short loc_1800462B0
0x18004623f  mov     rcx, [rbp+650h+var_670]
0x180046243  mov     rax, [rcx]
0x180046246  lea     rdx, [rbp+650h+var_5F0]
0x18004624a  mov     [rsp+750h+ppv], rdx
0x18004624f  lea     r9, [rbp+650h+var_5E0]
0x180046253  lea     r8, [rbp+650h+var_690]
0x180046257  mov     rdx, r12
0x18004625a  mov     rax, [rax+0C8h]
0x180046261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046266  test    eax, eax
0x180046268  js      short loc_1800462B0
0x18004626a  mov     rax, [rbp+650h+var_5F0]
0x18004626e  mov     dword ptr [rbp+650h+var_2E8], 1Ah
0x180046278  movups  xmm0, xmmword ptr [rbp+650h+var_2E8]
0x18004627f  movdqu  xmmword ptr [rbp+650h+var_2E8+8], xmm0
0x180046287  lea     rcx, aSystemRestore; "System Restore"
0x18004628e  mov     [rbp+650h+var_2D0], rcx
0x180046295  mov     [rbp+650h+var_2C8], rax
0x18004629c  lea     r8, [rbp+650h+var_2E8]
0x1800462a3  lea     rdx, [rsp+750h+TokenHandle]
0x1800462a8  mov     rcx, rsi
0x1800462ab  call    ??$emplace@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHVSTORAGE_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(std::pair<int const,STORAGE_USAGE> &&)
0x1800462b0  mov     [rbp+650h+var_350], r15d
0x1800462b7  lea     rax, aSystem; "System"
0x1800462be  mov     [rbp+650h+var_338], rax
0x1800462c5  mov     [rbp+650h+var_330], rdi
0x1800462cc  lea     r8, [rbp+650h+var_350]
0x1800462d3  lea     rdx, [rsp+750h+TokenHandle]
0x1800462d8  mov     rcx, rsi
0x1800462db  call    ??$emplace@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHVSTORAGE_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(std::pair<int const,STORAGE_USAGE> &&)
0x1800462e0  mov     [rbp+650h+var_350], 1Eh
0x1800462ea  lea     rax, aHardReserveAre; "Hard reserve area"
0x1800462f1  mov     [rbp+650h+var_338], rax
0x1800462f8  mov     [rbp+650h+var_330], rdi
0x1800462ff  lea     r8, [rbp+650h+var_350]
0x180046306  lea     rdx, [rsp+750h+TokenHandle]
0x18004630b  mov     rcx, rsi
0x18004630e  call    ??$emplace@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHVSTORAGE_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(std::pair<int const,STORAGE_USAGE> &&)
0x180046313  mov     [rbp+650h+var_350], 1Fh
0x18004631d  lea     rax, aSoftReserveAre; "Soft reserve area"
0x180046324  mov     [rbp+650h+var_338], rax
0x18004632b  mov     [rbp+650h+var_330], rdi
0x180046332  lea     r8, [rbp+650h+var_350]
0x180046339  lea     rdx, [rsp+750h+TokenHandle]
0x18004633e  mov     rcx, rsi
0x180046341  call    ??$emplace@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHVSTORAGE_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(std::pair<int const,STORAGE_USAGE> &&)
0x180046346  mov     [rbp+650h+var_350], 20h ; ' '
0x180046350  lea     rax, aScratchReserve; "Scratch reserve area"
0x180046357  mov     [rbp+650h+var_338], rax
0x18004635e  mov     [rbp+650h+var_330], rdi
0x180046365  lea     r8, [rbp+650h+var_350]
0x18004636c  lea     rdx, [rsp+750h+TokenHandle]
0x180046371  mov     rcx, rsi
0x180046374  call    ??$emplace@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@HVSTORAGE_USAGE@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHVSTORAGE_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHVSTORAGE_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<int,STORAGE_USAGE,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,STORAGE_USAGE>>,0>>::emplace<std::pair<int const,STORAGE_USAGE>>(std::pair<int const,STORAGE_USAGE> &&)
0x180046379  mov     [rbp+650h+hDevice], 0FFFFFFFFFFFFFFFFh
0x180046381  xorps   xmm0, xmm0
0x180046384  movdqu  xmmword ptr [rbp+650h+lpOutBuffer], xmm0
0x180046389  mov     [rbp+650h+var_648], rdi
0x18004638d  mov     r14d, 38h ; '8'
0x180046393  mov     [rsp+750h+hTemplateFile], rdi; hTemplateFile
0x180046398  mov     [rsp+750h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800463a0  lea     r8d, [r14-35h]; dwShareMode
0x1800463a4  mov     dword ptr [rsp+750h+ppv], r8d; dwCreationDisposition
0x1800463a9  xor     r9d, r9d; lpSecurityAttributes
0x1800463ac  mov     edx, 0C0000000h; dwDesiredAccess
0x1800463b1  mov     rcx, r12; lpFileName
0x1800463b4  call    cs:__imp_CreateFileW
0x1800463ba  mov     rdx, rax
0x1800463bd  lea     rcx, [rbp+650h+hDevice]
0x1800463c1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800463c6  cmp     [rbp+650h+hDevice], 0FFFFFFFFFFFFFFFFh
0x1800463cb  jz      loc_1800464C1
0x1800463d1  mov     rdx, [rbp+650h+lpOutBuffer]
0x1800463d5  mov     rdi, [rbp+650h+lpOutBuffer+8]
0x1800463d9  mov     rcx, rdi
0x1800463dc  sub     rcx, rdx
0x1800463df  mov     ebx, r14d
0x1800463e2  cmp     rbx, rcx
0x1800463e5  jnb     short loc_1800463ED
0x1800463e7  lea     rax, [rdx+rbx]
0x1800463eb  jmp     short loc_18004641D
0x1800463ed  jbe     short loc_180046421
0x1800463ef  mov     rax, [rbp+650h+var_648]
0x1800463f3  sub     rax, rdx
0x1800463f6  cmp     rbx, rax
0x1800463f9  jbe     short loc_180046409
0x1800463fb  mov     rdx, rbx
0x1800463fe  lea     rcx, [rbp+650h+lpOutBuffer]
0x180046402  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180046407  jmp     short loc_180046421
0x180046409  sub     rbx, rcx
0x18004640c  mov     r8, rbx; Size
0x18004640f  xor     edx, edx; Val
0x180046411  mov     rcx, rdi; void *
0x180046414  call    memset_0
0x180046419  lea     rax, [rbx+rdi]
0x18004641d  mov     [rbp+650h+lpOutBuffer+8], rax
0x180046421  mov     rbx, [rbp+650h+lpOutBuffer]
0x180046425  xor     edi, edi
0x180046427  mov     [rsp+750h+lpOverlapped], rdi; lpOverlapped
0x18004642c  mov     [rsp+750h+hTemplateFile], rdi; lpBytesReturned
0x180046431  mov     [rsp+750h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x180046436  mov     [rsp+750h+ppv], rbx; lpOutBuffer
0x18004643b  xor     r9d, r9d; nInBufferSize
0x18004643e  xor     r8d, r8d; lpInBuffer
0x180046441  mov     edx, 90414h; dwIoControlCode
0x180046446  mov     rcx, [rbp+650h+hDevice]; hDevice
0x18004644a  call    cs:__imp_DeviceIoControl
0x180046450  test    eax, eax
0x180046452  jnz     short loc_18004647C
0x180046454  call    cs:__imp_GetLastError
0x18004645a  cmp     eax, 0EAh
0x18004645f  jnz     short loc_1800464C1
0x180046461  mov     eax, r15d
0x180046464  cmp     [rbx+4], r15d
0x180046468  cmova   eax, [rbx+4]
0x18004646c  lea     eax, [rax+rax*2]
0x18004646f  lea     r14d, ds:8[rax*8]
0x180046477  jmp     loc_1800463D1
0x18004647c  cmp     [rbx+4], edi
0x18004647f  jbe     short loc_1800464C1
0x180046481  mov     eax, edi
0x180046483  lea     rcx, [rax+rax*2]
0x180046487  mov     edx, [rbx+rcx*8+8]
0x18004648b  lea     eax, [rdx-1]
0x18004648e  cmp     eax, 2
0x180046491  ja      short loc_1800464B7
0x180046493  mov     dword ptr [rsp+750h+TokenHandle], edx
0x180046497  mov     rax, [rbx+rcx*8+10h]
0x18004649c  mov     [rsp+750h+var_6F0], rax
0x1800464a1  lea     rcx, [rsi+0F8h]
0x1800464a8  lea     r8, [rsp+750h+TokenHandle]
0x1800464ad  lea     rdx, [rsp+750h+bstrString]
0x1800464b2  call    ??$_Emplace@U?$pair@$$CBW4_STORAGE_RESERVE_ID@@_K@std@@@?$_Tree@V?$_Tmap_traits@W4_STORAGE_RESERVE_ID@@_KU?$less@W4_STORAGE_RESERVE_ID@@@std@@V?$allocator@U?$pair@$$CBW4_STORAGE_RESERVE_ID@@_K@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4_STORAGE_RESERVE_ID@@_K@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CBW4_STORAGE_RESERVE_ID@@_K@1@@Z; std::_Tree<std::_Tmap_traits<_STORAGE_RESERVE_ID,unsigned __int64,std::less<_STORAGE_RESERVE_ID>,std::allocator<std::pair<_STORAGE_RESERVE_ID const,unsigned __int64>>,0>>::_Emplace<std::pair<_STORAGE_RESERVE_ID const,unsigned __int64>>(std::pair<_STORAGE_RESERVE_ID const,unsigned __int64> &&)
0x1800464b7  add     edi, r15d
0x1800464ba  cmp     edi, [rbx+4]
0x1800464bd  jb      short loc_180046481
0x1800464bf  xor     edi, edi
0x1800464c1  lea     rcx, [rbp+650h+lpOutBuffer]
0x1800464c5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800464ca  nop
0x1800464cb  lea     rcx, [rbp+650h+hDevice]
0x1800464cf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800464d4  mov     [rbp+650h+var_678], rdi
0x1800464d8  lea     rcx, [rbp+650h+var_280]; string
0x1800464df  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800464e4  mov     [rbp+650h+var_698], rdi
0x1800464e8  mov     [rbp+650h+var_6C8], rdi
0x1800464ec  mov     [rbp+650h+var_688], rdi
0x1800464f0  mov     byte ptr [rsp+750h+var_708], dil
0x1800464f5  mov     byte ptr [rsp+750h+var_708+1], dil
0x1800464fa  mov     [rbp+650h+string], rdi
0x1800464fe  lea     rdx, [rbp+650h+var_678]
0x180046502  mov     rcx, [rbp+650h+var_280]
0x180046509  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager3@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager3@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>)
0x18004650e  mov     r14, 0FFFFFFFFFFFFFFFEh
0x180046515  test    eax, eax
0x180046517  js      loc_1800466CE
0x18004651d  mov     rcx, [rbp+650h+var_678]
0x180046521  mov     rax, [rcx]
0x180046524  lea     rdx, [rbp+650h+var_698]
0x180046528  mov     rax, [rax+58h]
0x18004652c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046531  test    eax, eax
0x180046533  js      loc_1800466CE
0x180046539  mov     rcx, [rbp+650h+var_698]
0x18004653d  mov     rax, [rcx]
0x180046540  lea     rdx, [rbp+650h+var_6C8]
0x180046544  mov     rax, [rax+30h]
0x180046548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004654d  test    eax, eax
0x18004654f  js      loc_1800466CE
0x180046555  mov     rcx, [rbp+650h+var_6C8]
0x180046559  mov     rax, [rcx]
0x18004655c  mov     rax, [rax+38h]
0x180046560  jmp     loc_1800466B5
0x180046565  mov     rcx, [rbp+650h+var_6C8]
0x180046569  mov     rax, [rcx]
0x18004656c  lea     rdx, [rbp+650h+var_688]
0x180046570  mov     rax, [rax+30h]
0x180046574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046579  test    eax, eax
0x18004657b  js      loc_1800466CE
0x180046581  mov     rcx, [rbp+650h+var_688]
0x180046585  mov     rax, [rcx]
0x180046588  lea     rdx, [rsp+750h+var_708+1]
0x18004658d  mov     rax, [rax+30h]
0x180046591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046596  test    eax, eax
0x180046598  js      loc_1800466AA
0x18004659e  cmp     byte ptr [rsp+750h+var_708+1], dil
0x1800465a3  jnz     loc_1800466AA
0x1800465a9  mov     rcx, [rbp+650h+var_688]
0x1800465ad  mov     rax, [rcx]
0x1800465b0  lea     rdx, [rbp+650h+string]
0x1800465b4  mov     rax, [rax+50h]
0x1800465b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465bd  test    eax, eax
0x1800465bf  js      loc_1800466AA
0x1800465c5  xor     edx, edx; length
0x1800465c7  mov     rcx, [rbp+650h+string]; string
0x1800465cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800465d1  mov     rdx, rax
0x1800465d4  lea     rcx, [rsi+148h]
0x1800465db  mov     r8d, 2
0x1800465e1  call    cs:__imp__o__wcsnicmp
0x1800465e7  test    eax, eax
0x1800465e9  jnz     loc_1800466AA
0x1800465ef  lea     rdx, asc_180097F88; "\\\\.\\"
0x1800465f6  lea     rcx, [rbp+650h+var_308]
0x1800465fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180046602  nop
0x180046603  xor     edx, edx; length
0x180046605  mov     rcx, [rbp+650h+string]; string
0x180046609  call    cs:__imp_WindowsGetStringRawBuffer
0x18004660f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046613  inc     r8
0x180046616  cmp     [rax+r8*2], di
0x18004661b  jnz     short loc_180046613
0x18004661d  mov     rdx, rax
0x180046620  lea     rcx, [rbp+650h+var_308]
0x180046627  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004662c  lea     rcx, [rbp+650h+var_308]
0x180046633  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046638  mov     rdx, rax; unsigned __int16 *
0x18004663b  lea     r8, [rsp+750h+var_710]; __int64 *
0x180046640  mov     rcx, rsi; this
0x180046643  call    ?QueryFileId@CTreeWalker@@QEAAJPEBGPEA_J@Z; CTreeWalker::QueryFileId(ushort const *,__int64 *)
0x180046648  test    eax, eax
0x18004664a  js      short loc_18004669E
0x18004664c  xor     r9d, r9d; unsigned __int64
0x18004664f  lea     r8d, [r9+7]; unsigned int
0x180046653  mov     rdx, r14; __int64
0x180046656  lea     rcx, [rbp+650h+var_350]; this
0x18004665d  call    ??0FOLDER_USAGE@@QEAA@_JK_K@Z; FOLDER_USAGE::FOLDER_USAGE(__int64,ulong,unsigned __int64)
0x180046662  nop
0x180046663  mov     r8, rax
0x180046666  lea     rdx, [rsp+750h+var_710]
0x18004666b  lea     rcx, [rbp+650h+var_640]
0x18004666f  call    ??$?0AEA_JVFOLDER_USAGE@@$0A@@?$pair@$$CB_JVFOLDER_USAGE@@@std@@QEAA@AEA_J$$QEAVFOLDER_USAGE@@@Z; std::pair<__int64 const,FOLDER_USAGE>::pair<__int64 const,FOLDER_USAGE>(__int64 &,FOLDER_USAGE &&)
0x180046674  nop
0x180046675  lea     rcx, [rsi+40h]
0x180046679  mov     r8, rax
0x18004667c  lea     rdx, [rsp+750h+TokenHandle]
0x180046681  call    ??$emplace@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@?$_Hash@V?$_Umap_traits@_JVFOLDER_USAGE@@V?$_Uhash_compare@_JU?$hash@_J@std@@U?$equal_to@_J@2@@std@@V?$allocator@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_JVFOLDER_USAGE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CB_JVFOLDER_USAGE@@@1@@Z; std::_Hash<std::_Umap_traits<__int64,FOLDER_USAGE,std::_Uhash_compare<__int64,std::hash<__int64>,std::equal_to<__int64>>,std::allocator<std::pair<__int64 const,FOLDER_USAGE>>,0>>::emplace<std::pair<__int64 const,FOLDER_USAGE>>(std::pair<__int64 const,FOLDER_USAGE> &&)
0x180046686  nop
0x180046687  lea     rcx, [rbp+650h+var_640]
0x18004668b  call    ??1?$pair@$$CB_JVFOLDER_USAGE@@@std@@QEAA@XZ; std::pair<__int64 const,FOLDER_USAGE>::~pair<__int64 const,FOLDER_USAGE>(void)
0x180046690  nop
0x180046691  lea     rcx, [rbp+650h+var_350]; this
0x180046698  call    ??1FOLDER_USAGE@@QEAA@XZ; FOLDER_USAGE::~FOLDER_USAGE(void)
0x18004669d  nop
0x18004669e  lea     rcx, [rbp+650h+var_308]
  ... truncated ...
```
