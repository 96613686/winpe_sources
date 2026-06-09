# Windows::System::Internal::SignInResult::~SignInResult(void)

- ea: `0x1800c02b0`
- end: `0x1800c03bc`
- name: `??1SignInResult@Internal@System@Windows@@UEAA@XZ`
- size: `268`
- prototype: `void __fastcall(Windows::System::Internal::SignInResult *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c0410`

## callees

- `0x180071434`
- `0x1800c0280`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c033c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0364`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c033c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0364`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0378`

## pseudocode

```c
void __fastcall Windows::System::Internal::SignInResult::~SignInResult(Windows::System::Internal::SignInResult *this)
{
  *(_QWORD *)this = &Windows::System::Internal::SignInResult::`vftable';
  *((_QWORD *)this + 1) = &Windows::System::Internal::SignInResult::`vftable'{for `IUserAuthenticationCallback'};
  *((_QWORD *)this + 2) = &Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::System::Internal::ISignInResult,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &Windows::System::Internal::SignInResult::`vftable'{for `Windows::System::Internal::ISignInResult'};
  *((_QWORD *)this + 4) = &Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 5) = &Windows::System::Internal::SignInResult::`vftable'{for `Windows::System::Internal::ISignInResult3'};
  *((_QWORD *)this + 6) = &Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 7) = &Windows::System::Internal::SignInResult::`vftable'{for `Windows::System::Internal::ISignInResult5'};
  *((_QWORD *)this + 8) = &Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 26));
  *((_QWORD *)this + 26) = 0;
  WindowsDeleteString(*((HSTRING *)this + 24));
  *((_QWORD *)this + 24) = 0;
  WindowsDeleteString(*((HSTRING *)this + 23));
  *((_QWORD *)this + 23) = 0;
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 18) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close();
  *((_QWORD *)this + 16) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close();
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUserAuthenticationCallback,Windows::System::Internal::ISignInResult,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUserAuthenticationCallback,Windows::System::Internal::ISignInResult,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800c02b0  mov     [rsp+arg_0], rbx
0x1800c02b5  push    rdi
0x1800c02b6  sub     rsp, 20h
0x1800c02ba  lea     rax, ??_7SignInResult@Internal@System@Windows@@6B@; const Windows::System::Internal::SignInResult::`vftable'
0x1800c02c1  mov     rbx, rcx
0x1800c02c4  mov     [rcx], rax
0x1800c02c7  lea     rax, ??_7SignInResult@Internal@System@Windows@@6BIUserAuthenticationCallback@@@; const Windows::System::Internal::SignInResult::`vftable'{for `IUserAuthenticationCallback'}
0x1800c02ce  mov     [rcx+8], rax
0x1800c02d2  lea     rax, ??_7SignInResult@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UISignInResult@Internal@System@Windows@@UISignInResult2@678@UISignInResult3@678@UISignInResult4@678@UISignInResult5@678@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::System::Internal::ISignInResult,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>'}
0x1800c02d9  mov     [rcx+10h], rax
0x1800c02dd  lea     rax, ??_7SignInResult@Internal@System@Windows@@6BISignInResult@123@@; const Windows::System::Internal::SignInResult::`vftable'{for `Windows::System::Internal::ISignInResult'}
0x1800c02e4  mov     [rcx+18h], rax
0x1800c02e8  lea     rax, ??_7SignInResult@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISignInResult2@Internal@System@Windows@@UISignInResult3@567@UISignInResult4@567@UISignInResult5@567@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>'}
0x1800c02ef  mov     [rcx+20h], rax
0x1800c02f3  lea     rax, ??_7SignInResult@Internal@System@Windows@@6BISignInResult3@123@@; const Windows::System::Internal::SignInResult::`vftable'{for `Windows::System::Internal::ISignInResult3'}
0x1800c02fa  mov     [rcx+28h], rax
0x1800c02fe  lea     rax, ??_7SignInResult@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISignInResult4@Internal@System@Windows@@UISignInResult5@567@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>'}
0x1800c0305  mov     [rcx+30h], rax
0x1800c0309  lea     rax, ??_7SignInResult@Internal@System@Windows@@6BISignInResult5@123@@; const Windows::System::Internal::SignInResult::`vftable'{for `Windows::System::Internal::ISignInResult5'}
0x1800c0310  mov     [rcx+38h], rax
0x1800c0314  lea     rax, ??_7SignInResult@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInResult::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800c031b  mov     [rcx+40h], rax
0x1800c031f  mov     rcx, [rcx+0D0h]; string
0x1800c0326  call    cs:__imp_WindowsDeleteString
0x1800c032c  xor     edi, edi
0x1800c032e  mov     [rbx+0D0h], rdi
0x1800c0335  mov     rcx, [rbx+0C0h]; string
0x1800c033c  call    cs:__imp_WindowsDeleteString
0x1800c0342  mov     [rbx+0C0h], rdi
0x1800c0349  mov     rcx, [rbx+0B8h]; string
0x1800c0350  call    cs:__imp_WindowsDeleteString
0x1800c0356  mov     [rbx+0B8h], rdi
0x1800c035d  mov     rcx, [rbx+0A8h]; string
0x1800c0364  call    cs:__imp_WindowsDeleteString
0x1800c036a  mov     [rbx+0A8h], rdi
0x1800c0371  mov     rcx, [rbx+0A0h]; string
0x1800c0378  call    cs:__imp_WindowsDeleteString
0x1800c037e  mov     [rbx+0A0h], rdi
0x1800c0385  lea     rcx, [rbx+90h]
0x1800c038c  lea     rdi, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800c0393  mov     [rcx], rdi
0x1800c0396  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x1800c039b  lea     rcx, [rbx+80h]
0x1800c03a2  mov     [rcx], rdi
0x1800c03a5  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x1800c03aa  mov     rcx, rbx
0x1800c03ad  mov     rbx, [rsp+28h+arg_0]
0x1800c03b2  add     rsp, 20h
0x1800c03b6  pop     rdi
0x1800c03b7  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIUserAuthenticationCallback@@UISignInResult@Internal@System@Windows@@UISignInResult2@678@UISignInResult3@678@UISignInResult4@678@UISignInResult5@678@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUserAuthenticationCallback,Windows::System::Internal::ISignInResult,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUserAuthenticationCallback,Windows::System::Internal::ISignInResult,Windows::System::Internal::ISignInResult2,Windows::System::Internal::ISignInResult3,Windows::System::Internal::ISignInResult4,Windows::System::Internal::ISignInResult5,Microsoft::WRL::FtmBase>(void)
```
