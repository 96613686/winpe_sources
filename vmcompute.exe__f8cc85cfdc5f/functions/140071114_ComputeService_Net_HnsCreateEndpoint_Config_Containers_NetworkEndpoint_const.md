# ComputeService::Net::HnsCreateEndpoint(Config::Containers::NetworkEndpoint const &)

- ea: `0x140071114`
- end: `0x140071622`
- name: `?HnsCreateEndpoint@Net@ComputeService@@YA?AU_GUID@@AEBUNetworkEndpoint@Containers@Config@@@Z`
- size: `1294`
- prototype: `struct _GUID *__fastcall(ComputeService::Net *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr, const struct Config::Containers::NetworkEndpoint *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14028a680`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001bc28`
- `0x14001bce0`
- `0x14002450c`
- `0x140026a3c`
- `0x14002d7f0`
- `0x1400421f0`
- `0x140042e70`
- `0x14005bb24`
- `0x140070e48`
- `0x140071114`
- `0x140071628`
- `0x140071650`
- `0x140071d04`
- `0x140073a74`
- `0x1400c17a4`
- `0x1400c40e0`
- `0x1400ee418`
- `0x1400eee68`
- `0x1401177b4`
- `0x140124ae0`
- `0x1401332f0`
- `0x140219c68`
- `0x140219e4c`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400715eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400715eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400711ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400711ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14007114f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14007114f`

## string_xrefs

