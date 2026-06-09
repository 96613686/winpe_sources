# ComputeService::VirtualMachine::NetworkHelpers::AddEndpointSwitchPort(_GUID const &,_GUID const &,_GUID const &,_GUID const &)

- ea: `0x14008444c`
- end: `0x1400846f5`
- name: `?AddEndpointSwitchPort@NetworkHelpers@VirtualMachine@ComputeService@@YAXAEBU_GUID@@000@Z`
- size: `681`
- prototype: `void(ComputeService::VirtualMachine::NetworkHelpers *__hidden this, const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140025774`
- `0x1401cdb60`

## callees

- `0x14001629c`
- `0x140017040`
- `0x140017840`
- `0x140018d54`
- `0x14002ecd8`
- `0x14002f868`
- `0x14004249c`
- `0x140042d50`
- `0x140044974`
- `0x14006be0c`
- `0x140082ed0`
- `0x14008444c`
- `0x1400846fc`
- `0x1400847e0`
- `0x1400c40e0`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnCloseEndpoint` at `0x1400846b1`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnCloseEndpoint` at `0x1400846b1`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnOpenEndpoint` at `0x140084622`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnOpenEndpoint` at `0x140084622`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnModifyEndpoint` at `0x140084671`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnModifyEndpoint` at `0x140084671`

## string_xrefs

- `0x14008463c`: `onecore\vm\compute\management\orchestration\shared\vmconfig\networkhelpers.cpp`
- `0x14008468b`: `onecore\vm\compute\management\orchestration\shared\vmconfig\networkhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ComputeService::VirtualMachine::NetworkHelpers::AddEndpointSwitchPort(
        ComputeService::VirtualMachine::NetworkHelpers *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  __int128 *v5; // r8
  __int128 *v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rbx
  void *v9; // rax
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // rax
  HRESULT v13; // eax
  _OWORD Src[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v16; // [rsp+50h] [rbp-B0h]
  std::_Ref_count_base *v17; // [rsp+60h] [rbp-A0h]
  std::_Ref_count_base *v18; // [rsp+70h] [rbp-90h]
  _BYTE v19[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v20[32]; // [rsp+A8h] [rbp-58h] BYREF
  HCN_ENDPOINT Endpoint; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v22; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v23[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v24; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v25[2]; // [rsp+110h] [rbp+10h] BYREF
  int v26; // [rsp+130h] [rbp+30h]
  int v27; // [rsp+134h] [rbp+34h]
  int v28; // [rsp+138h] [rbp+38h]
  int v29; // [rsp+13Ch] [rbp+3Ch]
  _OWORD v30[3]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v31; // [rsp+170h] [rbp+70h]
  int v32; // [rsp+178h] [rbp+78h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  memset(v23, 0, sizeof(v23));
  std::wstring::_Construct_empty(v23);
  v24 = *v5;
  v22 = *v6;
  v8 = Vml::GuidToString(v15, v7, 0);
  memset(Src, 0, sizeof(Src));
  std::wstring::_Construct_empty(Src);
  Vml::VmGuid::ToString(&v24, Src, 0);
  v9 = (void *)std::wstring::_Append<unsigned short>(Src);
  std::wstring::wstring(v20, v9);
  std::wstring::wstring(v19, v10, v20, v8);
  std::wstring::operator=(v23, v19);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v19);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v20);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)Src);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v15);
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct_empty(v25);
  v27 = 0;
  v29 = 0;
  memset_0(v30, 0, 0x40u);
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v32 = 0;
  v28 = 0;
  v26 = 0;
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
    v15,
    &v22);
  Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(
    v30,
    v15);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  Endpoint = 0;
  v11 = HcnOpenEndpoint(a4, &Endpoint, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\networkhelpers.cpp",
      (const char *)(unsigned int)v11,
      3);
  v12 = Marshal::ToJson<HNS::Schema::Network::Endpoint::ModifyEndpointSettingRequest &,>(v15, v25);
  if ( *(_QWORD *)(v12 + 24) > 7u )
    v12 = *(_QWORD *)v12;
  v13 = HcnModifyEndpoint(Endpoint, (PCWSTR)v12, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmconfig\\networkhelpers.cpp",
      (const char *)(unsigned int)v13,
      3);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v15);
  if ( Endpoint )
    HcnCloseEndpoint(Endpoint);
  Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(v30);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v25);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
}

```

## disassembly

