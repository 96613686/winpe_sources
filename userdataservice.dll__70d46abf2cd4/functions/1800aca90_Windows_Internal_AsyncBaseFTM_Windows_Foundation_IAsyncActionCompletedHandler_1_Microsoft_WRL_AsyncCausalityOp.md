# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GenericMakeAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800aca90`
- end: `0x1800acb98`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?GenericMakeAsyncName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800aca90`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800acb1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800acb1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800acaed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800acaed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acb5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acb65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acb5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acb65`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800acafd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800acafd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800acaca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800acaca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acb52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acb52`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GenericMakeAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800aca90  mov     [rsp-8+arg_0], rbx
0x1800aca95  push    rbp
0x1800aca96  mov     rbp, rsp
0x1800aca99  sub     rsp, 50h
0x1800aca9d  xor     edx, edx; pUnkOuter
0x1800aca9f  mov     [rbp+var_18], 0
0x1800acaa7  lea     rax, [rbp+var_18]
0x1800acaab  mov     [rbp+var_8], 0
0x1800acab3  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800acaba  mov     [rsp+50h+ppv], rax; ppv
0x1800acabf  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800acac6  lea     r8d, [rdx+1]; dwClsContext
0x1800acaca  call    cs:__imp_CoCreateInstance
0x1800acad0  test    eax, eax
0x1800acad2  js      short loc_1800ACAED
0x1800acad4  mov     rcx, [rbp+var_18]
0x1800acad8  lea     r8, [rbp+var_8]
0x1800acadc  mov     edx, 4
0x1800acae1  mov     rax, [rcx]
0x1800acae4  mov     rax, [rax+20h]
0x1800acae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acaed  call    cs:__imp_GetCurrentProcessId
0x1800acaf3  xor     edx, edx; bInheritHandle
0x1800acaf5  mov     ecx, 1000h; dwDesiredAccess
0x1800acafa  mov     r8d, eax; dwProcessId
0x1800acafd  call    cs:__imp_OpenProcess
0x1800acb03  mov     rbx, rax
0x1800acb06  test    rax, rax
0x1800acb09  jz      short loc_1800ACB6B
0x1800acb0b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800acb0f  mov     [rbp+TokenHandle], 0
0x1800acb17  mov     edx, 8; DesiredAccess
0x1800acb1c  mov     rcx, rax; ProcessHandle
0x1800acb1f  call    cs:__imp_OpenProcessToken
0x1800acb25  test    eax, eax
0x1800acb27  jz      short loc_1800ACB62
0x1800acb29  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800acb2d  lea     rax, [rbp+ReturnLength]
0x1800acb31  mov     r9d, 4; TokenInformationLength
0x1800acb37  mov     [rbp+ReturnLength], 0
0x1800acb3e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800acb42  mov     [rbp+TokenInformation], 0
0x1800acb49  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800acb4e  lea     edx, [r9+19h]; TokenInformationClass
0x1800acb52  call    cs:__imp_GetTokenInformation
0x1800acb58  mov     rcx, [rbp+TokenHandle]; hObject
0x1800acb5c  call    cs:__imp_CloseHandle
0x1800acb62  mov     rcx, rbx; hObject
0x1800acb65  call    cs:__imp_CloseHandle
0x1800acb6b  mov     rcx, [rbp+var_18]
0x1800acb6f  test    rcx, rcx
0x1800acb72  jz      short loc_1800ACB88
0x1800acb74  mov     [rbp+var_18], 0
0x1800acb7c  mov     rdx, [rcx]
0x1800acb7f  mov     rax, [rdx+10h]
0x1800acb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acb88  mov     rbx, [rsp+50h+arg_0]
0x1800acb8d  mov     eax, 1
0x1800acb92  add     rsp, 50h
0x1800acb96  pop     rbp
0x1800acb97  retn
```
