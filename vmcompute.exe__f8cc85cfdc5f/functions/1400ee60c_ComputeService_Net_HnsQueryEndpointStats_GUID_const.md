# ComputeService::Net::HnsQueryEndpointStats(_GUID const &)

- ea: `0x1400ee60c`
- end: `0x1400ee8c5`
- name: `?HnsQueryEndpointStats@Net@ComputeService@@YA?AV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@AEBU_GUID@@@Z`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140114dd8`
- `0x140204370`

## callees

- `0x140017040`
- `0x14001bc28`
- `0x14002450c`
- `0x14002f868`
- `0x1400421f0`
- `0x14004249c`
- `0x14005c288`
- `0x140070d38`
- `0x140071d04`
- `0x140073a74`
- `0x1400c40e0`
- `0x1400ee60c`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x140134048`
- `0x140189fcc`
- `0x1401a622c`
- `0x140219638`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400ee891`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400ee891`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400ee69d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400ee69d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400ee645`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400ee645`

## string_xrefs

- `0x1400ee65c`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400ee6b4`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400ee74a`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void *__fastcall ComputeService::Net::HnsQueryEndpointStats(void *a1, __int64 a2)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, const wchar_t *, _QWORD *, const WCHAR *); // rbx
  _QWORD *v8; // r8
  int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h]
  _OWORD v18[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+98h] [rbp-68h]
  int v21[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v22; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v23[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v25[32]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v27; // [rsp+100h] [rbp+0h]
  __int128 v28; // [rsp+110h] [rbp+10h]
  __int128 v29; // [rsp+120h] [rbp+20h]
  int v30; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v22 = a1;
  v4 = CoInitializeEx(0, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v22 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v5 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v22);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  *(_QWORD *)v21 = 0;
  Vml::GuidToString(&v16, a2, 0);
  std::operator+<unsigned short>(v23);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v16);
  v6 = v22;
  v7 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, const WCHAR *))(*(_QWORD *)v22 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v21,
    0);
  v8 = v23;
  if ( v23[3] > 7u )
    v8 = (_QWORD *)v23[0];
  v9 = v7(v6, L"GET", v8, &szPassword);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v9,
      (int)v21);
  v24[0] = 0;
  std::wstring::wstring(v25);
  memset_0(&v26, 0, 0x40u);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(*(_QWORD *)v21 + 2 * v11) );
  v16 = *(_QWORD *)v21;
  v17 = v11;
  v12 = Marshal::FromJson<Config::Containers::HNS::HNSEndpointStatsResponse,>(v18, &v16, v24);
  Marshal::ThrowOnUnmarshalError(v12, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)v18 + 8);
  if ( v24[0] )
  {
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
      a1,
      &v26);
  }
  else
  {
    memset_0(v18, 0, 0x40u);
    memset(v18, 0, sizeof(v18));
    v19 = 0;
    v20 = 0;
    do
      ++v10;
    while ( *(_WORD *)(*(_QWORD *)v21 + 2 * v10) );
    v16 = *(_QWORD *)v21;
    v17 = v10;
    Marshal::FromJsonThrow<Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>,>(&v16, v18, 0);
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
      a1,
      v18);
    Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v18);
  }
  Schema::Requests::Guest::NetworkModifySettingRequest::~NetworkModifySettingRequest((Schema::Requests::Guest::NetworkModifySettingRequest *)v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  CoUninitialize();
  return a1;
}