- `0x140071169`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400711c7`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x14007150a`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140071598`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
struct _GUID *__fastcall ComputeService::Net::HnsCreateEndpoint(
        ComputeService::Net *this,
        struct _GUID *__return_ptr retstr,
        const struct Config::Containers::NetworkEndpoint *a3)
{
  HRESULT v5; // eax
  HRESULT v6; // eax
  __int128 v7; // xmm0
  unsigned __int16 *v8; // r8
  unsigned __int16 v9; // r9
  const unsigned __int8 *v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rdi
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, const wchar_t *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v15; // r9
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  const char *v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[24]; // [rsp+58h] [rbp-A8h] BYREF
  int v26[2]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v27; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v28[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v31; // [rsp+D0h] [rbp-30h]
  _BYTE v32[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v33[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v34; // [rsp+108h] [rbp+8h]
  __int64 v35; // [rsp+110h] [rbp+10h]
  unsigned __int8 *v36[4]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v37[32]; // [rsp+138h] [rbp+38h] BYREF
  __int16 v38; // [rsp+158h] [rbp+58h]
  char v39; // [rsp+15Ah] [rbp+5Ah]
  int v40; // [rsp+15Bh] [rbp+5Bh]
  char v41; // [rsp+15Fh] [rbp+5Fh]
  _BYTE v42[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v43[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v44[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v45[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v46[33]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v47; // [rsp+201h] [rbp+101h]
  __int16 v48; // [rsp+205h] [rbp+105h]
  char v49; // [rsp+207h] [rbp+107h]
  _BYTE v50[33]; // [rsp+208h] [rbp+108h] BYREF
  int v51; // [rsp+229h] [rbp+129h]
  __int16 v52; // [rsp+22Dh] [rbp+12Dh]
  char v53; // [rsp+22Fh] [rbp+12Fh]
  _BYTE v54[33]; // [rsp+230h] [rbp+130h] BYREF
  int v55; // [rsp+251h] [rbp+151h]
  __int16 v56; // [rsp+255h] [rbp+155h]
  char v57; // [rsp+257h] [rbp+157h]
  __int128 v58; // [rsp+258h] [rbp+158h]
  char v59; // [rsp+268h] [rbp+168h]
  int v60; // [rsp+269h] [rbp+169h]
  __int16 v61; // [rsp+26Dh] [rbp+16Dh]
  char v62; // [rsp+26Fh] [rbp+16Fh]
  _BYTE v63[24]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v64; // [rsp+288h] [rbp+188h]
  __int64 v65; // [rsp+298h] [rbp+198h]
  _BYTE v66[24]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v67; // [rsp+2B8h] [rbp+1B8h]
  int v68; // [rsp+2BAh] [rbp+1BAh]
  __int16 v69; // [rsp+2BEh] [rbp+1BEh]
  __int128 v70; // [rsp+2C0h] [rbp+1C0h]
  __int64 v71; // [rsp+2D0h] [rbp+1D0h]
  __int64 v72; // [rsp+2D8h] [rbp+1D8h]
  _BYTE v73[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v74[32]; // [rsp+300h] [rbp+200h] BYREF
  int v75; // [rsp+320h] [rbp+220h]
  __int128 v76; // [rsp+324h] [rbp+224h]
  int v77; // [rsp+334h] [rbp+234h]
  _BYTE v78[24]; // [rsp+338h] [rbp+238h] BYREF
  __int64 v79; // [rsp+350h] [rbp+250h]
  char v80[48]; // [rsp+360h] [rbp+260h] BYREF
  __int128 v81; // [rsp+390h] [rbp+290h]
  wil::details::in1diag3 *retaddr; // [rsp+678h] [rbp+578h]

  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  BYTE1(v22[0]) = 1;
  v27 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v6 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v27);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v6,
      ppva);
  v29 = 0;
  std::wstring::wstring(v30);
  v31 = 0;
  std::wstring::wstring(v32);
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v33);
  std::wstring::wstring(v36);
  std::wstring::wstring(v37);
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::wstring(v42);
  std::wstring::wstring(v43);
  std::wstring::wstring(v44);
  std::wstring::wstring(v45);
  std::wstring::wstring(v46);
  v46[32] = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  std::wstring::wstring(v50);
  v50[32] = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::wstring(v54);
  v54[32] = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v7 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  *(double *)&v7 = std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v63);
  v64 = v7;
  v65 = 0;
  *(double *)&v7 = std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v66);
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = v7;
  v71 = 0;
  v72 = 0;
  std::wstring::wstring(v73);
  std::wstring::wstring(v74);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(v78);
  v79 = 0;
  std::wstring::operator=(v30, &retstr[1]);
  v31 = retstr[7];
  std::wstring::operator=(v37, &retstr[5]);
  std::wstring::operator=(v36, &retstr[3]);
  if ( v36[2] )
  {
    v23 = *(_OWORD *)std::wstring::operator std::basic_string_view<unsigned short>(v36, v24);
    if ( !(unsigned __int8)MacAddressUtils::Details::ParseMacAddressString(&v23, (char *)v22 + 4, 0) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecore\\vm\\inc\\MacAddressUtils.h",
        (const char *)0x80070057LL,
        ppva);
    std::wstring::resize(v36);
    v10 = (const unsigned __int8 *)v36;
    if ( v36[3] > (unsigned __int8 *)7 )
      v10 = v36[0];
    MacAddressUtils::Details::WriteSeparatedMacAddressString((MacAddressUtils::Details *)((char *)v22 + 4), v10, v8, v9);
    std::wstring::resize(v36);
  }
  v11 = *(_QWORD *)&retstr[8].Data1;
  v12 = *(_QWORD *)retstr[8].Data4;
  while ( v11 != v12 )
  {
    std::wstring::wstring(v24);
    if ( v34 == v35 )
    {
      std::vector<Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>>::_Emplace_reallocate<Marshal::RawJson>(
        v33,
        v34,
        v24);
    }
    else
    {
      Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
        v34,
        v24);
      v34 += 64;
    }
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
    v11 += 32;
  }
  Marshal::ToJson<Config::Containers::HNS::HNSEndpoint &,>(v28, &v29);
  *(_QWORD *)v26 = 0;
  v13 = v27;
  v14 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD *))(*(_QWORD *)v27 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v26,
    0);
  v15 = v28;
  if ( v28[3] > 7u )
    v15 = (_QWORD *)v28[0];
  v16 = v14(v13, L"POST", L"/endpoints/", v15);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v16,
      (int)v26);
  Config::Containers::HNS::HNSSingleEndpointResponse::HNSSingleEndpointResponse((Config::Containers::HNS::HNSSingleEndpointResponse *)v80);
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(*(_QWORD *)v26 + 2 * v17) );
  *(_QWORD *)&v23 = *(_QWORD *)v26;
  *((_QWORD *)&v23 + 1) = v17;
  v18 = Marshal::FromJson<Config::Containers::HNS::HNSSingleEndpointResponse,>(v24, &v23, v80);
  Marshal::ThrowOnUnmarshalError(v18, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v25);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x178,
    (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
    (const char *)0x800704CFLL,
    v80[0],
    (bool)"Error creating HNS endpoints",
    v22[0]);
  *(_OWORD *)this = v81;
  Config::Containers::HNS::HNSSingleEndpointResponse::~HNSSingleEndpointResponse((Config::Containers::HNS::HNSSingleEndpointResponse *)v80);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v26);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v28);
  Config::Containers::HNS::HNSEndpoint::~HNSEndpoint((Config::Containers::HNS::HNSEndpoint *)&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  CoUninitialize();
  return (struct _GUID *)this;
}

```

