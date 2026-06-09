# TraceCurrentPosition(_GUID const &)

- ea: `0x18006d258`
- end: `0x18006d7df`
- name: `?TraceCurrentPosition@@YAXAEBU_GUID@@@Z`
- size: `1415`
- prototype: `void __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c4ae0`

## callees

- `0x18001c11c`
- `0x18006a448`
- `0x18006d258`
- `0x18006d7e8`
- `0x18006d830`
- `0x18006d880`
- `0x18006d92c`
- `0x18006d97c`
- `0x18006d9cc`
- `0x180084f50`
- `0x1800c4b00`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006d281`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006d281`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006d387`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006d387`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006d7b9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006d7b9`

## string_xrefs

- `0x18006d296`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d2fe`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d339`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d39c`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d3e6`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d423`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d45d`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d499`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d4fd`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d569`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d5a3`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d5f1`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d63f`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`
- `0x18006d684`: `onecoreuap\net\wcm\service\base\locationmanager\locationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall TraceCurrentPosition(const struct _GUID *a1)
{
  int v2; // eax
  __int64 v3; // rbx
  int v4; // eax
  int v5; // eax
  int ActivationFactory; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64); // rcx
  __int64 v27; // rcx
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-F8h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-B8h]
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+80h] [rbp-98h] BYREF
  __int64 v36; // [rsp+88h] [rbp-90h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-88h] BYREF
  __int64 v38; // [rsp+98h] [rbp-80h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v42; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-58h] BYREF
  __int128 v44; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v2 = RoInitialize(1);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v2,
        v29);
    v32 = 0;
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Devices.Geolocation.Geolocator",
      0x27u,
      0x26u);
    v3 = v31;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v4 = Windows::Foundation::ActivateInstance<Windows::Devices::Geolocation::IGeolocator>(v3, &v32);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v4,
        v29);
    v43 = 0;
    v5 = Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>::As<Windows::Devices::Geolocation::IGeolocatorWithScalarAccuracy>(
           &v32,
           (__int64)&v43);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v5,
        v29);
    v38 = 0;
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    ActivationFactory = RoGetActivationFactory(v31, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v38);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v29);
    v37 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v38 + 88LL))(v38, 100, &v37);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v7,
        v29);
    v41 = 0;
    v8 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IReference<unsigned int>>(&v37, (__int64)&v41);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v8,
        v29);
    v40 = 0;
    v9 = Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>::As<Windows::Devices::Geolocation::IGeolocatorWithScalarAccuracy>(
           &v32,
           (__int64)&v40);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v9,
        v29);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 56LL))(v40, v41);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v10,
        v29);
    v36 = 0;
    v11 = v32;
    v12 = (*v32)[14];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64, __int64, __int64 *))v12)(
            v11,
            30000000000LL,
            300000000,
            &v36);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v13,
        v29);
    v35 = 0;
    wil::wait_for_completion<Windows::Devices::Geolocation::Geoposition *,Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeoposition>>(
      &v35,
      v36);
    v33 = 0;
    v14 = v35;
    v15 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v35 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v16 = v15(v14, &v33);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v16,
        v29);
    v39 = 0;
    v17 = Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeocoordinate>::As<Windows::Devices::Geolocation::IGeocoordinateWithPoint>(
            &v33,
            (__int64)&v39);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v17,
        v29);
    v34 = 0;
    v18 = v39;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v20 = v19(v18, &v34);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v20,
        v29);
    v44 = 0;
    v45 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v34 + 48LL))(v34, &v44);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v21,
        v29);
    v42 = 0;
    v22 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*v33)[9])(v33, &v42);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
        (const char *)(unsigned int)v22,
        v29);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF__guid_gggg(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v23, v24, a1, v44, *((_QWORD *)&v44 + 1), v45, v42);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v25 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v26 = v37;
    if ( v37 )
    {
      v37 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v26)[2])(v26);
    }
    v27 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    RoUninitialize();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\locationmanager\\locationmanager.cpp",
      v28);
  }
}

```

