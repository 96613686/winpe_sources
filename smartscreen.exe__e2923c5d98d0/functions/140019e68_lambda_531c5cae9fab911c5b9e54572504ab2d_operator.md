# _lambda_531c5cae9fab911c5b9e54572504ab2d_::operator()

- ea: `0x140019e68`
- end: `0x14001a1b1`
- name: `_lambda_531c5cae9fab911c5b9e54572504ab2d_::operator()`
- size: `841`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140030afc`

## callees

- `0x140002ea8`
- `0x140005260`
- `0x140005e4c`
- `0x14000c498`
- `0x140019e68`
- `0x14001a1b8`
- `0x14001a1dc`
- `0x14001ca90`
- `0x140025aa0`
- `0x14002f250`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001a05a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001a13d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001a05a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001a13d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001a043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001a126`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001a043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001a126`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001a18b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001a18b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019f7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019f90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019f7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019f90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a167`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a167`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140019fb4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140019fb4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140019fe6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140019fe6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140019eb6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140019eb6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001a07c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001a07c`

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
0x140019e68  mov     r11, rsp
0x140019e6b  push    rbx
0x140019e6c  push    rsi
0x140019e6d  push    rdi
0x140019e6e  push    r12
0x140019e70  push    r14
0x140019e72  push    r15
0x140019e74  sub     rsp, 88h
0x140019e7b  mov     rax, cs:__security_cookie
0x140019e82  xor     rax, rsp
0x140019e85  mov     [rsp+0B8h+var_40], rax
0x140019e8a  mov     r14, rcx
0x140019e8d  mov     r15, rcx
0x140019e90  mov     [rsp+0B8h+var_70], rcx
0x140019e95  xor     esi, esi
0x140019e97  mov     [r11-50h], rsi
0x140019e9b  mov     [r11-58h], rsi
0x140019e9f  mov     [r11-48h], rsi
0x140019ea3  lea     rcx, [r11-48h]
0x140019ea7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ICallingProcessInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICallingProcessInfo>>)
0x140019eac  mov     rdx, rax; ppInterface
0x140019eaf  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x140019eb6  call    cs:__imp_CoGetCallContext
0x140019ebc  mov     rcx, [r15]
0x140019ebf  cmp     [rcx+80h], sil
0x140019ec6  jz      loc_140019F69
0x140019ecc  mov     rcx, [rsp+0B8h]; this
0x140019ed4  test    eax, eax
0x140019ed6  jns     short loc_140019EEA
0x140019ed8  mov     r9d, eax; char *
0x140019edb  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140019ee2  lea     edx, [rsi+43h]; void *
0x140019ee5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140019eea  mov     rdi, [rsp+0B8h+var_48]
0x140019eef  mov     rax, [rdi]
0x140019ef2  mov     r12, [rax+18h]
0x140019ef6  mov     rbx, [rsp+0B8h+hObject]
0x140019efb  lea     rax, [rbx-1]
0x140019eff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019f03  ja      short loc_140019F22
0x140019f05  lea     rcx, [rsp+0B8h+var_68]; this
0x140019f0a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140019f0f  mov     rcx, rbx; hObject
0x140019f12  call    cs:__imp_CloseHandle
0x140019f18  lea     rcx, [rsp+0B8h+var_68]; this
0x140019f1d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140019f22  mov     [rsp+0B8h+hObject], rsi
0x140019f27  lea     r8, [rsp+0B8h+hObject]
0x140019f2c  mov     edx, 400h
0x140019f31  mov     rcx, rdi
0x140019f34  mov     rax, r12
0x140019f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f3c  mov     rcx, [rsp+0B8h]; this
0x140019f44  test    eax, eax
0x140019f46  jns     short loc_140019F5D
0x140019f48  mov     r9d, eax; char *
0x140019f4b  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140019f52  mov     edx, 44h ; 'D'; void *
0x140019f57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140019f5d  jmp     short loc_140019F69
0x140019f5f  xor     esi, esi
0x140019f61  mov     r15, [rsp+0B8h+var_70]
0x140019f66  mov     r14, r15
0x140019f69  mov     rax, [rsp+0B8h+hObject]
0x140019f6e  inc     rax
0x140019f71  test    rax, 0FFFFFFFFFFFFFFFEh
0x140019f77  jnz     short loc_140019FD6
0x140019f79  mov     [rsp+0B8h+hObject], rsi
0x140019f7e  call    cs:__imp_GetCurrentProcess
0x140019f84  mov     rdi, rax
0x140019f87  call    cs:__imp_GetCurrentProcess
0x140019f8d  mov     rbx, rax
0x140019f90  call    cs:__imp_GetCurrentProcess
0x140019f96  mov     [rsp+0B8h+dwOptions], 2; dwOptions
0x140019f9e  mov     [rsp+0B8h+bInheritHandle], esi; bInheritHandle
0x140019fa2  mov     [rsp+0B8h+dwDesiredAccess], esi; dwDesiredAccess
0x140019fa6  lea     r9, [rsp+0B8h+hObject]; lpTargetHandle
0x140019fab  mov     r8, rdi; hTargetProcessHandle
0x140019fae  mov     rdx, rbx; hSourceHandle
0x140019fb1  mov     rcx, rax; hSourceProcessHandle
0x140019fb4  call    cs:__imp_DuplicateHandle
0x140019fba  mov     rcx, [rsp+0B8h]; this
0x140019fc2  test    eax, eax
0x140019fc4  jnz     short loc_140019FD6
0x140019fc6  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140019fcd  lea     edx, [rax+4Bh]; void *
0x140019fd0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140019fd6  mov     rax, [r14]
0x140019fd9  cmp     [rax+80h], sil
0x140019fe0  jz      loc_14001A0F5
0x140019fe6  call    cs:__imp_CoImpersonateClient
0x140019fec  mov     rcx, [rsp+0B8h]; this
0x140019ff4  test    eax, eax
0x140019ff6  jns     short loc_14001A00D
0x140019ff8  mov     r9d, eax; char *
0x140019ffb  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001a002  mov     edx, 50h ; 'P'; void *
0x14001a007  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001a00d  mov     [rsp+0B8h+var_5F], 1
0x14001a012  mov     rbx, [rsp+0B8h+TokenHandle]
0x14001a017  lea     rax, [rbx-1]
0x14001a01b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a01f  ja      short loc_14001A03E
0x14001a021  lea     rcx, [rsp+0B8h+var_78]; this
0x14001a026  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001a02b  mov     rcx, rbx; hObject
0x14001a02e  call    cs:__imp_CloseHandle
0x14001a034  lea     rcx, [rsp+0B8h+var_78]; this
0x14001a039  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001a03e  mov     [rsp+0B8h+TokenHandle], rsi
0x14001a043  call    cs:__imp_GetCurrentThread
0x14001a049  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x14001a04e  mov     edx, 0Ch; DesiredAccess
0x14001a053  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x14001a057  mov     rcx, rax; ThreadHandle
0x14001a05a  call    cs:__imp_OpenThreadToken
0x14001a060  mov     rcx, [rsp+0B8h]; this
0x14001a068  test    eax, eax
0x14001a06a  jnz     short loc_14001A07C
0x14001a06c  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001a073  lea     edx, [rax+53h]; void *
0x14001a076  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14001a07c  call    cs:__imp_CoRevertToSelf
0x14001a082  mov     rax, [rsp+0B8h+TokenHandle]
0x14001a087  mov     [rsp+0B8h+var_70], rax
0x14001a08c  mov     [rsp+0B8h+TokenHandle], rsi
0x14001a091  mov     rax, [rsp+0B8h+hObject]
0x14001a096  mov     [rsp+0B8h+var_68], rax
0x14001a09b  mov     [rsp+0B8h+hObject], rsi
0x14001a0a0  lea     r8, [rsp+0B8h+var_70]
0x14001a0a5  lea     rdx, [rsp+0B8h+var_68]
0x14001a0aa  mov     rcx, [r15+8]
0x14001a0ae  call    _lambda_34446dcb70f9648d12f61e8c6e9f58a2___operator__
0x14001a0b3  mov     ebx, eax
0x14001a0b5  lea     rcx, [rsp+0B8h+var_48]
0x14001a0ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001a0bf  nop
0x14001a0c0  lea     rcx, [rsp+0B8h+TokenHandle]
0x14001a0c5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001a0ca  nop
0x14001a0cb  lea     rcx, [rsp+0B8h+hObject]
0x14001a0d0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001a0d5  mov     eax, ebx
0x14001a0d7  mov     rcx, [rsp+0B8h+var_40]
0x14001a0dc  xor     rcx, rsp; StackCookie
0x14001a0df  call    __security_check_cookie
0x14001a0e4  add     rsp, 88h
0x14001a0eb  pop     r15
0x14001a0ed  pop     r14
0x14001a0ef  pop     r12
0x14001a0f1  pop     rdi
0x14001a0f2  pop     rsi
0x14001a0f3  pop     rbx
0x14001a0f4  retn
0x14001a0f5  mov     rbx, [rsp+0B8h+TokenHandle]
0x14001a0fa  lea     rax, [rbx-1]
0x14001a0fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a102  ja      short loc_14001A121
0x14001a104  lea     rcx, [rsp+0B8h+var_78]; this
0x14001a109  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001a10e  mov     rcx, rbx; hObject
0x14001a111  call    cs:__imp_CloseHandle
0x14001a117  lea     rcx, [rsp+0B8h+var_78]; this
0x14001a11c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001a121  mov     [rsp+0B8h+TokenHandle], rsi
0x14001a126  call    cs:__imp_GetCurrentThread
0x14001a12c  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x14001a131  mov     edx, 0Ch; DesiredAccess
0x14001a136  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x14001a13a  mov     rcx, rax; ThreadHandle
0x14001a13d  call    cs:__imp_OpenThreadToken
0x14001a143  test    eax, eax
0x14001a145  jnz     loc_14001A082
0x14001a14b  mov     rbx, [rsp+0B8h+TokenHandle]
0x14001a150  lea     rax, [rbx-1]
0x14001a154  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001a158  ja      short loc_14001A177
0x14001a15a  lea     rcx, [rsp+0B8h+var_78]; this
0x14001a15f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001a164  mov     rcx, rbx; hObject
0x14001a167  call    cs:__imp_CloseHandle
0x14001a16d  lea     rcx, [rsp+0B8h+var_78]; this
0x14001a172  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001a177  mov     [rsp+0B8h+TokenHandle], rsi
0x14001a17c  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x14001a181  mov     edx, 0Ah; DesiredAccess
0x14001a186  mov     rcx, [rsp+0B8h+hObject]; ProcessHandle
0x14001a18b  call    cs:__imp_OpenProcessToken
0x14001a191  mov     rcx, [rsp+0B8h]; this
0x14001a199  test    eax, eax
0x14001a19b  jnz     loc_14001A082
0x14001a1a1  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001a1a8  lea     edx, [rax+59h]; void *
0x14001a1ab  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
