# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const UserAuthenticationPreFetchAuthenticationTokenAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1801c8c70`
- end: `0x1801c8d7a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?UserAuthenticationPreFetchAuthenticationTokenAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1801c8c70`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801c8ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801c8ccd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801c8cff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801c8cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8d45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801c8caa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801c8caa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801c8d32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801c8d32`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801c8cdd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801c8cdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const UserAuthenticationPreFetchAuthenticationTokenAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1801c8c70  mov     [rsp-8+arg_0], rbx
0x1801c8c75  push    rbp
0x1801c8c76  mov     rbp, rsp
0x1801c8c79  sub     rsp, 50h
0x1801c8c7d  mov     [rbp+var_18], 0
0x1801c8c85  mov     [rbp+var_8], 0
0x1801c8c8d  lea     rax, [rbp+var_18]
0x1801c8c91  mov     [rsp+50h+ppv], rax; ppv
0x1801c8c96  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1801c8c9d  xor     edx, edx; pUnkOuter
0x1801c8c9f  lea     r8d, [rdx+1]; dwClsContext
0x1801c8ca3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1801c8caa  call    cs:__imp_CoCreateInstance
0x1801c8cb0  test    eax, eax
0x1801c8cb2  js      short loc_1801C8CCD
0x1801c8cb4  mov     rcx, [rbp+var_18]
0x1801c8cb8  mov     rax, [rcx]
0x1801c8cbb  lea     r8, [rbp+var_8]
0x1801c8cbf  mov     edx, 4
0x1801c8cc4  mov     rax, [rax+20h]
0x1801c8cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c8ccd  call    cs:__imp_GetCurrentProcessId
0x1801c8cd3  mov     r8d, eax; dwProcessId
0x1801c8cd6  xor     edx, edx; bInheritHandle
0x1801c8cd8  mov     ecx, 1000h; dwDesiredAccess
0x1801c8cdd  call    cs:__imp_OpenProcess
0x1801c8ce3  mov     rbx, rax
0x1801c8ce6  test    rax, rax
0x1801c8ce9  jz      short loc_1801C8D4C
0x1801c8ceb  mov     [rbp+TokenHandle], 0
0x1801c8cf3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801c8cf7  mov     edx, 8; DesiredAccess
0x1801c8cfc  mov     rcx, rax; ProcessHandle
0x1801c8cff  call    cs:__imp_OpenProcessToken
0x1801c8d05  test    eax, eax
0x1801c8d07  jz      short loc_1801C8D42
0x1801c8d09  mov     [rbp+ReturnLength], 0
0x1801c8d10  mov     [rbp+TokenInformation], 0
0x1801c8d17  lea     rax, [rbp+ReturnLength]
0x1801c8d1b  mov     [rsp+50h+ppv], rax; ReturnLength
0x1801c8d20  mov     r9d, 4; TokenInformationLength
0x1801c8d26  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1801c8d2a  lea     edx, [r9+19h]; TokenInformationClass
0x1801c8d2e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801c8d32  call    cs:__imp_GetTokenInformation
0x1801c8d38  mov     rcx, [rbp+TokenHandle]; hObject
0x1801c8d3c  call    cs:__imp_CloseHandle
0x1801c8d42  mov     rcx, rbx; hObject
0x1801c8d45  call    cs:__imp_CloseHandle
0x1801c8d4b  nop
0x1801c8d4c  mov     rcx, [rbp+var_18]
0x1801c8d50  test    rcx, rcx
0x1801c8d53  jz      short loc_1801C8D6A
0x1801c8d55  mov     [rbp+var_18], 0
0x1801c8d5d  mov     rdx, [rcx]
0x1801c8d60  mov     rax, [rdx+10h]
0x1801c8d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c8d69  nop
0x1801c8d6a  mov     eax, 1
0x1801c8d6f  mov     rbx, [rsp+50h+arg_0]
0x1801c8d74  add     rsp, 50h
0x1801c8d78  pop     rbp
0x1801c8d79  retn
```
