# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitDefaultJsonSettings(ushort const *)

- ea: `0x180017714`
- end: `0x18001787e`
- name: `?InitDefaultJsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@QEAAXPEBG@Z`
- size: `362`
- prototype: `void(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800195e0`
- `0x1800197a8`

## callees

- `0x180003110`
- `0x180005f50`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180014e9c`
- `0x180014ee0`
- `0x1800156e4`
- `0x180016a14`
- `0x180017714`
- `0x180017a08`
- `0x180017dec`
- `0x180019fb0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017767`

## string_xrefs

- `0x18001786c`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitDefaultJsonSettings(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        const unsigned __int16 *a2)
{
  HSTRING StringFromFile; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 JsonSettingsFromJson; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // [rsp+20h] [rbp-50h] BYREF
  __int64 v10; // [rsp+28h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v13; // [rsp+40h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *((_BYTE *)this + 96) = 1;
  StringFromFile = FileContentPurveyor::CreateStringFromFile(a2, (int)a2);
  WindowsDeleteString(0);
  v13 = StringFromFile;
  if ( StringFromFile )
    StringRawBuffer = WindowsGetStringRawBuffer(StringFromFile, 0);
  else
    StringRawBuffer = 0;
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJson(&v11, StringRawBuffer);
  v9 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
  {
    v10 = v11;
    Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(&v10);
    JsonSettingsFromJson = Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetJsonSettingsFromJson(
                             v12,
                             &v10);
    Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::operator=(&v9, JsonSettingsFromJson);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
  }
  else
  {
    v6 = v11;
    v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    v15 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"settings", 9u, 8u);
    v8 = v7(v6, v15, &v9);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
        (const char *)(unsigned int)v8,
        v9);
  }
  Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::operator=((char *)this + 88, &v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  WindowsDeleteString(StringFromFile);
}

```

## disassembly

```asm
0x180017714  mov     [rsp-18h+arg_10], rbx
0x180017719  mov     [rsp-18h+arg_18], rsi
0x18001771e  push    rbp
0x18001771f  push    rdi
0x180017720  push    r14
0x180017722  mov     rbp, rsp
0x180017725  sub     rsp, 70h
0x180017729  mov     rax, cs:__security_cookie
0x180017730  xor     rax, rsp
0x180017733  mov     [rbp+var_8], rax
0x180017737  mov     r14, rcx
0x18001773a  mov     byte ptr [rcx+60h], 1
0x18001773e  mov     [rbp+var_30], 0
0x180017746  mov     rcx, rdx; lpSrc
0x180017749  call    ?CreateStringFromFile@FileContentPurveyor@@SAPEAUHSTRING__@@PEBGI@Z; FileContentPurveyor::CreateStringFromFile(ushort const *,uint)
0x18001774e  mov     rsi, rax
0x180017751  xor     ecx, ecx; string
0x180017753  call    cs:__imp_WindowsDeleteString
0x180017759  mov     [rbp+var_30], rsi
0x18001775d  test    rsi, rsi
0x180017760  jz      short loc_18001776F
0x180017762  xor     edx, edx; length
0x180017764  mov     rcx, rsi; string
0x180017767  call    cs:__imp_WindowsGetStringRawBuffer
0x18001776d  jmp     short loc_180017771
0x18001776f  xor     eax, eax
0x180017771  mov     rdx, rax
0x180017774  lea     rcx, [rbp+var_40]
0x180017778  call    ?InitJson@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@CA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJson(ushort const *)
0x18001777d  nop
0x18001777e  mov     [rbp+var_50], 0
0x180017786  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl(void)'::`2'::impl
0x18001778d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(wil::ReportingKind)
0x180017792  test    al, al
0x180017794  jz      short loc_1800177CB
0x180017796  mov     rax, [rbp+var_40]
0x18001779a  mov     [rbp+var_48], rax
0x18001779e  lea     rcx, [rbp+var_48]
0x1800177a2  call    ?InternalAddRef@?$ComPtr@VOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(void)
0x1800177a7  lea     rdx, [rbp+var_48]
0x1800177ab  lea     rcx, [rbp+var_38]
0x1800177af  call    ?GetJsonSettingsFromJson@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@CA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V678@@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::GetJsonSettingsFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x1800177b4  mov     rdx, rax
0x1800177b7  lea     rcx, [rbp+var_50]
0x1800177bb  call    ??4?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::operator=(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &&)
0x1800177c0  lea     rcx, [rbp+var_38]
0x1800177c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800177c9  jmp     short loc_18001781D
0x1800177cb  mov     rdi, [rbp+var_40]
0x1800177cf  mov     rax, [rdi]
0x1800177d2  mov     rbx, [rax+40h]
0x1800177d6  lea     rcx, [rbp+var_50]
0x1800177da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800177df  mov     [rbp+var_10], 0
0x1800177e7  mov     r9d, 8; unsigned int
0x1800177ed  lea     r8d, [r9+1]; unsigned int
0x1800177f1  lea     rdx, ?c_jsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@0QBGB; "settings"
0x1800177f8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800177fc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017801  nop
0x180017802  lea     r8, [rbp+var_50]
0x180017806  mov     rdx, [rbp+var_10]
0x18001780a  mov     rcx, rdi
0x18001780d  mov     rax, rbx
0x180017810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017815  mov     rcx, [rbp+18h]; this
0x180017819  test    eax, eax
0x18001781b  js      short loc_180017869
0x18001781d  lea     rcx, [r14+58h]
0x180017821  lea     rdx, [rbp+var_50]
0x180017825  call    ??4?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::operator=(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)
0x18001782a  nop
0x18001782b  lea     rcx, [rbp+var_50]
0x18001782f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017834  nop
0x180017835  lea     rcx, [rbp+var_40]
0x180017839  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001783e  nop
0x18001783f  mov     rcx, rsi; string
0x180017842  call    cs:__imp_WindowsDeleteString
0x180017848  mov     rcx, [rbp+var_8]
0x18001784c  xor     rcx, rsp; StackCookie
0x18001784f  call    __security_check_cookie
0x180017854  lea     r11, [rsp+70h+var_s0]
0x180017859  mov     rbx, [r11+30h]
0x18001785d  mov     rsi, [r11+38h]
0x180017861  mov     rsp, r11
0x180017864  pop     r14
0x180017866  pop     rdi
0x180017867  pop     rbp
0x180017868  retn
0x180017869  mov     r9d, eax; char *
0x18001786c  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017873  mov     edx, 9Dh; void *
0x180017878  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
