# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180180250`
- end: `0x180180358`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180180250`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801802df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801802df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801802ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801802ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018031c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180180325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018031c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180180325`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180180312`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180180312`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801802bd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801802bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018028a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018028a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180180250  mov     [rsp-8+arg_0], rbx
0x180180255  push    rbp
0x180180256  mov     rbp, rsp
0x180180259  sub     rsp, 50h
0x18018025d  xor     edx, edx; pUnkOuter
0x18018025f  mov     [rbp+var_18], 0
0x180180267  lea     rax, [rbp+var_18]
0x18018026b  mov     [rbp+var_8], 0
0x180180273  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18018027a  mov     [rsp+50h+ppv], rax; ppv
0x18018027f  lea     rcx, CLSID_GlobalOptions; rclsid
0x180180286  lea     r8d, [rdx+1]; dwClsContext
0x18018028a  call    cs:__imp_CoCreateInstance
0x180180290  test    eax, eax
0x180180292  js      short loc_1801802AD
0x180180294  mov     rcx, [rbp+var_18]
0x180180298  lea     r8, [rbp+var_8]
0x18018029c  mov     edx, 4
0x1801802a1  mov     rax, [rcx]
0x1801802a4  mov     rax, [rax+20h]
0x1801802a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801802ad  call    cs:__imp_GetCurrentProcessId
0x1801802b3  xor     edx, edx; bInheritHandle
0x1801802b5  mov     ecx, 1000h; dwDesiredAccess
0x1801802ba  mov     r8d, eax; dwProcessId
0x1801802bd  call    cs:__imp_OpenProcess
0x1801802c3  mov     rbx, rax
0x1801802c6  test    rax, rax
0x1801802c9  jz      short loc_18018032B
0x1801802cb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801802cf  mov     [rbp+TokenHandle], 0
0x1801802d7  mov     edx, 8; DesiredAccess
0x1801802dc  mov     rcx, rax; ProcessHandle
0x1801802df  call    cs:__imp_OpenProcessToken
0x1801802e5  test    eax, eax
0x1801802e7  jz      short loc_180180322
0x1801802e9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801802ed  lea     rax, [rbp+ReturnLength]
0x1801802f1  mov     r9d, 4; TokenInformationLength
0x1801802f7  mov     [rbp+ReturnLength], 0
0x1801802fe  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180180302  mov     [rbp+TokenInformation], 0
0x180180309  mov     [rsp+50h+ppv], rax; ReturnLength
0x18018030e  lea     edx, [r9+19h]; TokenInformationClass
0x180180312  call    cs:__imp_GetTokenInformation
0x180180318  mov     rcx, [rbp+TokenHandle]; hObject
0x18018031c  call    cs:__imp_CloseHandle
0x180180322  mov     rcx, rbx; hObject
0x180180325  call    cs:__imp_CloseHandle
0x18018032b  mov     rcx, [rbp+var_18]
0x18018032f  test    rcx, rcx
0x180180332  jz      short loc_180180348
0x180180334  mov     [rbp+var_18], 0
0x18018033c  mov     rdx, [rcx]
0x18018033f  mov     rax, [rdx+10h]
0x180180343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180348  mov     rbx, [rsp+50h+arg_0]
0x18018034d  mov     eax, 1
0x180180352  add     rsp, 50h
0x180180356  pop     rbp
0x180180357  retn
```
