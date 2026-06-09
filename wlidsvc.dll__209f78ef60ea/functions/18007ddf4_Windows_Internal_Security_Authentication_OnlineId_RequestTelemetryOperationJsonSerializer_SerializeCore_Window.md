# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation const &,Windows::Data::Json::IJsonValue * *,unsigned __int64)

- ea: `0x18007ddf4`
- end: `0x18007e20a`
- name: `?SerializeCore@RequestTelemetryOperationJsonSerializer@OnlineId@Authentication@Security@Internal@Windows@@CAJAEBVRequestTelemetryOperation@23456@PEAPEAUIJsonValue@Json@Data@6@_K@Z`
- size: `1046`
- prototype: `__int64 __fastcall(const struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *, struct Windows::Data::Json::IJsonValue **, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f14e8`
- `0x18010b694`

## callees

- `0x18002d36c`
- `0x18007ddf4`
- `0x18007e27c`
- `0x18007e2dc`
- `0x1800a3b60`
- `0x18010b754`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007de64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007df24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007de64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007df24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007de85`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007df45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007e015`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007de85`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007df45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007e015`

## string_xrefs

- `0x18007de32`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007de98`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007ded9`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007df58`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007dfb3`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007e028`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007e0a0`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007e135`: `onecoreuap\ds\ext\common\lib\cloudidentitymatscommon\requesttelemetryoperationjsonserializer.cpp`
- `0x18007df1d`: `Windows.Data.Json.JsonValue`
- `0x18007de5d`: `Windows.Data.Json.JsonObject`
- `0x18007dff6`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(
        const struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *a1,
        struct Windows::Data::Json::IJsonValue **a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // eax
  struct Windows::Data::Json::IJsonObjectStatics *v12; // rcx
  struct Windows::Data::Json::IJsonObjectStatics *v13; // rcx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // eax
  struct Windows::Data::Json::IJsonValueStatics *v18; // rcx
  struct Windows::Data::Json::IJsonObjectStatics *v19; // rcx
  struct Windows::Data::Json::IJsonValueStatics *v20; // rcx
  int v21; // eax
  struct Windows::Data::Json::IJsonArrayStatics *v22; // rcx
  struct Windows::Data::Json::IJsonValueStatics *v23; // rcx
  struct Windows::Data::Json::IJsonObjectStatics *v24; // rcx
  struct Windows::Data::Json::IJsonArrayStatics *v25; // rcx
  struct Windows::Data::Json::IJsonValueStatics *v26; // rcx
  struct Windows::Data::Json::IJsonObjectStatics *v27; // rdx
  int v28; // eax
  struct Windows::Data::Json::IJsonArrayStatics *v29; // rcx
  struct Windows::Data::Json::IJsonValueStatics *v30; // rcx
  struct Windows::Data::Json::IJsonObjectStatics *v31; // rcx
  struct Windows::Data::Json::IJsonArrayStatics *v32; // rcx
  struct Windows::Data::Json::IJsonValueStatics *v33; // rcx
  struct Windows::Data::Json::IJsonObjectStatics *v34; // rcx
  int v35; // [rsp+20h] [rbp-50h]
  int v36; // [rsp+20h] [rbp-50h]
  struct Windows::Data::Json::IJsonObjectStatics *v37; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::Data::Json::IJsonValueStatics *v38; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Data::Json::IJsonArrayStatics *v39; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( !a2 )
  {
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)0x80004003LL,
      v35);
    return v6;
  }
  v37 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v37);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v35);
    v12 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v6;
  }
  if ( !v37 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)0x8007000ELL,
      v35);
LABEL_12:
    v13 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 2147942414LL;
  }
  v38 = 0;
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
    __debugbreak();
  }
  v17 = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v38);
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)(unsigned int)v17,
      v35);
    v18 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v6;
  }
  if ( !v38 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)0x8007000ELL,
      v35);
    v20 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_12;
  }
  v39 = 0;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  v21 = RoGetActivationFactory(string, &GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba, &v39);
  v6 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)(unsigned int)v21,
      v35);
    v22 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonArrayStatics *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v6;
  }
  if ( !v39 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)0x8007000ELL,
      v35);
    v25 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonArrayStatics *))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return 2147942414LL;
  }
  v28 = Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(
          a1,
          a2,
          v37,
          v38,
          v39,
          a3);
  v6 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\lib\\cloudidentitymatscommon\\requesttelemetryoperationjsonserializer.cpp",
      (const char *)(unsigned int)v28,
      v36);
    v29 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonArrayStatics *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return v6;
  }
  v32 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonArrayStatics *))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObjectStatics *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x18007ddf4  mov     [rsp-28h+arg_18], rbx
0x18007ddf9  push    rbp
0x18007ddfa  push    rsi
0x18007ddfb  push    rdi
0x18007ddfc  push    r14
0x18007ddfe  push    r15
0x18007de00  mov     rbp, rsp
0x18007de03  sub     rsp, 70h
0x18007de07  mov     rax, cs:__security_cookie
0x18007de0e  xor     rax, rsp
0x18007de11  mov     [rbp+var_8], rax
0x18007de15  mov     r14, r8
0x18007de18  mov     rdi, rdx
0x18007de1b  mov     rsi, rcx
0x18007de1e  xor     r15d, r15d
0x18007de21  test    rdx, rdx
0x18007de24  jnz     short loc_18007DE48
0x18007de26  mov     rcx, [rbp+28h]; this
0x18007de2a  mov     ebx, 80004003h
0x18007de2f  mov     r9d, ebx; char *
0x18007de32  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007de39  lea     edx, [rdi+62h]; void *
0x18007de3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007de41  mov     eax, ebx
0x18007de43  jmp     loc_18007E1EA
0x18007de48  mov     [rbp+var_40], r15
0x18007de4c  mov     [rbp+string], r15
0x18007de50  lea     r9, [rbp+string]; string
0x18007de54  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007de58  mov     edx, 1Ch; length
0x18007de5d  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007de64  call    cs:__imp_WindowsCreateStringReference
0x18007de6a  test    eax, eax
0x18007de6c  jns     short loc_18007DE76
0x18007de6e  mov     ecx, eax; this
0x18007de70  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007de75  int     3; Trap to Debugger
0x18007de76  lea     r8, [rbp+var_40]
0x18007de7a  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18007de81  mov     rcx, [rbp+string]
0x18007de85  call    cs:__imp_RoGetActivationFactory
0x18007de8b  mov     ebx, eax
0x18007de8d  test    eax, eax
0x18007de8f  jns     short loc_18007DEC9
0x18007de91  mov     rcx, [rbp+28h]; this
0x18007de95  mov     r9d, eax; char *
0x18007de98  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007de9f  mov     edx, 67h ; 'g'; void *
0x18007dea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dea9  nop
0x18007deaa  mov     rcx, [rbp+var_40]
0x18007deae  test    rcx, rcx
0x18007deb1  jz      short loc_18007DEC4
0x18007deb3  mov     [rbp+var_40], r15
0x18007deb7  mov     rax, [rcx]
0x18007deba  mov     rax, [rax+10h]
0x18007debe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dec3  nop
0x18007dec4  jmp     loc_18007DE41
0x18007dec9  cmp     [rbp+var_40], r15
0x18007decd  jnz     short loc_18007DF08
0x18007decf  mov     rcx, [rbp+28h]; this
0x18007ded3  mov     r9d, 8007000Eh; char *
0x18007ded9  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007dee0  mov     edx, 68h ; 'h'; void *
0x18007dee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007deea  nop
0x18007deeb  mov     rcx, [rbp+var_40]
0x18007deef  test    rcx, rcx
0x18007def2  jz      loc_18007E101
0x18007def8  mov     [rbp+var_40], r15
0x18007defc  mov     rax, [rcx]
0x18007deff  mov     rax, [rax+10h]
0x18007df03  jmp     loc_18007E0FB
0x18007df08  mov     [rbp+var_38], r15
0x18007df0c  mov     [rbp+string], r15
0x18007df10  lea     r9, [rbp+string]; string
0x18007df14  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007df18  mov     edx, 1Bh; length
0x18007df1d  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18007df24  call    cs:__imp_WindowsCreateStringReference
0x18007df2a  test    eax, eax
0x18007df2c  jns     short loc_18007DF36
0x18007df2e  mov     ecx, eax; this
0x18007df30  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007df35  int     3; Trap to Debugger
0x18007df36  lea     r8, [rbp+var_38]
0x18007df3a  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18007df41  mov     rcx, [rbp+string]
0x18007df45  call    cs:__imp_RoGetActivationFactory
0x18007df4b  mov     ebx, eax
0x18007df4d  test    eax, eax
0x18007df4f  jns     short loc_18007DFA3
0x18007df51  mov     rcx, [rbp+28h]; this
0x18007df55  mov     r9d, eax; char *
0x18007df58  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007df5f  mov     edx, 6Dh ; 'm'; void *
0x18007df64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007df69  nop
0x18007df6a  mov     rcx, [rbp+var_38]
0x18007df6e  test    rcx, rcx
0x18007df71  jz      short loc_18007DF84
0x18007df73  mov     [rbp+var_38], r15
0x18007df77  mov     rax, [rcx]
0x18007df7a  mov     rax, [rax+10h]
0x18007df7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df83  nop
0x18007df84  mov     rcx, [rbp+var_40]
0x18007df88  test    rcx, rcx
0x18007df8b  jz      short loc_18007DF9E
0x18007df8d  mov     [rbp+var_40], r15
0x18007df91  mov     rax, [rcx]
0x18007df94  mov     rax, [rax+10h]
0x18007df98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df9d  nop
0x18007df9e  jmp     loc_18007DE41
0x18007dfa3  cmp     [rbp+var_38], r15
0x18007dfa7  jnz     short loc_18007DFE4
0x18007dfa9  mov     rcx, [rbp+28h]; this
0x18007dfad  mov     r9d, 8007000Eh; char *
0x18007dfb3  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007dfba  mov     edx, 6Eh ; 'n'; void *
0x18007dfbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dfc4  nop
0x18007dfc5  mov     rcx, [rbp+var_38]
0x18007dfc9  test    rcx, rcx
0x18007dfcc  jz      short loc_18007DFDF
0x18007dfce  mov     [rbp+var_38], r15
0x18007dfd2  mov     rax, [rcx]
0x18007dfd5  mov     rax, [rax+10h]
0x18007dfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dfde  nop
0x18007dfdf  jmp     loc_18007DEEB
0x18007dfe4  mov     [rbp+var_30], r15
0x18007dfe8  mov     [rbp+string], r15
0x18007dfec  mov     r9d, 1Bh; unsigned int
0x18007dff2  lea     r8d, [r9+1]; unsigned int
0x18007dff6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18007dffd  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18007e001  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007e006  lea     r8, [rbp+var_30]
0x18007e00a  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x18007e011  mov     rcx, [rbp+string]
0x18007e015  call    cs:__imp_RoGetActivationFactory
0x18007e01b  mov     ebx, eax
0x18007e01d  test    eax, eax
0x18007e01f  jns     short loc_18007E08D
0x18007e021  mov     rcx, [rbp+28h]; this
0x18007e025  mov     r9d, eax; char *
0x18007e028  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007e02f  mov     edx, 73h ; 's'; void *
0x18007e034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e039  nop
0x18007e03a  mov     rcx, [rbp+var_30]
0x18007e03e  test    rcx, rcx
0x18007e041  jz      short loc_18007E054
0x18007e043  mov     [rbp+var_30], r15
0x18007e047  mov     rax, [rcx]
0x18007e04a  mov     rax, [rax+10h]
0x18007e04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e053  nop
0x18007e054  mov     rcx, [rbp+var_38]
0x18007e058  test    rcx, rcx
0x18007e05b  jz      short loc_18007E06E
0x18007e05d  mov     [rbp+var_38], r15
0x18007e061  mov     rax, [rcx]
0x18007e064  mov     rax, [rax+10h]
0x18007e068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e06d  nop
0x18007e06e  mov     rcx, [rbp+var_40]
0x18007e072  test    rcx, rcx
0x18007e075  jz      short loc_18007E088
0x18007e077  mov     [rbp+var_40], r15
0x18007e07b  mov     rax, [rcx]
0x18007e07e  mov     rax, [rax+10h]
0x18007e082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e087  nop
0x18007e088  jmp     loc_18007DE41
0x18007e08d  mov     rax, [rbp+var_30]
0x18007e091  test    rax, rax
0x18007e094  jnz     short loc_18007E10B
0x18007e096  mov     rcx, [rbp+28h]; this
0x18007e09a  mov     r9d, 8007000Eh; char *
0x18007e0a0  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007e0a7  lea     edx, [rax+74h]; void *
0x18007e0aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e0af  nop
0x18007e0b0  mov     rcx, [rbp+var_30]
0x18007e0b4  test    rcx, rcx
0x18007e0b7  jz      short loc_18007E0CA
0x18007e0b9  mov     [rbp+var_30], r15
0x18007e0bd  mov     rax, [rcx]
0x18007e0c0  mov     rax, [rax+10h]
0x18007e0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e0c9  nop
0x18007e0ca  mov     rcx, [rbp+var_38]
0x18007e0ce  test    rcx, rcx
0x18007e0d1  jz      short loc_18007E0E4
0x18007e0d3  mov     [rbp+var_38], r15
0x18007e0d7  mov     rax, [rcx]
0x18007e0da  mov     rax, [rax+10h]
0x18007e0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e0e3  nop
0x18007e0e4  mov     rdx, [rbp+var_40]
0x18007e0e8  test    rdx, rdx
0x18007e0eb  jz      short loc_18007E101
0x18007e0ed  mov     [rbp+var_40], r15
0x18007e0f1  mov     rcx, [rdx]
0x18007e0f4  mov     rax, [rcx+10h]
0x18007e0f8  mov     rcx, rdx
0x18007e0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e100  nop
0x18007e101  mov     eax, 8007000Eh
0x18007e106  jmp     loc_18007E1EA
0x18007e10b  mov     [rsp+70h+var_48], r14; unsigned __int64
0x18007e110  mov     [rsp+70h+var_50], rax; int
0x18007e115  mov     r9, [rbp+var_38]; struct Windows::Data::Json::IJsonValueStatics *
0x18007e119  mov     r8, [rbp+var_40]; struct Windows::Data::Json::IJsonObjectStatics *
0x18007e11d  mov     rdx, rdi; struct Windows::Data::Json::IJsonValue **
0x18007e120  mov     rcx, rsi; struct Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *
0x18007e123  call    ?SerializeCore@RequestTelemetryOperationJsonSerializer@OnlineId@Authentication@Security@Internal@Windows@@CAJAEBVRequestTelemetryOperation@23456@PEAPEAUIJsonValue@Json@Data@6@PEAUIJsonObjectStatics@9Data@6@PEAUIJsonValueStatics@9Data@6@PEAUIJsonArrayStatics@9Data@6@_K@Z; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperationJsonSerializer::SerializeCore(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation const &,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonObjectStatics *,Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonArrayStatics *,unsigned __int64)
0x18007e128  mov     ebx, eax
0x18007e12a  test    eax, eax
0x18007e12c  jns     short loc_18007E19A
0x18007e12e  mov     rcx, [rbp+28h]; this
0x18007e132  mov     r9d, eax; char *
0x18007e135  lea     r8, aOnecoreuapDsEx_32; "onecoreuap\\ds\\ext\\common\\lib\\cloud"...
0x18007e13c  mov     edx, 76h ; 'v'; void *
0x18007e141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e146  nop
0x18007e147  mov     rcx, [rbp+var_30]
0x18007e14b  test    rcx, rcx
0x18007e14e  jz      short loc_18007E161
0x18007e150  mov     [rbp+var_30], r15
0x18007e154  mov     rax, [rcx]
0x18007e157  mov     rax, [rax+10h]
0x18007e15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e160  nop
0x18007e161  mov     rcx, [rbp+var_38]
0x18007e165  test    rcx, rcx
0x18007e168  jz      short loc_18007E17B
0x18007e16a  mov     [rbp+var_38], r15
0x18007e16e  mov     rax, [rcx]
0x18007e171  mov     rax, [rax+10h]
0x18007e175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e17a  nop
0x18007e17b  mov     rcx, [rbp+var_40]
0x18007e17f  test    rcx, rcx
0x18007e182  jz      short loc_18007E195
0x18007e184  mov     [rbp+var_40], r15
0x18007e188  mov     rax, [rcx]
0x18007e18b  mov     rax, [rax+10h]
0x18007e18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e194  nop
0x18007e195  jmp     loc_18007DE41
0x18007e19a  mov     rcx, [rbp+var_30]
0x18007e19e  test    rcx, rcx
0x18007e1a1  jz      short loc_18007E1B4
0x18007e1a3  mov     [rbp+var_30], r15
0x18007e1a7  mov     rax, [rcx]
0x18007e1aa  mov     rax, [rax+10h]
0x18007e1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e1b3  nop
0x18007e1b4  mov     rcx, [rbp+var_38]
0x18007e1b8  test    rcx, rcx
0x18007e1bb  jz      short loc_18007E1CE
0x18007e1bd  mov     [rbp+var_38], r15
0x18007e1c1  mov     rax, [rcx]
0x18007e1c4  mov     rax, [rax+10h]
0x18007e1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e1cd  nop
0x18007e1ce  mov     rcx, [rbp+var_40]
0x18007e1d2  test    rcx, rcx
0x18007e1d5  jz      short loc_18007E1E8
0x18007e1d7  mov     [rbp+var_40], r15
0x18007e1db  mov     rax, [rcx]
0x18007e1de  mov     rax, [rax+10h]
0x18007e1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e1e7  nop
0x18007e1e8  xor     eax, eax
0x18007e1ea  mov     rcx, [rbp+var_8]
0x18007e1ee  xor     rcx, rsp; StackCookie
0x18007e1f1  call    __security_check_cookie
0x18007e1f6  mov     rbx, [rsp+70h+arg_18]
0x18007e1fe  add     rsp, 70h
0x18007e202  pop     r15
0x18007e204  pop     r14
0x18007e206  pop     rdi
0x18007e207  pop     rsi
0x18007e208  pop     rbp
0x18007e209  retn
```
