# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Internal::BackupRestore::SettingsProviders::IBackupSettingsProvider *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180069140`
- end: `0x180069275`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUIBackupSettingsProvider@SettingsProviders@BackupRestore@Internal@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `309`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180069140`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x1800691b9`
- `KERNEL32!OpenProcess` at `0x1800691b9`
- `KERNEL32!CloseHandle` at `0x18006922a`
- `KERNEL32!CloseHandle` at `0x180069239`
- `KERNEL32!CloseHandle` at `0x18006922a`
- `KERNEL32!CloseHandle` at `0x180069239`
- `KERNEL32!GetCurrentProcessId` at `0x1800691a3`
- `KERNEL32!GetCurrentProcessId` at `0x1800691a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006921a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006921a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800691e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800691e1`
- `ole32!CoCreateInstance` at `0x18006917a`
- `ole32!CoCreateInstance` at `0x18006917a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Internal::BackupRestore::SettingsProviders::IBackupSettingsProvider *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  LPVOID v6; // rcx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v11 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v11);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v4, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      CloseHandle(TokenHandle);
    }
    CloseHandle(v5);
  }
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 1;
}

```

## disassembly

```asm
0x180069140  mov     [rsp-8+arg_0], rbx
0x180069145  push    rbp
0x180069146  mov     rbp, rsp
0x180069149  sub     rsp, 50h
0x18006914d  mov     [rbp+var_18], 0
0x180069155  mov     [rbp+var_8], 0
0x18006915d  lea     rax, [rbp+var_18]
0x180069161  mov     [rsp+50h+ppv], rax; ppv
0x180069166  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18006916d  xor     edx, edx; pUnkOuter
0x18006916f  lea     r8d, [rdx+1]; dwClsContext
0x180069173  lea     rcx, CLSID_GlobalOptions; rclsid
0x18006917a  call    cs:__imp_CoCreateInstance
0x180069181  nop     dword ptr [rax+rax+00h]
0x180069186  test    eax, eax
0x180069188  js      short loc_1800691A3
0x18006918a  mov     rcx, [rbp+var_18]
0x18006918e  mov     rax, [rcx]
0x180069191  lea     r8, [rbp+var_8]
0x180069195  mov     edx, 4
0x18006919a  mov     rax, [rax+20h]
0x18006919e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691a3  call    cs:__imp_GetCurrentProcessId
0x1800691aa  nop     dword ptr [rax+rax+00h]
0x1800691af  mov     r8d, eax; dwProcessId
0x1800691b2  xor     edx, edx; bInheritHandle
0x1800691b4  mov     ecx, 1000h; dwDesiredAccess
0x1800691b9  call    cs:__imp_OpenProcess
0x1800691c0  nop     dword ptr [rax+rax+00h]
0x1800691c5  mov     rbx, rax
0x1800691c8  test    rax, rax
0x1800691cb  jz      short loc_180069246
0x1800691cd  mov     [rbp+TokenHandle], 0
0x1800691d5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800691d9  mov     edx, 8; DesiredAccess
0x1800691de  mov     rcx, rax; ProcessHandle
0x1800691e1  call    cs:__imp_OpenProcessToken
0x1800691e8  nop     dword ptr [rax+rax+00h]
0x1800691ed  test    eax, eax
0x1800691ef  jz      short loc_180069236
0x1800691f1  mov     [rbp+ReturnLength], 0
0x1800691f8  mov     [rbp+TokenInformation], 0
0x1800691ff  lea     rax, [rbp+ReturnLength]
0x180069203  mov     [rsp+50h+ppv], rax; ReturnLength
0x180069208  mov     r9d, 4; TokenInformationLength
0x18006920e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180069212  lea     edx, [r9+19h]; TokenInformationClass
0x180069216  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18006921a  call    cs:__imp_GetTokenInformation
0x180069221  nop     dword ptr [rax+rax+00h]
0x180069226  mov     rcx, [rbp+TokenHandle]; hObject
0x18006922a  call    cs:__imp_CloseHandle
0x180069231  nop     dword ptr [rax+rax+00h]
0x180069236  mov     rcx, rbx; hObject
0x180069239  call    cs:__imp_CloseHandle
0x180069240  nop     dword ptr [rax+rax+00h]
0x180069245  nop
0x180069246  mov     rcx, [rbp+var_18]
0x18006924a  test    rcx, rcx
0x18006924d  jz      short loc_180069264
0x18006924f  mov     [rbp+var_18], 0
0x180069257  mov     rdx, [rcx]
0x18006925a  mov     rax, [rdx+10h]
0x18006925e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069263  nop
0x180069264  mov     eax, 1
0x180069269  mov     rbx, [rsp+50h+arg_0]
0x18006926e  add     rsp, 50h
0x180069272  pop     rbp
0x180069273  retn
```
