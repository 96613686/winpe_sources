# UserMgrCli::IsAllowedToActivateAsUser(void *,void *,unsigned __int64,uchar *)

- ea: `0x180035c50`
- end: `0x1800360a4`
- name: `?IsAllowedToActivateAsUser@UserMgrCli@@QEAAJPEAX0_KPEAE@Z`
- size: `1108`
- prototype: `int(UserMgrCli *__hidden this, void *, void *, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035c30`

## callees

- `0x180006130`
- `0x180007920`
- `0x180009af0`
- `0x18000acdc`
- `0x18000cd30`
- `0x18000ce48`
- `0x180012890`
- `0x180014e7c`
- `0x180014e9c`
- `0x180014ee0`
- `0x180016380`
- `0x1800265c4`
- `0x180035c50`
- `0x18004e508`
- `0x18004e58c`
- `0x1800b6ac4`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f3f`

## string_xrefs

- `0x180035f9b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180035fb2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180035fc9`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180035fdd`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180035ff1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180036005`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180036019`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003602d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180036044`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180036058`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003606c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003607d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180036091`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UserMgrCli::IsAllowedToActivateAsUser(
        UserMgrCli *this,
        void *a2,
        void *a3,
        unsigned __int64 a4,
        unsigned __int8 *a5)
{
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  void (*v10)(void); // rbx
  unsigned __int8 *v11; // r14
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, unsigned __int64, struct Windows::System::IUser **); // rbx
  int v15; // eax
  struct Windows::System::IUser *v16; // rcx
  UserManagerTokenAndShellHandler *v17; // rbx
  int v18; // eax
  int valid; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  int v24; // eax
  __int64 v25; // rdi
  unsigned int (__fastcall *v26)(__int64, PCWSTR, void **); // rbx
  PCWSTR StringRawBuffer; // rax
  const char *v28; // r9
  unsigned int v29; // eax
  const struct _tlgProvider_t *v30; // rax
  __int64 result; // rax
  const struct _tlgProvider_t *v32; // rax
  int v33; // ebx
  wil *v34; // rcx
  unsigned int v35; // [rsp+20h] [rbp-78h]
  struct Windows::System::IUser *v36; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  void *v38; // [rsp+40h] [rbp-58h] BYREF
  __int64 v39; // [rsp+48h] [rbp-50h] BYREF
  __int64 v40; // [rsp+50h] [rbp-48h] BYREF
  __int64 v41; // [rsp+58h] [rbp-40h] BYREF
  unsigned __int64 v42[7]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  UserMgrCli *v44; // [rsp+A0h] [rbp+8h] BYREF
  void *v45; // [rsp+A8h] [rbp+10h] BYREF
  UserMgrCli *v46; // [rsp+B8h] [rbp+20h]

  v46 = (UserMgrCli *)a4;
  v45 = a2;
  v44 = this;
  v7 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    v44 = (UserMgrCli *)a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (_DWORD)v7,
      (unsigned int)byte_1801292ED,
      v8,
      v9,
      (__int64)&v44);
  }
  v36 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  string = 0;
  v38 = 0;
  v10 = *(void (**)(void))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  try
  {
    v10();
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x979,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v35);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v35);
    v11 = a5;
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        v35);
    *a5 = 0;
    v12 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(&v41);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v12,
        v35);
    v13 = v41;
    v14 = *(__int64 (__fastcall **)(__int64, unsigned __int64, struct Windows::System::IUser **))(*(_QWORD *)v41 + 160LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    v15 = v14(v13, a4, &v36);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x983,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v15,
        v35);
    v16 = v36;
    if ( !v36 )
    {
      v17 = (UserManagerTokenAndShellHandler *)qword_180148188;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v18 = UserManagerTokenAndShellHandler::QueryDefaultAccountUser(v17, a4, &v36);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x986,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v18,
          v35);
      v16 = v36;
    }
    valid = IsValidCallerForUser(v16, 0);
    if ( valid < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x988,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)valid,
        v35);
    LODWORD(v45) = 0;
    v20 = (*(__int64 (__fastcall **)(struct Windows::System::IUser *, void **))(*(_QWORD *)v36 + 56LL))(v36, &v45);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v20,
        v35);
    if ( !(_DWORD)v45 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        v35);
    v21 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v36,
            &v40);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v21,
        v35);
    v22 = v40;
    v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 72LL);
    WindowsDeleteString(string);
    string = 0;
    v24 = v23(v22, &string);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v24,
        v35);
    v25 = v39;
    v26 = *(unsigned int (__fastcall **)(__int64, PCWSTR, void **))(*(_QWORD *)v39 + 40LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !v26(v25, StringRawBuffer, &v38) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x990,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v28);
    v29 = IsActivationAllowed(a3, v38, v11);
    if ( v29 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x996,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)v29,
        v35);
    v30 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v30 > 5u )
    {
      LODWORD(v44) = 0;
      v42[0] = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v30,
        (unsigned int)&dword_180129244,
        0,
        0,
        (__int64)v42,
        (__int64)&v44);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v38);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    result = 0;
  }
  catch ( ... )
  {
    v32 = UserMgrUserModelTelemetry::Provider();
    v33 = (int)v32;
    v34 = (wil *)*(unsigned int *)v32;
    if ( (unsigned int)v34 > 5 )
    {
      LODWORD(v45) = wil::ResultFromCaughtException(v34);
      v44 = v46;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v33,
        (unsigned int)&byte_18012928F,
        0,
        0,
        (__int64)&v44,
        (__int64)&v45);
    }
    LODWORD(v45) = wil::ResultFromCaughtException(v34);
    return (unsigned int)v45;
  }
  return result;
}

```