## disassembly

```asm
0x140071114  mov     [rsp-8+arg_0], rbx
0x140071119  mov     [rsp-8+arg_10], rsi
0x14007111e  push    rbp
0x14007111f  push    rdi
0x140071120  push    r14
0x140071122  lea     rbp, [rsp-560h]
0x14007112a  sub     rsp, 660h
0x140071131  mov     rax, cs:__security_cookie
0x140071138  xor     rax, rsp
0x14007113b  mov     [rbp+570h+var_20], rax
0x140071142  mov     rdi, rdx
0x140071145  mov     rsi, rcx
0x140071148  xor     r14d, r14d
0x14007114b  xor     edx, edx; dwCoInit
0x14007114d  xor     ecx, ecx; pvReserved
0x14007114f  call    cs:__imp_CoInitializeEx
0x140071156  nop     dword ptr [rax+rax+00h]
0x14007115b  mov     rcx, [rbp+578h]; this
0x140071162  test    eax, eax
0x140071164  jns     short loc_14007117B
0x140071166  mov     r9d, eax; char *
0x140071169  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140071170  mov     edx, 159h; void *
0x140071175  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007117b  mov     [rsp+670h+var_63F], 1
0x140071180  mov     [rsp+670h+var_5F8], r14
0x140071185  lea     rcx, [rsp+670h+var_5F8]
0x14007118a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14007118f  lea     rax, [rsp+670h+var_5F8]
0x140071194  mov     [rsp+670h+ppv], rax; int
0x140071199  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x1400711a0  xor     edx, edx; pUnkOuter
0x1400711a2  lea     r8d, [rdx+17h]; dwClsContext
0x1400711a6  lea     rcx, rclsid; rclsid
0x1400711ad  call    cs:__imp_CoCreateInstance
0x1400711b4  nop     dword ptr [rax+rax+00h]
0x1400711b9  mov     rcx, [rbp+578h]; this
0x1400711c0  test    eax, eax
0x1400711c2  jns     short loc_1400711D9
0x1400711c4  mov     r9d, eax; char *
0x1400711c7  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400711ce  mov     edx, 15Dh; void *
0x1400711d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400711d9  xorps   xmm0, xmm0
0x1400711dc  movups  [rbp+570h+var_5D0], xmm0
0x1400711e0  lea     rcx, [rbp+570h+var_5C0]; void *
0x1400711e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400711e9  xorps   xmm0, xmm0
0x1400711ec  movups  [rbp+570h+var_5A0], xmm0
0x1400711f0  lea     rcx, [rbp+570h+var_590]; void *
0x1400711f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400711f9  lea     rcx, [rbp+570h+var_570]
0x1400711fd  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x140071202  lea     rcx, [rbp+570h+var_558]; void *
0x140071206  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14007120b  lea     rcx, [rbp+570h+var_538]; void *
0x14007120f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071214  mov     [rbp+570h+var_518], r14w
0x140071219  mov     [rbp+570h+var_516], r14b
0x14007121d  xor     eax, eax
0x14007121f  mov     [rbp+570h+var_515], eax
0x140071222  mov     [rbp+570h+var_511], al
0x140071225  lea     rcx, [rbp+570h+var_510]; void *
0x140071229  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14007122e  lea     rcx, [rbp+570h+var_4F0]; void *
0x140071235  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14007123a  lea     rcx, [rbp+570h+var_4D0]; void *
0x140071241  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071246  lea     rcx, [rbp+570h+var_4B0]; void *
0x14007124d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071252  lea     rcx, [rbp+570h+var_490]; void *
0x140071259  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14007125e  mov     [rbp+570h+var_470], r14b
0x140071265  xor     eax, eax
0x140071267  mov     [rbp+570h+var_46F], eax
0x14007126d  mov     [rbp+570h+var_46B], ax
0x140071274  mov     [rbp+570h+var_469], al
0x14007127a  lea     rcx, [rbp+570h+var_468]; void *
0x140071281  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071286  mov     [rbp+570h+var_448], r14b
0x14007128d  xor     eax, eax
0x14007128f  mov     [rbp+570h+var_447], eax
0x140071295  mov     [rbp+570h+var_443], ax
0x14007129c  mov     [rbp+570h+var_441], al
0x1400712a2  lea     rcx, [rbp+570h+var_440]; void *
0x1400712a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400712ae  mov     [rbp+570h+var_420], r14b
0x1400712b5  xor     eax, eax
0x1400712b7  mov     [rbp+570h+var_41F], eax
0x1400712bd  mov     [rbp+570h+var_41B], ax
0x1400712c4  mov     [rbp+570h+var_419], al
0x1400712ca  xorps   xmm0, xmm0
0x1400712cd  movups  [rbp+570h+var_418], xmm0
0x1400712d4  mov     [rbp+570h+var_408], r14b
0x1400712db  mov     [rbp+570h+var_407], eax
0x1400712e1  mov     [rbp+570h+var_403], ax
0x1400712e8  mov     [rbp+570h+var_401], al
0x1400712ee  lea     rcx, [rbp+570h+var_400]
0x1400712f5  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400712fa  movups  [rbp+570h+var_3E8], xmm0
0x140071301  mov     [rbp+570h+var_3D8], r14
0x140071308  lea     rcx, [rbp+570h+var_3D0]
0x14007130f  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x140071314  mov     [rbp+570h+var_3B8], r14w
0x14007131c  xor     eax, eax
0x14007131e  mov     [rbp+570h+var_3B6], eax
0x140071324  mov     [rbp+570h+var_3B2], ax
0x14007132b  movups  [rbp+570h+var_3B0], xmm0
0x140071332  mov     [rbp+570h+var_3A0], r14
0x140071339  mov     [rbp+570h+var_398], r14
0x140071340  lea     rcx, [rbp+570h+var_390]; void *
0x140071347  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14007134c  lea     rcx, [rbp+570h+var_370]; void *
0x140071353  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071358  mov     [rbp+570h+var_350], r14d
0x14007135f  xor     eax, eax
0x140071361  xorps   xmm0, xmm0
0x140071364  movups  [rbp+570h+var_34C], xmm0
0x14007136b  mov     [rbp+570h+var_33C], eax
0x140071371  lea     rcx, [rbp+570h+var_338]
0x140071378  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x14007137d  mov     [rbp+570h+var_320], r14
0x140071384  lea     rdx, [rdi+10h]
0x140071388  lea     rcx, [rbp+570h+var_5C0]
0x14007138c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140071391  movups  xmm0, xmmword ptr [rdi+70h]
0x140071395  movdqu  [rbp+570h+var_5A0], xmm0
0x14007139a  lea     rdx, [rdi+50h]
0x14007139e  lea     rcx, [rbp+570h+var_538]
0x1400713a2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400713a7  lea     rdx, [rdi+30h]
0x1400713ab  lea     rcx, [rbp+570h+var_558]
0x1400713af  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400713b4  cmp     [rbp+570h+var_548], r14
0x1400713b8  jz      loc_14007143F
0x1400713be  lea     rdx, [rsp+670h+var_620]
0x1400713c3  lea     rcx, [rbp+570h+var_558]
0x1400713c7  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x1400713cc  movups  xmm0, xmmword ptr [rax]
0x1400713cf  movdqu  [rsp+670h+var_630], xmm0
0x1400713d5  mov     rbx, [rbp+578h]
0x1400713dc  xor     r8d, r8d
0x1400713df  lea     rdx, [rsp+670h+var_63C]
0x1400713e4  lea     rcx, [rsp+670h+var_630]
0x1400713e9  call    ?ParseMacAddressString@Details@MacAddressUtils@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAEG@Z; MacAddressUtils::Details::ParseMacAddressString(std::basic_string_view<ushort>,uchar *,ushort)
0x1400713ee  test    al, al
0x1400713f0  jnz     short loc_14007140D
0x1400713f2  mov     r9d, 80070057h; char *
0x1400713f8  lea     r8, aOnecoreVmIncMa; "onecore\\vm\\inc\\MacAddressUtils.h"
0x1400713ff  mov     edx, 101h; void *
0x140071404  mov     rcx, rbx; this
0x140071407  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007140d  mov     edx, 12h
0x140071412  lea     rcx, [rbp+570h+var_558]
0x140071416  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14007141b  lea     rdx, [rbp+570h+var_558]
0x14007141f  cmp     [rbp+570h+var_540], 7
0x140071424  cmova   rdx, [rbp+570h+var_558]; unsigned __int8 *
0x140071429  lea     rcx, [rsp+670h+var_63C]; this
0x14007142e  call    ?WriteSeparatedMacAddressString@Details@MacAddressUtils@@YA_KPEBEPEAGG@Z; MacAddressUtils::Details::WriteSeparatedMacAddressString(uchar const *,ushort *,ushort)
0x140071433  mov     rdx, rax
0x140071436  lea     rcx, [rbp+570h+var_558]
0x14007143a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14007143f  mov     rbx, [rdi+80h]
0x140071446  mov     rdi, [rdi+88h]
0x14007144d  jmp     short loc_14007149B
0x14007144f  mov     rdx, rbx
0x140071452  lea     rcx, [rsp+670h+var_620]
0x140071457  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007145c  nop
0x14007145d  mov     rax, [rbp+570h+var_568]
0x140071461  cmp     rax, [rbp+570h+var_560]
0x140071465  jz      short loc_14007147B
0x140071467  lea     rdx, [rsp+670h+var_620]
0x14007146c  mov     rcx, rax
0x14007146f  call    ??$?0URawJson@Marshal@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@$$QEAURawJson@1@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(Marshal::RawJson &&)
0x140071474  add     [rbp+570h+var_568], 40h ; '@'
0x140071479  jmp     short loc_14007148D
0x14007147b  lea     r8, [rsp+670h+var_620]
0x140071480  mov     rdx, rax
0x140071483  lea     rcx, [rbp+570h+var_570]
0x140071487  call    ??$_Emplace_reallocate@URawJson@Marshal@@@?$vector@V?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@V?$allocator@V?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@@std@@@std@@AEAAPEAV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAV23@$$QEAURawJson@3@@Z; std::vector<Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>>::_Emplace_reallocate<Marshal::RawJson>(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> * const,Marshal::RawJson &&)
0x14007148c  nop
0x14007148d  lea     rcx, [rsp+670h+var_620]; this
0x140071492  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140071497  add     rbx, 20h ; ' '
0x14007149b  cmp     rbx, rdi
0x14007149e  jnz     short loc_14007144F
0x1400714a0  lea     rdx, [rbp+570h+var_5D0]
0x1400714a4  lea     rcx, [rbp+570h+var_5F0]
0x1400714a8  call    ??$ToJson@AEAUHNSEndpoint@HNS@Containers@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUHNSEndpoint@HNS@Containers@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Containers::HNS::HNSEndpoint &,>(Config::Containers::HNS::HNSEndpoint &,Marshal::MarshalFlags)
0x1400714ad  nop
0x1400714ae  mov     qword ptr [rsp+670h+var_600], r14
0x1400714b3  mov     rdi, [rsp+670h+var_5F8]
0x1400714b8  mov     rax, [rdi]
0x1400714bb  mov     rbx, [rax+38h]
0x1400714bf  xor     edx, edx
0x1400714c1  lea     rcx, [rsp+670h+var_600]
0x1400714c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400714cb  lea     r9, [rbp+570h+var_5F0]
0x1400714cf  cmp     [rbp+570h+var_5D8], 7
0x1400714d4  cmova   r9, [rbp+570h+var_5F0]
0x1400714d9  lea     rax, [rsp+670h+var_600]
0x1400714de  mov     [rsp+670h+ppv], rax; int
0x1400714e3  lea     r8, aEndpoints; "/endpoints/"
0x1400714ea  lea     rdx, aPost; "POST"
0x1400714f1  mov     rcx, rdi
0x1400714f4  mov     rax, rbx
0x1400714f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400714fc  mov     rcx, [rbp+578h]; this
0x140071503  test    eax, eax
0x140071505  jns     short loc_14007151C
0x140071507  mov     r9d, eax; char *
0x14007150a  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140071511  mov     edx, 171h; void *
0x140071516  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007151c  lea     rcx, [rbp+570h+var_310]; this
0x140071523  call    ??0HNSSingleEndpointResponse@HNS@Containers@Config@@QEAA@XZ; Config::Containers::HNS::HNSSingleEndpointResponse::HNSSingleEndpointResponse(void)
0x140071528  nop
0x140071529  mov     rcx, qword ptr [rsp+670h+var_600]
0x14007152e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140071532  inc     rax
0x140071535  cmp     [rcx+rax*2], r14w
0x14007153a  jnz     short loc_140071532
0x14007153c  mov     qword ptr [rsp+670h+var_630], rcx
0x140071541  mov     qword ptr [rsp+670h+var_630+8], rax
0x140071546  lea     r8, [rbp+570h+var_310]
0x14007154d  lea     rdx, [rsp+670h+var_630]
0x140071552  lea     rcx, [rsp+670h+var_620]
0x140071557  call    ??$FromJson@UHNSSingleEndpointResponse@HNS@Containers@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUHNSSingleEndpointResponse@HNS@Containers@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Config::Containers::HNS::HNSSingleEndpointResponse,>(std::basic_string_view<ushort>,Config::Containers::HNS::HNSSingleEndpointResponse *,Marshal::UnmarshalFlags)
0x14007155c  nop
0x14007155d  mov     edx, 0C037010Dh
0x140071562  mov     rcx, rax
0x140071565  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x14007156a  nop
0x14007156b  lea     rcx, [rsp+670h+var_618]
0x140071570  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140071575  mov     rcx, [rbp+578h]; this
0x14007157c  lea     rax, aErrorCreatingH; "Error creating HNS endpoints"
0x140071583  mov     qword ptr [rsp+670h+var_648], rax; bool
0x140071588  mov     al, [rbp+570h+var_310]
0x14007158e  mov     byte ptr [rsp+670h+ppv], al; char
0x140071592  mov     r9d, 800704CFh; char *
0x140071598  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14007159f  mov     edx, 178h; void *
0x1400715a4  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400715a9  movaps  xmm0, [rbp+570h+var_2E0]
0x1400715b0  movdqu  xmmword ptr [rsi], xmm0
0x1400715b4  lea     rcx, [rbp+570h+var_310]; this
0x1400715bb  call    ??1HNSSingleEndpointResponse@HNS@Containers@Config@@QEAA@XZ; Config::Containers::HNS::HNSSingleEndpointResponse::~HNSSingleEndpointResponse(void)
0x1400715c0  nop
0x1400715c1  lea     rcx, [rsp+670h+var_600]
0x1400715c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400715cb  nop
0x1400715cc  lea     rcx, [rbp+570h+var_5F0]; this
0x1400715d0  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400715d5  nop
0x1400715d6  lea     rcx, [rbp+570h+var_5D0]; this
0x1400715da  call    ??1HNSEndpoint@HNS@Containers@Config@@QEAA@XZ; Config::Containers::HNS::HNSEndpoint::~HNSEndpoint(void)
0x1400715df  nop
0x1400715e0  lea     rcx, [rsp+670h+var_5F8]
0x1400715e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400715ea  nop
0x1400715eb  call    cs:__imp_CoUninitialize
0x1400715f2  nop     dword ptr [rax+rax+00h]
0x1400715f7  mov     rax, rsi
0x1400715fa  mov     rcx, [rbp+570h+var_20]
0x140071601  xor     rcx, rsp; StackCookie
0x140071604  call    __security_check_cookie
0x140071609  lea     r11, [rsp+670h+var_10]
0x140071611  mov     rbx, [r11+20h]
0x140071615  mov     rsi, [r11+30h]
0x140071619  mov     rsp, r11
0x14007161c  pop     r14
0x14007161e  pop     rdi
0x14007161f  pop     rbp
0x140071620  retn
```
