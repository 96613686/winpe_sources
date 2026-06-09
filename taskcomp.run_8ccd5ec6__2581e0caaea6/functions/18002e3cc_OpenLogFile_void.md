# OpenLogFile(void)

- ea: `0x18002e3cc`
- end: `0x18002ea3b`
- name: `?OpenLogFile@@YAJXZ`
- size: `1647`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011958`

## callees

- `0x1800040c0`
- `0x180007988`
- `0x18002c238`
- `0x18002c720`
- `0x18002e3cc`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002e6de`
- `msvcrt!_wcsnicmp` at `0x18002e6de`
- `msvcrt!wcsrchr` at `0x18002e67c`
- `msvcrt!wcsrchr` at `0x18002e67c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e444`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e98f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e983`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e5f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e5f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e52e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e52e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e5a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e4df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e4df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e56b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e5e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e56b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e5e3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e842`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e842`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002e96a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002e96a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e80f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e8e5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e9b6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e80f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e8e5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e9b6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e7bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e7bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002e72a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002e72a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e47c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e47c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e641`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e641`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e761`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e761`

## string_xrefs

- `0x18002e4b8`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002e522`: `LogPath`
- `0x18002e54e`: `LogPath`
- `0x18002e4f1`: `%SystemRoot%\Tasks\SCHEDLGU.TXT`

## pseudocode

