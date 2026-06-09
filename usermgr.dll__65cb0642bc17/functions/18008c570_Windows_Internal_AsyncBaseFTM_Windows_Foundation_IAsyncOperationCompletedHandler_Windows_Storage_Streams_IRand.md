# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18008c570`
- end: `0x18008c665`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `245`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ce48`
- `0x18008c570`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c5aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c5aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008c632`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008c632`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008c5cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008c5cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008c5ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008c5ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c645`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008c5dd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008c5dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v10 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v10);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x18008c570  mov     [rsp-8+arg_0], rbx
0x18008c575  push    rbp
0x18008c576  mov     rbp, rsp
0x18008c579  sub     rsp, 50h
0x18008c57d  mov     [rbp+var_10], 0
0x18008c585  mov     [rbp+var_8], 0
0x18008c58d  lea     rax, [rbp+var_10]
0x18008c591  mov     [rsp+50h+ppv], rax; ppv
0x18008c596  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18008c59d  xor     edx, edx; pUnkOuter
0x18008c59f  lea     r8d, [rdx+1]; dwClsContext
0x18008c5a3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18008c5aa  call    cs:__imp_CoCreateInstance
0x18008c5b0  test    eax, eax
0x18008c5b2  js      short loc_18008C5CD
0x18008c5b4  mov     rcx, [rbp+var_10]
0x18008c5b8  mov     rax, [rcx]
0x18008c5bb  lea     r8, [rbp+var_8]
0x18008c5bf  mov     edx, 4
0x18008c5c4  mov     rax, [rax+20h]
0x18008c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c5cd  call    cs:__imp_GetCurrentProcessId
0x18008c5d3  mov     r8d, eax; dwProcessId
0x18008c5d6  xor     edx, edx; bInheritHandle
0x18008c5d8  mov     ecx, 1000h; dwDesiredAccess
0x18008c5dd  call    cs:__imp_OpenProcess
0x18008c5e3  mov     rbx, rax
0x18008c5e6  test    rax, rax
0x18008c5e9  jz      short loc_18008C64C
0x18008c5eb  mov     [rbp+TokenHandle], 0
0x18008c5f3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18008c5f7  mov     edx, 8; DesiredAccess
0x18008c5fc  mov     rcx, rax; ProcessHandle
0x18008c5ff  call    cs:__imp_OpenProcessToken
0x18008c605  test    eax, eax
0x18008c607  jz      short loc_18008C642
0x18008c609  mov     [rbp+ReturnLength], 0
0x18008c610  mov     [rbp+TokenInformation], 0
0x18008c617  lea     rax, [rbp+ReturnLength]
0x18008c61b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18008c620  mov     r9d, 4; TokenInformationLength
0x18008c626  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18008c62a  lea     edx, [r9+19h]; TokenInformationClass
0x18008c62e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18008c632  call    cs:__imp_GetTokenInformation
0x18008c638  mov     rcx, [rbp+TokenHandle]; hObject
0x18008c63c  call    cs:__imp_CloseHandle
0x18008c642  mov     rcx, rbx; hObject
0x18008c645  call    cs:__imp_CloseHandle
0x18008c64b  nop
0x18008c64c  lea     rcx, [rbp+var_10]
0x18008c650  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008c655  mov     eax, 1
0x18008c65a  mov     rbx, [rsp+50h+arg_0]
0x18008c65f  add     rsp, 50h
0x18008c663  pop     rbp
0x18008c664  retn
```
