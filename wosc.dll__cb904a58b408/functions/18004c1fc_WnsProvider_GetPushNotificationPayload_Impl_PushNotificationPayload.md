# WnsProvider::GetPushNotificationPayload_Impl(PushNotificationPayload &)

- ea: `0x18004c1fc`
- end: `0x18004c40a`
- name: `?GetPushNotificationPayload_Impl@WnsProvider@@AEAA_NAEAUPushNotificationPayload@@@Z`
- size: `526`
- prototype: `char __fastcall(WnsProvider *this, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x18004c1f0`
- `0x18004c4e4`

## callees

- `0x180003110`
- `0x1800101fc`
- `0x180015a4c`
- `0x180019e18`
- `0x180019ff0`
- `0x180049d40`
- `0x18004a79c`
- `0x18004b050`
- `0x18004c1fc`
- `0x18004d7a0`
- `0x18004dd14`
- `0x18004eda4`
- `0x180054660`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c369`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004c318`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004c318`
- `ntdll!RtlPublishWnfStateData` at `0x18004c29a`
- `ntdll!RtlPublishWnfStateData` at `0x18004c29a`

## pseudocode

```c
char __fastcall WnsProvider::GetPushNotificationPayload_Impl(WnsProvider *this, struct _FILETIME *a2)
{
  void *v3; // r9
  int v4; // ebx
  int v5; // eax
  int v6; // ebx
  HSTRING StringFromMultiByte; // rbx
  char IsEnabled; // al
  char v10; // dl
  int v11; // [rsp+20h] [rbp-E0h]
  _WNF_STATE_NAME v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR MultiByteStr[4112]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1078h] [rbp+F78h]

  LOBYTE(v12.Data[0]) = 1;
  v12.Data[1] = 0;
  v13 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl) )
  {
    v4 = wil::wnf_query_nothrow(
           (wil *)&WNF_WOSC_FORCE_REFRESH_REQUESTED_TRANSIENT,
           &v12,
           (bool *)MultiByteStr,
           v3,
           (unsigned __int64)&v13,
           (unsigned __int64 *)((char *)&v12 + 4),
           *(struct wil::WNF_CHANGE_STAMP_STRUCT **)&v12);
    v11 = 0;
    v5 = RtlPublishWnfStateData(WNF_WOSC_FORCE_REFRESH_REQUESTED_TRANSIENT, 0, 0, 0) | 0x10000000;
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v5,
        0);
  }
  else
  {
    v4 = wil::wnf_query_nothrow(
           (wil *)&WNF_WOSC_FORCE_REFRESH_REQUESTED,
           &v12,
           (bool *)MultiByteStr,
           v3,
           (unsigned __int64)&v13,
           (unsigned __int64 *)((char *)&v12 + 4),
           *(struct wil::WNF_CHANGE_STAMP_STRUCT **)&v12);
  }
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
      (const char *)(unsigned int)v4,
      v11);
  LOBYTE(a2->dwLowDateTime) = 0;
  a2[8].dwHighDateTime = v12.Data[1];
  if ( LOBYTE(v12.Data[0]) && (v6 = v13, v13) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
      GetSystemTimeAsFileTime(a2 + 9);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl) )
    {
      v13 = 0;
      v12.Data[1] = 0;
      StringFromMultiByte = FileContentPurveyor::CreateStringFromMultiByte(0xFDE9u, MultiByteStr, v6);
      WindowsDeleteString(0);
      v13 = (unsigned __int64)StringFromMultiByte;
      v14[0] = WindowsGetStringRawBuffer(StringFromMultiByte, (UINT32 *)&v12 + 1);
      OneSettingsClientTelemetry::WnsPushNotificationPayloadReceived<unsigned short const *>(v14);
      WnsProvider::ParseOnDemandRefreshJson(StringFromMultiByte, (struct PushNotificationPayload *)a2);
      WindowsDeleteString(StringFromMultiByte);
    }
    else
    {
      WnsProvider::ParseOnDemandRefreshJsonByteArray(MultiByteStr, v6, (struct PushNotificationPayload *)a2);
    }
    return 1;
  }
  else
  {
    OneSettingsClientTelemetry::WnsNoPushNotificationFound<bool &,unsigned __int64 &>(&v12, &v13);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl);
    v10 = v12.Data[0];
    if ( IsEnabled )
      return 0;
    return v10;
  }
}