```asm
0x14008444c  push    rbp
0x14008444e  push    rbx
0x14008444f  push    rdi
0x140084450  lea     rbp, [rsp-90h]
0x140084458  sub     rsp, 190h
0x14008445f  mov     rax, cs:__security_cookie
0x140084466  xor     rax, rsp
0x140084469  mov     [rbp+0A0h+var_20], rax
0x140084470  mov     rdi, r9
0x140084473  mov     r9, r8
0x140084476  mov     r8, rcx
0x140084479  mov     [rsp+1A0h+var_180], 0
0x140084481  xorps   xmm0, xmm0
0x140084484  xorps   xmm1, xmm1
0x140084487  movups  [rbp+0A0h+var_C0], xmm1
0x14008448b  movdqa  [rbp+0A0h+var_B0], xmm0
0x140084490  lea     rcx, [rbp+0A0h+var_C0]
0x140084494  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140084499  nop
0x14008449a  movups  xmm1, xmmword ptr [r8]
0x14008449e  movdqu  [rbp+0A0h+var_A0], xmm1
0x1400844a3  movups  xmm0, xmmword ptr [rdx]
0x1400844a6  movdqu  [rbp+0A0h+var_D0], xmm0
0x1400844ab  xor     r8d, r8d
0x1400844ae  mov     rdx, r9
0x1400844b1  lea     rcx, [rsp+1A0h+var_158]
0x1400844b6  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400844bb  mov     rbx, rax
0x1400844be  xorps   xmm0, xmm0
0x1400844c1  movups  [rsp+1A0h+Src], xmm0
0x1400844c6  xorps   xmm1, xmm1
0x1400844c9  movdqu  [rsp+1A0h+var_168], xmm1
0x1400844cf  lea     rcx, [rsp+1A0h+Src]
0x1400844d4  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400844d9  mov     [rsp+1A0h+var_180], 1
0x1400844e1  xor     r8d, r8d
0x1400844e4  lea     rdx, [rsp+1A0h+Src]
0x1400844e9  lea     rcx, [rbp+0A0h+var_A0]
0x1400844ed  call    ?ToString@VmGuid@Vml@@SAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Vml::VmGuid::ToString(_GUID const &,std::wstring &,int)
0x1400844f2  mov     r8d, 2
0x1400844f8  lea     rdx, asc_1402FEE20; "--"
0x1400844ff  lea     rcx, [rsp+1A0h+Src]; Src
0x140084504  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x140084509  mov     rdx, rax; void *
0x14008450c  lea     rcx, [rbp+0A0h+var_F8]; void *
0x140084510  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x140084515  mov     [rsp+1A0h+var_180], 3; int
0x14008451d  mov     r9, rbx
0x140084520  lea     r8, [rbp+0A0h+var_F8]
0x140084524  lea     rcx, [rbp+0A0h+var_118]
0x140084528  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x14008452d  lea     rdx, [rbp+0A0h+var_118]
0x140084531  lea     rcx, [rbp+0A0h+var_C0]
0x140084535  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008453a  lea     rcx, [rbp+0A0h+var_118]; this
0x14008453e  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140084543  nop
0x140084544  lea     rcx, [rbp+0A0h+var_F8]; this
0x140084548  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008454d  nop
0x14008454e  lea     rcx, [rsp+1A0h+Src]; this
0x140084553  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140084558  nop
0x140084559  lea     rcx, [rsp+1A0h+var_158]; this
0x14008455e  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140084563  xorps   xmm0, xmm0
0x140084566  movups  [rbp+0A0h+var_90], xmm0
0x14008456a  xorps   xmm1, xmm1
0x14008456d  movdqa  [rbp+0A0h+var_80], xmm1
0x140084572  lea     rcx, [rbp+0A0h+var_90]
0x140084576  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x14008457b  xor     ecx, ecx
0x14008457d  mov     [rbp+0A0h+var_6C], ecx
0x140084580  xor     eax, eax
0x140084582  mov     [rbp+0A0h+var_64], eax
0x140084585  xor     edx, edx; Val
0x140084587  lea     r8d, [rcx+40h]; Size
0x14008458b  lea     rcx, [rbp+0A0h+var_60]; void *
0x14008458f  call    memset_0
0x140084594  xorps   xmm0, xmm0
0x140084597  movdqa  [rbp+0A0h+var_60], xmm0
0x14008459c  xorps   xmm1, xmm1
0x14008459f  movdqa  [rbp+0A0h+var_50], xmm1
0x1400845a4  movdqa  [rbp+0A0h+var_40], xmm0
0x1400845a9  mov     [rbp+0A0h+var_30], 0
0x1400845b1  mov     [rbp+0A0h+var_28], 0
0x1400845b8  mov     [rbp+0A0h+var_68], 0
0x1400845bf  mov     [rbp+0A0h+var_70], 0
0x1400845c6  lea     rdx, [rbp+0A0h+var_D0]
0x1400845ca  lea     rcx, [rsp+1A0h+var_158]
0x1400845cf  call    ??$?0AEAUVmEndpointRequest@Endpoint@Network@Schema@HNS@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEAUVmEndpointRequest@Endpoint@Network@Schema@HNS@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(HNS::Schema::Network::Endpoint::VmEndpointRequest &)
0x1400845d4  lea     rdx, [rsp+1A0h+var_158]
0x1400845d9  lea     rcx, [rbp+0A0h+var_60]
0x1400845dd  call    ??4?$DelayedBase@UCacheQueryStatsResponse@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAAAEAV01@$$QEAV01@@Z; Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits>::operator=(Marshal::DelayedBase<Schema::Responses::System::CacheQueryStatsResponse,Marshal::Details::DelayedJsonTraits> &&)
0x1400845e2  mov     rcx, [rsp+1A0h+var_130]; this
0x1400845e7  test    rcx, rcx
0x1400845ea  jz      short loc_1400845F1
0x1400845ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400845f1  mov     rcx, [rsp+1A0h+var_140]; this
0x1400845f6  test    rcx, rcx
0x1400845f9  jz      short loc_140084600
0x1400845fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140084600  mov     rcx, [rsp+1A0h+var_150]; this
0x140084605  test    rcx, rcx
0x140084608  jz      short loc_140084610
0x14008460a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14008460f  nop
0x140084610  mov     [rbp+0A0h+Endpoint], 0
0x140084618  xor     r8d, r8d; ErrorRecord
0x14008461b  lea     rdx, [rbp+0A0h+Endpoint]; Endpoint
0x14008461f  mov     rcx, rdi; Id
0x140084622  call    cs:__imp_HcnOpenEndpoint
0x140084629  nop     dword ptr [rax+rax+00h]
0x14008462e  mov     rcx, [rbp+0A8h]; this
0x140084635  test    eax, eax
0x140084637  jns     short loc_14008464E
0x140084639  mov     r9d, eax; char *
0x14008463c  lea     r8, aOnecoreVmCompu_73; "onecore\\vm\\compute\\management\\orche"...
0x140084643  mov     edx, 0BAh; void *
0x140084648  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008464e  lea     rdx, [rbp+0A0h+var_90]
0x140084652  lea     rcx, [rsp+1A0h+var_158]
0x140084657  call    ??$ToJson@AEAUModifyEndpointSettingRequest@Endpoint@Network@Schema@HNS@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUModifyEndpointSettingRequest@Endpoint@Network@Schema@HNS@@W4MarshalFlags@0@@Z; Marshal::ToJson<HNS::Schema::Network::Endpoint::ModifyEndpointSettingRequest &,>(HNS::Schema::Network::Endpoint::ModifyEndpointSettingRequest &,Marshal::MarshalFlags)
0x14008465c  nop
0x14008465d  cmp     qword ptr [rax+18h], 7
0x140084662  jbe     short loc_140084667
0x140084664  mov     rax, [rax]
0x140084667  xor     r8d, r8d; ErrorRecord
0x14008466a  mov     rdx, rax; Settings
0x14008466d  mov     rcx, [rbp+0A0h+Endpoint]; Endpoint
0x140084671  call    cs:__imp_HcnModifyEndpoint
0x140084678  nop     dword ptr [rax+rax+00h]
0x14008467d  mov     rcx, [rbp+0A8h]; this
0x140084684  test    eax, eax
0x140084686  jns     short loc_14008469D
0x140084688  mov     r9d, eax; char *
0x14008468b  lea     r8, aOnecoreVmCompu_73; "onecore\\vm\\compute\\management\\orche"...
0x140084692  mov     edx, 0BBh; void *
0x140084697  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008469d  lea     rcx, [rsp+1A0h+var_158]; this
0x1400846a2  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400846a7  nop
0x1400846a8  mov     rcx, [rbp+0A0h+Endpoint]; Endpoint
0x1400846ac  test    rcx, rcx
0x1400846af  jz      short loc_1400846BE
0x1400846b1  call    cs:__imp_HcnCloseEndpoint
0x1400846b8  nop     dword ptr [rax+rax+00h]
0x1400846bd  nop
0x1400846be  lea     rcx, [rbp+0A0h+var_60]
0x1400846c2  call    ??1?$DelayedBase@UMemoryTopology@System@Responses@Schema@@UDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(void)
0x1400846c7  lea     rcx, [rbp+0A0h+var_90]; this
0x1400846cb  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400846d0  nop
0x1400846d1  lea     rcx, [rbp+0A0h+var_C0]; this
0x1400846d5  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400846da  mov     rcx, [rbp+0A0h+var_20]
0x1400846e1  xor     rcx, rsp; StackCookie
0x1400846e4  call    __security_check_cookie
0x1400846e9  add     rsp, 190h
0x1400846f0  pop     rdi
0x1400846f1  pop     rbx
0x1400846f2  pop     rbp
0x1400846f3  retn
```
