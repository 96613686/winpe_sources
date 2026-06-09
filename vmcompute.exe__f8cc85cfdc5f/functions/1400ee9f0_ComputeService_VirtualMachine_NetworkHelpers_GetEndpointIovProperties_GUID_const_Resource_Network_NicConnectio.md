# ComputeService::VirtualMachine::NetworkHelpers::GetEndpointIovProperties(_GUID const &,Resource::Network::NicConnectionResource *)

- ea: `0x1400ee9f0`
- end: `0x1400eec34`
- name: `?GetEndpointIovProperties@NetworkHelpers@VirtualMachine@ComputeService@@YAXAEBU_GUID@@PEAUNicConnectionResource@Network@Resource@@@Z`
- size: `580`
- prototype: `void __fastcall(GUID *Id, const struct _GUID *, struct Resource::Network::NicConnectionResource *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400261c8`

## callees

- `0x140017040`
- `0x14001bc28`
- `0x1400421f0`
- `0x140070ba0`
- `0x140071cd4`
- `0x140071d04`
- `0x140073a74`
- `0x14007fe20`
- `0x14007fea8`
- `0x1400c40e0`
- `0x1400ee9f0`
- `0x1400eec3c`
- `0x1400eece4`
- `0x1400eedc8`
- `0x1400eee68`
- `0x1401332f0`
- `0x1401f685c`

## import_xrefs

- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnCloseEndpoint` at `0x1400eea6a`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnCloseEndpoint` at `0x1400eea6a`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnQueryEndpointProperties` at `0x1400eeaf2`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnQueryEndpointProperties` at `0x1400eeaf2`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnOpenEndpoint` at `0x1400eea90`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnOpenEndpoint` at `0x1400eea90`

## string_xrefs

- `0x1400eeaaa`: `onecore\vm\compute\management\orchestration\shared\vmconfig\networkhelpers.cpp`
- `0x1400eeb0c`: `onecore\vm\compute\management\orchestration\shared\vmconfig\networkhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ComputeService::VirtualMachine::NetworkHelpers::GetEndpointIovProperties(
        GUID *Id,
        const struct _GUID *a2,
        struct Resource::Network::NicConnectionResource *a3)
{
  HRESULT v5; // eax
  __int64 v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD *i; // rcx
  __int64 v11; // rax
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v13[24]; // [rsp+28h] [rbp-D8h] BYREF
  HCN_ENDPOINT Endpoint; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR Properties; // [rsp+48h] [rbp-B8h] BYREF
  PWSTR v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+78h] [rbp-88h]
  _BYTE v20[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[520]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v22; // [rsp+2A8h] [rbp+1A8h]
  _DWORD *v23; // [rsp+2B0h] [rbp+1B0h]
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  Properties = 0;
  v19 = 0;
  std::wstring::wstring(v20);
  HNS::Schema::HostComputeEndpoint::HostComputeEndpoint((HNS::Schema::HostComputeEndpoint *)v21);
  v18 = 2;
  Endpoint = 0;
  v5 = HcnOpenEndpoint(Id, &Endpoint, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\networkhelpers.cpp",
      (const char *)(unsigned int)v5,
      v12);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &Properties,
    0);
  v6 = Marshal::ToJson<HNS::Schema::Common::HostComputeQuery &,>(&v16, &v18);
  if ( *(_QWORD *)(v6 + 24) > 7u )
    v6 = *(_QWORD *)v6;
  v7 = HcnQueryEndpointProperties(Endpoint, (PCWSTR)v6, &Properties, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\networkhelpers.cpp",
      (const char *)(unsigned int)v7,
      v12);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v16);
  v8 = -1;
  do
    ++v8;
  while ( Properties[v8] );
  v16 = Properties;
  v17 = v8;
  v9 = Marshal::FromJson<HNS::Schema::HostComputeEndpoint,>(&v12, &v16, v21);
  Marshal::ThrowOnUnmarshalError(v9, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v13);
  for ( i = v22; i != v23; i += 18 )
  {
    if ( *i == 15 )
    {
      v16 = 0;
      LODWORD(v17) = 0;
      v11 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<HNS::Schema::Network::Endpoint::Policy::IovPolicySetting>(
              i + 2,
              &v12,
              &v16);
      Marshal::ThrowOnUnmarshalError(v11, 2147942413LL);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v13);
      *(_DWORD *)&a2[6].Data2 = (_DWORD)v16;
      a2[6].Data4[0] = 1;
      *(_DWORD *)&a2[6].Data4[4] = HIDWORD(v16);
      LOBYTE(a2[7].Data1) = 1;
      *(_DWORD *)&a2[7].Data2 = v17;
      a2[7].Data4[0] = 1;
      break;
    }
  }
  HNS::Schema::HostComputeEndpoint::~HostComputeEndpoint((HNS::Schema::HostComputeEndpoint *)v21);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Properties);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long HcnCloseEndpoint(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long HcnCloseEndpoint(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Endpoint);
}

```

