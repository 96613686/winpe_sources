# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJson(ushort const *)

- ea: `0x180017a08`
- end: `0x180017c4a`
- name: `?InitJson@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@CA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `578`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800169c0`
- `0x180017714`
- `0x180017c50`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180013374`
- `0x180013620`
- `0x180017a08`
- `0x180059010`

## string_xrefs

- `0x180017a57`: `Windows.Data.Json.JsonObject`
- `0x180017be4`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x180017bf9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x180017c0e`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x180017c23`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x180017c38`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
WCHAR *__fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJson(WCHAR *a1, const WCHAR *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, PVOID, WCHAR *); // rbx
  HSTRING_HEADER *v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, int *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, WCHAR *); // rbx
  int v15; // eax
  int v17; // [rsp+20h] [rbp-60h] BYREF
  __int64 v18; // [rsp+28h] [rbp-58h] BYREF
  int v19; // [rsp+30h] [rbp-50h]
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  const WCHAR *v21[2]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v21[1] = a1;
  v21[0] = a2;
  v19 = 0;
  v18 = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v23,
         (__int64)&v18);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
      (const char *)(unsigned int)v4,
      v17);
  *(_QWORD *)a1 = 0;
  v19 = 1;
  if ( !a2 )
    goto LABEL_9;
  v5 = v18;
  v6 = *(__int64 (__fastcall **)(__int64, PVOID, WCHAR *))(*(_QWORD *)v18 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v21);
  v8 = v6(v5, v7[1].Reserved.Reserved1, a1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
      (const char *)(unsigned int)v8,
      v17);
  v20 = 0;
  v9 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))a1,
         (__int64)&v20);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
      (const char *)(unsigned int)v9,
      v17);
  LOBYTE(v17) = 0;
  v10 = v20;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v20 + 64LL);
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"settings", 9u, 8u);
  v12 = v11(v10, v23, &v17);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
      (const char *)(unsigned int)v12,
      v17);
  if ( !(_BYTE)v17 )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  if ( !*(_QWORD *)a1 )
  {
LABEL_9:
    v13 = v18;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, WCHAR *))(*(_QWORD *)v18 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"{\"settings\":{}}", 0x10u, 0xFu);
    v15 = v14(v13, v23, a1);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
        (const char *)(unsigned int)v15,
        v17);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return a1;
}

