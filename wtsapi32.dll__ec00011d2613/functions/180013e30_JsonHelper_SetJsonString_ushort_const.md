# JsonHelper::SetJsonString(ushort const *)

- ea: `0x180013e30`
- end: `0x180013f98`
- name: `?SetJsonString@JsonHelper@@UEAAJPEBG@Z`
- size: `360`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012230`
- `0x180012380`
- `0x180012640`
- `0x180013880`
- `0x180013e30`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## string_xrefs

- `0x180013ede`: `GetActivationFactory(JsonObject) failed!`
- `0x180013f3f`: `spJsonObjectStatics->Parse failed!`
- `0x180013e76`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall JsonHelper::SetJsonString(JsonHelper *this, const unsigned __int16 *a2)
{
  int v3; // ebx
  int ActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, _QWORD, char *); // rdi
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-78h] BYREF
  const unsigned __int16 *v12; // [rsp+38h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-68h] BYREF
  __int64 v14; // [rsp+58h] [rbp-50h]
  _QWORD v15[4]; // [rsp+60h] [rbp-48h] BYREF

  v12 = a2;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, &v12);
  v11 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v14,
         &v11);
  if ( v3 >= 0 )
  {
    v7 = v11;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v11 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((char *)this + 56);
    v3 = v8(v7, v15[3], (char *)this + 56);
    if ( v3 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v9, &WPP_GLOBAL_Control);
      v5 = 31;
      v6 = "spJsonObjectStatics->Parse failed!";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    v5 = 30;
    v6 = "GetActivationFactory(JsonObject) failed!";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v6,
      v3);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013e30  mov     r11, rsp
0x180013e33  mov     [r11+18h], rbx
0x180013e37  push    rbp
0x180013e38  push    rsi
0x180013e39  push    rdi
0x180013e3a  sub     rsp, 90h
0x180013e41  mov     rax, cs:__security_cookie
0x180013e48  xor     rax, rsp
0x180013e4b  mov     [rsp+0A8h+var_28], rax
0x180013e53  mov     rbp, rcx
0x180013e56  mov     [r11-70h], rdx
0x180013e5a  lea     rdx, [r11-70h]
0x180013e5e  lea     rcx, [r11-48h]
0x180013e62  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013e67  mov     r9d, 1Ch; unsigned int
0x180013e6d  mov     [rsp+0A8h+var_78], 0
0x180013e76  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180013e7d  mov     [rsp+0A8h+var_50], 0
0x180013e86  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x180013e8b  lea     r8d, [r9+1]; unsigned int
0x180013e8f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013e94  mov     rcx, [rsp+0A8h+var_50]
0x180013e99  lea     rdx, [rsp+0A8h+var_78]
0x180013e9e  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180013ea3  mov     ebx, eax
0x180013ea5  test    eax, eax
0x180013ea7  jns     short loc_180013EE7
0x180013ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eb0  lea     rdx, WPP_GLOBAL_Control
0x180013eb7  cmp     rcx, rdx
0x180013eba  jz      loc_180013F69
0x180013ec0  test    byte ptr [rcx+1Ch], 8
0x180013ec4  jz      loc_180013F69
0x180013eca  cmp     byte ptr [rcx+19h], 2
0x180013ece  jb      loc_180013F69
0x180013ed4  call    RdpX_GetActivityIdPrefix
0x180013ed9  mov     edx, 1Eh
0x180013ede  lea     rcx, aGetactivationf_0; "GetActivationFactory(JsonObject) failed"...
0x180013ee5  jmp     short loc_180013F46
0x180013ee7  mov     rsi, [rsp+0A8h+var_78]
0x180013eec  lea     rcx, [rbp+38h]
0x180013ef0  mov     rax, [rsi]
0x180013ef3  mov     rdi, [rax+30h]
0x180013ef7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180013efc  mov     rdx, [rsp+0A8h+var_30]
0x180013f01  lea     r8, [rbp+38h]
0x180013f05  mov     rcx, rsi
0x180013f08  mov     rax, rdi
0x180013f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f10  mov     ebx, eax
0x180013f12  test    eax, eax
0x180013f14  jns     short loc_180013F69
0x180013f16  mov     rax, cs:WPP_GLOBAL_Control
0x180013f1d  lea     rdx, WPP_GLOBAL_Control
0x180013f24  cmp     rax, rdx
0x180013f27  jz      short loc_180013F69
0x180013f29  test    byte ptr [rax+1Ch], 8
0x180013f2d  jz      short loc_180013F69
0x180013f2f  cmp     byte ptr [rax+19h], 2
0x180013f33  jb      short loc_180013F69
0x180013f35  call    RdpX_GetActivityIdPrefix
0x180013f3a  mov     edx, 1Fh
0x180013f3f  lea     rcx, aSpjsonobjectst; "spJsonObjectStatics->Parse failed!"
0x180013f46  mov     [rsp+0A8h+var_80], ebx
0x180013f4a  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013f51  mov     [rsp+0A8h+var_88], rcx
0x180013f56  mov     r9d, eax
0x180013f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f60  mov     rcx, [rcx+10h]
0x180013f64  call    WPP_SF_DsD
0x180013f69  lea     rcx, [rsp+0A8h+var_78]
0x180013f6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180013f73  mov     eax, ebx
0x180013f75  mov     rcx, [rsp+0A8h+var_28]
0x180013f7d  xor     rcx, rsp; StackCookie
0x180013f80  call    __security_check_cookie
0x180013f85  mov     rbx, [rsp+0A8h+arg_10]
0x180013f8d  add     rsp, 90h
0x180013f94  pop     rdi
0x180013f95  pop     rsi
0x180013f96  pop     rbp
0x180013f97  retn
```
