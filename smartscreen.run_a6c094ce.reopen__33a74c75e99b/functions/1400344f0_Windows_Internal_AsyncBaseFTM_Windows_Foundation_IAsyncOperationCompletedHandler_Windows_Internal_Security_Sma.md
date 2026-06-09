# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1400344f0`
- end: `0x14003463f`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `335`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140026c20`
- `0x1400344f0`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14003459f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14003459f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140034561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140034561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400345e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400345f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400345e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400345f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140034538`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140034538`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140034577`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140034577`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400345d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400345d8`

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
0x1400344f0  mov     [rsp-8+arg_0], rbx
0x1400344f5  push    rbp
0x1400344f6  mov     rbp, rsp
0x1400344f9  sub     rsp, 60h
0x1400344fd  mov     rax, cs:__security_cookie
0x140034504  xor     rax, rsp
0x140034507  mov     [rbp+var_10], rax
0x14003450b  mov     [rbp+var_28], 0
0x140034513  mov     [rbp+var_18], 0
0x14003451b  lea     rax, [rbp+var_28]
0x14003451f  mov     [rsp+60h+ppv], rax; ppv
0x140034524  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14003452b  xor     edx, edx; pUnkOuter
0x14003452d  lea     r8d, [rdx+1]; dwClsContext
0x140034531  lea     rcx, CLSID_GlobalOptions; rclsid
0x140034538  call    cs:__imp_CoCreateInstance
0x14003453f  nop     dword ptr [rax+rax+00h]
0x140034544  test    eax, eax
0x140034546  js      short loc_140034561
0x140034548  mov     rcx, [rbp+var_28]
0x14003454c  mov     rax, [rcx]
0x14003454f  lea     r8, [rbp+var_18]
0x140034553  mov     edx, 4
0x140034558  mov     rax, [rax+20h]
0x14003455c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034561  call    cs:__imp_GetCurrentProcessId
0x140034568  nop     dword ptr [rax+rax+00h]
0x14003456d  mov     r8d, eax; dwProcessId
0x140034570  xor     edx, edx; bInheritHandle
0x140034572  mov     ecx, 1000h; dwDesiredAccess
0x140034577  call    cs:__imp_OpenProcess
0x14003457e  nop     dword ptr [rax+rax+00h]
0x140034583  mov     rbx, rax
0x140034586  test    rax, rax
0x140034589  jz      short loc_140034604
0x14003458b  mov     [rbp+TokenHandle], 0
0x140034593  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140034597  mov     edx, 8; DesiredAccess
0x14003459c  mov     rcx, rax; ProcessHandle
0x14003459f  call    cs:__imp_OpenProcessToken
0x1400345a6  nop     dword ptr [rax+rax+00h]
0x1400345ab  test    eax, eax
0x1400345ad  jz      short loc_1400345F4
0x1400345af  mov     [rbp+ReturnLength], 0
0x1400345b6  mov     [rbp+TokenInformation], 0
0x1400345bd  lea     rax, [rbp+ReturnLength]
0x1400345c1  mov     [rsp+60h+ppv], rax; ReturnLength
0x1400345c6  mov     r9d, 4; TokenInformationLength
0x1400345cc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400345d0  lea     edx, [r9+19h]; TokenInformationClass
0x1400345d4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400345d8  call    cs:__imp_GetTokenInformation
0x1400345df  nop     dword ptr [rax+rax+00h]
0x1400345e4  mov     rcx, [rbp+TokenHandle]; hObject
0x1400345e8  call    cs:__imp_CloseHandle
0x1400345ef  nop     dword ptr [rax+rax+00h]
0x1400345f4  mov     rcx, rbx; hObject
0x1400345f7  call    cs:__imp_CloseHandle
0x1400345fe  nop     dword ptr [rax+rax+00h]
0x140034603  nop
0x140034604  mov     rcx, [rbp+var_28]
0x140034608  test    rcx, rcx
0x14003460b  jz      short loc_140034622
0x14003460d  mov     [rbp+var_28], 0
0x140034615  mov     rdx, [rcx]
0x140034618  mov     rax, [rdx+10h]
0x14003461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034621  nop
0x140034622  mov     eax, 1
0x140034627  mov     rcx, [rbp+var_10]
0x14003462b  xor     rcx, rsp; StackCookie
0x14003462e  call    __security_check_cookie
0x140034633  mov     rbx, [rsp+60h+arg_0]
0x140034638  add     rsp, 60h
0x14003463c  pop     rbp
0x14003463d  retn
```