```

## disassembly

```asm
0x180017a08  mov     [rsp-18h+arg_10], rbx
0x180017a0d  push    rbp
0x180017a0e  push    rsi
0x180017a0f  push    rdi
0x180017a10  mov     rbp, rsp
0x180017a13  sub     rsp, 80h
0x180017a1a  mov     rax, cs:__security_cookie
0x180017a21  xor     rax, rsp
0x180017a24  mov     [rbp+var_10], rax
0x180017a28  mov     rbx, rdx
0x180017a2b  mov     rsi, rcx
0x180017a2e  mov     [rbp+var_38], rcx
0x180017a32  mov     [rbp+var_40], rdx
0x180017a36  mov     [rbp+var_50], 0
0x180017a3d  mov     [rbp+var_58], 0
0x180017a45  mov     [rbp+var_18], 0
0x180017a4d  mov     r9d, 1Ch; unsigned int
0x180017a53  lea     r8d, [r9+1]; unsigned int
0x180017a57  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180017a5e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180017a62  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017a67  nop
0x180017a68  lea     rdx, [rbp+var_58]
0x180017a6c  mov     rcx, [rbp+var_18]
0x180017a70  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180017a75  mov     rcx, [rbp+18h]; this
0x180017a79  test    eax, eax
0x180017a7b  js      loc_180017BF6
0x180017a81  mov     qword ptr [rsi], 0
0x180017a88  mov     [rbp+var_50], 1
0x180017a8f  test    rbx, rbx
0x180017a92  jz      loc_180017B66
0x180017a98  mov     rdi, [rbp+var_58]
0x180017a9c  mov     rax, [rdi]
0x180017a9f  mov     rbx, [rax+30h]
0x180017aa3  mov     rcx, rsi
0x180017aa6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017aab  lea     rdx, [rbp+var_40]
0x180017aaf  lea     rcx, [rbp+hstringHeader]
0x180017ab3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017ab8  nop
0x180017ab9  mov     r8, rsi
0x180017abc  mov     rdx, [rax+18h]
0x180017ac0  mov     rcx, rdi
0x180017ac3  mov     rax, rbx
0x180017ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017acb  mov     rcx, [rbp+18h]; this
0x180017acf  test    eax, eax
0x180017ad1  js      loc_180017C0B
0x180017ad7  mov     [rbp+var_48], 0
0x180017adf  lea     rdx, [rbp+var_48]
0x180017ae3  mov     rcx, rsi
0x180017ae6  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180017aeb  mov     rcx, [rbp+18h]; this
0x180017aef  test    eax, eax
0x180017af1  js      loc_180017C20
0x180017af7  mov     byte ptr [rbp+var_60], 0
0x180017afb  mov     rdi, [rbp+var_48]
0x180017aff  mov     rax, [rdi]
0x180017b02  mov     rbx, [rax+40h]
0x180017b06  mov     [rbp+var_18], 0
0x180017b0e  mov     r9d, 8; unsigned int
0x180017b14  lea     r8d, [r9+1]; unsigned int
0x180017b18  lea     rdx, ?c_jsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@0QBGB; "settings"
0x180017b1f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180017b23  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017b28  nop
0x180017b29  lea     r8, [rbp+var_60]
0x180017b2d  mov     rdx, [rbp+var_18]
0x180017b31  mov     rcx, rdi
0x180017b34  mov     rax, rbx
0x180017b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b3c  mov     rcx, [rbp+18h]; this
0x180017b40  test    eax, eax
0x180017b42  js      loc_180017C35
0x180017b48  cmp     byte ptr [rbp+var_60], 0
0x180017b4c  jnz     short loc_180017B57
0x180017b4e  mov     rcx, rsi
0x180017b51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b56  nop
0x180017b57  lea     rcx, [rbp+var_48]
0x180017b5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b60  cmp     qword ptr [rsi], 0
0x180017b64  jnz     short loc_180017BB6
0x180017b66  mov     rdi, [rbp+var_58]
0x180017b6a  mov     rax, [rdi]
0x180017b6d  mov     rbx, [rax+30h]
0x180017b71  mov     rcx, rsi
0x180017b74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b79  mov     [rbp+var_18], 0
0x180017b81  mov     r9d, 0Fh; unsigned int
0x180017b87  lea     r8d, [r9+1]; unsigned int
0x180017b8b  lea     rdx, ?c_szPayloadEmpty@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@0QBGB; "{\"settings\":{}}"
0x180017b92  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180017b96  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017b9b  nop
0x180017b9c  mov     r8, rsi
0x180017b9f  mov     rdx, [rbp+var_18]
0x180017ba3  mov     rcx, rdi
0x180017ba6  mov     rax, rbx
0x180017ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bae  mov     rcx, [rbp+18h]; this
0x180017bb2  test    eax, eax
0x180017bb4  js      short loc_180017BE1
0x180017bb6  lea     rcx, [rbp+var_58]
0x180017bba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017bbf  mov     rax, rsi
0x180017bc2  mov     rcx, [rbp+var_10]
0x180017bc6  xor     rcx, rsp; StackCookie
0x180017bc9  call    __security_check_cookie
0x180017bce  mov     rbx, [rsp+80h+arg_10]
0x180017bd6  add     rsp, 80h
0x180017bdd  pop     rdi
0x180017bde  pop     rsi
0x180017bdf  pop     rbp
0x180017be0  retn
0x180017be1  mov     r9d, eax; char *
0x180017be4  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017beb  mov     edx, 0C2h; void *
0x180017bf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017bf6  mov     r9d, eax; char *
0x180017bf9  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017c00  mov     edx, 0A8h; void *
0x180017c05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017c0b  mov     r9d, eax; char *
0x180017c0e  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017c15  mov     edx, 0B0h; void *
0x180017c1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017c20  mov     r9d, eax; char *
0x180017c23  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017c2a  mov     edx, 0B4h; void *
0x180017c2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017c35  mov     r9d, eax; char *
0x180017c38  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180017c3f  mov     edx, 0B8h; void *
0x180017c44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
