# ComputeService::Net::HnsQueryEndpoint(_GUID const &,Config::Containers::VmHosted::NetworkAdapter &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400ee0c0`
- end: `0x1400ee410`
- name: `?HnsQueryEndpoint@Net@ComputeService@@YAXAEBU_GUID@@AEAUNetworkAdapter@VmHosted@Containers@Config@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `848`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140098ed0`
- `0x1400c0d08`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001bc28`
- `0x14002450c`
- `0x14004249c`
- `0x140044974`
- `0x14005bb24`
- `0x140071628`
- `0x140071650`
- `0x140071d04`
- `0x140073a74`
- `0x1400c18d8`
- `0x1400c2810`
- `0x1400c40e0`
- `0x1400ee0c0`
- `0x1400ee418`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x14021a0cc`
- `0x14021a1cc`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400ee3e2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400ee3e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400ee156`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400ee156`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400ee0f8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400ee0f8`

## string_xrefs

- `0x1400ee115`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400ee170`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400ee209`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400ee296`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ComputeService::Net::HnsQueryEndpoint(__int128 *a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, const wchar_t *, _QWORD *, const WCHAR *); // rbx
  _QWORD *v10; // r8
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  ComputeService::Net *v14; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  const char *v17; // [rsp+30h] [rbp-D0h]
  _QWORD v18[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[24]; // [rsp+68h] [rbp-98h] BYREF
  int v21[2]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v22; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v23[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-50h] BYREF
  bool EnableFirewall; // [rsp+C0h] [rbp-40h]
  char v26; // [rsp+C1h] [rbp-3Fh]
  _BYTE v27[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v28[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v29[40]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v30[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v31[34]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v32; // [rsp+172h] [rbp+72h]
  int v33; // [rsp+174h] [rbp+74h]
  __int128 v34; // [rsp+178h] [rbp+78h]
  __int64 v35; // [rsp+188h] [rbp+88h]
  int v36; // [rsp+190h] [rbp+90h]
  _BYTE v37[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v38[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v39[168]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v40[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v41[40]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v42[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v43[96]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v44[32]; // [rsp+350h] [rbp+250h] BYREF
  char v45; // [rsp+370h] [rbp+270h]
  char v46; // [rsp+3C0h] [rbp+2C0h]
  __int16 v47; // [rsp+428h] [rbp+328h]
  __int128 v48; // [rsp+430h] [rbp+330h]
  __int64 v49; // [rsp+440h] [rbp+340h]
  int v50; // [rsp+448h] [rbp+348h]
  int v51; // [rsp+44Ch] [rbp+34Ch]
  _BYTE v52[32]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v53[96]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  BYTE1(v17) = 1;
  v22 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v7 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v22);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2AC,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v7,
      ppva);
  *(_QWORD *)v21 = 0;
  Vml::GuidToString(v18, a1, 0);
  std::operator+<unsigned short>(v23);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v18);
  v8 = v22;
  v9 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, const WCHAR *))(*(_QWORD *)v22 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v21,
    0);
  v10 = v23;
  if ( v23[3] > 7u )
    v10 = (_QWORD *)v23[0];
  v11 = v9(v8, L"GET", v10, &szPassword);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v11,
      (int)v21);
  Config::Containers::HNS::HNSSingleEndpointResponse::HNSSingleEndpointResponse((Config::Containers::HNS::HNSSingleEndpointResponse *)v39);
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(*(_QWORD *)v21 + 2 * v12) );
  v18[0] = *(_QWORD *)v21;
  v18[1] = v12;
  v13 = Marshal::FromJson<Config::Containers::HNS::HNSSingleEndpointResponse,>(v19, v18, v39);
  Marshal::ThrowOnUnmarshalError(v13, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v20);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x2B7,
    (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
    (const char *)0x800704CFLL,
    v39[0],
    (bool)"Error querying HNS endpoints",
    v17);
  Config::Containers::VmHosted::NetworkAdapter::NetworkAdapter((Config::Containers::VmHosted::NetworkAdapter *)&v24);
  v24 = *a1;
  EnableFirewall = ComputeService::Net::GetEnableFirewall(v14);
  std::wstring::operator=(v27, v40);
  v34 = v48;
  v35 = v49;
  v36 = v50;
  v33 = v51;
  std::wstring::operator=(v37, v52);
  std::wstring::operator=(v38, v53);
  if ( v45 )
  {
    v26 = 1;
    std::wstring::operator=(v28, v41);
    std::wstring::operator=(v29, v44);
    v29[32] = v45;
    std::wstring::operator=(v30, v42);
    std::wstring::operator=(v31, v43);
    v31[32] = v46;
    v32 = v47;
  }
  std::wstring::operator=(a3, v40);
  Config::Containers::VmHosted::NetworkAdapter::operator=(a2, &v24);
  Config::Containers::VmHosted::NetworkAdapter::~NetworkAdapter((Config::Containers::VmHosted::NetworkAdapter *)&v24);
  Config::Containers::HNS::HNSSingleEndpointResponse::~HNSSingleEndpointResponse((Config::Containers::HNS::HNSSingleEndpointResponse *)v39);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  CoUninitialize();
}

