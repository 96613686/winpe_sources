# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitFinal(std::shared_ptr<IPayloadHandler>,bool,ushort const * const,bool)

- ea: `0x180017884`
- end: `0x180017a02`
- name: `?InitFinal@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@AEAAXV?$shared_ptr@VIPayloadHandler@@@std@@_NQEBG1@Z`
- size: `382`
- prototype: `void __fastcall(Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this, __int64, char, __int64, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800195e0`
- `0x180019884`

## callees

- `0x18000fe24`
- `0x180014b2c`
- `0x180017884`
- `0x180017c50`
- `0x180017dec`
- `0x180019e18`
- `0x180019ff0`
- `0x180027f80`
- `0x1800286b0`
- `0x180049c78`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800179d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800179d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017945`

## string_xrefs

- `0x1800179c4`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitFinal(
        Windows::Internal::Flighting::OneSettings::OneSettingsPayload *this,
        __int64 a2,
        char a3,
        __int64 a4,
        char a5)
{
  __int64 *v9; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  __int64 (*v12)(void); // rax
  HSTRING v13; // rbx
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v18; // rsi
  __int64 CnsFlights; // rdi
  int updated; // eax
  std::_Ref_count_base *v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-20h] BYREF
  std::_Ref_count_base *v23; // [rsp+28h] [rbp-18h]
  _BYTE v24[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v26; // [rsp+80h] [rbp+40h] BYREF

  v9 = (__int64 *)std::shared_ptr<ClientEndpoint>::shared_ptr<ClientEndpoint>(&v22, a2);
  v10 = *v9;
  *v9 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v10;
  v11 = v9[1];
  v9[1] = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v11;
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  *((_BYTE *)this + 97) = a3;
  if ( a3 )
  {
    if ( !*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) )
    {
      v13 = 0;
      goto LABEL_12;
    }
    v12 = *(__int64 (**)(void))(**((_QWORD **)this + 7) + 48LL);
    goto LABEL_10;
  }
  v14 = (__int64 *)*((_QWORD *)this + 7);
  v15 = *v14;
  if ( !a4 )
  {
    v12 = *(__int64 (**)(void))(v15 + 16);
LABEL_10:
    v16 = v12();
    goto LABEL_11;
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v15 + 24))(v14, a4);
LABEL_11:
  v13 = (HSTRING)v16;
LABEL_12:
  WindowsDeleteString(0);
  if ( v13 )
    StringRawBuffer = WindowsGetStringRawBuffer(v13, 0);
  else
    StringRawBuffer = 0;
  Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJsonSettings(this, StringRawBuffer);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
  {
    if ( a5 )
    {
      if ( ClientState::HasCnsFlights(*((ClientState **)this + 6)) )
      {
        v26 = 0;
        v18 = *((_QWORD *)this + 7);
        CnsFlights = ClientState::GetCnsFlights(*((_QWORD *)this + 6), v24);
        v22 = *((_QWORD *)this + 10);
        Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(&v22);
        updated = CnsPayloadUtilities::UpdateJsonFromCns(&v22, CnsFlights, v18, &v26);
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x223,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
            (const char *)(unsigned int)updated,
            v22);
      }
    }
  }
  WindowsDeleteString(v13);
  v21 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
}

```

## disassembly

