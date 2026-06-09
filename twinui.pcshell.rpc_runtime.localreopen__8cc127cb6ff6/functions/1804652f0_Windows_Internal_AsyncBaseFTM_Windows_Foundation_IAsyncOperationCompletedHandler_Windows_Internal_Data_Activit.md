# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Data::Activities::GetCurrentActivityForViewOperationResults *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1804652f0`
- end: `0x1804653fa`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVGetCurrentActivityForViewOperationResults@Activities@Data@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1804652f0`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18046532a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18046532a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18046534d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18046534d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18046537f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18046537f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804653bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804653c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804653bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804653c5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18046535d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18046535d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1804653b2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1804653b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Data::Activities::GetCurrentActivityForViewOperationResults *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1804652f0  mov     [rsp-8+arg_0], rbx
0x1804652f5  push    rbp
0x1804652f6  mov     rbp, rsp
0x1804652f9  sub     rsp, 50h
0x1804652fd  mov     [rbp+var_18], 0
0x180465305  mov     [rbp+var_8], 0
0x18046530d  lea     rax, [rbp+var_18]
0x180465311  mov     [rsp+50h+ppv], rax; ppv
0x180465316  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18046531d  xor     edx, edx; pUnkOuter
0x18046531f  lea     r8d, [rdx+1]; dwClsContext
0x180465323  lea     rcx, CLSID_GlobalOptions; rclsid
0x18046532a  call    cs:__imp_CoCreateInstance
0x180465330  test    eax, eax
0x180465332  js      short loc_18046534D
0x180465334  mov     rcx, [rbp+var_18]
0x180465338  mov     rax, [rcx]
0x18046533b  lea     r8, [rbp+var_8]
0x18046533f  mov     edx, 4
0x180465344  mov     rax, [rax+20h]
0x180465348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18046534d  call    cs:__imp_GetCurrentProcessId
0x180465353  mov     r8d, eax; dwProcessId
0x180465356  xor     edx, edx; bInheritHandle
0x180465358  mov     ecx, 1000h; dwDesiredAccess
0x18046535d  call    cs:__imp_OpenProcess
0x180465363  mov     rbx, rax
0x180465366  test    rax, rax
0x180465369  jz      short loc_1804653CC
0x18046536b  mov     [rbp+TokenHandle], 0
0x180465373  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180465377  mov     edx, 8; DesiredAccess
0x18046537c  mov     rcx, rax; ProcessHandle
0x18046537f  call    cs:__imp_OpenProcessToken
0x180465385  test    eax, eax
0x180465387  jz      short loc_1804653C2
0x180465389  mov     [rbp+ReturnLength], 0
0x180465390  mov     [rbp+TokenInformation], 0
0x180465397  lea     rax, [rbp+ReturnLength]
0x18046539b  mov     [rsp+50h+ppv], rax; ReturnLength
0x1804653a0  mov     r9d, 4; TokenInformationLength
0x1804653a6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1804653aa  lea     edx, [r9+19h]; TokenInformationClass
0x1804653ae  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1804653b2  call    cs:__imp_GetTokenInformation
0x1804653b8  mov     rcx, [rbp+TokenHandle]; hObject
0x1804653bc  call    cs:__imp_CloseHandle
0x1804653c2  mov     rcx, rbx; hObject
0x1804653c5  call    cs:__imp_CloseHandle
0x1804653cb  nop
0x1804653cc  mov     rcx, [rbp+var_18]
0x1804653d0  test    rcx, rcx
0x1804653d3  jz      short loc_1804653EA
0x1804653d5  mov     [rbp+var_18], 0
0x1804653dd  mov     rdx, [rcx]
0x1804653e0  mov     rax, [rdx+10h]
0x1804653e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804653e9  nop
0x1804653ea  mov     eax, 1
0x1804653ef  mov     rbx, [rsp+50h+arg_0]
0x1804653f4  add     rsp, 50h
0x1804653f8  pop     rbp
0x1804653f9  retn
```
