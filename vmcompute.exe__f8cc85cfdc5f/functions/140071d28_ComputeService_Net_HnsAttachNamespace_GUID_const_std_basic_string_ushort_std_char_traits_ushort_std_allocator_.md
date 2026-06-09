# ComputeService::Net::HnsAttachNamespace(_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140071d28`
- end: `0x14007202d`
- name: `?HnsAttachNamespace@Net@ComputeService@@YAKAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140070d60`
- `0x140288aa0`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001bc28`
- `0x14002450c`
- `0x1400421f0`
- `0x14004249c`
- `0x14005bb24`
- `0x140070350`
- `0x140070d38`
- `0x140071d04`
- `0x140071d28`
- `0x140073a74`
- `0x1400c40e0`
- `0x1400d6a88`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x140134048`
- `0x140219b98`
- `0x140219ce8`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140071ffc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140071ffc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140071db7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140071db7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140071d5a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140071d5a`

## string_xrefs

- `0x140071d76`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140071dd1`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140071ebb`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140071f81`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ComputeService::Net::HnsAttachNamespace(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  HRESULT v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, const wchar_t *, _QWORD *, _QWORD *); // rbx
  _QWORD *v8; // r9
  _QWORD *v9; // r8
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  const char *v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ebx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  _BYTE v19[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v21[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v22; // [rsp+90h] [rbp-70h] BYREF
  int v23[2]; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v24; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-38h]
  _QWORD v27[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v28[4]; // [rsp+F0h] [rbp-10h] BYREF
  char v29[8]; // [rsp+110h] [rbp+10h] BYREF
  char *v30[4]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v31; // [rsp+138h] [rbp+38h] BYREF
  __int128 v32; // [rsp+140h] [rbp+40h]
  __int128 v33; // [rsp+150h] [rbp+50h]
  __int128 v34; // [rsp+160h] [rbp+60h]
  int v35; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v4 = CoInitializeEx(0, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v24 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v5 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v24);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  std::wstring::wstring(v25);
  v26 = 0;
  std::wstring::operator=(v25, a2);
  LODWORD(v26) = 0;
  Marshal::ToJson<Config::Network::HNS::v2::NamespaceAttachDetachRequest &,>(v28, v25);
  *(_QWORD *)v23 = 0;
  Vml::GuidToString(v19, a1, 0);
  std::operator+<unsigned short>(v21);
  std::operator+<unsigned short>(v27);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v21);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v19);
  v6 = v24;
  v7 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, _QWORD *))(*(_QWORD *)v24 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v23,
    0);
  v8 = v28;
  if ( v28[3] > 7u )
    v8 = (_QWORD *)v28[0];
  v9 = v27;
  if ( v27[3] > 7u )
    v9 = (_QWORD *)v27[0];
  v10 = v7(v6, L"POST", v9, v8);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v10,
      (int)v23);
  v29[0] = 0;
  std::wstring::wstring(v30);
  memset_0(&v31, 0, 0x40u);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(*(_QWORD *)v23 + 2 * v11) );
  v21[0] = *(_QWORD *)v23;
  v21[1] = v11;
  v12 = Marshal::FromJson<Config::Network::HNS::v2::Response,>(v19, v21, v29);
  Marshal::ThrowOnUnmarshalError(v12, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v20);
  v13 = (const char *)v30;
  if ( v30[3] > (char *)7 )
    v13 = v30[0];
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x1C8,
    (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
    (const char *)0x800704CFLL,
    v29[0],
    (bool)"Error attaching HNS namespace %ws",
    v13);
  v22 = 0;
  v14 = Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Network::HNS::v2::NamespaceAttachResponse>(
          &v31,
          v19,
          &v22);
  Marshal::ThrowOnUnmarshalError(v14, 3224830221LL);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v20);
  v15 = v22;
  Schema::Requests::Guest::NetworkModifySettingRequest::~NetworkModifySettingRequest((Schema::Requests::Guest::NetworkModifySettingRequest *)v29);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v28);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  CoUninitialize();
  return v15;
}

