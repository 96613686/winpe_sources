# CopyFileToAutorecover(ushort *,ushort *,int)

- ea: `0x18001e2b0`
- end: `0x18001e988`
- name: `?CopyFileToAutorecover@@YAJPEAG0H@Z`
- size: `1752`
- prototype: `__int64 __fastcall(PUCHAR pbInput, LPCWSTR lpFileName, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a290`
- `0x18000fa30`
- `0x18001016c`
- `0x1800101cc`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x18001e2b0`
- `0x18001e990`
- `0x1800298f0`
- `0x18002c98c`
- `0x18002c9f4`
- `0x1800434d4`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e6cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e6cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e43e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e43e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e354`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e42c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e354`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e42c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e606`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e7c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e606`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e7c5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001e641`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001e641`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e823`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e83f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e823`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e83f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e486`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e4d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e486`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e4d9`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001e762`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001e890`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001e8d1`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001e762`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001e890`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001e8d1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e6a6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e6a6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001e77f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001e8ee`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001e77f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001e8ee`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e662`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e662`

## string_xrefs

- `0x18001e383`: `Working Directory`
- `0x18001e45b`: `Working Directory`

## pseudocode

```c
__int64 __fastcall CopyFileToAutorecover(PUCHAR pbInput, LPCWSTR lpFileName, int a3)
{
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 v7; // rsi
  FARPROC ProcAddress; // rax
  int RegistryDll; // ebx
  signed int LastError; // eax
  bool v11; // cc
  unsigned int v12; // esi
  void *v13; // rax
  const WCHAR *v14; // rbx
  __int64 v15; // r14
  FARPROC v16; // rax
  signed int v17; // eax
  bool v18; // cc
  unsigned __int64 v19; // r14
  void *v20; // rax
  unsigned __int16 *v21; // r13
  int v22; // eax
  const unsigned __int16 *v23; // r8
  unsigned __int64 v24; // rax
  unsigned __int16 *v25; // rcx
  unsigned __int64 v26; // rcx
  __int64 v27; // rdx
  const unsigned __int16 *v28; // r10
  unsigned __int64 v29; // rax
  unsigned __int16 *v30; // r9
  unsigned __int16 v31; // cx
  unsigned __int16 *v32; // rcx
  HANDLE FileW; // rax
  void *v34; // rbx
  signed int v35; // eax
  DWORD FileSize; // esi
  HANDLE FileMappingW; // rax
  void *v38; // r15
  signed int v39; // eax
  const void *v40; // rax
  const void *v41; // r12
  signed int v42; // eax
  int v43; // eax
  WowSettings *v44; // rcx
  HANDLE v45; // rax
  void *v46; // r14
  signed int v47; // eax
  signed int v48; // eax
  WowSettings *v49; // rcx
  WowSettings *v50; // rcx
  LPCWSTR lpSrc; // [rsp+40h] [rbp-59h] BYREF
  LPWSTR lpDst; // [rsp+48h] [rbp-51h] BYREF
  PVOID OlValue; // [rsp+50h] [rbp-49h] BYREF
  int v54; // [rsp+58h] [rbp-41h]
  int v55; // [rsp+60h] [rbp-39h] BYREF
  char v56[8]; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v57; // [rsp+70h] [rbp-29h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+74h] [rbp-25h] BYREF
  __int64 v59; // [rsp+78h] [rbp-21h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-19h] BYREF
  __int64 v61; // [rsp+98h] [rbp-1h]
  HANDLE v62; // [rsp+A0h] [rbp+7h]
  HANDLE v63; // [rsp+A8h] [rbp+Fh]
  const void *v64; // [rsp+B0h] [rbp+17h]
  HANDLE v65; // [rsp+B8h] [rbp+1Fh]
  unsigned __int16 *Buffer; // [rsp+118h] [rbp+7Fh] BYREF

  v59 = 0;
  result = DLRegOpenKeyExW(-2147483646, (unsigned int)L"Software\\Microsoft\\WBEM\\CIMOM", a3, 131353, (__int64)&v59);
  if ( (_DWORD)result )
  {
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = v59;
  v61 = v59;
  v55 = 0;
  v57 = 0;
  v7 = v59;
  ProcAddress = (FARPROC)qword_1800703F0;
  if ( qword_1800703F0 )
    goto LABEL_8;
  RegistryDll = DLpLoadRegistryDll();
  if ( RegistryDll )
  {
    v11 = RegistryDll < 0;
LABEL_97:
    if ( !v11 )
      RegistryDll = (unsigned __int16)RegistryDll | 0x80070000;
    goto LABEL_99;
  }
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegQueryValueExW");
  qword_1800703F0 = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_8:
    LastError = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, int *, _QWORD, unsigned int *))ProcAddress)(
                  v7,
                  L"Working Directory",
                  0,
                  &v55,
                  0,
                  &v57);
  else
    LastError = GetLastError();
  RegistryDll = LastError;
  v11 = LastError <= 0;
  if ( LastError )
    goto LABEL_97;
  if ( v55 != 2 )
  {
LABEL_99:
    DLRegCloseKey(v6);
    return (unsigned int)RegistryDll;
  }
  if ( !v57 )
  {
    v12 = 0;
LABEL_95:
    DLRegCloseKey(v6);
    return v12;
  }
  v13 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned __int64)v57 >> 1, 2u));
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&lpSrc, v13);
  v14 = lpSrc;
  if ( !lpSrc )
  {
LABEL_14:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
    v12 = -2147217402;
    goto LABEL_95;
  }
  v15 = v59;
  v16 = (FARPROC)qword_1800703F0;
  if ( qword_1800703F0 )
    goto LABEL_19;
  v12 = DLpLoadRegistryDll();
  if ( v12 )
  {
    v18 = (v12 & 0x80000000) != 0;
LABEL_92:
    if ( !v18 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_94;
  }
  v16 = GetProcAddress(g_hInstRegistryDLL, "RegQueryValueExW");
  qword_1800703F0 = (__int64)v16;
  if ( v16 )
LABEL_19:
    v17 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, int *, const WCHAR *, unsigned int *))v16)(
            v15,
            L"Working Directory",
            0,
            &v55,
            v14,
            &v57);
  else
    v17 = GetLastError();
  v12 = v17;
  v18 = v17 <= 0;
  if ( v17 )
    goto LABEL_92;
  if ( v55 != 2 )
  {
LABEL_94:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
    goto LABEL_95;
  }
  v19 = ExpandEnvironmentStringsW(v14, 0, 0) + 51LL;
  v20 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v19, 2u));
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&lpDst, v20);
  v21 = lpDst;
  if ( !lpDst )
  {
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpDst);
    goto LABEL_14;
  }
  ExpandEnvironmentStringsW(v14, lpDst, v19);
  Buffer = 0;
  v22 = ComposeName(pbInput, &Buffer);
  v12 = v22;
  if ( v22 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v22);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids, v12);
    }
    goto LABEL_29;
  }
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(v56, Buffer);
  if ( v19 <= 0x7FFFFFFF )
  {
    v24 = v19;
    v25 = v21;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    v26 = v24 ? v19 - v24 : 0LL;
    if ( v24 )
    {
      v27 = 2147483646;
      v28 = L"\\AutoRecover\\";
      v29 = v19 - v26;
      v30 = &v21[v26];
      if ( v19 != v26 )
      {
        do
        {
          if ( !v27 )
            break;
          v31 = *v28;
          if ( !*v28 )
            break;
          ++v28;
          *v30++ = v31;
          --v27;
          --v29;
        }
        while ( v29 );
      }
      v32 = v30 - 1;
      if ( v29 )
        v32 = v30;
      *v32 = 0;
    }
  }
  StringCchCatW(v21, v19, v23);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v34 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v35 = GetLastError();
    v12 = v35;
    if ( v35 > 0 )
      v12 = (unsigned __int16)v35 | 0x80070000;
    goto LABEL_48;
  }
  v62 = FileW;
  FileSize = GetFileSize(FileW, 0);
  LODWORD(Buffer) = FileSize;
  FileMappingW = CreateFileMappingW(v34, 0, 2u, 0, 0, 0);
  v38 = FileMappingW;
  if ( !FileMappingW )
  {
    v39 = GetLastError();
    v12 = v39;
    if ( v39 > 0 )
      v12 = (unsigned __int16)v39 | 0x80070000;
    goto LABEL_52;
  }
  v63 = FileMappingW;
  v40 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  v41 = v40;
  if ( !v40 )
  {
    v42 = GetLastError();
    v12 = v42;
    if ( v42 > 0 )
      v12 = (unsigned __int16)v42 | 0x80070000;
    goto LABEL_56;
  }
  v64 = v40;
  OlValue = 0;
  v54 = 0;
  if ( !CWbemInstallObject::m_bOffline )
  {
    v43 = WowSettings::Wow64DisableWow64FsRedirection(&OlValue);
    v12 = v43;
    if ( v43 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v43);
      v44 = (WowSettings *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids, v12);
      }
      goto LABEL_63;
    }
    FileSize = (unsigned int)Buffer;
  }
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = &g_FileSD;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  v45 = CreateFileW(v21, 0x40000000u, 0, &SecurityAttributes, 2u, 0, 0);
  v46 = v45;
  if ( v45 == (HANDLE)-1LL )
  {
    v47 = GetLastError();
    v12 = v47;
    if ( v47 > 0 )
      v12 = (unsigned __int16)v47 | 0x80070000;
LABEL_63:
    if ( (int)WowSettings::EnsureWowFunctions(v44) < 0 || !WowSettings::s_bIsWow64 || !v54 )
      goto LABEL_69;
    if ( Wow64RevertWow64FsRedirection(OlValue) )
    {
      OlValue = 0;
      v54 = 0;
      goto LABEL_69;
    }
LABEL_67:
    GetLastError();
LABEL_69:
    UnmapViewOfFile(v41);
LABEL_56:
    CloseHandle(v38);
LABEL_52:
    CloseHandle(v34);
LABEL_48:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v56);
LABEL_29:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpDst);
    goto LABEL_94;
  }
  v65 = v45;
  NumberOfBytesWritten = 0;
  if ( a3 && (LOWORD(Buffer) = -257, !WriteFile(v45, &Buffer, 2u, &NumberOfBytesWritten, 0))
    || !WriteFile(v46, v41, FileSize, &NumberOfBytesWritten, 0) )
  {
    v48 = GetLastError();
    v12 = v48;
    if ( v48 > 0 )
      v12 = (unsigned __int16)v48 | 0x80070000;
    CloseHandle(v46);
    if ( (int)WowSettings::EnsureWowFunctions(v49) < 0 || !WowSettings::s_bIsWow64 || !v54 )
      goto LABEL_69;
    if ( Wow64RevertWow64FsRedirection(OlValue) )
    {
      OlValue = 0;
      v54 = 0;
      goto LABEL_69;
    }
    goto LABEL_67;
  }
  CloseHandle(v46);
  if ( (int)WowSettings::EnsureWowFunctions(v50) >= 0 && WowSettings::s_bIsWow64 && v54 )
  {
    if ( Wow64RevertWow64FsRedirection(OlValue) )
    {
      OlValue = 0;
      v54 = 0;
    }
    else
    {
      GetLastError();
    }
  }
  UnmapViewOfFile(v41);
  CloseHandle(v38);
  CloseHandle(v34);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v56);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpDst);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpSrc);
  DLRegCloseKey(v6);
  return 0;
}

