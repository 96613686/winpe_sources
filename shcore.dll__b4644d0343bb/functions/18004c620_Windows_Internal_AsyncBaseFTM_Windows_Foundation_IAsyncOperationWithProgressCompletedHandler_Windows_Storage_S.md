# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18004c620`
- end: `0x18004c72a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004c620`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c67d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004c67d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004c6af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004c6af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c6ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c6ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c6f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c6e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c6e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004c68d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004c68d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c65a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c65a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18004c620  mov     [rsp-8+arg_0], rbx
0x18004c625  push    rbp
0x18004c626  mov     rbp, rsp
0x18004c629  sub     rsp, 50h
0x18004c62d  mov     [rbp+var_18], 0
0x18004c635  mov     [rbp+var_8], 0
0x18004c63d  lea     rax, [rbp+var_18]
0x18004c641  mov     [rsp+50h+ppv], rax; ppv
0x18004c646  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004c64d  xor     edx, edx; pUnkOuter
0x18004c64f  lea     r8d, [rdx+1]; dwClsContext
0x18004c653  lea     rcx, CLSID_GlobalOptions; rclsid
0x18004c65a  call    cs:__imp_CoCreateInstance
0x18004c660  test    eax, eax
0x18004c662  js      short loc_18004C67D
0x18004c664  mov     rcx, [rbp+var_18]
0x18004c668  mov     rax, [rcx]
0x18004c66b  lea     r8, [rbp+var_8]
0x18004c66f  mov     edx, 4
0x18004c674  mov     rax, [rax+20h]
0x18004c678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c67d  call    cs:__imp_GetCurrentProcessId
0x18004c683  mov     r8d, eax; dwProcessId
0x18004c686  xor     edx, edx; bInheritHandle
0x18004c688  mov     ecx, 1000h; dwDesiredAccess
0x18004c68d  call    cs:__imp_OpenProcess
0x18004c693  mov     rbx, rax
0x18004c696  test    rax, rax
0x18004c699  jz      short loc_18004C6FC
0x18004c69b  mov     [rbp+TokenHandle], 0
0x18004c6a3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004c6a7  mov     edx, 8; DesiredAccess
0x18004c6ac  mov     rcx, rax; ProcessHandle
0x18004c6af  call    cs:__imp_OpenProcessToken
0x18004c6b5  test    eax, eax
0x18004c6b7  jz      short loc_18004C6F2
0x18004c6b9  mov     [rbp+ReturnLength], 0
0x18004c6c0  mov     [rbp+TokenInformation], 0
0x18004c6c7  lea     rax, [rbp+ReturnLength]
0x18004c6cb  mov     [rsp+50h+ppv], rax; ReturnLength
0x18004c6d0  mov     r9d, 4; TokenInformationLength
0x18004c6d6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004c6da  lea     edx, [r9+19h]; TokenInformationClass
0x18004c6de  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004c6e2  call    cs:__imp_GetTokenInformation
0x18004c6e8  mov     rcx, [rbp+TokenHandle]; hObject
0x18004c6ec  call    cs:__imp_CloseHandle
0x18004c6f2  mov     rcx, rbx; hObject
0x18004c6f5  call    cs:__imp_CloseHandle
0x18004c6fb  nop
0x18004c6fc  mov     rcx, [rbp+var_18]
0x18004c700  test    rcx, rcx
0x18004c703  jz      short loc_18004C71A
0x18004c705  mov     [rbp+var_18], 0
0x18004c70d  mov     rdx, [rcx]
0x18004c710  mov     rax, [rdx+10h]
0x18004c714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c719  nop
0x18004c71a  mov     eax, 1
0x18004c71f  mov     rbx, [rsp+50h+arg_0]
0x18004c724  add     rsp, 50h
0x18004c728  pop     rbp
0x18004c729  retn
```
