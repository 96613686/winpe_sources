# _lambda_da1a1a09eda2cd8259e2f9e0eaa5a077_::operator()

- ea: `0x18000ac90`
- end: `0x18000ae80`
- name: `_lambda_da1a1a09eda2cd8259e2f9e0eaa5a077_::operator()`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a7bc`

## callees

- `0x180001590`
- `0x180008828`
- `0x18000a3a4`
- `0x18000a4ec`
- `0x18000a634`
- `0x18000a7e0`
- `0x18000ac1c`
- `0x18000ac90`
- `0x18000b158`
- `0x18000ba50`
- `0x18000bbb0`
- `0x18000e010`

## string_xrefs

- `0x18000acc0`: `Windows.Internal.Security.SmartScreen.AppReputationService`
- `0x18000aded`: `Windows.Internal.Security.SmartScreen.UriReputationService`
- `0x18000ad70`: `Windows.Internal.Security.SmartScreen.EventLogger`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall lambda_da1a1a09eda2cd8259e2f9e0eaa5a077_::operator()(__int64 a1)
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
  _BYTE v18[8]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.SmartScreen.AppReputationService",
    0x3Bu,
    0x3Au);
  if ( Microsoft::WRL::Wrappers::operator==(*(HSTRING **)a1, (__int64)&hstringHeader) )
  {
    anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IAppReputationService__anonymous_namespace_::smartscreen_(v18);
    v2 = (_QWORD *)windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(
                     &v15,
                     *(_QWORD *)(a1 + 8),
                     v18);
    v3 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*v2)(
           *v2,
           &GUID_00000035_0000_0000_c000_000000000046,
           **(_QWORD **)(a1 + 16));
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x3D, v4, (const char *)(unsigned int)v3, v15);
    v5 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
  }
  else
  {
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Security.SmartScreen.EventLogger",
      0x32u,
      0x31u);
    if ( Microsoft::WRL::Wrappers::operator==(*(HSTRING **)a1, (__int64)&hstringHeader) )
    {
      v6 = (_QWORD *)anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IEventLoggerFactory__anonymous_namespace_::smartscreen_(v18);
      v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*v6)(
             *v6,
             &GUID_00000035_0000_0000_c000_000000000046,
             **(_QWORD **)(a1 + 16));
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
      if ( !Microsoft::WRL::Wrappers::operator==(*(HSTRING **)a1, (__int64)&hstringHeader) )
        wil::details::in1diag3::Throw_Hr(retaddr, v9, v10, (const char *)0x80004002LL, v15);
      v11 = (_QWORD *)anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen_(v18);
      v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))*v11)(
              *v11,
              &GUID_00000035_0000_0000_c000_000000000046,
              **(_QWORD **)(a1 + 16));
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x45, v13, (const char *)(unsigned int)v12, v15);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ac90  mov     [rsp-8+arg_8], rbx
0x18000ac95  push    rbp
0x18000ac96  mov     rbp, rsp
0x18000ac99  sub     rsp, 60h
0x18000ac9d  mov     rax, cs:__security_cookie
0x18000aca4  xor     rax, rsp
0x18000aca7  mov     [rbp+var_10], rax
0x18000acab  mov     rbx, rcx
0x18000acae  mov     [rbp+var_20], 0
0x18000acb6  mov     r9d, 3Ah ; ':'; unsigned int
0x18000acbc  lea     r8d, [r9+1]; unsigned int
0x18000acc0  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_AppReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.A"...
0x18000acc7  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000accb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000acd0  lea     rdx, [rbp+hstringHeader]
0x18000acd4  mov     rcx, [rbx]
0x18000acd7  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18000acdc  test    al, al
0x18000acde  jz      short loc_18000AD5E
0x18000ace0  lea     rcx, [rbp+var_18]
0x18000ace4  call    _anonymous_namespace___get_instance_Windows__Internal__Security__SmartScreen__IAppReputationService__anonymous_namespace___smartscreen_
0x18000ace9  nop
0x18000acea  lea     r8, [rbp+var_18]
0x18000acee  mov     rdx, [rbx+8]
0x18000acf2  lea     rcx, [rbp+var_40]
0x18000acf6  call    ??$make@Vapplication_reputation_static@com@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@rt@windows@@YA?AV?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@AEAVapi_guard@@AEAV?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@34@@Z; windows::rt::make<com::application_reputation_static,api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &>(api_guard &,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService> &)
0x18000acfb  nop
0x18000acfc  mov     rcx, [rbx+10h]
0x18000ad00  mov     r9, [rax]
0x18000ad03  mov     rax, [r9]
0x18000ad06  mov     r8, [rcx]
0x18000ad09  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000ad10  mov     rcx, r9
0x18000ad13  mov     rax, [rax]
0x18000ad16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1b  nop
0x18000ad1c  mov     rcx, [rbp+8]; this
0x18000ad20  test    eax, eax
0x18000ad22  jns     short loc_18000AD32
0x18000ad24  mov     r9d, eax; char *
0x18000ad27  mov     edx, 3Dh ; '='; void *
0x18000ad2c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ad32  mov     rcx, [rbp+var_40]
0x18000ad36  test    rcx, rcx
0x18000ad39  jz      short loc_18000AD50
0x18000ad3b  mov     [rbp+var_40], 0
0x18000ad43  mov     rax, [rcx]
0x18000ad46  mov     rax, [rax+10h]
0x18000ad4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad4f  nop
0x18000ad50  lea     rcx, [rbp+var_18]
0x18000ad54  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ad59  jmp     loc_18000AE56
0x18000ad5e  mov     [rbp+var_20], 0
0x18000ad66  mov     r9d, 31h ; '1'; unsigned int
0x18000ad6c  lea     r8d, [r9+1]; unsigned int
0x18000ad70  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_EventLogger@@3QBGB; "Windows.Internal.Security.SmartScreen.E"...
0x18000ad77  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000ad7b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000ad80  lea     rdx, [rbp+hstringHeader]
0x18000ad84  mov     rcx, [rbx]
0x18000ad87  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18000ad8c  test    al, al
0x18000ad8e  jz      short loc_18000ADDB
0x18000ad90  lea     rcx, [rbp+var_18]
0x18000ad94  call    _anonymous_namespace___get_instance_Windows__Internal__Security__SmartScreen__IEventLoggerFactory__anonymous_namespace___smartscreen_
0x18000ad99  nop
0x18000ad9a  mov     rcx, [rbx+10h]
0x18000ad9e  mov     r9, [rax]
0x18000ada1  mov     rax, [r9]
0x18000ada4  mov     r8, [rcx]
0x18000ada7  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000adae  mov     rcx, r9
0x18000adb1  mov     rax, [rax]
0x18000adb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb9  nop
0x18000adba  mov     rcx, [rbp+8]; this
0x18000adbe  test    eax, eax
0x18000adc0  jns     short loc_18000ADD0
0x18000adc2  mov     r9d, eax; char *
0x18000adc5  mov     edx, 41h ; 'A'; void *
0x18000adca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000add0  lea     rcx, [rbp+var_18]
0x18000add4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000add9  jmp     short loc_18000AE56
0x18000addb  mov     [rbp+var_20], 0
0x18000ade3  mov     r9d, 3Ah ; ':'; unsigned int
0x18000ade9  lea     r8d, [r9+1]; unsigned int
0x18000aded  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_UriReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.U"...
0x18000adf4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000adf8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000adfd  lea     rdx, [rbp+hstringHeader]
0x18000ae01  mov     rcx, [rbx]
0x18000ae04  call    ??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z; Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)
0x18000ae09  test    al, al
0x18000ae0b  jz      short loc_18000AE70
0x18000ae0d  lea     rcx, [rbp+var_18]
0x18000ae11  call    _anonymous_namespace___get_instance_Windows__Internal__Security__SmartScreen__IUriReputationServiceStatics__anonymous_namespace___smartscreen_
0x18000ae16  nop
0x18000ae17  mov     rcx, [rbx+10h]
0x18000ae1b  mov     r9, [rax]
0x18000ae1e  mov     rax, [r9]
0x18000ae21  mov     r8, [rcx]
0x18000ae24  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000ae2b  mov     rcx, r9
0x18000ae2e  mov     rax, [rax]
0x18000ae31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae36  nop
0x18000ae37  mov     rcx, [rbp+8]; this
0x18000ae3b  test    eax, eax
0x18000ae3d  jns     short loc_18000AE4D
0x18000ae3f  mov     r9d, eax; char *
0x18000ae42  mov     edx, 45h ; 'E'; void *
0x18000ae47  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ae4d  lea     rcx, [rbp+var_18]
0x18000ae51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ae56  xor     eax, eax
0x18000ae58  mov     rcx, [rbp+var_10]
0x18000ae5c  xor     rcx, rsp; StackCookie
0x18000ae5f  call    __security_check_cookie
0x18000ae64  mov     rbx, [rsp+60h+arg_8]
0x18000ae69  add     rsp, 60h
0x18000ae6d  pop     rbp
0x18000ae6e  retn
0x18000ae70  mov     rcx, [rbp+8]; this
0x18000ae74  mov     r9d, 80004002h; char *
0x18000ae7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
