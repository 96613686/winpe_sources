# InstallClientTLSCertificatesLinux(void)

- ea: `0x10040d5d0`
- end: `0x10040e148`
- name: `?InstallClientTLSCertificatesLinux@@YAXXZ`
- size: `2936`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100412470`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x1004012e0`
- `0x100401580`
- `0x1004019a0`
- `0x100402ec0`
- `0x100403f80`
- `0x100404060`
- `0x10040d5d0`
- `0x10041ebd0`
- `0x1004403d0`
- `0x1004534f8`

## import_xrefs

- `CRYPT32!CryptStringToBinaryA` at `0x10040dda8`
- `CRYPT32!CryptStringToBinaryA` at `0x10040de8b`
- `CRYPT32!CryptStringToBinaryA` at `0x10040dda8`
- `CRYPT32!CryptStringToBinaryA` at `0x10040de8b`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x10040def8`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x10040def8`
- `CRYPT32!CertCloseStore` at `0x10040d8bf`
- `CRYPT32!CertCloseStore` at `0x10040d8ee`
- `CRYPT32!CertOpenStore` at `0x10040d96c`
- `CRYPT32!CertOpenStore` at `0x10040d96c`
- `KERNEL32!FindFirstFileW` at `0x10040da0e`
- `KERNEL32!FindFirstFileW` at `0x10040da0e`
- `KERNEL32!CreateFileW` at `0x10040dc35`
- `KERNEL32!CreateFileW` at `0x10040dc35`
- `KERNEL32!ReadFile` at `0x10040dd34`
- `KERNEL32!ReadFile` at `0x10040dd34`
- `KERNEL32!FindNextFileW` at `0x10040df85`
- `KERNEL32!FindNextFileW` at `0x10040df85`
- `KERNEL32!CloseHandle` at `0x10040df5e`
- `KERNEL32!CloseHandle` at `0x10040df5e`
- `KERNEL32!GetLastError` at `0x10040d986`
- `KERNEL32!GetLastError` at `0x10040da2f`
- `KERNEL32!GetLastError` at `0x10040dc56`
- `KERNEL32!GetLastError` at `0x10040dc75`
- `KERNEL32!GetLastError` at `0x10040dd48`
- `KERNEL32!GetLastError` at `0x10040ddbc`
- `KERNEL32!GetLastError` at `0x10040de9f`
- `KERNEL32!GetLastError` at `0x10040df0c`
- `KERNEL32!GetLastError` at `0x10040df9a`
- `KERNEL32!GetLastError` at `0x10040dfaf`
- `KERNEL32!GetLastError` at `0x10040d986`
- `KERNEL32!GetLastError` at `0x10040da2f`
- `KERNEL32!GetLastError` at `0x10040dc56`
- `KERNEL32!GetLastError` at `0x10040dc75`
- `KERNEL32!GetLastError` at `0x10040dd48`
- `KERNEL32!GetLastError` at `0x10040ddbc`
- `KERNEL32!GetLastError` at `0x10040de9f`
- `KERNEL32!GetLastError` at `0x10040df0c`
- `KERNEL32!GetLastError` at `0x10040df9a`
- `KERNEL32!GetLastError` at `0x10040dfaf`
- `KERNEL32!FindClose` at `0x10040dfdb`
- `KERNEL32!FindClose` at `0x10040dfdb`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040d755`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040d97c`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040da25`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040daca`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040db7a`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040dc4c`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040dd3e`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040ddb2`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040de95`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040df00`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040dfa5`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040e053`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x10040e0c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040d9da`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040d9e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040da83`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040da8c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040dcd7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040de2e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040e071`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040e07d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040d9da`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040d9e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040da83`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040da8c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040dcd7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040de2e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040e071`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040e07d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d6a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d6ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d87f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040e037`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d6a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d6ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040d87f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040e037`
- `sqldk!SystemThread_TlsOffset` at `0x10040d686`
- `sqldk!SystemThread_TlsOffset` at `0x10040d6e4`
- `sqldk!SystemThread_TlsOffset` at `0x10040d864`
- `sqldk!SystemThread_TlsOffset` at `0x10040e01e`
- `sqldk!SystemThread_TlsIndex` at `0x10040d67d`
- `sqldk!SystemThread_TlsIndex` at `0x10040d6db`
- `sqldk!SystemThread_TlsIndex` at `0x10040d85b`
- `sqldk!SystemThread_TlsIndex` at `0x10040e015`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040dcbe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040de15`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040dcbe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040de15`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040dd08`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040de5f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040dd08`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040de5f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040e04d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040e04d`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040d99c`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040da45`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040dc6c`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040dd5e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040ddd2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040deb5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040df22`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040dfc5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040d99c`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040da45`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040dc6c`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040dd5e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040ddd2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040deb5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040df22`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040dfc5`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10040d6c2`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10040d6c2`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x10040d89f`

## string_xrefs

- `0x10040d75f`: `Installing Client TLS certificates to the store.\n`
- `0x10040d7c2`: `c:\var\opt\mssql\security\ca-certificates\`
- `0x10040d768`: `c:\var\opt\mssql\security\ca-certificates\*.crt`
- `0x10040d9a5`: `Error opening trusted root store: %s`
- `0x10040dadc`: `Skipping %s as it is a directory\n`
- `0x10040da4e`: `Error searching first file in /var/opt/mssql/security/ca-certificates: %s`
- `0x10040dc89`: `Skipping file: %s due to error opening it for read. Error: %s\n`
- `0x10040db92`: `Skipping file: %s as creation of complete file path from directory and file name failed. Error code: %u\n`
- `0x10040dcea`: `InstallClientTLSCertificatesLinux`
- `0x10040de41`: `InstallClientTLSCertificatesLinux`
- `0x10040dd6f`: `Skipping file: %s due to error reading it. Error: %s\n`
- `0x10040dfce`: `Error searching next file in /var/opt/mssql/security/ca-certificates: %s`
- `0x10040e061`: `Number of Files Processed in /var/opt/mssql/security/ca-certificates directory: %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
void InstallClientTLSCertificatesLinux(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // rax
  struct IMemObj *v7; // r15
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  HANDLE FirstFileW; // rsi
  DWORD v11; // eax
  wchar_t *v12; // rax
  unsigned int v13; // r13d
  void *v14; // rbx
  int *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  HANDLE FileW; // r12
  DWORD v21; // eax
  wchar_t *v22; // r14
  DWORD v23; // eax
  void *v24; // r15
  DWORD v25; // eax
  wchar_t *v26; // rax
  DWORD v27; // eax
  wchar_t *v28; // rax
  int *v29; // r14
  DWORD v30; // eax
  wchar_t *v31; // rax
  DWORD v32; // eax
  wchar_t *v33; // rax
  DWORD v34; // eax
  wchar_t *v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rcx
  char v38; // [rsp+40h] [rbp-1768h] BYREF
  unsigned int v39; // [rsp+44h] [rbp-1764h]
  DWORD pcbBinary; // [rsp+48h] [rbp-1760h] BYREF
  int v41; // [rsp+4Ch] [rbp-175Ch]
  int *v42; // [rsp+50h] [rbp-1758h]
  void *v43; // [rsp+58h] [rbp-1750h]
  struct IMemObj *v44; // [rsp+60h] [rbp-1748h]
  HCERTSTORE hCertStore; // [rsp+68h] [rbp-1740h]
  int v46; // [rsp+70h] [rbp-1738h] BYREF
  __int64 v47; // [rsp+78h] [rbp-1730h]
  int v48; // [rsp+80h] [rbp-1728h] BYREF
  int v49; // [rsp+84h] [rbp-1724h]
  __int64 v50; // [rsp+88h] [rbp-1720h]
  int v51; // [rsp+90h] [rbp-1718h] BYREF
  __int64 v52; // [rsp+98h] [rbp-1710h]
  __int64 v53; // [rsp+A0h] [rbp-1708h]
  __int64 v54; // [rsp+A8h] [rbp-1700h]
  __int64 v55; // [rsp+B0h] [rbp-16F8h]
  bool v56; // [rsp+C0h] [rbp-16E8h]
  DWORD nFileSizeLow; // [rsp+D0h] [rbp-16D8h]
  DWORD NumberOfBytesRead; // [rsp+D4h] [rbp-16D4h] BYREF
  HANDLE v59; // [rsp+D8h] [rbp-16D0h]
  __int64 v60; // [rsp+E0h] [rbp-16C8h]
  int *v61; // [rsp+E8h] [rbp-16C0h]
  void ***v62; // [rsp+F0h] [rbp-16B8h]
  char *v63; // [rsp+F8h] [rbp-16B0h]
  __int64 v64; // [rsp+118h] [rbp-1690h]
  BOOL (__stdcall *v65)(HCERTSTORE, DWORD); // [rsp+120h] [rbp-1688h]
  void ***v66; // [rsp+128h] [rbp-1680h]
  _QWORD *v67; // [rsp+130h] [rbp-1678h]
  __int64 v68; // [rsp+138h] [rbp-1670h]
  __int64 v69; // [rsp+140h] [rbp-1668h]
  __int64 v70; // [rsp+148h] [rbp-1660h]
  void *v71; // [rsp+150h] [rbp-1658h]
  _BYTE v72[40]; // [rsp+168h] [rbp-1640h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+190h] [rbp-1618h] BYREF
  _BYTE v74[4096]; // [rsp+3E0h] [rbp-13C8h] BYREF
  _OWORD v75[5]; // [rsp+13E0h] [rbp-3C8h] BYREF
  int v76; // [rsp+1430h] [rbp-378h]
  wchar_t v77; // [rsp+1434h] [rbp-374h]
  WCHAR FileName[48]; // [rsp+1440h] [rbp-368h] BYREF
  void **v79; // [rsp+14A0h] [rbp-308h] BYREF
  _QWORD v80[2]; // [rsp+14A8h] [rbp-300h] BYREF
  int v81; // [rsp+14B8h] [rbp-2F0h]
  WCHAR v82[264]; // [rsp+1570h] [rbp-238h] BYREF

  v64 = -2;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v46, 1);
  hCertStore = &v48;
  v51 = 536872037;
  v52 = 0;
  v54 = 0;
  v53 = 0;
  v55 = 0;
  v56 = 0;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = *(_QWORD *)(v1 + 600);
  if ( v2 )
    v56 = (unsigned int)SOS_Task::PushWait(v2, &v51) == 0;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v50 = v4;
  v49 = (*(_DWORD *)(v4 + 800) >> 11) & 1;
  if ( v49 || (*(_BYTE *)(v4 + 800) & 4) == 0 )
  {
    v48 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 608) + 8LL))(*(_QWORD *)(v4 + 608));
  }
  else
  {
    v48 = 0;
  }
  SOS_OS_LogUnlocalizedRoutine(L"Installing Client TLS certificates to the store.\n");
  wcscpy(FileName, L"c:\\var\\opt\\mssql\\security\\ca-certificates\\*.crt");
  v75[0] = *(_OWORD *)L"c:\\var\\opt\\mssql\\security\\ca-certificates\\";
  v75[1] = *(_OWORD *)L"pt\\mssql\\security\\ca-certificates\\";
  v75[2] = *(_OWORD *)L"\\security\\ca-certificates\\";
  v75[3] = *(_OWORD *)L"y\\ca-certificates\\";
  v75[4] = *(_OWORD *)L"tificates\\";
  v76 = *(_DWORD *)L"s\\";
  v77 = aCVarOptMssqlSe[42];
  memset_0(v82, 0, 0x20Au);
  v39 = 0;
  v43 = 0;
  v42 = 0;
  v38 = 0;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
  }
  v7 = *(struct IMemObj **)(v6 + 1000);
  v44 = v7;
  ExcHandler::ExcHandler((ExcHandler *)v72, 0, 0, 0, hdl_backout, 0);
  v65 = CertCloseStore;
  v66 = &v79;
  v67 = v80;
  v80[0] = CertCloseStore;
  v80[1] = 0;
  v81 = 0;
  v79 = &FunctionCallBinderVirtual_2<void,int (*)(void *,unsigned long),void *,int>::`vftable';
  v62 = &v79;
  v63 = &v38;
  hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"root");
  if ( !hCertStore )
  {
    LastError = GetLastError();
    OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v74, 0, 0);
    SOS_OS_LogUnlocalizedRoutine(L"Error opening trusted root store: %s", OSErrString);
    if ( v38 )
      ((void (__fastcall *)(void ***))v79[1])(&v79);
LABEL_16:
    ExcHandler::~ExcHandler((ExcHandler *)v72);
    operator delete[](0);
    operator delete[](0);
    SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)&v46);
    return;
  }
  v38 = 1;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v59 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v11 = GetLastError();
    v12 = GetOSErrString(v11, (struct ErrorStringHolder *)v74, 0, 0);
    SOS_OS_LogUnlocalizedRoutine(L"Error searching first file in /var/opt/mssql/security/ca-certificates: %s", v12);
    if ( v38 )
      ((void (__fastcall *)(void ***))v79[1])(&v79);
    goto LABEL_16;
  }
  v13 = v39;
  v14 = v43;
  v15 = v42;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      SOS_OS_LogUnlocalizedRoutine(L"Skipping %s as it is a directory\n", FindFileData.cFileName);
    }
    else if ( !FindFileData.nFileSizeLow || FindFileData.nFileSizeHigh )
    {
      SOS_OS_LogUnlocalizedRoutine(
        L"Skipping file: %s as it is either empty or larger than 2^32 bytes\n",
        FindFileData.cFileName);
    }
    else
    {
      v16 = -1;
      do
        ++v16;
      while ( FindFileData.cFileName[v16] );
      v68 = v16;
      v17 = (unsigned int)v16;
      v69 = (unsigned int)v16;
      v41 = StringCchPrintfExW(v82, 0x105u, 0, 0, 0, L"%s%s", v75, FindFileData.cFileName);
      if ( v41 >= 0 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)v75 + v18) );
        v70 = v18;
        v19 = v17 + (unsigned int)v18;
        if ( v19 >= 261 )
          _report_rangecheckfailure();
        v82[v19] = 0;
        v60 = -1;
        FileW = CreateFileW(v82, 0x80000000, 3u, 0, 3u, 0x80u, 0);
        v60 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v21 = GetLastError();
          v22 = GetOSErrString(v21, (struct ErrorStringHolder *)v74, 0, 0);
          v23 = GetLastError();
          SOS_OS_LogUnlocalizedRoutine(
            L"Skipping file: %s due to error opening it for read. Error: %s\n",
            FindFileData.cFileName,
            v23,
            v22);
        }
        else
        {
          v24 = operator new[](FindFileData.nFileSizeLow + 1, v7, 1, "sql\\ntdbms\\ksource\\serverma.cpp", 886, 6u);
          if ( v14 != v24 )
          {
            v71 = v14;
            operator delete[](v14);
          }
          v14 = v24;
          v43 = v24;
          if ( !v24 )
          {
            scierrlog(0x42F2u, L"InstallClientTLSCertificatesLinux");
            SQLExit(414, 0, 2147942414LL);
          }
          nFileSizeLow = FindFileData.nFileSizeLow;
          if ( ReadFile(FileW, v24, FindFileData.nFileSizeLow, &NumberOfBytesRead, 0) )
          {
            *((_BYTE *)v24 + FindFileData.nFileSizeLow) = 0;
            if ( CryptStringToBinaryA((LPCSTR)v24, 0, 0, 0, &pcbBinary, 0, 0) )
            {
              v29 = (int *)operator new[](pcbBinary, v44, 1, "sql\\ntdbms\\ksource\\serverma.cpp", 930, 6u);
              if ( v15 != v29 )
              {
                v61 = v15;
                operator delete[](v15);
              }
              v15 = v29;
              v42 = v29;
              if ( v29 )
              {
                if ( CryptStringToBinaryA((LPCSTR)v24, 0, 0, (BYTE *)v29, &pcbBinary, 0, 0) )
                {
                  if ( CertAddEncodedCertificateToStore(hCertStore, 1u, (const BYTE *)v29, pcbBinary, 3u, 0) )
                  {
                    SOS_OS_LogUnlocalizedRoutine(
                      L"Successfully placed %s in trusted root store\n",
                      FindFileData.cFileName);
                  }
                  else
                  {
                    v32 = GetLastError();
                    v33 = GetOSErrString(v32, (struct ErrorStringHolder *)v74, 0, 0);
                    SOS_OS_LogUnlocalizedRoutine(
                      L"Skipping file: %s due to error while adding to trusted root store. Error: %s\n",
                      FindFileData.cFileName,
                      v33);
                  }
                }
                else
                {
                  v30 = GetLastError();
                  v31 = GetOSErrString(v30, (struct ErrorStringHolder *)v74, 0, 0);
                  SOS_OS_LogUnlocalizedRoutine(
                    L"Skipping file: %s due to error while decoding to DER format. Error: %s\n",
                    FindFileData.cFileName,
                    v31);
                }
              }
              else
              {
                scierrlog(0x42F2u, L"InstallClientTLSCertificatesLinux");
                SQLExit(414, 0, 2147942414LL);
              }
            }
            else
            {
              v27 = GetLastError();
              v28 = GetOSErrString(v27, (struct ErrorStringHolder *)v74, 0, 0);
              SOS_OS_LogUnlocalizedRoutine(
                L"Skipping file: %s due to error while determining size of DER format. Error: %s\n",
                FindFileData.cFileName,
                v28);
            }
          }
          else
          {
            v25 = GetLastError();
            v26 = GetOSErrString(v25, (struct ErrorStringHolder *)v74, 0, 0);
            SOS_OS_LogUnlocalizedRoutine(
              L"Skipping file: %s due to error reading it. Error: %s\n",
              FindFileData.cFileName,
              v26);
          }
        }
        if ( FileW != (HANDLE)-1LL )
          CloseHandle(FileW);
        v7 = v44;
      }
      else
      {
        _mm_lfence();
        SOS_OS_LogUnlocalizedRoutine(
          L"Skipping file: %s as creation of complete file path from directory and file name failed. Error code: %u\n",
          FindFileData.cFileName,
          (unsigned __int16)v41);
        v13 = v39;
        v14 = v43;
        v15 = v42;
        FirstFileW = v59;
      }
    }
    v39 = ++v13;
    if ( v13 >= 0x32 )
      break;
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      if ( GetLastError() != 18 )
      {
        v34 = GetLastError();
        v35 = GetOSErrString(v34, (struct ErrorStringHolder *)v74, 0, 0);
        SOS_OS_LogUnlocalizedRoutine(L"Error searching next file in /var/opt/mssql/security/ca-certificates: %s", v35);
      }
      break;
    }
  }
  FindClose(FirstFileW);
  if ( *v63 )
    ((void (__fastcall *)(void ***))(*v62)[1])(v62);
  ExcHandler::~ExcHandler((ExcHandler *)v72);
  v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v37 = *(_QWORD *)(v36 + 256);
  if ( !v37 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v37 = *(_QWORD *)(v36 + 256);
  }
  if ( *(_DWORD *)(v37 + 556) )
    ExceptionPostCatchActions((struct Worker *)v37);
  SOS_OS_LogUnlocalizedRoutine(
    L"Number of Files Processed in /var/opt/mssql/security/ca-certificates directory: %u\n",
    v39);
  operator delete[](v42);
  operator delete[](v43);
  v61 = &v48;
  if ( v48 )
  {
    if ( v49 )
      *(_DWORD *)(v50 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v50 + 608) + 16LL))(
        *(_QWORD *)(v50 + 608),
        v50,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v51);
  *(_DWORD *)(v47 + 616) &= ~v46;
}

```

