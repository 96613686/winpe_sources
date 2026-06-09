# WnsProvider::RegisterForWns(ushort const *,ushort const *)

- ea: `0x18004de2c`
- end: `0x18004e020`
- name: `?RegisterForWns@WnsProvider@@CAJPEBG0@Z`
- size: `500`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e028`

## callees

- `0x180003110`
- `0x180005f50`
- `0x1800101fc`
- `0x180049d40`
- `0x18004de2c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004de81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004de81`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WnsProvider::RegisterForWns(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  char IsEnabled; // al
  __int64 v12; // rcx
  int v13; // eax
  const char *v14; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-68h]
  __int64 v17; // [rsp+40h] [rbp-48h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-40h] BYREF
  LPVOID v19; // [rsp+50h] [rbp-38h] BYREF
  __int64 v20; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v19 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v4 = CoCreateInstance(
         &GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9,
         0,
         0x404u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &v19);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x226,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v4,
        ppv);
    v18 = 0;
    v5 = v19;
    v6 = *(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v19 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v7 = v6(v5, &v18);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    v17 = 0;
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
    v9 = **v18;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    v10 = v9(v8, &GUID_7d85494e_d99e_493a_bf51_80d2c9feab49, &v17);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v10,
        ppv);
    v20 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl);
    v12 = WNF_WOSC_FORCE_REFRESH_REQUESTED;
    if ( IsEnabled )
      v12 = WNF_WOSC_FORCE_REFRESH_REQUESTED_TRANSIENT;
    v20 = v12;
    v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)v17 + 24LL))(
            v17,
            a1,
            a2,
            2304);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v13,
        8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x240,
                           (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18004de2c  mov     [rsp+arg_10], rbx
0x18004de31  push    rsi
0x18004de32  push    rdi
0x18004de33  push    r14
0x18004de35  sub     rsp, 70h
0x18004de39  mov     rax, cs:__security_cookie
0x18004de40  xor     rax, rsp
0x18004de43  mov     [rsp+88h+var_28], rax
0x18004de48  mov     r14, rdx
0x18004de4b  mov     rsi, rcx
0x18004de4e  mov     [rsp+88h+var_38], 0
0x18004de57  lea     rcx, [rsp+88h+var_38]
0x18004de5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004de61  lea     rax, [rsp+88h+var_38]
0x18004de66  mov     [rsp+88h+ppv], rax; int
0x18004de6b  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18004de72  xor     edx, edx; pUnkOuter
0x18004de74  mov     r8d, 404h; dwClsContext
0x18004de7a  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x18004de81  call    cs:__imp_CoCreateInstance
0x18004de87  mov     rcx, [rsp+88h]; this
0x18004de8f  test    eax, eax
0x18004de91  js      loc_18004DFCC
0x18004de97  mov     [rsp+88h+var_40], 0
0x18004dea0  mov     rdi, [rsp+88h+var_38]
0x18004dea5  mov     rax, [rdi]
0x18004dea8  mov     rbx, [rax+28h]
0x18004deac  lea     rcx, [rsp+88h+var_40]
0x18004deb1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004deb6  lea     rdx, [rsp+88h+var_40]
0x18004debb  mov     rcx, rdi
0x18004debe  mov     rax, rbx
0x18004dec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dec6  mov     rcx, [rsp+88h]; this
0x18004dece  test    eax, eax
0x18004ded0  js      loc_18004DFE1
0x18004ded6  mov     [rsp+88h+var_48], 0
0x18004dedf  mov     rbx, [rsp+88h+var_40]
0x18004dee4  mov     rax, [rbx]
0x18004dee7  mov     rdi, [rax]
0x18004deea  lea     rcx, [rsp+88h+var_48]
0x18004deef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004def4  lea     r8, [rsp+88h+var_48]
0x18004def9  lea     rdx, _GUID_7d85494e_d99e_493a_bf51_80d2c9feab49
0x18004df00  mov     rcx, rbx
0x18004df03  mov     rax, rdi
0x18004df06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df0b  nop
0x18004df0c  mov     rcx, [rsp+88h]; this
0x18004df14  test    eax, eax
0x18004df16  js      loc_18004DFF6
0x18004df1c  mov     [rsp+88h+var_30], 0
0x18004df25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x18004df2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x18004df31  mov     rcx, cs:WNF_WOSC_FORCE_REFRESH_REQUESTED
0x18004df38  test    al, al
0x18004df3a  cmovnz  rcx, cs:WNF_WOSC_FORCE_REFRESH_REQUESTED_TRANSIENT
0x18004df42  mov     [rsp+88h+var_30], rcx
0x18004df47  mov     rcx, [rsp+88h+var_48]
0x18004df4c  mov     rax, [rcx]
0x18004df4f  lea     rdx, [rsp+88h+var_30]
0x18004df54  mov     [rsp+88h+var_60], rdx
0x18004df59  mov     dword ptr [rsp+88h+ppv], 8; int
0x18004df61  mov     r9d, 900h
0x18004df67  mov     r8, r14
0x18004df6a  mov     rdx, rsi
0x18004df6d  mov     rax, [rax+18h]
0x18004df71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df76  mov     rcx, [rsp+88h]; this
0x18004df7e  test    eax, eax
0x18004df80  js      loc_18004E00A
0x18004df86  lea     rcx, [rsp+88h+var_48]
0x18004df8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004df90  nop
0x18004df91  lea     rcx, [rsp+88h+var_40]
0x18004df96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004df9b  nop
0x18004df9c  lea     rcx, [rsp+88h+var_38]
0x18004dfa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dfa6  xor     eax, eax
0x18004dfa8  jmp     short loc_18004DFAE
0x18004dfaa  mov     eax, dword ptr [rsp+88h+var_48]
0x18004dfae  mov     rcx, [rsp+88h+var_28]
0x18004dfb3  xor     rcx, rsp; StackCookie
0x18004dfb6  call    __security_check_cookie
0x18004dfbb  mov     rbx, [rsp+88h+arg_10]
0x18004dfc3  add     rsp, 70h
0x18004dfc7  pop     r14
0x18004dfc9  pop     rdi
0x18004dfca  pop     rsi
0x18004dfcb  retn
0x18004dfcc  mov     r9d, eax; char *
0x18004dfcf  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004dfd6  mov     edx, 226h; void *
0x18004dfdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dfe1  mov     r9d, eax; char *
0x18004dfe4  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004dfeb  mov     edx, 22Ah; void *
0x18004dff0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dff6  mov     r9d, eax; char *
0x18004dff9  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e000  mov     edx, 22Eh; void *
0x18004e005  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e00a  mov     r9d, eax; char *
0x18004e00d  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004e014  mov     edx, 23Ch; void *
0x18004e019  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
