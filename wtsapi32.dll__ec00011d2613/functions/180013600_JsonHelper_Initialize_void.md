# JsonHelper::Initialize(void)

- ea: `0x180013600`
- end: `0x180013878`
- name: `?Initialize@JsonHelper@@UEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012290`
- `0x180012380`
- `0x180012640`
- `0x180013600`
- `0x180013880`
- `0x180014aac`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180013623`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180013623`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800137f8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800137f8`

## string_xrefs

- `0x1800137b0`: `GetActivationFactory(JsonObject) failed!`
- `0x180013738`: `ActivateInstance: JsonObject`
- `0x18001382d`: `GetActivationFactory: JsonValue`
- `0x1800136dc`: `Windows.Data.Json.JsonObject`
- `0x180013756`: `Windows.Data.Json.JsonObject`
- `0x1800137cb`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
__int64 __fastcall JsonHelper::Initialize(JsonHelper *this)
{
  int ActivationFactory; // ebx
  __int64 v3; // rdx
  int ActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h]

  ActivationFactory = RoInitialize(0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetImpl'::`2'::impl) )
  {
    if ( ActivationFactory == -2147417850 )
      goto LABEL_15;
    if ( ActivationFactory < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3);
        v5 = 17;
LABEL_8:
        v6 = "Windows::Foundation::Initialize failed!";
LABEL_30:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          ActivityIdPrefix,
          (__int64)v6,
          ActivationFactory);
        return (unsigned int)ActivationFactory;
      }
      return (unsigned int)ActivationFactory;
    }
LABEL_14:
    *((_BYTE *)this + 64) = 1;
