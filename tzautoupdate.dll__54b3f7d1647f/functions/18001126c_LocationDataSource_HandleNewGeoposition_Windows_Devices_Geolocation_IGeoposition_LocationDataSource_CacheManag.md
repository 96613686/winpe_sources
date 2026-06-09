# LocationDataSource::HandleNewGeoposition(Windows::Devices::Geolocation::IGeoposition *,LocationDataSource::CacheManager &)

- ea: `0x18001126c`
- end: `0x1800116b4`
- name: `?HandleNewGeoposition@LocationDataSource@@AEAAJPEAUIGeoposition@Geolocation@Devices@Windows@@AEAVCacheManager@1@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(LocationDataSource *__hidden this, struct Windows::Devices::Geolocation::IGeoposition *, struct LocationDataSource::CacheManager *)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011100`
- `0x180011b60`

## callees

- `0x18000166c`
- `0x1800018fc`
- `0x180001978`
- `0x1800019f8`
- `0x180006844`
- `0x18000885c`
- `0x18000cfec`
- `0x180010cac`
- `0x18001126c`
- `0x180011b0c`
- `0x180011e2c`
- `0x180012178`
- `0x1800123b8`
- `0x180012d38`
- `0x180012df8`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800113dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800113dc`

## string_xrefs

- `0x1800112d1`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`
- `0x180011322`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`
- `0x18001154d`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`
- `0x1800115a4`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`

## pseudocode

```c
__int64 __fastcall LocationDataSource::HandleNewGeoposition(
        LocationDataSource *this,
        struct Windows::Devices::Geolocation::IGeoposition *a2,
        struct LocationDataSource::CacheManager *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Devices::Geolocation::IGeoposition *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r8
  HRESULT v18; // eax
  __int64 v19; // rdx
  LPVOID v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r9
  LPVOID v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rdi
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rbx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // r8
  int ppv; // [rsp+20h] [rbp-E0h]
  char v42[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v48; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+80h] [rbp-80h] BYREF
  int v50; // [rsp+84h] [rbp-7Ch] BYREF
  int v51; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-70h] BYREF
  int v53[2]; // [rsp+98h] [rbp-68h] BYREF
  int v54; // [rsp+A0h] [rbp-60h] BYREF
  int v55; // [rsp+A4h] [rbp-5Ch] BYREF
  int v56; // [rsp+A8h] [rbp-58h] BYREF
  int v57; // [rsp+ACh] [rbp-54h] BYREF
  _BYTE v58[64]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v59[80]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v60; // [rsp+140h] [rbp+40h] BYREF
  __int64 v61; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v52 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Devices::Geolocation::IGeoposition *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  v7 = v6(a2, &v52);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    goto LABEL_40;
  }
  v44 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
  v10 = **v52;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
  v11 = v10(v9, &GUID_95e634be_dbd6_40ac_b8f2_a65c0340d9a6, &v44);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 317;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)v11,
      ppv);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
    goto LABEL_40;
  }
  v43 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 48LL))(v44, &v43);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 320;
    goto LABEL_5;
  }
  if ( *((_BYTE *)this + 76) && v43 == 3 )
  {
    Cache::Lock(*(_QWORD *)this, v58, v14);
    v42[0] = 1;
    Cache::ValueProxy<bool>::SetValue(v59, v42);
    Cache::Proxy::~Proxy((Cache::Proxy *)v58);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl'::`2'::impl,
                          v13,
                          v14,
                          v15) )
  {
    v48 = 0;
    v18 = CoCreateInstance(
            &GUID_581333f6_28db_41be_bc7a_ff201f12f3f6,
            0,
            4u,
            &GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7,
            &v48);
    v21 = (unsigned int)v18;
    v50 = 0;
    v51 = 0;
    v49 = 0;
    if ( v18 >= 0 )
    {
      v20 = v48;
      if ( v48 )
        v21 = (*(unsigned int (__fastcall **)(LPVOID, int *, int *, int *))(*(_QWORD *)v48 + 40LL))(
                v48,
                &v50,
                &v51,
                &v49);
    }
    if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v20, 0x400000000000LL, v21) )
    {
      v54 = v49;
      v55 = v50;
      v56 = v51;
      v57 = v21;
      v45 = v43;
      *(_QWORD *)v53 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v22,
        (__int64)&byte_18002943F,
        v21,
        v23,
        (__int64)v53,
        (__int64)&v45,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v54);
    }
    v24 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v24 + 16LL))(v24, v19, v21);
    }
  }
  else if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL, v17) )
  {
    v45 = v43;
    *(_QWORD *)v53 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v25,
      (__int64)&byte_1800291EF,
      v26,
      v27,
      (__int64)v53,
      (__int64)&v45);
  }
  v46 = 0;
  v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v52;
  v29 = **v52;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  v30 = v29(v28, &GUID_feea0525_d22c_4d46_b527_0b96066fc7db, &v46);
  v8 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)v30,
      ppv);
