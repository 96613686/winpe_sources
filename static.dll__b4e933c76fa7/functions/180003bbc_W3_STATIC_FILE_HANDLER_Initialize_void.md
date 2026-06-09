# W3_STATIC_FILE_HANDLER::Initialize(void)

- ea: `0x180003bbc`
- end: `0x180003d6e`
- name: `?Initialize@W3_STATIC_FILE_HANDLER@@SAJXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180002850`

## callees

- `0x180001358`
- `0x180002c04`
- `0x180003bbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003c60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c72`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x180003cb0`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x180003cb0`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180003ce0`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180003ce0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c31`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003d11`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003d3c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003d11`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003d3c`

## string_xrefs

- `0x180003be6`: `System\CurrentControlSet\Services\w3svc\Parameters`
- `0x180003c57`: `iisres.dll`

## pseudocode

```c
__int64 W3_STATIC_FILE_HANDLER::Initialize(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  LANG_STRING *v2; // rax
  LANG_STRING *v3; // rax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Data = 0;
  Type = 0;
  cbData = 4;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\w3svc\\Parameters", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"DoDirMonitoringForUnc", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      W3_STATIC_FILE_HANDLER::sm_fDoDirmonForUnc = Data;
    RegCloseKey(hKey);
  }
  W3_STATIC_FILE_HANDLER::sm_hResourceDll = LoadLibraryExW(L"iisres.dll", 0, 0);
  if ( !W3_STATIC_FILE_HANDLER::sm_hResourceDll )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  W3_STATIC_FILE_HANDLER::sm_StartupState = 1;
  v2 = (LANG_STRING *)operator new(0x58u);
  if ( !v2 )
  {
    W3_STATIC_FILE_HANDLER::sm_pLangString = 0;
    goto LABEL_18;
  }
  v3 = LANG_STRING::LANG_STRING(v2);
  W3_STATIC_FILE_HANDLER::sm_pLangString = v3;
  if ( !v3 )
  {
LABEL_18:
    v1 = -2147024888;
    goto LABEL_19;
  }
  W3_STATIC_FILE_HANDLER::sm_StartupState = 2;
  v1 = LANG_STRING::Initialize(v3, W3_STATIC_FILE_HANDLER::sm_hResourceDll, 5u);
  if ( v1 < 0 )
  {
LABEL_19:
    W3_STATIC_FILE_HANDLER::Terminate();
    return (unsigned int)v1;
  }
  W3_STATIC_FILE_HANDLER::sm_StartupState = 3;
  if ( _InterlockedIncrement(&MIME_MAP_TABLE::sm_lInitializeCount) == 1 )
    InitializeSRWLock(&MIME_MAP_TABLE::sm_GlobalLock);
  W3_STATIC_FILE_HANDLER::sm_StartupState = 4;
  if ( _InterlockedIncrement(&META_SCRIPT_MAP_TABLE::sm_lInitializeCount) == 1 )
    InitializeSRWLock(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
  W3_STATIC_FILE_HANDLER::sm_StartupState = 6;
  return 0;
}

