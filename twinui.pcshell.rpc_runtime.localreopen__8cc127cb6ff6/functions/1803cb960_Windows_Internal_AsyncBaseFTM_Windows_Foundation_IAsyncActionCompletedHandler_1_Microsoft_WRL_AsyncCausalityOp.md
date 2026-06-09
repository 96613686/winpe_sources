# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const c_gammaFlashAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1803cb960`
- end: `0x1803cba84`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?c_gammaFlashAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `292`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180356360`
- `0x1803cb960`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803cb9a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803cb9a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1803cb9cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1803cb9cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1803cb9fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1803cb9fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803cba3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803cba43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803cba3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803cba43`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803cb9db`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803cb9db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803cba30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1803cba30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const c_gammaFlashAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  LPVOID v6; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h] BYREF

  ppv = 0;
  v12 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v12);
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
0x1803cb960  mov     [rsp-8+arg_0], rbx
0x1803cb965  push    rbp
0x1803cb966  mov     rbp, rsp
0x1803cb969  sub     rsp, 60h
0x1803cb96d  mov     rax, cs:__security_cookie
0x1803cb974  xor     rax, rsp
0x1803cb977  mov     [rbp+var_10], rax
0x1803cb97b  mov     [rbp+var_28], 0
0x1803cb983  mov     [rbp+var_18], 0
0x1803cb98b  lea     rax, [rbp+var_28]
0x1803cb98f  mov     [rsp+60h+ppv], rax; ppv
0x1803cb994  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1803cb99b  xor     edx, edx; pUnkOuter
0x1803cb99d  lea     r8d, [rdx+1]; dwClsContext
0x1803cb9a1  lea     rcx, CLSID_GlobalOptions; rclsid
0x1803cb9a8  call    cs:__imp_CoCreateInstance
0x1803cb9ae  test    eax, eax
0x1803cb9b0  js      short loc_1803CB9CB
0x1803cb9b2  mov     rcx, [rbp+var_28]
0x1803cb9b6  mov     rax, [rcx]
0x1803cb9b9  lea     r8, [rbp+var_18]
0x1803cb9bd  mov     edx, 4
0x1803cb9c2  mov     rax, [rax+20h]
0x1803cb9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803cb9cb  call    cs:__imp_GetCurrentProcessId
0x1803cb9d1  mov     r8d, eax; dwProcessId
0x1803cb9d4  xor     edx, edx; bInheritHandle
0x1803cb9d6  mov     ecx, 1000h; dwDesiredAccess
0x1803cb9db  call    cs:__imp_OpenProcess
0x1803cb9e1  mov     rbx, rax
0x1803cb9e4  test    rax, rax
0x1803cb9e7  jz      short loc_1803CBA4A
0x1803cb9e9  mov     [rbp+TokenHandle], 0
0x1803cb9f1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1803cb9f5  mov     edx, 8; DesiredAccess
0x1803cb9fa  mov     rcx, rax; ProcessHandle
0x1803cb9fd  call    cs:__imp_OpenProcessToken
0x1803cba03  test    eax, eax
0x1803cba05  jz      short loc_1803CBA40
0x1803cba07  mov     [rbp+ReturnLength], 0
0x1803cba0e  mov     [rbp+TokenInformation], 0
0x1803cba15  lea     rax, [rbp+ReturnLength]
0x1803cba19  mov     [rsp+60h+ppv], rax; ReturnLength
0x1803cba1e  mov     r9d, 4; TokenInformationLength
0x1803cba24  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1803cba28  lea     edx, [r9+19h]; TokenInformationClass
0x1803cba2c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1803cba30  call    cs:__imp_GetTokenInformation
0x1803cba36  mov     rcx, [rbp+TokenHandle]; hObject
0x1803cba3a  call    cs:__imp_CloseHandle
0x1803cba40  mov     rcx, rbx; hObject
0x1803cba43  call    cs:__imp_CloseHandle
0x1803cba49  nop
0x1803cba4a  mov     rcx, [rbp+var_28]
0x1803cba4e  test    rcx, rcx
0x1803cba51  jz      short loc_1803CBA68
0x1803cba53  mov     [rbp+var_28], 0
0x1803cba5b  mov     rdx, [rcx]
0x1803cba5e  mov     rax, [rdx+10h]
0x1803cba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803cba67  nop
0x1803cba68  mov     eax, 1
0x1803cba6d  mov     rcx, [rbp+var_10]
0x1803cba71  xor     rcx, rsp; StackCookie
0x1803cba74  call    __security_check_cookie
0x1803cba79  mov     rbx, [rsp+60h+arg_0]
0x1803cba7e  add     rsp, 60h
0x1803cba82  pop     rbp
0x1803cba83  retn
```
