# Windows::System::UserStatics::FirePictureUpdated(Windows::System::IUser *,HSTRING__ *)

- ea: `0x180079a40`
- end: `0x18007a074`
- name: `?FirePictureUpdated@UserStatics@System@Windows@@UEAAJPEAUIUser@23@PEAUHSTRING__@@@Z`
- size: `1588`
- prototype: `__int64 __fastcall(Windows::System::UserStatics *__hidden this, struct Windows::System::IUser *, HSTRING)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800013a4`
- `0x18000acdc`
- `0x18000f2e4`
- `0x180013278`
- `0x1800132d0`
- `0x18003329c`
- `0x18003b578`
- `0x180041bb0`
- `0x18004254c`
- `0x18004e58c`
- `0x180062ab0`
- `0x180063fac`
- `0x18006b878`
- `0x18006ba78`
- `0x18006c18c`
- `0x180079a40`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180079aac`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180079aac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180079b9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180079bd1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180079b9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180079bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079ae5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079ae5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079f31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079f31`
- `ntdll!RtlPublishWnfStateData` at `0x180079b54`
- `ntdll!RtlPublishWnfStateData` at `0x180079bb9`
- `ntdll!RtlPublishWnfStateData` at `0x180079beb`
- `ntdll!RtlPublishWnfStateData` at `0x180079b54`
- `ntdll!RtlPublishWnfStateData` at `0x180079bb9`
- `ntdll!RtlPublishWnfStateData` at `0x180079beb`

## string_xrefs

