# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::Pickers::UpdateFilesResult *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1802b0020`
- end: `0x1802b0129`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUpdateFilesResult@Pickers@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `265`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1802b0020`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802b00af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802b00af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1802b007d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1802b007d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802b00ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802b00f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802b00ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802b00f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802b00e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802b00e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802b008d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802b008d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802b005a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802b005a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::Pickers::UpdateFilesResult *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1802b0020  mov     [rsp-8+arg_0], rbx
0x1802b0025  push    rbp
0x1802b0026  mov     rbp, rsp
0x1802b0029  sub     rsp, 50h
0x1802b002d  mov     [rbp+var_18], 0
0x1802b0035  mov     [rbp+var_8], 0
0x1802b003d  lea     rax, [rbp+var_18]
0x1802b0041  mov     [rsp+50h+ppv], rax; ppv
0x1802b0046  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1802b004d  xor     edx, edx; pUnkOuter
0x1802b004f  lea     r8d, [rdx+1]; dwClsContext
0x1802b0053  lea     rcx, CLSID_GlobalOptions; rclsid
0x1802b005a  call    cs:__imp_CoCreateInstance
0x1802b0060  test    eax, eax
0x1802b0062  js      short loc_1802B007D
0x1802b0064  mov     rcx, [rbp+var_18]
0x1802b0068  mov     rax, [rcx]
0x1802b006b  lea     r8, [rbp+var_8]
0x1802b006f  mov     edx, 4
0x1802b0074  mov     rax, [rax+20h]
0x1802b0078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b007d  call    cs:__imp_GetCurrentProcessId
0x1802b0083  mov     r8d, eax; dwProcessId
0x1802b0086  xor     edx, edx; bInheritHandle
0x1802b0088  mov     ecx, 1000h; dwDesiredAccess
0x1802b008d  call    cs:__imp_OpenProcess
0x1802b0093  mov     rbx, rax
0x1802b0096  test    rax, rax
0x1802b0099  jz      short loc_1802B00FC
0x1802b009b  mov     [rbp+TokenHandle], 0
0x1802b00a3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1802b00a7  mov     edx, 8; DesiredAccess
0x1802b00ac  mov     rcx, rax; ProcessHandle
0x1802b00af  call    cs:__imp_OpenProcessToken
0x1802b00b5  test    eax, eax
0x1802b00b7  jz      short loc_1802B00F2
0x1802b00b9  mov     [rbp+ReturnLength], 0
0x1802b00c0  mov     [rbp+TokenInformation], 0
0x1802b00c7  lea     rax, [rbp+ReturnLength]
0x1802b00cb  mov     [rsp+50h+ppv], rax; ReturnLength
0x1802b00d0  mov     r9d, 4; TokenInformationLength
0x1802b00d6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1802b00da  lea     edx, [r9+19h]; TokenInformationClass
0x1802b00de  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802b00e2  call    cs:__imp_GetTokenInformation
0x1802b00e8  mov     rcx, [rbp+TokenHandle]; hObject
0x1802b00ec  call    cs:__imp_CloseHandle
0x1802b00f2  mov     rcx, rbx; hObject
0x1802b00f5  call    cs:__imp_CloseHandle
0x1802b00fb  nop
0x1802b00fc  mov     rcx, [rbp+var_18]
0x1802b0100  test    rcx, rcx
0x1802b0103  jz      short loc_1802B0119
0x1802b0105  mov     [rbp+var_18], 0
0x1802b010d  mov     rdx, [rcx]
0x1802b0110  mov     rax, [rdx+10h]
0x1802b0114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b0119  mov     eax, 1
0x1802b011e  mov     rbx, [rsp+50h+arg_0]
0x1802b0123  add     rsp, 50h
0x1802b0127  pop     rbp
0x1802b0128  retn
```
