# UsoCommitHelper::IsShutdownAfterUpdateSetAndClearKey(int *,tagShutdownScenarios *)

- ea: `0x14000b13c`
- end: `0x14000b413`
- name: `?IsShutdownAfterUpdateSetAndClearKey@UsoCommitHelper@@SAJPEAHPEAW4tagShutdownScenarios@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(int *, enum tagShutdownScenarios *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140084e20`

## callees

- `0x14000aa04`
- `0x14000af7c`
- `0x14000b13c`
- `0x14000b41c`
- `0x14000b43c`
- `0x14005eebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b394`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b389`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b3a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b389`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b3a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b2c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b33d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b2c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000b33d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b181`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b1f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b181`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b1f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b1a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b20e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b381`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b39f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b1a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b20e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b381`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b39f`

## string_xrefs

- `0x14000b18a`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x14000b2f1`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x14000b365`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x14000b173`: `SOFTWARE\Microsoft\WindowsUpdate\CommitStatus`
- `0x14000b1e5`: `SOFTWARE\Microsoft\WindowsUpdate\CommitStatus`
- `0x14000b2bc`: `NoCommit`
- `0x14000b330`: `UpdateAndShutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UsoCommitHelper::IsShutdownAfterUpdateSetAndClearKey(int *a1, enum tagShutdownScenarios *a2)
{
  int v4; // r15d
  unsigned int ValueW; // eax
  int v6; // ebx
  int v7; // esi
  unsigned int v8; // eax
  int v9; // ebx
  __int64 v11; // rdx
  HKEY v12; // rdi
  HKEY v13; // rdi
  DWORD LastError; // ebx
  DWORD v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  int pvData; // [rsp+88h] [rbp+48h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+58h] BYREF

  *(_DWORD *)a2 = 0;
  v4 = 0;
  hKey = 0;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\CommitStatus", 0, 0x20019u, &hKey);
  if ( ValueW - 2 <= 1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_5;
  }
  if ( ValueW )
  {
    v16 = 266;
  }
  else
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, L"NoCommit", 0x18u, 0, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_5;
    }
    if ( !ValueW )
    {
      v4 = pvData;
      v12 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v12);
        SetLastError(LastError);
      }
      goto LABEL_5;
    }
    v16 = 284;
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v16,
         (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
         (const char *)ValueW,
         phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( v6 < 0 )
  {
    v11 = 124;
    goto LABEL_16;
  }
LABEL_5:
  v7 = 0;
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\CommitStatus", 0, 0x20019u, &hKey);
  if ( v8 - 2 <= 1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_8;
  }
  if ( v8 )
  {
    v17 = 266;
  }
  else
  {
    pvData = 0;
    pcbData = 4;
    v8 = RegGetValueW(hKey, 0, L"UpdateAndShutdown", 0x18u, 0, &pvData, &pcbData);
    if ( v8 == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_8;
    }
    if ( !v8 )
    {
      v7 = pvData;
      v13 = hKey;
      if ( hKey )
      {
        v15 = GetLastError();
        RegCloseKey(v13);
        SetLastError(v15);
      }
      goto LABEL_8;
    }
    v17 = 284;
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v17,
         (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
         (const char *)v8,
         phkResulta);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( v6 < 0 )
  {
    v11 = 127;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
      (const char *)(unsigned int)v6,
      phkResulta);
    return (unsigned int)v6;
  }
LABEL_8:
  v6 = UsoCommitHelper::RemoveCommitStatusKey();
  if ( v6 < 0 )
  {
    v11 = 130;
    goto LABEL_16;
  }
  v9 = 0;
  if ( v7 == 1 )
  {
    *(_DWORD *)a2 = 1;
    v9 = 1;
  }
  if ( v4 == 1 )
    *(_DWORD *)a2 = 2;
  UsoCommitHelper::PersistRebootEndTime();
  *a1 = v9;
  return 0;
}

```

## disassembly