- `0x180079f77`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180079f88`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180079f9d`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180079fb1`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180079fda`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180079fee`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007a003`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007a017`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007a02b`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007a046`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007a061`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::System::UserStatics::FirePictureUpdated(
        Windows::System::UserStatics *this,
        struct Windows::System::IUser *a2,
        HSTRING a3)
{
  int v5; // eax
  const char *v6; // r9
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rax
  HSTRING v12; // rcx
  PCWSTR v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  void *v18; // rax
  __int64 updated; // rdi
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // r14
  _QWORD *v28; // rcx
  __int64 (__fastcall *v29)(char *, char *, struct Windows::System::IUser *, _BYTE *); // rax
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r14
  _QWORD *v34; // rcx
  __int64 (__fastcall *v35)(char *, char *, struct Windows::System::IUser *, _BYTE *); // rax
  int v36; // eax
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // rcx
  const char *v40; // r9
  __int64 result; // rax
  int v42; // [rsp+20h] [rbp-C8h]
  __int64 v43; // [rsp+30h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v46; // [rsp+44h] [rbp-A4h] BYREF
  __int64 v47; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-98h] BYREF
  HSTRING v49; // [rsp+58h] [rbp-90h] BYREF
  PCWSTR v50; // [rsp+60h] [rbp-88h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-80h] BYREF
  int v52[2]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v53[8]; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v54[24]; // [rsp+80h] [rbp-68h] BYREF
  _QWORD *v55; // [rsp+98h] [rbp-50h]
  _BYTE v56[24]; // [rsp+A0h] [rbp-48h] BYREF
  _QWORD *v57; // [rsp+B8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  HSTRING v59; // [rsp+100h] [rbp+18h] BYREF
  int v60; // [rsp+108h] [rbp+20h] BYREF

  v59 = a3;
  hToken = 0;
  wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(
    v53,
    a2);
  try
  {
    wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(
      v53,
      &v48);
    v5 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v48 + 80LL))(v48, &hToken);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB39,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v5,
        v42);
    if ( !ImpersonateLoggedOnUser(hToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xB3A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        v6);
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set(&string, &v59);
    v49 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = -1;
    do
      ++v8;
    while ( StringRawBuffer[v8] );
    v9 = 2 * v8 + 2;
    v10 = 78;
    if ( v9 <= 0x4E )
    {
      v10 = v9;
      v12 = string;
    }
    else
    {
      v11 = WindowsGetStringRawBuffer(string, 0);
      Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v49, v11, 0x26u);
      v12 = v49;
    }
    v13 = WindowsGetStringRawBuffer(v12, 0);
    v14 = RtlPublishWnfStateData(WNF_UMGR_USER_PICTURE_ID, 0, v13, v10) | 0x10000000;
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v14,
        0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl'::`2'::impl) )
    {
      LODWORD(v43) = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 96LL))(v48, &v43);
      RevertToSelf();
      v15 = RtlPublishWnfStateData(WNF_UMGR_USER_PICTURE_CHANGED_CONTAINED, 0, &v43, 4) | 0x10000000;
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB58,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v15,
          0);
    }
    else
    {
      RevertToSelf();
      v16 = RtlPublishWnfStateData(WNF_UMGR_USER_PICTURE_CHANGED, 0, 0, 0) | 0x10000000;
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35A,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)(unsigned int)v16,
          0);
    }
    v47 = 0;
    v17 = 0;
    v50 = 0;
    v18 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
    v43 = (__int64)v18;
    updated = 0;
    if ( v18 )
    {
      updated = Windows::Foundation::Collections::Internal::Vector<enum Windows::System::UserWatcherUpdateKind,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::System::UserWatcherUpdateKind>>::Vector<enum Windows::System::UserWatcherUpdateKind,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::System::UserWatcherUpdateKind>>(v18);
      v43 = 0;
    }
    Microsoft::WRL::Details::MakeAllocator<Windows::System::UserStatics>::~MakeAllocator<Windows::System::UserStatics>(&v43);
    if ( updated )
    {
      v20 = 0;
      v17 = updated;
      v50 = (PCWSTR)updated;
    }
    else
    {
      v20 = -2147024882;
    }
    v21 = 0;
    if ( v20 < 0 )
      v21 = updated;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 104LL))(v17, 1);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB65,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v22,
        0);
    v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 64LL))(v17, &v47);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB66,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v23,
        0);
    LOBYTE(v60) = 0;
    *(_QWORD *)v52 = 0;
    v46 = 0;
    v45 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 48LL))(v48, &v46);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB6C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v24,
        0);
    v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 96LL))(v48, &v45);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB6D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v25,
        0);
    v26 = (*(__int64 (__fastcall **)(Windows::System::UserStatics *, _QWORD, _QWORD, int *))(*(_QWORD *)this + 136LL))(
            this,
            v46,
            v45,
            &v60);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB6F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v26,
        (int)v52);
    v27 = *((_QWORD *)this - 7);
    v43 = (__int64)v54;
    v55 = 0;
    v28 = operator new(0x20u);
    if ( !v28 )
      std::_Xbad_alloc();
    v29 = *(__int64 (__fastcall **)(char *, char *, struct Windows::System::IUser *, _BYTE *))(v27 + 64);
    *v28 = off_1800EFE90;
    v28[1] = &v47;
    v28[2] = &v59;
    v55 = v28;
    v30 = v29((char *)this - 56, (char *)this + 384, a2, v54);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB73,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v30,
        (int)v52);
    if ( !(_BYTE)v60 )
    {
      v33 = *((_QWORD *)this - 7);
      v43 = (__int64)v56;
      v57 = 0;
      v34 = operator new(0x20u);
      if ( !v34 )
        std::_Xbad_alloc();
      v35 = *(__int64 (__fastcall **)(char *, char *, struct Windows::System::IUser *, _BYTE *))(v33 + 64);
      *v34 = off_1800EFE58;
      v34[1] = &v47;
      v34[2] = &v59;
      v57 = v34;
      v36 = v35((char *)this - 56, (char *)this + 360, a2, v56);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB79,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v36,
          (int)v52);
    }
    if ( (unsigned int)dword_180146228 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180146228, 0x400000000000LL, v31, v32) )
    {
      v50 = WindowsGetStringRawBuffer(string, 0);
      v43 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_180146228,
        (unsigned int)word_180121EF2,
        v37,
        v38,
        (__int64)&v43,
        (__int64)&v50);
    }
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v52);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v39 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    WindowsDeleteString(v49);
    v49 = 0;
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v48);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v53);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB85,
                           (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
                           v40);
  }
  return result;
}

