# Windows::System::Internal::GetDefaultSignedInAccount(unsigned __int64)

- ea: `0x180012a1c`
- end: `0x180012ded`
- name: `?GetDefaultSignedInAccount@Internal@System@Windows@@YA?AU?$pair@V?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@U_GUID@@@std@@_K@Z`
- size: `977`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800458e0`
- `0x180048bc0`
- `0x18005286c`

## callees

- `0x18000acdc`
- `0x180012a1c`
- `0x180012e00`
- `0x180012f10`
- `0x180013278`
- `0x1800132d0`
- `0x1800156bc`
- `0x18004e58c`
- `0x180054618`
- `0x180063fac`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012b25`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012b25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012d7e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012d7e`

## string_xrefs

- `0x180012a67`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012aa5`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012acc`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012b0f`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012b33`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012b8e`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012bdc`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012c36`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012c8e`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012cc7`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`
- `0x180012cff`: `onecore\ds\security\umstartup\usermgr\lib\webaccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall Windows::System::Internal::GetDefaultSignedInAccount(__int64 a1, __int64 a2)
{
  int v4; // eax
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  const char *v8; // r9
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rsi
  int v10; // eax
  __int64 *v11; // rcx
  int v12; // eax
  __int64 (__fastcall *v13)(__int64, __int64 *); // rsi
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-39h] BYREF
  __int64 *v20; // [rsp+28h] [rbp-31h] BYREF
  __int64 v21; // [rsp+30h] [rbp-29h] BYREF
  __int64 v22; // [rsp+38h] [rbp-21h] BYREF
  char v23; // [rsp+41h] [rbp-18h]
  __int64 v24; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-9h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp+7h] BYREF
  __int64 v28; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v29; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v26 = a1;
  v25 = 0;
  v4 = Windows::System::Internal::StaticsCache::GetStaticInstance<Windows::System::Internal::Implementation::IUserStaticsInternal>(&v25);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)(unsigned int)v4,
      v19);
  v21 = 0;
  v5 = *v25;
  v21 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 160))(v25, a2, &v21);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)(unsigned int)v6,
      v19);
  if ( !v21 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)0x80070490LL,
      v19);
  wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(
    &v21,
    &v26);
  hToken = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v26 + 80LL))(v26, &hToken);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)(unsigned int)v7,
      v19);
  if ( !ImpersonateLoggedOnUser(hToken) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      v8);
  v23 = 1;
  wil::GetActivationFactory<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>((const WCHAR *)&v24);
  v19 = 0;
  v20 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl'::`2'::impl) )
  {
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics,wil::err_exception_policy>::query<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(
      &v24,
      &v28);
    if ( !v28 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
        (const char *)0x80004002LL,
        v19);
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v28 + 56LL);
    v19 = 0;
    v10 = v9(v28, a2, &v19);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
        (const char *)(unsigned int)v10,
        v19);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  else
  {
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 232LL);
    v19 = 0;
    v14 = v13(v24, &v19);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
        (const char *)(unsigned int)v14,
        v19);
  }
  v11 = v20;
  v20 = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
  v12 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *>(
          v19,
          (__int64)&v20);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)(unsigned int)v12,
      v19);
  v22 = 0;
  v15 = *v20;
  v22 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 48))(v20, &v22);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)(unsigned int)v16,
      v19);
  v29 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v20 + 56))(v20, &v29);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\webaccounthelper.cpp",
      (const char *)(unsigned int)v17,
      v19);
  wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(
    a1,
    v22);
  *(_OWORD *)(a1 + 8) = v29;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v20 )
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  RevertToSelf();
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v25 )
    (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
  return a1;
}

