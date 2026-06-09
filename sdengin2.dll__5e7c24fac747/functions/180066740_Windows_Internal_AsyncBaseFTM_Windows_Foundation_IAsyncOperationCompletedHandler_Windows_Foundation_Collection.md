# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<Windows::Internal::BackupRestore::SettingsProviders::IBackupSettingsProvider *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180066740`
- end: `0x18006684a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUIBackupSettingsProvider@SettingsProviders@BackupRestore@Internal@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180066740`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x1800667ad`
- `KERNEL32!OpenProcess` at `0x1800667ad`
- `KERNEL32!CloseHandle` at `0x18006680c`
- `KERNEL32!CloseHandle` at `0x180066815`
- `KERNEL32!CloseHandle` at `0x18006680c`
- `KERNEL32!CloseHandle` at `0x180066815`
- `KERNEL32!GetCurrentProcessId` at `0x18006679d`
- `KERNEL32!GetCurrentProcessId` at `0x18006679d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066802`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066802`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800667cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800667cf`
- `ole32!CoCreateInstance` at `0x18006677a`
- `ole32!CoCreateInstance` at `0x18006677a`

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
0x180066740  mov     [rsp-8+arg_0], rbx
0x180066745  push    rbp
0x180066746  mov     rbp, rsp
0x180066749  sub     rsp, 50h
0x18006674d  mov     [rbp+var_18], 0
0x180066755  mov     [rbp+var_8], 0
0x18006675d  lea     rax, [rbp+var_18]
0x180066761  mov     [rsp+50h+ppv], rax; ppv
0x180066766  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18006676d  xor     edx, edx; pUnkOuter
0x18006676f  lea     r8d, [rdx+1]; dwClsContext
0x180066773  lea     rcx, CLSID_GlobalOptions; rclsid
0x18006677a  call    cs:__imp_CoCreateInstance
0x180066780  test    eax, eax
0x180066782  js      short loc_18006679D
0x180066784  mov     rcx, [rbp+var_18]
0x180066788  mov     rax, [rcx]
0x18006678b  lea     r8, [rbp+var_8]
0x18006678f  mov     edx, 4
0x180066794  mov     rax, [rax+20h]
0x180066798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006679d  call    cs:__imp_GetCurrentProcessId
0x1800667a3  mov     r8d, eax; dwProcessId
0x1800667a6  xor     edx, edx; bInheritHandle
0x1800667a8  mov     ecx, 1000h; dwDesiredAccess
0x1800667ad  call    cs:__imp_OpenProcess
0x1800667b3  mov     rbx, rax
0x1800667b6  test    rax, rax
0x1800667b9  jz      short loc_18006681C
0x1800667bb  mov     [rbp+TokenHandle], 0
0x1800667c3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800667c7  mov     edx, 8; DesiredAccess
0x1800667cc  mov     rcx, rax; ProcessHandle
0x1800667cf  call    cs:__imp_OpenProcessToken
0x1800667d5  test    eax, eax
0x1800667d7  jz      short loc_180066812
0x1800667d9  mov     [rbp+ReturnLength], 0
0x1800667e0  mov     [rbp+TokenInformation], 0
0x1800667e7  lea     rax, [rbp+ReturnLength]
0x1800667eb  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800667f0  mov     r9d, 4; TokenInformationLength
0x1800667f6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800667fa  lea     edx, [r9+19h]; TokenInformationClass
0x1800667fe  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180066802  call    cs:__imp_GetTokenInformation
0x180066808  mov     rcx, [rbp+TokenHandle]; hObject
0x18006680c  call    cs:__imp_CloseHandle
0x180066812  mov     rcx, rbx; hObject
0x180066815  call    cs:__imp_CloseHandle
0x18006681b  nop
0x18006681c  mov     rcx, [rbp+var_18]
0x180066820  test    rcx, rcx
0x180066823  jz      short loc_18006683A
0x180066825  mov     [rbp+var_18], 0
0x18006682d  mov     rdx, [rcx]
0x180066830  mov     rax, [rdx+10h]
0x180066834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066839  nop
0x18006683a  mov     eax, 1
0x18006683f  mov     rbx, [rsp+50h+arg_0]
0x180066844  add     rsp, 50h
0x180066848  pop     rbp
0x180066849  retn
```
