# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180020e90`
- end: `0x180020f9a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180020e90`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020eed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020f1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020f1f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020f52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020f52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020eca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020eca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180020efd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180020efd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f65`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180020e90  mov     [rsp-8+arg_0], rbx
0x180020e95  push    rbp
0x180020e96  mov     rbp, rsp
0x180020e99  sub     rsp, 50h
0x180020e9d  mov     [rbp+var_18], 0
0x180020ea5  mov     [rbp+var_8], 0
0x180020ead  lea     rax, [rbp+var_18]
0x180020eb1  mov     [rsp+50h+ppv], rax; ppv
0x180020eb6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180020ebd  xor     edx, edx; pUnkOuter
0x180020ebf  lea     r8d, [rdx+1]; dwClsContext
0x180020ec3  lea     rcx, CLSID_GlobalOptions; rclsid
0x180020eca  call    cs:__imp_CoCreateInstance
0x180020ed0  test    eax, eax
0x180020ed2  js      short loc_180020EED
0x180020ed4  mov     rcx, [rbp+var_18]
0x180020ed8  mov     rax, [rcx]
0x180020edb  lea     r8, [rbp+var_8]
0x180020edf  mov     edx, 4
0x180020ee4  mov     rax, [rax+20h]
0x180020ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eed  call    cs:__imp_GetCurrentProcessId
0x180020ef3  mov     r8d, eax; dwProcessId
0x180020ef6  xor     edx, edx; bInheritHandle
0x180020ef8  mov     ecx, 1000h; dwDesiredAccess
0x180020efd  call    cs:__imp_OpenProcess
0x180020f03  mov     rbx, rax
0x180020f06  test    rax, rax
0x180020f09  jz      short loc_180020F6C
0x180020f0b  mov     [rbp+TokenHandle], 0
0x180020f13  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180020f17  mov     edx, 8; DesiredAccess
0x180020f1c  mov     rcx, rax; ProcessHandle
0x180020f1f  call    cs:__imp_OpenProcessToken
0x180020f25  test    eax, eax
0x180020f27  jz      short loc_180020F62
0x180020f29  mov     [rbp+ReturnLength], 0
0x180020f30  mov     [rbp+TokenInformation], 0
0x180020f37  lea     rax, [rbp+ReturnLength]
0x180020f3b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180020f40  mov     r9d, 4; TokenInformationLength
0x180020f46  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180020f4a  lea     edx, [r9+19h]; TokenInformationClass
0x180020f4e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180020f52  call    cs:__imp_GetTokenInformation
0x180020f58  mov     rcx, [rbp+TokenHandle]; hObject
0x180020f5c  call    cs:__imp_CloseHandle
0x180020f62  mov     rcx, rbx; hObject
0x180020f65  call    cs:__imp_CloseHandle
0x180020f6b  nop
0x180020f6c  mov     rcx, [rbp+var_18]
0x180020f70  test    rcx, rcx
0x180020f73  jz      short loc_180020F8A
0x180020f75  mov     [rbp+var_18], 0
0x180020f7d  mov     rdx, [rcx]
0x180020f80  mov     rax, [rdx+10h]
0x180020f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f89  nop
0x180020f8a  mov     eax, 1
0x180020f8f  mov     rbx, [rsp+50h+arg_0]
0x180020f94  add     rsp, 50h
0x180020f98  pop     rbp
0x180020f99  retn
```
