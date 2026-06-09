# CVsSoftwareProvider::GetVolumeInformationFlags(ushort const *,long,CVssAutoString<CVssAutoCOMPtr<ushort *>> *,int,long)

- ea: `0x180011178`
- end: `0x18001224b`
- name: `?GetVolumeInformationFlags@CVsSoftwareProvider@@SAJPEBGJPEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@HJ@Z`
- size: `4307`
- prototype: `__int64 __fastcall(const WCHAR *, int, __int64, int, char)`
- caller_count: `13`
- callee_count: `27`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e900`
- `0x1800122a0`
- `0x180012740`
- `0x18001fb80`
- `0x1800200c0`
- `0x180020c6c`
- `0x180021bc4`
- `0x1800250bc`
- `0x180026da0`
- `0x18002a280`
- `0x18002c080`
- `0x18002c830`
- `0x18002d1f0`

## callees

- `0x180001580`
- `0x1800016c0`
- `0x18000212c`
- `0x180002f1c`
- `0x180003718`
- `0x1800039d8`
- `0x180003de8`
- `0x1800049e0`
- `0x18000610c`
- `0x180007604`
- `0x18000dc10`
- `0x18000dc40`
- `0x180011178`
- `0x180015864`
- `0x180016ff0`
- `0x180031914`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x180034038`
- `0x1800358f4`
- `0x180035f44`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x1800377c4`
- `0x180039394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001194a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001194a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011592`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d14`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180011c43`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180011c43`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800112b4`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800112b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011447`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011447`
- `ntdll!NtQueryVolumeInformationFile` at `0x180011644`
- `ntdll!NtQueryVolumeInformationFile` at `0x180011644`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800116d6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800116d6`

## string_xrefs

