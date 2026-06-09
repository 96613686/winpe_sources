# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18004e590`
- end: `0x18004e69a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004e590`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004e61f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004e61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e5ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e5ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e665`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e652`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e652`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004e5fd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004e5fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e5ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e5ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18004e590  mov     [rsp-8+arg_0], rbx
0x18004e595  push    rbp
0x18004e596  mov     rbp, rsp
0x18004e599  sub     rsp, 50h
0x18004e59d  mov     [rbp+var_18], 0
0x18004e5a5  mov     [rbp+var_8], 0
0x18004e5ad  lea     rax, [rbp+var_18]
0x18004e5b1  mov     [rsp+50h+ppv], rax; ppv
0x18004e5b6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004e5bd  xor     edx, edx; pUnkOuter
0x18004e5bf  lea     r8d, [rdx+1]; dwClsContext
0x18004e5c3  lea     rcx, CLSID_GlobalOptions; rclsid
0x18004e5ca  call    cs:__imp_CoCreateInstance
0x18004e5d0  test    eax, eax
0x18004e5d2  js      short loc_18004E5ED
0x18004e5d4  mov     rcx, [rbp+var_18]
0x18004e5d8  mov     rax, [rcx]
0x18004e5db  lea     r8, [rbp+var_8]
0x18004e5df  mov     edx, 4
0x18004e5e4  mov     rax, [rax+20h]
0x18004e5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5ed  call    cs:__imp_GetCurrentProcessId
0x18004e5f3  mov     r8d, eax; dwProcessId
0x18004e5f6  xor     edx, edx; bInheritHandle
0x18004e5f8  mov     ecx, 1000h; dwDesiredAccess
0x18004e5fd  call    cs:__imp_OpenProcess
0x18004e603  mov     rbx, rax
0x18004e606  test    rax, rax
0x18004e609  jz      short loc_18004E66C
0x18004e60b  mov     [rbp+TokenHandle], 0
0x18004e613  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004e617  mov     edx, 8; DesiredAccess
0x18004e61c  mov     rcx, rax; ProcessHandle
0x18004e61f  call    cs:__imp_OpenProcessToken
0x18004e625  test    eax, eax
0x18004e627  jz      short loc_18004E662
0x18004e629  mov     [rbp+ReturnLength], 0
0x18004e630  mov     [rbp+TokenInformation], 0
0x18004e637  lea     rax, [rbp+ReturnLength]
0x18004e63b  mov     [rsp+50h+ppv], rax; ReturnLength
0x18004e640  mov     r9d, 4; TokenInformationLength
0x18004e646  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004e64a  lea     edx, [r9+19h]; TokenInformationClass
0x18004e64e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004e652  call    cs:__imp_GetTokenInformation
0x18004e658  mov     rcx, [rbp+TokenHandle]; hObject
0x18004e65c  call    cs:__imp_CloseHandle
0x18004e662  mov     rcx, rbx; hObject
0x18004e665  call    cs:__imp_CloseHandle
0x18004e66b  nop
0x18004e66c  mov     rcx, [rbp+var_18]
0x18004e670  test    rcx, rcx
0x18004e673  jz      short loc_18004E68A
0x18004e675  mov     [rbp+var_18], 0
0x18004e67d  mov     rdx, [rcx]
0x18004e680  mov     rax, [rdx+10h]
0x18004e684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e689  nop
0x18004e68a  mov     eax, 1
0x18004e68f  mov     rbx, [rsp+50h+arg_0]
0x18004e694  add     rsp, 50h
0x18004e698  pop     rbp
0x18004e699  retn
```