```

## disassembly

```asm
0x180012a1c  mov     [rsp-8+arg_10], rbx
0x180012a21  push    rbp
0x180012a22  push    rsi
0x180012a23  push    rdi
0x180012a24  push    r14
0x180012a26  push    r15
0x180012a28  lea     rbp, [rsp-37h]
0x180012a2d  sub     rsp, 90h
0x180012a34  mov     rax, cs:__security_cookie
0x180012a3b  xor     rax, rsp
0x180012a3e  mov     [rbp+57h+var_28], rax
0x180012a42  mov     r14, rdx
0x180012a45  mov     rdi, rcx
0x180012a48  mov     [rbp+57h+var_58], rcx
0x180012a4c  xor     r15d, r15d
0x180012a4f  mov     [rbp+57h+var_60], r15
0x180012a53  lea     rcx, [rbp+57h+var_60]
0x180012a57  call    ??$GetStaticInstance@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@StaticsCache@Internal@System@Windows@@SAJPEAPEAUIUserStaticsInternal@Implementation@123@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Windows::System::Internal::Implementation::IUserStaticsInternal>(Windows::System::Internal::Implementation::IUserStaticsInternal * *,ulong)
0x180012a5c  mov     rcx, [rbp+5Fh]; this
0x180012a60  test    eax, eax
0x180012a62  jns     short loc_180012A78
0x180012a64  mov     r9d, eax; char *
0x180012a67  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012a6e  lea     edx, [r15+24h]; void *
0x180012a72  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012a78  mov     [rbp+57h+var_80], r15
0x180012a7c  mov     rcx, [rbp+57h+var_60]
0x180012a80  mov     rax, [rcx]
0x180012a83  mov     [rbp+57h+var_80], r15
0x180012a87  lea     r8, [rbp+57h+var_80]
0x180012a8b  mov     rdx, r14
0x180012a8e  mov     rax, [rax+0A0h]
0x180012a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a9a  mov     rcx, [rbp+5Fh]; this
0x180012a9e  test    eax, eax
0x180012aa0  jns     short loc_180012AB7
0x180012aa2  mov     r9d, eax; char *
0x180012aa5  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012aac  mov     edx, 27h ; '''; void *
0x180012ab1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012ab7  cmp     [rbp+57h+var_80], r15
0x180012abb  setz    al
0x180012abe  mov     rcx, [rbp+5Fh]; this
0x180012ac2  test    al, al
0x180012ac4  jz      short loc_180012ADE
0x180012ac6  mov     r9d, 80070490h; char *
0x180012acc  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012ad3  mov     edx, 28h ; '('; void *
0x180012ad8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012ade  lea     rdx, [rbp+57h+var_58]
0x180012ae2  lea     rcx, [rbp+57h+var_80]
0x180012ae6  call    ??$query@UIUserInternal@Implementation@Internal@System@Windows@@@?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUserInternal@Implementation@Internal@System@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(void)
0x180012aeb  nop
0x180012aec  mov     [rbp+57h+hToken], r15
0x180012af0  mov     rcx, [rbp+57h+var_58]
0x180012af4  mov     rax, [rcx]
0x180012af7  lea     rdx, [rbp+57h+hToken]
0x180012afb  mov     rax, [rax+50h]
0x180012aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b04  mov     rcx, [rbp+5Fh]; this
0x180012b08  test    eax, eax
0x180012b0a  jns     short loc_180012B21
0x180012b0c  mov     r9d, eax; char *
0x180012b0f  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012b16  mov     edx, 2Ch ; ','; void *
0x180012b1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012b21  mov     rcx, [rbp+57h+hToken]; hToken
0x180012b25  call    cs:__imp_ImpersonateLoggedOnUser
0x180012b2b  mov     rcx, [rbp+5Fh]; this
0x180012b2f  test    eax, eax
0x180012b31  jnz     short loc_180012B43
0x180012b33  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012b3a  lea     edx, [rax+2Fh]; void *
0x180012b3d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180012b43  mov     [rbp+57h+var_6F], 1
0x180012b47  lea     rcx, [rbp+57h+var_68]
0x180012b4b  call    ??$GetActivationFactory@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>(ushort const *)
0x180012b50  nop
0x180012b51  mov     [rbp+57h+var_90], r15
0x180012b55  mov     [rbp+57h+var_88], r15
0x180012b59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserPictureFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix> `wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl(void)'::`2'::impl
0x180012b60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(void)
0x180012b65  test    al, al
0x180012b67  jz      loc_180012C48
0x180012b6d  lea     rdx, [rbp+57h+var_48]
0x180012b71  lea     rcx, [rbp+57h+var_68]
0x180012b75  call    ??$query@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@@?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics,wil::err_exception_policy>::query<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(void)
0x180012b7a  nop
0x180012b7b  mov     rcx, [rbp+5Fh]; this
0x180012b7f  mov     rbx, [rbp+57h+var_48]
0x180012b83  test    rbx, rbx
0x180012b86  jnz     short loc_180012B9E
0x180012b88  mov     r9d, 80004002h; char *
0x180012b8e  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012b95  lea     edx, [rbx+39h]; void *
0x180012b98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012b9e  mov     rax, [rbx]
0x180012ba1  mov     rsi, [rax+38h]
0x180012ba5  mov     rcx, [rbp+57h+var_90]
0x180012ba9  mov     [rbp+57h+var_90], r15
0x180012bad  test    rcx, rcx
0x180012bb0  jz      short loc_180012BBF
0x180012bb2  mov     rax, [rcx]
0x180012bb5  mov     rax, [rax+10h]
0x180012bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bbe  nop
0x180012bbf  lea     r8, [rbp+57h+var_90]
0x180012bc3  mov     rdx, r14
0x180012bc6  mov     rcx, rbx
0x180012bc9  mov     rax, rsi
0x180012bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bd1  mov     rcx, [rbp+5Fh]; this
0x180012bd5  test    eax, eax
0x180012bd7  jns     short loc_180012BEE
0x180012bd9  mov     r9d, eax; char *
0x180012bdc  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012be3  mov     edx, 3Ah ; ':'; void *
0x180012be8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012bee  mov     rcx, [rbp+57h+var_48]
0x180012bf2  test    rcx, rcx
0x180012bf5  jz      short loc_180012C04
0x180012bf7  mov     rax, [rcx]
0x180012bfa  mov     rax, [rax+10h]
0x180012bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c03  nop
0x180012c04  mov     rcx, [rbp+57h+var_88]
0x180012c08  mov     [rbp+57h+var_88], r15
0x180012c0c  test    rcx, rcx
0x180012c0f  jz      short loc_180012C1E
0x180012c11  mov     rax, [rcx]
0x180012c14  mov     rax, [rax+10h]
0x180012c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c1d  nop
0x180012c1e  lea     rdx, [rbp+57h+var_88]
0x180012c22  mov     rcx, [rbp+57h+var_90]
0x180012c26  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@PEAUIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@3@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@PEAPEAUIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@2@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult * *,tagCOWAIT_FLAGS,void *)
0x180012c2b  mov     rcx, [rbp+5Fh]; this
0x180012c2f  test    eax, eax
0x180012c31  jns     short loc_180012CA0
0x180012c33  mov     r9d, eax; char *
0x180012c36  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012c3d  mov     edx, 41h ; 'A'; void *
0x180012c42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012c48  mov     rbx, [rbp+57h+var_68]
0x180012c4c  mov     rax, [rbx]
0x180012c4f  mov     rsi, [rax+0E8h]
0x180012c56  mov     rcx, [rbp+57h+var_90]
0x180012c5a  mov     [rbp+57h+var_90], r15
0x180012c5e  test    rcx, rcx
0x180012c61  jz      short loc_180012C70
0x180012c63  mov     rax, [rcx]
0x180012c66  mov     rax, [rax+10h]
0x180012c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c6f  nop
0x180012c70  lea     rdx, [rbp+57h+var_90]
0x180012c74  mov     rcx, rbx
0x180012c77  mov     rax, rsi
0x180012c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c7f  mov     rcx, [rbp+5Fh]; this
0x180012c83  test    eax, eax
0x180012c85  jns     loc_180012C04
0x180012c8b  mov     r9d, eax; char *
0x180012c8e  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012c95  mov     edx, 3Eh ; '>'; void *
0x180012c9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012ca0  mov     [rbp+57h+var_78], r15
0x180012ca4  mov     rcx, [rbp+57h+var_88]
0x180012ca8  mov     rax, [rcx]
0x180012cab  mov     [rbp+57h+var_78], r15
0x180012caf  lea     rdx, [rbp+57h+var_78]
0x180012cb3  mov     rax, [rax+30h]
0x180012cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cbc  mov     rcx, [rbp+5Fh]; this
0x180012cc0  test    eax, eax
0x180012cc2  jns     short loc_180012CD9
0x180012cc4  mov     r9d, eax; char *
0x180012cc7  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012cce  mov     edx, 44h ; 'D'; void *
0x180012cd3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012cd9  xorps   xmm0, xmm0
0x180012cdc  movups  [rbp+57h+var_38], xmm0
0x180012ce0  mov     rcx, [rbp+57h+var_88]
0x180012ce4  mov     rax, [rcx]
0x180012ce7  lea     rdx, [rbp+57h+var_38]
0x180012ceb  mov     rax, [rax+38h]
0x180012cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf4  mov     rcx, [rbp+5Fh]; this
0x180012cf8  test    eax, eax
0x180012cfa  jns     short loc_180012D11
0x180012cfc  mov     r9d, eax; char *
0x180012cff  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\umstartup\\userm"...
0x180012d06  mov     edx, 47h ; 'G'; void *
0x180012d0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012d11  mov     rdx, [rbp+57h+var_78]
0x180012d15  mov     rcx, rdi
0x180012d18  call    ??0?$com_ptr_t@UISignInContext@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUISignInContext@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(Windows::System::Internal::ISignInContext *)
0x180012d1d  movups  xmm0, [rbp+57h+var_38]
0x180012d21  movdqu  xmmword ptr [rdi+8], xmm0
0x180012d26  mov     rcx, [rbp+57h+var_78]
0x180012d2a  test    rcx, rcx
0x180012d2d  jz      short loc_180012D3C
0x180012d2f  mov     rax, [rcx]
0x180012d32  mov     rax, [rax+10h]
0x180012d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d3b  nop
0x180012d3c  mov     rcx, [rbp+57h+var_88]
0x180012d40  test    rcx, rcx
0x180012d43  jz      short loc_180012D52
0x180012d45  mov     rax, [rcx]
0x180012d48  mov     rax, [rax+10h]
0x180012d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d51  nop
0x180012d52  mov     rcx, [rbp+57h+var_90]
0x180012d56  test    rcx, rcx
0x180012d59  jz      short loc_180012D68
0x180012d5b  mov     rax, [rcx]
0x180012d5e  mov     rax, [rax+10h]
0x180012d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d67  nop
0x180012d68  mov     rcx, [rbp+57h+var_68]
0x180012d6c  test    rcx, rcx
0x180012d6f  jz      short loc_180012D7E
0x180012d71  mov     rax, [rcx]
0x180012d74  mov     rax, [rax+10h]
0x180012d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d7d  nop
0x180012d7e  call    cs:__imp_RevertToSelf
0x180012d84  nop
0x180012d85  mov     rcx, [rbp+57h+var_58]
0x180012d89  test    rcx, rcx
0x180012d8c  jz      short loc_180012D9B
0x180012d8e  mov     rax, [rcx]
0x180012d91  mov     rax, [rax+10h]
0x180012d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d9a  nop
0x180012d9b  mov     rcx, [rbp+57h+var_80]
0x180012d9f  test    rcx, rcx
0x180012da2  jz      short loc_180012DB1
0x180012da4  mov     rax, [rcx]
0x180012da7  mov     rax, [rax+10h]
0x180012dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db0  nop
0x180012db1  mov     rcx, [rbp+57h+var_60]
0x180012db5  test    rcx, rcx
0x180012db8  jz      short loc_180012DC7
0x180012dba  mov     rdx, [rcx]
0x180012dbd  mov     rax, [rdx+10h]
0x180012dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dc6  nop
0x180012dc7  mov     rax, rdi
0x180012dca  mov     rcx, [rbp+57h+var_28]
0x180012dce  xor     rcx, rsp; StackCookie
0x180012dd1  call    __security_check_cookie
0x180012dd6  mov     rbx, [rsp+0B0h+arg_10]
0x180012dde  add     rsp, 90h
0x180012de5  pop     r15
0x180012de7  pop     r14
0x180012de9  pop     rdi
0x180012dea  pop     rsi
0x180012deb  pop     rbp
0x180012dec  retn
```
