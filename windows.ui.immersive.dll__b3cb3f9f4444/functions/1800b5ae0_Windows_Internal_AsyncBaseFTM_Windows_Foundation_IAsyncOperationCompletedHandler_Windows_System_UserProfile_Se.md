# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::UserProfile::SetAccountPictureResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800b5ae0`
- end: `0x1800b5c14`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4SetAccountPictureResult@UserProfile@System@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `308`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800b5ae0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b5b81`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b5b81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b5b43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b5b43`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b5b59`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b5b59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5bd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5bca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5bd9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b5bba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b5bba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5b1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5b1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::UserProfile::SetAccountPictureResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800b5ae0  mov     [rsp-8+arg_0], rbx
0x1800b5ae5  push    rbp
0x1800b5ae6  mov     rbp, rsp
0x1800b5ae9  sub     rsp, 50h
0x1800b5aed  mov     [rbp+var_18], 0
0x1800b5af5  mov     [rbp+var_8], 0
0x1800b5afd  lea     rax, [rbp+var_18]
0x1800b5b01  mov     [rsp+50h+ppv], rax; ppv
0x1800b5b06  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800b5b0d  xor     edx, edx; pUnkOuter
0x1800b5b0f  lea     r8d, [rdx+1]; dwClsContext
0x1800b5b13  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800b5b1a  call    cs:__imp_CoCreateInstance
0x1800b5b21  nop     dword ptr [rax+rax+00h]
0x1800b5b26  test    eax, eax
0x1800b5b28  js      short loc_1800B5B43
0x1800b5b2a  mov     rcx, [rbp+var_18]
0x1800b5b2e  mov     rax, [rcx]
0x1800b5b31  lea     r8, [rbp+var_8]
0x1800b5b35  mov     edx, 4
0x1800b5b3a  mov     rax, [rax+20h]
0x1800b5b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5b43  call    cs:__imp_GetCurrentProcessId
0x1800b5b4a  nop     dword ptr [rax+rax+00h]
0x1800b5b4f  mov     r8d, eax; dwProcessId
0x1800b5b52  xor     edx, edx; bInheritHandle
0x1800b5b54  mov     ecx, 1000h; dwDesiredAccess
0x1800b5b59  call    cs:__imp_OpenProcess
0x1800b5b60  nop     dword ptr [rax+rax+00h]
0x1800b5b65  mov     rbx, rax
0x1800b5b68  test    rax, rax
0x1800b5b6b  jz      short loc_1800B5BE6
0x1800b5b6d  mov     [rbp+TokenHandle], 0
0x1800b5b75  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800b5b79  mov     edx, 8; DesiredAccess
0x1800b5b7e  mov     rcx, rax; ProcessHandle
0x1800b5b81  call    cs:__imp_OpenProcessToken
0x1800b5b88  nop     dword ptr [rax+rax+00h]
0x1800b5b8d  test    eax, eax
0x1800b5b8f  jz      short loc_1800B5BD6
0x1800b5b91  mov     [rbp+ReturnLength], 0
0x1800b5b98  mov     [rbp+TokenInformation], 0
0x1800b5b9f  lea     rax, [rbp+ReturnLength]
0x1800b5ba3  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800b5ba8  mov     r9d, 4; TokenInformationLength
0x1800b5bae  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800b5bb2  lea     edx, [r9+19h]; TokenInformationClass
0x1800b5bb6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800b5bba  call    cs:__imp_GetTokenInformation
0x1800b5bc1  nop     dword ptr [rax+rax+00h]
0x1800b5bc6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800b5bca  call    cs:__imp_CloseHandle
0x1800b5bd1  nop     dword ptr [rax+rax+00h]
0x1800b5bd6  mov     rcx, rbx; hObject
0x1800b5bd9  call    cs:__imp_CloseHandle
0x1800b5be0  nop     dword ptr [rax+rax+00h]
0x1800b5be5  nop
0x1800b5be6  mov     rcx, [rbp+var_18]
0x1800b5bea  test    rcx, rcx
0x1800b5bed  jz      short loc_1800B5C03
0x1800b5bef  mov     [rbp+var_18], 0
0x1800b5bf7  mov     rdx, [rcx]
0x1800b5bfa  mov     rax, [rdx+10h]
0x1800b5bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5c03  mov     eax, 1
0x1800b5c08  mov     rbx, [rsp+50h+arg_0]
0x1800b5c0d  add     rsp, 50h
0x1800b5c11  pop     rbp
0x1800b5c12  retn
```
