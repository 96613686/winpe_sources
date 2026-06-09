# JsonHelper::ParseArray(ushort const *,IValuesArray * *)

- ea: `0x180013990`
- end: `0x180013bd1`
- name: `?ParseArray@JsonHelper@@UEAAJPEBGPEAPEAVIValuesArray@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, struct IValuesArray **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007a64`
- `0x180011210`
- `0x180012230`
- `0x1800123bc`
- `0x180012640`
- `0x180013880`
- `0x180013990`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013a1b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013a1b`

## string_xrefs

- `0x180013aed`: `spJsonArrayStatics->Parse failed!`
- `0x180013a5c`: `GetActivationFactory(JsonArray) failed!`
- `0x1800139d4`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
__int64 __fastcall JsonHelper::ParseArray(JsonHelper *this, const unsigned __int16 *a2, struct IValuesArray **a3)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  int ActivationFactory; // ebx
  int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, struct Windows::Data::Json::IJsonArray **); // rbx
  __int64 v12; // rdx
  ValuesArray *v13; // rax
  __int64 v14; // rdx
  struct IValuesArray *v15; // rdi
  int ActivityIdPrefix; // eax
  const unsigned __int16 *v18; // [rsp+30h] [rbp-19h] BYREF
  __int64 v19; // [rsp+38h] [rbp-11h] BYREF
  struct Windows::Data::Json::IJsonArray *v20; // [rsp+40h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-1h] BYREF
  __int64 v22; // [rsp+60h] [rbp+17h]
  _BYTE v23[24]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+80h] [rbp+37h]

  v18 = a2;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, &v18);
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  v4 = v22;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v19);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba, &v19);
  if ( ActivationFactory >= 0 )
  {
    v10 = v19;
    v11 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Data::Json::IJsonArray **))(*(_QWORD *)v19 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v20);
    ActivationFactory = v11(v10, v24, &v20);
    if ( ActivationFactory >= 0 )
    {
      v13 = (ValuesArray *)operator new(0x40u);
      if ( v13 && (v15 = ValuesArray::ValuesArray(v13, v20)) != 0 )
      {
        TCntPtr<ValuesArray>::SafeRelease(&v18);
        (*(void (__fastcall **)(struct IValuesArray *))(*(_QWORD *)v15 + 8LL))(v15);
        v18 = 0;
        *a3 = v15;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v14);
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            ActivityIdPrefix,
            (__int64)"ValuesArray");
        }
        ActivationFactory = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12);
      v8 = 49;
      v9 = "spJsonArrayStatics->Parse failed!";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5);
    v8 = 48;
    v9 = "GetActivationFactory(JsonArray) failed!";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v7,
      (__int64)v9,
      ActivationFactory);
  }
  TCntPtr<ValuesArray>::SafeRelease(&v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v20);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180013990  mov     [rsp-8+arg_0], rbx
0x180013995  push    rbp
0x180013996  push    rsi
0x180013997  push    rdi
0x180013998  lea     rbp, [rsp-47h]
0x18001399d  sub     rsp, 90h
0x1800139a4  mov     rax, cs:__security_cookie
0x1800139ab  xor     rax, rsp
0x1800139ae  mov     [rbp+57h+var_18], rax
0x1800139b2  mov     [rbp+57h+var_70], rdx
0x1800139b6  lea     rcx, [rbp+57h+var_38]
0x1800139ba  lea     rdx, [rbp+57h+var_70]
0x1800139be  mov     rsi, r8
0x1800139c1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800139c6  mov     r9d, 1Bh; unsigned int
0x1800139cc  mov     [rbp+57h+var_60], 0
0x1800139d4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800139db  mov     [rbp+57h+var_68], 0
0x1800139e3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800139e7  mov     [rbp+57h+var_70], 0
0x1800139ef  mov     [rbp+57h+var_40], 0
0x1800139f7  lea     r8d, [r9+1]; unsigned int
0x1800139fb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013a00  mov     rbx, [rbp+57h+var_40]
0x180013a04  lea     rcx, [rbp+57h+var_68]
0x180013a08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180013a0d  lea     r8, [rbp+57h+var_68]
0x180013a11  mov     rcx, rbx
0x180013a14  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x180013a1b  call    cs:__imp_RoGetActivationFactory
0x180013a21  mov     ebx, eax
0x180013a23  test    eax, eax
0x180013a25  jns     short loc_180013A8B
0x180013a27  mov     rax, cs:WPP_GLOBAL_Control
0x180013a2e  lea     rcx, WPP_GLOBAL_Control
0x180013a35  cmp     rax, rcx
0x180013a38  jz      loc_180013B95
0x180013a3e  test    byte ptr [rax+1Ch], 8
0x180013a42  jz      loc_180013B95
0x180013a48  cmp     byte ptr [rax+19h], 2
0x180013a4c  jb      loc_180013B95
0x180013a52  call    RdpX_GetActivityIdPrefix
0x180013a57  mov     edx, 30h ; '0'
0x180013a5c  lea     rcx, aGetactivationf; "GetActivationFactory(JsonArray) failed!"
0x180013a63  mov     [rsp+0A0h+var_78], ebx
0x180013a67  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013a6e  mov     [rsp+0A0h+var_80], rcx
0x180013a73  mov     r9d, eax
0x180013a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a7d  mov     rcx, [rcx+10h]
0x180013a81  call    WPP_SF_DsD
0x180013a86  jmp     loc_180013B95
0x180013a8b  mov     rdi, [rbp+57h+var_68]
0x180013a8f  lea     rcx, [rbp+57h+var_60]
0x180013a93  mov     rax, [rdi]
0x180013a96  mov     rbx, [rax+30h]
0x180013a9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180013a9f  mov     rdx, [rbp+57h+var_20]
0x180013aa3  lea     r8, [rbp+57h+var_60]
0x180013aa7  mov     rcx, rdi
0x180013aaa  mov     rax, rbx
0x180013aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab2  mov     ebx, eax
0x180013ab4  test    eax, eax
0x180013ab6  jns     short loc_180013AF9
0x180013ab8  mov     rax, cs:WPP_GLOBAL_Control
0x180013abf  lea     rcx, WPP_GLOBAL_Control
0x180013ac6  cmp     rax, rcx
0x180013ac9  jz      loc_180013B95
0x180013acf  test    byte ptr [rax+1Ch], 8
0x180013ad3  jz      loc_180013B95
0x180013ad9  cmp     byte ptr [rax+19h], 2
0x180013add  jb      loc_180013B95
0x180013ae3  call    RdpX_GetActivityIdPrefix
0x180013ae8  mov     edx, 31h ; '1'
0x180013aed  lea     rcx, aSpjsonarraysta; "spJsonArrayStatics->Parse failed!"
0x180013af4  jmp     loc_180013A63
0x180013af9  mov     ecx, 40h ; '@'; Size
0x180013afe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013b03  test    rax, rax
0x180013b06  jz      short loc_180013B41
0x180013b08  mov     rdx, [rbp+57h+var_60]; struct Windows::Data::Json::IJsonArray *
0x180013b0c  mov     rcx, rax; this
0x180013b0f  call    ??0ValuesArray@@QEAA@PEAUIJsonArray@Json@Data@Windows@@@Z; ValuesArray::ValuesArray(Windows::Data::Json::IJsonArray *)
0x180013b14  mov     rdi, rax
0x180013b17  test    rax, rax
0x180013b1a  jz      short loc_180013B41
0x180013b1c  lea     rcx, [rbp+57h+var_70]
0x180013b20  call    ?SafeRelease@?$TCntPtr@VValuesArray@@@@AEAAXXZ; TCntPtr<ValuesArray>::SafeRelease(void)
0x180013b25  mov     rcx, [rdi]
0x180013b28  mov     rax, [rcx+8]
0x180013b2c  mov     rcx, rdi
0x180013b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b34  mov     [rbp+57h+var_70], 0
0x180013b3c  mov     [rsi], rdi
0x180013b3f  jmp     short loc_180013B95
0x180013b41  mov     rax, cs:WPP_GLOBAL_Control
0x180013b48  lea     rcx, WPP_GLOBAL_Control
0x180013b4f  cmp     rax, rcx
0x180013b52  jz      short loc_180013B90
0x180013b54  test    byte ptr [rax+1Ch], 8
0x180013b58  jz      short loc_180013B90
0x180013b5a  cmp     byte ptr [rax+19h], 2
0x180013b5e  jb      short loc_180013B90
0x180013b60  call    RdpX_GetActivityIdPrefix
0x180013b65  lea     rcx, aValuesarray; "ValuesArray"
0x180013b6c  mov     edx, 32h ; '2'
0x180013b71  mov     [rsp+0A0h+var_80], rcx
0x180013b76  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b84  mov     r9d, eax
0x180013b87  mov     rcx, [rcx+10h]
0x180013b8b  call    WPP_SF_Ds
0x180013b90  mov     ebx, 8007000Eh
0x180013b95  lea     rcx, [rbp+57h+var_70]
0x180013b99  call    ?SafeRelease@?$TCntPtr@VValuesArray@@@@AEAAXXZ; TCntPtr<ValuesArray>::SafeRelease(void)
0x180013b9e  lea     rcx, [rbp+57h+var_68]
0x180013ba2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180013ba7  lea     rcx, [rbp+57h+var_60]
0x180013bab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180013bb0  mov     eax, ebx
0x180013bb2  mov     rcx, [rbp+57h+var_18]
0x180013bb6  xor     rcx, rsp; StackCookie
0x180013bb9  call    __security_check_cookie
0x180013bbe  mov     rbx, [rsp+0A0h+arg_0]
0x180013bc6  add     rsp, 90h
0x180013bcd  pop     rdi
0x180013bce  pop     rsi
0x180013bcf  pop     rbp
0x180013bd0  retn
```
