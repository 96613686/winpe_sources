# CClassificationSessionBase::CreatePropertyBagForPath(ushort const *,ulong,long,ATL::CComObject<CPropertyBag> * *)

- ea: `0x180096d3c`
- end: `0x180098371`
- name: `?CreatePropertyBagForPath@CClassificationSessionBase@@QEAAJPEBGKJPEAPEAV?$CComObject@VCPropertyBag@@@ATL@@@Z`
- size: `5685`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, int, _QWORD *)`
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062b10`
- `0x1800640e4`

## callees

- `0x180001350`
- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x180010bc4`
- `0x180034b2c`
- `0x180050bec`
- `0x180050e18`
- `0x180050fd0`
- `0x180051278`
- `0x1800513f8`
- `0x180051570`
- `0x180061be4`
- `0x18006febc`
- `0x1800700b8`
- `0x180070648`
- `0x180070bd8`
- `0x180073a80`
- `0x180073f54`
- `0x18007c030`
- `0x18007dbc0`
- `0x18007ecc8`
- `0x1800827e4`
- `0x180083a68`
- `0x18008e8c4`
- `0x180095680`
- `0x180096c0c`
- `0x180096d3c`
- `0x1800a51e8`
- `0x1800a53a4`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800971ea`
- `ole32!CoTaskMemFree` at `0x180097201`
- `ole32!CoTaskMemFree` at `0x180097216`
- `ole32!CoTaskMemFree` at `0x18009722b`
- `ole32!CoTaskMemFree` at `0x180097251`
- `ole32!CoTaskMemFree` at `0x18009726c`
- `ole32!CoTaskMemFree` at `0x1800975f2`
- `ole32!CoTaskMemFree` at `0x180097607`
- `ole32!CoTaskMemFree` at `0x18009761c`
- `ole32!CoTaskMemFree` at `0x180097631`
- `ole32!CoTaskMemFree` at `0x180097657`
- `ole32!CoTaskMemFree` at `0x180097672`
- `ole32!CoTaskMemFree` at `0x180097e89`
- `ole32!CoTaskMemFree` at `0x180097e9e`
- `ole32!CoTaskMemFree` at `0x180097eb3`
- `ole32!CoTaskMemFree` at `0x180097ec8`
- `ole32!CoTaskMemFree` at `0x180097eee`
- `ole32!CoTaskMemFree` at `0x180097f09`
- `ole32!CoTaskMemFree` at `0x1800971ea`
- `ole32!CoTaskMemFree` at `0x180097201`
- `ole32!CoTaskMemFree` at `0x180097216`
- `ole32!CoTaskMemFree` at `0x18009722b`
- `ole32!CoTaskMemFree` at `0x180097251`
- `ole32!CoTaskMemFree` at `0x18009726c`
- `ole32!CoTaskMemFree` at `0x1800975f2`
- `ole32!CoTaskMemFree` at `0x180097607`
- `ole32!CoTaskMemFree` at `0x18009761c`
- `ole32!CoTaskMemFree` at `0x180097631`
- `ole32!CoTaskMemFree` at `0x180097657`
- `ole32!CoTaskMemFree` at `0x180097672`
- `ole32!CoTaskMemFree` at `0x180097e89`
- `ole32!CoTaskMemFree` at `0x180097e9e`
- `ole32!CoTaskMemFree` at `0x180097eb3`
- `ole32!CoTaskMemFree` at `0x180097ec8`
- `ole32!CoTaskMemFree` at `0x180097eee`
- `ole32!CoTaskMemFree` at `0x180097f09`
- `KERNEL32!CreateFileW` at `0x180097424`
- `KERNEL32!CreateFileW` at `0x180097424`
- `KERNEL32!CloseHandle` at `0x1800971bc`
- `KERNEL32!CloseHandle` at `0x180097561`
- `KERNEL32!CloseHandle` at `0x1800975cf`
- `KERNEL32!CloseHandle` at `0x180097dfd`
- `KERNEL32!CloseHandle` at `0x180097e66`
- `KERNEL32!CloseHandle` at `0x1800971bc`
- `KERNEL32!CloseHandle` at `0x180097561`
- `KERNEL32!CloseHandle` at `0x1800975cf`
- `KERNEL32!CloseHandle` at `0x180097dfd`
- `KERNEL32!CloseHandle` at `0x180097e66`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180097d1c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180097d1c`
- `KERNEL32!GetLastError` at `0x180097f61`
- `KERNEL32!GetLastError` at `0x180097f61`
- `KERNEL32!LocalFree` at `0x180097967`
- `KERNEL32!LocalFree` at `0x180097c47`
- `KERNEL32!LocalFree` at `0x180097dd4`
- `KERNEL32!LocalFree` at `0x180097967`
- `KERNEL32!LocalFree` at `0x180097c47`
- `KERNEL32!LocalFree` at `0x180097dd4`
- `KERNEL32!GetFileAttributesW` at `0x180098290`
- `KERNEL32!GetFileAttributesW` at `0x180098290`
- `KERNEL32!GetFileInformationByHandle` at `0x180097361`
- `KERNEL32!GetFileInformationByHandle` at `0x1800974a0`
- `KERNEL32!GetFileInformationByHandle` at `0x180097361`
- `KERNEL32!GetFileInformationByHandle` at `0x1800974a0`
- `KERNEL32!DeviceIoControl` at `0x1800978d2`
- `KERNEL32!DeviceIoControl` at `0x1800978d2`
- `KERNEL32!GetFileSizeEx` at `0x180097a85`
- `KERNEL32!GetFileSizeEx` at `0x180097a85`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1800977ef`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180097a46`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1800977ef`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180097a46`
- `ADVAPI32!GetSecurityInfo` at `0x180097b12`
- `ADVAPI32!GetSecurityInfo` at `0x180097b12`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097b57`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097c19`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097b57`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180097c19`
- `SHLWAPI!PathFindFileNameW` at `0x1800976bf`
- `SHLWAPI!PathFindFileNameW` at `0x1800976bf`

## string_xrefs

- `0x180096dad`: `CClassificationSessionBase::CreatePropertyBagForPath`
- `0x180096d9f`: `base\fs\fsrm\service\pipeline\classsession.cpp`
- `0x180097b8a`: `GetSecurityInfo for '%s' with access %#x failed with %#x; using WinNullSid`

## pseudocode