```asm
0x14000b13c  push    rbp
0x14000b13e  push    rbx
0x14000b13f  push    rsi
0x14000b140  push    rdi
0x14000b141  push    r12
0x14000b143  push    r14
0x14000b145  push    r15
0x14000b147  mov     rbp, rsp
0x14000b14a  sub     rsp, 40h
0x14000b14e  mov     r14, rdx
0x14000b151  mov     r12, rcx
0x14000b154  mov     dword ptr [rdx], 0
0x14000b15a  xor     r15d, r15d
0x14000b15d  mov     [rbp+hKey], r15
0x14000b161  lea     rax, [rbp+hKey]
0x14000b165  mov     [rsp+40h+phkResult], rax; unsigned int
0x14000b16a  mov     r9d, 20019h; samDesired
0x14000b170  xor     r8d, r8d; ulOptions
0x14000b173  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate\\Com"...
0x14000b17a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b181  call    cs:__imp_RegOpenKeyExW
0x14000b187  lea     ecx, [rax-2]
0x14000b18a  lea     rdi, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x14000b191  cmp     ecx, 1
0x14000b194  ja      loc_14000B289
0x14000b19a  mov     rcx, [rbp+hKey]; hKey
0x14000b19e  test    rcx, rcx
0x14000b1a1  jz      short loc_14000B1CD
0x14000b1a3  call    cs:__imp_RegCloseKey
0x14000b1a9  jmp     short loc_14000B1CD
0x14000b1ab  mov     r9d, eax; char *
0x14000b1ae  mov     r8, rdi; unsigned int
0x14000b1b1  mov     rcx, [rbp+38h]; this
0x14000b1b5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000b1ba  mov     ebx, eax
0x14000b1bc  lea     rcx, [rbp+hKey]
0x14000b1c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b1c5  test    ebx, ebx
0x14000b1c7  js      loc_14000B3D1
0x14000b1cd  xor     esi, esi
0x14000b1cf  mov     [rbp+hKey], rsi
0x14000b1d3  lea     rax, [rbp+hKey]
0x14000b1d7  mov     [rsp+40h+phkResult], rax; int
0x14000b1dc  mov     r9d, 20019h; samDesired
0x14000b1e2  xor     r8d, r8d; ulOptions
0x14000b1e5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate\\Com"...
0x14000b1ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b1f3  call    cs:__imp_RegOpenKeyExW
0x14000b1f9  lea     ecx, [rax-2]
0x14000b1fc  cmp     ecx, 1
0x14000b1ff  ja      loc_14000B2FD
0x14000b205  mov     rcx, [rbp+hKey]; hKey
0x14000b209  test    rcx, rcx
0x14000b20c  jz      short loc_14000B214
0x14000b20e  call    cs:__imp_RegCloseKey
0x14000b214  call    ?RemoveCommitStatusKey@UsoCommitHelper@@CAJXZ; UsoCommitHelper::RemoveCommitStatusKey(void)
0x14000b219  mov     ebx, eax
0x14000b21b  test    eax, eax
0x14000b21d  js      loc_14000B365
0x14000b223  xor     ebx, ebx
0x14000b225  lea     eax, [rbx+1]
0x14000b228  cmp     esi, eax
0x14000b22a  jz      loc_14000B3FD
0x14000b230  cmp     r15d, eax
0x14000b233  jz      loc_14000B407
0x14000b239  call    ?PersistRebootEndTime@UsoCommitHelper@@CAXXZ; UsoCommitHelper::PersistRebootEndTime(void)
0x14000b23e  mov     [r12], ebx
0x14000b242  xor     eax, eax
0x14000b244  jmp     short loc_14000B27A
0x14000b246  mov     r9d, eax; char *
0x14000b249  mov     r8, rdi; unsigned int
0x14000b24c  mov     rcx, [rbp+38h]; this
0x14000b250  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000b255  mov     ebx, eax
0x14000b257  lea     rcx, [rbp+hKey]
0x14000b25b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b260  test    ebx, ebx
0x14000b262  jns     short loc_14000B214
0x14000b264  mov     edx, 7Fh; void *
0x14000b269  mov     r8, rdi; unsigned int
0x14000b26c  mov     rcx, [rbp+38h]; this
0x14000b270  mov     r9d, ebx; char *
0x14000b273  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b278  mov     eax, ebx
0x14000b27a  add     rsp, 40h
0x14000b27e  pop     r15
0x14000b280  pop     r14
0x14000b282  pop     r12
0x14000b284  pop     rdi
0x14000b285  pop     rsi
0x14000b286  pop     rbx
0x14000b287  pop     rbp
0x14000b288  retn
0x14000b289  test    eax, eax
0x14000b28b  jnz     loc_14000B3AF
0x14000b291  mov     [rbp+arg_8], eax
0x14000b294  mov     [rbp+arg_10], 4
0x14000b29b  lea     rax, [rbp+arg_10]
0x14000b29f  mov     [rsp+40h+pcbData], rax; pcbData
0x14000b2a4  lea     rax, [rbp+arg_8]
0x14000b2a8  mov     [rsp+40h+pvData], rax; pvData
0x14000b2ad  mov     [rsp+40h+phkResult], 0; pdwType
0x14000b2b6  mov     r9d, 18h; dwFlags
0x14000b2bc  lea     r8, aNocommit; "NoCommit"
0x14000b2c3  xor     edx, edx; lpSubKey
0x14000b2c5  mov     rcx, [rbp+hKey]; hkey
0x14000b2c9  call    cs:__imp_RegGetValueW
0x14000b2cf  cmp     eax, 2
0x14000b2d2  jz      loc_14000B3B9
0x14000b2d8  test    eax, eax
0x14000b2da  jnz     loc_14000B3C7
0x14000b2e0  mov     r15d, [rbp+arg_8]
0x14000b2e4  mov     rdi, [rbp+hKey]
0x14000b2e8  test    rdi, rdi
0x14000b2eb  jnz     loc_14000B376
0x14000b2f1  lea     rdi, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x14000b2f8  jmp     loc_14000B1CD
0x14000b2fd  test    eax, eax
0x14000b2ff  jnz     loc_14000B3DB
0x14000b305  mov     [rbp+arg_8], eax
0x14000b308  mov     [rbp+arg_10], 4
0x14000b30f  lea     rax, [rbp+arg_10]
0x14000b313  mov     [rsp+40h+pcbData], rax; pcbData
0x14000b318  lea     rax, [rbp+arg_8]
0x14000b31c  mov     [rsp+40h+pvData], rax; pvData
0x14000b321  mov     [rsp+40h+phkResult], 0; pdwType
0x14000b32a  mov     r9d, 18h; dwFlags
0x14000b330  lea     r8, aUpdateandshutd; "UpdateAndShutdown"
0x14000b337  xor     edx, edx; lpSubKey
0x14000b339  mov     rcx, [rbp+hKey]; hkey
0x14000b33d  call    cs:__imp_RegGetValueW
0x14000b343  cmp     eax, 2
0x14000b346  jz      loc_14000B3E5
0x14000b34c  test    eax, eax
0x14000b34e  jnz     loc_14000B3F3
0x14000b354  mov     esi, [rbp+arg_8]
0x14000b357  mov     rdi, [rbp+hKey]
0x14000b35b  test    rdi, rdi
0x14000b35e  jnz     short loc_14000B394
0x14000b360  jmp     loc_14000B214
0x14000b365  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x14000b36c  mov     edx, 82h
0x14000b371  jmp     loc_14000B26C
0x14000b376  call    cs:__imp_GetLastError
0x14000b37c  mov     ebx, eax
0x14000b37e  mov     rcx, rdi; hKey
0x14000b381  call    cs:__imp_RegCloseKey
0x14000b387  mov     ecx, ebx; dwErrCode
0x14000b389  call    cs:__imp_SetLastError
0x14000b38f  jmp     loc_14000B2F1
0x14000b394  call    cs:__imp_GetLastError
0x14000b39a  mov     ebx, eax
0x14000b39c  mov     rcx, rdi; hKey
0x14000b39f  call    cs:__imp_RegCloseKey
0x14000b3a5  mov     ecx, ebx; dwErrCode
0x14000b3a7  call    cs:__imp_SetLastError
0x14000b3ad  jmp     short loc_14000B360
0x14000b3af  mov     edx, 10Ah; void *
0x14000b3b4  jmp     loc_14000B1AB
0x14000b3b9  lea     rcx, [rbp+hKey]
0x14000b3bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b3c2  jmp     loc_14000B1CD
0x14000b3c7  mov     edx, 11Ch
0x14000b3cc  jmp     loc_14000B1AB
0x14000b3d1  mov     edx, 7Ch ; '|'
0x14000b3d6  jmp     loc_14000B269
0x14000b3db  mov     edx, 10Ah; void *
0x14000b3e0  jmp     loc_14000B246
0x14000b3e5  lea     rcx, [rbp+hKey]
0x14000b3e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000b3ee  jmp     loc_14000B214
0x14000b3f3  mov     edx, 11Ch
0x14000b3f8  jmp     loc_14000B246
0x14000b3fd  mov     [r14], eax
0x14000b400  mov     ebx, eax
0x14000b402  jmp     loc_14000B230
0x14000b407  mov     dword ptr [r14], 2
0x14000b40e  jmp     loc_14000B239
```
