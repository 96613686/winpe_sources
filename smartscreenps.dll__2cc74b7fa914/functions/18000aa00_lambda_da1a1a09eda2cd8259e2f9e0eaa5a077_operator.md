# _lambda_da1a1a09eda2cd8259e2f9e0eaa5a077_::operator()

- ea: `0x18000aa00`
- end: `0x18000abef`
- name: `_lambda_da1a1a09eda2cd8259e2f9e0eaa5a077_::operator()`
- size: `495`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a548`

## callees

- `0x180001590`
- `0x18000871c`
- `0x18000a160`
- `0x18000a298`
- `0x18000a3d0`
- `0x18000a56c`
- `0x18000a99c`
- `0x18000aa00`
- `0x18000aebc`
- `0x18000b784`
- `0x18000b8e0`
- `0x18000e010`

## string_xrefs

- `0x18000aa30`: `Windows.Internal.Security.SmartScreen.AppReputationService`
- `0x18000ab5d`: `Windows.Internal.Security.SmartScreen.UriReputationService`
- `0x18000aae0`: `Windows.Internal.Security.SmartScreen.EventLogger`

## pseudocode

```c
__int64 __fastcall lambda_da1a1a09eda2cd8259e2f9e0eaa5a077_::operator()(_QWORD *a1)
{
  _QWORD *v2; // rax
  int v3; // eax
  unsigned int v4; // r8d
  __int64 v5; // rcx
  _QWORD *v6; // rax
  int v7; // eax
  unsigned int v8; // r8d
  void *v9; // rdx
  unsigned int v10; // r8d
  _QWORD *v11; // rax
  int v12; // eax
  unsigned int v13; // r8d
  __int64 v15; // [rsp+20h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h]
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.SmartScreen.AppReputationService",
    0x3Bu,
    0x3Au);
  if ( (unsigned __int8)Microsoft::WRL::Wrappers::operator==(*a1, &hstringHeader) )
  {
    anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_(&v18);
    v2 = (_QWORD *)windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(
                     &v15,
                     a1[1],
                     &v18);
    v3 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*v2)(
           *v2,
           &GUID_00000035_0000_0000_c000_000000000046,
           *(_QWORD *)a1[2]);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x3D, v4, (const char *)(unsigned int)v3, v15);
    v5 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  }
  else
  {
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Security.SmartScreen.EventLogger",
      0x32u,
      0x31u);
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::operator==(*a1, &hstringHeader) )
    {
      v6 = anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_(&v18);
      v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*v6)(
             *v6,
             &GUID_00000035_0000_0000_c000_000000000046,
             *(_QWORD *)a1[2]);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x41, v8, (const char *)(unsigned int)v7, v15);
    }
    else
    {
      v17 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Security.SmartScreen.UriReputationService",
        0x3Bu,
        0x3Au);
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::operator==(*a1, &hstringHeader) )
        wil::details::in1diag3::Throw_Hr(retaddr, v9, v10, (const char *)0x80004002LL, v15);
      v11 = anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_(&v18);
      v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*v11)(
              *v11,
              &GUID_00000035_0000_0000_c000_000000000046,
              *(_QWORD *)a1[2]);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x45, v13, (const char *)(unsigned int)v12, v15);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000aa00  mov     [rsp-8+arg_8], rbx
