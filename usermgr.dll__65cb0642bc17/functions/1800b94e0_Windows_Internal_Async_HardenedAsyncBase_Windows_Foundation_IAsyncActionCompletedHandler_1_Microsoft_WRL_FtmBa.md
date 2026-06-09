# Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800b94e0`
- end: `0x1800b95f4`
- name: `?CheckExecutionEnvironment@?$HardenedAsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `276`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ce48`
- `0x1800b94e0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b951a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b951a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b95b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b95b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b954b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b954b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b957d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b957d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b95cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b95d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b95cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b95d4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b955b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b955b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  DWORD ReturnLength; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+48h] [rbp-8h] BYREF
  int TokenInformation; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v10 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v10);
    Windows::Internal::Async::s_bIsWakeOnRpcSuppressionEnabled = (v10 & 0x20) != 0;
  }
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
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
        && TokenInformation )
      {
        Windows::Internal::Async::s_bIsAppContainer = 1;
      }
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
0x1800b94e0  mov     [rsp-8+arg_0], rbx
0x1800b94e5  push    rbp
0x1800b94e6  mov     rbp, rsp
0x1800b94e9  sub     rsp, 50h
0x1800b94ed  mov     [rbp+var_10], 0
0x1800b94f5  mov     [rbp+var_8], 0
0x1800b94fd  lea     rax, [rbp+var_10]
0x1800b9501  mov     [rsp+50h+ppv], rax; ppv
0x1800b9506  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800b950d  xor     edx, edx; pUnkOuter
0x1800b950f  lea     r8d, [rdx+1]; dwClsContext
0x1800b9513  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800b951a  call    cs:__imp_CoCreateInstance
0x1800b9520  test    eax, eax
0x1800b9522  js      short loc_1800B954B
0x1800b9524  mov     rcx, [rbp+var_10]
0x1800b9528  mov     rax, [rcx]
0x1800b952b  lea     r8, [rbp+var_8]
0x1800b952f  mov     edx, 4
0x1800b9534  mov     rax, [rax+20h]
0x1800b9538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b953d  mov     al, byte ptr [rbp+var_8]
0x1800b9540  shr     al, 5
0x1800b9543  and     al, 1
0x1800b9545  mov     cs:?s_bIsWakeOnRpcSuppressionEnabled@Async@Internal@Windows@@3_NA, al; bool Windows::Internal::Async::s_bIsWakeOnRpcSuppressionEnabled
0x1800b954b  call    cs:__imp_GetCurrentProcessId
0x1800b9551  mov     r8d, eax; dwProcessId
0x1800b9554  xor     edx, edx; bInheritHandle
0x1800b9556  mov     ecx, 1000h; dwDesiredAccess
0x1800b955b  call    cs:__imp_OpenProcess
0x1800b9561  mov     rbx, rax
0x1800b9564  test    rax, rax
0x1800b9567  jz      short loc_1800B95DB
0x1800b9569  mov     [rbp+TokenHandle], 0
0x1800b9571  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800b9575  mov     edx, 8; DesiredAccess
0x1800b957a  mov     rcx, rax; ProcessHandle
0x1800b957d  call    cs:__imp_OpenProcessToken
0x1800b9583  test    eax, eax
0x1800b9585  jz      short loc_1800B95D1
0x1800b9587  mov     [rbp+ReturnLength], 0
0x1800b958e  mov     [rbp+TokenInformation], 0
0x1800b9595  lea     rax, [rbp+ReturnLength]
0x1800b9599  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800b959e  mov     r9d, 4; TokenInformationLength
0x1800b95a4  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800b95a8  lea     edx, [r9+19h]; TokenInformationClass
0x1800b95ac  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800b95b0  call    cs:__imp_GetTokenInformation
0x1800b95b6  test    eax, eax
0x1800b95b8  jz      short loc_1800B95C7
0x1800b95ba  cmp     [rbp+TokenInformation], 0
0x1800b95be  jz      short loc_1800B95C7
0x1800b95c0  mov     cs:?s_bIsAppContainer@Async@Internal@Windows@@3_NA, 1; bool Windows::Internal::Async::s_bIsAppContainer
0x1800b95c7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800b95cb  call    cs:__imp_CloseHandle
0x1800b95d1  mov     rcx, rbx; hObject
0x1800b95d4  call    cs:__imp_CloseHandle
0x1800b95da  nop
0x1800b95db  lea     rcx, [rbp+var_10]
0x1800b95df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b95e4  mov     eax, 1
0x1800b95e9  mov     rbx, [rsp+50h+arg_0]
0x1800b95ee  add     rsp, 50h
0x1800b95f2  pop     rbp
0x1800b95f3  retn
```