## disassembly

```asm
0x180035c50  mov     rax, rsp
0x180035c53  mov     [rax+18h], rbx
0x180035c57  mov     [rax+20h], r9
0x180035c5b  mov     [rax+10h], rdx
0x180035c5f  mov     [rax+8], rcx
0x180035c63  push    rsi
0x180035c64  push    rdi
0x180035c65  push    r12
0x180035c67  push    r14
0x180035c69  push    r15
0x180035c6b  sub     rsp, 70h
0x180035c6f  mov     rsi, r9
0x180035c72  mov     r15, r8
0x180035c75  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180035c7a  mov     ecx, [rax]
0x180035c7c  cmp     ecx, 5
0x180035c7f  jbe     short loc_180035CA5
0x180035c81  mov     [rsp+98h+arg_0], rsi
0x180035c89  lea     rcx, [rsp+98h+arg_0]
0x180035c91  mov     qword ptr [rsp+98h+var_78], rcx; unsigned int
0x180035c96  lea     rdx, byte_1801292ED
0x180035c9d  mov     rcx, rax
0x180035ca0  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180035ca5  xor     r12d, r12d
0x180035ca8  mov     [rsp+98h+var_68], r12
0x180035cad  mov     [rsp+98h+var_40], r12
0x180035cb2  mov     [rsp+98h+var_48], r12
0x180035cb7  mov     [rsp+98h+var_50], r12
0x180035cbc  mov     [rsp+98h+string], r12
0x180035cc1  mov     [rsp+98h+var_58], r12
0x180035cc6  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180035ccd  mov     rbx, [rax+38h]
0x180035cd1  lea     rcx, [rsp+98h+var_50]
0x180035cd6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035cdb  lea     rdx, [rsp+98h+var_50]
0x180035ce0  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180035ce7  mov     rax, rbx
0x180035cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cef  mov     rcx, [rsp+98h]; this
0x180035cf7  test    rsi, rsi
0x180035cfa  jz      loc_180035F95
0x180035d00  mov     rcx, [rsp+98h]; this
0x180035d08  test    r15, r15
0x180035d0b  jz      loc_180035FAC
0x180035d11  mov     rcx, [rsp+98h]; this
0x180035d19  mov     r14, [rsp+98h+arg_20]
0x180035d21  test    r14, r14
0x180035d24  jz      loc_180035FC3
0x180035d2a  mov     [r14], r12b
0x180035d2d  lea     rcx, [rsp+98h+var_40]
0x180035d32  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x180035d37  mov     rcx, [rsp+98h]; this
0x180035d3f  test    eax, eax
0x180035d41  js      loc_180035FDA
0x180035d47  mov     rdi, [rsp+98h+var_40]
0x180035d4c  mov     rax, [rdi]
0x180035d4f  mov     rbx, [rax+0A0h]
0x180035d56  lea     rcx, [rsp+98h+var_68]
0x180035d5b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035d60  lea     r8, [rsp+98h+var_68]
0x180035d65  mov     rdx, rsi
0x180035d68  mov     rcx, rdi
0x180035d6b  mov     rax, rbx
0x180035d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d73  mov     rcx, [rsp+98h]; this
0x180035d7b  test    eax, eax
0x180035d7d  js      loc_180035FEE
0x180035d83  mov     rcx, [rsp+98h+var_68]
0x180035d88  test    rcx, rcx
0x180035d8b  jnz     short loc_180035DC3
0x180035d8d  mov     rbx, cs:qword_180148188
0x180035d94  lea     rcx, [rsp+98h+var_68]
0x180035d99  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035d9e  lea     r8, [rsp+98h+var_68]; struct Windows::System::IUser **
0x180035da3  mov     rdx, rsi; unsigned __int64
0x180035da6  mov     rcx, rbx; this
0x180035da9  call    ?QueryDefaultAccountUser@UserManagerTokenAndShellHandler@@QEAAJ_KPEAPEAUIUser@System@Windows@@@Z; UserManagerTokenAndShellHandler::QueryDefaultAccountUser(unsigned __int64,Windows::System::IUser * *)
0x180035dae  mov     rcx, [rsp+98h]; this
0x180035db6  test    eax, eax
0x180035db8  js      loc_180036002
0x180035dbe  mov     rcx, [rsp+98h+var_68]; struct Windows::System::IUser *
0x180035dc3  xor     edx, edx; struct _BASIC_CALLER_INFORMATION *
0x180035dc5  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x180035dca  mov     rcx, [rsp+98h]; this
0x180035dd2  test    eax, eax
0x180035dd4  js      loc_180036016
0x180035dda  mov     dword ptr [rsp+98h+arg_8], r12d
0x180035de2  mov     rcx, [rsp+98h+var_68]
0x180035de7  mov     rax, [rcx]
0x180035dea  lea     rdx, [rsp+98h+arg_8]
0x180035df2  mov     rax, [rax+38h]
0x180035df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dfb  mov     rcx, [rsp+98h]; this
0x180035e03  test    eax, eax
0x180035e05  js      loc_18003602A
0x180035e0b  cmp     dword ptr [rsp+98h+arg_8], r12d
0x180035e13  setz    al
0x180035e16  mov     rcx, [rsp+98h]; this
0x180035e1e  test    al, al
0x180035e20  jnz     loc_18003603E
0x180035e26  lea     rdx, [rsp+98h+var_48]
0x180035e2b  lea     rcx, [rsp+98h+var_68]
0x180035e30  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180035e35  mov     rcx, [rsp+98h]; this
0x180035e3d  test    eax, eax
0x180035e3f  js      loc_180036055
0x180035e45  mov     rdi, [rsp+98h+var_48]
0x180035e4a  mov     rax, [rdi]
0x180035e4d  mov     rbx, [rax+48h]
0x180035e51  mov     rcx, [rsp+98h+string]; string
0x180035e56  call    cs:__imp_WindowsDeleteString
0x180035e5c  mov     [rsp+98h+string], r12
0x180035e61  lea     rdx, [rsp+98h+string]
0x180035e66  mov     rcx, rdi
0x180035e69  mov     rax, rbx
0x180035e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e71  mov     rcx, [rsp+98h]; this
0x180035e79  test    eax, eax
0x180035e7b  js      loc_180036069
0x180035e81  mov     rdi, [rsp+98h+var_50]
0x180035e86  mov     rax, [rdi]
0x180035e89  mov     rbx, [rax+28h]
0x180035e8d  xor     edx, edx
0x180035e8f  lea     rcx, [rsp+98h+var_58]
0x180035e94  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035e99  xor     edx, edx; length
0x180035e9b  mov     rcx, [rsp+98h+string]; string
0x180035ea0  call    cs:__imp_WindowsGetStringRawBuffer
0x180035ea6  lea     r8, [rsp+98h+var_58]
0x180035eab  mov     rdx, rax
0x180035eae  mov     rcx, rdi
0x180035eb1  mov     rax, rbx
0x180035eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035eb9  mov     rcx, [rsp+98h]; this
0x180035ec1  test    eax, eax
0x180035ec3  jz      loc_18003607D
0x180035ec9  mov     r8, r14; unsigned __int8 *
0x180035ecc  mov     rdx, [rsp+98h+var_58]; void *
0x180035ed1  mov     rcx, r15; hExistingToken
0x180035ed4  call    ?IsActivationAllowed@@YAKPEAX0PEAE@Z; IsActivationAllowed(void *,void *,uchar *)
0x180035ed9  mov     rcx, [rsp+98h]; this
0x180035ee1  test    eax, eax
0x180035ee3  jnz     loc_18003608E
0x180035ee9  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180035eee  mov     ecx, [rax]
0x180035ef0  cmp     ecx, 5
0x180035ef3  jbe     short loc_180035F2F
0x180035ef5  mov     dword ptr [rsp+98h+arg_0], r12d
0x180035efd  mov     [rsp+98h+var_38], rsi
0x180035f02  lea     rcx, [rsp+98h+arg_0]
0x180035f0a  mov     [rsp+98h+var_70], rcx
0x180035f0f  lea     rcx, [rsp+98h+var_38]
0x180035f14  mov     qword ptr [rsp+98h+var_78], rcx
0x180035f19  xor     r9d, r9d
0x180035f1c  xor     r8d, r8d
0x180035f1f  lea     rdx, dword_180129244
0x180035f26  mov     rcx, rax
0x180035f29  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180035f2e  nop
0x180035f2f  lea     rcx, [rsp+98h+var_58]
0x180035f34  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180035f39  nop
0x180035f3a  mov     rcx, [rsp+98h+string]; string
0x180035f3f  call    cs:__imp_WindowsDeleteString
0x180035f45  mov     [rsp+98h+string], r12
0x180035f4a  lea     rcx, [rsp+98h+var_50]
0x180035f4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035f54  nop
0x180035f55  lea     rcx, [rsp+98h+var_48]
0x180035f5a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035f5f  nop
0x180035f60  lea     rcx, [rsp+98h+var_40]
0x180035f65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035f6a  nop
0x180035f6b  lea     rcx, [rsp+98h+var_68]
0x180035f70  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035f75  xor     eax, eax
0x180035f77  jmp     short loc_180035F80
0x180035f79  mov     eax, dword ptr [rsp+98h+arg_8]
0x180035f80  mov     rbx, [rsp+98h+arg_10]
0x180035f88  add     rsp, 70h
0x180035f8c  pop     r15
0x180035f8e  pop     r14
0x180035f90  pop     r12
0x180035f92  pop     rdi
0x180035f93  pop     rsi
0x180035f94  retn
0x180035f95  mov     r9d, 80070057h; char *
0x180035f9b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180035fa2  mov     edx, 979h; void *
0x180035fa7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035fac  mov     r9d, 80070057h; char *
0x180035fb2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180035fb9  mov     edx, 97Ah; void *
0x180035fbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035fc3  mov     r9d, 80070057h; char *
0x180035fc9  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180035fd0  mov     edx, 97Bh; void *
0x180035fd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035fda  mov     r9d, eax; char *
0x180035fdd  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180035fe4  mov     edx, 97Eh; void *
0x180035fe9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035fee  mov     r9d, eax; char *
0x180035ff1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180035ff8  mov     edx, 983h; void *
0x180035ffd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036002  mov     r9d, eax; char *
0x180036005  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003600c  mov     edx, 986h; void *
0x180036011  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036016  mov     r9d, eax; char *
0x180036019  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180036020  mov     edx, 988h; void *
0x180036025  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003602a  mov     r9d, eax; char *
0x18003602d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180036034  mov     edx, 98Bh; void *
0x180036039  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003603e  mov     r9d, 80070520h; char *
0x180036044  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003604b  mov     edx, 98Ch; void *
0x180036050  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036055  mov     r9d, eax; char *
0x180036058  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003605f  mov     edx, 98Eh; void *
0x180036064  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036069  mov     r9d, eax; char *
0x18003606c  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180036073  mov     edx, 98Fh; void *
0x180036078  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003607d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180036084  mov     edx, 990h; void *
0x180036089  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003608e  mov     r9d, eax; char *
0x180036091  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180036098  mov     edx, 996h; void *
0x18003609d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
