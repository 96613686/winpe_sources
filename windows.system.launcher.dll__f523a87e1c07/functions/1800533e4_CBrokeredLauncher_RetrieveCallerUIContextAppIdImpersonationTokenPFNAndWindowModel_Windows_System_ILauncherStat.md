# CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(Windows::System::ILauncherStatics *,PROCESS_UICONTEXT *,ushort * *,void * *,ushort * *,bool *)

- ea: `0x1800533e4`
- end: `0x180053636`
- name: `?RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAW4PROCESS_UICONTEXT@@PEAPEAGPEAPEAX2PEA_N@Z`
- size: `594`
- prototype: `void __fastcall(struct Windows::System::ILauncherStatics *, enum PROCESS_UICONTEXT *, unsigned __int16 **, void **, _QWORD *Buffer, bool *)`
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800509cc`
- `0x18005101c`
- `0x180051644`
- `0x1800539c0`
- `0x180085f20`

## callees

- `0x18000f194`
- `0x18003ab7c`
- `0x18003fd00`
- `0x180042590`
- `0x180052c38`
- `0x180052dc8`
- `0x180052f4c`
- `0x1800533e4`
- `0x1800536a8`
- `0x1800596d8`
- `0x18008b09c`
- `0x1800a0ee8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180053462`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180053462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800534f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800534f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053506`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053506`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180053552`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180053552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053619`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1800534cb`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1800534cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180053479`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180053479`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180053598`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180053598`

## string_xrefs

- `0x180053430`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(
        struct Windows::System::ILauncherStatics *a1,
        enum PROCESS_UICONTEXT *a2,
        unsigned __int16 **a3,
        void **a4,
        _QWORD *Buffer,
        bool *a6)
{
  _QWORD *v9; // r14
  int ProcessHandleForClientOfObject_nothrow; // eax
  bool *v11; // r8
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rdx
  unsigned int StringW; // eax
  const char *v15; // r9
  HANDLE CurrentThread; // rax
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  int WindowingModelPolicy; // eax
  unsigned __int16 **v21; // r8
  unsigned __int16 **v22; // r8
  void *v23; // rax
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-20h]
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HANDLE ProcessHandle; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  *a4 = 0;
  v9 = Buffer;
  *Buffer = 0;
  LOBYTE(Buffer) = 0;
  ProcessHandle = 0;
  ProcessHandleForClientOfObject_nothrow = wil::GetProcessHandleForClientOfObject_nothrow(a1, 4096, &ProcessHandle);
  v12 = retaddr;
  if ( ProcessHandleForClientOfObject_nothrow < 0 )
  {
    v13 = 965;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      v12,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)ProcessHandleForClientOfObject_nothrow,
      TokenType);
    goto LABEL_4;
  }
  ProcessHandleForClientOfObject_nothrow = CallerIdentity::IsProcessRestrictedAppContainer(ProcessHandle, &Buffer, v11);
  v12 = retaddr;
  if ( ProcessHandleForClientOfObject_nothrow < 0 )
  {
    v13 = 966;
    goto LABEL_3;
  }
  if ( (_BYTE)Buffer )
  {
LABEL_4:
    Buffer = 0;
    StringW = LoadStringW(&_ImageBase, 0x2CFEu, (LPWSTR)&Buffer, 0);
    if ( StringW )
      RoOriginateErrorW(2147942405LL, StringW, Buffer);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3CC,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)0x80070005LL,
      TokenType);
  }
  v25 = 0;
  if ( (unsigned __int8)IsGetProcessUIContextInformationPresent(retaddr)
    && !(unsigned int)GetProcessUIContextInformation(ProcessHandle, &v25) )
  {
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3D3,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      v15);
  }
  *(_DWORD *)a2 = v25;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        v17);
    Buffer = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &Buffer,
      0);
    if ( !OpenProcessToken(ProcessHandle, 0xEu, (PHANDLE)&Buffer) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3E1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        v18);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    if ( !DuplicateTokenEx(Buffer, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3E4,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        v19);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Buffer);
  }
  WindowingModelPolicy = AppModelPolicy::GetWindowingModelPolicy(TokenHandle);
  *a6 = WindowingModelPolicy == 196609;
  Buffer = 0;
  CallerIdentity::GetProcessAppId((CallerIdentity *)ProcessHandle, &Buffer, v21);
  v26 = 0;
  CallerIdentity::GetPackageFamilyNameFromProcess(ProcessHandle, &v26, v22);
  *a3 = (unsigned __int16 *)Buffer;
  v23 = TokenHandle;
  TokenHandle = 0;
  *a4 = v23;
  *v9 = v26;
  if ( ProcessHandle )
    CloseHandle(ProcessHandle);
}

