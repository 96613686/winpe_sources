# _lambda_e7afd5546cf7fe2ec72f4884e8ea035c_::operator()

- ea: `0x140020440`
- end: `0x1400205b5`
- name: `_lambda_e7afd5546cf7fe2ec72f4884e8ea035c_::operator()`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003bd28`

## callees

- `0x1400055ac`
- `0x1400061cc`
- `0x140020440`
- `0x1400205bc`
- `0x1400205ec`
- `0x14002063c`
- `0x140026c20`
- `0x14006a010`

## string_xrefs

- `0x140020486`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140020509`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`
- `0x140020551`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

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
0x140020440  push    rbp
0x140020442  push    rbx
0x140020443  push    rsi
0x140020444  push    rdi
0x140020445  push    r14
0x140020447  push    r15
0x140020449  mov     rbp, rsp
0x14002044c  sub     rsp, 48h
0x140020450  mov     rax, cs:__security_cookie
0x140020457  xor     rax, rsp
0x14002045a  mov     [rbp+var_10], rax
0x14002045e  mov     r15, rcx
0x140020461  mov     [rbp+var_28], 0
0x140020469  lea     rcx, [rbp+var_28]
0x14002046d  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x140020472  lea     rdx, [rbp+var_28]
0x140020476  call    ??$CreateExternalObjectVector@VButtonInfo@SmartScreen@Security@Internal@Windows@@V?$AgileVector@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVButtonInfo@SmartScreen@Security@Internal@Windows@@@4785@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::SmartScreen::ButtonInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::SmartScreen::ButtonInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::SmartScreen::ButtonInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::SmartScreen::ButtonInfo *>,0> * *)
0x14002047b  mov     rcx, [rbp+30h]; this
0x14002047f  test    eax, eax
0x140020481  jns     short loc_140020498
0x140020483  mov     r9d, eax; char *
0x140020486  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14002048d  mov     edx, 0D1h; void *
0x140020492  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140020498  mov     rdi, [r15]
0x14002049b  mov     rdi, [rdi+0C0h]
0x1400204a2  mov     rbx, [rdi]
0x1400204a5  cmp     rbx, rdi
0x1400204a8  jz      short loc_14002051B
0x1400204aa  mov     r14, [rbp+var_28]
0x1400204ae  mov     rax, [r14]
0x1400204b1  mov     rsi, [rax+68h]
0x1400204b5  mov     r8, [r15]
0x1400204b8  add     r8, 0D8h
0x1400204bf  lea     rdx, [rbx+10h]
0x1400204c3  lea     rcx, [rbp+var_20]
0x1400204c7  call    windows__rt__make__anonymous_namespace___com_button_os_smartscreen__ux__NotificationButton_const___api_guard___
0x1400204cc  nop
0x1400204cd  mov     rdx, [rax]
0x1400204d0  mov     rcx, r14
0x1400204d3  mov     rax, rsi
0x1400204d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400204db  mov     rcx, [rbp+30h]; this
0x1400204df  test    eax, eax
0x1400204e1  js      short loc_140020506
0x1400204e3  mov     rcx, [rbp+var_20]
0x1400204e7  test    rcx, rcx
0x1400204ea  jz      short loc_140020501
0x1400204ec  mov     [rbp+var_20], 0
0x1400204f4  mov     rax, [rcx]
0x1400204f7  mov     rax, [rax+10h]
0x1400204fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020500  nop
0x140020501  mov     rbx, [rbx]
0x140020504  jmp     short loc_1400204A5
0x140020506  mov     r9d, eax; char *
0x140020509  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140020510  mov     edx, 0D5h; void *
0x140020515  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002051b  mov     [rbp+var_18], 0
0x140020523  mov     rdi, [rbp+var_28]
0x140020527  mov     rax, [rdi]
0x14002052a  mov     rbx, [rax+40h]
0x14002052e  lea     rcx, [rbp+var_18]
0x140020532  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140020537  lea     rdx, [rbp+var_18]
0x14002053b  mov     rcx, rdi
0x14002053e  mov     rax, rbx
0x140020541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020546  mov     rcx, [rbp+30h]; this
0x14002054a  test    eax, eax
0x14002054c  jns     short loc_140020563
0x14002054e  mov     r9d, eax; char *
0x140020551  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140020558  mov     edx, 0D9h; void *
0x14002055d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140020563  mov     rax, [r15+8]
0x140020567  mov     rbx, [rax]
0x14002056a  mov     rcx, [rbp+var_18]
0x14002056e  test    rcx, rcx
0x140020571  jz      short loc_140020583
0x140020573  mov     rax, [rcx]
0x140020576  mov     rax, [rax+8]
0x14002057a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002057f  mov     rcx, [rbp+var_18]
0x140020583  mov     [rbx], rcx
0x140020586  lea     rcx, [rbp+var_18]
0x14002058a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14002058f  nop
0x140020590  lea     rcx, [rbp+var_28]
0x140020594  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x140020599  xor     eax, eax
0x14002059b  mov     rcx, [rbp+var_10]
0x14002059f  xor     rcx, rsp; StackCookie
0x1400205a2  call    __security_check_cookie
0x1400205a7  add     rsp, 48h
0x1400205ab  pop     r15
0x1400205ad  pop     r14
0x1400205af  pop     rdi
0x1400205b0  pop     rsi
0x1400205b1  pop     rbx
0x1400205b2  pop     rbp
0x1400205b3  retn
```