LABEL_27:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    goto LABEL_6;
  }
  v47 = 0;
  v31 = v46;
  v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  v33 = v32(v31, &v47);
  v8 = v33;
  if ( v33 < 0 )
  {
    v34 = 369;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)v33,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    goto LABEL_27;
  }
  v60 = 0;
  v61 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v47 + 48LL))(v47, &v60);
  v8 = v33;
  if ( v33 < 0 )
  {
    v34 = 372;
    goto LABEL_30;
  }
  if ( (unsigned int)dword_180030000 > 5 )
  {
    *(_QWORD *)v53 = *((_QWORD *)&v60 + 1);
    v48 = (LPVOID)v60;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v35,
      (__int64)&word_180028C76,
      v36,
      v37,
      (__int64)&v48,
      (__int64)v53);
  }
  LocationDataSource::CacheManager::WriteLocationToCache(
    a3,
    (struct Windows::Devices::Geolocation::BasicGeoposition *)&v60);
  if ( *((_BYTE *)this + 76) )
  {
    LocationDataSource::UpdateMovementThreshold(this);
    LocationDataSource::ToggleActiveModeBasedOnRadius(this);
  }
  if ( *((_BYTE *)this + 77) )
    LocationDataSource::EnableServiceIfAppropriate(v38, v43, v39);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
  v8 = 0;
LABEL_40:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  return v8;
}