```

## disassembly

```asm
0x1800533e4  mov     [rsp-28h+arg_0], rbx
0x1800533e9  mov     [rsp-28h+arg_8], rsi
0x1800533ee  push    rbp
0x1800533ef  push    rdi
0x1800533f0  push    r12
0x1800533f2  push    r14
0x1800533f4  push    r15
0x1800533f6  mov     rbp, rsp
0x1800533f9  sub     rsp, 40h
0x1800533fd  mov     rdi, r9
0x180053400  mov     rsi, r8
0x180053403  mov     rbx, rdx
0x180053406  xor     r15d, r15d
0x180053409  mov     [r8], r15
0x18005340c  mov     [r9], r15
0x18005340f  mov     r14, [rbp+Buffer]
0x180053413  mov     [r14], r15
0x180053416  mov     byte ptr [rbp+Buffer], r15b
0x18005341a  mov     [rbp+ProcessHandle], r15
0x18005341e  lea     r8, [rbp+ProcessHandle]
0x180053422  mov     edx, 1000h
0x180053427  call    ?GetProcessHandleForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetProcessHandleForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18005342c  mov     rcx, [rbp+28h]; this
0x180053430  lea     r12, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x180053437  test    eax, eax
0x180053439  jns     short loc_180053494
0x18005343b  mov     edx, 3C5h; void *
0x180053440  mov     r8, r12; unsigned int
0x180053443  mov     r9d, eax; char *
0x180053446  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005344b  mov     [rbp+Buffer], r15
0x18005344f  xor     r9d, r9d; cchBufferMax
0x180053452  lea     r8, [rbp+Buffer]; lpBuffer
0x180053456  mov     edx, 2CFEh; uID
0x18005345b  lea     rcx, __ImageBase; hInstance
0x180053462  call    cs:__imp_LoadStringW
0x180053468  mov     ebx, 80070005h
0x18005346d  test    eax, eax
0x18005346f  jz      short loc_18005347F
0x180053471  mov     r8, [rbp+Buffer]
0x180053475  mov     edx, eax
0x180053477  mov     ecx, ebx
0x180053479  call    cs:__imp_RoOriginateErrorW
0x18005347f  mov     rcx, [rbp+28h]; this
0x180053483  mov     r9d, ebx; char *
0x180053486  mov     r8, r12; unsigned int
0x180053489  mov     edx, 3CCh; void *
0x18005348e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053494  lea     rdx, [rbp+Buffer]; void *
0x180053498  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18005349c  call    ?IsProcessRestrictedAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessRestrictedAppContainer(void *,bool *)
0x1800534a1  mov     rcx, [rbp+28h]
0x1800534a5  test    eax, eax
0x1800534a7  jns     short loc_1800534B0
0x1800534a9  mov     edx, 3C6h
0x1800534ae  jmp     short loc_180053440
0x1800534b0  cmp     byte ptr [rbp+Buffer], r15b
0x1800534b4  jnz     short loc_18005344B
0x1800534b6  mov     [rbp+var_10], r15
0x1800534ba  call    IsGetProcessUIContextInformationPresent
0x1800534bf  test    al, al
0x1800534c1  jz      short loc_1800534E7
0x1800534c3  lea     rdx, [rbp+var_10]
0x1800534c7  mov     rcx, [rbp+ProcessHandle]
0x1800534cb  call    cs:__imp_GetProcessUIContextInformation
0x1800534d1  mov     rcx, [rbp+28h]; this
0x1800534d5  test    eax, eax
0x1800534d7  jnz     short loc_1800534E7
0x1800534d9  mov     r8, r12; unsigned int
0x1800534dc  mov     edx, 3D3h; void *
0x1800534e1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800534e7  mov     eax, dword ptr [rbp+var_10]
0x1800534ea  mov     [rbx], eax
0x1800534ec  mov     [rbp+TokenHandle], r15
0x1800534f0  call    cs:__imp_GetCurrentThread
0x1800534f6  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800534fa  mov     edx, 0Ch; DesiredAccess
0x1800534ff  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180053503  mov     rcx, rax; ThreadHandle
0x180053506  call    cs:__imp_OpenThreadToken
0x18005350c  test    eax, eax
0x18005350e  jnz     loc_1800535BD
0x180053514  mov     rbx, [rbp+28h]
0x180053518  call    cs:__imp_GetLastError
0x18005351e  cmp     eax, 3F0h
0x180053523  jz      short loc_180053536
0x180053525  mov     r8, r12; unsigned int
0x180053528  mov     edx, 3DEh; void *
0x18005352d  mov     rcx, rbx; this
0x180053530  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053536  mov     [rbp+Buffer], r15
0x18005353a  xor     edx, edx
0x18005353c  lea     rcx, [rbp+Buffer]
0x180053540  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180053545  lea     r8, [rbp+Buffer]; TokenHandle
0x180053549  mov     edx, 0Eh; DesiredAccess
0x18005354e  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x180053552  call    cs:__imp_OpenProcessToken
0x180053558  mov     rcx, [rbp+28h]; this
0x18005355c  test    eax, eax
0x18005355e  jnz     short loc_18005356E
0x180053560  mov     r8, r12; unsigned int
0x180053563  mov     edx, 3E1h; void *
0x180053568  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005356e  xor     edx, edx
0x180053570  lea     rcx, [rbp+TokenHandle]
0x180053574  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180053579  lea     rax, [rbp+TokenHandle]
0x18005357d  mov     [rsp+40h+phNewToken], rax; phNewToken
0x180053582  mov     r9d, 2; ImpersonationLevel
0x180053588  mov     [rsp+40h+TokenType], r9d; TokenType
0x18005358d  xor     r8d, r8d; lpTokenAttributes
0x180053590  lea     edx, [r9+0Ah]; dwDesiredAccess
0x180053594  mov     rcx, [rbp+Buffer]; hExistingToken
0x180053598  call    cs:__imp_DuplicateTokenEx
0x18005359e  mov     rcx, [rbp+28h]; this
0x1800535a2  test    eax, eax
0x1800535a4  jnz     short loc_1800535B4
0x1800535a6  mov     r8, r12; unsigned int
0x1800535a9  mov     edx, 3E4h; void *
0x1800535ae  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800535b4  lea     rcx, [rbp+Buffer]
0x1800535b8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800535bd  mov     rcx, [rbp+TokenHandle]
0x1800535c1  call    ?GetWindowingModelPolicy@AppModelPolicy@@YA?AW4WindowingModelPolicy@1@PEAX@Z; AppModelPolicy::GetWindowingModelPolicy(void *)
0x1800535c6  cmp     eax, 30001h
0x1800535cb  setz    cl
0x1800535ce  mov     rax, [rbp+arg_28]
0x1800535d2  mov     [rax], cl
0x1800535d4  mov     [rbp+Buffer], r15
0x1800535d8  lea     rdx, [rbp+Buffer]; void *
0x1800535dc  mov     rcx, [rbp+ProcessHandle]; this
0x1800535e0  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800535e5  nop
0x1800535e6  mov     [rbp+var_8], r15
0x1800535ea  lea     rdx, [rbp+var_8]; void *
0x1800535ee  mov     rcx, [rbp+ProcessHandle]; hProcess
0x1800535f2  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x1800535f7  mov     rax, [rbp+Buffer]
0x1800535fb  mov     [rsi], rax
0x1800535fe  mov     rax, [rbp+TokenHandle]
0x180053602  mov     [rbp+TokenHandle], r15
0x180053606  mov     [rdi], rax
0x180053609  mov     rax, [rbp+var_8]
0x18005360d  mov     [r14], rax
0x180053610  mov     rcx, [rbp+ProcessHandle]; hObject
0x180053614  test    rcx, rcx
0x180053617  jz      short loc_18005361F
0x180053619  call    cs:__imp_CloseHandle
0x18005361f  mov     rbx, [rsp+40h+arg_0]
0x180053624  mov     rsi, [rsp+40h+arg_8]
0x180053629  add     rsp, 40h
0x18005362d  pop     r15
0x18005362f  pop     r14
0x180053631  pop     r12
0x180053633  pop     rdi
0x180053634  pop     rbp
0x180053635  retn
```