```

## disassembly

```asm
0x140071d28  mov     [rsp-8+arg_10], rbx
0x140071d2d  push    rbp
0x140071d2e  push    rsi
0x140071d2f  push    rdi
0x140071d30  lea     rbp, [rsp-90h]
0x140071d38  sub     rsp, 190h
0x140071d3f  mov     rax, cs:__security_cookie
0x140071d46  xor     rax, rsp
0x140071d49  mov     [rbp+0A0h+var_20], rax
0x140071d50  mov     rdi, rdx
0x140071d53  mov     rbx, rcx
0x140071d56  xor     edx, edx; dwCoInit
0x140071d58  xor     ecx, ecx; pvReserved
0x140071d5a  call    cs:__imp_CoInitializeEx
0x140071d61  nop     dword ptr [rax+rax+00h]
0x140071d66  mov     rcx, [rbp+0A8h]; this
0x140071d6d  xor     esi, esi
0x140071d6f  test    eax, eax
0x140071d71  jns     short loc_140071D88
0x140071d73  mov     r9d, eax; char *
0x140071d76  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140071d7d  mov     edx, 1B5h; void *
0x140071d82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140071d88  mov     [rsp+1A0h+var_15F], 1
0x140071d8d  mov     [rbp+0A0h+var_100], rsi
0x140071d91  lea     rcx, [rbp+0A0h+var_100]
0x140071d95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140071d9a  lea     rax, [rbp+0A0h+var_100]
0x140071d9e  mov     [rsp+1A0h+ppv], rax; int
0x140071da3  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x140071daa  xor     edx, edx; pUnkOuter
0x140071dac  lea     r8d, [rdx+17h]; dwClsContext
0x140071db0  lea     rcx, rclsid; rclsid
0x140071db7  call    cs:__imp_CoCreateInstance
0x140071dbe  nop     dword ptr [rax+rax+00h]
0x140071dc3  mov     rcx, [rbp+0A8h]; this
0x140071dca  test    eax, eax
0x140071dcc  jns     short loc_140071DE3
0x140071dce  mov     r9d, eax; char *
0x140071dd1  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140071dd8  mov     edx, 1B9h; void *
0x140071ddd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140071de3  lea     rcx, [rbp+0A0h+var_F8]; void *
0x140071de7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071dec  mov     [rbp+0A0h+var_D8], rsi
0x140071df0  mov     rdx, rdi
0x140071df3  lea     rcx, [rbp+0A0h+var_F8]
0x140071df7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140071dfc  mov     dword ptr [rbp+0A0h+var_D8], esi
0x140071dff  lea     rdx, [rbp+0A0h+var_F8]
0x140071e03  lea     rcx, [rbp+0A0h+var_B0]
0x140071e07  call    ??$ToJson@AEAUNamespaceAttachDetachRequest@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUNamespaceAttachDetachRequest@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::NamespaceAttachDetachRequest &,>(Config::Network::HNS::v2::NamespaceAttachDetachRequest &,Marshal::MarshalFlags)
0x140071e0c  nop
0x140071e0d  mov     qword ptr [rbp+0A0h+var_108], rsi
0x140071e11  xor     r8d, r8d
0x140071e14  mov     rdx, rbx
0x140071e17  lea     rcx, [rsp+1A0h+var_158]
0x140071e1c  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x140071e21  nop
0x140071e22  mov     r8, rax
0x140071e25  lea     rdx, aNamespaces; "/namespaces/"
0x140071e2c  lea     rcx, [rsp+1A0h+var_130]; void *
0x140071e31  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x140071e36  nop
0x140071e37  lea     r8, aAttach; "/attach"
0x140071e3e  mov     rdx, rax
0x140071e41  lea     rcx, [rbp+0A0h+var_D0]; void *
0x140071e45  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140071e4a  nop
0x140071e4b  lea     rcx, [rsp+1A0h+var_130]; this
0x140071e50  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140071e55  nop
0x140071e56  lea     rcx, [rsp+1A0h+var_158]; this
0x140071e5b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140071e60  mov     rdi, [rbp+0A0h+var_100]
0x140071e64  mov     rax, [rdi]
0x140071e67  mov     rbx, [rax+38h]
0x140071e6b  xor     edx, edx
0x140071e6d  lea     rcx, [rbp+0A0h+var_108]
0x140071e71  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140071e76  lea     r9, [rbp+0A0h+var_B0]
0x140071e7a  cmp     [rbp+0A0h+var_98], 7
0x140071e7f  cmova   r9, [rbp+0A0h+var_B0]
0x140071e84  lea     r8, [rbp+0A0h+var_D0]
0x140071e88  cmp     [rbp+0A0h+var_B8], 7
0x140071e8d  cmova   r8, [rbp+0A0h+var_D0]
0x140071e92  lea     rax, [rbp+0A0h+var_108]
0x140071e96  mov     [rsp+1A0h+ppv], rax; int
0x140071e9b  lea     rdx, aPost; "POST"
0x140071ea2  mov     rcx, rdi
0x140071ea5  mov     rax, rbx
0x140071ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071ead  mov     rcx, [rbp+0A8h]; this
0x140071eb4  test    eax, eax
0x140071eb6  jns     short loc_140071ECD
0x140071eb8  mov     r9d, eax; char *
0x140071ebb  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140071ec2  mov     edx, 1C2h; void *
0x140071ec7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140071ecd  mov     [rbp+0A0h+var_90], sil
0x140071ed1  lea     rcx, [rbp+0A0h+var_88]; void *
0x140071ed5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140071eda  xor     edx, edx; Val
0x140071edc  lea     r8d, [rdx+40h]; Size
0x140071ee0  lea     rcx, [rbp+0A0h+var_68]; void *
0x140071ee4  call    memset_0
0x140071ee9  mov     [rbp+0A0h+var_68], rsi
0x140071eed  xorps   xmm0, xmm0
0x140071ef0  movdqa  [rbp+0A0h+var_60], xmm0
0x140071ef5  xorps   xmm1, xmm1
0x140071ef8  movdqa  [rbp+0A0h+var_50], xmm1
0x140071efd  movdqa  [rbp+0A0h+var_40], xmm0
0x140071f02  mov     [rbp+0A0h+var_30], esi
0x140071f05  mov     rcx, qword ptr [rbp+0A0h+var_108]
0x140071f09  or      rax, 0FFFFFFFFFFFFFFFFh
0x140071f0d  inc     rax
0x140071f10  cmp     [rcx+rax*2], si
0x140071f14  jnz     short loc_140071F0D
0x140071f16  mov     [rsp+1A0h+var_130], rcx
0x140071f1b  mov     [rsp+1A0h+var_128], rax
0x140071f20  lea     r8, [rbp+0A0h+var_90]
0x140071f24  lea     rdx, [rsp+1A0h+var_130]
0x140071f29  lea     rcx, [rsp+1A0h+var_158]
0x140071f2e  call    ??$FromJson@UResponse@v2@HNS@Network@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEAUResponse@v2@HNS@Network@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Config::Network::HNS::v2::Response,>(std::basic_string_view<ushort>,Config::Network::HNS::v2::Response *,Marshal::UnmarshalFlags)
0x140071f33  nop
0x140071f34  mov     ebx, 0C037010Dh
0x140071f39  mov     edx, ebx
0x140071f3b  mov     rcx, rax
0x140071f3e  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x140071f43  nop
0x140071f44  lea     rcx, [rsp+1A0h+var_150]
0x140071f49  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140071f4e  lea     rax, [rbp+0A0h+var_88]
0x140071f52  cmp     [rbp+0A0h+var_70], 7
0x140071f57  cmova   rax, [rbp+0A0h+var_88]
0x140071f5c  mov     rcx, [rbp+0A8h]; this
0x140071f63  mov     [rsp+1A0h+var_170], rax; char *
0x140071f68  lea     rax, aErrorAttaching; "Error attaching HNS namespace %ws"
0x140071f6f  mov     qword ptr [rsp+1A0h+var_178], rax; bool
0x140071f74  mov     al, [rbp+0A0h+var_90]
0x140071f77  mov     byte ptr [rsp+1A0h+ppv], al; char
0x140071f7b  mov     r9d, 800704CFh; char *
0x140071f81  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140071f88  mov     edx, 1C8h; void *
0x140071f8d  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x140071f92  mov     [rbp+0A0h+var_110], esi
0x140071f95  lea     r8, [rbp+0A0h+var_110]
0x140071f99  lea     rdx, [rsp+1A0h+var_158]
0x140071f9e  lea     rcx, [rbp+0A0h+var_68]
0x140071fa2  call    ??$Unmarshal@UNamespaceAttachResponse@v2@HNS@Network@Config@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUNamespaceAttachResponse@v2@HNS@Network@Config@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Config::Network::HNS::v2::NamespaceAttachResponse>(Config::Network::HNS::v2::NamespaceAttachResponse *)
0x140071fa7  nop
0x140071fa8  mov     edx, ebx
0x140071faa  mov     rcx, rax
0x140071fad  call    ?ThrowOnUnmarshalError@Marshal@@YAXAEBU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@J@Z; Marshal::ThrowOnUnmarshalError(std::pair<bool,std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>> const &,long)
0x140071fb2  nop
0x140071fb3  lea     rcx, [rsp+1A0h+var_150]
0x140071fb8  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140071fbd  mov     ebx, [rbp+0A0h+var_110]
0x140071fc0  lea     rcx, [rbp+0A0h+var_90]; this
0x140071fc4  call    ??1NetworkModifySettingRequest@Guest@Requests@Schema@@QEAA@XZ; Schema::Requests::Guest::NetworkModifySettingRequest::~NetworkModifySettingRequest(void)
0x140071fc9  nop
0x140071fca  lea     rcx, [rbp+0A0h+var_D0]; this
0x140071fce  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140071fd3  nop
0x140071fd4  lea     rcx, [rbp+0A0h+var_108]
0x140071fd8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140071fdd  nop
0x140071fde  lea     rcx, [rbp+0A0h+var_B0]; this
0x140071fe2  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140071fe7  nop
0x140071fe8  lea     rcx, [rbp+0A0h+var_F8]; this
0x140071fec  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140071ff1  nop
0x140071ff2  lea     rcx, [rbp+0A0h+var_100]
0x140071ff6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140071ffb  nop
0x140071ffc  call    cs:__imp_CoUninitialize
0x140072003  nop     dword ptr [rax+rax+00h]
0x140072008  mov     eax, ebx
0x14007200a  mov     rcx, [rbp+0A0h+var_20]
0x140072011  xor     rcx, rsp; StackCookie
0x140072014  call    __security_check_cookie
0x140072019  mov     rbx, [rsp+1A0h+arg_10]
0x140072021  add     rsp, 190h
0x140072028  pop     rdi
0x140072029  pop     rsi
0x14007202a  pop     rbp
0x14007202b  retn
```
