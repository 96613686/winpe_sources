# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180076220`
- end: `0x180076353`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `307`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180076220`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800762c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800762c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076283`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180076299`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180076299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007630a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007630a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076319`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800762fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800762fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007625a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007625a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180076220  mov     [rsp-8+arg_0], rbx
0x180076225  push    rbp
0x180076226  mov     rbp, rsp
0x180076229  sub     rsp, 50h
0x18007622d  xor     edx, edx; pUnkOuter
0x18007622f  mov     [rbp+var_18], 0
0x180076237  lea     rax, [rbp+var_18]
0x18007623b  mov     [rbp+var_8], 0
0x180076243  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007624a  mov     [rsp+50h+ppv], rax; ppv
0x18007624f  lea     rcx, CLSID_GlobalOptions; rclsid
0x180076256  lea     r8d, [rdx+1]; dwClsContext
0x18007625a  call    cs:__imp_CoCreateInstance
0x180076261  nop     dword ptr [rax+rax+00h]
0x180076266  test    eax, eax
0x180076268  js      short loc_180076283
0x18007626a  mov     rcx, [rbp+var_18]
0x18007626e  lea     r8, [rbp+var_8]
0x180076272  mov     edx, 4
0x180076277  mov     rax, [rcx]
0x18007627a  mov     rax, [rax+20h]
0x18007627e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076283  call    cs:__imp_GetCurrentProcessId
0x18007628a  nop     dword ptr [rax+rax+00h]
0x18007628f  xor     edx, edx; bInheritHandle
0x180076291  mov     ecx, 1000h; dwDesiredAccess
0x180076296  mov     r8d, eax; dwProcessId
0x180076299  call    cs:__imp_OpenProcess
0x1800762a0  nop     dword ptr [rax+rax+00h]
0x1800762a5  mov     rbx, rax
0x1800762a8  test    rax, rax
0x1800762ab  jz      short loc_180076325
0x1800762ad  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800762b1  mov     [rbp+TokenHandle], 0
0x1800762b9  mov     edx, 8; DesiredAccess
0x1800762be  mov     rcx, rax; ProcessHandle
0x1800762c1  call    cs:__imp_OpenProcessToken
0x1800762c8  nop     dword ptr [rax+rax+00h]
0x1800762cd  test    eax, eax
0x1800762cf  jz      short loc_180076316
0x1800762d1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800762d5  lea     rax, [rbp+ReturnLength]
0x1800762d9  mov     r9d, 4; TokenInformationLength
0x1800762df  mov     [rbp+ReturnLength], 0
0x1800762e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800762ea  mov     [rbp+TokenInformation], 0
0x1800762f1  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800762f6  lea     edx, [r9+19h]; TokenInformationClass
0x1800762fa  call    cs:__imp_GetTokenInformation
0x180076301  nop     dword ptr [rax+rax+00h]
0x180076306  mov     rcx, [rbp+TokenHandle]; hObject
0x18007630a  call    cs:__imp_CloseHandle
0x180076311  nop     dword ptr [rax+rax+00h]
0x180076316  mov     rcx, rbx; hObject
0x180076319  call    cs:__imp_CloseHandle
0x180076320  nop     dword ptr [rax+rax+00h]
0x180076325  mov     rcx, [rbp+var_18]
0x180076329  test    rcx, rcx
0x18007632c  jz      short loc_180076342
0x18007632e  mov     [rbp+var_18], 0
0x180076336  mov     rdx, [rcx]
0x180076339  mov     rax, [rdx+10h]
0x18007633d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076342  mov     rbx, [rsp+50h+arg_0]
0x180076347  mov     eax, 1
0x18007634c  add     rsp, 50h
0x180076350  pop     rbp
0x180076351  retn
```