```c
__int64 __fastcall CClassificationSessionBase::CreatePropertyBagForPath(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        _QWORD *a5)
{
  bool v7; // dl
  bool IsRemotePath; // r13
  WCHAR *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rbx
  char v12; // di
  char v13; // r14
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r15
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  void *v20; // r12
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v25; // rcx
  WCHAR *v26; // rdx
  __int64 v27; // rcx
  HANDLE FileW; // rsi
  int v29; // edx
  __int64 v30; // rax
  void **v31; // r9
  __int64 v32; // rcx
  LPWSTR FileNameW; // rax
  LPWSTR v34; // r8
  unsigned __int64 v35; // rdx
  WCHAR *v36; // rcx
  __int64 v37; // rax
  WCHAR v38; // r9
  HANDLE v39; // r15
  int v40; // edx
  int v41; // ecx
  char v42; // r14
  unsigned int *v43; // rdi
  __int64 v44; // r13
  __int64 v45; // rax
  unsigned int v46; // r14d
  __int64 v47; // rsi
  __int64 v48; // rbx
  PSECURITY_DESCRIPTOR v49; // rdi
  DWORD SecurityInfo; // eax
  enum WELL_KNOWN_SID_TYPE v51; // edx
  PSID v52; // rbx
  __int64 v53; // rcx
  __int64 v54; // rcx
  void **v55; // r9
  int v56; // ecx
  __int64 v57; // rbx
  bool v58; // r14
  unsigned __int16 *v59; // rax
  __int64 v60; // rax
  unsigned int v61; // ebx
  DWORD LastError; // eax
  signed int v63; // ebx
  char v64; // al
  int v65; // eax
  char v66; // al
  int v67; // eax
  char v68; // al
  int v69; // eax
  char v70; // al
  int v71; // eax
  char v72; // al
  int v73; // eax
  char v74; // al
  char v75; // al
  int v76; // eax
  char v77; // al
  int v78; // eax
  char v79; // al
  char v80; // al
  int LastFailureAsHRESULT; // eax
  char v82; // al
  int v83; // eax
  char v84; // al
  int v85; // eax
  char v86; // al
  DWORD FileAttributesW; // eax
  int v88; // eax
  char v89; // al
  char v90; // al
  char Hr; // al
  struct _SECURITY_ATTRIBUTES *dwCreationDisposition; // [rsp+20h] [rbp-658h]
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-650h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-650h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-648h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-640h]
  LPCWSTR pszPath; // [rsp+50h] [rbp-628h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-620h] BYREF
  bool v99; // [rsp+60h] [rbp-618h] BYREF
  bool v100; // [rsp+61h] [rbp-617h]
  char v101; // [rsp+62h] [rbp-616h]
  LPVOID pv; // [rsp+68h] [rbp-610h] BYREF
  struct _SECURITY_ATTRIBUTES v103; // [rsp+70h] [rbp-608h] BYREF
  __int64 v104; // [rsp+88h] [rbp-5F0h] BYREF
  int v105; // [rsp+90h] [rbp-5E8h]
  _BYTE v106[4]; // [rsp+94h] [rbp-5E4h] BYREF
  void **v107; // [rsp+98h] [rbp-5E0h]
  __int64 v108; // [rsp+A0h] [rbp-5D8h]
  void **v109; // [rsp+A8h] [rbp-5D0h]
  __int64 v110; // [rsp+B0h] [rbp-5C8h]
  unsigned int v111; // [rsp+B8h] [rbp-5C0h] BYREF
  unsigned int v112[2]; // [rsp+C0h] [rbp-5B8h] BYREF
  unsigned __int64 v113; // [rsp+C8h] [rbp-5B0h]
  void **v114; // [rsp+D0h] [rbp-5A8h] BYREF
  LPVOID lpOutBuffer; // [rsp+D8h] [rbp-5A0h]
  HANDLE hObject; // [rsp+E0h] [rbp-598h] BYREF
  DWORD BytesReturned; // [rsp+E8h] [rbp-590h] BYREF
  int v118; // [rsp+ECh] [rbp-58Ch]
  void **v119; // [rsp+F0h] [rbp-588h] BYREF
  PSID pSourceSid; // [rsp+F8h] [rbp-580h]
  int v121; // [rsp+100h] [rbp-578h]
  void **v122; // [rsp+108h] [rbp-570h]
  PSECURITY_DESCRIPTOR v123; // [rsp+110h] [rbp-568h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+118h] [rbp-560h] BYREF
  PSID ppsidOwner; // [rsp+120h] [rbp-558h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+128h] [rbp-550h] BYREF
  HANDLE v127; // [rsp+130h] [rbp-548h]
  unsigned __int64 v128; // [rsp+138h] [rbp-540h]
  WCHAR *v129; // [rsp+140h] [rbp-538h]
  __int64 i; // [rsp+148h] [rbp-530h]
  union _LARGE_INTEGER FileSize; // [rsp+150h] [rbp-528h] BYREF
  _QWORD *v132; // [rsp+158h] [rbp-520h]
  __int64 v133; // [rsp+168h] [rbp-510h]
  unsigned __int64 v134; // [rsp+170h] [rbp-508h]
  LPWSTR v135; // [rsp+178h] [rbp-500h]
  const unsigned __int16 *v136; // [rsp+180h] [rbp-4F8h]
  _QWORD v137[3]; // [rsp+198h] [rbp-4E0h] BYREF
  int v138; // [rsp+1B0h] [rbp-4C8h]
  int v139; // [rsp+1B4h] [rbp-4C4h]
  int v140; // [rsp+1B8h] [rbp-4C0h]
  _DWORD v141[28]; // [rsp+1C0h] [rbp-4B8h] BYREF
  void **v142; // [rsp+230h] [rbp-448h] BYREF
  int v143; // [rsp+238h] [rbp-440h]
  void *Block[2]; // [rsp+2E0h] [rbp-398h] BYREF
  __int64 v145; // [rsp+2F0h] [rbp-388h]
  unsigned __int64 v146; // [rsp+2F8h] [rbp-380h]
  __int128 v147; // [rsp+308h] [rbp-370h] BYREF
  __int128 v148; // [rsp+318h] [rbp-360h]
  __int64 v149; // [rsp+328h] [rbp-350h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+330h] [rbp-348h] BYREF
  __int128 v151; // [rsp+368h] [rbp-310h] BYREF
  __int64 v152; // [rsp+378h] [rbp-300h]
  int v153; // [rsp+380h] [rbp-2F8h] BYREF
  __int128 v154; // [rsp+384h] [rbp-2F4h]
  __int64 v155; // [rsp+394h] [rbp-2E4h]
  union _LARGE_INTEGER v156; // [rsp+3A0h] [rbp-2D8h]
  __int64 v157; // [rsp+3A8h] [rbp-2D0h]
  unsigned __int64 v158; // [rsp+3B0h] [rbp-2C8h]
  DWORD nFileIndexLow; // [rsp+3B8h] [rbp-2C0h]
  DWORD nFileIndexHigh; // [rsp+3BCh] [rbp-2BCh]
  _WORD v161[260]; // [rsp+3C0h] [rbp-2B8h] BYREF
  unsigned int NamespaceRootIndex; // [rsp+5C8h] [rbp-B0h]
  int v163; // [rsp+5CCh] [rbp-ACh]
  _BYTE pDestinationSid[80]; // [rsp+5E0h] [rbp-98h] BYREF

  v105 = a4;
  v136 = a2;
  v104 = a1;
  v132 = a5;
  v127 = v137;
  v137[0] = L"base\\fs\\fsrm\\service\\pipeline\\classsession.cpp";
  v137[1] = L"CClassificationSessionBase::CreatePropertyBagForPath";
  v137[2] = L"CLSSESSC";
  v138 = 63;
  v139 = 22;
  v140 = 255;
  v141[24] = 0x1000000;
  memset_0(v141, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v142, v137, 0);
  if ( !a5 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x48u, Hr, 0);
  }
  *a5 = 0;
  v143 = 0;
  if ( !a2 || !*a2 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, -2147024809);
    v90 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x49u, v90, 0);
  }
  v143 = 0;
  memset_0(&v153, 0, 0x2A8u);
  pszPath = 0;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&pszPath, a2);
  SrmTrimEdgeSpace((unsigned __int16 *)pszPath);
  *(_QWORD *)&v103.bInheritHandle = 0;
  IsRemotePath = SrmIsRemotePath((wchar_t *)pszPath, v7, (unsigned __int16 **)&v103.bInheritHandle);
  v100 = IsRemotePath;
  v9 = (WCHAR *)pszPath;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( pszPath[v11] );
  v128 = v11;
  if ( *(_QWORD *)&v103.bInheritHandle && **(_WORD **)&v103.bInheritHandle )
  {
    do
      ++v10;
    while ( *(_WORD *)(*(_QWORD *)&v103.bInheritHandle + 2 * v10) );
  }
  else
  {
    v10 = 0;
  }
  if ( !v11 || (v12 = 1, pszPath[v11 - 1] != 92) )
    v12 = 0;
  v101 = v12;
  if ( IsRemotePath )
  {
    if ( v11 <= v10 )
    {
      v13 = 1;
      if ( !v12 )
      {
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&pszPath, L"\\");
        v128 = ++v11;
        v101 = 1;
LABEL_22:
        v9 = (WCHAR *)pszPath;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
  }
  else
  {
    v14 = IsVolumeRootPath(pszPath);
    v9 = (WCHAR *)pszPath;
    if ( v14 )
    {
      v13 = 1;
      goto LABEL_23;
    }
  }
  v13 = 0;
  if ( v12 )
  {
    v9[--v11] = 0;
    v128 = v11;
    goto LABEL_22;
  }
LABEL_23:
  hObject = v9;
  *(_QWORD *)v112 = 1509;
  CSrmFunctionTracerBase::AddContext(&v142, 1, v112, &hObject);
  v16 = 260;
  if ( v11 >= 0x104 && *pszPath != 92 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, -2147200214);
    v64 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x76u, v64, 0);
  }
  v143 = 0;
  CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)v106, v15, !IsRemotePath);
  lpFileName = 0;
  v103.lpSecurityDescriptor = 0;
  *(_QWORD *)&v103.nLength = 0;
  pv = 0;
  v99 = 0;
  if ( IsRemotePath )
  {
    CScanInformation::GetRemoteNamespaceVolumePaths(
      pszPath,
      *(const unsigned __int16 **)&v103.bInheritHandle,
      (struct CSrmAutoPWSZ *)&lpFileName,
      (struct CSrmAutoPWSZ *)&v103.lpSecurityDescriptor,
      (struct CSrmAutoPWSZ *)&v103,
      (struct CSrmAutoPWSZ *)&pv);
    v163 |= 0x20000u;
LABEL_29:
    v17 = v104;
    goto LABEL_33;
  }
  if ( (v105 & 0x10) != 0 )
  {
    CScanInformation::GetNamespaceVolumePathsLight(
      pszPath,
      (struct CSrmAutoPWSZ *)&lpFileName,
      (struct CSrmAutoPWSZ *)&v103.lpSecurityDescriptor,
      (struct CSrmAutoPWSZ *)&v103,
      (struct CSrmAutoPWSZ *)&pv);
    goto LABEL_29;
  }
  v17 = v104;
  v18 = *(_QWORD *)(v104 + 16);
  v19 = v18 + 8;
  if ( !v18 )
    v19 = 16;
  CScanInformation::GetNamespaceVolumePaths(
    pszPath,
    (struct CSrmVssUtil *)v19,
    (struct CSrmAutoPWSZ *)&lpFileName,
    (struct CSrmAutoPWSZ *)&v103.lpSecurityDescriptor,
    (struct CSrmAutoPWSZ *)&v103,
    (struct CSrmAutoPWSZ *)&pv,
    &v99);
LABEL_33:
  v111 = 0;
  v108 = -1;
  v107 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v20 = SrmCreateFileWithAlternateAccess(
          pszPath,
          a3 | 0x20000,
          a3,
          7u,
          dwCreationDisposition,
          dwFlagsAndAttributes,
          0x2200000u,
          lpOverlapped,
          0,
          &v111);
  hObject = v20;
  v21 = -1;
  v108 = (__int64)v20;
  if ( v20 == (void *)-1LL )
  {
    LastError = GetLastError();
    v63 = LastError;
    v118 = LastError;
    if ( LastError == 32 )
    {
      v143 = -2147200134;
      v85 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v85);
      v86 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0xBEu, v86, 0);
    }
    if ( LastError == 5 )
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW == -1 || (FileAttributesW & 1) == 0 )
      {
LABEL_147:
        v63 = (unsigned __int16)v63 | 0x80070000;
LABEL_148:
        v143 = v63;
        v88 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v88);
        v89 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0xCCu, v89, 0);
      }
      v63 = 6009;
      v118 = 6009;
    }
    if ( v63 <= 0 )
      goto LABEL_148;
    goto LABEL_147;
  }
  v112[0] = -1;
  if ( *(_BYTE *)(v17 + 8) )
  {
    v22 = *(_QWORD *)(v17 + 16);
    v23 = v22 + 224;
    if ( !v22 )
      v23 = 232;
    v112[0] = CNamespaceIndexCache::FindVolumeIndex((CNamespaceIndexCache *)v23, (const unsigned __int16 *)pv);
    if ( v112[0] == -1 )
    {
      v107 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
      CloseHandle(v20);
      v107 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
      v108 = -1;
      CoTaskMemFree(pv);
      pv = 0;
      CoTaskMemFree(*(LPVOID *)&v103.nLength);
      *(_QWORD *)&v103.nLength = 0;
      CoTaskMemFree(v103.lpSecurityDescriptor);
      v103.lpSecurityDescriptor = 0;
      CoTaskMemFree((LPVOID)lpFileName);
      lpFileName = 0;
      CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v106);
      CoTaskMemFree(*(LPVOID *)&v103.bInheritHandle);
      *(_QWORD *)&v103.bInheritHandle = 0;
      CoTaskMemFree((LPVOID)pszPath);
      pszPath = 0;
      v142 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v142);
      return 2147767167LL;
    }
    v21 = -1;
  }
  v146 = 7;
  v145 = 0;
  LOWORD(Block[0]) = 0;
  v25 = -1;
  do
    ++v25;
  while ( *((_WORD *)v103.lpSecurityDescriptor + v25) );
  if ( v25 )
    v26 = (WCHAR *)&lpFileName[v25 - 1];
  else
    v26 = (WCHAR *)lpFileName;
  do
    ++v21;
  while ( v26[v21] );
  std::wstring::assign(Block, v26);
  CVolumePathInfo::NormalizeRelativePath(Block);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(v20, &FileInformation) )
  {
    v65 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v65);
    v66 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0xF5u, v66, 0);
  }
  v143 = 0;
  v113 = __PAIR64__(FileInformation.nFileIndexHigh, FileInformation.nFileIndexLow);
  nFileIndexLow = FileInformation.nFileIndexLow;
  nFileIndexHigh = FileInformation.nFileIndexHigh;
  v27 = -1;
  do
    ++v27;
  while ( lpFileName[v27] );
  if ( lpFileName[v27 - 1] != 92 )
    CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&lpFileName, L"\\");
  v110 = -1;
  v109 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2000000u, 0);
  v127 = FileW;
  v110 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v83 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v83);
    v84 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x10Eu, v84, 0);
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  v143 = 0;
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    v67 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v67);
    v68 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x111u, v68, 0);
  }
  v29 = 0;
  v143 = 0;
  v113 = __PAIR64__(FileInformation.nFileIndexHigh, FileInformation.nFileIndexLow);
  v158 = __PAIR64__(FileInformation.nFileIndexHigh, FileInformation.nFileIndexLow);
  NamespaceRootIndex = -1;
  if ( *(_BYTE *)(v104 + 8) )
  {
    v30 = *(_QWORD *)(v104 + 16);
    v31 = Block;
    if ( v146 >= 8 )
      v31 = (void **)Block[0];
    v32 = v30 + 224;
    if ( !v30 )
      v32 = 232;
    NamespaceRootIndex = CNamespaceIndexCache::FindNamespaceRootIndex(
                           (CNamespaceIndexCache *)v32,
                           v112[0],
                           v113,
                           (const unsigned __int16 *)v31);
    if ( NamespaceRootIndex == -1 )
    {
      v109 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
      CloseHandle(FileW);
      v109 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
      v110 = -1;
      if ( v146 >= 8 )
        operator delete(Block[0]);
      v146 = 7;
      v145 = 0;
      LOWORD(Block[0]) = 0;
      v107 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
      CloseHandle(hObject);
      v107 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
      v108 = -1;
      CoTaskMemFree(pv);
      pv = 0;
      CoTaskMemFree(*(LPVOID *)&v103.nLength);
      *(_QWORD *)&v103.nLength = 0;
      CoTaskMemFree(v103.lpSecurityDescriptor);
      v103.lpSecurityDescriptor = 0;
      CoTaskMemFree((LPVOID)lpFileName);
      lpFileName = 0;
      CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v106);
      CoTaskMemFree(*(LPVOID *)&v103.bInheritHandle);
      *(_QWORD *)&v103.bInheritHandle = 0;
      CoTaskMemFree((LPVOID)pszPath);
      pszPath = 0;
      v142 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v142);
      return 2147767167LL;
    }
    v29 = v143;
  }
  if ( !v13 )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v34 = FileNameW;
    v35 = -1;
    do
      ++v35;
    while ( FileNameW[v35] );
    if ( v35 <= 0x7FFFFFFE )
    {
      v134 = v35;
      v135 = FileNameW;
      v133 = 260;
      v36 = v161;
      v129 = v161;
      v37 = 0;
      for ( i = 0; v16; i = v37 )
      {
        if ( !v35 )
          break;
        v38 = *v34;
        if ( !*v34 )
          break;
        v135 = ++v34;
        *v36++ = v38;
        v129 = v36;
        v133 = --v16;
        v134 = --v35;
        ++v37;
      }
      v29 = 0;
      if ( !v16 )
      {
        v129 = --v36;
        i = v37 - 1;
        v29 = -2147024774;
      }
      *v36 = 0;
    }
    else
    {
      v29 = -2147024809;
      v161[0] = 0;
    }
    v143 = v29;
    if ( v29 < 0 )
    {
      v69 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v69);
      v70 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x132u, v70, 0);
    }
    v143 = v29;
  }
  v147 = 0;
  v148 = 0;
  v149 = 0;
  v143 = v29;
  v39 = hObject;
  if ( !GetFileInformationByHandleEx(hObject, FileBasicInfo, &v147, 0x28u) )
  {
    v71 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v71);
    v72 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x136u, v72, 0);
  }
  v40 = 0;
  v143 = 0;
  v41 = v149;
  if ( (v149 & 0x400) != 0 )
  {
    if ( (v149 & 0x10) != 0 || (v42 = v105, (v105 & 0x20) != 0) )
    {
      lpOutBuffer = 0;
      v114 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
      BytesReturned = 0;
      CSrmAutoLocalPtr_Storage<_REPARSE_GUID_DATA_BUFFER *>::AllocateBytes(&v114, 0);
      v43 = (unsigned int *)lpOutBuffer;
      if ( !DeviceIoControl(v39, 0x900A8u, 0, 0, lpOutBuffer, 0x4000u, &BytesReturned, 0) )
      {
        v73 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v73);
        v74 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x14Au, v74, 0);
      }
      v143 = 0;
      v44 = v104;
      v45 = *(_QWORD *)(v104 + 16);
      v46 = *v43;
      v47 = v45 + 306;
      if ( !v45 )
        v47 = 314;
      v48 = v45 + 312;
      if ( !v45 )
        v48 = 320;
      if ( !*(_BYTE *)v47 )
      {
        CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify((CReparsePointTagsToClassify *)v48);
        *(_BYTE *)v47 = 1;
      }
      if ( !CReparsePointTagsToClassify::CanReparsePointTagBeClassified((CReparsePointTagsToClassify *)v48, v46) )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, -2147200170);
        v75 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x14Du, v75, 0);
      }
      v143 = 0;
      v114 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
      if ( v43 )
        LocalFree(v43);
      v114 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
      lpOutBuffer = 0;
      v40 = v143;
      v41 = v149;
      FileW = v127;
      v42 = v105;
      goto LABEL_95;
    }
  }
  else
  {
    v42 = v105;
  }
  v44 = v104;
LABEL_95:
  v154 = v147;
  v155 = v148;
  v153 = v41;
  v151 = 0;
  v152 = 0;
  v143 = v40;
  if ( !GetFileInformationByHandleEx(v39, FileStandardInfo, &v151, 0x18u) )
  {
    v76 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v76);
    v77 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x15Bu, v77, 0);
  }
  v157 = v151;
  FileSize.QuadPart = 0;
  v143 = 0;
  if ( !GetFileSizeEx(v39, &FileSize) )
  {
    v78 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, v78);
    v79 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x163u, v79, 0);
  }
  v143 = 0;
  v156 = FileSize;
  ppsidOwner = 0;
  ppSecurityDescriptor = 0;
  v49 = 0;
  v123 = 0;
  v122 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  SecurityInfo = GetSecurityInfo(v39, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    LODWORD(hTemplateFile) = SecurityInfo;
    dwFlagsAndAttributesa[0] = v111;
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v142,
      0x8Cu,
      0x182u,
      L"GetSecurityInfo for '%s' with access %#x failed with %#x; using WinNullSid",
      pszPath,
      *(_QWORD *)dwFlagsAndAttributesa,
      hTemplateFile);
    pSourceSid = 0;
    v119 = &CAutoSid::`vftable';
    v121 = 8;
    CAutoSid::CreateBasicSid((CAutoSid *)&v119, v51);
    v52 = pSourceSid;
    if ( !CopySid(0x44u, pDestinationSid, pSourceSid) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v53, 0);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, LastFailureAsHRESULT);
      v82 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x186u, v82, 0);
    }
    v143 = 0;
    v119 = &CSrmAuto<_SID *,CSrmAutoGenericValue_Storage<_SID *,0,void * (*)(void *),&void * LocalFree(void *),_SID * & (*)(_SID * &),&public: static _SID * & DTyper<_SID *>::Identity(_SID * &)>>::`vftable';
    if ( v52 )
      LocalFree(v52);
    v119 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
    pSourceSid = 0;
  }
  else
  {
    v49 = ppSecurityDescriptor;
    v123 = ppSecurityDescriptor;
    if ( !CopySid(0x44u, pDestinationSid, ppsidOwner) )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v142, -2147200225);
      v80 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v142);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v142, 0x17Bu, v80, 0);
    }
    v143 = 0;
  }
  CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v106);
  if ( v100 || (v42 & 8) != 0 )
    goto LABEL_112;
  v54 = *(_QWORD *)(v44 + 16);
  v55 = Block;
  if ( v146 >= 8 )
    v55 = (void **)Block[0];
  if ( !v54 )
    v54 = 8;
  if ( !CClassificationSessionConfiguration::IsProtectedPath(
          (CClassificationSessionConfiguration *)v54,
          (const unsigned __int16 *)pv,
          (struct SRM_FILE_INFO *)&v153,
          (const unsigned __int16 *)v55) )
  {
LABEL_112:
    v56 = v163;
  }
  else
  {
    v56 = v163 | 0x20000000;
    v163 |= 0x20000000u;
  }
  if ( (v42 & 1) == 0 )
  {
    v56 |= 0x10000u;
    v163 = v56;
  }
  if ( (v42 & 4) != 0 )
    v163 = v56 | 0x8000;
  v57 = (unsigned __int64)v136 & -(__int64)((v42 & 2) != 0);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v104 = 0;
  v58 = (v42 & 0x40) != 0;
  v59 = (unsigned __int16 *)Block;
  if ( v146 >= 8 )
    v59 = (unsigned __int16 *)Block[0];
  CPropertyBag::CreateInstance(
    (unsigned __int16 *)pv,
    v112[0],
    (struct SRM_FILE_INFO *)&v153,
    *(unsigned __int16 **)&v103.nLength,
    v59,
    *(_QWORD *)&SystemTimeAsFileTime,
    v58,
    v57,
    (__int64)&v104);
  v60 = v104;
  v104 = 0;
  *v132 = v60;
  v122 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  if ( v49 )
    LocalFree(v49);
  v123 = 0;
  v109 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  v109 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  v110 = -1;
  if ( v146 >= 8 )
    operator delete(Block[0]);
  v146 = 7;
  v145 = 0;
  LOWORD(Block[0]) = 0;
  v107 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( v39 != (HANDLE)-1LL )
    CloseHandle(v39);
  v107 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  v108 = -1;
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(*(LPVOID *)&v103.nLength);
  *(_QWORD *)&v103.nLength = 0;
  CoTaskMemFree(v103.lpSecurityDescriptor);
  v103.lpSecurityDescriptor = 0;
  CoTaskMemFree((LPVOID)lpFileName);
  lpFileName = 0;
  CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v106);
  CoTaskMemFree(*(LPVOID *)&v103.bInheritHandle);
  *(_QWORD *)&v103.bInheritHandle = 0;
  CoTaskMemFree((LPVOID)pszPath);
  pszPath = 0;
  v61 = v143;
  v142 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v142);
  return v61;
}

```

