# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x140033070`
- end: `0x140033194`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `292`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140025aa0`
- `0x140033070`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14003310d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14003310d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400330db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400330db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003314a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033153`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003314a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033153`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400330b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400330b8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400330eb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400330eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140033140`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140033140`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x140033070  mov     [rsp-8+arg_0], rbx
0x140033075  push    rbp
0x140033076  mov     rbp, rsp
0x140033079  sub     rsp, 60h
0x14003307d  mov     rax, cs:__security_cookie
0x140033084  xor     rax, rsp
0x140033087  mov     [rbp+var_10], rax
0x14003308b  mov     [rbp+var_28], 0
0x140033093  mov     [rbp+var_18], 0
0x14003309b  lea     rax, [rbp+var_28]
0x14003309f  mov     [rsp+60h+ppv], rax; ppv
0x1400330a4  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1400330ab  xor     edx, edx; pUnkOuter
0x1400330ad  lea     r8d, [rdx+1]; dwClsContext
0x1400330b1  lea     rcx, CLSID_GlobalOptions; rclsid
0x1400330b8  call    cs:__imp_CoCreateInstance
0x1400330be  test    eax, eax
0x1400330c0  js      short loc_1400330DB
0x1400330c2  mov     rcx, [rbp+var_28]
0x1400330c6  mov     rax, [rcx]
0x1400330c9  lea     r8, [rbp+var_18]
0x1400330cd  mov     edx, 4
0x1400330d2  mov     rax, [rax+20h]
0x1400330d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400330db  call    cs:__imp_GetCurrentProcessId
0x1400330e1  mov     r8d, eax; dwProcessId
0x1400330e4  xor     edx, edx; bInheritHandle
0x1400330e6  mov     ecx, 1000h; dwDesiredAccess
0x1400330eb  call    cs:__imp_OpenProcess
0x1400330f1  mov     rbx, rax
0x1400330f4  test    rax, rax
0x1400330f7  jz      short loc_14003315A
0x1400330f9  mov     [rbp+TokenHandle], 0
0x140033101  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140033105  mov     edx, 8; DesiredAccess
0x14003310a  mov     rcx, rax; ProcessHandle
0x14003310d  call    cs:__imp_OpenProcessToken
0x140033113  test    eax, eax
0x140033115  jz      short loc_140033150
0x140033117  mov     [rbp+ReturnLength], 0
0x14003311e  mov     [rbp+TokenInformation], 0
0x140033125  lea     rax, [rbp+ReturnLength]
0x140033129  mov     [rsp+60h+ppv], rax; ReturnLength
0x14003312e  mov     r9d, 4; TokenInformationLength
0x140033134  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140033138  lea     edx, [r9+19h]; TokenInformationClass
0x14003313c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140033140  call    cs:__imp_GetTokenInformation
0x140033146  mov     rcx, [rbp+TokenHandle]; hObject
0x14003314a  call    cs:__imp_CloseHandle
0x140033150  mov     rcx, rbx; hObject
0x140033153  call    cs:__imp_CloseHandle
0x140033159  nop
0x14003315a  mov     rcx, [rbp+var_28]
0x14003315e  test    rcx, rcx
0x140033161  jz      short loc_140033178
0x140033163  mov     [rbp+var_28], 0
0x14003316b  mov     rdx, [rcx]
0x14003316e  mov     rax, [rdx+10h]
0x140033172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033177  nop
0x140033178  mov     eax, 1
0x14003317d  mov     rcx, [rbp+var_10]
0x140033181  xor     rcx, rsp; StackCookie
0x140033184  call    __security_check_cookie
0x140033189  mov     rbx, [rsp+60h+arg_0]
0x14003318e  add     rsp, 60h
0x140033192  pop     rbp
0x140033193  retn
```