```

## disassembly

```asm
0x18004c1fc  mov     [rsp-8+arg_0], rbx
0x18004c201  mov     [rsp-8+arg_10], rdi
0x18004c206  push    rbp
0x18004c207  lea     rbp, [rsp-0F70h]
0x18004c20f  mov     eax, 1070h
0x18004c214  call    _alloca_probe
0x18004c219  sub     rsp, rax
0x18004c21c  mov     rax, cs:__security_cookie
0x18004c223  xor     rax, rsp
0x18004c226  mov     [rbp+0F70h+var_10], rax
0x18004c22d  mov     rdi, rdx
0x18004c230  mov     byte ptr [rsp+1070h+var_1040.Data], 1; struct wil::WNF_CHANGE_STAMP_STRUCT *
0x18004c235  mov     [rsp+1070h+var_1040.Data+4], 0
0x18004c23d  mov     [rsp+1070h+var_1038], 0
0x18004c246  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x18004c24d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x18004c252  lea     r8, [rsp+1070h+MultiByteStr]; bool *
0x18004c257  lea     rdx, [rsp+1070h+var_1040]; struct _WNF_STATE_NAME *
0x18004c25c  test    al, al
0x18004c25e  lea     rax, [rsp+1070h+var_1040.Data+4]
0x18004c263  mov     [rsp+1070h+var_1048], rax; unsigned __int64 *
0x18004c268  lea     rax, [rsp+1070h+var_1038]
0x18004c26d  mov     [rsp+1070h+var_1050], rax; int
0x18004c272  jz      short loc_18004C2C4
0x18004c274  lea     rcx, WNF_WOSC_FORCE_REFRESH_REQUESTED_TRANSIENT; this
0x18004c27b  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAX_KPEA_KPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,void *,unsigned __int64,unsigned __int64 *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18004c280  mov     ebx, eax
0x18004c282  mov     [rsp+1070h+var_1050], 0; int
0x18004c28b  xor     r9d, r9d
0x18004c28e  xor     r8d, r8d
0x18004c291  xor     edx, edx
0x18004c293  mov     rcx, cs:WNF_WOSC_FORCE_REFRESH_REQUESTED_TRANSIENT
0x18004c29a  call    cs:__imp_RtlPublishWnfStateData
0x18004c2a0  or      eax, 10000000h
0x18004c2a5  mov     rcx, [rbp+0F78h]; this
0x18004c2ac  jge     short loc_18004C2D2
0x18004c2ae  mov     r9d, eax; char *
0x18004c2b1  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004c2b8  mov     edx, 1DFh; void *
0x18004c2bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c2c2  jmp     short loc_18004C2D2
0x18004c2c4  lea     rcx, WNF_WOSC_FORCE_REFRESH_REQUESTED; this
0x18004c2cb  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAX_KPEA_KPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,void *,unsigned __int64,unsigned __int64 *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18004c2d0  mov     ebx, eax
0x18004c2d2  mov     rcx, [rbp+0F78h]; this
0x18004c2d9  test    ebx, ebx
0x18004c2db  js      loc_18004C3F5
0x18004c2e1  mov     byte ptr [rdi], 0
0x18004c2e4  mov     eax, [rsp+1070h+var_1040.Data+4]
0x18004c2e8  mov     [rdi+44h], eax
0x18004c2eb  cmp     byte ptr [rsp+1070h+var_1040.Data], 0
0x18004c2f0  jz      loc_18004C3A8
0x18004c2f6  mov     rbx, [rsp+1070h+var_1038]
0x18004c2fb  test    rbx, rbx
0x18004c2fe  jz      loc_18004C3A8
0x18004c304  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl(void)'::`2'::impl
0x18004c30b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(void)
0x18004c310  test    al, al
0x18004c312  jz      short loc_18004C31E
0x18004c314  lea     rcx, [rdi+48h]; lpSystemTimeAsFileTime
0x18004c318  call    cs:__imp_GetSystemTimeAsFileTime
0x18004c31e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x18004c325  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x18004c32a  test    al, al
0x18004c32c  jz      short loc_18004C395
0x18004c32e  mov     [rsp+1070h+var_1038], 0
0x18004c337  mov     [rsp+1070h+var_1040.Data+4], 0
0x18004c33f  mov     r8d, ebx; cbMultiByte
0x18004c342  lea     rdx, [rsp+1070h+MultiByteStr]; lpMultiByteStr
0x18004c347  mov     ecx, 0FDE9h; CodePage
0x18004c34c  call    ?CreateStringFromMultiByte@FileContentPurveyor@@SAPEAUHSTRING__@@IPEBDH@Z; FileContentPurveyor::CreateStringFromMultiByte(uint,char const *,int)
0x18004c351  mov     rbx, rax
0x18004c354  xor     ecx, ecx; string
0x18004c356  call    cs:__imp_WindowsDeleteString
0x18004c35c  mov     [rsp+1070h+var_1038], rbx
0x18004c361  lea     rdx, [rsp+1070h+var_1040.Data+4]; length
0x18004c366  mov     rcx, rbx; string
0x18004c369  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c36f  mov     [rsp+1070h+var_1030], rax
0x18004c374  lea     rcx, [rsp+1070h+var_1030]
0x18004c379  call    ??$WnsPushNotificationPayloadReceived@PEBG@OneSettingsClientTelemetry@@SAX$$QEAPEBG@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadReceived<ushort const *>(ushort const * &&)
0x18004c37e  mov     rdx, rdi; struct PushNotificationPayload *
0x18004c381  mov     rcx, rbx; HSTRING
0x18004c384  call    ?ParseOnDemandRefreshJson@WnsProvider@@CA_NPEAUHSTRING__@@AEAUPushNotificationPayload@@@Z; WnsProvider::ParseOnDemandRefreshJson(HSTRING__ *,PushNotificationPayload &)
0x18004c389  nop
0x18004c38a  mov     rcx, rbx; string
0x18004c38d  call    cs:__imp_WindowsDeleteString
0x18004c393  jmp     short loc_18004C3A4
0x18004c395  mov     r8, rdi; struct PushNotificationPayload *
0x18004c398  mov     edx, ebx; cbMultiByte
0x18004c39a  lea     rcx, [rsp+1070h+MultiByteStr]; lpMultiByteStr
0x18004c39f  call    ?ParseOnDemandRefreshJsonByteArray@WnsProvider@@CA_NPEAEHAEAUPushNotificationPayload@@@Z; WnsProvider::ParseOnDemandRefreshJsonByteArray(uchar *,int,PushNotificationPayload &)
0x18004c3a4  mov     al, 1
0x18004c3a6  jmp     short loc_18004C3D1
0x18004c3a8  lea     rdx, [rsp+1070h+var_1038]
0x18004c3ad  lea     rcx, [rsp+1070h+var_1040]
0x18004c3b2  call    ??$WnsNoPushNotificationFound@AEA_NAEA_K@OneSettingsClientTelemetry@@SAXAEA_NAEA_K@Z; OneSettingsClientTelemetry::WnsNoPushNotificationFound<bool &,unsigned __int64 &>(bool &,unsigned __int64 &)
0x18004c3b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x18004c3be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x18004c3c3  movzx   edx, byte ptr [rsp+1070h+var_1040.Data]
0x18004c3c8  xor     ecx, ecx
0x18004c3ca  test    al, al
0x18004c3cc  cmovnz  edx, ecx
0x18004c3cf  mov     al, dl
0x18004c3d1  mov     rcx, [rbp+0F70h+var_10]
0x18004c3d8  xor     rcx, rsp; StackCookie
0x18004c3db  call    __security_check_cookie
0x18004c3e0  lea     r11, [rsp+1070h+var_s0]
0x18004c3e8  mov     rbx, [r11+10h]
0x18004c3ec  mov     rdi, [r11+20h]
0x18004c3f0  mov     rsp, r11
0x18004c3f3  pop     rbp
0x18004c3f4  retn
0x18004c3f5  mov     r9d, ebx; char *
0x18004c3f8  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004c3ff  mov     edx, 1E5h; void *
0x18004c404  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
