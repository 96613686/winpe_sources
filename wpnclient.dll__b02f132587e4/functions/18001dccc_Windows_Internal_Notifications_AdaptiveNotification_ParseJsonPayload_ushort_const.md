# Windows::Internal::Notifications::AdaptiveNotification::ParseJsonPayload(ushort const *)

- ea: `0x18001dccc`
- end: `0x18001df17`
- name: `?ParseJsonPayload@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEBG@Z`
- size: `587`
- prototype: `void __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023ba4`

## callees

- `0x180005670`
- `0x180013740`
- `0x18001478c`
- `0x18001b848`
- `0x18001dccc`
- `0x18001df20`
- `0x18001e1a4`
- `0x18001e5a0`
- `0x18001e9a4`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de71`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001dd39`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001dd39`

## string_xrefs

- `0x18001dd0d`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Internal::Notifications::AdaptiveNotification::ParseJsonPayload(
        Windows::Internal::Notifications::AdaptiveNotification *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  int ActivationFactory; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, struct Windows::Data::Json::IJsonObject **); // rbx
  int v11; // eax
  Windows::Internal::Notifications::AdaptiveNotification *v12; // rcx
  Windows::Internal::Notifications::AdaptiveNotification *v13; // rcx
  Windows::Internal::Notifications::AdaptiveNotification *v14; // rcx
  Windows::Internal::Notifications::AdaptiveNotification *v15; // rcx
  int v16; // [rsp+20h] [rbp-60h]
  struct Windows::Data::Json::IJsonObject *v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v20 = a2;
  v19 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v3 = v22;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v19);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v16);
  v18 = 0;
  v5 = v19;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v20);
  v8 = v6(v5, *(_QWORD *)(v7 + 24), &v18);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v8,
      v16);
  v17 = 0;
  v9 = v18;
  v10 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonObject **))(*(_QWORD *)v18 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v11 = v10(v9, &v17);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v11,
      v16);
  Windows::Internal::Notifications::AdaptiveNotification::ValidatePayload(retaddr, v17);
  Windows::Internal::Notifications::AdaptiveNotification::ParseActivation((HSTRING *)this, v17);
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  Windows::Internal::Notifications::AdaptiveNotification::ParseTitle(
    v12,
    v17,
    L"title",
    (HSTRING *)this + 13,
    (HSTRING *)this + 14);
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  Windows::Internal::Notifications::AdaptiveNotification::ParseTitle(
    v13,
    v17,
    L"subtitle",
    (HSTRING *)this + 15,
    (HSTRING *)this + 16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
  Windows::Internal::Notifications::AdaptiveNotification::ParseImage(
    v14,
    v17,
    L"profile",
    (struct Windows::Internal::Notifications::IAdaptiveImage **)this + 17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  Windows::Internal::Notifications::AdaptiveNotification::ParseImage(
    v15,
    v17,
    L"card",
    (struct Windows::Internal::Notifications::IAdaptiveImage **)this + 18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
}

```

## disassembly

