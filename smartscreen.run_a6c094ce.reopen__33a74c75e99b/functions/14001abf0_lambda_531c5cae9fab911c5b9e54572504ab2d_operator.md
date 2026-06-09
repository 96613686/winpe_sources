# _lambda_531c5cae9fab911c5b9e54572504ab2d_::operator()

- ea: `0x14001abf0`
- end: `0x14001af9a`
- name: `_lambda_531c5cae9fab911c5b9e54572504ab2d_::operator()`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140031ea0`

## callees

- `0x140002fac`
- `0x1400055ac`
- `0x1400061cc`
- `0x14000cb90`
- `0x14001abf0`
- `0x14001afa0`
- `0x14001afcc`
- `0x14001d9f4`
- `0x140026c20`
- `0x140030510`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001ae18`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001af14`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001ae18`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001af14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001adfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001aef7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001adfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001aef7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001af6e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001af6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001aca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ade0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001aedc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001af44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001aca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ade0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001aedc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001af44`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14001ad5a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14001ad5a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001ad92`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001ad92`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001ac3e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x14001ac3e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001ae40`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001ae40`

## pseudocode

```c
__int64 __fastcall lambda_531c5cae9fab911c5b9e54572504ab2d_::operator()(_QWORD *a1)
{
  void **v3; // rax
  HRESULT v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, HANDLE *); // r12
  HANDLE v7; // rbx
  int v8; // eax
  HANDLE CurrentProcess; // rdi
  HANDLE v10; // rbx
  HANDLE v11; // rax
  const char *v12; // r9
  HRESULT v13; // eax
  HANDLE v14; // rbx
  HANDLE CurrentThread; // rax
  const char *v16; // r9
  unsigned int v17; // ebx
  HANDLE v19; // rbx
  HANDLE v20; // rax
  HANDLE v21; // rbx
  const char *v22; // r9
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-98h]
  _BYTE v24[8]; // [rsp+40h] [rbp-78h] BYREF
  HANDLE v25; // [rsp+48h] [rbp-70h] BYREF
  HANDLE v26; // [rsp+50h] [rbp-68h] BYREF
  char v27; // [rsp+59h] [rbp-5Fh]
  HANDLE TokenHandle; // [rsp+60h] [rbp-58h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-50h] BYREF
  __int64 v30; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v25 = a1;
  hObject = 0;
  TokenHandle = 0;
  v30 = 0;
  v3 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ICallingProcessInfo>>(&v30);
  v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, v3);
  if ( *(_BYTE *)(*a1 + 128LL) )
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\api_guard.h",
        (const char *)(unsigned int)v4,
        dwDesiredAccess);
    v5 = v30;
    v6 = *(__int64 (__fastcall **)(__int64, __int64, HANDLE *))(*(_QWORD *)v30 + 24LL);
    v7 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
      CloseHandle(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
    }
    hObject = 0;
    v8 = v6(v5, 1024, &hObject);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\api_guard.h",
        (const char *)(unsigned int)v8,
        dwDesiredAccess);
  }
  if ( (((unsigned __int64)hObject + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    v10 = GetCurrentProcess();
    v11 = GetCurrentProcess();
    if ( !DuplicateHandle(v11, v10, CurrentProcess, &hObject, 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\api_guard.h",
        v12);
  }
  if ( *(_BYTE *)(*a1 + 128LL) )
  {
    v13 = CoImpersonateClient();
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\api_guard.h",
        (const char *)(unsigned int)v13,
        dwDesiredAccess);
    v27 = 1;
    v14 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v24);
      CloseHandle(v14);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v24);
    }
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\api_guard.h",
        v16);
    CoRevertToSelf();
  }
  else
  {
    v19 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v24);
      CloseHandle(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v24);
    }
    TokenHandle = 0;
    v20 = GetCurrentThread();
    if ( !OpenThreadToken(v20, 0xCu, 1, &TokenHandle) )
    {
      v21 = TokenHandle;
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v24);
        CloseHandle(v21);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v24);
      }
      TokenHandle = 0;
      if ( !OpenProcessToken(hObject, 0xAu, &TokenHandle) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x59,
          (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\api_guard.h",
          v22);
    }
  }
  v25 = TokenHandle;
  TokenHandle = 0;
  v26 = hObject;
  hObject = 0;
  v17 = lambda_34446dcb70f9648d12f61e8c6e9f58a2_::operator()(a1[1], &v26, &v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  return v17;
}

