# OpenLogFile(void)

- ea: `0x18002c5d4`
- end: `0x18002cba8`
- name: `?OpenLogFile@@YAJXZ`
- size: `1492`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010efc`

## callees

- `0x180003ef0`
- `0x1800074c8`
- `0x18002a734`
- `0x18002abc4`
- `0x18002c5d4`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002c8a4`
- `msvcrt!_wcsnicmp` at `0x18002c8a4`
- `msvcrt!wcsrchr` at `0x18002c848`
- `msvcrt!wcsrchr` at `0x18002c848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c64c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c64c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cb0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c7cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c7cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c71e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c788`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c71e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c788`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c755`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c7c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c755`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c7c1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c9ea`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c9ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cafc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002cafc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c9bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ca83`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cb36`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c9bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ca83`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cb36`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c973`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c973`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002c8ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002c8ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c67e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c67e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c813`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c813`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c91b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c91b`

## string_xrefs

- `0x18002c6ae`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002c712`: `LogPath`
- `0x18002c738`: `LogPath`
- `0x18002c6e1`: `%SystemRoot%\Tasks\SCHEDLGU.TXT`

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
  signed int TasksFolder; // eax
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
          if ( Buffer[v0] != asc_180055100[v14] )
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
0x18002c5d4  push    rbp
0x18002c5d6  push    rbx
0x18002c5d7  push    rsi
0x18002c5d8  push    rdi
0x18002c5d9  push    r12
0x18002c5db  push    r13
0x18002c5dd  push    r14
0x18002c5df  push    r15
0x18002c5e1  lea     rbp, [rsp-8F8h]
0x18002c5e9  sub     rsp, 9F8h
0x18002c5f0  mov     rax, cs:__security_cookie
0x18002c5f7  xor     rax, rsp
0x18002c5fa  mov     [rbp+930h+var_50], rax
0x18002c601  xor     esi, esi
0x18002c603  lea     rcx, [rbp+930h+var_87C]; void *
0x18002c60a  xor     edx, edx; Val
0x18002c60c  mov     dword ptr [rbp+930h+Data], esi
0x18002c612  mov     r8d, 206h; Size
0x18002c618  call    memset_0
0x18002c61d  mov     r15d, 20Ah
0x18002c623  mov     [rsp+0A30h+String2], rsi
0x18002c628  lea     ebx, [rsi+20h]
0x18002c62b  mov     [rsp+0A30h+cbData], r15d
0x18002c630  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002c637  mov     dword ptr [rsp+0A30h+var_9DC], ebx
0x18002c63b  mov     r12d, esi
0x18002c63e  mov     [rsp+0A30h+Type], esi
0x18002c642  mov     [rsp+0A30h+hKey], rsi
0x18002c647  mov     [rsp+0A30h+SecurityDescriptor], rsi
0x18002c64c  call    cs:__imp_EnterCriticalSection
0x18002c652  cmp     cs:?ghLog@@3PEAXEA, rsi; void * ghLog
0x18002c659  jz      short loc_18002C665
0x18002c65b  mov     ebx, 80004005h
0x18002c660  jmp     loc_18002CB59
0x18002c665  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002c66c  lea     r8, Buffer; lpBuffer
0x18002c673  mov     r9d, 81h; cchBufferMax
0x18002c679  mov     edx, 0D05h; uID
0x18002c67e  call    cs:__imp_LoadStringW
0x18002c684  mov     cs:?gcbMostRecentEntryMarkerSize@@3KA, eax; ulong gcbMostRecentEntryMarkerSize
0x18002c68a  test    eax, eax
0x18002c68c  jnz     short loc_18002C6AC
0x18002c68e  call    cs:__imp_GetLastError
0x18002c694  mov     ebx, eax
0x18002c696  test    eax, eax
0x18002c698  jle     loc_18002CB59
0x18002c69e  movzx   ebx, ax
0x18002c6a1  or      ebx, 80070000h
0x18002c6a7  jmp     loc_18002CB59
0x18002c6ac  add     eax, eax
0x18002c6ae  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002c6b5  mov     cs:?gcbMostRecentEntryMarkerSize@@3KA, eax; ulong gcbMostRecentEntryMarkerSize
0x18002c6bb  mov     r9d, 2001Bh; samDesired
0x18002c6c1  lea     rax, [rsp+0A30h+hKey]
0x18002c6c6  xor     r8d, r8d; ulOptions
0x18002c6c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c6d0  mov     [rsp+0A30h+phkResult], rax; phkResult
0x18002c6d5  call    cs:__imp_RegOpenKeyExW
0x18002c6db  mov     r14d, 1
0x18002c6e1  lea     rdi, aSystemrootTask_0; "%SystemRoot%\\Tasks\\SCHEDLGU.TXT"
0x18002c6e8  lea     r13d, [r14+3]
0x18002c6ec  test    eax, eax
0x18002c6ee  jnz     loc_18002C7D2
0x18002c6f4  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002c6f9  lea     rax, [rsp+0A30h+cbData]
0x18002c6fe  mov     [rsp+0A30h+lpcbData], rax; lpcbData
0x18002c703  lea     r9, [rsp+0A30h+Type]; lpType
0x18002c708  lea     rax, [rbp+930h+Data]
0x18002c70f  xor     r8d, r8d; lpReserved
0x18002c712  lea     rdx, aLogpath; "LogPath"
0x18002c719  mov     [rsp+0A30h+phkResult], rax; lpData
0x18002c71e  call    cs:__imp_RegQueryValueExW
0x18002c724  test    eax, eax
0x18002c726  jnz     short loc_18002C733
0x18002c728  mov     eax, [rsp+0A30h+Type]
0x18002c72c  dec     eax
0x18002c72e  cmp     eax, r14d
0x18002c731  jbe     short loc_18002C75B
0x18002c733  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002c738  lea     rdx, aLogpath; "LogPath"
0x18002c73f  mov     dword ptr [rsp+0A30h+lpcbData], 40h ; '@'; cbData
0x18002c747  mov     r9d, 2; dwType
0x18002c74d  xor     r8d, r8d; Reserved
0x18002c750  mov     [rsp+0A30h+phkResult], rdi; lpData
0x18002c755  call    cs:__imp_RegSetValueExW
0x18002c75b  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002c760  lea     rax, [rsp+0A30h+cbData]
0x18002c765  mov     [rsp+0A30h+lpcbData], rax; lpcbData
0x18002c76a  lea     r9, [rsp+0A30h+Type]; lpType
0x18002c76f  lea     rax, [rsp+0A30h+var_9DC]
0x18002c774  mov     [rsp+0A30h+cbData], r13d
0x18002c779  xor     r8d, r8d; lpReserved
0x18002c77c  mov     [rsp+0A30h+phkResult], rax; lpData
0x18002c781  lea     rdx, aMaxlogsizekb; "MaxLogSizeKB"
0x18002c788  call    cs:__imp_RegQueryValueExW
0x18002c78e  test    eax, eax
0x18002c790  jnz     short loc_18002C799
0x18002c792  cmp     [rsp+0A30h+Type], r13d
0x18002c797  jz      short loc_18002C7C7
0x18002c799  mov     eax, [rsp+0A30h+cbData]
0x18002c79d  lea     rdx, aMaxlogsizekb; "MaxLogSizeKB"
0x18002c7a4  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002c7a9  mov     r9d, r13d; dwType
0x18002c7ac  mov     dword ptr [rsp+0A30h+lpcbData], eax; cbData
0x18002c7b0  xor     r8d, r8d; Reserved
0x18002c7b3  lea     rax, [rsp+0A30h+var_9DC]
0x18002c7b8  mov     dword ptr [rsp+0A30h+var_9DC], ebx
0x18002c7bc  mov     [rsp+0A30h+phkResult], rax; lpData
0x18002c7c1  call    cs:__imp_RegSetValueExW
0x18002c7c7  mov     rcx, [rsp+0A30h+hKey]; hKey
0x18002c7cc  call    cs:__imp_RegCloseKey
0x18002c7d2  mov     ebx, 105h
0x18002c7d7  cmp     word ptr [rbp+930h+Data], si
0x18002c7de  jnz     short loc_18002C7F1
0x18002c7e0  mov     r8, rdi; unsigned __int16 *
0x18002c7e3  lea     rcx, [rbp+930h+Data]; unsigned __int16 *
0x18002c7ea  mov     edx, ebx; unsigned __int64
0x18002c7ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c7f1  mov     r8, r15; Size
0x18002c7f4  lea     rcx, [rbp+930h+Dst]; void *
0x18002c7fb  xor     edx, edx; Val
0x18002c7fd  call    memset_0
0x18002c802  mov     r8d, ebx; nSize
0x18002c805  lea     rdx, [rbp+930h+Dst]; lpDst
0x18002c80c  lea     rcx, [rbp+930h+Data]; lpSrc
0x18002c813  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c819  dec     eax
0x18002c81b  cmp     eax, 104h
0x18002c820  ja      loc_18002CB54
0x18002c826  lea     r8, [rbp+930h+Dst]; unsigned __int16 *
0x18002c82d  mov     rdx, rbx; unsigned __int64
0x18002c830  lea     rcx, [rbp+930h+Str]; unsigned __int16 *
0x18002c837  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c83c  mov     edx, 5Ch ; '\'; Ch
0x18002c841  lea     rcx, [rbp+930h+Str]; Str
0x18002c848  call    cs:__imp_wcsrchr
0x18002c84e  test    rax, rax
0x18002c851  jz      short loc_18002C856
0x18002c853  mov     [rax], si
0x18002c856  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002c85a  lea     rax, [rbp+930h+Str]
0x18002c861  mov     rdi, r15
0x18002c864  inc     rdi
0x18002c867  cmp     [rax+rdi*2], si
0x18002c86b  jnz     short loc_18002C864
0x18002c86d  lea     rcx, [rsp+0A30h+String2]; unsigned __int16 **
0x18002c872  call    ?GetTasksFolder@@YAJPEAPEAG@Z; GetTasksFolder(ushort * *)
0x18002c877  mov     r12, [rsp+0A30h+String2]
0x18002c87c  mov     ebx, eax
0x18002c87e  test    eax, eax
0x18002c880  js      loc_18002CB59
0x18002c886  mov     rax, r15
0x18002c889  inc     rax
0x18002c88c  cmp     [r12+rax*2], si
0x18002c891  jnz     short loc_18002C889
0x18002c893  cmp     edi, eax
0x18002c895  jnz     short loc_18002C8B6
0x18002c897  mov     r8d, eax; MaxCount
0x18002c89a  lea     rcx, [rbp+930h+Dst]; String1
0x18002c8a1  mov     rdx, r12; String2
0x18002c8a4  call    cs:__imp__wcsnicmp
0x18002c8aa  test    eax, eax
0x18002c8ac  jnz     short loc_18002C8B6
0x18002c8ae  mov     edx, r14d
0x18002c8b1  mov     rcx, r12
0x18002c8b4  jmp     short loc_18002C8BF
0x18002c8b6  xor     edx, edx; int
0x18002c8b8  lea     rcx, [rbp+930h+Str]; unsigned __int16 *
0x18002c8bf  call    ?EnsureTasksFolderExists@@YAJPEAGH@Z; EnsureTasksFolderExists(ushort *,int)
0x18002c8c4  mov     ebx, eax
0x18002c8c6  test    eax, eax
0x18002c8c8  js      loc_18002CB59
0x18002c8ce  xor     edx, edx; Val
0x18002c8d0  lea     rcx, [rbp+930h+VersionInformation.dwMajorVersion]; void *
0x18002c8d4  mov     r8d, 118h; Size
0x18002c8da  call    memset_0
0x18002c8df  lea     rcx, [rbp+930h+VersionInformation]; lpVersionInformation
0x18002c8e3  mov     [rbp+930h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18002c8ea  call    cs:__imp_GetVersionExW
0x18002c8f0  test    eax, eax
0x18002c8f2  jnz     short loc_18002C8FE
0x18002c8f4  mov     ebx, 80004005h
0x18002c8f9  jmp     loc_18002CB76
0x18002c8fe  mov     cl, [rbp+930h+var_886]
0x18002c904  cmp     cl, r14b
0x18002c907  jnz     short loc_18002C92F
0x18002c909  xor     r9d, r9d; SecurityDescriptorSize
0x18002c90c  lea     r8, [rsp+0A30h+SecurityDescriptor]; SecurityDescriptor
0x18002c911  mov     edx, r14d; StringSDRevision
0x18002c914  lea     rcx, aDAFaCoAFrAuAFa; "D:(A;;FA;;;CO)(A;;FR;;;AU)(A;;FA;;;BA)("...
0x18002c91b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002c921  test    eax, eax
0x18002c923  jz      loc_18002C68E
0x18002c929  mov     cl, [rbp+930h+var_886]
0x18002c92f  mov     rax, [rsp+0A30h+SecurityDescriptor]
0x18002c934  lea     r9, [rsp+0A30h+var_9C0]
0x18002c939  cmp     cl, r14b
0x18002c93c  mov     [rsp+0A30h+hTemplateFile], rsi; hTemplateFile
0x18002c941  mov     dword ptr [rsp+0A30h+lpcbData], 80000080h; dwFlagsAndAttributes
0x18002c949  lea     rcx, [rbp+930h+Dst]; lpFileName
0x18002c950  cmovnz  r9, rsi; lpSecurityAttributes
0x18002c954  mov     [rsp+0A30h+var_9C0], 18h
0x18002c95d  mov     r8d, r14d; dwShareMode
0x18002c960  mov     [rbp+930h+var_9B0], rsi
0x18002c964  mov     edx, 0C0000000h; dwDesiredAccess
0x18002c969  mov     [rsp+0A30h+var_9B8], rax
0x18002c96e  mov     dword ptr [rsp+0A30h+phkResult], r13d; dwCreationDisposition
0x18002c973  call    cs:__imp_CreateFileW
0x18002c979  mov     r14, rax
0x18002c97c  cmp     rax, r15
0x18002c97f  jz      loc_18002C68E
0x18002c985  xor     edx, edx; Val
0x18002c987  lea     rcx, [rbp+930h+Buffer]; void *
0x18002c98e  mov     r8d, 200h; Size
0x18002c994  call    memset_0
0x18002c999  mov     [rsp+0A30h+NumberOfBytesRead], esi
0x18002c99d  mov     r15d, esi
0x18002c9a0  mov     r13d, esi
0x18002c9a3  mov     edi, 80070000h
0x18002c9a8  mov     r9d, 1; dwMoveMethod
0x18002c9ae  mov     [rsp+0A30h+String2], rsi
0x18002c9b3  lea     r8, [rsp+0A30h+String2+4]; lpDistanceToMoveHigh
0x18002c9b8  xor     edx, edx; lDistanceToMove
0x18002c9ba  mov     rcx, r14; hFile
0x18002c9bd  call    cs:__imp_SetFilePointer
0x18002c9c3  mov     dword ptr [rsp+0A30h+String2], eax
0x18002c9c7  cmp     eax, 0FFFFFFFFh
0x18002c9ca  jz      loc_18002CACB
0x18002c9d0  lea     r9, [rsp+0A30h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002c9d5  mov     [rsp+0A30h+phkResult], rsi; lpOverlapped
0x18002c9da  mov     r8d, 200h; nNumberOfBytesToRead
0x18002c9e0  lea     rdx, [rbp+930h+Buffer]; lpBuffer
0x18002c9e7  mov     rcx, r14; hFile
0x18002c9ea  call    cs:__imp_ReadFile
0x18002c9f0  test    eax, eax
0x18002c9f2  jz      loc_18002CACB
0x18002c9f8  mov     edx, [rsp+0A30h+NumberOfBytesRead]
0x18002c9fc  test    edx, edx
0x18002c9fe  jz      loc_18002CACF
0x18002ca04  shr     edx, 1
0x18002ca06  mov     [rsp+0A30h+NumberOfBytesRead], edx
0x18002ca0a  cmp     esi, edx
0x18002ca0c  jnb     loc_18002CAB7
0x18002ca12  cmp     esi, 100h
0x18002ca18  ja      loc_18002CAC1
0x18002ca1e  mov     eax, esi
0x18002ca20  cmp     [rbp+rax*2+930h+Buffer], 5Bh ; '['
0x18002ca29  jz      short loc_18002CA56
0x18002ca2b  test    r15d, r15d
0x18002ca2e  jz      short loc_18002CAA7
0x18002ca30  jmp     short loc_18002CA56
0x18002ca32  cmp     edx, esi
0x18002ca34  jz      short loc_18002CAA7
0x18002ca36  mov     eax, r15d
0x18002ca39  lea     r8, asc_180055100; "[ *****"
0x18002ca40  mov     ecx, esi
0x18002ca42  movzx   eax, word ptr [r8+rax*2]
0x18002ca47  cmp     [rbp+rcx*2+930h+Buffer], ax
0x18002ca4f  jnz     short loc_18002CAAE
0x18002ca51  inc     r15d
0x18002ca54  inc     esi
0x18002ca56  cmp     r15d, 7
0x18002ca5a  jb      short loc_18002CA32
0x18002ca5c  cmp     r15d, 7
0x18002ca60  jnz     short loc_18002CAA7
0x18002ca62  mov     rax, [rsp+0A30h+String2]
0x18002ca67  lea     r8, [rsp+0A30h+String2+4]; lpDistanceToMoveHigh
0x18002ca6c  add     rax, 0FFFFFFFFFFFFFFF2h
0x18002ca70  mov     ecx, esi
0x18002ca72  xor     r9d, r9d; dwMoveMethod
0x18002ca75  lea     rcx, [rax+rcx*2]
0x18002ca79  mov     [rsp+0A30h+String2], rcx
0x18002ca7e  mov     edx, ecx; lDistanceToMove
0x18002ca80  mov     rcx, r14; hFile
0x18002ca83  call    cs:__imp_SetFilePointer
0x18002ca89  cmp     eax, 0FFFFFFFFh
0x18002ca8c  jnz     loc_18002CB41
0x18002ca92  call    cs:__imp_GetLastError
0x18002ca98  mov     ebx, eax
0x18002ca9a  test    eax, eax
0x18002ca9c  jle     short loc_18002CAA3
0x18002ca9e  movzx   ebx, ax
0x18002caa1  or      ebx, edi
0x18002caa3  mov     edx, [rsp+0A30h+NumberOfBytesRead]
0x18002caa7  inc     esi
0x18002caa9  jmp     loc_18002CA0A
0x18002caae  cmp     edx, esi
0x18002cab0  jz      short loc_18002CAA7
0x18002cab2  xor     r15d, r15d
0x18002cab5  jmp     short loc_18002CAA7
0x18002cab7  inc     r13d
0x18002caba  xor     esi, esi
0x18002cabc  jmp     loc_18002C9A8
0x18002cac1  mov     ebx, 8007007Ah
0x18002cac6  jmp     loc_18002CB59
0x18002cacb  mov     edx, [rsp+0A30h+NumberOfBytesRead]
0x18002cacf  test    r13d, r13d
0x18002cad2  jnz     short loc_18002CB28
0x18002cad4  test    edx, edx
0x18002cad6  jnz     short loc_18002CB28
  ... truncated ...
```