## disassembly

```asm
0x10040d5d0  push    r13
0x10040d5d2  push    r14
0x10040d5d4  push    r15
0x10040d5d6  mov     eax, 1790h
0x10040d5db  call    _alloca_probe
0x10040d5e0  sub     rsp, rax
0x10040d5e3  mov     [rsp+17A8h+var_1690], 0FFFFFFFFFFFFFFFEh
0x10040d5ef  mov     [rsp+17A8h+arg_0], rbx
0x10040d5f7  mov     [rsp+17A8h+arg_8], rsi
0x10040d5ff  mov     [rsp+17A8h+arg_10], rdi
0x10040d607  mov     [rsp+17A8h+arg_18], r12
0x10040d60f  mov     rax, cs:__security_cookie
0x10040d616  xor     rax, rsp
0x10040d619  mov     [rsp+17A8h+var_28], rax
0x10040d621  mov     edx, 1
0x10040d626  lea     rcx, [rsp+17A8h+var_1738]
0x10040d62b  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10040d630  nop
0x10040d631  lea     rax, [rsp+17A8h+var_1728]
0x10040d639  mov     [rsp+17A8h+hCertStore], rax
0x10040d63e  mov     [rsp+17A8h+var_1718], 20000465h
0x10040d649  xor     r12d, r12d
0x10040d64c  mov     [rsp+17A8h+var_1710], r12
0x10040d654  mov     [rsp+17A8h+var_1700], r12
0x10040d65c  mov     [rsp+17A8h+var_1708], r12
0x10040d664  mov     [rsp+17A8h+var_16F8], r12
0x10040d66c  mov     [rsp+17A8h+var_16E8], r12b
0x10040d674  mov     rdx, gs:58h
0x10040d67d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d684  mov     ecx, [rax]
0x10040d686  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d68d  mov     ebx, [rax]
0x10040d68f  add     rbx, [rdx+rcx*8]
0x10040d693  mov     rax, [rbx+100h]
0x10040d69a  test    rax, rax
0x10040d69d  jnz     short loc_10040D6AE
0x10040d69f  xor     ecx, ecx
0x10040d6a1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040d6a7  mov     rax, [rbx+100h]
0x10040d6ae  mov     rcx, [rax+258h]
0x10040d6b5  test    rcx, rcx
0x10040d6b8  jz      short loc_10040D6D2
0x10040d6ba  lea     rdx, [rsp+17A8h+var_1718]
0x10040d6c2  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10040d6c8  test    eax, eax
0x10040d6ca  setz    [rsp+17A8h+var_16E8]
0x10040d6d2  mov     rdx, gs:58h
0x10040d6db  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d6e2  mov     ecx, [rax]
0x10040d6e4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d6eb  mov     ebx, [rax]
0x10040d6ed  add     rbx, [rdx+rcx*8]
0x10040d6f1  mov     rdx, [rbx+100h]
0x10040d6f8  test    rdx, rdx
0x10040d6fb  jnz     short loc_10040D70C
0x10040d6fd  xor     ecx, ecx
0x10040d6ff  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040d705  mov     rdx, [rbx+100h]
0x10040d70c  mov     [rsp+17A8h+var_1720], rdx
0x10040d714  mov     eax, [rdx+320h]
0x10040d71a  shr     eax, 0Bh
0x10040d71d  and     eax, 1
0x10040d720  mov     [rsp+17A8h+var_1724], eax
0x10040d727  jnz     short loc_10040D73C
0x10040d729  test    byte ptr [rdx+320h], 4
0x10040d730  jz      short loc_10040D73C
0x10040d732  mov     [rsp+17A8h+var_1728], r12d
0x10040d73a  jmp     short loc_10040D755
0x10040d73c  mov     [rsp+17A8h+var_1728], 1
0x10040d747  mov     rcx, [rdx+260h]
0x10040d74e  mov     rax, [rcx]
0x10040d751  call    qword ptr [rax+8]
0x10040d754  nop
0x10040d755  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040d75c  mov     rdx, [rax]
0x10040d75f  lea     rcx, aInstallingClie; "Installing Client TLS certificates to t"...
0x10040d766  call    rdx
0x10040d768  movaps  xmm0, xmmword ptr cs:aCVarOptMssqlSe_0; "c:\\var\\opt\\mssql\\security\\ca-certi"...
0x10040d76f  movaps  xmmword ptr [rsp+17A8h+FileName], xmm0
0x10040d777  movaps  xmm1, xmmword ptr cs:aCVarOptMssqlSe_0+10h; "pt\\mssql\\security\\ca-certificates\\*"...
0x10040d77e  movaps  [rsp+17A8h+var_358], xmm1
0x10040d786  movaps  xmm0, xmmword ptr cs:aCVarOptMssqlSe_0+20h; "\\security\\ca-certificates\\*.crt"
0x10040d78d  movaps  [rsp+17A8h+var_348], xmm0
0x10040d795  movaps  xmm1, xmmword ptr cs:aCVarOptMssqlSe_0+30h; "y\\ca-certificates\\*.crt"
0x10040d79c  movaps  [rsp+17A8h+var_338], xmm1
0x10040d7a4  movaps  xmm0, xmmword ptr cs:aCVarOptMssqlSe_0+40h; "tificates\\*.crt"
0x10040d7ab  movaps  [rsp+17A8h+var_328], xmm0
0x10040d7b3  movaps  xmm1, xmmword ptr cs:aCVarOptMssqlSe_0+50h; "s\\*.crt"
0x10040d7ba  movaps  [rsp+17A8h+var_318], xmm1
0x10040d7c2  movaps  xmm0, xmmword ptr cs:aCVarOptMssqlSe; "c:\\var\\opt\\mssql\\security\\ca-certi"...
0x10040d7c9  movaps  [rsp+17A8h+var_3C8], xmm0
0x10040d7d1  movaps  xmm1, xmmword ptr cs:aCVarOptMssqlSe+10h; "pt\\mssql\\security\\ca-certificates\\"
0x10040d7d8  movaps  [rsp+17A8h+var_3B8], xmm1
0x10040d7e0  movaps  xmm0, xmmword ptr cs:aCVarOptMssqlSe+20h; "\\security\\ca-certificates\\"
0x10040d7e7  movaps  [rsp+17A8h+var_3A8], xmm0
0x10040d7ef  movaps  xmm1, xmmword ptr cs:aCVarOptMssqlSe+30h; "y\\ca-certificates\\"
0x10040d7f6  movaps  [rsp+17A8h+var_398], xmm1
0x10040d7fe  movaps  xmm0, xmmword ptr cs:aCVarOptMssqlSe+40h; "tificates\\"
0x10040d805  movaps  [rsp+17A8h+var_388], xmm0
0x10040d80d  mov     eax, dword ptr cs:aCVarOptMssqlSe+50h; "s\\"
0x10040d813  mov     [rsp+17A8h+var_378], eax
0x10040d81a  movzx   eax, word ptr cs:aCVarOptMssqlSe+54h; ""
0x10040d821  mov     [rsp+17A8h+var_374], ax
0x10040d829  xor     edx, edx; Val
0x10040d82b  mov     r8d, 20Ah; Size
0x10040d831  lea     rcx, [rsp+17A8h+var_238]; void *
0x10040d839  call    memset_0
0x10040d83e  mov     [rsp+17A8h+var_1764], r12d
0x10040d843  mov     [rsp+17A8h+var_1750], r12
0x10040d848  mov     [rsp+17A8h+var_1758], r12
0x10040d84d  mov     [rsp+17A8h+var_1768], 0
0x10040d852  mov     rdx, gs:58h
0x10040d85b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d862  mov     ecx, [rax]
0x10040d864  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d86b  mov     ebx, [rax]
0x10040d86d  add     rbx, [rdx+rcx*8]
0x10040d871  mov     rax, [rbx+100h]
0x10040d878  test    rax, rax
0x10040d87b  jnz     short loc_10040D88C
0x10040d87d  xor     ecx, ecx
0x10040d87f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040d885  mov     rax, [rbx+100h]
0x10040d88c  mov     r15, [rax+3E8h]
0x10040d893  mov     [rsp+17A8h+var_1748], r15
0x10040d898  xor     edx, edx; unsigned __int16
0x10040d89a  mov     qword ptr [rsp+17A8h+dwFlagsAndAttributes], r12; struct Worker *
0x10040d89f  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x10040d8a6  mov     [rsp+17A8h+pvPara], rax; int (*)(int, int, int, int, char *)
0x10040d8ab  xor     r9d, r9d; unsigned __int8
0x10040d8ae  xor     r8d, r8d; unsigned __int8
0x10040d8b1  lea     rcx, [rsp+17A8h+var_1640]; this
0x10040d8b9  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10040d8be  nop
0x10040d8bf  mov     rax, cs:__imp_CertCloseStore
0x10040d8c6  mov     [rsp+17A8h+var_1688], rax
0x10040d8ce  lea     rax, [rsp+17A8h+var_308]
0x10040d8d6  mov     [rsp+17A8h+var_1680], rax
0x10040d8de  lea     rax, [rsp+17A8h+var_300]
0x10040d8e6  mov     [rsp+17A8h+var_1678], rax
0x10040d8ee  mov     rax, cs:__imp_CertCloseStore
0x10040d8f5  mov     [rsp+17A8h+var_300], rax
0x10040d8fd  mov     [rsp+17A8h+var_2F8], r12
0x10040d905  mov     [rsp+17A8h+var_2F0], r12d
0x10040d90d  xor     eax, eax
0x10040d90f  mov     [rsp+17A8h+var_308], rax
0x10040d917  lea     rax, ??_7?$FunctorVirtualBase@X@@6B@; const FunctorVirtualBase<void>::`vftable'
0x10040d91e  mov     [rsp+17A8h+var_308], rax
0x10040d926  lea     rax, ??_7?$FunctionCallBinderVirtual_2@XP6AHPEAXK@ZPEAXH@@6B@; const FunctionCallBinderVirtual_2<void,int (*)(void *,ulong),void *,int>::`vftable'
0x10040d92d  mov     [rsp+17A8h+var_308], rax
0x10040d935  lea     rax, [rsp+17A8h+var_308]
0x10040d93d  mov     [rsp+17A8h+var_16B8], rax
0x10040d945  lea     rax, [rsp+17A8h+var_1768]
0x10040d94a  mov     [rsp+17A8h+var_16B0], rax
0x10040d952  lea     rax, aRoot; "root"
0x10040d959  mov     [rsp+17A8h+pvPara], rax; pvPara
0x10040d95e  mov     r9d, 20000h; dwFlags
0x10040d964  xor     r8d, r8d; hCryptProv
0x10040d967  xor     edx, edx; dwEncodingType
0x10040d969  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x10040d96c  call    cs:__imp_CertOpenStore
0x10040d972  mov     [rsp+17A8h+hCertStore], rax
0x10040d977  test    rax, rax
0x10040d97a  jnz     short loc_10040D9F9
0x10040d97c  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040d983  mov     rbx, [rax]
0x10040d986  call    cs:__imp_GetLastError
0x10040d98c  mov     ecx, eax
0x10040d98e  xor     r9d, r9d
0x10040d991  xor     r8d, r8d
0x10040d994  lea     rdx, [rsp+17A8h+var_13C8]
0x10040d99c  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040d9a2  mov     rdx, rax
0x10040d9a5  lea     rcx, aErrorOpeningTr; "Error opening trusted root store: %s"
0x10040d9ac  call    rbx
0x10040d9ae  nop
0x10040d9af  cmp     [rsp+17A8h+var_1768], 0
0x10040d9b4  jz      short loc_10040D9CA
0x10040d9b6  lea     rcx, [rsp+17A8h+var_308]
0x10040d9be  mov     rax, [rsp+17A8h+var_308]
0x10040d9c6  call    qword ptr [rax+8]
0x10040d9c9  nop
0x10040d9ca  lea     rcx, [rsp+17A8h+var_1640]; this
0x10040d9d2  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10040d9d7  nop
0x10040d9d8  xor     ecx, ecx
0x10040d9da  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040d9e0  nop
0x10040d9e1  xor     ecx, ecx
0x10040d9e3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040d9e9  nop
0x10040d9ea  lea     rcx, [rsp+17A8h+var_1738]; this
0x10040d9ef  call    ??1AutoSwitchPreemptive@SOS_Task@@QEAA@XZ; SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10040d9f4  jmp     loc_10040E110
0x10040d9f9  mov     [rsp+17A8h+var_1768], 1
0x10040d9fe  lea     rdx, [rsp+17A8h+FindFileData]; lpFindFileData
0x10040da06  lea     rcx, [rsp+17A8h+FileName]; lpFileName
0x10040da0e  call    cs:__imp_FindFirstFileW
0x10040da14  mov     rsi, rax
0x10040da17  mov     [rsp+17A8h+var_16D0], rax
0x10040da1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10040da23  jnz     short loc_10040DAA2
0x10040da25  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040da2c  mov     rbx, [rax]
0x10040da2f  call    cs:__imp_GetLastError
0x10040da35  mov     ecx, eax
0x10040da37  xor     r9d, r9d
0x10040da3a  xor     r8d, r8d
0x10040da3d  lea     rdx, [rsp+17A8h+var_13C8]
0x10040da45  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040da4b  mov     rdx, rax
0x10040da4e  lea     rcx, aErrorSearching_0; "Error searching first file in /var/opt/"...
0x10040da55  call    rbx
0x10040da57  nop
0x10040da58  cmp     [rsp+17A8h+var_1768], 0
0x10040da5d  jz      short loc_10040DA73
0x10040da5f  lea     rcx, [rsp+17A8h+var_308]
0x10040da67  mov     rax, [rsp+17A8h+var_308]
0x10040da6f  call    qword ptr [rax+8]
0x10040da72  nop
0x10040da73  lea     rcx, [rsp+17A8h+var_1640]; this
0x10040da7b  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10040da80  nop
0x10040da81  xor     ecx, ecx
0x10040da83  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040da89  nop
0x10040da8a  xor     ecx, ecx
0x10040da8c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040da92  nop
0x10040da93  lea     rcx, [rsp+17A8h+var_1738]; this
0x10040da98  call    ??1AutoSwitchPreemptive@SOS_Task@@QEAA@XZ; SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10040da9d  jmp     loc_10040E110
0x10040daa2  lea     rdx, aSS_1; "%s%s"
0x10040daa9  mov     r13d, [rsp+17A8h+var_1764]
0x10040daae  mov     rbx, [rsp+17A8h+var_1750]
0x10040dab3  mov     rdi, [rsp+17A8h+var_1758]
0x10040dab8  nop     dword ptr [rax+rax+00000000h]
0x10040dac0  test    byte ptr [rsp+17A8h+FindFileData.dwFileAttributes], 10h
0x10040dac8  jz      short loc_10040DAEB
0x10040daca  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040dad1  mov     r8, [rax]
0x10040dad4  lea     rdx, [rsp+17A8h+FindFileData.cFileName]
0x10040dadc  lea     rcx, aSkippingSAsItI; "Skipping %s as it is a directory\n"
0x10040dae3  call    r8
0x10040dae6  jmp     loc_10040DF6C
0x10040daeb  cmp     [rsp+17A8h+FindFileData.nFileSizeLow], 0
0x10040daf3  jz      loc_10040E0C3
0x10040daf9  cmp     [rsp+17A8h+FindFileData.nFileSizeHigh], 0
0x10040db01  jnz     loc_10040E0C3
0x10040db07  lea     rcx, [rsp+17A8h+FindFileData.cFileName]
0x10040db0f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10040db16  inc     rax
0x10040db19  cmp     word ptr [rcx+rax*2], 0
0x10040db1e  jnz     short loc_10040DB16
0x10040db20  mov     [rsp+17A8h+var_1670], rax
0x10040db28  mov     r14d, eax
0x10040db2b  mov     [rsp+17A8h+var_1668], r14
0x10040db33  lea     rax, [rsp+17A8h+FindFileData.cFileName]
0x10040db3b  mov     [rsp+17A8h+var_1770], rax
0x10040db40  lea     rax, [rsp+17A8h+var_3C8]
0x10040db48  mov     [rsp+17A8h+hTemplateFile], rax
0x10040db4d  mov     qword ptr [rsp+17A8h+dwFlagsAndAttributes], rdx; wchar_t *
0x10040db52  mov     [rsp+17A8h+pvPara], r12; unsigned int
0x10040db57  xor     r9d, r9d; unsigned __int64 *
0x10040db5a  xor     r8d, r8d; wchar_t **
0x10040db5d  mov     edx, 105h; unsigned __int64
0x10040db62  lea     rcx, [rsp+17A8h+var_238]; wchar_t *
0x10040db6a  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x10040db6f  mov     [rsp+17A8h+var_175C], eax
0x10040db73  test    eax, eax
0x10040db75  jns     short loc_10040DBB8
0x10040db77  lfence
0x10040db7a  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10040db81  mov     r9, [rax]
0x10040db84  movzx   r8d, word ptr [rsp+17A8h+var_175C]
0x10040db8a  lea     rdx, [rsp+17A8h+FindFileData.cFileName]
0x10040db92  lea     rcx, aSkippingFileSA; "Skipping file: %s as creation of comple"...
0x10040db99  call    r9
0x10040db9c  mov     r13d, [rsp+17A8h+var_1764]
0x10040dba1  mov     rbx, [rsp+17A8h+var_1750]
0x10040dba6  mov     rdi, [rsp+17A8h+var_1758]
0x10040dbab  mov     rsi, [rsp+17A8h+var_16D0]
0x10040dbb3  jmp     loc_10040DF6C
0x10040dbb8  lea     rcx, [rsp+17A8h+var_3C8]
0x10040dbc0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10040dbc7  nop     word ptr [rax+rax+00000000h]
0x10040dbd0  inc     rax
0x10040dbd3  cmp     word ptr [rcx+rax*2], 0
0x10040dbd8  jnz     short loc_10040DBD0
0x10040dbda  mov     [rsp+17A8h+var_1660], rax
0x10040dbe2  mov     ecx, eax
0x10040dbe4  add     rcx, r14
0x10040dbe7  add     rcx, rcx
0x10040dbea  cmp     rcx, 20Ah
0x10040dbf1  jnb     loc_10040E142
0x10040dbf7  mov     [rsp+rcx+17A8h+var_238], r12w
0x10040dc00  mov     [rsp+17A8h+var_16C8], 0FFFFFFFFFFFFFFFFh
0x10040dc0c  mov     [rsp+17A8h+hTemplateFile], r12; hTemplateFile
0x10040dc11  mov     [rsp+17A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x10040dc19  mov     dword ptr [rsp+17A8h+pvPara], 3; dwCreationDisposition
  ... truncated ...
```