```asm
0x18001dccc  mov     [rsp-18h+arg_10], rbx
0x18001dcd1  push    rbp
0x18001dcd2  push    rsi
0x18001dcd3  push    rdi
0x18001dcd4  mov     rbp, rsp
0x18001dcd7  sub     rsp, 80h
0x18001dcde  mov     rax, cs:__security_cookie
0x18001dce5  xor     rax, rsp
0x18001dce8  mov     [rbp+var_10], rax
0x18001dcec  mov     rsi, rcx
0x18001dcef  mov     [rbp+var_38], rdx
0x18001dcf3  mov     [rbp+var_40], 0
0x18001dcfb  mov     [rbp+var_18], 0
0x18001dd03  mov     r9d, 1Bh; unsigned int
0x18001dd09  lea     r8d, [r9+1]; unsigned int
0x18001dd0d  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001dd14  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001dd18  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001dd1d  nop
0x18001dd1e  mov     rbx, [rbp+var_18]
0x18001dd22  lea     rcx, [rbp+var_40]
0x18001dd26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd2b  lea     r8, [rbp+var_40]
0x18001dd2f  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001dd36  mov     rcx, rbx
0x18001dd39  call    cs:__imp_RoGetActivationFactory
0x18001dd3f  mov     rcx, [rbp+18h]; this
0x18001dd43  test    eax, eax
0x18001dd45  jns     short loc_18001DD5C
0x18001dd47  mov     r9d, eax; char *
0x18001dd4a  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dd51  mov     edx, 2Bh ; '+'; void *
0x18001dd56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dd5c  mov     [rbp+var_48], 0
0x18001dd64  mov     rdi, [rbp+var_40]
0x18001dd68  mov     rax, [rdi]
0x18001dd6b  mov     rbx, [rax+30h]
0x18001dd6f  lea     rcx, [rbp+var_48]
0x18001dd73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd78  lea     rdx, [rbp+var_38]
0x18001dd7c  lea     rcx, [rbp+hstringHeader]
0x18001dd80  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001dd85  nop
0x18001dd86  lea     r8, [rbp+var_48]
0x18001dd8a  mov     rdx, [rax+18h]
0x18001dd8e  mov     rcx, rdi
0x18001dd91  mov     rax, rbx
0x18001dd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd99  mov     rcx, [rbp+18h]; this
0x18001dd9d  test    eax, eax
0x18001dd9f  jns     short loc_18001DDB6
0x18001dda1  mov     r9d, eax; char *
0x18001dda4  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ddab  mov     edx, 2Dh ; '-'; void *
0x18001ddb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ddb6  mov     [rbp+var_50], 0
0x18001ddbe  mov     rdi, [rbp+var_48]
0x18001ddc2  mov     rax, [rdi]
0x18001ddc5  mov     rbx, [rax+60h]
0x18001ddc9  lea     rcx, [rbp+var_50]
0x18001ddcd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ddd2  lea     rdx, [rbp+var_50]
0x18001ddd6  mov     rcx, rdi
0x18001ddd9  mov     rax, rbx
0x18001dddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dde1  mov     rcx, [rbp+18h]; this
0x18001dde5  test    eax, eax
0x18001dde7  jns     short loc_18001DDFE
0x18001dde9  mov     r9d, eax; char *
0x18001ddec  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ddf3  mov     edx, 2Fh ; '/'; void *
0x18001ddf8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ddfe  mov     rdx, [rbp+var_50]; struct Windows::Data::Json::IJsonObject *
0x18001de02  call    ?ValidatePayload@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@@Z; Windows::Internal::Notifications::AdaptiveNotification::ValidatePayload(Windows::Data::Json::IJsonObject *)
0x18001de07  mov     rdx, [rbp+var_50]; struct Windows::Data::Json::IJsonObject *
0x18001de0b  mov     rcx, rsi; this
0x18001de0e  call    ?ParseActivation@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@@Z; Windows::Internal::Notifications::AdaptiveNotification::ParseActivation(Windows::Data::Json::IJsonObject *)
0x18001de13  lea     rdi, [rsi+70h]
0x18001de17  mov     rcx, [rdi]; string
0x18001de1a  call    cs:__imp_WindowsDeleteString
0x18001de20  mov     qword ptr [rdi], 0
0x18001de27  lea     rbx, [rsi+68h]
0x18001de2b  mov     rcx, [rbx]; string
0x18001de2e  call    cs:__imp_WindowsDeleteString
0x18001de34  mov     qword ptr [rbx], 0
0x18001de3b  mov     qword ptr [rsp+80h+var_60], rdi; HSTRING *
0x18001de40  mov     r9, rbx; HSTRING *
0x18001de43  lea     r8, aTitle; "title"
0x18001de4a  mov     rdx, [rbp+var_50]; struct Windows::Data::Json::IJsonObject *
0x18001de4e  call    ?ParseTitle@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@PEBGPEAPEAUHSTRING__@@2@Z; Windows::Internal::Notifications::AdaptiveNotification::ParseTitle(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *,HSTRING__ * *)
0x18001de53  lea     rdi, [rsi+80h]
0x18001de5a  mov     rcx, [rdi]; string
0x18001de5d  call    cs:__imp_WindowsDeleteString
0x18001de63  mov     qword ptr [rdi], 0
0x18001de6a  lea     rbx, [rsi+78h]
0x18001de6e  mov     rcx, [rbx]; string
0x18001de71  call    cs:__imp_WindowsDeleteString
0x18001de77  mov     qword ptr [rbx], 0
0x18001de7e  mov     qword ptr [rsp+80h+var_60], rdi; HSTRING *
0x18001de83  mov     r9, rbx; HSTRING *
0x18001de86  lea     r8, aSubtitle; "subtitle"
0x18001de8d  mov     rdx, [rbp+var_50]; struct Windows::Data::Json::IJsonObject *
0x18001de91  call    ?ParseTitle@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@PEBGPEAPEAUHSTRING__@@2@Z; Windows::Internal::Notifications::AdaptiveNotification::ParseTitle(Windows::Data::Json::IJsonObject *,ushort const *,HSTRING__ * *,HSTRING__ * *)
0x18001de96  lea     rbx, [rsi+88h]
0x18001de9d  mov     rcx, rbx
0x18001dea0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dea5  mov     r9, rbx; struct Windows::Internal::Notifications::IAdaptiveImage **
0x18001dea8  lea     r8, aProfile; "profile"
0x18001deaf  mov     rdx, [rbp+var_50]; struct Windows::Data::Json::IJsonObject *
0x18001deb3  call    ?ParseImage@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@PEBGPEAPEAUIAdaptiveImage@234@@Z; Windows::Internal::Notifications::AdaptiveNotification::ParseImage(Windows::Data::Json::IJsonObject *,ushort const *,Windows::Internal::Notifications::IAdaptiveImage * *)
0x18001deb8  lea     rbx, [rsi+90h]
0x18001debf  mov     rcx, rbx
0x18001dec2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dec7  mov     r9, rbx; struct Windows::Internal::Notifications::IAdaptiveImage **
0x18001deca  lea     r8, aCard; "card"
0x18001ded1  mov     rdx, [rbp+var_50]; struct Windows::Data::Json::IJsonObject *
0x18001ded5  call    ?ParseImage@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@PEBGPEAPEAUIAdaptiveImage@234@@Z; Windows::Internal::Notifications::AdaptiveNotification::ParseImage(Windows::Data::Json::IJsonObject *,ushort const *,Windows::Internal::Notifications::IAdaptiveImage * *)
0x18001deda  nop
0x18001dedb  lea     rcx, [rbp+var_50]
0x18001dedf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dee4  nop
0x18001dee5  lea     rcx, [rbp+var_48]
0x18001dee9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001deee  nop
0x18001deef  lea     rcx, [rbp+var_40]
0x18001def3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001def8  mov     rcx, [rbp+var_10]
0x18001defc  xor     rcx, rsp; StackCookie
0x18001deff  call    __security_check_cookie
0x18001df04  mov     rbx, [rsp+80h+arg_10]
0x18001df0c  add     rsp, 80h
0x18001df13  pop     rdi
0x18001df14  pop     rsi
0x18001df15  pop     rbp
0x18001df16  retn
```
