# Windows::System::Internal::UserManagerStatics::CreateDefaultAccountUser(uint,unsigned __int64,unsigned __int64,Windows::System::IUser * *)

- ea: `0x18008f2a0`
- end: `0x18008f96d`
- name: `?CreateDefaultAccountUser@UserManagerStatics@Internal@System@Windows@@UEAAJI_K0PEAPEAUIUser@34@@Z`
- size: `1741`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int, unsigned __int64, unsigned __int64, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002e34`
- `0x180006130`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x180011490`
- `0x180012890`
- `0x180014e7c`
- `0x180018b60`
- `0x180024580`
- `0x180024828`
- `0x18003322c`
- `0x1800332e8`
- `0x18004e4e8`
- `0x18004e58c`
- `0x1800626e8`
- `0x18006c380`
- `0x18008f2a0`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18008f7ea`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18008f7ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008f5c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008f5c6`

## string_xrefs

- `0x18008f859`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f86d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f87e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f892`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f8a9`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f8ba`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f8ce`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f8e2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f8f6`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f90a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f91e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f932`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f946`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18008f95a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::System::Internal::UserManagerStatics::CreateDefaultAccountUser(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        struct Windows::System::IUser **a5)
{
  void (*v9)(void); // rbx
  void (__fastcall *v10)(void *, __int64 *); // rbx
  const struct _tlgProvider_t *v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  unsigned int (__fastcall *v14)(__int64, __int64, __int64 *); // rbx
  const char *v15; // r9
  int v16; // eax
  void *v17; // rax
  WCHAR *v18; // rbx
  const char *v19; // r9
  HRESULT v20; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // r10
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v33; // rax
  int v34; // ebx
  wil *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  int v38; // [rsp+20h] [rbp-3D8h]
  int v39; // [rsp+20h] [rbp-3D8h]
  UINT32 length; // [rsp+60h] [rbp-398h] BYREF
  unsigned int v41; // [rsp+64h] [rbp-394h] BYREF
  int v42; // [rsp+68h] [rbp-390h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-388h]
  __int64 v44; // [rsp+78h] [rbp-380h] BYREF
  PCNZWCH sourceString; // [rsp+80h] [rbp-378h] BYREF
  HSTRING v46; // [rsp+88h] [rbp-370h] BYREF
  __int64 v47; // [rsp+90h] [rbp-368h] BYREF
  struct Windows::System::IUser *v48; // [rsp+98h] [rbp-360h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-358h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-350h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-348h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-340h] BYREF
  int v53; // [rsp+C0h] [rbp-338h]
  int v54; // [rsp+C4h] [rbp-334h]
  HSTRING string; // [rsp+C8h] [rbp-330h] BYREF
  unsigned __int64 v56; // [rsp+D0h] [rbp-328h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-320h]
  __int64 v58; // [rsp+E0h] [rbp-318h]
  unsigned int *v59; // [rsp+110h] [rbp-2E8h]
  __int64 v60; // [rsp+118h] [rbp-2E0h]
  __int64 *v61; // [rsp+120h] [rbp-2D8h]
  __int64 v62; // [rsp+128h] [rbp-2D0h]
  __int64 *v63; // [rsp+130h] [rbp-2C8h]
  __int64 v64; // [rsp+138h] [rbp-2C0h]
  __int64 v65[12]; // [rsp+140h] [rbp-2B8h] BYREF
  int v66; // [rsp+1A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v43 = a2;
  v58 = a3;
  v57 = a4;
  v49 = 0;
  v52 = 0;
  v48 = 0;
  v47 = 0;
  v9 = *(void (**)(void))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  try
  {
    v9();
    v10 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    v10(&Windows::System::Internal::Adapters::g_AdapterCollection, &v52);
    length = 0;
    sourceString = 0;
    v53 = 0;
    v51 = 0;
    v46 = 0;
    string = 0;
    v11 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      v50 = a4;
      v44 = a3;
      v41 = a2;
      v63 = &v50;
      v64 = 8;
      v61 = &v44;
      v62 = 8;
      v59 = &v41;
      v60 = 4;
      v38 = 5;
      tlgWriteTransfer_EventWriteTransfer(v11, &dword_180125A74, 0, 0);
    }
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12D4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v38);
    *a5 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v52 + 24LL))(v52, a3, 1, v65);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x12D9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v12,
        84);
    v13 = v49;
    v14 = *(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v51,
      0);
    if ( !v14(v13, v65[0], &v51) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x12DB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        v15);
    v44 = v51;
    v16 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v46);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12DC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v16,
        84);
    length = 513;
    v17 = operator new[](0x404u, (const struct std::nothrow_t *)std::nothrow);
    std::unique_ptr<unsigned short [0]>::reset(&sourceString, v17);
    v18 = (WCHAR *)sourceString;
    if ( !sourceString )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12E0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x8007000ELL,
        84);
    LOWORD(v66) = 0;
    v42 = 260;
    v54 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, PCNZWCH, UINT32 *))(*(_QWORD *)v49 + 104LL))(
            v49,
            v65[0],
            sourceString,
            &length) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x12E6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        v19);
    v20 = WindowsCreateString(v18, length, &string);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12E8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v20,
        (int)&v66);
    UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)((char *)this - 112));
    v22 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, __int64, HSTRING, __int64))(*(_QWORD *)UserStaticsInternal + 104LL))(
            UserStaticsInternal,
            0x100000,
            string,
            a3);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v22,
        0);
    v23 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v48,
            &v47);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v23,
        0);
    v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 56LL))(v47, 1);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v24,
        0);
    v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 136LL))(v47, 4);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v25,
        0);
    v26 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 53) + 80LL))(*((_QWORD *)this + 53), v46);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v26,
        0);
    v56 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v47 + 88LL))(v47, &v56);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12FC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v27,
        0);
    v28 = Windows::System::Internal::UserManagerStatics::SendServiceAndLsaNotification(retaddr, 1, v56, a2, 0);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12FD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v28,
        v39);
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
    *a5 = v48;
    v29 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v29 > 5u )
    {
      v41 = 0;
      v44 = a4;
      v50 = a3;
      LODWORD(sourceString) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v29,
        (unsigned int)&byte_180125A0F,
        v30,
        v31,
        (__int64)&sourceString,
        (__int64)&v50,
        (__int64)&v44,
        (__int64)&v41);
    }
    WindowsDeleteString(v46);
    v46 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v51);
    operator delete[](v18);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    result = 0;
  }
  catch ( ... )
  {
    v33 = UserMgrUserModelTelemetry::Provider();
    v34 = (int)v33;
    v35 = (wil *)*(unsigned int *)v33;
    if ( (unsigned int)v35 > 5 )
    {
      LODWORD(sourceString) = wil::ResultFromCaughtException(v35);
      v44 = v57;
      v50 = v58;
      v42 = v43;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v34,
        (unsigned int)&byte_180125997,
        v36,
        v37,
        (__int64)&v42,
        (__int64)&v50,
        (__int64)&v44,
        (__int64)&sourceString);
    }
    return (unsigned int)wil::ResultFromCaughtException(v35);
  }
  return result;
}

```