```

## disassembly

```asm
0x18001126c  mov     [rsp-8+arg_18], rbx
0x180011271  push    rbp
0x180011272  push    rsi
0x180011273  push    rdi
0x180011274  push    r14
0x180011276  push    r15
0x180011278  lea     rbp, [rsp-60h]
0x18001127d  sub     rsp, 160h
0x180011284  mov     rax, cs:__security_cookie
0x18001128b  xor     rax, rsp
0x18001128e  mov     [rbp+80h+var_28], rax
0x180011292  mov     r14, r8
0x180011295  mov     rdi, rdx
0x180011298  mov     rsi, rcx
0x18001129b  xor     r15d, r15d
0x18001129e  mov     [rbp+80h+var_F0], r15
0x1800112a2  mov     rax, [rdx]
0x1800112a5  mov     rbx, [rax+30h]
0x1800112a9  lea     rcx, [rbp+80h+var_F0]
0x1800112ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800112b2  lea     rdx, [rbp+80h+var_F0]
0x1800112b6  mov     rcx, rdi
0x1800112b9  mov     rax, rbx
0x1800112bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c1  mov     ebx, eax
0x1800112c3  test    eax, eax
0x1800112c5  jns     short loc_1800112E7
0x1800112c7  mov     rcx, [rbp+88h]; this
0x1800112ce  mov     r9d, eax; char *
0x1800112d1  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x1800112d8  mov     edx, 13Ah; void *
0x1800112dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112e2  jmp     loc_180011686
0x1800112e7  mov     [rsp+180h+var_128], r15
0x1800112ec  mov     rbx, [rbp+80h+var_F0]
0x1800112f0  mov     rax, [rbx]
0x1800112f3  mov     rdi, [rax]
0x1800112f6  lea     rcx, [rsp+180h+var_128]
0x1800112fb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011300  lea     r8, [rsp+180h+var_128]
0x180011305  lea     rdx, _GUID_95e634be_dbd6_40ac_b8f2_a65c0340d9a6
0x18001130c  mov     rcx, rbx
0x18001130f  mov     rax, rdi
0x180011312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011317  mov     ebx, eax
0x180011319  test    eax, eax
0x18001131b  jns     short loc_180011348
0x18001131d  mov     edx, 13Dh; void *
0x180011322  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180011329  mov     r9d, eax; char *
0x18001132c  mov     rcx, [rbp+88h]; this
0x180011333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011338  nop
0x180011339  lea     rcx, [rsp+180h+var_128]
0x18001133e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011343  jmp     loc_180011686
0x180011348  mov     [rsp+180h+var_12C], r15d
0x18001134d  mov     rcx, [rsp+180h+var_128]
0x180011352  mov     rax, [rcx]
0x180011355  lea     rdx, [rsp+180h+var_12C]
0x18001135a  mov     rax, [rax+30h]
0x18001135e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011363  mov     ebx, eax
0x180011365  test    eax, eax
0x180011367  jns     short loc_180011370
0x180011369  mov     edx, 140h
0x18001136e  jmp     short loc_180011322
0x180011370  cmp     [rsi+4Ch], r15b
0x180011374  jz      short loc_1800113A5
0x180011376  cmp     [rsp+180h+var_12C], 3
0x18001137b  jnz     short loc_1800113A5
0x18001137d  lea     rdx, [rbp+80h+var_D0]
0x180011381  mov     rcx, [rsi]
0x180011384  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x180011389  mov     [rsp+180h+var_130], 1
0x18001138e  lea     rdx, [rsp+180h+var_130]
0x180011393  lea     rcx, [rbp+80h+var_90]
0x180011397  call    ?SetValue@?$ValueProxy@_N@Cache@@QEAAXAEB_N@Z; Cache::ValueProxy<bool>::SetValue(bool const &)
0x18001139c  lea     rcx, [rbp+80h+var_D0]; this
0x1800113a0  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x1800113a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Scenario58454712@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712> `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl(void)'::`2'::impl
0x1800113ac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(void)
0x1800113b1  test    al, al
0x1800113b3  jz      loc_1800114C0
0x1800113b9  mov     [rsp+180h+var_108], r15
0x1800113be  lea     rax, [rsp+180h+var_108]
0x1800113c3  mov     [rsp+180h+ppv], rax; ppv
0x1800113c8  lea     r9, _GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7; riid
0x1800113cf  xor     edx, edx; pUnkOuter
0x1800113d1  lea     r8d, [rdx+4]; dwClsContext
0x1800113d5  lea     rcx, _GUID_581333f6_28db_41be_bc7a_ff201f12f3f6; rclsid
0x1800113dc  call    cs:__imp_CoCreateInstance
0x1800113e2  mov     r8d, eax
0x1800113e5  mov     [rbp+80h+var_FC], r15d
0x1800113e9  mov     [rbp+80h+var_F8], r15d
0x1800113ed  mov     [rbp+80h+var_100], r15d
0x1800113f1  test    eax, eax
0x1800113f3  js      short loc_18001141A
0x1800113f5  mov     rcx, [rsp+180h+var_108]
0x1800113fa  test    rcx, rcx
0x1800113fd  jz      short loc_18001141A
0x1800113ff  mov     rax, [rcx]
0x180011402  lea     r9, [rbp+80h+var_100]
0x180011406  lea     r8, [rbp+80h+var_F8]
0x18001140a  lea     rdx, [rbp+80h+var_FC]
0x18001140e  mov     rax, [rax+28h]
0x180011412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011417  mov     r8d, eax
0x18001141a  mov     eax, cs:dword_180030000
0x180011420  cmp     eax, 5
0x180011423  jbe     short loc_1800114A2
0x180011425  mov     rdx, 400000000000h
0x18001142f  call    _tlgKeywordOn
0x180011434  test    al, al
0x180011436  jz      short loc_1800114A2
0x180011438  mov     eax, [rbp+80h+var_100]
0x18001143b  mov     [rbp+80h+var_E0], eax
0x18001143e  mov     eax, [rbp+80h+var_FC]
0x180011441  mov     [rbp+80h+var_DC], eax
0x180011444  mov     eax, [rbp+80h+var_F8]
0x180011447  mov     [rbp+80h+var_D8], eax
0x18001144a  mov     [rbp+80h+var_D4], r8d
0x18001144e  mov     eax, [rsp+180h+var_12C]
0x180011452  mov     [rsp+180h+var_120], eax
0x180011456  mov     qword ptr [rbp+80h+var_E8], 1000000h
0x18001145e  lea     rax, [rbp+80h+var_E0]
0x180011462  mov     [rsp+180h+var_138], rax
0x180011467  lea     rax, [rbp+80h+var_DC]
0x18001146b  mov     [rsp+180h+var_140], rax
0x180011470  lea     rax, [rbp+80h+var_D8]
0x180011474  mov     [rsp+180h+var_148], rax
0x180011479  lea     rax, [rbp+80h+var_D4]
0x18001147d  mov     [rsp+180h+var_150], rax
0x180011482  lea     rax, [rsp+180h+var_120]
0x180011487  mov     [rsp+180h+var_158], rax
0x18001148c  lea     rax, [rbp+80h+var_E8]
0x180011490  mov     [rsp+180h+ppv], rax
0x180011495  lea     rdx, byte_18002943F
0x18001149c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800114a1  nop
0x1800114a2  mov     rcx, [rsp+180h+var_108]
0x1800114a7  test    rcx, rcx
0x1800114aa  jz      short loc_1800114BE
0x1800114ac  mov     [rsp+180h+var_108], r15
0x1800114b1  mov     rax, [rcx]
0x1800114b4  mov     rax, [rax+10h]
0x1800114b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114bd  nop
0x1800114be  jmp     short loc_18001150D
0x1800114c0  mov     eax, cs:dword_180030000
0x1800114c6  cmp     eax, 5
0x1800114c9  jbe     short loc_18001150D
0x1800114cb  mov     rdx, 400000000000h
0x1800114d5  call    _tlgKeywordOn
0x1800114da  test    al, al
0x1800114dc  jz      short loc_18001150D
0x1800114de  mov     eax, [rsp+180h+var_12C]
0x1800114e2  mov     [rsp+180h+var_120], eax
0x1800114e6  mov     qword ptr [rbp+80h+var_E8], 1000000h
0x1800114ee  lea     rax, [rsp+180h+var_120]
0x1800114f3  mov     [rsp+180h+var_158], rax
0x1800114f8  lea     rax, [rbp+80h+var_E8]
0x1800114fc  mov     [rsp+180h+ppv], rax; int
0x180011501  lea     rdx, byte_1800291EF
0x180011508  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001150d  mov     [rsp+180h+var_118], r15
0x180011512  mov     rbx, [rbp+80h+var_F0]
0x180011516  mov     rax, [rbx]
0x180011519  mov     rdi, [rax]
0x18001151c  lea     rcx, [rsp+180h+var_118]
0x180011521  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011526  lea     r8, [rsp+180h+var_118]
0x18001152b  lea     rdx, _GUID_feea0525_d22c_4d46_b527_0b96066fc7db
0x180011532  mov     rcx, rbx
0x180011535  mov     rax, rdi
0x180011538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001153d  mov     ebx, eax
0x18001153f  test    eax, eax
0x180011541  jns     short loc_18001156E
0x180011543  mov     rcx, [rbp+88h]; this
0x18001154a  mov     r9d, eax; char *
0x18001154d  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180011554  mov     edx, 16Eh; void *
0x180011559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001155e  nop
0x18001155f  lea     rcx, [rsp+180h+var_118]
0x180011564  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011569  jmp     loc_180011339
0x18001156e  mov     [rsp+180h+var_110], r15
0x180011573  mov     rdi, [rsp+180h+var_118]
0x180011578  mov     rax, [rdi]
0x18001157b  mov     rbx, [rax+30h]
0x18001157f  lea     rcx, [rsp+180h+var_110]
0x180011584  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011589  lea     rdx, [rsp+180h+var_110]
0x18001158e  mov     rcx, rdi
0x180011591  mov     rax, rbx
0x180011594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011599  mov     ebx, eax
0x18001159b  test    eax, eax
0x18001159d  jns     short loc_1800115C7
0x18001159f  mov     edx, 171h; void *
0x1800115a4  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x1800115ab  mov     r9d, eax; char *
0x1800115ae  mov     rcx, [rbp+88h]; this
0x1800115b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115ba  nop
0x1800115bb  lea     rcx, [rsp+180h+var_110]
0x1800115c0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800115c5  jmp     short loc_18001155F
0x1800115c7  xorps   xmm0, xmm0
0x1800115ca  xor     eax, eax
0x1800115cc  movups  [rbp+80h+var_40], xmm0
0x1800115d0  mov     [rbp+80h+var_30], rax
0x1800115d4  mov     rcx, [rsp+180h+var_110]
0x1800115d9  mov     rax, [rcx]
0x1800115dc  lea     rdx, [rbp+80h+var_40]
0x1800115e0  mov     rax, [rax+30h]
0x1800115e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115e9  mov     ebx, eax
0x1800115eb  test    eax, eax
0x1800115ed  jns     short loc_1800115F6
0x1800115ef  mov     edx, 174h
0x1800115f4  jmp     short loc_1800115A4
0x1800115f6  mov     eax, cs:dword_180030000
0x1800115fc  cmp     eax, 5
0x1800115ff  jbe     short loc_180011631
0x180011601  mov     rax, qword ptr [rbp+80h+var_40+8]
0x180011605  mov     qword ptr [rbp+80h+var_E8], rax
0x180011609  mov     rax, qword ptr [rbp+80h+var_40]
0x18001160d  mov     [rsp+180h+var_108], rax
0x180011612  lea     rax, [rbp+80h+var_E8]
0x180011616  mov     [rsp+180h+var_158], rax
0x18001161b  lea     rax, [rsp+180h+var_108]
0x180011620  mov     [rsp+180h+ppv], rax
0x180011625  lea     rdx, word_180028C76
0x18001162c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180011631  lea     rdx, [rbp+80h+var_40]; struct Windows::Devices::Geolocation::BasicGeoposition *
0x180011635  mov     rcx, r14; this
0x180011638  call    ?WriteLocationToCache@CacheManager@LocationDataSource@@QEAAXAEAUBasicGeoposition@Geolocation@Devices@Windows@@@Z; LocationDataSource::CacheManager::WriteLocationToCache(Windows::Devices::Geolocation::BasicGeoposition &)
0x18001163d  cmp     [rsi+4Ch], r15b
0x180011641  jz      short loc_180011653
0x180011643  mov     rcx, rsi; this
0x180011646  call    ?UpdateMovementThreshold@LocationDataSource@@AEAAXXZ; LocationDataSource::UpdateMovementThreshold(void)
0x18001164b  mov     rcx, rsi; this
0x18001164e  call    ?ToggleActiveModeBasedOnRadius@LocationDataSource@@AEAAXXZ; LocationDataSource::ToggleActiveModeBasedOnRadius(void)
0x180011653  cmp     [rsi+4Dh], r15b
0x180011657  jz      short loc_180011663
0x180011659  mov     edx, [rsp+180h+var_12C]
0x18001165d  call    ?EnableServiceIfAppropriate@LocationDataSource@@QEAAXW4PositionSource@Geolocation@Devices@Windows@@@Z; LocationDataSource::EnableServiceIfAppropriate(Windows::Devices::Geolocation::PositionSource)
0x180011662  nop
0x180011663  lea     rcx, [rsp+180h+var_110]
0x180011668  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001166d  nop
0x18001166e  lea     rcx, [rsp+180h+var_118]
0x180011673  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011678  nop
0x180011679  lea     rcx, [rsp+180h+var_128]
0x18001167e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180011683  mov     ebx, r15d
0x180011686  lea     rcx, [rbp+80h+var_F0]
0x18001168a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001168f  mov     eax, ebx
0x180011691  mov     rcx, [rbp+80h+var_28]
0x180011695  xor     rcx, rsp; StackCookie
0x180011698  call    __security_check_cookie
0x18001169d  mov     rbx, [rsp+180h+arg_18]
0x1800116a5  add     rsp, 160h
0x1800116ac  pop     r15
0x1800116ae  pop     r14
0x1800116b0  pop     rdi
0x1800116b1  pop     rsi
0x1800116b2  pop     rbp
0x1800116b3  retn
```