## disassembly

```asm
0x18006d258  push    rbx
0x18006d25a  push    rsi
0x18006d25b  push    rdi
0x18006d25c  push    r14
0x18006d25e  sub     rsp, 0F8h
0x18006d265  mov     rax, cs:__security_cookie
0x18006d26c  xor     rax, rsp
0x18006d26f  mov     [rsp+118h+var_38], rax
0x18006d277  mov     rsi, rcx
0x18006d27a  xor     r14d, r14d
0x18006d27d  lea     ecx, [r14+1]
0x18006d281  call    cs:__imp_RoInitialize
0x18006d287  mov     rcx, [rsp+118h]; this
0x18006d28f  test    eax, eax
0x18006d291  jns     short loc_18006D2A7
0x18006d293  mov     r9d, eax; char *
0x18006d296  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d29d  mov     edx, 85h; void *
0x18006d2a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d2a7  mov     [rsp+118h+var_D7], 1
0x18006d2ac  mov     [rsp+118h+var_B0], r14
0x18006d2b1  mov     [rsp+118h+var_B8], r14
0x18006d2b6  mov     r9d, 26h ; '&'; unsigned int
0x18006d2bc  lea     r8d, [r9+1]; unsigned int
0x18006d2c0  lea     rdx, ?RuntimeClass_Windows_Devices_Geolocation_Geolocator@@3QBGB; "Windows.Devices.Geolocation.Geolocator"
0x18006d2c7  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x18006d2cc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006d2d1  nop
0x18006d2d2  mov     rbx, [rsp+118h+var_B8]
0x18006d2d7  lea     rcx, [rsp+118h+var_B0]
0x18006d2dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d2e1  lea     rdx, [rsp+118h+var_B0]
0x18006d2e6  mov     rcx, rbx
0x18006d2e9  call    ??$ActivateInstance@UIGeolocator@Geolocation@Devices@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeolocator@Geolocation@Devices@1@@Z; Windows::Foundation::ActivateInstance<Windows::Devices::Geolocation::IGeolocator>(HSTRING__ *,Windows::Devices::Geolocation::IGeolocator * *)
0x18006d2ee  nop
0x18006d2ef  mov     rcx, [rsp+118h]; this
0x18006d2f7  test    eax, eax
0x18006d2f9  jns     short loc_18006D310
0x18006d2fb  mov     r9d, eax; char *
0x18006d2fe  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d305  mov     edx, 8Ch; void *
0x18006d30a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d310  mov     [rsp+118h+var_58], r14
0x18006d318  lea     rdx, [rsp+118h+var_58]
0x18006d320  lea     rcx, [rsp+118h+var_B0]
0x18006d325  call    ??$As@UIGeolocatorWithScalarAccuracy@Geolocation@Devices@Windows@@@?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIGeolocatorWithScalarAccuracy@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>::As<Windows::Devices::Geolocation::IGeolocatorWithScalarAccuracy>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocatorWithScalarAccuracy>>)
0x18006d32a  mov     rcx, [rsp+118h]; this
0x18006d332  test    eax, eax
0x18006d334  jns     short loc_18006D34A
0x18006d336  mov     r9d, eax; char *
0x18006d339  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d340  mov     edx, 8Fh; void *
0x18006d345  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d34a  mov     [rsp+118h+var_80], r14
0x18006d352  mov     [rsp+118h+var_B8], r14
0x18006d357  mov     r9d, 20h ; ' '; unsigned int
0x18006d35d  lea     r8d, [r9+1]; unsigned int
0x18006d361  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18006d368  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x18006d36d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006d372  nop
0x18006d373  lea     r8, [rsp+118h+var_80]
0x18006d37b  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18006d382  mov     rcx, [rsp+118h+var_B8]
0x18006d387  call    cs:__imp_RoGetActivationFactory
0x18006d38d  mov     rcx, [rsp+118h]; this
0x18006d395  test    eax, eax
0x18006d397  jns     short loc_18006D3AE
0x18006d399  mov     r9d, eax; char *
0x18006d39c  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d3a3  mov     edx, 93h; void *
0x18006d3a8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d3ae  mov     [rsp+118h+var_88], r14
0x18006d3b6  mov     rcx, [rsp+118h+var_80]
0x18006d3be  mov     rax, [rcx]
0x18006d3c1  lea     r8, [rsp+118h+var_88]
0x18006d3c9  mov     edx, 64h ; 'd'
0x18006d3ce  mov     rax, [rax+58h]
0x18006d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d3d7  mov     rcx, [rsp+118h]; this
0x18006d3df  test    eax, eax
0x18006d3e1  jns     short loc_18006D3F7
0x18006d3e3  mov     r9d, eax; char *
0x18006d3e6  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d3ed  mov     edx, 96h; void *
0x18006d3f2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d3f7  mov     [rsp+118h+var_68], r14
0x18006d3ff  lea     rdx, [rsp+118h+var_68]
0x18006d407  lea     rcx, [rsp+118h+var_88]
0x18006d40f  call    ??$As@U?$IReference@I@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IReference@I@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IReference<uint>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IReference<uint>>>)
0x18006d414  mov     rcx, [rsp+118h]; this
0x18006d41c  test    eax, eax
0x18006d41e  jns     short loc_18006D434
0x18006d420  mov     r9d, eax; char *
0x18006d423  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d42a  mov     edx, 99h; void *
0x18006d42f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d434  mov     [rsp+118h+var_70], r14
0x18006d43c  lea     rdx, [rsp+118h+var_70]
0x18006d444  lea     rcx, [rsp+118h+var_B0]
0x18006d449  call    ??$As@UIGeolocatorWithScalarAccuracy@Geolocation@Devices@Windows@@@?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIGeolocatorWithScalarAccuracy@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>::As<Windows::Devices::Geolocation::IGeolocatorWithScalarAccuracy>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocatorWithScalarAccuracy>>)
0x18006d44e  mov     rcx, [rsp+118h]; this
0x18006d456  test    eax, eax
0x18006d458  jns     short loc_18006D46E
0x18006d45a  mov     r9d, eax; char *
0x18006d45d  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d464  mov     edx, 9Ch; void *
0x18006d469  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d46e  mov     rcx, [rsp+118h+var_70]
0x18006d476  mov     rax, [rcx]
0x18006d479  mov     rdx, [rsp+118h+var_68]
0x18006d481  mov     rax, [rax+38h]
0x18006d485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d48a  mov     rcx, [rsp+118h]; this
0x18006d492  test    eax, eax
0x18006d494  jns     short loc_18006D4AA
0x18006d496  mov     r9d, eax; char *
0x18006d499  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d4a0  mov     edx, 9Dh; void *
0x18006d4a5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d4aa  mov     [rsp+118h+var_90], r14
0x18006d4b2  mov     rdi, [rsp+118h+var_B0]
0x18006d4b7  mov     rax, [rdi]
0x18006d4ba  mov     rbx, [rax+70h]
0x18006d4be  lea     rcx, [rsp+118h+var_90]
0x18006d4c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d4cb  mov     rdx, 6FC23AC00h
0x18006d4d5  lea     r9, [rsp+118h+var_90]
0x18006d4dd  mov     r8d, 11E1A300h
0x18006d4e3  mov     rcx, rdi
0x18006d4e6  mov     rax, rbx
0x18006d4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d4ee  mov     rcx, [rsp+118h]; this
0x18006d4f6  test    eax, eax
0x18006d4f8  jns     short loc_18006D50E
0x18006d4fa  mov     r9d, eax; char *
0x18006d4fd  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d504  mov     edx, 0A7h; void *
0x18006d509  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d50e  mov     [rsp+118h+var_98], r14
0x18006d516  mov     rdx, [rsp+118h+var_90]
0x18006d51e  lea     rcx, [rsp+118h+var_98]
0x18006d526  call    ??$wait_for_completion@PEAVGeoposition@Geolocation@Devices@Windows@@V?$ComPtr@UIGeoposition@Geolocation@Devices@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIGeoposition@Geolocation@Devices@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Devices::Geolocation::Geoposition *,Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeoposition>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS)
0x18006d52b  nop
0x18006d52c  mov     [rsp+118h+var_A8], r14
0x18006d531  mov     rdi, [rsp+118h+var_98]
0x18006d539  mov     rax, [rdi]
0x18006d53c  mov     rbx, [rax+30h]
0x18006d540  lea     rcx, [rsp+118h+var_A8]
0x18006d545  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d54a  lea     rdx, [rsp+118h+var_A8]
0x18006d54f  mov     rcx, rdi
0x18006d552  mov     rax, rbx
0x18006d555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d55a  mov     rcx, [rsp+118h]; this
0x18006d562  test    eax, eax
0x18006d564  jns     short loc_18006D57A
0x18006d566  mov     r9d, eax; char *
0x18006d569  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d570  mov     edx, 0ACh; void *
0x18006d575  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d57a  mov     [rsp+118h+var_78], r14
0x18006d582  lea     rdx, [rsp+118h+var_78]
0x18006d58a  lea     rcx, [rsp+118h+var_A8]
0x18006d58f  call    ??$As@UIGeocoordinateWithPoint@Geolocation@Devices@Windows@@@?$ComPtr@UIGeocoordinate@Geolocation@Devices@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIGeocoordinateWithPoint@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeocoordinate>::As<Windows::Devices::Geolocation::IGeocoordinateWithPoint>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeocoordinateWithPoint>>)
0x18006d594  mov     rcx, [rsp+118h]; this
0x18006d59c  test    eax, eax
0x18006d59e  jns     short loc_18006D5B4
0x18006d5a0  mov     r9d, eax; char *
0x18006d5a3  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d5aa  mov     edx, 0AEh; void *
0x18006d5af  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d5b4  mov     [rsp+118h+var_A0], r14
0x18006d5b9  mov     rdi, [rsp+118h+var_78]
0x18006d5c1  mov     rax, [rdi]
0x18006d5c4  mov     rbx, [rax+30h]
0x18006d5c8  lea     rcx, [rsp+118h+var_A0]
0x18006d5cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d5d2  lea     rdx, [rsp+118h+var_A0]
0x18006d5d7  mov     rcx, rdi
0x18006d5da  mov     rax, rbx
0x18006d5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5e2  mov     rcx, [rsp+118h]; this
0x18006d5ea  test    eax, eax
0x18006d5ec  jns     short loc_18006D602
0x18006d5ee  mov     r9d, eax; char *
0x18006d5f1  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d5f8  mov     edx, 0B0h; void *
0x18006d5fd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d602  xorps   xmm0, xmm0
0x18006d605  xor     eax, eax
0x18006d607  movups  [rsp+118h+var_50], xmm0
0x18006d60f  mov     [rsp+118h+var_40], rax
0x18006d617  mov     rcx, [rsp+118h+var_A0]
0x18006d61c  mov     rax, [rcx]
0x18006d61f  lea     rdx, [rsp+118h+var_50]
0x18006d627  mov     rax, [rax+30h]
0x18006d62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d630  mov     rcx, [rsp+118h]; this
0x18006d638  test    eax, eax
0x18006d63a  jns     short loc_18006D650
0x18006d63c  mov     r9d, eax; char *
0x18006d63f  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d646  mov     edx, 0B3h; void *
0x18006d64b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d650  xorps   xmm0, xmm0
0x18006d653  movsd   [rsp+118h+var_60], xmm0
0x18006d65c  mov     rcx, [rsp+118h+var_A8]
0x18006d661  mov     rax, [rcx]
0x18006d664  lea     rdx, [rsp+118h+var_60]
0x18006d66c  mov     rax, [rax+48h]
0x18006d670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d675  mov     rcx, [rsp+118h]; this
0x18006d67d  test    eax, eax
0x18006d67f  jns     short loc_18006D695
0x18006d681  mov     r9d, eax; char *
0x18006d684  lea     r8, aOnecoreuapNetW_38; "onecoreuap\\net\\wcm\\service\\base\\lo"...
0x18006d68b  mov     edx, 0B5h; void *
0x18006d690  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006d695  lea     rax, WPP_GLOBAL_Control
0x18006d69c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d6a3  cmp     rcx, rax
0x18006d6a6  jz      short loc_18006D6EC
0x18006d6a8  cmp     byte ptr [rcx+19h], 4
0x18006d6ac  jb      short loc_18006D6EC
0x18006d6ae  test    byte ptr [rcx+1Ch], 1
0x18006d6b2  jz      short loc_18006D6EC
0x18006d6b4  movsd   xmm0, [rsp+118h+var_60]
0x18006d6bd  movsd   [rsp+118h+var_E0], xmm0
0x18006d6c3  movups  xmm1, [rsp+118h+var_50+8]
0x18006d6cb  movups  [rsp+118h+var_F0], xmm1
0x18006d6d0  movsd   xmm1, qword ptr [rsp+118h+var_50]
0x18006d6d9  movsd   [rsp+118h+var_F8], xmm1
0x18006d6df  mov     r9, rsi
0x18006d6e2  mov     rcx, [rcx+10h]
0x18006d6e6  call    WPP_SF__guid_gggg
0x18006d6eb  nop
0x18006d6ec  lea     rcx, [rsp+118h+var_A0]
0x18006d6f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d6f6  nop
0x18006d6f7  lea     rcx, [rsp+118h+var_78]
0x18006d6ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d704  nop
0x18006d705  lea     rcx, [rsp+118h+var_A8]
0x18006d70a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d70f  nop
0x18006d710  mov     rcx, [rsp+118h+var_98]
0x18006d718  test    rcx, rcx
0x18006d71b  jz      short loc_18006D732
0x18006d71d  mov     [rsp+118h+var_98], r14
0x18006d725  mov     rax, [rcx]
0x18006d728  mov     rax, [rax+10h]
0x18006d72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d731  nop
0x18006d732  lea     rcx, [rsp+118h+var_90]
0x18006d73a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d73f  nop
0x18006d740  lea     rcx, [rsp+118h+var_70]
0x18006d748  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d74d  nop
0x18006d74e  lea     rcx, [rsp+118h+var_68]
0x18006d756  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d75b  nop
0x18006d75c  mov     rcx, [rsp+118h+var_88]
0x18006d764  test    rcx, rcx
0x18006d767  jz      short loc_18006D77E
0x18006d769  mov     [rsp+118h+var_88], r14
0x18006d771  mov     rax, [rcx]
0x18006d774  mov     rax, [rax+10h]
0x18006d778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d77d  nop
0x18006d77e  mov     rcx, [rsp+118h+var_80]
0x18006d786  test    rcx, rcx
0x18006d789  jz      short loc_18006D7A0
0x18006d78b  mov     [rsp+118h+var_80], r14
0x18006d793  mov     rax, [rcx]
0x18006d796  mov     rax, [rax+10h]
0x18006d79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d79f  nop
0x18006d7a0  lea     rcx, [rsp+118h+var_58]
0x18006d7a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d7ad  nop
0x18006d7ae  lea     rcx, [rsp+118h+var_B0]
0x18006d7b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d7b8  nop
0x18006d7b9  call    cs:__imp_RoUninitialize
0x18006d7bf  nop
0x18006d7c0  jmp     short $+2
0x18006d7c2  mov     rcx, [rsp+118h+var_38]
0x18006d7ca  xor     rcx, rsp; StackCookie
0x18006d7cd  call    __security_check_cookie
0x18006d7d2  add     rsp, 0F8h
0x18006d7d9  pop     r14
0x18006d7db  pop     rdi
0x18006d7dc  pop     rsi
0x18006d7dd  pop     rbx
0x18006d7de  retn
```