LABEL_15:
    v13 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                          v13,
                          (char *)this + 40);
    if ( ActivationFactory >= 0 )
    {
      v13 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      ActivationFactory = ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
                            v13,
                            (char *)this + 48);
      if ( ActivationFactory >= 0 )
      {
        v13 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        v9 = v13;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((char *)this + 56);
        ActivationFactory = RoGetActivationFactory(v9, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, (char *)this + 56);
        if ( ActivationFactory < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v10);
          v5 = 21;
          v6 = "GetActivationFactory: JsonValue";
          goto LABEL_30;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8);
        v5 = 20;
        v6 = "GetActivationFactory(JsonObject) failed!";
        goto LABEL_30;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v7);
      v5 = 19;
      v6 = "ActivateInstance: JsonObject";
      goto LABEL_30;
    }
    return (unsigned int)ActivationFactory;
  }
  if ( ActivationFactory >= 0 )
    goto LABEL_14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3);
    v5 = 18;
    goto LABEL_8;
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180013600  mov     [rsp+arg_8], rbx
0x180013605  mov     [rsp+arg_10], rsi
0x18001360a  push    rdi
0x18001360b  sub     rsp, 60h
0x18001360f  mov     rax, cs:__security_cookie
0x180013616  xor     rax, rsp
0x180013619  mov     [rsp+68h+var_18], rax
0x18001361e  mov     rsi, rcx
0x180013621  xor     ecx, ecx
0x180013623  call    cs:__imp_RoInitialize
0x180013629  mov     ebx, eax
0x18001362b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA> `wil::Feature<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetImpl(void)'::`2'::impl
0x180013632  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(void)
0x180013637  test    al, al
0x180013639  jz      short loc_18001368C
0x18001363b  cmp     ebx, 80010106h
0x180013641  jz      loc_1800136CB
0x180013647  test    ebx, ebx
0x180013649  jns     short loc_1800136C7
0x18001364b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013652  lea     rax, WPP_GLOBAL_Control
0x180013659  cmp     rcx, rax
0x18001365c  jz      loc_180013857
0x180013662  test    byte ptr [rcx+1Ch], 8
0x180013666  jz      loc_180013857
0x18001366c  cmp     byte ptr [rcx+19h], 2
0x180013670  jb      loc_180013857
0x180013676  call    RdpX_GetActivityIdPrefix
0x18001367b  mov     edx, 11h
0x180013680  lea     rcx, aWindowsFoundat; "Windows::Foundation::Initialize failed!"
0x180013687  jmp     loc_180013834
0x18001368c  test    ebx, ebx
0x18001368e  jns     short loc_1800136C7
0x180013690  mov     rcx, cs:WPP_GLOBAL_Control
0x180013697  lea     rax, WPP_GLOBAL_Control
0x18001369e  cmp     rcx, rax
0x1800136a1  jz      loc_180013857
0x1800136a7  test    byte ptr [rcx+1Ch], 8
0x1800136ab  jz      loc_180013857
0x1800136b1  cmp     byte ptr [rcx+19h], 2
0x1800136b5  jb      loc_180013857
0x1800136bb  call    RdpX_GetActivityIdPrefix
0x1800136c0  mov     edx, 12h
0x1800136c5  jmp     short loc_180013680
0x1800136c7  mov     byte ptr [rsi+40h], 1
0x1800136cb  mov     edi, 1Ch
0x1800136d0  mov     [rsp+68h+var_20], 0
0x1800136d9  mov     r9d, edi; unsigned int
0x1800136dc  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800136e3  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1800136e8  lea     r8d, [rdi+1]; unsigned int
0x1800136ec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800136f1  mov     rcx, [rsp+68h+var_20]
0x1800136f6  lea     rdx, [rsi+28h]
0x1800136fa  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800136ff  mov     ebx, eax
0x180013701  test    eax, eax
0x180013703  jns     short loc_180013744
0x180013705  mov     rcx, cs:WPP_GLOBAL_Control
0x18001370c  lea     rax, WPP_GLOBAL_Control
0x180013713  cmp     rcx, rax
0x180013716  jz      loc_180013857
0x18001371c  test    byte ptr [rcx+1Ch], 8
0x180013720  jz      loc_180013857
0x180013726  cmp     byte ptr [rcx+19h], 2
0x18001372a  jb      loc_180013857
0x180013730  call    RdpX_GetActivityIdPrefix
0x180013735  lea     edx, [rdi-9]
0x180013738  lea     rcx, aActivateinstan; "ActivateInstance: JsonObject"
0x18001373f  jmp     loc_180013834
0x180013744  mov     r9d, edi; unsigned int
0x180013747  mov     [rsp+68h+var_20], 0
0x180013750  mov     r8d, 1Dh; unsigned int
0x180013756  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001375d  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180013762  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013767  mov     rcx, [rsp+68h+var_20]
0x18001376c  lea     rdx, [rsi+30h]
0x180013770  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180013775  mov     ebx, eax
0x180013777  test    eax, eax
0x180013779  jns     short loc_1800137B9
0x18001377b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013782  lea     rax, WPP_GLOBAL_Control
0x180013789  cmp     rcx, rax
0x18001378c  jz      loc_180013857
0x180013792  test    byte ptr [rcx+1Ch], 8
0x180013796  jz      loc_180013857
0x18001379c  cmp     byte ptr [rcx+19h], 2
0x1800137a0  jb      loc_180013857
0x1800137a6  call    RdpX_GetActivityIdPrefix
0x1800137ab  mov     edx, 14h
0x1800137b0  lea     rcx, aGetactivationf_0; "GetActivationFactory(JsonObject) failed"...
0x1800137b7  jmp     short loc_180013834
0x1800137b9  mov     r9d, 1Bh; unsigned int
0x1800137bf  mov     [rsp+68h+var_20], 0
0x1800137c8  mov     r8d, edi; unsigned int
0x1800137cb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800137d2  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1800137d7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800137dc  mov     rdi, [rsp+68h+var_20]
0x1800137e1  lea     rcx, [rsi+38h]
0x1800137e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800137ea  lea     r8, [rsi+38h]
0x1800137ee  mov     rcx, rdi
0x1800137f1  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800137f8  call    cs:__imp_RoGetActivationFactory
0x1800137fe  mov     ebx, eax
0x180013800  test    eax, eax
0x180013802  jns     short loc_180013857
0x180013804  mov     rcx, cs:WPP_GLOBAL_Control
0x18001380b  lea     rax, WPP_GLOBAL_Control
0x180013812  cmp     rcx, rax
0x180013815  jz      short loc_180013857
0x180013817  test    byte ptr [rcx+1Ch], 8
0x18001381b  jz      short loc_180013857
0x18001381d  cmp     byte ptr [rcx+19h], 2
0x180013821  jb      short loc_180013857
0x180013823  call    RdpX_GetActivityIdPrefix
0x180013828  mov     edx, 15h
0x18001382d  lea     rcx, aGetactivationf_1; "GetActivationFactory: JsonValue"
0x180013834  mov     [rsp+68h+var_40], ebx
0x180013838  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18001383f  mov     [rsp+68h+var_48], rcx
0x180013844  mov     r9d, eax
0x180013847  mov     rcx, cs:WPP_GLOBAL_Control
0x18001384e  mov     rcx, [rcx+10h]
0x180013852  call    WPP_SF_DsD
0x180013857  mov     eax, ebx
0x180013859  mov     rcx, [rsp+68h+var_18]
0x18001385e  xor     rcx, rsp; StackCookie
0x180013861  call    __security_check_cookie
0x180013866  lea     r11, [rsp+68h+var_8]
0x18001386b  mov     rbx, [r11+18h]
0x18001386f  mov     rsi, [r11+20h]
0x180013873  mov     rsp, r11
0x180013876  pop     rdi
0x180013877  retn
```