## disassembly

```asm
0x180096d3c  mov     r11, rsp
0x180096d3f  push    rbx
0x180096d40  push    rsi
0x180096d41  push    rdi
0x180096d42  push    r12
0x180096d44  push    r13
0x180096d46  push    r14
0x180096d48  push    r15
0x180096d4a  sub     rsp, 640h
0x180096d51  mov     rax, cs:__security_cookie
0x180096d58  xor     rax, rsp
0x180096d5b  mov     [rsp+678h+var_48], rax
0x180096d63  mov     [rsp+678h+var_5E8], r9d
0x180096d6b  mov     r12d, r8d
0x180096d6e  mov     rbx, rdx
0x180096d71  mov     [rsp+678h+var_4F8], rdx
0x180096d79  mov     [rsp+678h+var_5F0], rcx
0x180096d81  mov     rdi, [rsp+678h+arg_20]
0x180096d89  mov     [rsp+678h+var_520], rdi
0x180096d91  lea     rax, [r11-4E0h]
0x180096d98  mov     [r11-548h], rax
0x180096d9f  lea     rax, aBaseFsFsrmServ_30; "base\\fs\\fsrm\\service\\pipeline\\clas"...
0x180096da6  mov     [r11-4E0h], rax
0x180096dad  lea     rax, aCclassificatio; "CClassificationSessionBase::CreatePrope"...
0x180096db4  mov     [r11-4D8h], rax
0x180096dbb  lea     rax, aClssessc; "CLSSESSC"
0x180096dc2  mov     [r11-4D0h], rax
0x180096dc9  mov     [rsp+678h+var_4C8], 3Fh ; '?'
0x180096dd4  mov     [rsp+678h+var_4C4], 16h
0x180096ddf  mov     [rsp+678h+var_4C0], 0FFh
0x180096dea  xor     r15d, r15d
0x180096ded  mov     [rsp+678h+var_458], 1000000h
0x180096df8  xor     edx, edx; Val
0x180096dfa  lea     r8d, [r15+60h]; Size
0x180096dfe  lea     rcx, [r11-4B8h]; void *
0x180096e05  call    memset_0
0x180096e0a  nop
0x180096e0b  xor     r8d, r8d
0x180096e0e  lea     rdx, [rsp+678h+var_4E0]
0x180096e16  lea     rcx, [rsp+678h+var_448]
0x180096e1e  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180096e23  nop
0x180096e24  test    rdi, rdi
0x180096e27  jz      short loc_180096E2C
0x180096e29  mov     [rdi], r15
0x180096e2c  mov     eax, [rsp+678h+var_440]
0x180096e33  mov     [rsp+678h+var_440], eax
0x180096e3a  test    rdi, rdi
0x180096e3d  jz      loc_180098339
0x180096e43  mov     [rsp+678h+var_440], r15d
0x180096e4b  mov     [rsp+678h+var_440], r15d
0x180096e53  test    rbx, rbx
0x180096e56  jz      loc_180098303
0x180096e5c  cmp     [rbx], r15w
0x180096e60  jz      loc_180098303
0x180096e66  mov     [rsp+678h+var_440], r15d
0x180096e6e  xor     edx, edx; Val
0x180096e70  mov     r8d, 2A8h; Size
0x180096e76  lea     rcx, [rsp+678h+var_2F8]; void *
0x180096e7e  call    memset_0
0x180096e83  mov     [rsp+678h+pszPath], r15
0x180096e88  mov     rdx, rbx; unsigned __int16 *
0x180096e8b  lea     rcx, [rsp+678h+pszPath]; this
0x180096e90  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180096e95  mov     rcx, [rsp+678h+pszPath]; unsigned __int16 *
0x180096e9a  call    ?SrmTrimEdgeSpace@@YAXPEAG@Z; SrmTrimEdgeSpace(ushort *)
0x180096e9f  mov     qword ptr [rsp+678h+var_608.bInheritHandle], r15
0x180096ea7  lea     r8, [rsp+678h+var_608.bInheritHandle]; unsigned __int16 **
0x180096eaf  mov     rcx, [rsp+678h+pszPath]; String1
0x180096eb4  call    ?SrmIsRemotePath@@YA_NPEBG_NPEAPEAG@Z; SrmIsRemotePath(ushort const *,bool,ushort * *)
0x180096eb9  mov     r13b, al
0x180096ebc  mov     [rsp+678h+var_617], al
0x180096ec0  mov     rcx, [rsp+678h+pszPath]; lpszFileName
0x180096ec5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180096ec9  mov     rbx, rdx
0x180096ecc  inc     rbx
0x180096ecf  cmp     [rcx+rbx*2], r15w
0x180096ed4  jnz     short loc_180096ECC
0x180096ed6  mov     [rsp+678h+var_540], rbx
0x180096ede  mov     rax, qword ptr [rsp+678h+var_608.bInheritHandle]
0x180096ee6  test    rax, rax
0x180096ee9  jz      short loc_180096EFD
0x180096eeb  cmp     [rax], r15w
0x180096eef  jz      short loc_180096EFD
0x180096ef1  inc     rdx
0x180096ef4  cmp     [rax+rdx*2], r15w
0x180096ef9  jnz     short loc_180096EF1
0x180096efb  jmp     short loc_180096F00
0x180096efd  mov     rdx, r15
0x180096f00  mov     esi, 5Ch ; '\'
0x180096f05  test    rbx, rbx
0x180096f08  jz      short loc_180096F14
0x180096f0a  cmp     si, [rcx+rbx*2-2]
0x180096f0f  mov     dil, 1
0x180096f12  jz      short loc_180096F17
0x180096f14  mov     dil, r15b
0x180096f17  mov     [rsp+678h+var_616], dil
0x180096f1c  test    r13b, r13b
0x180096f1f  jz      short loc_180096F51
0x180096f21  cmp     rbx, rdx
0x180096f24  ja      short loc_180096F64
0x180096f26  mov     r14b, 1
0x180096f29  test    dil, dil
0x180096f2c  jnz     short loc_180096F82
0x180096f2e  lea     rdx, psz; "\\"
0x180096f35  lea     rcx, [rsp+678h+pszPath]; this
0x180096f3a  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x180096f3f  inc     rbx
0x180096f42  mov     [rsp+678h+var_540], rbx
0x180096f4a  mov     [rsp+678h+var_616], r14b
0x180096f4f  jmp     short loc_180096F7D
0x180096f51  call    ?IsVolumeRootPath@@YAHPEBG@Z; IsVolumeRootPath(ushort const *)
0x180096f56  mov     rcx, [rsp+678h+pszPath]
0x180096f5b  test    eax, eax
0x180096f5d  jz      short loc_180096F64
0x180096f5f  mov     r14b, 1
0x180096f62  jmp     short loc_180096F82
0x180096f64  mov     r14b, r15b
0x180096f67  test    dil, dil
0x180096f6a  jz      short loc_180096F82
0x180096f6c  mov     [rcx+rbx*2-2], r15w
0x180096f72  dec     rbx
0x180096f75  mov     [rsp+678h+var_540], rbx
0x180096f7d  mov     rcx, [rsp+678h+pszPath]
0x180096f82  mov     [rsp+678h+hObject], rcx
0x180096f8a  mov     qword ptr [rsp+678h+var_5B8], 5E5h
0x180096f96  lea     r9, [rsp+678h+hObject]
0x180096f9e  lea     r8, [rsp+678h+var_5B8]
0x180096fa6  mov     edx, 1
0x180096fab  lea     rcx, [rsp+678h+var_448]
0x180096fb3  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x180096fb8  mov     eax, [rsp+678h+var_440]
0x180096fbf  mov     [rsp+678h+var_440], eax
0x180096fc6  mov     r15d, 104h
0x180096fcc  cmp     rbx, r15
0x180096fcf  jb      short loc_180096FDF
0x180096fd1  mov     rax, [rsp+678h+pszPath]
0x180096fd6  cmp     [rax], si
0x180096fd9  jnz     loc_180097F85
0x180096fdf  xor     edi, edi
0x180096fe1  mov     [rsp+678h+var_440], edi
0x180096fe8  mov     r8b, r13b
0x180096feb  xor     r8b, 1; bool
0x180096fef  lea     rcx, [rsp+678h+var_5E4]; this
0x180096ff7  call    ??0CSrmImpersonationSession@@QEAA@_N0@Z; CSrmImpersonationSession::CSrmImpersonationSession(bool,bool)
0x180096ffc  nop
0x180096ffd  mov     [rsp+678h+lpFileName], rdi
0x180097002  mov     [rsp+678h+var_608.lpSecurityDescriptor], rdi
0x180097007  mov     qword ptr [rsp+678h+var_608.nLength], rdi
0x18009700c  mov     [rsp+678h+pv], rdi
0x180097011  mov     [rsp+678h+var_618], dil
0x180097016  mov     rcx, [rsp+678h+pszPath]; unsigned __int16 *
0x18009701b  test    r13b, r13b
0x18009701e  jz      short loc_18009705A
0x180097020  lea     rax, [rsp+678h+pv]
0x180097025  mov     qword ptr [rsp+678h+dwFlagsAndAttributes], rax; struct CSrmAutoPWSZ *
0x18009702a  lea     rax, [rsp+678h+var_608]
0x18009702f  mov     qword ptr [rsp+678h+dwCreationDisposition], rax; struct CSrmAutoPWSZ *
0x180097034  lea     r9, [rsp+678h+var_608.lpSecurityDescriptor]; struct CSrmAutoPWSZ *
0x180097039  lea     r8, [rsp+678h+lpFileName]; this
0x18009703e  mov     rdx, qword ptr [rsp+678h+var_608.bInheritHandle]; unsigned __int16 *
0x180097046  call    ?GetRemoteNamespaceVolumePaths@CScanInformation@@SAXPEBG0AEAVCSrmAutoPWSZ@@111@Z; CScanInformation::GetRemoteNamespaceVolumePaths(ushort const *,ushort const *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &)
0x18009704b  bts     [rsp+678h+var_AC], 11h
0x180097054  lea     r13d, [rdi+10h]
0x180097058  jmp     short loc_180097088
0x18009705a  mov     r13d, 10h
0x180097060  test    byte ptr [rsp+678h+var_5E8], r13b
0x180097068  jz      short loc_180097092
0x18009706a  lea     rax, [rsp+678h+pv]
0x18009706f  mov     qword ptr [rsp+678h+dwCreationDisposition], rax; struct CSrmAutoPWSZ *
0x180097074  lea     r9, [rsp+678h+var_608]; struct CSrmAutoPWSZ *
0x180097079  lea     r8, [rsp+678h+var_608.lpSecurityDescriptor]; struct CSrmAutoPWSZ *
0x18009707e  lea     rdx, [rsp+678h+lpFileName]; this
0x180097083  call    ?GetNamespaceVolumePathsLight@CScanInformation@@SAXPEBGAEAVCSrmAutoPWSZ@@111@Z; CScanInformation::GetNamespaceVolumePathsLight(ushort const *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &)
0x180097088  mov     rbx, [rsp+678h+var_5F0]
0x180097090  jmp     short loc_1800970D6
0x180097092  mov     rbx, [rsp+678h+var_5F0]
0x18009709a  mov     rax, [rbx+10h]
0x18009709e  lea     rdx, [rax+8]
0x1800970a2  test    rax, rax
0x1800970a5  cmovz   rdx, r13; struct CSrmVssUtil *
0x1800970a9  lea     rax, [rsp+678h+var_618]
0x1800970ae  mov     [rsp+678h+hTemplateFile], rax; bool *
0x1800970b3  lea     rax, [rsp+678h+pv]
0x1800970b8  mov     qword ptr [rsp+678h+dwFlagsAndAttributes], rax; unsigned int
0x1800970bd  lea     rax, [rsp+678h+var_608]
0x1800970c2  mov     qword ptr [rsp+678h+dwCreationDisposition], rax; struct _SECURITY_ATTRIBUTES *
0x1800970c7  lea     r9, [rsp+678h+var_608.lpSecurityDescriptor]; struct CSrmAutoPWSZ *
0x1800970cc  lea     r8, [rsp+678h+lpFileName]; struct CSrmAutoPWSZ *
0x1800970d1  call    ?GetNamespaceVolumePaths@CScanInformation@@SAXPEBGPEAVCSrmVssUtil@@AEAVCSrmAutoPWSZ@@222AEA_N@Z; CScanInformation::GetNamespaceVolumePaths(ushort const *,CSrmVssUtil *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,bool &)
0x1800970d6  mov     [rsp+678h+var_5C0], edi
0x1800970dd  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x1800970e4  mov     [rsp+678h+var_5E0], rax
0x1800970ec  mov     [rsp+678h+var_5D8], 0FFFFFFFFFFFFFFFFh
0x1800970f8  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1800970ff  mov     [rsp+678h+var_5E0], rax
0x180097107  mov     edx, r12d
0x18009710a  bts     edx, 11h; unsigned int
0x18009710e  lea     rax, [rsp+678h+var_5C0]
0x180097116  mov     [rsp+678h+var_630], rax; unsigned int *
0x18009711b  mov     [rsp+678h+var_638], dil; bool
0x180097120  mov     dword ptr [rsp+678h+hTemplateFile], 2200000h; DWORD
0x180097128  mov     r9d, 7; unsigned int
0x18009712e  mov     r8d, r12d; unsigned int
0x180097131  mov     rcx, [rsp+678h+pszPath]; lpFileName
0x180097136  call    ?SrmCreateFileWithAlternateAccess@@YAPEAXPEBGKKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX_NPEAK@Z; SrmCreateFileWithAlternateAccess(ushort const *,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,bool,ulong *)
0x18009713b  mov     r12, rax
0x18009713e  mov     [rsp+678h+hObject], rax
0x180097146  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009714a  mov     [rsp+678h+var_5D8], r8
0x180097152  mov     [rsp+678h+var_5D8], rax
0x18009715a  cmp     rax, r8
0x18009715d  jz      loc_180097F61
0x180097163  or      edi, 0FFFFFFFFh
0x180097166  mov     [rsp+678h+var_5B8], edi
0x18009716d  xor     r9d, r9d
0x180097170  cmp     [rbx+8], r9b
0x180097174  jz      loc_1800972AB
0x18009717a  mov     rax, [rbx+10h]
0x18009717e  lea     rcx, [rax+0E0h]
0x180097185  mov     ebx, 0E8h
0x18009718a  test    rax, rax
0x18009718d  cmovz   rcx, rbx; this
0x180097191  mov     rdx, [rsp+678h+pv]; unsigned __int16 *
0x180097196  call    ?FindVolumeIndex@CNamespaceIndexCache@@QEAAKPEBG@Z; CNamespaceIndexCache::FindVolumeIndex(ushort const *)
0x18009719b  mov     [rsp+678h+var_5B8], eax
0x1800971a2  cmp     eax, edi
0x1800971a4  jnz     loc_1800972A2
0x1800971aa  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1800971b1  mov     [rsp+678h+var_5E0], rax
0x1800971b9  mov     rcx, r12; hObject
0x1800971bc  call    cs:__imp_CloseHandle
0x1800971c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800971c6  mov     [rsp+678h+var_5D8], rax
0x1800971ce  lea     rcx, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x1800971d5  mov     [rsp+678h+var_5E0], rcx
0x1800971dd  mov     [rsp+678h+var_5D8], rax
0x1800971e5  mov     rcx, [rsp+678h+pv]; pv
0x1800971ea  call    cs:__imp_CoTaskMemFree
0x1800971f0  xor     ebx, ebx
0x1800971f2  mov     [rsp+678h+pv], rbx
0x1800971f7  mov     [rsp+678h+pv], rbx
0x1800971fc  mov     rcx, qword ptr [rsp+678h+var_608.nLength]; pv
0x180097201  call    cs:__imp_CoTaskMemFree
0x180097207  mov     qword ptr [rsp+678h+var_608.nLength], rbx
0x18009720c  mov     qword ptr [rsp+678h+var_608.nLength], rbx
0x180097211  mov     rcx, [rsp+678h+var_608.lpSecurityDescriptor]; pv
0x180097216  call    cs:__imp_CoTaskMemFree
0x18009721c  mov     [rsp+678h+var_608.lpSecurityDescriptor], rbx
0x180097221  mov     [rsp+678h+var_608.lpSecurityDescriptor], rbx
0x180097226  mov     rcx, [rsp+678h+lpFileName]; pv
0x18009722b  call    cs:__imp_CoTaskMemFree
0x180097231  mov     [rsp+678h+lpFileName], rbx
0x180097236  mov     [rsp+678h+lpFileName], rbx
0x18009723b  lea     rcx, [rsp+678h+var_5E4]; this
0x180097243  call    ?RevertImpersonation@CSrmImpersonationSession@@QEAAJXZ; CSrmImpersonationSession::RevertImpersonation(void)
0x180097248  nop
0x180097249  mov     rcx, qword ptr [rsp+678h+var_608.bInheritHandle]; pv
0x180097251  call    cs:__imp_CoTaskMemFree
0x180097257  mov     qword ptr [rsp+678h+var_608.bInheritHandle], rbx
0x18009725f  mov     qword ptr [rsp+678h+var_608.bInheritHandle], rbx
0x180097267  mov     rcx, [rsp+678h+pszPath]; pv
0x18009726c  call    cs:__imp_CoTaskMemFree
0x180097272  mov     [rsp+678h+pszPath], rbx
0x180097277  mov     [rsp+678h+pszPath], rbx
0x18009727c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180097283  mov     [rsp+678h+var_448], rax
0x18009728b  lea     rcx, [rsp+678h+var_448]; this
0x180097293  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180097298  mov     eax, 8004537Fh
0x18009729d  jmp     loc_180097F3E
0x1800972a2  xor     r9d, r9d
0x1800972a5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800972a9  jmp     short loc_1800972B0
0x1800972ab  mov     ebx, 0E8h
0x1800972b0  mov     [rsp+678h+var_380], 7
0x1800972bc  mov     [rsp+678h+var_388], r9
0x1800972c4  mov     word ptr [rsp+678h+Block], r9w
0x1800972cd  mov     rax, [rsp+678h+var_608.lpSecurityDescriptor]
0x1800972d2  mov     rcx, r8
0x1800972d5  inc     rcx
0x1800972d8  cmp     [rax+rcx*2], r9w
0x1800972dd  jnz     short loc_1800972D5
0x1800972df  lea     rax, [rcx-1]
0x1800972e3  cmp     rax, rcx
0x1800972e6  ja      short loc_1800972F7
0x1800972e8  mov     rdx, [rsp+678h+lpFileName]
0x1800972ed  add     rdx, 0FFFFFFFFFFFFFFFEh
0x1800972f1  lea     rdx, [rdx+rcx*2]
0x1800972f5  jmp     short loc_180097300
0x1800972f7  mov     rax, [rsp+678h+lpFileName]
0x1800972fc  lea     rdx, [rax+rcx*2]; Src
0x180097300  inc     r8
0x180097303  cmp     [rdx+r8*2], r9w
0x180097308  jnz     short loc_180097300
0x18009730a  lea     rcx, [rsp+678h+Block]; void *
0x180097312  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180097317  lea     rcx, [rsp+678h+Block]; void *
0x18009731f  call    ?NormalizeRelativePath@CVolumePathInfo@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CVolumePathInfo::NormalizeRelativePath(std::wstring &)
0x180097324  xorps   xmm0, xmm0
  ... truncated ...
```