```

## disassembly

```asm
0x180003bbc  push    rbp
0x180003bbe  push    rbx
0x180003bbf  mov     rbp, rsp
0x180003bc2  sub     rsp, 38h
0x180003bc6  lea     rax, [rbp+hKey]
0x180003bca  mov     [rbp+Data], 0
0x180003bd1  mov     r9d, 20019h; samDesired
0x180003bd7  mov     [rsp+38h+phkResult], rax; phkResult
0x180003bdc  xor     r8d, r8d; ulOptions
0x180003bdf  mov     [rbp+Type], 0
0x180003be6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x180003bed  mov     [rbp+cbData], 4
0x180003bf4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003bfb  mov     [rbp+hKey], 0
0x180003c03  call    cs:__imp_RegOpenKeyExW
0x180003c09  test    eax, eax
0x180003c0b  jnz     short loc_180003C54
0x180003c0d  mov     rcx, [rbp+hKey]; hKey
0x180003c11  lea     rax, [rbp+cbData]
0x180003c15  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180003c1a  lea     r9, [rbp+Type]; lpType
0x180003c1e  lea     rax, [rbp+Data]
0x180003c22  xor     r8d, r8d; lpReserved
0x180003c25  lea     rdx, ValueName; "DoDirMonitoringForUnc"
0x180003c2c  mov     [rsp+38h+phkResult], rax; lpData
0x180003c31  call    cs:__imp_RegQueryValueExW
0x180003c37  test    eax, eax
0x180003c39  jnz     short loc_180003C4A
0x180003c3b  cmp     [rbp+Type], 4
0x180003c3f  jnz     short loc_180003C4A
0x180003c41  mov     eax, [rbp+Data]
0x180003c44  mov     cs:?sm_fDoDirmonForUnc@W3_STATIC_FILE_HANDLER@@0HA, eax; int W3_STATIC_FILE_HANDLER::sm_fDoDirmonForUnc
0x180003c4a  mov     rcx, [rbp+hKey]; hKey
0x180003c4e  call    cs:__imp_RegCloseKey
0x180003c54  xor     r8d, r8d; dwFlags
0x180003c57  lea     rcx, LibFileName; "iisres.dll"
0x180003c5e  xor     edx, edx; hFile
0x180003c60  call    cs:__imp_LoadLibraryExW
0x180003c66  mov     cs:?sm_hResourceDll@W3_STATIC_FILE_HANDLER@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * W3_STATIC_FILE_HANDLER::sm_hResourceDll
0x180003c6d  test    rax, rax
0x180003c70  jnz     short loc_180003C90
0x180003c72  call    cs:__imp_GetLastError
0x180003c78  mov     ebx, eax
0x180003c7a  test    eax, eax
0x180003c7c  jle     loc_180003D60
0x180003c82  movzx   ebx, ax
0x180003c85  or      ebx, 80070000h
0x180003c8b  jmp     loc_180003D60
0x180003c90  mov     ecx, 58h ; 'X'; Size
0x180003c95  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 1; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180003c9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ca4  test    rax, rax
0x180003ca7  jz      loc_180003D50
0x180003cad  mov     rcx, rax
0x180003cb0  call    cs:__imp_??0LANG_STRING@@QEAA@XZ; LANG_STRING::LANG_STRING(void)
0x180003cb6  mov     cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA, rax; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x180003cbd  test    rax, rax
0x180003cc0  jz      loc_180003D5B
0x180003cc6  mov     rdx, cs:?sm_hResourceDll@W3_STATIC_FILE_HANDLER@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * W3_STATIC_FILE_HANDLER::sm_hResourceDll
0x180003ccd  mov     r8d, 5
0x180003cd3  mov     rcx, rax
0x180003cd6  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 2; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180003ce0  call    cs:__imp_?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x180003ce6  mov     ebx, eax
0x180003ce8  test    eax, eax
0x180003cea  js      short loc_180003D60
0x180003cec  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 3; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180003cf6  mov     eax, 1
0x180003cfb  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x180003d03  inc     eax
0x180003d05  cmp     eax, 1
0x180003d08  jnz     short loc_180003D17
0x180003d0a  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180003d11  call    cs:__imp_InitializeSRWLock
0x180003d17  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 4; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180003d21  mov     eax, 1
0x180003d26  lock xadd cs:?sm_lInitializeCount@META_SCRIPT_MAP_TABLE@@0JA, eax; long META_SCRIPT_MAP_TABLE::sm_lInitializeCount
0x180003d2e  inc     eax
0x180003d30  cmp     eax, 1
0x180003d33  jnz     short loc_180003D42
0x180003d35  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180003d3c  call    cs:__imp_InitializeSRWLock
0x180003d42  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 6; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180003d4c  xor     eax, eax
0x180003d4e  jmp     short loc_180003D67
0x180003d50  mov     cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x180003d5b  mov     ebx, 80070008h
0x180003d60  call    ?Terminate@W3_STATIC_FILE_HANDLER@@SAXXZ; W3_STATIC_FILE_HANDLER::Terminate(void)
0x180003d65  mov     eax, ebx
0x180003d67  add     rsp, 38h
0x180003d6b  pop     rbx
0x180003d6c  pop     rbp
0x180003d6d  retn
```