```

## disassembly

```asm
0x14001abf0  mov     r11, rsp
0x14001abf3  push    rbx
0x14001abf4  push    rsi
0x14001abf5  push    rdi
0x14001abf6  push    r12
0x14001abf8  push    r14
0x14001abfa  push    r15
0x14001abfc  sub     rsp, 88h
0x14001ac03  mov     rax, cs:__security_cookie
0x14001ac0a  xor     rax, rsp
0x14001ac0d  mov     [rsp+0B8h+var_40], rax
0x14001ac12  mov     r14, rcx
0x14001ac15  mov     r15, rcx
0x14001ac18  mov     [rsp+0B8h+var_70], rcx
0x14001ac1d  xor     esi, esi
0x14001ac1f  mov     [r11-50h], rsi
0x14001ac23  mov     [r11-58h], rsi
0x14001ac27  mov     [r11-48h], rsi
0x14001ac2b  lea     rcx, [r11-48h]
0x14001ac2f  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ICallingProcessInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICallingProcessInfo>>)
0x14001ac34  mov     rdx, rax; ppInterface
0x14001ac37  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x14001ac3e  call    cs:__imp_CoGetCallContext
0x14001ac45  nop     dword ptr [rax+rax+00h]
0x14001ac4a  mov     rcx, [r15]
0x14001ac4d  cmp     [rcx+80h], sil
0x14001ac54  jz      loc_14001ACFD
0x14001ac5a  mov     rcx, [rsp+0B8h]; this
0x14001ac62  test    eax, eax
0x14001ac64  jns     short loc_14001AC78
0x14001ac66  mov     r9d, eax; char *
0x14001ac69  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001ac70  lea     edx, [rsi+43h]; void *
0x14001ac73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001ac78  mov     rdi, [rsp+0B8h+var_48]
0x14001ac7d  mov     rax, [rdi]
0x14001ac80  mov     r12, [rax+18h]
0x14001ac84  mov     rbx, [rsp+0B8h+hObject]
0x14001ac89  lea     rax, [rbx-1]
0x14001ac8d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ac91  ja      short loc_14001ACB6
0x14001ac93  lea     rcx, [rsp+0B8h+var_68]; this
0x14001ac98  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001ac9d  mov     rcx, rbx; hObject
0x14001aca0  call    cs:__imp_CloseHandle
0x14001aca7  nop     dword ptr [rax+rax+00h]
0x14001acac  lea     rcx, [rsp+0B8h+var_68]; this
0x14001acb1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001acb6  mov     [rsp+0B8h+hObject], rsi
0x14001acbb  lea     r8, [rsp+0B8h+hObject]
0x14001acc0  mov     edx, 400h
0x14001acc5  mov     rcx, rdi
0x14001acc8  mov     rax, r12
0x14001accb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001acd0  mov     rcx, [rsp+0B8h]; this
0x14001acd8  test    eax, eax
0x14001acda  jns     short loc_14001ACF1
0x14001acdc  mov     r9d, eax; char *
0x14001acdf  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001ace6  mov     edx, 44h ; 'D'; void *
0x14001aceb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001acf1  jmp     short loc_14001ACFD
0x14001acf3  xor     esi, esi
0x14001acf5  mov     r15, [rsp+0B8h+var_70]
0x14001acfa  mov     r14, r15
0x14001acfd  mov     rax, [rsp+0B8h+hObject]
0x14001ad02  inc     rax
0x14001ad05  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001ad0b  jnz     short loc_14001AD82
0x14001ad0d  mov     [rsp+0B8h+hObject], rsi
0x14001ad12  call    cs:__imp_GetCurrentProcess
0x14001ad19  nop     dword ptr [rax+rax+00h]
0x14001ad1e  mov     rdi, rax
0x14001ad21  call    cs:__imp_GetCurrentProcess
0x14001ad28  nop     dword ptr [rax+rax+00h]
0x14001ad2d  mov     rbx, rax
0x14001ad30  call    cs:__imp_GetCurrentProcess
0x14001ad37  nop     dword ptr [rax+rax+00h]
0x14001ad3c  mov     [rsp+0B8h+dwOptions], 2; dwOptions
0x14001ad44  mov     [rsp+0B8h+bInheritHandle], esi; bInheritHandle
0x14001ad48  mov     [rsp+0B8h+dwDesiredAccess], esi; dwDesiredAccess
0x14001ad4c  lea     r9, [rsp+0B8h+hObject]; lpTargetHandle
0x14001ad51  mov     r8, rdi; hTargetProcessHandle
0x14001ad54  mov     rdx, rbx; hSourceHandle
0x14001ad57  mov     rcx, rax; hSourceProcessHandle
0x14001ad5a  call    cs:__imp_DuplicateHandle
0x14001ad61  nop     dword ptr [rax+rax+00h]
0x14001ad66  mov     rcx, [rsp+0B8h]; this
0x14001ad6e  test    eax, eax
0x14001ad70  jnz     short loc_14001AD82
0x14001ad72  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001ad79  lea     edx, [rax+4Bh]; void *
0x14001ad7c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14001ad82  mov     rax, [r14]
0x14001ad85  cmp     [rax+80h], sil
0x14001ad8c  jz      loc_14001AEC0
0x14001ad92  call    cs:__imp_CoImpersonateClient
0x14001ad99  nop     dword ptr [rax+rax+00h]
0x14001ad9e  mov     rcx, [rsp+0B8h]; this
0x14001ada6  test    eax, eax
0x14001ada8  jns     short loc_14001ADBF
0x14001adaa  mov     r9d, eax; char *
0x14001adad  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001adb4  mov     edx, 50h ; 'P'; void *
0x14001adb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001adbf  mov     [rsp+0B8h+var_5F], 1
0x14001adc4  mov     rbx, [rsp+0B8h+TokenHandle]
0x14001adc9  lea     rax, [rbx-1]
0x14001adcd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001add1  ja      short loc_14001ADF6
0x14001add3  lea     rcx, [rsp+0B8h+var_78]; this
0x14001add8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001addd  mov     rcx, rbx; hObject
0x14001ade0  call    cs:__imp_CloseHandle
0x14001ade7  nop     dword ptr [rax+rax+00h]
0x14001adec  lea     rcx, [rsp+0B8h+var_78]; this
0x14001adf1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001adf6  mov     [rsp+0B8h+TokenHandle], rsi
0x14001adfb  call    cs:__imp_GetCurrentThread
0x14001ae02  nop     dword ptr [rax+rax+00h]
0x14001ae07  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x14001ae0c  mov     edx, 0Ch; DesiredAccess
0x14001ae11  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x14001ae15  mov     rcx, rax; ThreadHandle
0x14001ae18  call    cs:__imp_OpenThreadToken
0x14001ae1f  nop     dword ptr [rax+rax+00h]
0x14001ae24  mov     rcx, [rsp+0B8h]; this
0x14001ae2c  test    eax, eax
0x14001ae2e  jnz     short loc_14001AE40
0x14001ae30  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001ae37  lea     edx, [rax+53h]; void *
0x14001ae3a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14001ae40  call    cs:__imp_CoRevertToSelf
0x14001ae47  nop     dword ptr [rax+rax+00h]
0x14001ae4c  mov     rax, [rsp+0B8h+TokenHandle]
0x14001ae51  mov     [rsp+0B8h+var_70], rax
0x14001ae56  mov     [rsp+0B8h+TokenHandle], rsi
0x14001ae5b  mov     rax, [rsp+0B8h+hObject]
0x14001ae60  mov     [rsp+0B8h+var_68], rax
0x14001ae65  mov     [rsp+0B8h+hObject], rsi
0x14001ae6a  lea     r8, [rsp+0B8h+var_70]
0x14001ae6f  lea     rdx, [rsp+0B8h+var_68]
0x14001ae74  mov     rcx, [r15+8]
0x14001ae78  call    _lambda_34446dcb70f9648d12f61e8c6e9f58a2___operator__
0x14001ae7d  mov     ebx, eax
0x14001ae7f  lea     rcx, [rsp+0B8h+var_48]
0x14001ae84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001ae89  nop
0x14001ae8a  lea     rcx, [rsp+0B8h+TokenHandle]
0x14001ae8f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001ae94  nop
0x14001ae95  lea     rcx, [rsp+0B8h+hObject]
0x14001ae9a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001ae9f  mov     eax, ebx
0x14001aea1  mov     rcx, [rsp+0B8h+var_40]
0x14001aea6  xor     rcx, rsp; StackCookie
0x14001aea9  call    __security_check_cookie
0x14001aeae  add     rsp, 88h
0x14001aeb5  pop     r15
0x14001aeb7  pop     r14
0x14001aeb9  pop     r12
0x14001aebb  pop     rdi
0x14001aebc  pop     rsi
0x14001aebd  pop     rbx
0x14001aebe  retn
0x14001aec0  mov     rbx, [rsp+0B8h+TokenHandle]
0x14001aec5  lea     rax, [rbx-1]
0x14001aec9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001aecd  ja      short loc_14001AEF2
0x14001aecf  lea     rcx, [rsp+0B8h+var_78]; this
0x14001aed4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001aed9  mov     rcx, rbx; hObject
0x14001aedc  call    cs:__imp_CloseHandle
0x14001aee3  nop     dword ptr [rax+rax+00h]
0x14001aee8  lea     rcx, [rsp+0B8h+var_78]; this
0x14001aeed  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001aef2  mov     [rsp+0B8h+TokenHandle], rsi
0x14001aef7  call    cs:__imp_GetCurrentThread
0x14001aefe  nop     dword ptr [rax+rax+00h]
0x14001af03  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x14001af08  mov     edx, 0Ch; DesiredAccess
0x14001af0d  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x14001af11  mov     rcx, rax; ThreadHandle
0x14001af14  call    cs:__imp_OpenThreadToken
0x14001af1b  nop     dword ptr [rax+rax+00h]
0x14001af20  test    eax, eax
0x14001af22  jnz     loc_14001AE4C
0x14001af28  mov     rbx, [rsp+0B8h+TokenHandle]
0x14001af2d  lea     rax, [rbx-1]
0x14001af31  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001af35  ja      short loc_14001AF5A
0x14001af37  lea     rcx, [rsp+0B8h+var_78]; this
0x14001af3c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001af41  mov     rcx, rbx; hObject
0x14001af44  call    cs:__imp_CloseHandle
0x14001af4b  nop     dword ptr [rax+rax+00h]
0x14001af50  lea     rcx, [rsp+0B8h+var_78]; this
0x14001af55  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001af5a  mov     [rsp+0B8h+TokenHandle], rsi
0x14001af5f  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x14001af64  mov     edx, 0Ah; DesiredAccess
0x14001af69  mov     rcx, [rsp+0B8h+hObject]; ProcessHandle
0x14001af6e  call    cs:__imp_OpenProcessToken
0x14001af75  nop     dword ptr [rax+rax+00h]
0x14001af7a  mov     rcx, [rsp+0B8h]; this
0x14001af82  test    eax, eax
0x14001af84  jnz     loc_14001AE4C
0x14001af8a  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001af91  lea     edx, [rax+59h]; void *
0x14001af94  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