- `0x18001155b`: `Error calling CreateFile on volume '%s'`
- `0x180011891`: `Volume not found: NtQueryVolumeInformationFile on volume '%s' returns ERROR_NOT_READY or ERROR_DEVICE_NOT_CONNECTED, NTSTATUS 0x%08lx, NTSUCCESS %d, winerror 0x%08lx`
- `0x1800118da`: `Volume not found: NtQueryVolumeInformationFile on volume '%s' returns ERROR_NOT_READY or ERROR_DEVICE_NOT_CONNECTED, NTSTATUS 0x%08lx, NTSUCCESS %d, winerror 0x%08lx`
- `0x180011aa5`: `Volume (%s) is read-only, not supported`
- `0x180012128`: `Error reading encryption status on volume %s`
- `0x18001216d`: `Error reading encryption status on volume %s (0x%08lx)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVsSoftwareProvider::GetVolumeInformationFlags(const WCHAR *a1, int a2, __int64 a3, int a4, char a5)
{
  unsigned int v6; // esi
  DWORD v7; // eax
  unsigned __int16 *v8; // rbx
  __int64 v10; // rax
  void *v11; // r11
  void *v12; // rax
  unsigned __int64 v13; // rax
  CVssDebugInfo *v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbx
  signed int v17; // eax
  signed int v18; // ebx
  int v19; // r15d
  __int64 LowPart; // r9
  unsigned __int16 *v21; // rax
  int v22; // ecx
  int v23; // edx
  unsigned __int16 *v24; // rax
  int v25; // ecx
  int v26; // edx
  unsigned __int16 *v27; // rax
  int v28; // ecx
  int v29; // edx
  union _ULARGE_INTEGER v30; // rdi
  union _ULARGE_INTEGER v31; // rbx
  CVssDebugInfo *v32; // rax
  int v33; // ebx
  unsigned int v34; // r15d
  __int64 v35; // rdi
  unsigned __int16 **Ref; // rax
  __int64 v37; // rbx
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-758h]
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-758h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-758h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-750h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-748h]
  int Status; // [rsp+50h] [rbp-728h]
  NTSTATUS Statusa; // [rsp+50h] [rbp-728h]
  char v45[4]; // [rsp+54h] [rbp-724h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-720h]
  LPCWSTR lpRootPathName; // [rsp+60h] [rbp-718h]
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+68h] [rbp-710h] BYREF
  const unsigned __int16 *v49; // [rsp+70h] [rbp-708h] BYREF
  const unsigned __int16 *v50; // [rsp+78h] [rbp-700h]
  const unsigned __int16 *v51; // [rsp+80h] [rbp-6F8h]
  int v52; // [rsp+88h] [rbp-6F0h]
  int v53; // [rsp+8Ch] [rbp-6ECh]
  int v54; // [rsp+90h] [rbp-6E8h]
  _BYTE v55[120]; // [rsp+98h] [rbp-6E0h] BYREF
  int v56; // [rsp+110h] [rbp-668h]
  __int64 v57; // [rsp+118h] [rbp-660h]
  void **v58; // [rsp+120h] [rbp-658h] BYREF
  __int64 v59; // [rsp+128h] [rbp-650h]
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+130h] [rbp-648h] BYREF
  unsigned __int16 *v61; // [rsp+138h] [rbp-640h] BYREF
  LPVOID v62; // [rsp+140h] [rbp-638h] BYREF
  int v63; // [rsp+148h] [rbp-630h]
  unsigned int v64; // [rsp+164h] [rbp-614h]
  _QWORD v65[2]; // [rsp+1B0h] [rbp-5C8h] BYREF
  int v66; // [rsp+1C0h] [rbp-5B8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+1C8h] [rbp-5B0h] BYREF
  __int64 v68; // [rsp+1D0h] [rbp-5A8h] BYREF
  __int128 v69; // [rsp+1D8h] [rbp-5A0h]
  __int128 v70; // [rsp+1E8h] [rbp-590h]
  __int16 v71; // [rsp+1F8h] [rbp-580h]
  __int64 v72; // [rsp+1FCh] [rbp-57Ch]
  __int64 v73; // [rsp+208h] [rbp-570h]
  __int64 v74; // [rsp+210h] [rbp-568h]
  int v75; // [rsp+218h] [rbp-560h]
  __int64 v76; // [rsp+220h] [rbp-558h]
  __int16 v77; // [rsp+228h] [rbp-550h]
  void **v78; // [rsp+230h] [rbp-548h]
  __int64 v79; // [rsp+238h] [rbp-540h]
  _com_error *v80; // [rsp+240h] [rbp-538h] BYREF
  const std::exception *v81; // [rsp+248h] [rbp-530h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+250h] [rbp-528h] BYREF
  _BYTE v83[176]; // [rsp+260h] [rbp-518h] BYREF
  WCHAR FileName[264]; // [rsp+310h] [rbp-468h] BYREF
  unsigned __int16 v85[264]; // [rsp+520h] [rbp-258h] BYREF

  v57 = a3;
  lpRootPathName = a1;
  v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
  v51 = L"SPRPROVC";
  v52 = 2279;
  v53 = 2;
  v54 = 255;
  v6 = 0;
  v56 = 0x1000000;
  memset_0(v55, 0, sizeof(v55));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v62, (__int64)&v49, 0);
  v68 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v79 = 0;
  v78 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v69 = 0;
  v70 = 0;
  v7 = a2 & 0xFF3FFFFF;
  if ( a2 == -1 )
    v7 = -1;
  TotalNumberOfBytes.LowPart = v7;
  v8 = (unsigned __int16 *)lpRootPathName;
  LODWORD(FileHandle) = GetDriveTypeW(lpRootPathName);
  if ( (_DWORD)FileHandle != 3 )
  {
    v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
    v51 = L"SPRPROVC";
    v52 = 2293;
    v53 = 2;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    CVssFunctionTracer::Trace(
      &v62,
      &v49,
      L"Warning: Ignoring the non-fixed volume (%s) - %ud",
      lpRootPathName,
      (_DWORD)FileHandle);
LABEL_5:
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v68);
    CVssFunctionTracer::~CVssFunctionTracer(&v62);
    return 0;
  }
  IoStatusBlock = 0;
  memset_0(v85, 0, 0x20Au);
  memset_0(FileName, 0, 0x20Au);
  if ( !lpRootPathName )
    goto LABEL_89;
  v10 = -1;
  do
    ++v10;
  while ( lpRootPathName[v10] );
  if ( !v10 )
  {
LABEL_89:
    if ( a4 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2315;
      v53 = 11;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::Throw(&v62, &v49, 2147942487LL, L"Bad parameter to GetVolumeInformationFlags.");
    }
    goto LABEL_5;
  }
  StringCchCopyW(FileName, 0x105u, lpRootPathName);
  v12 = v11;
  do
    v12 = (char *)v12 + 1;
  while ( FileName[(_QWORD)v12] );
  if ( *(_WORD *)&v83[2 * (_QWORD)v12 + 174] == 92 )
  {
    v13 = 2LL * (_QWORD)v12 - 2;
    if ( v13 >= 0x20A )
      _report_rangecheckfailure(FileName);
    *(WCHAR *)((char *)FileName + v13) = 0;
  }
  FileHandle = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x80u, v11);
  v65[0] = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v65[1] = FileHandle;
  if ( FileHandle == (HANDLE)-1LL )
  {
    if ( GetLastError() == 5 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2336;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      v14 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v49, (CVssDebugInfo *)v83, v8);
      CVssFunctionTracer::LogError(&v62, 12348, v14);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v49);
    }
    if ( a4 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2339;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::TranslateWin32Error(&v62, &v49, L"Error calling CreateFile on volume '%s'", v8);
    }
LABEL_21:
    CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v65);
    goto LABEL_5;
  }
  v15 = (unsigned __int16 *)malloc(0x21Au);
  v16 = v15;
  v61 = v15;
  if ( !v15 )
  {
    v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
    v51 = L"SPRPROVC";
    v52 = 2351;
    v53 = 11;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    CVssFunctionTracer::Throw(&v62, &v49, 2147942414LL, L"Out of memory to check volume filesystem.");
  }
  memset_0(v15, 0, 0x21Au);
  Status = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, v16, 0x21Au, FileFsAttributeInformation);
  LODWORD(FileHandle) = Status >= 0;
  v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
  v51 = L"SPRPROVC";
  v52 = 2362;
  v53 = 2;
  v54 = 255;
  v56 = 0x1000000;
  memset_0(v55, 0, sizeof(v55));
  dwCreationDispositionb[0] = (unsigned int)FileHandle;
  CVssFunctionTracer::Trace(
    &v62,
    &v49,
    L"NtQueryVolumeInformationFile: NTSTATUS: 0x%08lx NTSUCCESS: %d",
    (unsigned int)Status,
    *(_QWORD *)dwCreationDispositionb);
  if ( Status < 0 )
  {
    v17 = RtlNtStatusToDosErrorNoTeb(Status);
    v18 = v17;
    if ( v17 == 21 || v17 == 1167 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      if ( a4 )
      {
        v52 = 2370;
        memset_0(v55, 0, sizeof(v55));
        LODWORD(hTemplateFile) = (_DWORD)FileHandle;
        dwFlagsAndAttributes[0] = Status;
        CVssFunctionTracer::Throw(
          &v62,
          &v49,
          2147754760LL,
          L"Volume not found: NtQueryVolumeInformationFile on volume '%s' returns ERROR_NOT_READY or ERROR_DEVICE_NOT_CONN"
           "ECTED, NTSTATUS 0x%08lx, NTSUCCESS %d, winerror 0x%08lx",
          lpRootPathName,
          *(_QWORD *)dwFlagsAndAttributes,
          hTemplateFile,
          v18);
      }
      v52 = 2375;
      memset_0(v55, 0, sizeof(v55));
      LODWORD(hTemplateFile) = v18;
      dwFlagsAndAttributes[0] = (unsigned int)FileHandle;
      dwCreationDisposition[0] = Status;
      CVssFunctionTracer::Trace(
        &v62,
        &v49,
        L"Volume not found: NtQueryVolumeInformationFile on volume '%s' returns ERROR_NOT_READY or ERROR_DEVICE_NOT_CONNEC"
         "TED, NTSTATUS 0x%08lx, NTSUCCESS %d, winerror 0x%08lx",
        lpRootPathName,
        *(_QWORD *)dwCreationDisposition,
        *(_QWORD *)dwFlagsAndAttributes,
        hTemplateFile);
      CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>::~CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>(&v61);
      goto LABEL_21;
    }
    if ( a4 )
    {
      if ( v17 > 0 )
        TotalNumberOfBytes.LowPart = (unsigned __int16)v17 | 0x80070000;
      else
        TotalNumberOfBytes.LowPart = v17;
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2386;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      LODWORD(hTemplateFile) = (_DWORD)FileHandle;
      dwFlagsAndAttributes[0] = Status;
      CVssFunctionTracer::TranslateGenericError(
        &v62,
        &v49,
        TotalNumberOfBytes.LowPart,
        L"NtQueryVolumeInformationFile failed for volume %s, NTSTATUS 0x%08lx, NTSUCCESS %d, winerror 0x%08lx",
        lpRootPathName,
        *(_QWORD *)dwFlagsAndAttributes,
        hTemplateFile,
        v18);
    }
    v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
    v51 = L"SPRPROVC";
    v52 = 2391;
    v53 = 2;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    LODWORD(hTemplateFile) = v18;
    dwFlagsAndAttributes[0] = (unsigned int)FileHandle;
    dwCreationDisposition[0] = Status;
    CVssFunctionTracer::LogGenericWarning(
      &v62,
      &v49,
      L"NtQueryVolumeInformationFile failed for volume %s, NTSTATUS 0x%08lx, NTSUCCESS %d, winerror 0x%08lx",
      lpRootPathName,
      *(_QWORD *)dwCreationDisposition,
      *(_QWORD *)dwFlagsAndAttributes,
      hTemplateFile);
    goto LABEL_61;
  }
  v19 = 0;
  LODWORD(FileHandle) = *(_DWORD *)v16;
  if ( (unsigned int)(*((_DWORD *)v16 + 2) - 1) <= 0x103 )
    StringCchCopyW(v85, 0x105u, v16 + 6);
  if ( (unsigned int)_o__wcsnicmp(v85, L"RAW", 3) )
  {
    LowPart = TotalNumberOfBytes.LowPart;
  }
  else
  {
    v19 = 8;
    v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
    v51 = L"SPRPROVC";
    v52 = 2407;
    v53 = 2;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    CVssFunctionTracer::Trace(&v62, &v49, L"Encountered a RAW volume (%s)", lpRootPathName);
    LowPart = TotalNumberOfBytes.LowPart;
    if ( TotalNumberOfBytes.LowPart != -1 && (TotalNumberOfBytes.LowPart & 5) != 0 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2412;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::Trace(&v62, &v49, L"RAW volumes not supported for timewarp nor persistent snapshots");
LABEL_60:
      v6 = v19;
LABEL_61:
      CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>::~CVssMallocAutoPtr<_FILE_FS_ATTRIBUTE_INFORMATION>(&v61);
      CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v65);
      CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v68);
      CVssFunctionTracer::~CVssFunctionTracer(&v62);
      return v6;
    }
  }
  if ( ((unsigned int)FileHandle & 0x80000) != 0 )
  {
    v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
    v51 = L"SPRPROVC";
    v52 = 2419;
    v53 = 2;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    CVssFunctionTracer::Trace(&v62, &v49, L"Volume (%s) is read-only, not supported", lpRootPathName);
    goto LABEL_60;
  }
  v21 = v85;
  do
  {
    v22 = *(unsigned __int16 *)((char *)v21 + (char *)L"NTFS" - (char *)v85);
    v23 = *v21 - v22;
    if ( v23 )
      break;
    ++v21;
  }
  while ( v22 );
  if ( !v23 )
    goto LABEL_62;
  v24 = v85;
  do
  {
    v25 = *(unsigned __int16 *)((char *)v24 + (char *)L"ReFS" - (char *)v85);
    v26 = *v24 - v25;
    if ( v26 )
      break;
    ++v24;
  }
  while ( v25 );
  if ( !v26 )
    goto LABEL_62;
  v27 = v85;
  do
  {
    v28 = *(unsigned __int16 *)((char *)v27 + (char *)L"CSVFS" - (char *)v85);
    v29 = *v27 - v28;
    if ( v29 )
      break;
    ++v27;
  }
  while ( v28 );
  if ( v29 )
  {
    if ( (_DWORD)LowPart != -1 && (LowPart & 5) != 0 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2470;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::Trace(
        &v62,
        &v49,
        L"Encountered a %s volume (%s) - Not supported for timewarp nor persistent snapshots",
        lpRootPathName,
        v85);
      goto LABEL_60;
    }
  }
  else
  {
LABEL_62:
    FreeBytesAvailableToCaller.QuadPart = 0;
    TotalNumberOfFreeBytes.QuadPart = 0;
    TotalNumberOfBytes.QuadPart = 0;
    if ( GetDiskFreeSpaceExW(lpRootPathName, &FreeBytesAvailableToCaller, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
    {
      v30.QuadPart = CVssMachineInformation::GetMinDiffAreaOnVolume(lpRootPathName);
      v31 = TotalNumberOfBytes;
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2444;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::Trace(
        &v62,
        &v49,
        L"volume %s: freespace=%I64d minDiffArea=%I64d",
        lpRootPathName,
        v31.QuadPart,
        v30.QuadPart);
      if ( TotalNumberOfBytes.QuadPart >= v30.QuadPart && TotalNumberOfBytes.QuadPart < 0x400000000000LL )
        v19 |= 2u;
    }
    else
    {
      LODWORD(FileHandle) = GetLastError();
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2455;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      dwCreationDisposition[0] = (unsigned int)FileHandle;
      CVssFunctionTracer::Trace(
        &v62,
        &v49,
        L"Cannot get the free space for volume (%s) - [0x%08lx]",
        lpRootPathName,
        *(_QWORD *)dwCreationDisposition);
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      if ( (_DWORD)FileHandle == -1073741790 )
      {
        v52 = 2459;
        memset_0(v55, 0, sizeof(v55));
        v32 = CVssDebugInfo::operator<<(
                (struct CVssDebugInfo *)&v49,
                (CVssDebugInfo *)v83,
                (unsigned __int16 *)lpRootPathName);
        CVssFunctionTracer::LogError(&v62, 12348, v32);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v49);
      }
      else
      {
        v52 = 2461;
        memset_0(v55, 0, sizeof(v55));
        dwCreationDisposition[0] = (unsigned int)FileHandle;
        CVssFunctionTracer::LogGenericWarning(
          &v62,
          &v49,
          L"GetDiskFreeSpaceEx() for %s failed with 0x%08lx",
          lpRootPathName,
          *(_QWORD *)dwCreationDisposition);
      }
    }
  }
  try
  {
    LOBYTE(dwCreationDisposition[0]) = 1;
    LOBYTE(LowPart) = 1;
    CVssIOCTLChannel::Open(&v68, &v62, lpRootPathName, LowPart, dwCreationDisposition[0], 2, 0);
    v33 = CVssIOCTLChannel::Call(&v68, (__int64)&v62, 0x530018u, 1, 0, 0);
    v63 = v33;
    if ( v33 < 0 )
    {
      v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
      v51 = L"SPRPROVC";
      v52 = 2484;
      v53 = 2;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      dwCreationDispositiona[0] = v33;
      CVssFunctionTracer::Throw(
        &v62,
        &v49,
        0,
        L"Volume is not supported by volsnap driver. Call returned 0x%08lx",
        *(_QWORD *)dwCreationDispositiona);
    }
    v34 = v19 | 1;
    Statusa = v34;
    TotalNumberOfBytes.LowPart = 0;
    CVssIOCTLChannel::Unpack<unsigned long>(
      (CVssIOCTLChannel *)&v68,
      (struct CVssFunctionTracer *)&v62,
      &TotalNumberOfBytes);
    if ( TotalNumberOfBytes.LowPart != 2 )
    {
      v34 |= 4u;
      Statusa = v34;
      v35 = v57;
      if ( v57 )
      {
        v59 = 0;
        v58 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
        while ( 1 )
        {
          Ref = (unsigned __int16 **)CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(&v58);
          if ( !CVssIOCTLChannel::UnpackZeroString((CVssIOCTLChannel *)&v68, (struct CVssFunctionTracer *)&v62, Ref) )
            break;
          v37 = v59;
          v59 = 0;
          CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(v35);
          *(_QWORD *)(v35 + 8) = v37;
        }
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v58);
      }
    }
  }
  catch ( long v66 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v62,
      v66,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::GetVolumeInformationFlags",
      0x9D0u,
      v64);
    v34 = Statusa;
  }
  catch ( _com_error *v80 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v62,
      v80,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::GetVolumeInformationFlags",
      0x9D0u,
      v64);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v62,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::GetVolumeInformationFlags",
      0x9D0u,
      v64);
    v34 = Statusa;
  }
  catch ( const std::exception *v81 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v62,
      v81,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::GetVolumeInformationFlags",
      0x9D0u,
      v64);
  }
  LOBYTE(dwCreationDisposition[0]) = 1;
  LOBYTE(LowPart) = 1;
  CVssIOCTLChannel::Open(&v68, &v62, lpRootPathName, LowPart, dwCreationDisposition[0], 2, 0);
  v33 = CVssIOCTLChannel::Call(&v68, (__int64)&v62, 0x530018u, 1, 0, 0);
  v63 = v33;
  if ( v33 < 0 )
  {
    v49 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = L"CVsSoftwareProvider::GetVolumeInformationFlags";
    v51 = L"SPRPROVC";
    v52 = 2484;
    v53 = 2;
    v54 = 255;
    v56 = 0x1000000;
    memset_0(v55, 0, sizeof(v55));
    dwCreationDispositiona[0] = v33;
    CVssFunctionTracer::Throw(
      &v62,
      &v49,
      0,
      L"Volume is not supported by volsnap driver. Call returned 0x%08lx",
      *(_QWORD *)dwCreationDispositiona);
  }
  v34 = v19 | 1;
}

```

