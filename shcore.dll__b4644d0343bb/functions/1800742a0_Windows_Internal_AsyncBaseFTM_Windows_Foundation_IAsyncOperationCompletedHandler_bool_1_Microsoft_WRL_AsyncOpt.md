# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800742a0`
- end: `0x1800743aa`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800742a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800742fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800742fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007432f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007432f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007436c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007436c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074375`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074362`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074362`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007430d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007430d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800742da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800742da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800742a0  mov     [rsp-8+arg_0], rbx
0x1800742a5  push    rbp
0x1800742a6  mov     rbp, rsp
0x1800742a9  sub     rsp, 50h
0x1800742ad  mov     [rbp+var_18], 0
0x1800742b5  mov     [rbp+var_8], 0
0x1800742bd  lea     rax, [rbp+var_18]
0x1800742c1  mov     [rsp+50h+ppv], rax; ppv
0x1800742c6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800742cd  xor     edx, edx; pUnkOuter
0x1800742cf  lea     r8d, [rdx+1]; dwClsContext
0x1800742d3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800742da  call    cs:__imp_CoCreateInstance
0x1800742e0  test    eax, eax
0x1800742e2  js      short loc_1800742FD
0x1800742e4  mov     rcx, [rbp+var_18]
0x1800742e8  mov     rax, [rcx]
0x1800742eb  lea     r8, [rbp+var_8]
0x1800742ef  mov     edx, 4
0x1800742f4  mov     rax, [rax+20h]
0x1800742f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742fd  call    cs:__imp_GetCurrentProcessId
0x180074303  mov     r8d, eax; dwProcessId
0x180074306  xor     edx, edx; bInheritHandle
0x180074308  mov     ecx, 1000h; dwDesiredAccess
0x18007430d  call    cs:__imp_OpenProcess
0x180074313  mov     rbx, rax
0x180074316  test    rax, rax
0x180074319  jz      short loc_18007437C
0x18007431b  mov     [rbp+TokenHandle], 0
0x180074323  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180074327  mov     edx, 8; DesiredAccess
0x18007432c  mov     rcx, rax; ProcessHandle
0x18007432f  call    cs:__imp_OpenProcessToken
0x180074335  test    eax, eax
0x180074337  jz      short loc_180074372
0x180074339  mov     [rbp+ReturnLength], 0
0x180074340  mov     [rbp+TokenInformation], 0
0x180074347  lea     rax, [rbp+ReturnLength]
0x18007434b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180074350  mov     r9d, 4; TokenInformationLength
0x180074356  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007435a  lea     edx, [r9+19h]; TokenInformationClass
0x18007435e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180074362  call    cs:__imp_GetTokenInformation
0x180074368  mov     rcx, [rbp+TokenHandle]; hObject
0x18007436c  call    cs:__imp_CloseHandle
0x180074372  mov     rcx, rbx; hObject
0x180074375  call    cs:__imp_CloseHandle
0x18007437b  nop
0x18007437c  mov     rcx, [rbp+var_18]
0x180074380  test    rcx, rcx
0x180074383  jz      short loc_18007439A
0x180074385  mov     [rbp+var_18], 0
0x18007438d  mov     rdx, [rcx]
0x180074390  mov     rax, [rdx+10h]
0x180074394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074399  nop
0x18007439a  mov     eax, 1
0x18007439f  mov     rbx, [rsp+50h+arg_0]
0x1800743a4  add     rsp, 50h
0x1800743a8  pop     rbp
0x1800743a9  retn
```