```

## disassembly

```asm
0x18001e2b0  mov     [rsp-8+arg_0], rbx
0x18001e2b5  mov     [rsp-8+arg_10], r8d
0x18001e2ba  push    rbp
0x18001e2bb  push    rsi
0x18001e2bc  push    rdi
0x18001e2bd  push    r12
0x18001e2bf  push    r13
0x18001e2c1  push    r14
0x18001e2c3  push    r15
0x18001e2c5  lea     rbp, [rsp-27h]
0x18001e2ca  sub     rsp, 0C0h
0x18001e2d1  mov     r12, rdx
0x18001e2d4  mov     r15, rcx
0x18001e2d7  xor     r13d, r13d
0x18001e2da  mov     [rbp+57h+var_78], r13
0x18001e2de  lea     rax, [rbp+57h+var_78]
0x18001e2e2  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x18001e2e7  mov     r9d, 20119h
0x18001e2ed  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\CIMOM"
0x18001e2f4  mov     rcx, 0FFFFFFFF80000002h
0x18001e2fb  call    DLRegOpenKeyExW
0x18001e300  test    eax, eax
0x18001e302  jz      short loc_18001E317
0x18001e304  jle     loc_18001E96D
0x18001e30a  movzx   eax, ax
0x18001e30d  or      eax, 80070000h
0x18001e312  jmp     loc_18001E96D
0x18001e317  mov     rdi, [rbp+57h+var_78]
0x18001e31b  mov     [rbp+57h+var_58], rdi
0x18001e31f  mov     [rbp+57h+var_90], r13d
0x18001e323  mov     [rbp+57h+var_80], r13d
0x18001e327  mov     rsi, [rbp+57h+var_78]
0x18001e32b  mov     rax, cs:qword_1800703F0
0x18001e332  test    rax, rax
0x18001e335  jnz     short loc_18001E36E
0x18001e337  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18001e33c  mov     ebx, eax
0x18001e33e  test    eax, eax
0x18001e340  jnz     loc_18001E956
0x18001e346  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18001e34d  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001e354  call    cs:__imp_GetProcAddress
0x18001e35a  mov     cs:qword_1800703F0, rax
0x18001e361  test    rax, rax
0x18001e364  jnz     short loc_18001E36E
0x18001e366  call    cs:__imp_GetLastError
0x18001e36c  jmp     short loc_18001E392
0x18001e36e  lea     rcx, [rbp+57h+var_80]
0x18001e372  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rcx
0x18001e377  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r13
0x18001e37c  lea     r9, [rbp+57h+var_90]
0x18001e380  xor     r8d, r8d
0x18001e383  lea     rdx, aWorkingDirecto; "Working Directory"
0x18001e38a  mov     rcx, rsi
0x18001e38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e392  mov     ebx, eax
0x18001e394  test    eax, eax
0x18001e396  jnz     loc_18001E958
0x18001e39c  cmp     [rbp+57h+var_90], 2
0x18001e3a0  jnz     loc_18001E963
0x18001e3a6  mov     eax, [rbp+57h+var_80]
0x18001e3a9  test    eax, eax
0x18001e3ab  jnz     short loc_18001E3B5
0x18001e3ad  mov     esi, r13d
0x18001e3b0  jmp     loc_18001E94A
0x18001e3b5  mov     rcx, rax
0x18001e3b8  shr     rcx, 1
0x18001e3bb  mov     eax, 2
0x18001e3c0  mul     rcx
0x18001e3c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e3ca  cmovb   rax, rcx
0x18001e3ce  mov     rcx, rax; unsigned __int64
0x18001e3d1  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e3d6  mov     rdx, rax
0x18001e3d9  lea     rcx, [rbp+57h+lpSrc]
0x18001e3dd  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001e3e2  nop
0x18001e3e3  mov     rbx, [rbp+57h+lpSrc]
0x18001e3e7  test    rbx, rbx
0x18001e3ea  jnz     short loc_18001E3FF
0x18001e3ec  lea     rcx, [rbp+57h+lpSrc]
0x18001e3f0  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001e3f5  mov     esi, 80041006h
0x18001e3fa  jmp     loc_18001E94A
0x18001e3ff  mov     r14, [rbp+57h+var_78]
0x18001e403  mov     rax, cs:qword_1800703F0
0x18001e40a  test    rax, rax
0x18001e40d  jnz     short loc_18001E446
0x18001e40f  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18001e414  mov     esi, eax
0x18001e416  test    eax, eax
0x18001e418  jnz     loc_18001E933
0x18001e41e  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18001e425  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001e42c  call    cs:__imp_GetProcAddress
0x18001e432  mov     cs:qword_1800703F0, rax
0x18001e439  test    rax, rax
0x18001e43c  jnz     short loc_18001E446
0x18001e43e  call    cs:__imp_GetLastError
0x18001e444  jmp     short loc_18001E46A
0x18001e446  lea     rcx, [rbp+57h+var_80]
0x18001e44a  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rcx
0x18001e44f  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rbx
0x18001e454  lea     r9, [rbp+57h+var_90]
0x18001e458  xor     r8d, r8d
0x18001e45b  lea     rdx, aWorkingDirecto; "Working Directory"
0x18001e462  mov     rcx, r14
0x18001e465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e46a  mov     esi, eax
0x18001e46c  test    eax, eax
0x18001e46e  jnz     loc_18001E935
0x18001e474  cmp     [rbp+57h+var_90], 2
0x18001e478  jnz     loc_18001E940
0x18001e47e  xor     r8d, r8d; nSize
0x18001e481  xor     edx, edx; lpDst
0x18001e483  mov     rcx, rbx; lpSrc
0x18001e486  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e48c  mov     r14d, eax
0x18001e48f  add     r14, 33h ; '3'
0x18001e493  lea     eax, [rsi+2]
0x18001e496  mul     r14
0x18001e499  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e4a0  cmovb   rax, rcx
0x18001e4a4  mov     rcx, rax; unsigned __int64
0x18001e4a7  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e4ac  mov     rdx, rax
0x18001e4af  lea     rcx, [rbp+57h+lpDst]
0x18001e4b3  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001e4b8  nop
0x18001e4b9  mov     r13, [rbp+57h+lpDst]
0x18001e4bd  test    r13, r13
0x18001e4c0  jnz     short loc_18001E4D0
0x18001e4c2  lea     rcx, [rbp+57h+lpDst]
0x18001e4c6  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001e4cb  jmp     loc_18001E3EC
0x18001e4d0  mov     r8d, r14d; nSize
0x18001e4d3  mov     rdx, r13; lpDst
0x18001e4d6  mov     rcx, rbx; lpSrc
0x18001e4d9  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e4df  xor     ebx, ebx
0x18001e4e1  mov     [rbp+57h+Buffer], rbx
0x18001e4e5  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 **
0x18001e4e9  mov     rcx, r15; pbInput
0x18001e4ec  call    ?ComposeName@@YAJPEAGPEAPEAG@Z; ComposeName(ushort *,ushort * *)
0x18001e4f1  mov     esi, eax
0x18001e4f3  test    eax, eax
0x18001e4f5  jns     short loc_18001E549
0x18001e4f7  mov     edx, eax; int
0x18001e4f9  lea     rcx, qword_18006A9C0; this
0x18001e500  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001e505  lea     rax, WPP_GLOBAL_Control
0x18001e50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e513  cmp     rcx, rax
0x18001e516  jz      short loc_18001E53B
0x18001e518  test    byte ptr [rcx+1Ch], 1
0x18001e51c  jz      short loc_18001E53B
0x18001e51e  cmp     byte ptr [rcx+19h], 2
0x18001e522  jb      short loc_18001E53B
0x18001e524  lea     edx, [rbx+0Bh]
0x18001e527  mov     r9d, esi
0x18001e52a  lea     r8, WPP_ee0346ed31b93840a3824ae448285ccd_Traceguids
0x18001e531  mov     rcx, [rcx+10h]
0x18001e535  call    WPP_SF_D
0x18001e53a  nop
0x18001e53b  lea     rcx, [rbp+57h+lpDst]
0x18001e53f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001e544  jmp     loc_18001E940
0x18001e549  mov     r8, [rbp+57h+Buffer]
0x18001e54d  mov     rdx, r8
0x18001e550  lea     rcx, [rbp+57h+var_88]
0x18001e554  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001e559  nop
0x18001e55a  cmp     r14, 7FFFFFFFh
0x18001e561  ja      short loc_18001E5D7
0x18001e563  mov     rax, r14
0x18001e566  mov     rcx, r13
0x18001e569  cmp     [rcx], bx
0x18001e56c  jz      short loc_18001E578
0x18001e56e  add     rcx, 2
0x18001e572  sub     rax, 1
0x18001e576  jnz     short loc_18001E569
0x18001e578  test    rax, rax
0x18001e57b  jz      short loc_18001E585
0x18001e57d  mov     rcx, r14
0x18001e580  sub     rcx, rax
0x18001e583  jmp     short loc_18001E588
0x18001e585  mov     rcx, rbx
0x18001e588  test    rax, rax
0x18001e58b  jz      short loc_18001E5D7
0x18001e58d  mov     edx, 7FFFFFFEh
0x18001e592  lea     r10, aAutorecover; "\\AutoRecover\\"
0x18001e599  mov     rax, r14
0x18001e59c  sub     rax, rcx
0x18001e59f  lea     r9, [r13+rcx*2+0]
0x18001e5a4  jz      short loc_18001E5C9
0x18001e5a6  test    rdx, rdx
0x18001e5a9  jz      short loc_18001E5C9
0x18001e5ab  movzx   ecx, word ptr [r10]
0x18001e5af  test    cx, cx
0x18001e5b2  jz      short loc_18001E5C9
0x18001e5b4  add     r10, 2
0x18001e5b8  mov     [r9], cx
0x18001e5bc  add     r9, 2
0x18001e5c0  dec     rdx
0x18001e5c3  sub     rax, 1
0x18001e5c7  jnz     short loc_18001E5A6
0x18001e5c9  lea     rcx, [r9-2]
0x18001e5cd  test    rax, rax
0x18001e5d0  cmovnz  rcx, r9
0x18001e5d4  mov     [rcx], bx
0x18001e5d7  mov     rdx, r14; unsigned __int64
0x18001e5da  mov     rcx, r13; unsigned __int16 *
0x18001e5dd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e5e2  xor     r14d, r14d
0x18001e5e5  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x18001e5ea  mov     [rsp+0F0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18001e5ef  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001e5f7  xor     r9d, r9d; lpSecurityAttributes
0x18001e5fa  mov     edx, 80000000h; dwDesiredAccess
0x18001e5ff  lea     r8d, [r14+1]; dwShareMode
0x18001e603  mov     rcx, r12; lpFileName
0x18001e606  call    cs:__imp_CreateFileW
0x18001e60c  mov     rbx, rax
0x18001e60f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e613  jnz     short loc_18001E638
0x18001e615  call    cs:__imp_GetLastError
0x18001e61b  mov     esi, eax
0x18001e61d  test    eax, eax
0x18001e61f  jle     short loc_18001E62A
0x18001e621  movzx   esi, ax
0x18001e624  or      esi, 80070000h
0x18001e62a  lea     rcx, [rbp+57h+var_88]
0x18001e62e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001e633  jmp     loc_18001E53B
0x18001e638  mov     [rbp+57h+var_50], rbx
0x18001e63c  xor     edx, edx; lpFileSizeHigh
0x18001e63e  mov     rcx, rbx; hFile
0x18001e641  call    cs:__imp_GetFileSize
0x18001e647  mov     esi, eax
0x18001e649  mov     dword ptr [rbp+57h+Buffer], eax
0x18001e64c  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r14; lpName
0x18001e651  mov     [rsp+0F0h+dwCreationDisposition], r14d; dwMaximumSizeLow
0x18001e656  xor     r9d, r9d; dwMaximumSizeHigh
0x18001e659  xor     edx, edx; lpFileMappingAttributes
0x18001e65b  lea     r8d, [r9+2]; flProtect
0x18001e65f  mov     rcx, rbx; hFile
0x18001e662  call    cs:__imp_CreateFileMappingW
0x18001e668  mov     r15, rax
0x18001e66b  test    rax, rax
0x18001e66e  jnz     short loc_18001E690
0x18001e670  call    cs:__imp_GetLastError
0x18001e676  mov     esi, eax
0x18001e678  test    eax, eax
0x18001e67a  jle     short loc_18001E685
0x18001e67c  movzx   esi, ax
0x18001e67f  or      esi, 80070000h
0x18001e685  mov     rcx, rbx; hObject
0x18001e688  call    cs:__imp_CloseHandle
0x18001e68e  jmp     short loc_18001E62A
0x18001e690  mov     [rbp+57h+var_48], r15
0x18001e694  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r14; dwNumberOfBytesToMap
0x18001e699  xor     r9d, r9d; dwFileOffsetLow
0x18001e69c  xor     r8d, r8d; dwFileOffsetHigh
0x18001e69f  lea     edx, [r9+4]; dwDesiredAccess
0x18001e6a3  mov     rcx, r15; hFileMappingObject
0x18001e6a6  call    cs:__imp_MapViewOfFile
0x18001e6ac  mov     r12, rax
0x18001e6af  test    rax, rax
0x18001e6b2  jnz     short loc_18001E6D4
0x18001e6b4  call    cs:__imp_GetLastError
0x18001e6ba  mov     esi, eax
0x18001e6bc  test    eax, eax
0x18001e6be  jle     short loc_18001E6C9
0x18001e6c0  movzx   esi, ax
0x18001e6c3  or      esi, 80070000h
0x18001e6c9  mov     rcx, r15; hObject
0x18001e6cc  call    cs:__imp_CloseHandle
0x18001e6d2  jmp     short loc_18001E685
0x18001e6d4  mov     [rbp+57h+var_40], r12
0x18001e6d8  mov     [rbp+57h+OlValue], r14
0x18001e6dc  mov     [rbp+57h+var_98], r14d
0x18001e6e0  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, r14b; bool CWbemInstallObject::m_bOffline
0x18001e6e7  jnz     loc_18001E78D
0x18001e6ed  lea     rcx, [rbp+57h+OlValue]; OldValue
0x18001e6f1  call    ?Wow64DisableWow64FsRedirection@WowSettings@@QEAAJXZ; WowSettings::Wow64DisableWow64FsRedirection(void)
0x18001e6f6  mov     esi, eax
0x18001e6f8  test    eax, eax
0x18001e6fa  jns     loc_18001E78A
0x18001e700  mov     edx, eax; int
0x18001e702  lea     rcx, qword_18006A9C0; this
0x18001e709  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001e70e  lea     rax, WPP_GLOBAL_Control
0x18001e715  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e71c  cmp     rcx, rax
0x18001e71f  jz      short loc_18001E746
0x18001e721  test    byte ptr [rcx+1Ch], 1
0x18001e725  jz      short loc_18001E746
0x18001e727  cmp     byte ptr [rcx+19h], 2
0x18001e72b  jb      short loc_18001E746
0x18001e72d  mov     edx, 0Ch
  ... truncated ...
```
