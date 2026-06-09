# W3_STATIC_FILE_HANDLER::Initialize(void)

- ea: `0x180017560`
- end: `0x180017712`
- name: `?Initialize@W3_STATIC_FILE_HANDLER@@SAJXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000806c`

## callees

- `0x1800011d4`
- `0x1800084a0`
- `0x180017560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017616`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017604`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017604`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x180017654`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x180017654`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180017684`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180017684`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800175d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800175d5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800176b5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800176e0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800176b5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800176e0`

## string_xrefs

- `0x18001758a`: `System\CurrentControlSet\Services\w3svc\Parameters`
- `0x1800175fb`: `iisres.dll`

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
0x180017560  push    rbp
0x180017562  push    rbx
0x180017563  mov     rbp, rsp
0x180017566  sub     rsp, 38h
0x18001756a  lea     rax, [rbp+hKey]
0x18001756e  mov     [rbp+Data], 0
0x180017575  mov     r9d, 20019h; samDesired
0x18001757b  mov     [rsp+38h+phkResult], rax; phkResult
0x180017580  xor     r8d, r8d; ulOptions
0x180017583  mov     [rbp+Type], 0
0x18001758a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x180017591  mov     [rbp+cbData], 4
0x180017598  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001759f  mov     [rbp+hKey], 0
0x1800175a7  call    cs:__imp_RegOpenKeyExW
0x1800175ad  test    eax, eax
0x1800175af  jnz     short loc_1800175F8
0x1800175b1  mov     rcx, [rbp+hKey]; hKey
0x1800175b5  lea     rax, [rbp+cbData]
0x1800175b9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800175be  lea     r9, [rbp+Type]; lpType
0x1800175c2  lea     rax, [rbp+Data]
0x1800175c6  xor     r8d, r8d; lpReserved
0x1800175c9  lea     rdx, ValueName; "DoDirMonitoringForUnc"
0x1800175d0  mov     [rsp+38h+phkResult], rax; lpData
0x1800175d5  call    cs:__imp_RegQueryValueExW
0x1800175db  test    eax, eax
0x1800175dd  jnz     short loc_1800175EE
0x1800175df  cmp     [rbp+Type], 4
0x1800175e3  jnz     short loc_1800175EE
0x1800175e5  mov     eax, [rbp+Data]
0x1800175e8  mov     cs:?sm_fDoDirmonForUnc@W3_STATIC_FILE_HANDLER@@0HA, eax; int W3_STATIC_FILE_HANDLER::sm_fDoDirmonForUnc
0x1800175ee  mov     rcx, [rbp+hKey]; hKey
0x1800175f2  call    cs:__imp_RegCloseKey
0x1800175f8  xor     r8d, r8d; dwFlags
0x1800175fb  lea     rcx, LibFileName; "iisres.dll"
0x180017602  xor     edx, edx; hFile
0x180017604  call    cs:__imp_LoadLibraryExW
0x18001760a  mov     cs:?sm_hResourceDll@W3_STATIC_FILE_HANDLER@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * W3_STATIC_FILE_HANDLER::sm_hResourceDll
0x180017611  test    rax, rax
0x180017614  jnz     short loc_180017634
0x180017616  call    cs:__imp_GetLastError
0x18001761c  mov     ebx, eax
0x18001761e  test    eax, eax
0x180017620  jle     loc_180017704
0x180017626  movzx   ebx, ax
0x180017629  or      ebx, 80070000h
0x18001762f  jmp     loc_180017704
0x180017634  mov     ecx, 58h ; 'X'; Size
0x180017639  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 1; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180017643  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017648  test    rax, rax
0x18001764b  jz      loc_1800176F4
0x180017651  mov     rcx, rax
0x180017654  call    cs:__imp_??0LANG_STRING@@QEAA@XZ; LANG_STRING::LANG_STRING(void)
0x18001765a  mov     cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA, rax; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x180017661  test    rax, rax
0x180017664  jz      loc_1800176FF
0x18001766a  mov     rdx, cs:?sm_hResourceDll@W3_STATIC_FILE_HANDLER@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * W3_STATIC_FILE_HANDLER::sm_hResourceDll
0x180017671  mov     r8d, 5
0x180017677  mov     rcx, rax
0x18001767a  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 2; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x180017684  call    cs:__imp_?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x18001768a  mov     ebx, eax
0x18001768c  test    eax, eax
0x18001768e  js      short loc_180017704
0x180017690  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 3; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x18001769a  mov     eax, 1
0x18001769f  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x1800176a7  inc     eax
0x1800176a9  cmp     eax, 1
0x1800176ac  jnz     short loc_1800176BB
0x1800176ae  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800176b5  call    cs:__imp_InitializeSRWLock
0x1800176bb  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 4; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x1800176c5  mov     eax, 1
0x1800176ca  lock xadd cs:?sm_lInitializeCount@META_SCRIPT_MAP_TABLE@@0JA, eax; long META_SCRIPT_MAP_TABLE::sm_lInitializeCount
0x1800176d2  inc     eax
0x1800176d4  cmp     eax, 1
0x1800176d7  jnz     short loc_1800176E6
0x1800176d9  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800176e0  call    cs:__imp_InitializeSRWLock
0x1800176e6  mov     cs:?sm_StartupState@W3_STATIC_FILE_HANDLER@@0W4StaticStartup@@A, 6; StaticStartup W3_STATIC_FILE_HANDLER::sm_StartupState
0x1800176f0  xor     eax, eax
0x1800176f2  jmp     short loc_18001770B
0x1800176f4  mov     cs:?sm_pLangString@W3_STATIC_FILE_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * W3_STATIC_FILE_HANDLER::sm_pLangString
0x1800176ff  mov     ebx, 80070008h
0x180017704  call    ?Terminate@W3_STATIC_FILE_HANDLER@@SAXXZ; W3_STATIC_FILE_HANDLER::Terminate(void)
0x180017709  mov     eax, ebx
0x18001770b  add     rsp, 38h
0x18001770f  pop     rbx
0x180017710  pop     rbp
0x180017711  retn
```