0x18000aa05  push    rbp
0x18000aa06  mov     rbp, rsp
0x18000aa09  sub     rsp, 60h
0x18000aa0d  mov     rax, cs:__security_cookie
0x18000aa14  xor     rax, rsp
0x18000aa17  mov     [rbp+var_10], rax
0x18000aa1b  mov     rbx, rcx
0x18000aa1e  mov     [rbp+var_20], 0
0x18000aa26  mov     r9d, 3Ah ; ':'; unsigned int
0x18000aa2c  lea     r8d, [r9+1]; unsigned int
0x18000aa30  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_AppReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.A"...
0x18000aa37  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000aa3b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000aa40  lea     rdx, [rbp+hstringHeader]
0x18000aa44  mov     rcx, [rbx]
0x18000aa47  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18000aa4c  test    al, al
0x18000aa4e  jz      short loc_18000AACE
0x18000aa50  lea     rcx, [rbp+var_18]
0x18000aa54  call    _anonymous_namespace___get_instance_Windows__Internal__Security__SmartScreen__IAppReputationService__anonymous_namespace___smartscreen_
0x18000aa59  nop
0x18000aa5a  lea     r8, [rbp+var_18]
0x18000aa5e  mov     rdx, [rbx+8]
0x18000aa62  lea     rcx, [rbp+var_40]
0x18000aa66  call    ??$make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@rt@windows@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@34@@Z; windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)
0x18000aa6b  nop
0x18000aa6c  mov     rcx, [rbx+10h]
0x18000aa70  mov     r9, [rax]
0x18000aa73  mov     rax, [r9]
0x18000aa76  mov     r8, [rcx]
0x18000aa79  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000aa80  mov     rcx, r9
0x18000aa83  mov     rax, [rax]
0x18000aa86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa8b  nop
0x18000aa8c  mov     rcx, [rbp+8]; this
0x18000aa90  test    eax, eax
0x18000aa92  jns     short loc_18000AAA2
0x18000aa94  mov     r9d, eax; char *
0x18000aa97  mov     edx, 3Dh ; '='; void *
0x18000aa9c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000aaa2  mov     rcx, [rbp+var_40]
0x18000aaa6  test    rcx, rcx
0x18000aaa9  jz      short loc_18000AAC0
0x18000aaab  mov     [rbp+var_40], 0
0x18000aab3  mov     rax, [rcx]
0x18000aab6  mov     rax, [rax+10h]
0x18000aaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aabf  nop
0x18000aac0  lea     rcx, [rbp+var_18]
0x18000aac4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000aac9  jmp     loc_18000ABC6
0x18000aace  mov     [rbp+var_20], 0
0x18000aad6  mov     r9d, 31h ; '1'; unsigned int
0x18000aadc  lea     r8d, [r9+1]; unsigned int
0x18000aae0  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_EventLogger@@3QBGB; "Windows.Internal.Security.SmartScreen.E"...
0x18000aae7  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000aaeb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000aaf0  lea     rdx, [rbp+hstringHeader]
0x18000aaf4  mov     rcx, [rbx]
0x18000aaf7  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18000aafc  test    al, al
0x18000aafe  jz      short loc_18000AB4B
0x18000ab00  lea     rcx, [rbp+var_18]
0x18000ab04  call    _anonymous_namespace___get_instance_Windows__Internal__Security__SmartScreen__IEventLoggerFactory__anonymous_namespace___smartscreen_
0x18000ab09  nop
0x18000ab0a  mov     rcx, [rbx+10h]
0x18000ab0e  mov     r9, [rax]
0x18000ab11  mov     rax, [r9]
0x18000ab14  mov     r8, [rcx]
0x18000ab17  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000ab1e  mov     rcx, r9
0x18000ab21  mov     rax, [rax]
0x18000ab24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab29  nop
0x18000ab2a  mov     rcx, [rbp+8]; this
0x18000ab2e  test    eax, eax
0x18000ab30  jns     short loc_18000AB40
0x18000ab32  mov     r9d, eax; char *
0x18000ab35  mov     edx, 41h ; 'A'; void *
0x18000ab3a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ab40  lea     rcx, [rbp+var_18]
0x18000ab44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ab49  jmp     short loc_18000ABC6
0x18000ab4b  mov     [rbp+var_20], 0
0x18000ab53  mov     r9d, 3Ah ; ':'; unsigned int
0x18000ab59  lea     r8d, [r9+1]; unsigned int
0x18000ab5d  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_UriReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.U"...
0x18000ab64  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000ab68  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000ab6d  lea     rdx, [rbp+hstringHeader]
0x18000ab71  mov     rcx, [rbx]
0x18000ab74  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18000ab79  test    al, al
0x18000ab7b  jz      short loc_18000ABDF
0x18000ab7d  lea     rcx, [rbp+var_18]
0x18000ab81  call    _anonymous_namespace___get_instance_Windows__Internal__Security__SmartScreen__IUriReputationServiceStatics__anonymous_namespace___smartscreen_
0x18000ab86  nop
0x18000ab87  mov     rcx, [rbx+10h]
0x18000ab8b  mov     r9, [rax]
0x18000ab8e  mov     rax, [r9]
0x18000ab91  mov     r8, [rcx]
0x18000ab94  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000ab9b  mov     rcx, r9
0x18000ab9e  mov     rax, [rax]
0x18000aba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aba6  nop
0x18000aba7  mov     rcx, [rbp+8]; this
0x18000abab  test    eax, eax
0x18000abad  jns     short loc_18000ABBD
0x18000abaf  mov     r9d, eax; char *
0x18000abb2  mov     edx, 45h ; 'E'; void *
0x18000abb7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000abbd  lea     rcx, [rbp+var_18]
0x18000abc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000abc6  xor     eax, eax
0x18000abc8  mov     rcx, [rbp+var_10]
0x18000abcc  xor     rcx, rsp; StackCookie
0x18000abcf  call    __security_check_cookie
0x18000abd4  mov     rbx, [rsp+60h+arg_8]
0x18000abd9  add     rsp, 60h
0x18000abdd  pop     rbp
0x18000abde  retn
0x18000abdf  mov     rcx, [rbp+8]; this
0x18000abe3  mov     r9d, 80004002h; char *
0x18000abe9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