## disassembly

```asm
0x180011178  mov     r11, rsp
0x18001117b  mov     [r11+20h], r9d
0x18001117f  push    rbx
0x180011180  push    rsi
0x180011181  push    rdi
0x180011182  push    r12
0x180011184  push    r13
0x180011186  push    r14
0x180011188  push    r15
0x18001118a  sub     rsp, 740h
0x180011191  mov     rax, cs:__security_cookie
0x180011198  xor     rax, rsp
0x18001119b  mov     [rsp+778h+var_48], rax
0x1800111a3  mov     [rsp+778h+var_660], r8
0x1800111ab  mov     ebx, edx
0x1800111ad  mov     [rsp+778h+lpRootPathName], rcx
0x1800111b2  lea     r12, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800111b9  mov     [rsp+778h+var_708], r12
0x1800111be  lea     r13, aCvssoftwarepro_2; "CVsSoftwareProvider::GetVolumeInformati"...
0x1800111c5  mov     [rsp+778h+var_700], r13
0x1800111ca  lea     rdi, aSprprovc; "SPRPROVC"
0x1800111d1  mov     [r11-6F8h], rdi
0x1800111d8  mov     [rsp+778h+var_6F0], 8E7h
0x1800111e3  mov     r14d, 2
0x1800111e9  mov     [r11-6ECh], r14d
0x1800111f0  mov     r15d, 0FFh
0x1800111f6  mov     [r11-6E8h], r15d
0x1800111fd  xor     esi, esi
0x1800111ff  mov     [rsp+778h+var_668], 1000000h
0x18001120a  xor     edx, edx; Val
0x18001120c  lea     r8d, [r14+76h]; Size
0x180011210  lea     rcx, [r11-6E0h]; void *
0x180011217  call    memset_0
0x18001121c  xor     r8d, r8d
0x18001121f  lea     rdx, [rsp+778h+var_708]
0x180011224  lea     rcx, [rsp+778h+var_638]
0x18001122c  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180011231  nop
0x180011232  mov     [rsp+778h+var_5A8], rsi
0x18001123a  mov     [rsp+778h+var_580], si
0x180011242  mov     [rsp+778h+var_57C], rsi
0x18001124a  mov     [rsp+778h+var_570], rsi
0x180011252  mov     [rsp+778h+var_568], rsi
0x18001125a  mov     [rsp+778h+var_560], esi
0x180011261  mov     [rsp+778h+var_558], rsi
0x180011269  mov     [rsp+778h+var_550], si
0x180011271  mov     [rsp+778h+var_540], rsi
0x180011279  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180011280  mov     [rsp+778h+var_548], rax
0x180011288  xorps   xmm0, xmm0
0x18001128b  movups  [rsp+778h+var_5A0], xmm0
0x180011293  movups  [rsp+778h+var_590], xmm0
0x18001129b  mov     eax, ebx
0x18001129d  and     eax, 0FF3FFFFFh
0x1800112a2  cmp     ebx, 0FFFFFFFFh
0x1800112a5  cmovz   eax, ebx
0x1800112a8  mov     dword ptr [rsp+778h+TotalNumberOfBytes], eax
0x1800112ac  mov     rbx, [rsp+778h+lpRootPathName]
0x1800112b1  mov     rcx, rbx; lpRootPathName
0x1800112b4  call    cs:__imp_GetDriveTypeW
0x1800112ba  mov     dword ptr [rsp+778h+FileHandle], eax
0x1800112be  cmp     eax, 3
0x1800112c1  jz      loc_180011377
0x1800112c7  mov     [rsp+778h+var_708], r12
0x1800112cc  mov     [rsp+778h+var_700], r13
0x1800112d1  mov     [rsp+778h+var_6F8], rdi
0x1800112d9  mov     [rsp+778h+var_6F0], 8F5h
0x1800112e4  mov     [rsp+778h+var_6EC], r14d
0x1800112ec  mov     [rsp+778h+var_6E8], r15d
0x1800112f4  mov     [rsp+778h+var_668], 1000000h
0x1800112ff  xor     edx, edx; Val
0x180011301  lea     r8d, [r14+76h]; Size
0x180011305  lea     rcx, [rsp+778h+var_6E0]; void *
0x18001130d  call    memset_0
0x180011312  mov     eax, dword ptr [rsp+778h+FileHandle]
0x180011316  mov     [rsp+778h+dwCreationDisposition], eax
0x18001131a  mov     r9, rbx
0x18001131d  lea     r8, aWarningIgnorin; "Warning: Ignoring the non-fixed volume "...
0x180011324  lea     rdx, [rsp+778h+var_708]
0x180011329  lea     rcx, [rsp+778h+var_638]
0x180011331  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180011336  nop
0x180011337  lea     rcx, [rsp+778h+var_5A8]; this
0x18001133f  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x180011344  nop
0x180011345  lea     rcx, [rsp+778h+var_638]; this
0x18001134d  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180011352  xor     eax, eax
0x180011354  mov     rcx, [rsp+778h+var_48]
0x18001135c  xor     rcx, rsp; StackCookie
0x18001135f  call    __security_check_cookie
0x180011364  add     rsp, 740h
0x18001136b  pop     r15
0x18001136d  pop     r14
0x18001136f  pop     r13
0x180011371  pop     r12
0x180011373  pop     rdi
0x180011374  pop     rsi
0x180011375  pop     rbx
0x180011376  retn
0x180011377  xorps   xmm0, xmm0
0x18001137a  movups  xmmword ptr [rsp+778h+IoStatusBlock], xmm0
0x180011382  xor     edx, edx; Val
0x180011384  mov     r8d, 20Ah; Size
0x18001138a  lea     rcx, [rsp+778h+var_258]; void *
0x180011392  call    memset_0
0x180011397  xor     edx, edx; Val
0x180011399  mov     r8d, 20Ah; Size
0x18001139f  lea     rcx, [rsp+778h+FileName]; void *
0x1800113a7  call    memset_0
0x1800113ac  test    rbx, rbx
0x1800113af  jz      loc_1800121D0
0x1800113b5  or      r11, 0FFFFFFFFFFFFFFFFh
0x1800113b9  mov     rax, r11
0x1800113bc  inc     rax
0x1800113bf  cmp     [rbx+rax*2], si
0x1800113c3  jnz     short loc_1800113BC
0x1800113c5  test    rax, rax
0x1800113c8  jz      loc_1800121D0
0x1800113ce  mov     r8, rbx; unsigned __int16 *
0x1800113d1  mov     edx, 105h; unsigned __int64
0x1800113d6  lea     rcx, [rsp+778h+FileName]; unsigned __int16 *
0x1800113de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800113e3  lea     rcx, [rsp+778h+FileName]
0x1800113eb  mov     rax, r11
0x1800113ee  inc     rax
0x1800113f1  cmp     [rcx+rax*2], si
0x1800113f5  jnz     short loc_1800113EE
0x1800113f7  cmp     [rsp+rax*2+778h+var_46A], 5Ch ; '\'
0x180011400  jnz     short loc_18001141E
0x180011402  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001140a  cmp     rax, 20Ah
0x180011410  jnb     loc_180011575
0x180011416  mov     [rsp+rax+778h+FileName], si
0x18001141e  mov     [rsp+778h+hTemplateFile], r11; hTemplateFile
0x180011423  mov     [rsp+778h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001142b  mov     [rsp+778h+dwCreationDisposition], 3; dwCreationDisposition
0x180011433  xor     r9d, r9d; lpSecurityAttributes
0x180011436  mov     edx, 80000000h; dwDesiredAccess
0x18001143b  lea     r8d, [r9+3]; dwShareMode
0x18001143f  lea     rcx, [rsp+778h+FileName]; lpFileName
0x180011447  call    cs:__imp_CreateFileW
0x18001144d  mov     [rsp+778h+FileHandle], rax
0x180011452  lea     rcx, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x180011459  mov     [rsp+778h+var_5C8], rcx
0x180011461  mov     [rsp+778h+var_5C0], rax
0x180011469  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001146d  jnz     loc_18001158D
0x180011473  call    cs:__imp_GetLastError
0x180011479  cmp     eax, 5
0x18001147c  jnz     loc_180011504
0x180011482  mov     [rsp+778h+var_708], r12
0x180011487  mov     [rsp+778h+var_700], r13
0x18001148c  mov     [rsp+778h+var_6F8], rdi
0x180011494  mov     [rsp+778h+var_6F0], 920h
0x18001149f  mov     [rsp+778h+var_6EC], r14d
0x1800114a7  mov     [rsp+778h+var_6E8], r15d
0x1800114af  mov     [rsp+778h+var_668], 1000000h
0x1800114ba  xor     edx, edx; Val
0x1800114bc  lea     r8d, [rax+73h]; Size
0x1800114c0  lea     rcx, [rsp+778h+var_6E0]; void *
0x1800114c8  call    memset_0
0x1800114cd  mov     r8, rbx; unsigned __int16 *
0x1800114d0  lea     rdx, [rsp+778h+var_518]; this
0x1800114d8  lea     rcx, [rsp+778h+var_708]; struct CVssDebugInfo *
0x1800114dd  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x1800114e2  mov     r9d, r14d
0x1800114e5  mov     r8, rax
0x1800114e8  mov     edx, 303Ch
0x1800114ed  lea     rcx, [rsp+778h+var_638]
0x1800114f5  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x1800114fa  lea     rcx, [rsp+778h+var_708]; this
0x1800114ff  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180011504  cmp     [rsp+778h+arg_18], esi
0x18001150b  jz      short loc_18001157B
0x18001150d  mov     [rsp+778h+var_708], r12
0x180011512  mov     [rsp+778h+var_700], r13
0x180011517  mov     [rsp+778h+var_6F8], rdi
0x18001151f  mov     [rsp+778h+var_6F0], 923h
0x18001152a  mov     [rsp+778h+var_6EC], r14d
0x180011532  mov     [rsp+778h+var_6E8], r15d
0x18001153a  mov     [rsp+778h+var_668], 1000000h
0x180011545  xor     edx, edx; Val
0x180011547  lea     r8d, [rdx+78h]; Size
0x18001154b  lea     rcx, [rsp+778h+var_6E0]; void *
0x180011553  call    memset_0
0x180011558  mov     r9, rbx
0x18001155b  lea     r8, aErrorCallingCr; "Error calling CreateFile on volume '%s'"
0x180011562  lea     rdx, [rsp+778h+var_708]
0x180011567  lea     rcx, [rsp+778h+var_638]
0x18001156f  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x180011575  call    __report_rangecheckfailure
0x18001157b  lea     rcx, [rsp+778h+var_5C8]
0x180011583  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x180011588  jmp     loc_180011337
0x18001158d  mov     ecx, 21Ah; Size
0x180011592  call    cs:__imp_malloc
0x180011598  mov     rbx, rax
0x18001159b  mov     [rsp+778h+var_640], rax
0x1800115a3  test    rax, rax
0x1800115a6  jnz     short loc_180011616
0x1800115a8  mov     [rsp+778h+var_708], r12
0x1800115ad  mov     [rsp+778h+var_700], r13
0x1800115b2  mov     [rsp+778h+var_6F8], rdi
0x1800115ba  mov     [rsp+778h+var_6F0], 92Fh
0x1800115c5  mov     [rsp+778h+var_6EC], 0Bh
0x1800115d0  mov     [rsp+778h+var_6E8], r15d
0x1800115d8  mov     [rsp+778h+var_668], 1000000h
0x1800115e3  xor     edx, edx; Val
0x1800115e5  lea     r8d, [rax+78h]; Size
0x1800115e9  lea     rcx, [rsp+778h+var_6E0]; void *
0x1800115f1  call    memset_0
0x1800115f6  lea     r9, aOutOfMemoryToC; "Out of memory to check volume filesyste"...
0x1800115fd  mov     r8d, 8007000Eh
0x180011603  lea     rdx, [rsp+778h+var_708]
0x180011608  lea     rcx, [rsp+778h+var_638]
0x180011610  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180011616  xor     edx, edx; Val
0x180011618  mov     r8d, 21Ah; Size
0x18001161e  mov     rcx, rbx; void *
0x180011621  call    memset_0
0x180011626  mov     [rsp+778h+dwCreationDisposition], 5; FsInformationClass
0x18001162e  mov     r9d, 21Ah; Length
0x180011634  mov     r8, rbx; FsInformation
0x180011637  lea     rdx, [rsp+778h+IoStatusBlock]; IoStatusBlock
0x18001163f  mov     rcx, [rsp+778h+FileHandle]; FileHandle
0x180011644  call    cs:__imp_NtQueryVolumeInformationFile
0x18001164a  mov     [rsp+778h+Status], eax
0x18001164e  not     eax
0x180011650  shr     eax, 1Fh
0x180011653  mov     dword ptr [rsp+778h+FileHandle], eax
0x180011657  mov     [rsp+778h+var_708], r12
0x18001165c  mov     [rsp+778h+var_700], r13
0x180011661  mov     [rsp+778h+var_6F8], rdi
0x180011669  mov     [rsp+778h+var_6F0], 93Ah
0x180011674  mov     [rsp+778h+var_6EC], r14d
0x18001167c  mov     [rsp+778h+var_6E8], r15d
0x180011684  mov     [rsp+778h+var_668], 1000000h
0x18001168f  xor     edx, edx; Val
0x180011691  lea     r8d, [rdx+78h]; Size
0x180011695  lea     rcx, [rsp+778h+var_6E0]; void *
0x18001169d  call    memset_0
0x1800116a2  mov     eax, dword ptr [rsp+778h+FileHandle]
0x1800116a6  mov     [rsp+778h+dwCreationDisposition], eax
0x1800116aa  mov     r9d, [rsp+778h+Status]
0x1800116af  lea     r8, aNtqueryvolumei; "NtQueryVolumeInformationFile: NTSTATUS:"...
0x1800116b6  lea     rdx, [rsp+778h+var_708]
0x1800116bb  lea     rcx, [rsp+778h+var_638]
0x1800116c3  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800116c8  mov     eax, [rsp+778h+Status]
0x1800116cc  test    eax, eax
0x1800116ce  jns     loc_180011906
0x1800116d4  mov     ecx, eax; Status
0x1800116d6  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800116dc  mov     ebx, eax
0x1800116de  cmp     eax, 15h
0x1800116e1  jz      loc_18001181F
0x1800116e7  cmp     eax, 48Fh
0x1800116ec  jz      loc_18001181F
0x1800116f2  cmp     [rsp+778h+arg_18], esi
0x1800116f9  jz      loc_18001179D
0x1800116ff  test    eax, eax
0x180011701  jg      short loc_180011709
0x180011703  mov     dword ptr [rsp+778h+TotalNumberOfBytes], eax
0x180011707  jmp     short loc_180011715
0x180011709  movzx   eax, bx
0x18001170c  or      eax, 80070000h
0x180011711  mov     dword ptr [rsp+778h+TotalNumberOfBytes], eax
0x180011715  mov     [rsp+778h+var_708], r12
0x18001171a  mov     [rsp+778h+var_700], r13
0x18001171f  mov     [rsp+778h+var_6F8], rdi
0x180011727  mov     [rsp+778h+var_6F0], 952h
0x180011732  mov     [rsp+778h+var_6EC], r14d
0x18001173a  mov     [rsp+778h+var_6E8], r15d
0x180011742  mov     [rsp+778h+var_668], 1000000h
0x18001174d  xor     edx, edx; Val
0x18001174f  lea     r8d, [rdx+78h]; Size
0x180011753  lea     rcx, [rsp+778h+var_6E0]; void *
0x18001175b  call    memset_0
0x180011760  mov     [rsp+778h+var_740], ebx
0x180011764  mov     eax, dword ptr [rsp+778h+FileHandle]
0x180011768  mov     dword ptr [rsp+778h+hTemplateFile], eax
0x18001176c  mov     eax, [rsp+778h+Status]
0x180011770  mov     [rsp+778h+dwFlagsAndAttributes], eax
0x180011774  mov     r9, [rsp+778h+lpRootPathName]
0x180011779  mov     qword ptr [rsp+778h+dwCreationDisposition], r9
0x18001177e  lea     r9, aNtqueryvolumei_0; "NtQueryVolumeInformationFile failed for"...
0x180011785  mov     r8d, dword ptr [rsp+778h+TotalNumberOfBytes]
0x18001178a  lea     rdx, [rsp+778h+var_708]
0x18001178f  lea     rcx, [rsp+778h+var_638]
0x180011797  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18001179d  mov     [rsp+778h+var_708], r12
0x1800117a2  mov     [rsp+778h+var_700], r13
0x1800117a7  mov     [rsp+778h+var_6F8], rdi
0x1800117af  mov     [rsp+778h+var_6F0], 957h
0x1800117ba  mov     [rsp+778h+var_6EC], r14d
0x1800117c2  mov     [rsp+778h+var_6E8], r15d
0x1800117ca  mov     [rsp+778h+var_668], 1000000h
0x1800117d5  xor     edx, edx; Val
0x1800117d7  lea     r8d, [rdx+78h]; Size
  ... truncated ...
```
