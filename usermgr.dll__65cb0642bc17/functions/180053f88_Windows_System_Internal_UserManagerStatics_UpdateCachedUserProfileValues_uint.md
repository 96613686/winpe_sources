# Windows::System::Internal::UserManagerStatics::UpdateCachedUserProfileValues(uint)

- ea: `0x180053f88`
- end: `0x180054498`
- name: `?UpdateCachedUserProfileValues@UserManagerStatics@Internal@System@Windows@@AEAAXI@Z`
- size: `1296`
- prototype: `void __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180089fe0`

## callees

- `0x18000acdc`
- `0x180012f10`
- `0x180013278`
- `0x1800156bc`
- `0x1800181f0`
- `0x1800332e8`
- `0x18003b578`
- `0x18004ba28`
- `0x18004e58c`
- `0x180053f88`
- `0x1800544a0`
- `0x180054544`
- `0x1800545f4`
- `0x180054618`
- `0x180063fac`
- `0x18007512c`
- `0x1800d2540`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800540bd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800540bd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800543bb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800543bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054445`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005445b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800542ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054445`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005445b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180053fe7`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180053fe7`

## string_xrefs

- `0x180054015`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005403c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005407f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800540cb`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180054154`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005418c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800541e0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180054220`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180054251`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800543e8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005441b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall Windows::System::Internal::UserManagerStatics::UpdateCachedUserProfileValues(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2)
{
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rbx
  __int64 (__fastcall *v4)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD); // rdi
  unsigned int CurrentServiceSessionId; // eax
  int v6; // eax
  HSTRING v7; // [rsp+48h] [rbp-61h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v7 = 0;
  UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
  v4 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)UserStaticsInternal + 136LL);
  v7 = 0;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId(0);
  v6 = v4(UserStaticsInternal, a2, CurrentServiceSessionId, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C9E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v6,
      (int)&v7);
  wil::details::in1diag3::Throw_Hr(
    retaddr,
    (void *)0x1C9F,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
    (const char *)0x80070490LL,
    (int)&v7);
}

