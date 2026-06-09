# ClientState::LoadRegData(HKEY__ *)

- ea: `0x1800290ac`
- end: `0x180029a7b`
- name: `?LoadRegData@ClientState@@AEAAXPEAUHKEY__@@@Z`
- size: `2511`
- prototype: `void __fastcall(ClientState *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025bc4`

## callees

- `0x18000fe24`
- `0x180010130`
- `0x1800101fc`
- `0x180019fb0`
- `0x18001a030`
- `0x180021f1c`
- `0x180024dec`
- `0x180025180`
- `0x1800279f4`
- `0x180028250`
- `0x180028550`
- `0x180028714`
- `0x180028d58`
- `0x1800290ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800293bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002971a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029770`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800293bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002971a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029770`

## string_xrefs

- `0x180029841`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029859`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029871`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029889`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800298a1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800298b9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800298d1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800298e9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029901`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029919`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029931`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029949`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029961`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029979`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029991`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800299a9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800299c1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800299d9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800299f1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029a09`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029a21`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029a39`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029a51`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029a69`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002937b`: `LastUserTokenResult`
- `0x180029340`: `LastDeviceTokenResult`
- `0x180029240`: `LastRefreshAttempted`
- `0x1800291f1`: `LastUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClientState::LoadRegData(ClientState *this, HKEY a2)
{
  HKEY v2; // r12
  ClientState *v3; // r13
  unsigned int v4; // eax
  char v5; // r14
  char v6; // cl
  unsigned int v7; // eax
  char v8; // cl
  unsigned int v9; // eax
  char v10; // cl
  unsigned int v11; // eax
  char v12; // cl
  unsigned int Value; // eax
  char v14; // cl
  unsigned int v15; // eax
  char v16; // cl
  unsigned int v17; // eax
  char v18; // cl
  unsigned int DWord; // eax
  char v20; // cl
  unsigned int v21; // eax
  char v22; // cl
  unsigned int v23; // eax
  char v24; // cl
  unsigned int v25; // eax
  char v26; // cl
  void *v27; // rcx
  unsigned int BinaryAlloc; // eax
  char v29; // cl
  unsigned int v30; // eax
  char v31; // cl
  _DWORD *v32; // rbx
  unsigned int v33; // eax
  char v34; // cl
  _WORD **v35; // rbx
  unsigned int v36; // eax
  char v37; // cl
  _WORD *v38; // rdx
  __int64 TypeFromJson; // rax
  const char *v40; // r9
  unsigned int v41; // eax
  char v42; // cl
  unsigned int v43; // eax
  char v44; // cl
  unsigned int v45; // eax
  char v46; // cl
  _DWORD *v47; // rbx
  unsigned int v48; // eax
  char v49; // cl
  unsigned int v50; // eax
  char v51; // cl
  unsigned int v52; // eax
  char v53; // cl
  void *v54; // rcx
  unsigned int v55; // eax
  char v56; // cl
  void *v57; // rcx
  unsigned int v58; // eax
  char v59; // cl
  unsigned int v60; // eax
  bool v61; // r8
  int v62; // [rsp+20h] [rbp-68h]
  int v63; // [rsp+20h] [rbp-68h]
  int v64; // [rsp+20h] [rbp-68h]
  int v65; // [rsp+20h] [rbp-68h]
  int v66; // [rsp+20h] [rbp-68h]
  int v67; // [rsp+20h] [rbp-68h]
  int v68; // [rsp+20h] [rbp-68h]
  int v69; // [rsp+20h] [rbp-68h]
  int v70; // [rsp+20h] [rbp-68h]
  ClientState *v71; // [rsp+40h] [rbp-48h] BYREF
  std::_Ref_count_base *v72; // [rsp+48h] [rbp-40h]
  __int64 v73; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  ClientState *v75; // [rsp+90h] [rbp+8h] BYREF
  HKEY v76; // [rsp+98h] [rbp+10h]

  v76 = a2;
  v75 = this;
  v2 = a2;
  v3 = this;
  v4 = RegWow64Helpers::InitializeCoTaskMemNativeString(a2, 0);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147024894 )
  {
    v6 = 0;
    v5 = 1;
  }
  else
  {
    v5 = 1;
    v6 = 1;
  }
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CB,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v4,
      v62);
  v7 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v7 + 0x80000000) & 0x80000000) != 0 || (v8 = 1, v7 == -2147024894) )
    v8 = 0;
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v7,
      v62);
  v9 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v9 + 0x80000000) & 0x80000000) != 0 || (v10 = 1, v9 == -2147024894) )
    v10 = 0;
  if ( v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v9,
      v62);
  v11 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v11 + 0x80000000) & 0x80000000) != 0 || (v12 = 1, v11 == -2147024894) )
    v12 = 0;
  if ( v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v11,
      v62);
  Value = RegWow64Helpers::GetValue(v2, 0, L"LastUpdated", 0x40u, (char *)v3 + 184, 8u, 0);
  if ( ((Value + 0x80000000) & 0x80000000) != 0 || (v14 = 1, Value == -2147024894) )
    v14 = 0;
  if ( v14 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)Value,
      v63);
  v15 = RegWow64Helpers::GetValue(v2, 0, L"LastRefreshAttempted", 0x40u, (char *)v3 + 192, 8u, 0);
  if ( ((v15 + 0x80000000) & 0x80000000) != 0 || (v16 = 1, v15 == -2147024894) )
    v16 = 0;
  if ( v16 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v15,
      v64);
  v17 = RegWow64Helpers::GetValue(v2, 0, L"LastRefreshByApp", 0x40u, (char *)v3 + 200, 8u, 0);
  if ( ((v17 + 0x80000000) & 0x80000000) != 0 || (v18 = 1, v17 == -2147024894) )
    v18 = 0;
  if ( v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v17,
      v65);
  DWord = RegWow64Helpers::GetDWord(v2, 0, L"RefreshInterval", (unsigned int *)v3 + 52);
  if ( ((DWord + 0x80000000) & 0x80000000) != 0 || (v20 = 1, DWord == -2147024894) )
    v20 = 0;
  if ( v20 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E3,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)DWord,
      v65);
  v21 = RegWow64Helpers::GetDWord(v2, 0, L"LastHTTPCode", (unsigned int *)v3 + 53);
  if ( ((v21 + 0x80000000) & 0x80000000) != 0 || (v22 = 1, v21 == -2147024894) )
    v22 = 0;
  if ( v22 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v21,
      v65);
  v23 = RegWow64Helpers::GetDWord(v2, 0, L"LastDeviceTokenResult", (unsigned int *)v3 + 54);
  if ( ((v23 + 0x80000000) & 0x80000000) != 0 || (v24 = 1, v23 == -2147024894) )
    v24 = 0;
  if ( v24 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v23,
      v65);
  v25 = RegWow64Helpers::GetDWord(v2, 0, L"LastUserTokenResult", (unsigned int *)v3 + 55);
  if ( ((v25 + 0x80000000) & 0x80000000) != 0 || (v26 = 1, v25 == -2147024894) )
    v26 = 0;
  if ( v26 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v25,
      v65);
  v27 = (void *)*((_QWORD *)v3 + 28);
  *((_QWORD *)v3 + 28) = 0;
  CoTaskMemFree(v27);
  BinaryAlloc = RegWow64Helpers::GetBinaryAlloc(v2, 0, L"QueryStringHash", (void **)v3 + 28, (unsigned int *)v3 + 58);
  if ( ((BinaryAlloc + 0x80000000) & 0x80000000) != 0 || (v29 = 1, BinaryAlloc == -2147024894) )
    v29 = 0;
  if ( v29 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)BinaryAlloc,
      v66);
  v30 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v30 + 0x80000000) & 0x80000000) != 0 || (v31 = 1, v30 == -2147024894) )
    v31 = 0;
  if ( v31 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v30,
      v66);
  v32 = (_DWORD *)((char *)v3 + 280);
  v33 = RegWow64Helpers::GetDWord(v2, 0, L"Environment", (unsigned int *)v3 + 70);
  if ( ((v33 + 0x80000000) & 0x80000000) != 0 || (v34 = 1, v33 == -2147024894) )
    v34 = 0;
  if ( v34 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v33,
      v66);
  if ( *v32 > 1u )
    *v32 = 0;
  v35 = (_WORD **)((char *)v3 + 304);
  v36 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v36 + 0x80000000) & 0x80000000) != 0 || (v37 = 1, v36 == -2147024894) )
    v37 = 0;
  if ( v37 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v36,
      v66);
  v38 = *v35;
  if ( *v35 && *v38 )
  {
    try
    {
      TypeFromJson = ClientState::MakeTypeFromJsonString<IPayloadHandler>((__int64)&v71, (__int64)v38);
      std::shared_ptr<CnsFlightState>::operator=((char *)v3 + 288, TypeFromJson);
      if ( v72 )
        std::_Ref_count_base::_Decref(v72);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x307,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        v40);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)v75 + 304);
      v5 = 1;
      v3 = v75;
      v2 = v76;
    }
  }
  v41 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v41 + 0x80000000) & 0x80000000) != 0 || (v42 = 1, v41 == -2147024894) )
    v42 = 0;
  if ( v42 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v41,
      v66);
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v43 = RegWow64Helpers::InitializeCoTaskMemNativeString(v2, 0);
  if ( ((v43 + 0x80000000) & 0x80000000) != 0 || (v44 = 1, v43 == -2147024894) )
    v44 = 0;
  if ( v44 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x314,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v43,
      v66);
  if ( v71 && *(_WORD *)v71 )
  {
    v75 = v71;
    Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)v3 + 336, &v75);
  }
  v45 = RegWow64Helpers::GetValue(v2, 0, L"LastForceRefresh", 0x40u, (char *)v3 + 404, 8u, 0);
  if ( ((v45 + 0x80000000) & 0x80000000) != 0 || (v46 = 1, v45 == -2147024894) )
    v46 = 0;
  if ( v46 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)v45,
      v67);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::GetImpl'::`2'::impl) )
  {
    v47 = (_DWORD *)((char *)v3 + 428);
    v48 = RegWow64Helpers::GetDWord(v2, 0, L"WnsEnvironment", (unsigned int *)v3 + 107);
    if ( ((v48 + 0x80000000) & 0x80000000) != 0 || (v49 = 1, v48 == -2147024894) )
      v49 = 0;
    if ( v49 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x322,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v48,
        v67);
    if ( *v47 > 1u )
      *v47 = 0;
    v50 = RegWow64Helpers::GetValue(v2, 0, L"WnsChannelExpires", 0x40u, (char *)v3 + 444, 8u, 0);
    if ( ((v50 + 0x80000000) & 0x80000000) != 0 || (v51 = 1, v50 == -2147024894) )
      v51 = 0;
    if ( v51 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v50,
        v68);
    v52 = RegWow64Helpers::GetDWord(v2, 0, L"WnsChannelExpiresDays", (unsigned int *)v3 + 113);
    if ( ((v52 + 0x80000000) & 0x80000000) != 0 || (v53 = 1, v52 == -2147024894) )
      v53 = 0;
    if ( v53 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32D,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v52,
        v68);
    if ( v52 == -2147024894 )
      *((_DWORD *)v3 + 113) = 0;
    v54 = (void *)*((_QWORD *)v3 + 54);
    *((_QWORD *)v3 + 54) = 0;
    CoTaskMemFree(v54);
    v55 = RegWow64Helpers::GetBinaryAlloc(v2, 0, L"WnsRegistered", (void **)v3 + 54, (unsigned int *)v3 + 110);
    if ( ((v55 + 0x80000000) & 0x80000000) != 0 || (v56 = 1, v55 == -2147024894) )
      v56 = 0;
    if ( v56 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x336,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v55,
        v69);
    v57 = (void *)*((_QWORD *)v3 + 57);
    *((_QWORD *)v3 + 57) = 0;
    CoTaskMemFree(v57);
    v58 = RegWow64Helpers::GetBinaryAlloc(v2, 0, L"WnsChannelRegistered", (void **)v3 + 57, (unsigned int *)v3 + 116);
    if ( ((v58 + 0x80000000) & 0x80000000) != 0 || (v59 = 1, v58 == -2147024894) )
      v59 = 0;
    if ( v59 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33B,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v58,
        v70);
    v60 = RegWow64Helpers::GetDWord(v2, 0, L"WnsLastWnfEvent", (unsigned int *)v3 + 117);
    if ( ((v60 + 0x80000000) & 0x80000000) != 0 || v60 == -2147024894 )
      v5 = 0;
    if ( v5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x340,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v60,
        v70);
    *((_BYTE *)v3 + 472) = v60 != -2147024894;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
    ClientState::LoadCnsRegData(v3, v2, v61);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v71);
}