## disassembly

```asm
0x18008f2a0  mov     r11, rsp
0x18008f2a3  push    rbx
0x18008f2a4  push    rsi
0x18008f2a5  push    rdi
0x18008f2a6  push    r12
0x18008f2a8  push    r13
0x18008f2aa  push    r14
0x18008f2ac  push    r15
0x18008f2ae  sub     rsp, 3C0h
0x18008f2b5  mov     rax, cs:__security_cookie
0x18008f2bc  xor     rax, rsp
0x18008f2bf  mov     [rsp+3F8h+var_48], rax
0x18008f2c7  mov     r15, r9
0x18008f2ca  mov     r14, r8
0x18008f2cd  mov     esi, edx
0x18008f2cf  mov     r13, rcx
0x18008f2d2  mov     [rsp+3F8h+var_388], edx
0x18008f2d6  mov     [rsp+3F8h+var_318], r8
0x18008f2de  mov     [rsp+3F8h+var_320], r9
0x18008f2e6  mov     r12, [rsp+3F8h+arg_20]
0x18008f2ee  xor     edi, edi
0x18008f2f0  mov     [r11-358h], rdi
0x18008f2f7  mov     [r11-340h], rdi
0x18008f2fe  mov     [r11-360h], rdi
0x18008f305  mov     [r11-368h], rdi
0x18008f30c  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18008f313  mov     rbx, [rax+38h]
0x18008f317  lea     rcx, [r11-358h]
0x18008f31e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008f323  lea     rdx, [rsp+3F8h+var_358]
0x18008f32b  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18008f332  mov     rax, rbx
0x18008f335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f33a  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18008f341  mov     rbx, [rax+58h]
0x18008f345  lea     rcx, [rsp+3F8h+var_340]
0x18008f34d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008f352  lea     rdx, [rsp+3F8h+var_340]
0x18008f35a  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18008f361  mov     rax, rbx
0x18008f364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f369  mov     [rsp+3F8h+length], edi
0x18008f36d  mov     [rsp+3F8h+sourceString], rdi
0x18008f375  mov     [rsp+3F8h+var_338], edi
0x18008f37c  mov     [rsp+3F8h+var_348], rdi
0x18008f384  mov     [rsp+3F8h+var_370], rdi
0x18008f38c  mov     [rsp+3F8h+string], rdi
0x18008f394  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18008f399  mov     ecx, [rax]
0x18008f39b  cmp     ecx, 5
0x18008f39e  jbe     loc_18008F42D
0x18008f3a4  mov     [rsp+3F8h+var_350], r15
0x18008f3ac  mov     [rsp+3F8h+var_380], r14
0x18008f3b1  mov     [rsp+3F8h+var_394], esi
0x18008f3b5  lea     rcx, [rsp+3F8h+var_350]
0x18008f3bd  mov     [rsp+3F8h+var_2C8], rcx
0x18008f3c5  mov     [rsp+3F8h+var_2C0], 8
0x18008f3d1  lea     rcx, [rsp+3F8h+var_380]
0x18008f3d6  mov     [rsp+3F8h+var_2D8], rcx
0x18008f3de  mov     [rsp+3F8h+var_2D0], 8
0x18008f3ea  lea     rcx, [rsp+3F8h+var_394]
0x18008f3ef  mov     [rsp+3F8h+var_2E8], rcx
0x18008f3f7  mov     [rsp+3F8h+var_2E0], 4
0x18008f403  lea     rcx, [rsp+3F8h+var_308]
0x18008f40b  mov     [rsp+3F8h+var_3D0], rcx
0x18008f410  mov     dword ptr [rsp+3F8h+var_3D8], 5; int
0x18008f418  xor     r9d, r9d
0x18008f41b  xor     r8d, r8d
0x18008f41e  lea     rdx, dword_180125A74
0x18008f425  mov     rcx, rax
0x18008f428  call    _tlgWriteTransfer_EventWriteTransfer
0x18008f42d  mov     rcx, [rsp+3F8h]; this
0x18008f435  test    r12, r12
0x18008f438  jz      loc_18008F853
0x18008f43e  mov     [r12], rdi
0x18008f442  mov     rcx, [rsp+3F8h+var_340]
0x18008f44a  mov     rax, [rcx]
0x18008f44d  lea     rdx, [rsp+3F8h+var_338]
0x18008f455  mov     [rsp+3F8h+var_3D0], rdx
0x18008f45a  mov     dword ptr [rsp+3F8h+var_3D8], 54h ; 'T'; int
0x18008f462  lea     r9, [rsp+3F8h+var_2B8]
0x18008f46a  mov     r8d, 1
0x18008f470  mov     rdx, r14
0x18008f473  mov     rax, [rax+18h]
0x18008f477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f47c  mov     rcx, [rsp+3F8h]; this
0x18008f484  test    eax, eax
0x18008f486  js      loc_18008F86A
0x18008f48c  mov     rdi, [rsp+3F8h+var_358]
0x18008f494  mov     rax, [rdi]
0x18008f497  mov     rbx, [rax+20h]
0x18008f49b  xor     edx, edx
0x18008f49d  lea     rcx, [rsp+3F8h+var_348]
0x18008f4a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008f4aa  lea     r8, [rsp+3F8h+var_348]
0x18008f4b2  mov     rdx, [rsp+3F8h+var_2B8]
0x18008f4ba  mov     rcx, rdi
0x18008f4bd  mov     rax, rbx
0x18008f4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4c5  mov     rcx, [rsp+3F8h]; this
0x18008f4cd  xor     edi, edi
0x18008f4cf  test    eax, eax
0x18008f4d1  jz      loc_18008F87E
0x18008f4d7  mov     rax, [rsp+3F8h+var_348]
0x18008f4df  mov     [rsp+3F8h+var_380], rax
0x18008f4e4  lea     rdx, [rsp+3F8h+var_380]
0x18008f4e9  lea     rcx, [rsp+3F8h+var_370]; string
0x18008f4f1  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18008f4f6  mov     rcx, [rsp+3F8h]; this
0x18008f4fe  test    eax, eax
0x18008f500  js      loc_18008F88F
0x18008f506  mov     [rsp+3F8h+length], 201h
0x18008f50e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008f515  mov     ecx, 404h; unsigned __int64
0x18008f51a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008f51f  mov     rdx, rax
0x18008f522  lea     rcx, [rsp+3F8h+sourceString]
0x18008f52a  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18008f52f  mov     rcx, [rsp+3F8h]; this
0x18008f537  mov     rbx, [rsp+3F8h+sourceString]
0x18008f53f  test    rbx, rbx
0x18008f542  jz      loc_18008F8A3
0x18008f548  mov     word ptr [rsp+3F8h+var_258], di
0x18008f550  mov     [rsp+3F8h+var_390], 104h
0x18008f558  mov     [rsp+3F8h+var_334], edi
0x18008f55f  mov     rcx, [rsp+3F8h+var_358]
0x18008f567  mov     rax, [rcx]
0x18008f56a  lea     rdx, [rsp+3F8h+var_334]
0x18008f572  mov     [rsp+3F8h+var_3C8], rdx
0x18008f577  lea     rdx, [rsp+3F8h+var_390]
0x18008f57c  mov     [rsp+3F8h+var_3D0], rdx
0x18008f581  lea     rdx, [rsp+3F8h+var_258]
0x18008f589  mov     [rsp+3F8h+var_3D8], rdx; int
0x18008f58e  lea     r9, [rsp+3F8h+length]
0x18008f593  mov     r8, rbx
0x18008f596  mov     rdx, [rsp+3F8h+var_2B8]
0x18008f59e  mov     rax, [rax+68h]
0x18008f5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f5a7  mov     rcx, [rsp+3F8h]; this
0x18008f5af  test    eax, eax
0x18008f5b1  jz      loc_18008F8BA
0x18008f5b7  lea     r8, [rsp+3F8h+string]; string
0x18008f5bf  mov     edx, [rsp+3F8h+length]; length
0x18008f5c3  mov     rcx, rbx; sourceString
0x18008f5c6  call    cs:__imp_WindowsCreateString
0x18008f5cc  mov     rcx, [rsp+3F8h]; this
0x18008f5d4  test    eax, eax
0x18008f5d6  js      loc_18008F8CB
0x18008f5dc  lea     rcx, [r13-70h]; this
0x18008f5e0  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18008f5e5  mov     r10, rax
0x18008f5e8  mov     rdx, [rsp+3F8h+var_370]
0x18008f5f0  mov     rcx, [rax]
0x18008f5f3  mov     rax, [rcx+68h]
0x18008f5f7  lea     rcx, [rsp+3F8h+var_360]
0x18008f5ff  mov     [rsp+3F8h+var_3A8], rcx
0x18008f604  mov     [rsp+3F8h+var_3B0], esi
0x18008f608  mov     [rsp+3F8h+var_3B8], rdi
0x18008f60d  mov     [rsp+3F8h+var_3C0], rdx
0x18008f612  mov     [rsp+3F8h+var_3C8], r15
0x18008f617  mov     [rsp+3F8h+var_3D0], rdi
0x18008f61c  mov     dword ptr [rsp+3F8h+var_3D8], edi; int
0x18008f620  mov     r9, r14
0x18008f623  mov     r8, [rsp+3F8h+string]
0x18008f62b  mov     edx, 100000h
0x18008f630  mov     rcx, r10
0x18008f633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f638  mov     rcx, [rsp+3F8h]; this
0x18008f640  test    eax, eax
0x18008f642  js      loc_18008F8DF
0x18008f648  lea     rdx, [rsp+3F8h+var_368]
0x18008f650  lea     rcx, [rsp+3F8h+var_360]
0x18008f658  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18008f65d  mov     rcx, [rsp+3F8h]; this
0x18008f665  test    eax, eax
0x18008f667  js      loc_18008F8F3
0x18008f66d  mov     rcx, [rsp+3F8h+var_368]
0x18008f675  mov     rax, [rcx]
0x18008f678  mov     edx, 1
0x18008f67d  mov     rax, [rax+38h]
0x18008f681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f686  mov     rcx, [rsp+3F8h]; this
0x18008f68e  test    eax, eax
0x18008f690  js      loc_18008F907
0x18008f696  mov     rcx, [rsp+3F8h+var_368]
0x18008f69e  mov     rax, [rcx]
0x18008f6a1  mov     edx, 4
0x18008f6a6  mov     rax, [rax+88h]
0x18008f6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f6b2  mov     rcx, [rsp+3F8h]; this
0x18008f6ba  test    eax, eax
0x18008f6bc  js      loc_18008F91B
0x18008f6c2  mov     rcx, [r13+1A8h]
0x18008f6c9  mov     rax, [rcx]
0x18008f6cc  mov     rdx, [rsp+3F8h+var_370]
0x18008f6d4  mov     rax, [rax+50h]
0x18008f6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f6dd  mov     rcx, [rsp+3F8h]; this
0x18008f6e5  test    eax, eax
0x18008f6e7  js      loc_18008F92F
0x18008f6ed  mov     [rsp+3F8h+var_328], rdi
0x18008f6f5  mov     rcx, [rsp+3F8h+var_368]
0x18008f6fd  mov     rax, [rcx]
0x18008f700  lea     rdx, [rsp+3F8h+var_328]
0x18008f708  mov     rax, [rax+58h]
0x18008f70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f711  mov     rcx, [rsp+3F8h]; this
0x18008f719  test    eax, eax
0x18008f71b  js      loc_18008F943
0x18008f721  mov     [rsp+3F8h+var_3D8], rdi; int
0x18008f726  mov     r9d, esi; unsigned int
0x18008f729  mov     r8, [rsp+3F8h+var_328]; unsigned __int64
0x18008f731  mov     dl, 1; bool
0x18008f733  call    ?SendServiceAndLsaNotification@UserManagerStatics@Internal@System@Windows@@AEAAJ_N_KKPEAX@Z; Windows::System::Internal::UserManagerStatics::SendServiceAndLsaNotification(bool,unsigned __int64,ulong,void *)
0x18008f738  mov     rcx, [rsp+3F8h]; this
0x18008f740  test    eax, eax
0x18008f742  js      loc_18008F957
0x18008f748  lea     rcx, [rsp+3F8h+var_360]
0x18008f750  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18008f755  mov     rax, [rsp+3F8h+var_360]
0x18008f75d  mov     [r12], rax
0x18008f761  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18008f766  mov     ecx, [rax]
0x18008f768  cmp     ecx, 5
0x18008f76b  jbe     short loc_18008F7C3
0x18008f76d  mov     [rsp+3F8h+var_394], edi
0x18008f771  mov     [rsp+3F8h+var_380], r15
0x18008f776  mov     [rsp+3F8h+var_350], r14
0x18008f77e  mov     dword ptr [rsp+3F8h+sourceString], esi
0x18008f785  lea     rcx, [rsp+3F8h+var_394]
0x18008f78a  mov     [rsp+3F8h+var_3C0], rcx
0x18008f78f  lea     rcx, [rsp+3F8h+var_380]
0x18008f794  mov     [rsp+3F8h+var_3C8], rcx
0x18008f799  lea     rcx, [rsp+3F8h+var_350]
0x18008f7a1  mov     [rsp+3F8h+var_3D0], rcx
0x18008f7a6  lea     rcx, [rsp+3F8h+sourceString]
0x18008f7ae  mov     [rsp+3F8h+var_3D8], rcx
0x18008f7b3  lea     rdx, byte_180125A0F
0x18008f7ba  mov     rcx, rax
0x18008f7bd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18008f7c2  nop
0x18008f7c3  mov     rcx, [rsp+3F8h+var_370]; string
0x18008f7cb  call    cs:__imp_WindowsDeleteString
0x18008f7d1  mov     [rsp+3F8h+var_370], rdi
0x18008f7d9  lea     rcx, [rsp+3F8h+var_348]
0x18008f7e1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008f7e6  nop
0x18008f7e7  mov     rcx, rbx
0x18008f7ea  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18008f7f0  nop
0x18008f7f1  lea     rcx, [rsp+3F8h+var_368]
0x18008f7f9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f7fe  nop
0x18008f7ff  lea     rcx, [rsp+3F8h+var_360]
0x18008f807  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f80c  nop
0x18008f80d  lea     rcx, [rsp+3F8h+var_340]
0x18008f815  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008f81a  nop
0x18008f81b  lea     rcx, [rsp+3F8h+var_358]
0x18008f823  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008f828  xor     eax, eax
0x18008f82a  jmp     short loc_18008F830
0x18008f82c  mov     eax, [rsp+3F8h+var_388]
0x18008f830  mov     rcx, [rsp+3F8h+var_48]
0x18008f838  xor     rcx, rsp; StackCookie
0x18008f83b  call    __security_check_cookie
0x18008f840  add     rsp, 3C0h
0x18008f847  pop     r15
0x18008f849  pop     r14
0x18008f84b  pop     r13
0x18008f84d  pop     r12
0x18008f84f  pop     rdi
0x18008f850  pop     rsi
0x18008f851  pop     rbx
0x18008f852  retn
0x18008f853  mov     r9d, 80004003h; char *
0x18008f859  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008f860  mov     edx, 12D4h; void *
0x18008f865  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f86a  mov     r9d, eax; char *
0x18008f86d  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008f874  mov     edx, 12D9h; void *
0x18008f879  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18008f87e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008f885  mov     edx, 12DBh; void *
0x18008f88a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008f88f  mov     r9d, eax; char *
0x18008f892  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008f899  mov     edx, 12DCh; void *
0x18008f89e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f8a3  mov     r9d, 8007000Eh; char *
0x18008f8a9  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008f8b0  mov     edx, 12E0h; void *
0x18008f8b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f8ba  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18008f8c1  mov     edx, 12E6h; void *
0x18008f8c6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008f8cb  mov     r9d, eax; char *
0x18008f8ce  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
  ... truncated ...
```