```

## disassembly

```asm
0x180079a40  mov     rax, rsp
0x180079a43  mov     [rax+8], rbx
0x180079a47  mov     [rax+18h], r8
0x180079a4b  push    rsi
0x180079a4c  push    rdi
0x180079a4d  push    r12
0x180079a4f  push    r14
0x180079a51  push    r15
0x180079a53  sub     rsp, 0C0h
0x180079a5a  mov     r15, rdx
0x180079a5d  mov     rsi, rcx
0x180079a60  xor     r12d, r12d
0x180079a63  mov     [rax-80h], r12
0x180079a67  lea     rcx, [rax-70h]
0x180079a6b  call    ??0?$com_ptr_t@UISignInContext@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUISignInContext@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(Windows::System::Internal::ISignInContext *)
0x180079a70  nop
0x180079a71  lea     rdx, [rsp+0E8h+var_98]
0x180079a76  lea     rcx, [rsp+0E8h+var_70]
0x180079a7b  call    ??$query@UIUserInternal@Implementation@Internal@System@Windows@@@?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUserInternal@Implementation@Internal@System@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(void)
0x180079a80  nop
0x180079a81  mov     rcx, [rsp+0E8h+var_98]
0x180079a86  mov     rax, [rcx]
0x180079a89  lea     rdx, [rsp+0E8h+hToken]
0x180079a8e  mov     rax, [rax+50h]
0x180079a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a97  mov     rcx, [rsp+0E8h]; this
0x180079a9f  test    eax, eax
0x180079aa1  js      loc_180079F74
0x180079aa7  mov     rcx, [rsp+0E8h+hToken]; hToken
0x180079aac  call    cs:__imp_ImpersonateLoggedOnUser
0x180079ab2  mov     rcx, [rsp+0E8h]; this
0x180079aba  test    eax, eax
0x180079abc  jz      loc_180079F88
0x180079ac2  mov     [rsp+0E8h+string], r12
0x180079ac7  lea     rdx, [rsp+0E8h+arg_10]; HSTRING *
0x180079acf  lea     rcx, [rsp+0E8h+string]; newString
0x180079ad4  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180079ad9  mov     [rsp+0E8h+var_90], r12
0x180079ade  xor     edx, edx; length
0x180079ae0  mov     rcx, [rsp+0E8h+string]; string
0x180079ae5  call    cs:__imp_WindowsGetStringRawBuffer
0x180079aeb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180079aef  inc     rcx
0x180079af2  cmp     [rax+rcx*2], r12w
0x180079af7  jnz     short loc_180079AEF
0x180079af9  lea     rcx, ds:2[rcx*2]
0x180079b01  mov     ebx, 4Eh ; 'N'
0x180079b06  cmp     rcx, rbx
0x180079b09  jbe     short loc_180079B30
0x180079b0b  xor     edx, edx; length
0x180079b0d  mov     rcx, [rsp+0E8h+string]; string
0x180079b12  call    cs:__imp_WindowsGetStringRawBuffer
0x180079b18  lea     r8d, [rbx-28h]; unsigned int
0x180079b1c  mov     rdx, rax; unsigned __int16 *
0x180079b1f  lea     rcx, [rsp+0E8h+var_90]; this
0x180079b24  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180079b29  mov     rcx, [rsp+0E8h+var_90]
0x180079b2e  jmp     short loc_180079B38
0x180079b30  mov     rbx, rcx
0x180079b33  mov     rcx, [rsp+0E8h+string]; string
0x180079b38  xor     edx, edx; length
0x180079b3a  call    cs:__imp_WindowsGetStringRawBuffer
0x180079b40  mov     r9d, ebx
0x180079b43  mov     qword ptr [rsp+0E8h+var_C8], r12; int
0x180079b48  mov     r8, rax
0x180079b4b  xor     edx, edx
0x180079b4d  mov     rcx, cs:WNF_UMGR_USER_PICTURE_ID
0x180079b54  call    cs:__imp_RtlPublishWnfStateData
0x180079b5a  mov     ebx, 10000000h
0x180079b5f  or      eax, ebx
0x180079b61  mov     rcx, [rsp+0E8h]; this
0x180079b69  jl      loc_180079F9A
0x180079b6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserPictureFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix> `wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl(void)'::`2'::impl
0x180079b76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(void)
0x180079b7b  test    al, al
0x180079b7d  jz      short loc_180079BD1
0x180079b7f  mov     dword ptr [rsp+0E8h+var_B8], r12d
0x180079b84  mov     rcx, [rsp+0E8h+var_98]
0x180079b89  mov     rax, [rcx]
0x180079b8c  lea     rdx, [rsp+0E8h+var_B8]
0x180079b91  mov     rax, [rax+60h]
0x180079b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b9a  call    cs:__imp_RevertToSelf
0x180079ba0  mov     qword ptr [rsp+0E8h+var_C8], r12; int
0x180079ba5  mov     r9d, 4
0x180079bab  lea     r8, [rsp+0E8h+var_B8]
0x180079bb0  xor     edx, edx
0x180079bb2  mov     rcx, cs:WNF_UMGR_USER_PICTURE_CHANGED_CONTAINED
0x180079bb9  call    cs:__imp_RtlPublishWnfStateData
0x180079bbf  or      eax, ebx
0x180079bc1  mov     rcx, [rsp+0E8h]; this
0x180079bc9  jl      loc_180079FAE
0x180079bcf  jmp     short loc_180079C01
0x180079bd1  call    cs:__imp_RevertToSelf
0x180079bd7  mov     qword ptr [rsp+0E8h+var_C8], r12; int
0x180079bdc  xor     r9d, r9d
0x180079bdf  xor     r8d, r8d
0x180079be2  xor     edx, edx
0x180079be4  mov     rcx, cs:WNF_UMGR_USER_PICTURE_CHANGED
0x180079beb  call    cs:__imp_RtlPublishWnfStateData
0x180079bf1  or      eax, ebx
0x180079bf3  mov     rcx, [rsp+0E8h]; this
0x180079bfb  jl      loc_180079FC2
0x180079c01  mov     [rsp+0E8h+var_A0], r12
0x180079c06  mov     rbx, r12
0x180079c09  mov     [rsp+0E8h+var_88], rbx
0x180079c0e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180079c15  mov     ecx, 70h ; 'p'; unsigned __int64
0x180079c1a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180079c1f  mov     [rsp+0E8h+var_B8], rax
0x180079c24  mov     rdi, r12
0x180079c27  test    rax, rax
0x180079c2a  jz      short loc_180079C3C
0x180079c2c  mov     rcx, rax
0x180079c2f  call    ??0?$Vector@W4UserWatcherUpdateKind@System@Windows@@U?$DefaultEqualityPredicate@W4UserWatcherUpdateKind@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@W4UserWatcherUpdateKind@System@Windows@@@5673@U?$DefaultVectorOptions@W4UserWatcherUpdateKind@System@Windows@@@5673@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@W4UserWatcherUpdateKind@System@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::System::UserWatcherUpdateKind,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::UserWatcherUpdateKind>>::Vector<Windows::System::UserWatcherUpdateKind,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::UserWatcherUpdateKind>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::UserWatcherUpdateKind> const &,Windows::Foundation::Collections::Internal::Vector<Windows::System::UserWatcherUpdateKind,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::UserWatcherUpdateKind>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::UserWatcherUpdateKind>>::permission)
0x180079c34  mov     rdi, rax
0x180079c37  mov     [rsp+0E8h+var_B8], r12
0x180079c3c  lea     rcx, [rsp+0E8h+var_B8]
0x180079c41  call    ??1?$MakeAllocator@VUserStatics@System@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::System::UserStatics>::~MakeAllocator<Windows::System::UserStatics>(void)
0x180079c46  test    rdi, rdi
0x180079c49  jz      short loc_180079C58
0x180079c4b  mov     eax, r12d
0x180079c4e  mov     rbx, rdi
0x180079c51  mov     [rsp+0E8h+var_88], rbx
0x180079c56  jmp     short loc_180079C5D
0x180079c58  mov     eax, 8007000Eh
0x180079c5d  mov     rcx, r12
0x180079c60  test    eax, eax
0x180079c62  cmovs   rcx, rdi
0x180079c66  test    rcx, rcx
0x180079c69  jz      short loc_180079C78
0x180079c6b  mov     rax, [rcx]
0x180079c6e  mov     rax, [rax+10h]
0x180079c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c77  nop
0x180079c78  mov     rax, [rbx]
0x180079c7b  mov     edx, 1
0x180079c80  mov     rcx, rbx
0x180079c83  mov     rax, [rax+68h]
0x180079c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c8c  mov     rcx, [rsp+0E8h]; this
0x180079c94  test    eax, eax
0x180079c96  js      loc_180079FD7
0x180079c9c  mov     rax, [rbx]
0x180079c9f  lea     rdx, [rsp+0E8h+var_A0]
0x180079ca4  mov     rcx, rbx
0x180079ca7  mov     rax, [rax+40h]
0x180079cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079cb0  mov     rcx, [rsp+0E8h]; this
0x180079cb8  test    eax, eax
0x180079cba  js      loc_180079FEB
0x180079cc0  mov     byte ptr [rsp+0E8h+arg_18], r12b
0x180079cc8  mov     qword ptr [rsp+0E8h+var_78], r12
0x180079ccd  mov     [rsp+0E8h+var_A4], r12d
0x180079cd2  mov     [rsp+0E8h+var_A8], r12d
0x180079cd7  mov     rcx, [rsp+0E8h+var_98]
0x180079cdc  mov     rax, [rcx]
0x180079cdf  lea     rdx, [rsp+0E8h+var_A4]
0x180079ce4  mov     rax, [rax+30h]
0x180079ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ced  mov     rcx, [rsp+0E8h]; this
0x180079cf5  test    eax, eax
0x180079cf7  js      loc_18007A000
0x180079cfd  mov     rcx, [rsp+0E8h+var_98]
0x180079d02  mov     rax, [rcx]
0x180079d05  lea     rdx, [rsp+0E8h+var_A8]
0x180079d0a  mov     rax, [rax+60h]
0x180079d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d13  mov     rcx, [rsp+0E8h]; this
0x180079d1b  test    eax, eax
0x180079d1d  js      loc_18007A014
0x180079d23  mov     rax, [rsi]
0x180079d26  lea     rcx, [rsp+0E8h+var_78]
0x180079d2b  mov     qword ptr [rsp+0E8h+var_C8], rcx; int
0x180079d30  lea     r9, [rsp+0E8h+arg_18]
0x180079d38  mov     r8d, [rsp+0E8h+var_A8]
0x180079d3d  mov     edx, [rsp+0E8h+var_A4]
0x180079d41  mov     rcx, rsi
0x180079d44  mov     rax, [rax+88h]
0x180079d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d50  mov     rcx, [rsp+0E8h]; this
0x180079d58  test    eax, eax
0x180079d5a  js      loc_18007A028
0x180079d60  lea     rdi, [rsi-38h]
0x180079d64  mov     r14, [rdi]
0x180079d67  lea     rax, [rsp+0E8h+var_68]
0x180079d6f  mov     [rsp+0E8h+var_B8], rax
0x180079d74  mov     [rsp+0E8h+var_50], r12
0x180079d7c  mov     ecx, 20h ; ' '; Size
0x180079d81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079d86  mov     rcx, rax
0x180079d89  test    rax, rax
0x180079d8c  jz      loc_18007A03D
0x180079d92  mov     rax, [r14+40h]
0x180079d96  lea     rdx, off_1800EFE90
0x180079d9d  mov     [rcx], rdx
0x180079da0  lea     rdx, [rsp+0E8h+var_A0]
0x180079da5  mov     [rcx+8], rdx
0x180079da9  lea     rdx, [rsp+0E8h+arg_10]
0x180079db1  mov     [rcx+10h], rdx
0x180079db5  mov     [rsp+0E8h+var_50], rcx
0x180079dbd  lea     rdx, [rsi+180h]
0x180079dc4  lea     r9, [rsp+0E8h+var_68]
0x180079dcc  mov     r8, r15
0x180079dcf  mov     rcx, rdi
0x180079dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079dd7  mov     rcx, [rsp+0E8h]; this
0x180079ddf  test    eax, eax
0x180079de1  js      loc_18007A043
0x180079de7  cmp     byte ptr [rsp+0E8h+arg_18], r12b
0x180079def  jnz     loc_180079E78
0x180079df5  mov     r14, [rdi]
0x180079df8  lea     rax, [rsp+0E8h+var_48]
0x180079e00  mov     [rsp+0E8h+var_B8], rax
0x180079e05  mov     [rsp+0E8h+var_30], r12
0x180079e0d  mov     ecx, 20h ; ' '; Size
0x180079e12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079e17  mov     rcx, rax
0x180079e1a  test    rax, rax
0x180079e1d  jz      loc_18007A058
0x180079e23  mov     rax, [r14+40h]
0x180079e27  lea     rdx, off_1800EFE58
0x180079e2e  mov     [rcx], rdx
0x180079e31  lea     rdx, [rsp+0E8h+var_A0]
0x180079e36  mov     [rcx+8], rdx
0x180079e3a  lea     rdx, [rsp+0E8h+arg_10]
0x180079e42  mov     [rcx+10h], rdx
0x180079e46  mov     [rsp+0E8h+var_30], rcx
0x180079e4e  lea     rdx, [rsi+168h]
0x180079e55  lea     r9, [rsp+0E8h+var_48]
0x180079e5d  mov     r8, r15
0x180079e60  mov     rcx, rdi
0x180079e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e68  mov     rcx, [rsp+0E8h]; this
0x180079e70  test    eax, eax
0x180079e72  js      loc_18007A05E
0x180079e78  mov     eax, cs:dword_180146228
0x180079e7e  cmp     eax, 5
0x180079e81  jbe     short loc_180079EE0
0x180079e83  mov     rdx, 400000000000h
0x180079e8d  lea     rcx, dword_180146228
0x180079e94  call    _tlgKeywordOn
0x180079e99  test    al, al
0x180079e9b  jz      short loc_180079EE0
0x180079e9d  xor     edx, edx; length
0x180079e9f  mov     rcx, [rsp+0E8h+string]; string
0x180079ea4  call    cs:__imp_WindowsGetStringRawBuffer
0x180079eaa  mov     [rsp+0E8h+var_88], rax
0x180079eaf  mov     [rsp+0E8h+var_B8], 1000000h
0x180079eb8  lea     rax, [rsp+0E8h+var_88]
0x180079ebd  mov     [rsp+0E8h+var_C0], rax
0x180079ec2  lea     rax, [rsp+0E8h+var_B8]
0x180079ec7  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180079ecc  lea     rdx, word_180121EF2
0x180079ed3  lea     rcx, dword_180146228
0x180079eda  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180079edf  nop
0x180079ee0  lea     rcx, [rsp+0E8h+var_78]
0x180079ee5  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180079eea  nop
0x180079eeb  test    rbx, rbx
0x180079eee  jz      short loc_180079F00
0x180079ef0  mov     rax, [rbx]
0x180079ef3  mov     rcx, rbx
0x180079ef6  mov     rax, [rax+10h]
0x180079efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079eff  nop
0x180079f00  mov     rcx, [rsp+0E8h+var_A0]
0x180079f05  test    rcx, rcx
0x180079f08  jz      short loc_180079F1C
0x180079f0a  mov     [rsp+0E8h+var_A0], r12
0x180079f0f  mov     rax, [rcx]
0x180079f12  mov     rax, [rax+10h]
0x180079f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f1b  nop
0x180079f1c  mov     rcx, [rsp+0E8h+var_90]; string
0x180079f21  call    cs:__imp_WindowsDeleteString
0x180079f27  mov     [rsp+0E8h+var_90], r12
0x180079f2c  mov     rcx, [rsp+0E8h+string]; string
0x180079f31  call    cs:__imp_WindowsDeleteString
0x180079f37  mov     [rsp+0E8h+string], r12
0x180079f3c  lea     rcx, [rsp+0E8h+var_98]
0x180079f41  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180079f46  nop
0x180079f47  lea     rcx, [rsp+0E8h+var_70]
0x180079f4c  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180079f51  xor     eax, eax
0x180079f53  jmp     short loc_180079F5C
0x180079f55  mov     eax, [rsp+0E8h+arg_18]
0x180079f5c  mov     rbx, [rsp+0E8h+arg_0]
0x180079f64  add     rsp, 0C0h
0x180079f6b  pop     r15
0x180079f6d  pop     r14
0x180079f6f  pop     r12
0x180079f71  pop     rdi
0x180079f72  pop     rsi
0x180079f73  retn
0x180079f74  mov     r9d, eax; char *
0x180079f77  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180079f7e  mov     edx, 0B39h; void *
  ... truncated ...
```