```c
__int64 OpenLogFile(void)
{
  unsigned int v0; // esi
  wchar_t *v1; // r12
  signed int v2; // ebx
  int StringW; // eax
  signed int LastError; // eax
  wchar_t *v5; // rax
  __int64 v6; // rdi
  int TasksFolder; // eax
  __int64 v8; // rax
  int v9; // edx
  unsigned __int16 *v10; // rcx
  char v11; // cl
  struct _SECURITY_ATTRIBUTES *v12; // r9
  HANDLE FileW; // r14
  unsigned int v14; // r15d
  int v15; // r13d
  DWORD v16; // edx
  DWORD v17; // edx
  signed int v18; // eax
  signed int v19; // eax
  wchar_t *String2; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v25[4]; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v26; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+90h] [rbp-70h] BYREF
  char v31; // [rsp+1AAh] [rbp+AAh]
  BYTE Data[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v33[524]; // [rsp+1B4h] [rbp+B4h] BYREF
  WCHAR Dst[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  wchar_t Buffer[256]; // [rsp+5D0h] [rbp+4D0h] BYREF
  wchar_t Str[264]; // [rsp+7D0h] [rbp+6D0h] BYREF

  v0 = 0;
  *(_DWORD *)Data = 0;
  memset_0(v33, 0, 0x206u);
  String2 = 0;
  cbData = 522;
  *(_DWORD *)v25 = 32;
  v1 = 0;
  Type = 0;
  hKey = 0;
  SecurityDescriptor = 0;
  EnterCriticalSection(&gcsLogCritSection);
  if ( !ghLog )
  {
    StringW = LoadStringW(g_hInstance, 0xD05u, &::Buffer, 129);
    gcbMostRecentEntryMarkerSize = StringW;
    if ( !StringW )
      goto LABEL_4;
    gcbMostRecentEntryMarkerSize = 2 * StringW;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x2001Bu, &hKey) )
    {
      if ( RegQueryValueExW(hKey, L"LogPath", 0, &Type, Data, &cbData) || Type - 1 > 1 )
        RegSetValueExW(hKey, L"LogPath", 0, 2u, L"%SystemRoot%\\Tasks\\SCHEDLGU.TXT", 0x40u);
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"MaxLogSizeKB", 0, &Type, v25, &cbData) || Type != 4 )
      {
        *(_DWORD *)v25 = 32;
        RegSetValueExW(hKey, L"MaxLogSizeKB", 0, 4u, v25, cbData);
      }
      RegCloseKey(hKey);
    }
    if ( !*(_WORD *)Data )
      StringCchCopyW((unsigned __int16 *)Data, 0x105u, L"%SystemRoot%\\Tasks\\SCHEDLGU.TXT");
    memset_0(Dst, 0, 0x20Au);
    if ( ExpandEnvironmentStringsW((LPCWSTR)Data, Dst, 0x105u) - 1 > 0x104 )
    {
      v2 = -2147024882;
      goto LABEL_71;
    }
    StringCchCopyW(Str, 0x105u, Dst);
    v5 = wcsrchr(Str, 0x5Cu);
    if ( v5 )
      *v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( Str[v6] );
    TasksFolder = GetTasksFolder(&String2);
    v1 = String2;
    v2 = TasksFolder;
    if ( TasksFolder < 0 )
      goto LABEL_71;
    v8 = -1;
    do
      ++v8;
    while ( String2[v8] );
    if ( (_DWORD)v6 != (_DWORD)v8 || _wcsnicmp(Dst, String2, (unsigned int)v8) )
    {
      v9 = 0;
      v10 = Str;
    }
    else
    {
      v9 = 1;
      v10 = v1;
    }
    v2 = EnsureTasksFolderExists(v10, v9);
    if ( v2 < 0 )
      goto LABEL_71;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
    {
      v2 = -2147467259;
      goto LABEL_75;
    }
    v11 = v31;
    if ( v31 == 1 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:(A;;FA;;;CO)(A;;FR;;;AU)(A;;FA;;;BA)(A;;FA;;;SY)",
              1u,
              &SecurityDescriptor,
              0) )
      {
LABEL_4:
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_71;
      }
      v11 = v31;
    }
    v12 = (struct _SECURITY_ATTRIBUTES *)v29;
    if ( v11 != 1 )
      v12 = 0;
    v29[0] = 24;
    v29[2] = 0;
    v29[1] = SecurityDescriptor;
    FileW = CreateFileW(Dst, 0xC0000000, 1u, v12, 4u, 0x80000080, 0);
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_4;
    memset_0(Buffer, 0, sizeof(Buffer));
    NumberOfBytesRead = 0;
    v14 = 0;
    v15 = 0;
LABEL_38:
    String2 = 0;
    LODWORD(String2) = SetFilePointer(FileW, 0, (PLONG)&String2 + 1, 1u);
    if ( (_DWORD)String2 == -1 || !ReadFile(FileW, Buffer, 0x200u, &NumberOfBytesRead, 0) )
    {
      v16 = NumberOfBytesRead;
    }
    else
    {
      v16 = NumberOfBytesRead;
      if ( NumberOfBytesRead )
      {
        v17 = NumberOfBytesRead >> 1;
        NumberOfBytesRead >>= 1;
        while ( 1 )
        {
          if ( v0 >= v17 )
          {
            ++v15;
            v0 = 0;
            goto LABEL_38;
          }
          if ( v0 > 0x100 )
          {
            v2 = -2147024774;
            goto LABEL_71;
          }
          if ( Buffer[v0] == 91 || v14 )
            break;
LABEL_56:
          ++v0;
        }
        while ( v14 < 7 )
        {
          if ( v17 == v0 )
            goto LABEL_56;
          if ( Buffer[v0] != asc_180057108[v14] )
          {
            if ( v17 != v0 )
              v14 = 0;
            goto LABEL_56;
          }
          ++v14;
          ++v0;
        }
        if ( v14 != 7 )
          goto LABEL_56;
        String2 = &String2[v0 - 7];
        if ( SetFilePointer(FileW, (LONG)String2, (PLONG)&String2 + 1, 0) == -1 )
        {
          v18 = GetLastError();
          v2 = v18;
          if ( v18 > 0 )
            v2 = (unsigned __int16)v18 | 0x80070000;
          v17 = NumberOfBytesRead;
          goto LABEL_56;
        }
LABEL_69:
        gdwMaxLogSizeKB = *(_DWORD *)v25;
        ghLog = FileW;
        goto LABEL_71;
      }
    }
    if ( !v15
      && !v16
      && ((LODWORD(String2) = 0, v26 = -257, !WriteFile(FileW, &v26, 2u, (LPDWORD)&String2, 0)) || !(_DWORD)String2)
      || SetFilePointer(FileW, 0, 0, 2u) == -1 )
    {
      CloseHandle(FileW);
      v19 = GetLastError();
      v2 = v19;
      if ( v19 > 0 )
        v2 = (unsigned __int16)v19 | 0x80070000;
      goto LABEL_71;
    }
    goto LABEL_69;
  }
  v2 = -2147467259;
LABEL_71:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v1 )
    operator delete(v1);
LABEL_75:
  LeaveCriticalSection(&gcsLogCritSection);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002e3cc  push    rbp
0x18002e3ce  push    rbx
0x18002e3cf  push    rsi
0x18002e3d0  push    rdi
0x18002e3d1  push    r12
0x18002e3d3  push    r13
0x18002e3d5  push    r14
0x18002e3d7  push    r15
0x18002e3d9  lea     rbp, [rsp-8F8h]
0x18002e3e1  sub     rsp, 9F8h
0x18002e3e8  mov     rax, cs:__security_cookie
0x18002e3ef  xor     rax, rsp
0x18002e3f2  mov     [rbp+930h+var_50], rax
0x18002e3f9  xor     esi, esi
0x18002e3fb  lea     rcx, [rbp+930h+var_87C]; void *
0x18002e402  xor     edx, edx; Val
0x18002e404  mov     dword ptr [rbp+930h+Data], esi
0x18002e40a  mov     r8d, 206h; Size
0x18002e410  call    memset_0
0x18002e415  mov     r15d, 20Ah
0x18002e41b  mov     [rsp+0A30h+String2], rsi
0x18002e420  lea     ebx, [rsi+20h]
0x18002e423  mov     [rsp+0A30h+cbData], r15d
0x18002e428  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002e42f  mov     dword ptr [rsp+0A30h+var_9DC], ebx
0x18002e433  mov     r12d, esi
0x18002e436  mov     [rsp+0A30h+Type], esi
0x18002e43a  mov     [rsp+0A30h+hKey], rsi
0x18002e43f  mov     [rsp+0A30h+SecurityDescriptor], rsi
0x18002e444  call    cs:__imp_EnterCriticalSection
0x18002e44b  nop     dword ptr [rax+rax+00h]
0x18002e450  cmp     cs:?ghLog@@3PEAXEA, rsi; void * ghLog
0x18002e457  jz      short loc_18002E463
0x18002e459  mov     ebx, 80004005h
0x18002e45e  jmp     loc_18002E9DF
0x18002e463  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e46a  lea     r8, Buffer; lpBuffer
0x18002e471  mov     r9d, 81h; cchBufferMax
0x18002e477  mov     edx, 0D05h; uID
0x18002e47c  call    cs:__imp_LoadStringW
0x18002e483  nop     dword ptr [rax+rax+00h]
0x18002e488  mov     cs:?gcbMostRecentEntryMarkerSize@@3KA, eax; ulong gcbMostRecentEntryMarkerSize
0x18002e48e  test    eax, eax
0x18002e490  jnz     short loc_18002E4B6
0x18002e492  call    cs:__imp_GetLastError
0x18002e499  nop     dword ptr [rax+rax+00h]
0x18002e49e  mov     ebx, eax
0x18002e4a0  test    eax, eax
0x18002e4a2  jle     loc_18002E9DF
0x18002e4a8  movzx   ebx, ax
0x18002e4ab  or      ebx, 80070000h
0x18002e4b1  jmp     loc_18002E9DF
0x18002e4b6  add     eax, eax
0x18002e4b8  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002e4bf  mov     cs:?gcbMostRecentEntryMarkerSize@@3KA, eax; ulong gcbMostRecentEntryMarkerSize
0x18002e4c5  mov     r9d, 2001Bh; samDesired
0x18002e4cb  lea     rax, [rsp+0A30h+hKey]
0x18002e4d0  xor     r8d, r8d; ulOptions
0x18002e4d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e4da  mov     [rsp+0A30h+phkResult], rax; phkResult
0x18002e4df  call    cs:__imp_RegOpenKeyExW
0x18002e4e6  nop     dword ptr [rax+rax+00h]
0x18002e4eb  mov     r14d, 1
0x18002e4f1  lea     rdi, aSystemrootTask_0; "%SystemRoot%\\Tasks\\SCHEDLGU.TXT"
0x18002e4f8  lea     r13d, [r14+3]
0x18002e4fc  test    eax, eax
0x18002e4fe  jnz     loc_18002E600
0x18002e504  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002e509  lea     rax, [rsp+0A30h+cbData]
0x18002e50e  mov     [rsp+0A30h+lpcbData], rax; lpcbData
0x18002e513  lea     r9, [rsp+0A30h+Type]; lpType
0x18002e518  lea     rax, [rbp+930h+Data]
0x18002e51f  xor     r8d, r8d; lpReserved
0x18002e522  lea     rdx, aLogpath; "LogPath"
0x18002e529  mov     [rsp+0A30h+phkResult], rax; lpData
0x18002e52e  call    cs:__imp_RegQueryValueExW
0x18002e535  nop     dword ptr [rax+rax+00h]
0x18002e53a  test    eax, eax
0x18002e53c  jnz     short loc_18002E549
0x18002e53e  mov     eax, [rsp+0A30h+Type]
0x18002e542  dec     eax
0x18002e544  cmp     eax, r14d
0x18002e547  jbe     short loc_18002E577
0x18002e549  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002e54e  lea     rdx, aLogpath; "LogPath"
0x18002e555  mov     dword ptr [rsp+0A30h+lpcbData], 40h ; '@'; cbData
0x18002e55d  mov     r9d, 2; dwType
0x18002e563  xor     r8d, r8d; Reserved
0x18002e566  mov     [rsp+0A30h+phkResult], rdi; lpData
0x18002e56b  call    cs:__imp_RegSetValueExW
0x18002e572  nop     dword ptr [rax+rax+00h]
0x18002e577  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002e57c  lea     rax, [rsp+0A30h+cbData]
0x18002e581  mov     [rsp+0A30h+lpcbData], rax; lpcbData
0x18002e586  lea     r9, [rsp+0A30h+Type]; lpType
0x18002e58b  lea     rax, [rsp+0A30h+var_9DC]
0x18002e590  mov     [rsp+0A30h+cbData], r13d
0x18002e595  xor     r8d, r8d; lpReserved
0x18002e598  mov     [rsp+0A30h+phkResult], rax; lpData
0x18002e59d  lea     rdx, aMaxlogsizekb; "MaxLogSizeKB"
0x18002e5a4  call    cs:__imp_RegQueryValueExW
0x18002e5ab  nop     dword ptr [rax+rax+00h]
0x18002e5b0  test    eax, eax
0x18002e5b2  jnz     short loc_18002E5BB
0x18002e5b4  cmp     [rsp+0A30h+Type], r13d
0x18002e5b9  jz      short loc_18002E5EF
0x18002e5bb  mov     eax, [rsp+0A30h+cbData]
0x18002e5bf  lea     rdx, aMaxlogsizekb; "MaxLogSizeKB"
0x18002e5c6  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002e5cb  mov     r9d, r13d; dwType
0x18002e5ce  mov     dword ptr [rsp+0A30h+lpcbData], eax; cbData
0x18002e5d2  xor     r8d, r8d; Reserved
0x18002e5d5  lea     rax, [rsp+0A30h+var_9DC]
0x18002e5da  mov     dword ptr [rsp+0A30h+var_9DC], ebx
0x18002e5de  mov     [rsp+0A30h+phkResult], rax; lpData
0x18002e5e3  call    cs:__imp_RegSetValueExW
0x18002e5ea  nop     dword ptr [rax+rax+00h]
0x18002e5ef  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002e5f4  call    cs:__imp_RegCloseKey
0x18002e5fb  nop     dword ptr [rax+rax+00h]
0x18002e600  mov     ebx, 105h
0x18002e605  cmp     word ptr [rbp+930h+Data], si
0x18002e60c  jnz     short loc_18002E61F
0x18002e60e  mov     r8, rdi; unsigned __int16 *
0x18002e611  lea     rcx, [rbp+930h+Data]; unsigned __int16 *
0x18002e618  mov     edx, ebx; unsigned __int64
0x18002e61a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e61f  mov     r8, r15; Size
0x18002e622  lea     rcx, [rbp+930h+Dst]; void *
0x18002e629  xor     edx, edx; Val
0x18002e62b  call    memset_0
0x18002e630  mov     r8d, ebx; nSize
0x18002e633  lea     rdx, [rbp+930h+Dst]; lpDst
0x18002e63a  lea     rcx, [rbp+930h+Data]; lpSrc
0x18002e641  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e648  nop     dword ptr [rax+rax+00h]
0x18002e64d  dec     eax
0x18002e64f  cmp     eax, 104h
0x18002e654  ja      loc_18002E9DA
0x18002e65a  lea     r8, [rbp+930h+Dst]; unsigned __int16 *
0x18002e661  mov     rdx, rbx; unsigned __int64
0x18002e664  lea     rcx, [rbp+930h+Str]; unsigned __int16 *
0x18002e66b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e670  mov     edx, 5Ch ; '\'; Ch
0x18002e675  lea     rcx, [rbp+930h+Str]; Str
0x18002e67c  call    cs:__imp_wcsrchr
0x18002e683  nop     dword ptr [rax+rax+00h]
0x18002e688  test    rax, rax
0x18002e68b  jz      short loc_18002E690
0x18002e68d  mov     [rax], si
0x18002e690  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002e694  lea     rax, [rbp+930h+Str]
0x18002e69b  mov     rdi, r15
0x18002e69e  inc     rdi
0x18002e6a1  cmp     [rax+rdi*2], si
0x18002e6a5  jnz     short loc_18002E69E
0x18002e6a7  lea     rcx, [rsp+0A30h+String2]; unsigned __int16 **
0x18002e6ac  call    ?GetTasksFolder@@YAJPEAPEAG@Z; GetTasksFolder(ushort * *)
0x18002e6b1  mov     r12, [rsp+0A30h+String2]
0x18002e6b6  mov     ebx, eax
0x18002e6b8  test    eax, eax
0x18002e6ba  js      loc_18002E9DF
0x18002e6c0  mov     rax, r15
0x18002e6c3  inc     rax
0x18002e6c6  cmp     [r12+rax*2], si
0x18002e6cb  jnz     short loc_18002E6C3
0x18002e6cd  cmp     edi, eax
0x18002e6cf  jnz     short loc_18002E6F6
0x18002e6d1  mov     r8d, eax; MaxCount
0x18002e6d4  lea     rcx, [rbp+930h+Dst]; String1
0x18002e6db  mov     rdx, r12; String2
0x18002e6de  call    cs:__imp__wcsnicmp
0x18002e6e5  nop     dword ptr [rax+rax+00h]
0x18002e6ea  test    eax, eax
0x18002e6ec  jnz     short loc_18002E6F6
0x18002e6ee  mov     edx, r14d
0x18002e6f1  mov     rcx, r12
0x18002e6f4  jmp     short loc_18002E6FF
0x18002e6f6  xor     edx, edx; int
0x18002e6f8  lea     rcx, [rbp+930h+Str]; unsigned __int16 *
0x18002e6ff  call    ?EnsureTasksFolderExists@@YAJPEAGH@Z; EnsureTasksFolderExists(ushort *,int)
0x18002e704  mov     ebx, eax
0x18002e706  test    eax, eax
0x18002e708  js      loc_18002E9DF
0x18002e70e  xor     edx, edx; Val
0x18002e710  lea     rcx, [rbp+930h+VersionInformation.dwMajorVersion]; void *
0x18002e714  mov     r8d, 118h; Size
0x18002e71a  call    memset_0
0x18002e71f  lea     rcx, [rbp+930h+VersionInformation]; lpVersionInformation
0x18002e723  mov     [rbp+930h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002e72a  call    cs:__imp_GetVersionExW
0x18002e731  nop     dword ptr [rax+rax+00h]
0x18002e736  test    eax, eax
0x18002e738  jnz     short loc_18002E744
0x18002e73a  mov     ebx, 80004005h
0x18002e73f  jmp     loc_18002EA02
0x18002e744  mov     cl, [rbp+930h+var_886]
0x18002e74a  cmp     cl, r14b
0x18002e74d  jnz     short loc_18002E77B
0x18002e74f  xor     r9d, r9d; SecurityDescriptorSize
0x18002e752  lea     r8, [rsp+0A30h+SecurityDescriptor]; SecurityDescriptor
0x18002e757  mov     edx, r14d; StringSDRevision
0x18002e75a  lea     rcx, aDAFaCoAFrAuAFa; "D:(A;;FA;;;CO)(A;;FR;;;AU)(A;;FA;;;BA)("...
0x18002e761  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002e768  nop     dword ptr [rax+rax+00h]
0x18002e76d  test    eax, eax
0x18002e76f  jz      loc_18002E492
0x18002e775  mov     cl, [rbp+930h+var_886]
0x18002e77b  mov     rax, [rsp+0A30h+SecurityDescriptor]
0x18002e780  lea     r9, [rsp+0A30h+var_9C0]
0x18002e785  cmp     cl, r14b
0x18002e788  mov     [rsp+0A30h+hTemplateFile], rsi; hTemplateFile
0x18002e78d  mov     dword ptr [rsp+0A30h+lpcbData], 80000080h; dwFlagsAndAttributes
0x18002e795  lea     rcx, [rbp+930h+Dst]; lpFileName
0x18002e79c  cmovnz  r9, rsi; lpSecurityAttributes
0x18002e7a0  mov     [rsp+0A30h+var_9C0], 18h
0x18002e7a9  mov     r8d, r14d; dwShareMode
0x18002e7ac  mov     [rbp+930h+var_9B0], rsi
0x18002e7b0  mov     edx, 0C0000000h; dwDesiredAccess
0x18002e7b5  mov     [rsp+0A30h+var_9B8], rax
0x18002e7ba  mov     dword ptr [rsp+0A30h+phkResult], r13d; dwCreationDisposition
0x18002e7bf  call    cs:__imp_CreateFileW
0x18002e7c6  nop     dword ptr [rax+rax+00h]
0x18002e7cb  mov     r14, rax
0x18002e7ce  cmp     rax, r15
0x18002e7d1  jz      loc_18002E492
0x18002e7d7  xor     edx, edx; Val
0x18002e7d9  lea     rcx, [rbp+930h+Buffer]; void *
0x18002e7e0  mov     r8d, 200h; Size
0x18002e7e6  call    memset_0
0x18002e7eb  mov     [rsp+0A30h+NumberOfBytesRead], esi
0x18002e7ef  mov     r15d, esi
0x18002e7f2  mov     r13d, esi
0x18002e7f5  mov     edi, 80070000h
0x18002e7fa  mov     r9d, 1; dwMoveMethod
0x18002e800  mov     [rsp+0A30h+String2], rsi
0x18002e805  lea     r8, [rsp+0A30h+String2+4]; lpDistanceToMoveHigh
0x18002e80a  xor     edx, edx; lDistanceToMove
0x18002e80c  mov     rcx, r14; hFile
0x18002e80f  call    cs:__imp_SetFilePointer
0x18002e816  nop     dword ptr [rax+rax+00h]
0x18002e81b  mov     dword ptr [rsp+0A30h+String2], eax
0x18002e81f  cmp     eax, 0FFFFFFFFh
0x18002e822  jz      loc_18002E939
0x18002e828  lea     r9, [rsp+0A30h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e82d  mov     [rsp+0A30h+phkResult], rsi; lpOverlapped
0x18002e832  mov     r8d, 200h; nNumberOfBytesToRead
0x18002e838  lea     rdx, [rbp+930h+Buffer]; lpBuffer
0x18002e83f  mov     rcx, r14; hFile
0x18002e842  call    cs:__imp_ReadFile
0x18002e849  nop     dword ptr [rax+rax+00h]
0x18002e84e  test    eax, eax
0x18002e850  jz      loc_18002E939
0x18002e856  mov     edx, [rsp+0A30h+NumberOfBytesRead]
0x18002e85a  test    edx, edx
0x18002e85c  jz      loc_18002E93D
0x18002e862  shr     edx, 1
0x18002e864  mov     [rsp+0A30h+NumberOfBytesRead], edx
0x18002e868  cmp     esi, edx
0x18002e86a  jnb     loc_18002E925
0x18002e870  cmp     esi, 100h
0x18002e876  ja      loc_18002E92F
0x18002e87c  mov     eax, esi
0x18002e87e  cmp     [rbp+rax*2+930h+Buffer], 5Bh ; '['
0x18002e887  jz      short loc_18002E8B8
0x18002e889  test    r15d, r15d
0x18002e88c  jz      loc_18002E915
0x18002e892  jmp     short loc_18002E8B8
0x18002e894  cmp     edx, esi
0x18002e896  jz      short loc_18002E915
0x18002e898  mov     eax, r15d
0x18002e89b  lea     r8, asc_180057108; "[ *****"
0x18002e8a2  mov     ecx, esi
0x18002e8a4  movzx   eax, word ptr [r8+rax*2]
0x18002e8a9  cmp     [rbp+rcx*2+930h+Buffer], ax
0x18002e8b1  jnz     short loc_18002E91C
0x18002e8b3  inc     r15d
0x18002e8b6  inc     esi
0x18002e8b8  cmp     r15d, 7
0x18002e8bc  jb      short loc_18002E894
0x18002e8be  cmp     r15d, 7
0x18002e8c2  jnz     short loc_18002E915
0x18002e8c4  mov     rax, [rsp+0A30h+String2]
0x18002e8c9  lea     r8, [rsp+0A30h+String2+4]; lpDistanceToMoveHigh
0x18002e8ce  add     rax, 0FFFFFFFFFFFFFFF2h
0x18002e8d2  mov     ecx, esi
0x18002e8d4  xor     r9d, r9d; dwMoveMethod
0x18002e8d7  lea     rcx, [rax+rcx*2]
0x18002e8db  mov     [rsp+0A30h+String2], rcx
0x18002e8e0  mov     edx, ecx; lDistanceToMove
0x18002e8e2  mov     rcx, r14; hFile
0x18002e8e5  call    cs:__imp_SetFilePointer
0x18002e8ec  nop     dword ptr [rax+rax+00h]
0x18002e8f1  cmp     eax, 0FFFFFFFFh
0x18002e8f4  jnz     loc_18002E9C7
0x18002e8fa  call    cs:__imp_GetLastError
0x18002e901  nop     dword ptr [rax+rax+00h]
0x18002e906  mov     ebx, eax
0x18002e908  test    eax, eax
0x18002e90a  jle     short loc_18002E911
  ... truncated ...
```