```

## disassembly

```asm
0x1800290ac  mov     rax, rsp
0x1800290af  mov     [rax+18h], rbx
0x1800290b3  mov     [rax+20h], rsi
0x1800290b7  mov     [rax+10h], rdx
0x1800290bb  mov     [rax+8], rcx
0x1800290bf  push    rdi
0x1800290c0  push    r12
0x1800290c2  push    r13
0x1800290c4  push    r14
0x1800290c6  push    r15
0x1800290c8  sub     rsp, 60h
0x1800290cc  mov     r12, rdx
0x1800290cf  mov     r13, rcx
0x1800290d2  lea     r9, [rcx+48h]
0x1800290d6  lea     r8, ?c_regvalETag@ClientState@@0QBGB; "ETag"
0x1800290dd  xor     edx, edx; unsigned __int16 *
0x1800290df  mov     rcx, r12; HKEY
0x1800290e2  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800290e7  mov     r15d, 80000000h
0x1800290ed  lea     r8d, [rax+r15]
0x1800290f1  mov     esi, 80070002h
0x1800290f6  test    r15d, r8d
0x1800290f9  jnz     short loc_18002910C
0x1800290fb  cmp     eax, esi
0x1800290fd  jz      short loc_18002910C
0x1800290ff  mov     r14d, 1
0x180029105  mov     cl, r14b
0x180029108  xor     edi, edi
0x18002910a  jmp     short loc_180029115
0x18002910c  xor     edi, edi
0x18002910e  mov     cl, dil
0x180029111  lea     r14d, [rdi+1]
0x180029115  mov     r10, [rsp+88h]
0x18002911d  test    cl, cl
0x18002911f  jnz     loc_18002983E
0x180029125  lea     r9, [r13+70h]
0x180029129  lea     r8, ?c_regvalETagBackup@ClientState@@0QBGB; "ETagBackup"
0x180029130  xor     edx, edx; unsigned __int16 *
0x180029132  mov     rcx, r12; HKEY
0x180029135  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18002913a  lea     ecx, [rax+r15]
0x18002913e  test    r15d, ecx
0x180029141  jnz     short loc_18002914A
0x180029143  cmp     eax, esi
0x180029145  mov     cl, r14b
0x180029148  jnz     short loc_18002914D
0x18002914a  mov     cl, dil
0x18002914d  mov     r10, [rsp+88h]
0x180029155  test    cl, cl
0x180029157  jnz     loc_180029856
0x18002915d  lea     r9, [r13+88h]
0x180029164  lea     r8, ?c_regvalETagValidated@ClientState@@0QBGB; "ETagValidated"
0x18002916b  xor     edx, edx; unsigned __int16 *
0x18002916d  mov     rcx, r12; HKEY
0x180029170  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180029175  lea     ecx, [rax+r15]
0x180029179  test    r15d, ecx
0x18002917c  jnz     short loc_180029185
0x18002917e  cmp     eax, esi
0x180029180  mov     cl, r14b
0x180029183  jnz     short loc_180029188
0x180029185  mov     cl, dil
0x180029188  mov     r10, [rsp+88h]
0x180029190  test    cl, cl
0x180029192  jnz     loc_18002986E
0x180029198  lea     r9, [r13+0A0h]
0x18002919f  lea     r8, ?c_regvalETagAcknowledged@ClientState@@0QBGB; "ETagAcknowledged"
0x1800291a6  xor     edx, edx; unsigned __int16 *
0x1800291a8  mov     rcx, r12; HKEY
0x1800291ab  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800291b0  lea     ecx, [rax+r15]
0x1800291b4  test    r15d, ecx
0x1800291b7  jnz     short loc_1800291C0
0x1800291b9  cmp     eax, esi
0x1800291bb  mov     cl, r14b
0x1800291be  jnz     short loc_1800291C3
0x1800291c0  mov     cl, dil
0x1800291c3  mov     r10, [rsp+88h]
0x1800291cb  test    cl, cl
0x1800291cd  jnz     loc_180029886
0x1800291d3  lea     rax, [r13+0B8h]
0x1800291da  mov     [rsp+88h+var_58], rdi; unsigned int *
0x1800291df  mov     ebx, 8
0x1800291e4  mov     [rsp+88h+var_60], ebx; unsigned int
0x1800291e8  mov     [rsp+88h+var_68], rax; int
0x1800291ed  lea     r9d, [rbx+38h]; unsigned int
0x1800291f1  lea     r8, ?c_regvalLastUpdated@ClientState@@0QBGB; "LastUpdated"
0x1800291f8  xor     edx, edx; unsigned __int16 *
0x1800291fa  mov     rcx, r12; HKEY
0x1800291fd  call    ?GetValue@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1KPEAXKPEAK@Z; RegWow64Helpers::GetValue(HKEY__ * const,ushort const * const,ushort const * const,ulong,void *,ulong,ulong *)
0x180029202  lea     ecx, [rax+r15]
0x180029206  test    r15d, ecx
0x180029209  jnz     short loc_180029212
0x18002920b  cmp     eax, esi
0x18002920d  mov     cl, r14b
0x180029210  jnz     short loc_180029215
0x180029212  mov     cl, dil
0x180029215  mov     r10, [rsp+88h]
0x18002921d  test    cl, cl
0x18002921f  jnz     loc_18002989E
0x180029225  lea     rax, [r13+0C0h]
0x18002922c  mov     [rsp+88h+var_58], rdi; unsigned int *
0x180029231  mov     [rsp+88h+var_60], ebx; unsigned int
0x180029235  mov     [rsp+88h+var_68], rax; int
0x18002923a  mov     r9d, 40h ; '@'; unsigned int
0x180029240  lea     r8, ?c_regvalLastRefresh@ClientState@@0QBGB; "LastRefreshAttempted"
0x180029247  xor     edx, edx; unsigned __int16 *
0x180029249  mov     rcx, r12; HKEY
0x18002924c  call    ?GetValue@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1KPEAXKPEAK@Z; RegWow64Helpers::GetValue(HKEY__ * const,ushort const * const,ushort const * const,ulong,void *,ulong,ulong *)
0x180029251  lea     ecx, [rax+r15]
0x180029255  test    r15d, ecx
0x180029258  jnz     short loc_180029261
0x18002925a  cmp     eax, esi
0x18002925c  mov     cl, r14b
0x18002925f  jnz     short loc_180029264
0x180029261  mov     cl, dil
0x180029264  mov     r10, [rsp+88h]
0x18002926c  test    cl, cl
0x18002926e  jnz     loc_1800298B6
0x180029274  lea     rax, [r13+0C8h]
0x18002927b  mov     [rsp+88h+var_58], rdi; unsigned int *
0x180029280  mov     [rsp+88h+var_60], ebx; unsigned int
0x180029284  mov     [rsp+88h+var_68], rax; int
0x180029289  mov     r9d, 40h ; '@'; unsigned int
0x18002928f  lea     r8, ?c_regvalLastRefreshByApp@ClientState@@0QBGB; "LastRefreshByApp"
0x180029296  xor     edx, edx; unsigned __int16 *
0x180029298  mov     rcx, r12; HKEY
0x18002929b  call    ?GetValue@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1KPEAXKPEAK@Z; RegWow64Helpers::GetValue(HKEY__ * const,ushort const * const,ushort const * const,ulong,void *,ulong,ulong *)
0x1800292a0  lea     ecx, [rax+r15]
0x1800292a4  test    r15d, ecx
0x1800292a7  jnz     short loc_1800292B0
0x1800292a9  cmp     eax, esi
0x1800292ab  mov     cl, r14b
0x1800292ae  jnz     short loc_1800292B3
0x1800292b0  mov     cl, dil
0x1800292b3  mov     r10, [rsp+88h]
0x1800292bb  test    cl, cl
0x1800292bd  jnz     loc_1800298CE
0x1800292c3  lea     r9, [r13+0D0h]; unsigned int *
0x1800292ca  lea     r8, ?c_regvalRefreshInterval@ClientState@@0QBGB; "RefreshInterval"
0x1800292d1  xor     edx, edx; unsigned __int16 *
0x1800292d3  mov     rcx, r12; HKEY
0x1800292d6  call    ?GetDWord@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAK@Z; RegWow64Helpers::GetDWord(HKEY__ * const,ushort const * const,ushort const * const,ulong *)
0x1800292db  lea     ecx, [rax+r15]
0x1800292df  test    r15d, ecx
0x1800292e2  jnz     short loc_1800292EB
0x1800292e4  cmp     eax, esi
0x1800292e6  mov     cl, r14b
0x1800292e9  jnz     short loc_1800292EE
0x1800292eb  mov     cl, dil
0x1800292ee  mov     r10, [rsp+88h]
0x1800292f6  test    cl, cl
0x1800292f8  jnz     loc_1800298E6
0x1800292fe  lea     r9, [r13+0D4h]; unsigned int *
0x180029305  lea     r8, ?c_regvalLastHTTPCode@ClientState@@0QBGB; "LastHTTPCode"
0x18002930c  xor     edx, edx; unsigned __int16 *
0x18002930e  mov     rcx, r12; HKEY
0x180029311  call    ?GetDWord@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAK@Z; RegWow64Helpers::GetDWord(HKEY__ * const,ushort const * const,ushort const * const,ulong *)
0x180029316  lea     ecx, [rax+r15]
0x18002931a  test    r15d, ecx
0x18002931d  jnz     short loc_180029326
0x18002931f  cmp     eax, esi
0x180029321  mov     cl, r14b
0x180029324  jnz     short loc_180029329
0x180029326  mov     cl, dil
0x180029329  mov     r10, [rsp+88h]
0x180029331  test    cl, cl
0x180029333  jnz     loc_1800298FE
0x180029339  lea     r9, [r13+0D8h]; unsigned int *
0x180029340  lea     r8, ?c_regvalLastDeviceTokenResult@ClientState@@0QBGB; "LastDeviceTokenResult"
0x180029347  xor     edx, edx; unsigned __int16 *
0x180029349  mov     rcx, r12; HKEY
0x18002934c  call    ?GetDWord@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAK@Z; RegWow64Helpers::GetDWord(HKEY__ * const,ushort const * const,ushort const * const,ulong *)
0x180029351  lea     ecx, [rax+r15]
0x180029355  test    r15d, ecx
0x180029358  jnz     short loc_180029361
0x18002935a  cmp     eax, esi
0x18002935c  mov     cl, r14b
0x18002935f  jnz     short loc_180029364
0x180029361  mov     cl, dil
0x180029364  mov     r10, [rsp+88h]
0x18002936c  test    cl, cl
0x18002936e  jnz     loc_180029916
0x180029374  lea     r9, [r13+0DCh]; unsigned int *
0x18002937b  lea     r8, ?c_regvalLastUserTokenResult@ClientState@@0QBGB; "LastUserTokenResult"
0x180029382  xor     edx, edx; unsigned __int16 *
0x180029384  mov     rcx, r12; HKEY
0x180029387  call    ?GetDWord@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAK@Z; RegWow64Helpers::GetDWord(HKEY__ * const,ushort const * const,ushort const * const,ulong *)
0x18002938c  lea     ecx, [rax+r15]
0x180029390  test    r15d, ecx
0x180029393  jnz     short loc_18002939C
0x180029395  cmp     eax, esi
0x180029397  mov     cl, r14b
0x18002939a  jnz     short loc_18002939F
0x18002939c  mov     cl, dil
0x18002939f  mov     r10, [rsp+88h]
0x1800293a7  test    cl, cl
0x1800293a9  jnz     loc_18002992E
0x1800293af  lea     rbx, [r13+0E0h]
0x1800293b6  mov     rcx, [rbx]; pv
0x1800293b9  mov     [rbx], rdi
0x1800293bc  call    cs:__imp_CoTaskMemFree
0x1800293c2  lea     rax, [r13+0E8h]
0x1800293c9  mov     [rsp+88h+var_68], rax; int
0x1800293ce  mov     r9, rbx; void **
0x1800293d1  lea     r8, ?c_regvalQueryStringHash@ClientState@@0QBGB; "QueryStringHash"
0x1800293d8  xor     edx, edx; unsigned __int16 *
0x1800293da  mov     rcx, r12; HKEY
0x1800293dd  call    ?GetBinaryAlloc@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAPEAXPEAK@Z; RegWow64Helpers::GetBinaryAlloc(HKEY__ * const,ushort const * const,ushort const * const,void * *,ulong *)
0x1800293e2  lea     ecx, [rax+r15]
0x1800293e6  test    r15d, ecx
0x1800293e9  jnz     short loc_1800293F2
0x1800293eb  cmp     eax, esi
0x1800293ed  mov     cl, r14b
0x1800293f0  jnz     short loc_1800293F5
0x1800293f2  mov     cl, dil
0x1800293f5  mov     r10, [rsp+88h]
0x1800293fd  test    cl, cl
0x1800293ff  jnz     loc_180029946
0x180029405  lea     r9, [r13+100h]
0x18002940c  lea     r8, ?c_regvalLastVersion@ClientState@@0QBGB; "Version"
0x180029413  xor     edx, edx; unsigned __int16 *
0x180029415  mov     rcx, r12; HKEY
0x180029418  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18002941d  lea     ecx, [rax+r15]
0x180029421  test    r15d, ecx
0x180029424  jnz     short loc_18002942D
0x180029426  cmp     eax, esi
0x180029428  mov     cl, r14b
0x18002942b  jnz     short loc_180029430
0x18002942d  mov     cl, dil
0x180029430  mov     r10, [rsp+88h]
0x180029438  test    cl, cl
0x18002943a  jnz     loc_18002995E
0x180029440  lea     rbx, [r13+118h]
0x180029447  mov     r9, rbx; unsigned int *
0x18002944a  lea     r8, ?c_regvalEnvironment@ClientState@@0QBGB; "Environment"
0x180029451  xor     edx, edx; unsigned __int16 *
0x180029453  mov     rcx, r12; HKEY
0x180029456  call    ?GetDWord@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAK@Z; RegWow64Helpers::GetDWord(HKEY__ * const,ushort const * const,ushort const * const,ulong *)
0x18002945b  lea     ecx, [rax+r15]
0x18002945f  test    r15d, ecx
0x180029462  jnz     short loc_18002946B
0x180029464  cmp     eax, esi
0x180029466  mov     cl, r14b
0x180029469  jnz     short loc_18002946E
0x18002946b  mov     cl, dil
0x18002946e  mov     r10, [rsp+88h]
0x180029476  test    cl, cl
0x180029478  jnz     loc_180029976
0x18002947e  cmp     [rbx], r14d
0x180029481  jbe     short loc_180029485
0x180029483  mov     [rbx], edi
0x180029485  lea     rbx, [r13+130h]
0x18002948c  mov     r9, rbx
0x18002948f  lea     r8, ?c_regvalLastPayload@ClientState@@0QBGB; "LastPayload"
0x180029496  xor     edx, edx; unsigned __int16 *
0x180029498  mov     rcx, r12; HKEY
0x18002949b  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800294a0  lea     ecx, [rax+r15]
0x1800294a4  test    r15d, ecx
0x1800294a7  jnz     short loc_1800294B0
0x1800294a9  cmp     eax, esi
0x1800294ab  mov     cl, r14b
0x1800294ae  jnz     short loc_1800294B3
0x1800294b0  mov     cl, dil
0x1800294b3  mov     r10, [rsp+88h]
0x1800294bb  test    cl, cl
0x1800294bd  jnz     loc_18002998E
0x1800294c3  mov     rdx, [rbx]
0x1800294c6  test    rdx, rdx
0x1800294c9  jz      short loc_18002951C
0x1800294cb  cmp     [rdx], di
0x1800294ce  jz      short loc_18002951C
0x1800294d0  lea     rcx, [rsp+88h+var_48]
0x1800294d5  call    ??$MakeTypeFromJsonString@VIPayloadHandler@@@ClientState@@CA?AV?$shared_ptr@VIPayloadHandler@@@std@@PEBGP6A?AV12@PEAUIJsonObject@Json@Data@Windows@@@Z@Z; ClientState::MakeTypeFromJsonString<IPayloadHandler>(ushort const *,std::shared_ptr<IPayloadHandler> (*)(Windows::Data::Json::IJsonObject *))
0x1800294da  lea     rcx, [r13+120h]
0x1800294e1  mov     rdx, rax
0x1800294e4  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> &&)
0x1800294e9  mov     rcx, [rsp+88h+var_40]; this
0x1800294ee  test    rcx, rcx
0x1800294f1  jz      short loc_1800294F9
0x1800294f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800294f8  nop
0x1800294f9  jmp     short loc_18002951C
0x1800294fb  mov     esi, 80070002h
0x180029500  xor     edi, edi
0x180029502  mov     r15d, 80000000h
0x180029508  lea     r14d, [rdi+1]
0x18002950c  mov     r13, [rsp+88h+arg_0]
0x180029514  mov     r12, [rsp+88h+arg_8]
0x18002951c  lea     r9, [r13+170h]
0x180029523  lea     r8, ?c_regvalLastNotification@ClientState@@0QBGB; "LastNotification"
0x18002952a  xor     edx, edx; unsigned __int16 *
0x18002952c  mov     rcx, r12; HKEY
0x18002952f  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180029534  lea     ecx, [rax+r15]
0x180029538  test    r15d, ecx
0x18002953b  jnz     short loc_180029544
0x18002953d  cmp     eax, esi
  ... truncated ...
```