## disassembly

```asm
0x1400ee9f0  mov     [rsp-8+arg_10], rbx
0x1400ee9f5  mov     [rsp-8+arg_18], rsi
0x1400ee9fa  push    rbp
0x1400ee9fb  push    rdi
0x1400ee9fc  push    r14
0x1400ee9fe  lea     rbp, [rsp-290h]
0x1400eea06  sub     rsp, 390h
0x1400eea0d  mov     rax, cs:__security_cookie
0x1400eea14  xor     rax, rsp
0x1400eea17  mov     [rbp+2A0h+var_20], rax
0x1400eea1e  mov     rsi, rdx
0x1400eea21  mov     rdi, rcx
0x1400eea24  xor     r14d, r14d
0x1400eea27  mov     [rsp+3A0h+Endpoint], r14
0x1400eea2c  mov     [rsp+3A0h+Properties], r14
0x1400eea31  mov     [rsp+3A0h+var_328], r14d
0x1400eea36  lea     rcx, [rbp+2A0h+var_320]; void *
0x1400eea3a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400eea3f  nop
0x1400eea40  lea     rcx, [rbp+2A0h+var_300]; this
0x1400eea44  call    ??0HostComputeEndpoint@Schema@HNS@@QEAA@XZ; HNS::Schema::HostComputeEndpoint::HostComputeEndpoint(void)
0x1400eea49  nop
0x1400eea4a  mov     [rsp+3A0h+var_330], 2
0x1400eea53  mov     rbx, [rsp+3A0h+Endpoint]
0x1400eea58  test    rbx, rbx
0x1400eea5b  jz      short loc_1400EEA80
0x1400eea5d  lea     rcx, [rsp+3A0h+var_350]; this
0x1400eea62  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400eea67  mov     rcx, rbx; Endpoint
0x1400eea6a  call    cs:__imp_HcnCloseEndpoint
0x1400eea71  nop     dword ptr [rax+rax+00h]
0x1400eea76  lea     rcx, [rsp+3A0h+var_350]; this
0x1400eea7b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400eea80  mov     [rsp+3A0h+Endpoint], r14
0x1400eea85  xor     r8d, r8d; ErrorRecord
0x1400eea88  lea     rdx, [rsp+3A0h+Endpoint]; Endpoint
0x1400eea8d  mov     rcx, rdi; Id
0x1400eea90  call    cs:__imp_HcnOpenEndpoint
0x1400eea97  nop     dword ptr [rax+rax+00h]
0x1400eea9c  mov     rcx, [rbp+2A8h]; this
0x1400eeaa3  test    eax, eax
0x1400eeaa5  jns     short loc_1400EEABC
0x1400eeaa7  mov     r9d, eax; char *
0x1400eeaaa  lea     r8, aOnecoreVmCompu_73; "onecore\\vm\\compute\\management\\orche"...
0x1400eeab1  mov     edx, 100h; void *
0x1400eeab6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400eeabc  xor     edx, edx
0x1400eeabe  lea     rcx, [rsp+3A0h+Properties]
0x1400eeac3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400eeac8  lea     rdx, [rsp+3A0h+var_330]
0x1400eeacd  lea     rcx, [rsp+3A0h+var_350]
0x1400eead2  call    ??$ToJson@AEAUHostComputeQuery@Common@Schema@HNS@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUHostComputeQuery@Common@Schema@HNS@@W4MarshalFlags@0@@Z; Marshal::ToJson<HNS::Schema::Common::HostComputeQuery &,>(HNS::Schema::Common::HostComputeQuery &,Marshal::MarshalFlags)
0x1400eead7  nop
0x1400eead8  cmp     qword ptr [rax+18h], 7
0x1400eeadd  jbe     short loc_1400EEAE2
0x1400eeadf  mov     rax, [rax]
0x1400eeae2  xor     r9d, r9d; ErrorRecord
0x1400eeae5  lea     r8, [rsp+3A0h+Properties]; Properties
0x1400eeaea  mov     rdx, rax; Query
0x1400eeaed  mov     rcx, [rsp+3A0h+Endpoint]; Endpoint
0x1400eeaf2  call    cs:__imp_HcnQueryEndpointProperties
0x1400eeaf9  nop     dword ptr [rax+rax+00h]
0x1400eeafe  mov     rcx, [rbp+2A8h]; this
0x1400eeb05  test    eax, eax
0x1400eeb07  jns     short loc_1400EEB1E
0x1400eeb09  mov     r9d, eax; char *
0x1400eeb0c  lea     r8, aOnecoreVmCompu_73; "onecore\\vm\\compute\\management\\orche"...
0x1400eeb13  mov     edx, 101h; void *
0x1400eeb18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400eeb1e  lea     rcx, [rsp+3A0h+var_350]; this
0x1400eeb23  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400eeb28  mov     rcx, [rsp+3A0h+Properties]
0x1400eeb2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400eeb31  inc     rax
0x1400eeb34  cmp     [rcx+rax*2], r14w
0x1400eeb39  jnz     short loc_1400EEB31
0x1400eeb3b  mov     [rsp+3A0h+var_350], rcx
0x1400eeb40  mov     [rsp+3A0h+var_348], rax
0x1400eeb45  lea     r8, [rbp+2A0h+var_300]
0x1400eeb49  lea     rdx, [rsp+3A0h+var_350]
0x1400eeb4e  lea     rcx, [rsp+3A0h+var_380]
0x1400eeb53  call    ??$FromJson@UHostComputeEndpoint@Schema@HNS@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUHostComputeEndpoint@Schema@HNS@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<HNS::Schema::HostComputeEndpoint,>(std::basic_string_view<ushort>,HNS::Schema::HostComputeEndpoint *,Marshal::UnmarshalFlags)
0x1400eeb58  nop
0x1400eeb59  mov     edx, 0C037010Dh
0x1400eeb5e  mov     rcx, rax
0x1400eeb61  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400eeb66  nop
0x1400eeb67  lea     rcx, [rsp+3A0h+var_378]
0x1400eeb6c  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400eeb71  mov     rcx, [rbp+2A0h+var_F8]
0x1400eeb78  cmp     rcx, [rbp+2A0h+var_F0]
0x1400eeb7f  jz      short loc_1400EEBE3
0x1400eeb81  cmp     dword ptr [rcx], 0Fh
0x1400eeb84  jz      short loc_1400EEB8C
0x1400eeb86  add     rcx, 48h ; 'H'
0x1400eeb8a  jmp     short loc_1400EEB78
0x1400eeb8c  mov     [rsp+3A0h+var_350], r14
0x1400eeb91  mov     dword ptr [rsp+3A0h+var_348], r14d
0x1400eeb96  add     rcx, 8
0x1400eeb9a  lea     r8, [rsp+3A0h+var_350]
0x1400eeb9f  lea     rdx, [rsp+3A0h+var_380]
0x1400eeba4  call    ??$Unmarshal@UIovPolicySetting@Policy@Endpoint@Network@Schema@HNS@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUIovPolicySetting@Policy@Endpoint@Network@Schema@HNS@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<HNS::Schema::Network::Endpoint::Policy::IovPolicySetting>(HNS::Schema::Network::Endpoint::Policy::IovPolicySetting *)
0x1400eeba9  nop
0x1400eebaa  mov     edx, 8007000Dh
0x1400eebaf  mov     rcx, rax
0x1400eebb2  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x1400eebb7  nop
0x1400eebb8  lea     rcx, [rsp+3A0h+var_378]
0x1400eebbd  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400eebc2  mov     eax, dword ptr [rsp+3A0h+var_350]
0x1400eebc6  mov     [rsi+64h], eax
0x1400eebc9  mov     byte ptr [rsi+68h], 1
0x1400eebcd  mov     eax, dword ptr [rsp+3A0h+var_350+4]
0x1400eebd1  mov     [rsi+6Ch], eax
0x1400eebd4  mov     byte ptr [rsi+70h], 1
0x1400eebd8  mov     eax, dword ptr [rsp+3A0h+var_348]
0x1400eebdc  mov     [rsi+74h], eax
0x1400eebdf  mov     byte ptr [rsi+78h], 1
0x1400eebe3  lea     rcx, [rbp+2A0h+var_300]; this
0x1400eebe7  call    ??1HostComputeEndpoint@Schema@HNS@@QEAA@XZ; HNS::Schema::HostComputeEndpoint::~HostComputeEndpoint(void)
0x1400eebec  nop
0x1400eebed  lea     rcx, [rbp+2A0h+var_320]; this
0x1400eebf1  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400eebf6  nop
0x1400eebf7  lea     rcx, [rsp+3A0h+Properties]
0x1400eebfc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400eec01  nop
0x1400eec02  lea     rcx, [rsp+3A0h+Endpoint]
0x1400eec07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HcnCloseEndpoint@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HcnCloseEndpoint(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HcnCloseEndpoint(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400eec0c  mov     rcx, [rbp+2A0h+var_20]
0x1400eec13  xor     rcx, rsp; StackCookie
0x1400eec16  call    __security_check_cookie
0x1400eec1b  lea     r11, [rsp+3A0h+var_10]
0x1400eec23  mov     rbx, [r11+30h]
0x1400eec27  mov     rsi, [r11+38h]
0x1400eec2b  mov     rsp, r11
0x1400eec2e  pop     r14
0x1400eec30  pop     rdi
0x1400eec31  pop     rbp
0x1400eec32  retn
```
