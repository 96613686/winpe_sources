# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800401c0`
- end: `0x1800402ca`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800401c0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004021d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004021d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004024f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004024f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004022d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004022d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004028c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004028c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040295`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800401fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800401fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180040282`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180040282`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800401c0  mov     [rsp-8+arg_0], rbx
0x1800401c5  push    rbp
0x1800401c6  mov     rbp, rsp
0x1800401c9  sub     rsp, 50h
0x1800401cd  mov     [rbp+var_18], 0
0x1800401d5  mov     [rbp+var_8], 0
0x1800401dd  lea     rax, [rbp+var_18]
0x1800401e1  mov     [rsp+50h+ppv], rax; ppv
0x1800401e6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800401ed  xor     edx, edx; pUnkOuter
0x1800401ef  lea     r8d, [rdx+1]; dwClsContext
0x1800401f3  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800401fa  call    cs:__imp_CoCreateInstance
0x180040200  test    eax, eax
0x180040202  js      short loc_18004021D
0x180040204  mov     rcx, [rbp+var_18]
0x180040208  mov     rax, [rcx]
0x18004020b  lea     r8, [rbp+var_8]
0x18004020f  mov     edx, 4
0x180040214  mov     rax, [rax+20h]
0x180040218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004021d  call    cs:__imp_GetCurrentProcessId
0x180040223  mov     r8d, eax; dwProcessId
0x180040226  xor     edx, edx; bInheritHandle
0x180040228  mov     ecx, 1000h; dwDesiredAccess
0x18004022d  call    cs:__imp_OpenProcess
0x180040233  mov     rbx, rax
0x180040236  test    rax, rax
0x180040239  jz      short loc_18004029C
0x18004023b  mov     [rbp+TokenHandle], 0
0x180040243  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180040247  mov     edx, 8; DesiredAccess
0x18004024c  mov     rcx, rax; ProcessHandle
0x18004024f  call    cs:__imp_OpenProcessToken
0x180040255  test    eax, eax
0x180040257  jz      short loc_180040292
0x180040259  mov     [rbp+ReturnLength], 0
0x180040260  mov     [rbp+TokenInformation], 0
0x180040267  lea     rax, [rbp+ReturnLength]
0x18004026b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180040270  mov     r9d, 4; TokenInformationLength
0x180040276  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004027a  lea     edx, [r9+19h]; TokenInformationClass
0x18004027e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180040282  call    cs:__imp_GetTokenInformation
0x180040288  mov     rcx, [rbp+TokenHandle]; hObject
0x18004028c  call    cs:__imp_CloseHandle
0x180040292  mov     rcx, rbx; hObject
0x180040295  call    cs:__imp_CloseHandle
0x18004029b  nop
0x18004029c  mov     rcx, [rbp+var_18]
0x1800402a0  test    rcx, rcx
0x1800402a3  jz      short loc_1800402BA
0x1800402a5  mov     [rbp+var_18], 0
0x1800402ad  mov     rdx, [rcx]
0x1800402b0  mov     rax, [rdx+10h]
0x1800402b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402b9  nop
0x1800402ba  mov     eax, 1
0x1800402bf  mov     rbx, [rsp+50h+arg_0]
0x1800402c4  add     rsp, 50h
0x1800402c8  pop     rbp
0x1800402c9  retn
```