```

## disassembly

```asm
0x1400ee0c0  push    rbp
0x1400ee0c2  push    rbx
0x1400ee0c3  push    rsi
0x1400ee0c4  push    rdi
0x1400ee0c5  push    r12
0x1400ee0c7  push    r14
0x1400ee0c9  push    r15
0x1400ee0cb  lea     rbp, [rsp-3E0h]
0x1400ee0d3  sub     rsp, 4E0h
0x1400ee0da  mov     rax, cs:__security_cookie
0x1400ee0e1  xor     rax, rsp
0x1400ee0e4  mov     [rbp+410h+var_40], rax
0x1400ee0eb  mov     r14, r8
0x1400ee0ee  mov     rsi, rdx
0x1400ee0f1  mov     r15, rcx
0x1400ee0f4  xor     edx, edx; dwCoInit
0x1400ee0f6  xor     ecx, ecx; pvReserved
0x1400ee0f8  call    cs:__imp_CoInitializeEx
0x1400ee0ff  nop     dword ptr [rax+rax+00h]
0x1400ee104  mov     rcx, [rbp+418h]; this
0x1400ee10b  xor     r12d, r12d
0x1400ee10e  test    eax, eax
0x1400ee110  jns     short loc_1400EE127
0x1400ee112  mov     r9d, eax; char *
0x1400ee115  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee11c  mov     edx, 2A8h; void *
0x1400ee121  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ee127  mov     [rsp+510h+var_4DF], 1
0x1400ee12c  mov     [rbp+410h+var_488], r12
0x1400ee130  lea     rcx, [rbp+410h+var_488]
0x1400ee134  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400ee139  lea     rax, [rbp+410h+var_488]
0x1400ee13d  mov     [rsp+510h+ppv], rax; int
0x1400ee142  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x1400ee149  xor     edx, edx; pUnkOuter
0x1400ee14b  lea     r8d, [rdx+17h]; dwClsContext
0x1400ee14f  lea     rcx, rclsid; rclsid
0x1400ee156  call    cs:__imp_CoCreateInstance
0x1400ee15d  nop     dword ptr [rax+rax+00h]
0x1400ee162  mov     rcx, [rbp+418h]; this
0x1400ee169  test    eax, eax
0x1400ee16b  jns     short loc_1400EE182
0x1400ee16d  mov     r9d, eax; char *
0x1400ee170  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee177  mov     edx, 2ACh; void *
0x1400ee17c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ee182  mov     qword ptr [rbp+410h+var_490], r12
0x1400ee186  xor     r8d, r8d
0x1400ee189  mov     rdx, r15
0x1400ee18c  lea     rcx, [rsp+510h+var_4D0]
0x1400ee191  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ee196  nop
0x1400ee197  mov     r8, rax
0x1400ee19a  lea     rdx, aEndpoints; "/endpoints/"
0x1400ee1a1  lea     rcx, [rbp+410h+var_480]; void *
0x1400ee1a5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1400ee1aa  nop
0x1400ee1ab  lea     rcx, [rsp+510h+var_4D0]; this
0x1400ee1b0  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400ee1b5  mov     rdi, [rbp+410h+var_488]
0x1400ee1b9  mov     rax, [rdi]
0x1400ee1bc  mov     rbx, [rax+38h]
0x1400ee1c0  xor     edx, edx
0x1400ee1c2  lea     rcx, [rbp+410h+var_490]
0x1400ee1c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400ee1cb  lea     r8, [rbp+410h+var_480]
0x1400ee1cf  cmp     [rbp+410h+var_468], 7
0x1400ee1d4  cmova   r8, [rbp+410h+var_480]
0x1400ee1d9  lea     rax, [rbp+410h+var_490]
0x1400ee1dd  mov     [rsp+510h+ppv], rax; int
0x1400ee1e2  lea     r9, szPassword
0x1400ee1e9  lea     rdx, aGet_0; "GET"
0x1400ee1f0  mov     rcx, rdi
0x1400ee1f3  mov     rax, rbx
0x1400ee1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee1fb  mov     rcx, [rbp+418h]; this
0x1400ee202  test    eax, eax
0x1400ee204  jns     short loc_1400EE21B
0x1400ee206  mov     r9d, eax; char *
0x1400ee209  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee210  mov     edx, 2B0h; void *
0x1400ee215  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ee21b  lea     rcx, [rbp+410h+var_330]; this
0x1400ee222  call    ??0HNSSingleEndpointResponse@HNS@Containers@Config@@QEAA@XZ; Config::Containers::HNS::HNSSingleEndpointResponse::HNSSingleEndpointResponse(void)
0x1400ee227  nop
0x1400ee228  mov     rcx, qword ptr [rbp+410h+var_490]
0x1400ee22c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400ee230  inc     rax
0x1400ee233  cmp     [rcx+rax*2], r12w
0x1400ee238  jnz     short loc_1400EE230
0x1400ee23a  mov     [rsp+510h+var_4D0], rcx
0x1400ee23f  mov     [rsp+510h+var_4C8], rax
0x1400ee244  lea     r8, [rbp+410h+var_330]
0x1400ee24b  lea     rdx, [rsp+510h+var_4D0]
0x1400ee250  lea     rcx, [rsp+510h+var_4B0]
0x1400ee255  call    ??$FromJson@UHNSSingleEndpointResponse@HNS@Containers@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUHNSSingleEndpointResponse@HNS@Containers@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Config::Containers::HNS::HNSSingleEndpointResponse,>(std::basic_string_view<ushort>,Config::Containers::HNS::HNSSingleEndpointResponse *,Marshal::UnmarshalFlags)
0x1400ee25a  nop
0x1400ee25b  mov     edx, 0C037010Dh
0x1400ee260  mov     rcx, rax
0x1400ee263  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400ee268  nop
0x1400ee269  lea     rcx, [rsp+510h+var_4A8]
0x1400ee26e  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400ee273  mov     rcx, [rbp+418h]; this
0x1400ee27a  lea     rax, aErrorQueryingH; "Error querying HNS endpoints"
0x1400ee281  mov     qword ptr [rsp+510h+var_4E8], rax; bool
0x1400ee286  mov     al, [rbp+410h+var_330]
0x1400ee28c  mov     byte ptr [rsp+510h+ppv], al; char
0x1400ee290  mov     r9d, 800704CFh; char *
0x1400ee296  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee29d  mov     edx, 2B7h; void *
0x1400ee2a2  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400ee2a7  lea     rcx, [rbp+410h+var_460]; this
0x1400ee2ab  call    ??0NetworkAdapter@VmHosted@Containers@Config@@QEAA@XZ; Config::Containers::VmHosted::NetworkAdapter::NetworkAdapter(void)
0x1400ee2b0  nop
0x1400ee2b1  movups  xmm0, xmmword ptr [r15]
0x1400ee2b5  movdqu  [rbp+410h+var_460], xmm0
0x1400ee2ba  call    ?GetEnableFirewall@Net@ComputeService@@YA_NXZ; ComputeService::Net::GetEnableFirewall(void)
0x1400ee2bf  mov     [rbp+410h+var_450], al
0x1400ee2c2  lea     rdx, [rbp+410h+var_288]
0x1400ee2c9  lea     rcx, [rbp+410h+var_448]
0x1400ee2cd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee2d2  movaps  xmm0, [rbp+410h+var_E0]
0x1400ee2d9  movdqu  [rbp+410h+var_398], xmm0
0x1400ee2de  mov     rax, [rbp+410h+var_D0]
0x1400ee2e5  mov     [rbp+410h+var_388], rax
0x1400ee2ec  mov     eax, [rbp+410h+var_C8]
0x1400ee2f2  mov     [rbp+410h+var_380], eax
0x1400ee2f8  mov     eax, [rbp+410h+var_C4]
0x1400ee2fe  mov     [rbp+410h+var_39C], eax
0x1400ee301  lea     rdx, [rbp+410h+var_C0]
0x1400ee308  lea     rcx, [rbp+410h+var_378]
0x1400ee30f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee314  lea     rdx, [rbp+410h+var_A0]
0x1400ee31b  lea     rcx, [rbp+410h+var_358]
0x1400ee322  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee327  cmp     [rbp+410h+var_1A0], r12b
0x1400ee32e  jz      short loc_1400EE391
0x1400ee330  mov     [rbp+410h+var_44F], 1
0x1400ee334  lea     rdx, [rbp+410h+var_268]
0x1400ee33b  lea     rcx, [rbp+410h+var_428]
0x1400ee33f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee344  lea     rdx, [rbp+410h+var_1C0]
0x1400ee34b  lea     rcx, [rbp+410h+var_408]
0x1400ee34f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee354  mov     al, [rbp+410h+var_1A0]
0x1400ee35a  mov     [rbp+410h+var_3E8], al
0x1400ee35d  lea     rdx, [rbp+410h+var_240]
0x1400ee364  lea     rcx, [rbp+410h+var_3E0]
0x1400ee368  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee36d  lea     rdx, [rbp+410h+var_220]
0x1400ee374  lea     rcx, [rbp+410h+var_3C0]
0x1400ee378  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400ee37d  mov     al, [rbp+410h+var_150]
0x1400ee383  mov     [rbp+410h+var_3A0], al
0x1400ee386  movzx   eax, [rbp+410h+var_E8]
0x1400ee38d  mov     [rbp+410h+var_39E], ax
0x1400ee391  lea     rdx, [rbp+410h+var_288]
0x1400ee398  mov     rcx, r14
0x1400ee39b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400ee3a0  lea     rdx, [rbp+410h+var_460]
0x1400ee3a4  mov     rcx, rsi
0x1400ee3a7  call    ??4NetworkAdapter@VmHosted@Containers@Config@@QEAAAEAU0123@$$QEAU0123@@Z; Config::Containers::VmHosted::NetworkAdapter::operator=(Config::Containers::VmHosted::NetworkAdapter &&)
0x1400ee3ac  nop
0x1400ee3ad  lea     rcx, [rbp+410h+var_460]; this
0x1400ee3b1  call    ??1NetworkAdapter@VmHosted@Containers@Config@@QEAA@XZ; Config::Containers::VmHosted::NetworkAdapter::~NetworkAdapter(void)
0x1400ee3b6  nop
0x1400ee3b7  lea     rcx, [rbp+410h+var_330]; this
0x1400ee3be  call    ??1HNSSingleEndpointResponse@HNS@Containers@Config@@QEAA@XZ; Config::Containers::HNS::HNSSingleEndpointResponse::~HNSSingleEndpointResponse(void)
0x1400ee3c3  nop
0x1400ee3c4  lea     rcx, [rbp+410h+var_480]; this
0x1400ee3c8  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400ee3cd  nop
0x1400ee3ce  lea     rcx, [rbp+410h+var_490]
0x1400ee3d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400ee3d7  nop
0x1400ee3d8  lea     rcx, [rbp+410h+var_488]
0x1400ee3dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400ee3e1  nop
0x1400ee3e2  call    cs:__imp_CoUninitialize
0x1400ee3e9  nop     dword ptr [rax+rax+00h]
0x1400ee3ee  mov     rcx, [rbp+410h+var_40]
0x1400ee3f5  xor     rcx, rsp; StackCookie
0x1400ee3f8  call    __security_check_cookie
0x1400ee3fd  add     rsp, 4E0h
0x1400ee404  pop     r15
0x1400ee406  pop     r14
0x1400ee408  pop     r12
0x1400ee40a  pop     rdi
0x1400ee40b  pop     rsi
0x1400ee40c  pop     rbx
0x1400ee40d  pop     rbp
0x1400ee40e  retn
```