```

## disassembly

```asm
0x180053f88  mov     [rsp-8+arg_10], rbx
0x180053f8d  push    rbp
0x180053f8e  push    rsi
0x180053f8f  push    rdi
0x180053f90  push    r14
0x180053f92  push    r15
0x180053f94  lea     rbp, [rsp-37h]
0x180053f99  sub     rsp, 0E0h
0x180053fa0  mov     rax, cs:__security_cookie
0x180053fa7  xor     rax, rsp
0x180053faa  mov     [rbp+57h+var_30], rax
0x180053fae  mov     r14d, edx
0x180053fb1  mov     rsi, rcx
0x180053fb4  xor     r15d, r15d
0x180053fb7  mov     [rbp+57h+var_B8], r15
0x180053fbb  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180053fc0  mov     rbx, rax
0x180053fc3  mov     rdx, [rax]
0x180053fc6  mov     rdi, [rdx+88h]
0x180053fcd  mov     rcx, [rbp+57h+var_B8]
0x180053fd1  mov     [rbp+57h+var_B8], r15
0x180053fd5  test    rcx, rcx
0x180053fd8  jz      short loc_180053FE7
0x180053fda  mov     rdx, [rcx]
0x180053fdd  mov     rax, [rdx+10h]
0x180053fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fe6  nop
0x180053fe7  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180053fed  lea     rcx, [rbp+57h+var_B8]
0x180053ff1  mov     [rsp+100h+var_E0], rcx; int
0x180053ff6  xor     r9d, r9d
0x180053ff9  mov     r8d, eax
0x180053ffc  mov     edx, r14d
0x180053fff  mov     rcx, rbx
0x180054002  mov     rax, rdi
0x180054005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005400a  mov     rcx, [rbp+5Fh]; this
0x18005400e  test    eax, eax
0x180054010  jns     short loc_180054027
0x180054012  mov     r9d, eax; char *
0x180054015  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18005401c  mov     edx, 1C9Eh; void *
0x180054021  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054027  cmp     [rbp+57h+var_B8], r15
0x18005402b  setz    al
0x18005402e  mov     rcx, [rbp+5Fh]; this
0x180054032  test    al, al
0x180054034  jz      short loc_18005404E
0x180054036  mov     r9d, 80070490h; char *
0x18005403c  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180054043  mov     edx, 1C9Fh; void *
0x180054048  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005404e  lea     rdx, [rbp+57h+var_68]
0x180054052  lea     rcx, [rbp+57h+var_B8]
0x180054056  call    ??$query@UIUserInternal@Implementation@Internal@System@Windows@@@?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUserInternal@Implementation@Internal@System@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::query<Windows::System::Internal::Implementation::IUserInternal>(void)
0x18005405b  nop
0x18005405c  mov     [rbp+57h+hToken], r15
0x180054060  mov     rcx, [rbp+57h+var_68]
0x180054064  mov     rax, [rcx]
0x180054067  lea     rdx, [rbp+57h+hToken]
0x18005406b  mov     rax, [rax+50h]
0x18005406f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054074  mov     rcx, [rbp+5Fh]; this
0x180054078  test    eax, eax
0x18005407a  jns     short loc_180054091
0x18005407c  mov     r9d, eax; char *
0x18005407f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180054086  mov     edx, 1CA3h; void *
0x18005408b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054091  mov     [rbp+57h+var_90], r15
0x180054095  mov     [rbp+57h+var_98], r15
0x180054099  mov     [rbp+57h+string], r15
0x18005409d  lea     rcx, [rbp+57h+var_70]
0x1800540a1  call    ??$ActivateInstance@UIPropertySet@Collections@Foundation@Windows@@@wil@@YA?AV?$com_ptr_t@UIPropertySet@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Foundation::Collections::IPropertySet>(ushort const *)
0x1800540a6  nop
0x1800540a7  lea     rdx, [rbp+57h+var_A8]
0x1800540ab  lea     rcx, [rbp+57h+var_70]
0x1800540af  call    ??$query@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$com_ptr_t@UIPropertySet@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IPropertySet,wil::err_exception_policy>::query<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(void)
0x1800540b4  nop
0x1800540b5  mov     [rbp+57h+var_D0], r15b
0x1800540b9  mov     rcx, [rbp+57h+hToken]; hToken
0x1800540bd  call    cs:__imp_ImpersonateLoggedOnUser
0x1800540c3  mov     rcx, [rbp+5Fh]; this
0x1800540c7  test    eax, eax
0x1800540c9  jnz     short loc_1800540DD
0x1800540cb  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800540d2  mov     edx, 1CAFh; void *
0x1800540d7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800540dd  mov     [rbp+57h+var_87], 1
0x1800540e1  lea     rcx, [rbp+57h+var_78]
0x1800540e5  call    ??$GetActivationFactory@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>(ushort const *)
0x1800540ea  nop
0x1800540eb  mov     [rbp+57h+var_C8], r15
0x1800540ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserPictureFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix> `wil::Feature<__WilFeatureTraits_Feature_UserPictureFix>::GetImpl(void)'::`2'::impl
0x1800540f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UserPictureFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserPictureFix>::__private_IsEnabled(void)
0x1800540fb  test    al, al
0x1800540fd  jz      loc_18005419E
0x180054103  lea     rdx, [rbp+57h+hstringHeader]
0x180054107  lea     rcx, [rbp+57h+var_78]
0x18005410b  call    ??$query@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@@?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics,wil::err_exception_policy>::query<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(void)
0x180054110  nop
0x180054111  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180054115  mov     rax, [rbx]
0x180054118  mov     rdi, [rax+38h]
0x18005411c  mov     rcx, [rbp+57h+var_C8]
0x180054120  mov     [rbp+57h+var_C8], r15
0x180054124  test    rcx, rcx
0x180054127  jz      short loc_180054136
0x180054129  mov     rdx, [rcx]
0x18005412c  mov     rax, [rdx+10h]
0x180054130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054135  nop
0x180054136  lea     r8, [rbp+57h+var_C8]
0x18005413a  mov     rdx, [rbp+57h+hToken]
0x18005413e  mov     rcx, rbx
0x180054141  mov     rax, rdi
0x180054144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054149  mov     rcx, [rbp+5Fh]; this
0x18005414d  test    eax, eax
0x18005414f  jns     short loc_180054166
0x180054151  mov     r9d, eax; char *
0x180054154  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18005415b  mov     edx, 1CB9h; void *
0x180054160  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054166  lea     rcx, [rbp+57h+hstringHeader]
0x18005416a  call    ??1?$com_ptr_t@UIValidateCredentialsResult@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IValidateCredentialsResult,wil::err_exception_policy>(void)
0x18005416f  nop
0x180054170  mov     [rbp+57h+var_B0], r15
0x180054174  lea     rdx, [rbp+57h+var_B0]
0x180054178  mov     rcx, [rbp+57h+var_C8]
0x18005417c  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@PEAUIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@3@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@PEAPEAUIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@2@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult * *,tagCOWAIT_FLAGS,void *)
0x180054181  mov     rcx, [rbp+5Fh]; this
0x180054185  test    eax, eax
0x180054187  jns     short loc_1800541F2
0x180054189  mov     r9d, eax; char *
0x18005418c  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180054193  mov     edx, 1CC1h; void *
0x180054198  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005419e  mov     rbx, [rbp+57h+var_78]
0x1800541a2  mov     rax, [rbx]
0x1800541a5  mov     rdi, [rax+0E8h]
0x1800541ac  mov     rcx, [rbp+57h+var_C8]
0x1800541b0  mov     [rbp+57h+var_C8], r15
0x1800541b4  test    rcx, rcx
0x1800541b7  jz      short loc_1800541C6
0x1800541b9  mov     rdx, [rcx]
0x1800541bc  mov     rax, [rdx+10h]
0x1800541c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541c5  nop
0x1800541c6  lea     rdx, [rbp+57h+var_C8]
0x1800541ca  mov     rcx, rbx
0x1800541cd  mov     rax, rdi
0x1800541d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541d5  mov     rcx, [rbp+5Fh]; this
0x1800541d9  test    eax, eax
0x1800541db  jns     short loc_180054170
0x1800541dd  mov     r9d, eax; char *
0x1800541e0  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800541e7  mov     edx, 1CBDh; void *
0x1800541ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800541f2  mov     [rbp+57h+var_C0], r15
0x1800541f6  xorps   xmm0, xmm0
0x1800541f9  movups  [rbp+57h+var_40], xmm0
0x1800541fd  mov     rcx, [rbp+57h+var_B0]
0x180054201  mov     rax, [rcx]
0x180054204  mov     [rbp+57h+var_C0], r15
0x180054208  lea     rdx, [rbp+57h+var_C0]
0x18005420c  mov     rax, [rax+30h]
0x180054210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054215  mov     rcx, [rbp+5Fh]; this
0x180054219  test    eax, eax
0x18005421b  jns     short loc_180054232
0x18005421d  mov     r9d, eax; char *
0x180054220  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180054227  mov     edx, 1CC5h; void *
0x18005422c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054232  mov     rcx, [rbp+57h+var_B0]
0x180054236  mov     rax, [rcx]
0x180054239  lea     rdx, [rbp+57h+var_40]
0x18005423d  mov     rax, [rax+38h]
0x180054241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054246  mov     rcx, [rbp+5Fh]; this
0x18005424a  test    eax, eax
0x18005424c  jns     short loc_180054263
0x18005424e  mov     r9d, eax; char *
0x180054251  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180054258  mov     edx, 1CC6h; void *
0x18005425d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054263  xor     ecx, ecx; string
0x180054265  call    cs:__imp_WindowsDeleteString
0x18005426b  mov     [rbp+57h+var_90], r15
0x18005426f  movaps  xmm0, [rbp+57h+var_40]
0x180054273  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180054278  lea     r9, [rbp+57h+var_90]; unsigned int
0x18005427c  mov     r8d, 1; struct Windows::Security::Credentials::IWebAccount *
0x180054282  mov     rdx, [rbp+57h+var_C0]; struct _GUID
0x180054286  lea     rcx, [rbp+57h+hstringHeader]; this
0x18005428a  call    ?GetKnownUserPropertyValue@Internal@System@Windows@@YAJU_GUID@@PEAUIWebAccount@Credentials@Security@3@KPEAPEAUHSTRING__@@@Z; Windows::System::Internal::GetKnownUserPropertyValue(_GUID,Windows::Security::Credentials::IWebAccount *,ulong,HSTRING__ * *)
0x18005428f  test    eax, eax
0x180054291  js      short loc_1800542C8
0x180054293  mov     [rbp+57h+var_48], r15
0x180054297  mov     r9d, 0Bh; unsigned int
0x18005429d  lea     r8d, [r9+1]; unsigned int
0x1800542a1  lea     rdx, aDisplayname_1; "DisplayName"
0x1800542a8  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800542ac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800542b1  nop
0x1800542b2  lea     r9, [rbp+57h+var_D0]
0x1800542b6  mov     r8, [rbp+57h+var_90]
0x1800542ba  mov     rdx, [rbp+57h+var_48]
0x1800542be  mov     rcx, [rbp+57h+var_A8]
0x1800542c2  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800542c7  nop
0x1800542c8  xor     ecx, ecx; string
0x1800542ca  call    cs:__imp_WindowsDeleteString
0x1800542d0  mov     [rbp+57h+var_98], r15
0x1800542d4  movaps  xmm0, [rbp+57h+var_40]
0x1800542d8  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800542dd  lea     r9, [rbp+57h+var_98]; unsigned int
0x1800542e1  mov     r8d, 2; struct Windows::Security::Credentials::IWebAccount *
0x1800542e7  mov     rdx, [rbp+57h+var_C0]; struct _GUID
0x1800542eb  lea     rcx, [rbp+57h+hstringHeader]; this
0x1800542ef  call    ?GetKnownUserPropertyValue@Internal@System@Windows@@YAJU_GUID@@PEAUIWebAccount@Credentials@Security@3@KPEAPEAUHSTRING__@@@Z; Windows::System::Internal::GetKnownUserPropertyValue(_GUID,Windows::Security::Credentials::IWebAccount *,ulong,HSTRING__ * *)
0x1800542f4  mov     ebx, 9
0x1800542f9  test    eax, eax
0x1800542fb  js      short loc_18005432F
0x1800542fd  mov     [rbp+57h+var_48], r15
0x180054301  mov     r9d, ebx; unsigned int
0x180054304  lea     r8d, [rbx+1]; unsigned int
0x180054308  lea     rdx, aFirstname_1; "FirstName"
0x18005430f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180054313  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180054318  nop
0x180054319  lea     r9, [rbp+57h+var_D0]
0x18005431d  mov     r8, [rbp+57h+var_98]
0x180054321  mov     rdx, [rbp+57h+var_48]
0x180054325  mov     rcx, [rbp+57h+var_A8]
0x180054329  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x18005432e  nop
0x18005432f  xor     ecx, ecx; string
0x180054331  call    cs:__imp_WindowsDeleteString
0x180054337  mov     [rbp+57h+string], r15
0x18005433b  movaps  xmm0, [rbp+57h+var_40]
0x18005433f  movdqa  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180054344  lea     r9, [rbp+57h+string]; unsigned int
0x180054348  mov     r8d, 3; struct Windows::Security::Credentials::IWebAccount *
0x18005434e  mov     rdx, [rbp+57h+var_C0]; struct _GUID
0x180054352  lea     rcx, [rbp+57h+hstringHeader]; this
0x180054356  call    ?GetKnownUserPropertyValue@Internal@System@Windows@@YAJU_GUID@@PEAUIWebAccount@Credentials@Security@3@KPEAPEAUHSTRING__@@@Z; Windows::System::Internal::GetKnownUserPropertyValue(_GUID,Windows::Security::Credentials::IWebAccount *,ulong,HSTRING__ * *)
0x18005435b  test    eax, eax
0x18005435d  js      short loc_180054393
0x18005435f  mov     [rbp+57h+var_48], r15
0x180054363  mov     r9d, 8; unsigned int
0x180054369  mov     r8d, ebx; unsigned int
0x18005436c  lea     rdx, aLastname_1; "LastName"
0x180054373  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180054377  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005437c  nop
0x18005437d  lea     r9, [rbp+57h+var_D0]
0x180054381  mov     r8, [rbp+57h+string]
0x180054385  mov     rdx, [rbp+57h+var_48]
0x180054389  mov     rcx, [rbp+57h+var_A8]
0x18005438d  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x180054392  nop
0x180054393  lea     rcx, [rbp+57h+var_C0]
0x180054397  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18005439c  nop
0x18005439d  lea     rcx, [rbp+57h+var_B0]
0x1800543a1  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x1800543a6  nop
0x1800543a7  lea     rcx, [rbp+57h+var_C8]
0x1800543ab  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x1800543b0  nop
0x1800543b1  lea     rcx, [rbp+57h+var_78]
0x1800543b5  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x1800543ba  nop
0x1800543bb  call    cs:__imp_RevertToSelf
0x1800543c1  lea     rcx, [rsi+220h]
0x1800543c8  mov     edx, 7530h
0x1800543cd  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x1800543d2  mov     rax, [rbp+5Fh]
0x1800543d6  mov     rcx, [rsi+218h]
0x1800543dd  test    rcx, rcx
0x1800543e0  jnz     short loc_1800543FD
0x1800543e2  mov     r9d, 8000FFFFh; char *
0x1800543e8  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800543ef  mov     edx, 1CDAh; void *
0x1800543f4  mov     rcx, rax; this
0x1800543f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800543fd  mov     rax, [rcx]
0x180054400  mov     r8, [rbp+57h+var_70]
0x180054404  mov     edx, r14d
0x180054407  mov     rax, [rax+70h]
0x18005440b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054410  mov     rcx, [rbp+5Fh]; this
0x180054414  test    eax, eax
0x180054416  jns     short loc_18005442D
0x180054418  mov     r9d, eax; char *
0x18005441b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180054422  mov     edx, 1CDCh; void *
  ... truncated ...
```
