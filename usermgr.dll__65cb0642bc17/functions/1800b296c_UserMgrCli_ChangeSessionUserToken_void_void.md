# UserMgrCli::ChangeSessionUserToken(void *,void *)

- ea: `0x1800b296c`
- end: `0x1800b2cc1`
- name: `?ChangeSessionUserToken@UserMgrCli@@QEAAJPEAX0@Z`
- size: `853`
- prototype: `int(UserMgrCli *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b5e30`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008b10`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c6d0`
- `0x18000cd30`
- `0x18000ce48`
- `0x180012890`
- `0x180015250`
- `0x180015960`
- `0x18002799c`
- `0x18004e58c`
- `0x18006f1c9`
- `0x1800b296c`
- `0x1800b6560`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b2a87`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b2a5d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b2aa8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b2a5d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b2aa8`

## string_xrefs

- `0x1800b2c10`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c24`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c35`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c46`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c5a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c6e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c85`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2c9a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b2cae`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UserMgrCli::ChangeSessionUserToken(UserMgrCli *this, void *a2, void *a3)
{
  unsigned __int64 v3; // rbp
  const struct _tlgProvider_t *v5; // rax
  void *v6; // rdx
  int BasicCallerInformation; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  const char *v10; // r9
  HANDLE v11; // rbx
  HANDLE v12; // rax
  const char *v13; // r9
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, void *, unsigned __int64); // rbx
  int v17; // eax
  int v18; // eax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  void *v23; // rdx
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 result; // rax
  _DWORD *v28; // rbp
  const struct _tlgProvider_t *v29; // rax
  int v30; // ebx
  wil *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  int dwDesiredAccess; // [rsp+20h] [rbp-40h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-40h]
  int v36; // [rsp+60h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+268h] [rbp+208h]

  v3 = (unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL;
  v5 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v5 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v5,
      byte_180128FAB,
      0);
  memset_0((void *)(v3 + 64), 0, 0x1A0u);
  try
  {
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    if ( byte_1801481CC )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB94,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8000FFFFLL,
        dwDesiredAccess);
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               retaddr,
                               v6,
                               (struct _BASIC_CALLER_INFORMATION *)(v3 + 64));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB96,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        dwDesiredAccess);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v3 + 64),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135E8);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v3 + 16,
      0);
    CurrentProcess = GetCurrentProcess();
    v9 = GetCurrentProcess();
    if ( !DuplicateHandle(v9, a3, CurrentProcess, (LPHANDLE)(v3 + 16), 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBA0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v10);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v3 + 8,
      0);
    v11 = GetCurrentProcess();
    v12 = GetCurrentProcess();
    if ( !DuplicateHandle(v12, a3, v11, (LPHANDLE)(v3 + 8), 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBA9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v13);
    v14 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v3 + 40));
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBAF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v14,
        dwDesiredAccessa);
    v15 = *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    v16 = *(__int64 (__fastcall **)(__int64, void *, unsigned __int64))(*(_QWORD *)v15 + 176LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 24);
    v17 = v16(v15, a3, v3 + 24);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBB0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v17,
        dwDesiredAccessa);
    if ( !*(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBB1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        dwDesiredAccessa);
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v3 + 24),
            (__int64 *)(v3 + 32));
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBB4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v18,
        dwDesiredAccessa);
    v19 = *(__int64 **)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    v20 = *v19;
    v21 = *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v20 + 144))(v19, v21);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBB5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v22,
        dwDesiredAccessa);
    v23 = *(void **)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    *(_QWORD *)(((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    UserManagerTokenAndShellHandler::ChangeSessionUserToken((UserManagerTokenAndShellHandler *)qword_180148188, v23);
    v24 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v24 > 4u )
    {
      *(_DWORD *)v3 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v24,
        (unsigned int)word_180128F22,
        v25,
        v26,
        (unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v3 + 8);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v3 + 16);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3 + 40);
    result = 0;
  }
  catch ( ... )
  {
    v28 = (_DWORD *)((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL);
    v29 = UserMgrUserModelTelemetry::Provider();
    v30 = (int)v29;
    v31 = (wil *)*(unsigned int *)v29;
    if ( (unsigned int)v31 > 4 )
    {
      *v28 = wil::ResultFromCaughtException(v31);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)byte_180128F5D,
        v32,
        v33,
        (__int64)v28);
    }
    *v28 = wil::ResultFromCaughtException(v31);
    return *(unsigned int *)((unsigned __int64)&v36 & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x1800b296c  mov     [rsp-8+arg_0], rbx
0x1800b2971  mov     [rsp-8+arg_8], rsi
0x1800b2976  push    rbp
0x1800b2977  push    rdi
0x1800b2978  push    r14
0x1800b297a  sub     rsp, 250h
0x1800b2981  lea     rbp, [rsp+60h]
0x1800b2986  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800b298a  mov     rax, cs:__security_cookie
0x1800b2991  xor     rax, rsp
0x1800b2994  mov     [rbp+200h+var_20], rax
0x1800b299b  mov     rsi, r8
0x1800b299e  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b29a3  mov     ecx, [rax]
0x1800b29a5  cmp     ecx, 4
0x1800b29a8  jbe     short loc_1800B29BC
0x1800b29aa  xor     r8d, r8d
0x1800b29ad  lea     rdx, byte_180128FAB
0x1800b29b4  mov     rcx, rax
0x1800b29b7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b29bc  xor     edx, edx; Val
0x1800b29be  mov     r8d, 1A0h; Size
0x1800b29c4  lea     rcx, [rbp+200h+var_1C0]; void *
0x1800b29c8  call    memset_0
0x1800b29cd  xor     r14d, r14d
0x1800b29d0  mov     [rbp+200h+var_1D8], r14
0x1800b29d4  mov     [rbp+200h+var_1E8], r14
0x1800b29d8  mov     [rbp+200h+TargetHandle], r14
0x1800b29dc  mov     [rbp+200h+var_1F8], r14
0x1800b29e0  cmp     cs:byte_1801481CC, r14b
0x1800b29e7  setnz   al
0x1800b29ea  mov     rcx, [rsp+268h]; this
0x1800b29f2  test    al, al
0x1800b29f4  jnz     loc_1800B2C0A
0x1800b29fa  lea     r8, [rbp+200h+var_1C0]; struct _BASIC_CALLER_INFORMATION *
0x1800b29fe  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x1800b2a03  mov     rcx, [rsp+268h]; this
0x1800b2a0b  test    eax, eax
0x1800b2a0d  js      loc_1800B2C21
0x1800b2a13  lea     r8, byte_1801135E8; struct _CALLER_RESTRICTIONS *
0x1800b2a1a  lea     rdx, [rbp+200h+var_1C0]; struct _BASIC_CALLER_INFORMATION *
0x1800b2a1e  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x1800b2a23  xor     edx, edx
0x1800b2a25  lea     rcx, [rbp+200h+TargetHandle]
0x1800b2a29  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b2a2e  call    cs:__imp_GetCurrentProcess
0x1800b2a34  mov     rbx, rax
0x1800b2a37  call    cs:__imp_GetCurrentProcess
0x1800b2a3d  mov     edi, 2
0x1800b2a42  mov     [rsp+260h+dwOptions], edi; dwOptions
0x1800b2a46  mov     [rsp+260h+bInheritHandle], r14d; bInheritHandle
0x1800b2a4b  mov     [rsp+260h+dwDesiredAccess], r14d; dwDesiredAccess
0x1800b2a50  lea     r9, [rbp+200h+TargetHandle]; lpTargetHandle
0x1800b2a54  mov     r8, rbx; hTargetProcessHandle
0x1800b2a57  mov     rdx, rsi; hSourceHandle
0x1800b2a5a  mov     rcx, rax; hSourceProcessHandle
0x1800b2a5d  call    cs:__imp_DuplicateHandle
0x1800b2a63  mov     rcx, [rsp+268h]; this
0x1800b2a6b  test    eax, eax
0x1800b2a6d  jz      loc_1800B2C35
0x1800b2a73  xor     edx, edx
0x1800b2a75  lea     rcx, [rbp+200h+var_1F8]
0x1800b2a79  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b2a7e  call    cs:__imp_GetCurrentProcess
0x1800b2a84  mov     rbx, rax
0x1800b2a87  call    cs:__imp_GetCurrentProcess
0x1800b2a8d  mov     [rsp+260h+dwOptions], edi; dwOptions
0x1800b2a91  mov     [rsp+260h+bInheritHandle], r14d; bInheritHandle
0x1800b2a96  mov     [rsp+260h+dwDesiredAccess], r14d; int
0x1800b2a9b  lea     r9, [rbp+200h+var_1F8]; lpTargetHandle
0x1800b2a9f  mov     r8, rbx; hTargetProcessHandle
0x1800b2aa2  mov     rdx, rsi; hSourceHandle
0x1800b2aa5  mov     rcx, rax; hSourceProcessHandle
0x1800b2aa8  call    cs:__imp_DuplicateHandle
0x1800b2aae  mov     rcx, [rsp+268h]; this
0x1800b2ab6  test    eax, eax
0x1800b2ab8  jz      loc_1800B2C46
0x1800b2abe  lea     rcx, [rbp+200h+var_1D8]
0x1800b2ac2  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x1800b2ac7  mov     rcx, [rsp+268h]; this
0x1800b2acf  test    eax, eax
0x1800b2ad1  js      loc_1800B2C57
0x1800b2ad7  mov     rdi, [rbp+200h+var_1D8]
0x1800b2adb  mov     rax, [rdi]
0x1800b2ade  mov     rbx, [rax+0B0h]
0x1800b2ae5  lea     rcx, [rbp+200h+var_1E8]
0x1800b2ae9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b2aee  lea     r8, [rbp+200h+var_1E8]
0x1800b2af2  mov     rdx, rsi
0x1800b2af5  mov     rcx, rdi
0x1800b2af8  mov     rax, rbx
0x1800b2afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b00  mov     rcx, [rsp+268h]; this
0x1800b2b08  test    eax, eax
0x1800b2b0a  js      loc_1800B2C6B
0x1800b2b10  mov     rcx, [rsp+268h]; this
0x1800b2b18  cmp     [rbp+200h+var_1E8], r14
0x1800b2b1c  jz      loc_1800B2C7F
0x1800b2b22  mov     [rbp+200h+var_1E0], r14
0x1800b2b26  lea     rdx, [rbp+200h+var_1E0]
0x1800b2b2a  lea     rcx, [rbp+200h+var_1E8]
0x1800b2b2e  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x1800b2b33  mov     rcx, [rsp+268h]; this
0x1800b2b3b  test    eax, eax
0x1800b2b3d  js      loc_1800B2C97
0x1800b2b43  mov     rcx, [rbp+200h+var_1E0]
0x1800b2b47  mov     rax, [rcx]
0x1800b2b4a  mov     rdx, [rbp+200h+TargetHandle]
0x1800b2b4e  mov     [rbp+200h+TargetHandle], r14
0x1800b2b52  mov     rax, [rax+90h]
0x1800b2b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2b5e  mov     rcx, [rsp+268h]; this
0x1800b2b66  test    eax, eax
0x1800b2b68  js      loc_1800B2CAB
0x1800b2b6e  mov     rdx, [rbp+200h+var_1F8]; void *
0x1800b2b72  mov     [rbp+200h+var_1F8], r14
0x1800b2b76  mov     rcx, cs:qword_180148188; this
0x1800b2b7d  call    ?ChangeSessionUserToken@UserManagerTokenAndShellHandler@@QEAAXPEAX@Z; UserManagerTokenAndShellHandler::ChangeSessionUserToken(void *)
0x1800b2b82  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b2b87  mov     ecx, [rax]
0x1800b2b89  cmp     ecx, 4
0x1800b2b8c  jbe     short loc_1800B2BAB
0x1800b2b8e  mov     [rbp+200h+var_200], r14d
0x1800b2b92  lea     rcx, [rbp+200h+var_200]
0x1800b2b96  mov     qword ptr [rsp+260h+dwDesiredAccess], rcx
0x1800b2b9b  lea     rdx, word_180128F22
0x1800b2ba2  mov     rcx, rax
0x1800b2ba5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b2baa  nop
0x1800b2bab  lea     rcx, [rbp+200h+var_1E0]
0x1800b2baf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b2bb4  nop
0x1800b2bb5  lea     rcx, [rbp+200h+var_1F8]
0x1800b2bb9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b2bbe  nop
0x1800b2bbf  lea     rcx, [rbp+200h+TargetHandle]
0x1800b2bc3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b2bc8  nop
0x1800b2bc9  lea     rcx, [rbp+200h+var_1E8]
0x1800b2bcd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b2bd2  nop
0x1800b2bd3  lea     rcx, [rbp+200h+var_1D8]
0x1800b2bd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b2bdc  xor     eax, eax
0x1800b2bde  jmp     short loc_1800B2BE3
0x1800b2be0  mov     eax, [rbp+200h+var_200]
0x1800b2be3  mov     rcx, [rbp+200h+var_20]
0x1800b2bea  xor     rcx, rsp; StackCookie
0x1800b2bed  call    __security_check_cookie
0x1800b2bf2  lea     r11, [rsp+260h+var_10]
0x1800b2bfa  mov     rbx, [r11+20h]
0x1800b2bfe  mov     rsi, [r11+28h]
0x1800b2c02  mov     rsp, r11
0x1800b2c05  pop     r14
0x1800b2c07  pop     rdi
0x1800b2c08  pop     rbp
0x1800b2c09  retn
0x1800b2c0a  mov     r9d, 8000FFFFh; char *
0x1800b2c10  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c17  mov     edx, 0B94h; void *
0x1800b2c1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2c21  mov     r9d, eax; char *
0x1800b2c24  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c2b  mov     edx, 0B96h; void *
0x1800b2c30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2c35  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c3c  mov     edx, 0BA0h; void *
0x1800b2c41  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800b2c46  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c4d  mov     edx, 0BA9h; void *
0x1800b2c52  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800b2c57  mov     r9d, eax; char *
0x1800b2c5a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c61  mov     edx, 0BAFh; void *
0x1800b2c66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2c6b  mov     r9d, eax; char *
0x1800b2c6e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c75  mov     edx, 0BB0h; void *
0x1800b2c7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2c7f  mov     r9d, 80070520h; char *
0x1800b2c85  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2c8c  mov     edx, 0BB1h; void *
0x1800b2c91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2c97  mov     r9d, eax; char *
0x1800b2c9a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2ca1  mov     edx, 0BB4h; void *
0x1800b2ca6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2cab  mov     r9d, eax; char *
0x1800b2cae  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b2cb5  mov     edx, 0BB5h; void *
0x1800b2cba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
