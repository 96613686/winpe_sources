# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180029820`
- end: `0x18002992a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180029820`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002985a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002985a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002987d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002987d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800298af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800298af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800298e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800298e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002988d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002988d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::CheckExecutionEnvironment(
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
0x180029820  mov     [rsp-8+arg_0], rbx
0x180029825  push    rbp
0x180029826  mov     rbp, rsp
0x180029829  sub     rsp, 50h
0x18002982d  mov     [rbp+var_18], 0
0x180029835  mov     [rbp+var_8], 0
0x18002983d  lea     rax, [rbp+var_18]
0x180029841  mov     [rsp+50h+ppv], rax; ppv
0x180029846  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18002984d  xor     edx, edx; pUnkOuter
0x18002984f  lea     r8d, [rdx+1]; dwClsContext
0x180029853  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002985a  call    cs:__imp_CoCreateInstance
0x180029860  test    eax, eax
0x180029862  js      short loc_18002987D
0x180029864  mov     rcx, [rbp+var_18]
0x180029868  mov     rax, [rcx]
0x18002986b  lea     r8, [rbp+var_8]
0x18002986f  mov     edx, 4
0x180029874  mov     rax, [rax+20h]
0x180029878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002987d  call    cs:__imp_GetCurrentProcessId
0x180029883  mov     r8d, eax; dwProcessId
0x180029886  xor     edx, edx; bInheritHandle
0x180029888  mov     ecx, 1000h; dwDesiredAccess
0x18002988d  call    cs:__imp_OpenProcess
0x180029893  mov     rbx, rax
0x180029896  test    rax, rax
0x180029899  jz      short loc_1800298FC
0x18002989b  mov     [rbp+TokenHandle], 0
0x1800298a3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800298a7  mov     edx, 8; DesiredAccess
0x1800298ac  mov     rcx, rax; ProcessHandle
0x1800298af  call    cs:__imp_OpenProcessToken
0x1800298b5  test    eax, eax
0x1800298b7  jz      short loc_1800298F2
0x1800298b9  mov     [rbp+ReturnLength], 0
0x1800298c0  mov     [rbp+TokenInformation], 0
0x1800298c7  lea     rax, [rbp+ReturnLength]
0x1800298cb  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800298d0  mov     r9d, 4; TokenInformationLength
0x1800298d6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800298da  lea     edx, [r9+19h]; TokenInformationClass
0x1800298de  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800298e2  call    cs:__imp_GetTokenInformation
0x1800298e8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800298ec  call    cs:__imp_CloseHandle
0x1800298f2  mov     rcx, rbx; hObject
0x1800298f5  call    cs:__imp_CloseHandle
0x1800298fb  nop
0x1800298fc  mov     rcx, [rbp+var_18]
0x180029900  test    rcx, rcx
0x180029903  jz      short loc_18002991A
0x180029905  mov     [rbp+var_18], 0
0x18002990d  mov     rdx, [rcx]
0x180029910  mov     rax, [rdx+10h]
0x180029914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029919  nop
0x18002991a  mov     eax, 1
0x18002991f  mov     rbx, [rsp+50h+arg_0]
0x180029924  add     rsp, 50h
0x180029928  pop     rbp
0x180029929  retn
```