```asm
0x180017884  mov     [rsp-28h+arg_18], rbx
0x180017889  mov     [rsp-28h+arg_8], rdx
0x18001788e  push    rbp
0x18001788f  push    rsi
0x180017890  push    rdi
0x180017891  push    r14
0x180017893  push    r15
0x180017895  mov     rbp, rsp
0x180017898  sub     rsp, 40h
0x18001789c  mov     rdi, r9
0x18001789f  mov     bl, r8b
0x1800178a2  mov     r15, rdx
0x1800178a5  mov     r14, rcx
0x1800178a8  lea     rcx, [rbp+var_20]
0x1800178ac  call    ??0?$shared_ptr@VClientEndpoint@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ClientEndpoint>::shared_ptr<ClientEndpoint>(std::shared_ptr<ClientEndpoint> const &)
0x1800178b1  mov     r10, [rax]
0x1800178b4  mov     r9, [r14+38h]
0x1800178b8  mov     [rax], r9
0x1800178bb  mov     [r14+38h], r10
0x1800178bf  mov     rdx, [rax+8]
0x1800178c3  mov     rcx, [r14+40h]
0x1800178c7  mov     [rax+8], rcx
0x1800178cb  mov     [r14+40h], rdx
0x1800178cf  mov     rcx, [rbp+var_18]; this
0x1800178d3  test    rcx, rcx
0x1800178d6  jz      short loc_1800178DD
0x1800178d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800178dd  mov     [r14+61h], bl
0x1800178e1  mov     [rbp+arg_0], 0
0x1800178e9  test    bl, bl
0x1800178eb  jz      short loc_180017909
0x1800178ed  mov     rax, [r14+30h]
0x1800178f1  cmp     qword ptr [rax+70h], 0
0x1800178f6  jz      short loc_180017905
0x1800178f8  mov     rcx, [r14+38h]
0x1800178fc  mov     rax, [rcx]
0x1800178ff  mov     rax, [rax+30h]
0x180017903  jmp     short loc_180017927
0x180017905  xor     ebx, ebx
0x180017907  jmp     short loc_18001792F
0x180017909  mov     rcx, [r14+38h]
0x18001790d  mov     rax, [rcx]
0x180017910  test    rdi, rdi
0x180017913  jz      short loc_180017923
0x180017915  mov     rdx, rdi
0x180017918  mov     rax, [rax+18h]
0x18001791c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017921  jmp     short loc_18001792C
0x180017923  mov     rax, [rax+10h]
0x180017927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001792c  mov     rbx, rax
0x18001792f  xor     ecx, ecx; string
0x180017931  call    cs:__imp_WindowsDeleteString
0x180017937  mov     [rbp+arg_0], rbx
0x18001793b  test    rbx, rbx
0x18001793e  jz      short loc_18001794D
0x180017940  xor     edx, edx; length
0x180017942  mov     rcx, rbx; string
0x180017945  call    cs:__imp_WindowsGetStringRawBuffer
0x18001794b  jmp     short loc_18001794F
0x18001794d  xor     eax, eax
0x18001794f  mov     rdx, rax; unsigned __int16 *
0x180017952  mov     rcx, r14; this
0x180017955  call    ?InitJsonSettings@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::Flighting::OneSettings::OneSettingsPayload::InitJsonSettings(ushort const *)
0x18001795a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl(void)'::`2'::impl
0x180017961  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(void)
0x180017966  test    al, al
0x180017968  jz      short loc_1800179D6
0x18001796a  cmp     [rbp+arg_20], 0
0x18001796e  jz      short loc_1800179D6
0x180017970  mov     rcx, [r14+30h]; this
0x180017974  call    ?HasCnsFlights@ClientState@@QEAA_NXZ; ClientState::HasCnsFlights(void)
0x180017979  test    al, al
0x18001797b  jz      short loc_1800179D6
0x18001797d  mov     [rbp+arg_10], 0
0x180017981  mov     rsi, [r14+38h]
0x180017985  lea     rdx, [rbp+var_10]
0x180017989  mov     rcx, [r14+30h]
0x18001798d  call    ?GetCnsFlights@ClientState@@QEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@XZ; ClientState::GetCnsFlights(void)
0x180017992  mov     rdi, rax
0x180017995  mov     rcx, [r14+50h]
0x180017999  mov     [rbp+var_20], rcx
0x18001799d  lea     rcx, [rbp+var_20]
0x1800179a1  call    ?InternalAddRef@?$ComPtr@VOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(void)
0x1800179a6  lea     r9, [rbp+arg_10]
0x1800179aa  mov     r8, rsi
0x1800179ad  mov     rdx, rdi
0x1800179b0  lea     rcx, [rbp+var_20]
0x1800179b4  call    ?UpdateJsonFromCns@CnsPayloadUtilities@@YAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@PEAVIPayloadHandler@@AEA_N@Z; CnsPayloadUtilities::UpdateJsonFromCns(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,std::map<std::wstring,std::shared_ptr<CnsFlightState>>,IPayloadHandler *,bool &)
0x1800179b9  mov     rcx, [rbp+28h]; this
0x1800179bd  test    eax, eax
0x1800179bf  jns     short loc_1800179D6
0x1800179c1  mov     r9d, eax; char *
0x1800179c4  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x1800179cb  mov     edx, 223h; void *
0x1800179d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800179d5  nop
0x1800179d6  mov     rcx, rbx; string
0x1800179d9  call    cs:__imp_WindowsDeleteString
0x1800179df  nop
0x1800179e0  mov     rcx, [r15+8]; this
0x1800179e4  test    rcx, rcx
0x1800179e7  jz      short loc_1800179EE
0x1800179e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800179ee  mov     rbx, [rsp+40h+arg_18]
0x1800179f6  add     rsp, 40h
0x1800179fa  pop     r15
0x1800179fc  pop     r14
0x1800179fe  pop     rdi
0x1800179ff  pop     rsi
0x180017a00  pop     rbp
0x180017a01  retn
```