```

## disassembly

```asm
0x1400ee60c  mov     [rsp-8+arg_10], rbx
0x1400ee611  mov     [rsp-8+arg_18], rsi
0x1400ee616  push    rbp
0x1400ee617  push    rdi
0x1400ee618  push    r14
0x1400ee61a  lea     rbp, [rsp-50h]
0x1400ee61f  sub     rsp, 150h
0x1400ee626  mov     rax, cs:__security_cookie
0x1400ee62d  xor     rax, rsp
0x1400ee630  mov     [rbp+60h+var_20], rax
0x1400ee634  mov     rbx, rdx
0x1400ee637  mov     rsi, rcx
0x1400ee63a  mov     [rbp+60h+var_B8], rcx
0x1400ee63e  xor     r14d, r14d
0x1400ee641  xor     edx, edx; dwCoInit
0x1400ee643  xor     ecx, ecx; pvReserved
0x1400ee645  call    cs:__imp_CoInitializeEx
0x1400ee64c  nop     dword ptr [rax+rax+00h]
0x1400ee651  mov     rcx, [rbp+68h]; this
0x1400ee655  test    eax, eax
0x1400ee657  jns     short loc_1400EE66E
0x1400ee659  mov     r9d, eax; char *
0x1400ee65c  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee663  mov     edx, 2EDh; void *
0x1400ee668  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ee66e  mov     [rsp+160h+var_12F], 1
0x1400ee673  mov     [rbp+60h+var_B8], r14
0x1400ee677  lea     rcx, [rbp+60h+var_B8]
0x1400ee67b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400ee680  lea     rax, [rbp+60h+var_B8]
0x1400ee684  mov     qword ptr [rsp+160h+ppv], rax; int
0x1400ee689  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x1400ee690  xor     edx, edx; pUnkOuter
0x1400ee692  lea     r8d, [rdx+17h]; dwClsContext
0x1400ee696  lea     rcx, rclsid; rclsid
0x1400ee69d  call    cs:__imp_CoCreateInstance
0x1400ee6a4  nop     dword ptr [rax+rax+00h]
0x1400ee6a9  mov     rcx, [rbp+68h]; this
0x1400ee6ad  test    eax, eax
0x1400ee6af  jns     short loc_1400EE6C6
0x1400ee6b1  mov     r9d, eax; char *
0x1400ee6b4  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee6bb  mov     edx, 2F1h; void *
0x1400ee6c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ee6c6  mov     qword ptr [rbp+60h+var_C0], r14
0x1400ee6ca  xor     r8d, r8d
0x1400ee6cd  mov     rdx, rbx
0x1400ee6d0  lea     rcx, [rsp+160h+var_120]
0x1400ee6d5  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ee6da  nop
0x1400ee6db  mov     r8, rax
0x1400ee6de  lea     rdx, aEndpointstats; "/endpointstats/"
0x1400ee6e5  lea     rcx, [rbp+60h+var_B0]; void *
0x1400ee6e9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1400ee6ee  nop
0x1400ee6ef  lea     rcx, [rsp+160h+var_120]; this
0x1400ee6f4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400ee6f9  mov     rdi, [rbp+60h+var_B8]
0x1400ee6fd  mov     rax, [rdi]
0x1400ee700  mov     rbx, [rax+38h]
0x1400ee704  xor     edx, edx
0x1400ee706  lea     rcx, [rbp+60h+var_C0]
0x1400ee70a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400ee70f  lea     r8, [rbp+60h+var_B0]
0x1400ee713  cmp     [rbp+60h+var_98], 7
0x1400ee718  cmova   r8, [rbp+60h+var_B0]
0x1400ee71d  lea     rax, [rbp+60h+var_C0]
0x1400ee721  mov     qword ptr [rsp+160h+ppv], rax; int
0x1400ee726  lea     r9, szPassword
0x1400ee72d  lea     rdx, aGet_0; "GET"
0x1400ee734  mov     rcx, rdi
0x1400ee737  mov     rax, rbx
0x1400ee73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ee73f  mov     rcx, [rbp+68h]; this
0x1400ee743  test    eax, eax
0x1400ee745  jns     short loc_1400EE75C
0x1400ee747  mov     r9d, eax; char *
0x1400ee74a  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ee751  mov     edx, 2F5h; void *
0x1400ee756  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ee75c  mov     [rbp+60h+var_90], r14b
0x1400ee760  lea     rcx, [rbp+60h+var_88]; void *
0x1400ee764  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400ee769  mov     edi, 40h ; '@'
0x1400ee76e  mov     r8d, edi; Size
0x1400ee771  xor     edx, edx; Val
0x1400ee773  lea     rcx, [rbp+60h+var_68]; void *
0x1400ee777  call    memset_0
0x1400ee77c  mov     [rbp+60h+var_68], r14
0x1400ee780  xorps   xmm0, xmm0
0x1400ee783  movdqa  [rbp+60h+var_60], xmm0
0x1400ee788  xorps   xmm1, xmm1
0x1400ee78b  movdqa  [rbp+60h+var_50], xmm1
0x1400ee790  movdqa  [rbp+60h+var_40], xmm0
0x1400ee795  mov     [rbp+60h+var_30], r14d
0x1400ee799  mov     rcx, qword ptr [rbp+60h+var_C0]
0x1400ee79d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400ee7a1  mov     rax, rbx
0x1400ee7a4  inc     rax
0x1400ee7a7  cmp     [rcx+rax*2], r14w
0x1400ee7ac  jnz     short loc_1400EE7A4
0x1400ee7ae  mov     [rsp+160h+var_120], rcx
0x1400ee7b3  mov     [rsp+160h+var_118], rax
0x1400ee7b8  lea     r8, [rbp+60h+var_90]
0x1400ee7bc  lea     rdx, [rsp+160h+var_120]
0x1400ee7c1  lea     rcx, [rsp+160h+var_100]
0x1400ee7c6  call    ??$FromJson@UHNSEndpointStatsResponse@HNS@Containers@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUHNSEndpointStatsResponse@HNS@Containers@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Config::Containers::HNS::HNSEndpointStatsResponse,>(std::basic_string_view<ushort>,Config::Containers::HNS::HNSEndpointStatsResponse *,Marshal::UnmarshalFlags)
0x1400ee7cb  nop
0x1400ee7cc  mov     edx, 0C037010Dh
0x1400ee7d1  mov     rcx, rax
0x1400ee7d4  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400ee7d9  nop
0x1400ee7da  lea     rcx, [rsp+160h+var_100+8]
0x1400ee7df  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400ee7e4  cmp     [rbp+60h+var_90], r14b
0x1400ee7e8  jz      short loc_1400EE7F8
0x1400ee7ea  lea     rdx, [rbp+60h+var_68]
0x1400ee7ee  mov     rcx, rsi
0x1400ee7f1  call    ??0?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEBV01@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> const &)
0x1400ee7f6  jmp     short loc_1400EE869
0x1400ee7f8  mov     r8, rdi; Size
0x1400ee7fb  xor     edx, edx; Val
0x1400ee7fd  lea     rcx, [rsp+160h+var_100]; void *
0x1400ee802  call    memset_0
0x1400ee807  xorps   xmm0, xmm0
0x1400ee80a  movdqa  [rsp+160h+var_100], xmm0
0x1400ee810  xorps   xmm1, xmm1
0x1400ee813  movdqa  [rsp+160h+var_F0], xmm1
0x1400ee819  movdqa  [rbp+60h+var_E0], xmm0
0x1400ee81e  mov     [rbp+60h+var_D0], r14
0x1400ee822  mov     [rbp+60h+var_C8], r14d
0x1400ee826  mov     rax, qword ptr [rbp+60h+var_C0]
0x1400ee82a  inc     rbx
0x1400ee82d  cmp     [rax+rbx*2], r14w
0x1400ee832  jnz     short loc_1400EE82A
0x1400ee834  mov     [rsp+160h+var_120], rax
0x1400ee839  mov     [rsp+160h+var_118], rbx
0x1400ee83e  xor     r8d, r8d
0x1400ee841  lea     rdx, [rsp+160h+var_100]
0x1400ee846  lea     rcx, [rsp+160h+var_120]
0x1400ee84b  call    ??$FromJsonThrow@V?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@$$V@Marshal@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@0@W4UnmarshalFlags@0@J@Z; Marshal::FromJsonThrow<Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>,>(std::basic_string_view<ushort>,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> *,Marshal::UnmarshalFlags,long)
0x1400ee850  lea     rdx, [rsp+160h+var_100]
0x1400ee855  mov     rcx, rsi
0x1400ee858  call    ??0?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@$$QEAV01@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> &&)
0x1400ee85d  nop
0x1400ee85e  lea     rcx, [rsp+160h+var_100]
0x1400ee863  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x1400ee868  nop
0x1400ee869  lea     rcx, [rbp+60h+var_90]; this
0x1400ee86d  call    ??1NetworkModifySettingRequest@Guest@Requests@Schema@@QEAA@XZ; Schema::Requests::Guest::NetworkModifySettingRequest::~NetworkModifySettingRequest(void)
0x1400ee872  nop
0x1400ee873  lea     rcx, [rbp+60h+var_B0]; this
0x1400ee877  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400ee87c  nop
0x1400ee87d  lea     rcx, [rbp+60h+var_C0]
0x1400ee881  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400ee886  nop
0x1400ee887  lea     rcx, [rbp+60h+var_B8]
0x1400ee88b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400ee890  nop
0x1400ee891  call    cs:__imp_CoUninitialize
0x1400ee898  nop     dword ptr [rax+rax+00h]
0x1400ee89d  mov     rax, rsi
0x1400ee8a0  mov     rcx, [rbp+60h+var_20]
0x1400ee8a4  xor     rcx, rsp; StackCookie
0x1400ee8a7  call    __security_check_cookie
0x1400ee8ac  lea     r11, [rsp+160h+var_10]
0x1400ee8b4  mov     rbx, [r11+30h]
0x1400ee8b8  mov     rsi, [r11+38h]
0x1400ee8bc  mov     rsp, r11
0x1400ee8bf  pop     r14
0x1400ee8c1  pop     rdi
0x1400ee8c2  pop     rbp
0x1400ee8c3  retn
```
