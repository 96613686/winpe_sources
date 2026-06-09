# _lambda_e7afd5546cf7fe2ec72f4884e8ea035c_::operator()

- ea: `0x14001f310`
- end: `0x14001f484`
- name: `_lambda_e7afd5546cf7fe2ec72f4884e8ea035c_::operator()`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003a6d4`

## callees

- `0x140005260`
- `0x140005e4c`
- `0x14001f310`
- `0x14001f48c`
- `0x14001f4b8`
- `0x14001f508`
- `0x140025aa0`
- `0x140068010`

## string_xrefs

- `0x14001f356`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x14001f3d9`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x14001f421`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_e7afd5546cf7fe2ec72f4884e8ea035c_::operator()(_QWORD **a1)
{
  __int64 v2; // rcx
  int v3; // eax
  _QWORD **v4; // rdi
  _QWORD *i; // rbx
  __int64 v6; // r14
  __int64 (__fastcall *v7)(__int64, _QWORD); // rsi
  _QWORD *v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  _QWORD *v14; // rbx
  __int64 v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+28h] [rbp-20h] BYREF
  __int64 v19; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v17 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v17);
  v3 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::SmartScreen::ButtonInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0>>(
         v2,
         &v17);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
      (const char *)(unsigned int)v3,
      v17);
  v4 = (_QWORD **)(*a1)[24];
  for ( i = *v4; i != v4; i = (_QWORD *)*i )
  {
    v6 = v17;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 104LL);
    v8 = (_QWORD *)windows::rt::make__anonymous_namespace_::com_button_os_smartscreen::ux::NotificationButton_const___api_guard___(
                     &v18,
                     i + 2,
                     *a1 + 27);
    v9 = v7(v6, *v8);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
        (const char *)(unsigned int)v9,
        v17);
    v10 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  v19 = 0;
  v11 = v17;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v13 = v12(v11, &v19);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
      (const char *)(unsigned int)v13,
      v17);
  v14 = (_QWORD *)*a1[1];
  v15 = v19;
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
    v15 = v19;
  }
  *v14 = v15;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v17);
  return 0;
}

```

## disassembly

```asm
0x14001f310  push    rbp
0x14001f312  push    rbx
0x14001f313  push    rsi
0x14001f314  push    rdi
0x14001f315  push    r14
0x14001f317  push    r15
0x14001f319  mov     rbp, rsp
0x14001f31c  sub     rsp, 48h
0x14001f320  mov     rax, cs:__security_cookie
0x14001f327  xor     rax, rsp
0x14001f32a  mov     [rbp+var_10], rax
0x14001f32e  mov     r15, rcx
0x14001f331  mov     [rbp+var_28], 0
0x14001f339  lea     rcx, [rbp+var_28]
0x14001f33d  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x14001f342  lea     rdx, [rbp+var_28]
0x14001f346  call    ??$CreateExternalObjectVector@VButtonInfo@SmartScreen@Security@Internal@Windows@@V?$AgileVector@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4785@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::SmartScreen::ButtonInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0> * *)
0x14001f34b  mov     rcx, [rbp+30h]; this
0x14001f34f  test    eax, eax
0x14001f351  jns     short loc_14001F368
0x14001f353  mov     r9d, eax; char *
0x14001f356  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001f35d  mov     edx, 0D1h; void *
0x14001f362  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001f368  mov     rdi, [r15]
0x14001f36b  mov     rdi, [rdi+0C0h]
0x14001f372  mov     rbx, [rdi]
0x14001f375  cmp     rbx, rdi
0x14001f378  jz      short loc_14001F3EB
0x14001f37a  mov     r14, [rbp+var_28]
0x14001f37e  mov     rax, [r14]
0x14001f381  mov     rsi, [rax+68h]
0x14001f385  mov     r8, [r15]
0x14001f388  add     r8, 0D8h
0x14001f38f  lea     rdx, [rbx+10h]
0x14001f393  lea     rcx, [rbp+var_20]
0x14001f397  call    windows__rt__make__anonymous_namespace___com_button_os_smartscreen__ux__NotificationButton_const___api_guard___
0x14001f39c  nop
0x14001f39d  mov     rdx, [rax]
0x14001f3a0  mov     rcx, r14
0x14001f3a3  mov     rax, rsi
0x14001f3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f3ab  mov     rcx, [rbp+30h]; this
0x14001f3af  test    eax, eax
0x14001f3b1  js      short loc_14001F3D6
0x14001f3b3  mov     rcx, [rbp+var_20]
0x14001f3b7  test    rcx, rcx
0x14001f3ba  jz      short loc_14001F3D1
0x14001f3bc  mov     [rbp+var_20], 0
0x14001f3c4  mov     rax, [rcx]
0x14001f3c7  mov     rax, [rax+10h]
0x14001f3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f3d0  nop
0x14001f3d1  mov     rbx, [rbx]
0x14001f3d4  jmp     short loc_14001F375
0x14001f3d6  mov     r9d, eax; char *
0x14001f3d9  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001f3e0  mov     edx, 0D5h; void *
0x14001f3e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001f3eb  mov     [rbp+var_18], 0
0x14001f3f3  mov     rdi, [rbp+var_28]
0x14001f3f7  mov     rax, [rdi]
0x14001f3fa  mov     rbx, [rax+40h]
0x14001f3fe  lea     rcx, [rbp+var_18]
0x14001f402  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f407  lea     rdx, [rbp+var_18]
0x14001f40b  mov     rcx, rdi
0x14001f40e  mov     rax, rbx
0x14001f411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f416  mov     rcx, [rbp+30h]; this
0x14001f41a  test    eax, eax
0x14001f41c  jns     short loc_14001F433
0x14001f41e  mov     r9d, eax; char *
0x14001f421  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14001f428  mov     edx, 0D9h; void *
0x14001f42d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001f433  mov     rax, [r15+8]
0x14001f437  mov     rbx, [rax]
0x14001f43a  mov     rcx, [rbp+var_18]
0x14001f43e  test    rcx, rcx
0x14001f441  jz      short loc_14001F453
0x14001f443  mov     rax, [rcx]
0x14001f446  mov     rax, [rax+8]
0x14001f44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f44f  mov     rcx, [rbp+var_18]
0x14001f453  mov     [rbx], rcx
0x14001f456  lea     rcx, [rbp+var_18]
0x14001f45a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f45f  nop
0x14001f460  lea     rcx, [rbp+var_28]
0x14001f464  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x14001f469  xor     eax, eax
0x14001f46b  mov     rcx, [rbp+var_10]
0x14001f46f  xor     rcx, rsp; StackCookie
0x14001f472  call    __security_check_cookie
0x14001f477  add     rsp, 48h
0x14001f47b  pop     r15
0x14001f47d  pop     r14
0x14001f47f  pop     rdi
0x14001f480  pop     rsi
0x14001f481  pop     rbx
0x14001f482  pop     rbp
0x14001f483  retn
```
