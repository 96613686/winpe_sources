# ComputeService::Net::HnsDetachEndpoint(_GUID const &,ushort const *)

- ea: `0x1400edd94`
- end: `0x1400edfd6`
- name: `?HnsDetachEndpoint@Net@ComputeService@@YAXAEBU_GUID@@PEBG@Z`
- size: `578`
- prototype: `void __fastcall(ComputeService::Net *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140089c30`
- `0x14009aa60`

## callees

- `0x140017040`
- `0x14001d490`
- `0x14002450c`
- `0x1400421f0`
- `0x14004249c`
- `0x140044974`
- `0x140071d04`
- `0x1400c40e0`
- `0x1400d4520`
- `0x1400d6a88`
- `0x1400edd94`
- `0x1400edfdc`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400edfaa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400edfaa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400ede22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400ede22`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400eddc0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400eddc0`

## string_xrefs

- `0x1400eddd7`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400ede39`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400edf65`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ComputeService::Net::HnsDetachEndpoint(
        ComputeService::Net *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  HRESULT v5; // eax
  char v6; // si
  HRESULT v7; // eax
  __int64 v8; // rax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, const wchar_t *, _QWORD *, _QWORD *); // rbx
  _QWORD *v11; // r9
  _QWORD *v12; // r8
  unsigned int v13; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  _BYTE v16[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[32]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v18; // [rsp+78h] [rbp-88h] BYREF
  int v19[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v20[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v21[5]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v22[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-10h]
  _BYTE v24[40]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27C,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v6 = 1;
  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v7 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v18);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v7,
      ppva);
  std::wstring::wstring(v22);
  v23 = 0;
  std::wstring::wstring(v24);
  v8 = std::wstring::wstring(v16, a2);
  std::wstring::operator=(v22, v8);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v16);
  LODWORD(v23) = 0;
  Marshal::ToJson<Config::Network::HNS::v2::EndpointAttachDetachRequest &,>(v21, v22);
  *(_QWORD *)v19 = 0;
  Vml::GuidToString(v17, this, 0);
  std::operator+<unsigned short>(v16);
  std::operator+<unsigned short>(v20);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v16);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v17);
  v9 = v18;
  v10 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, _QWORD *))(*(_QWORD *)v18 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v19,
    0);
  v11 = v21;
  if ( v21[3] > 7u )
    v11 = (_QWORD *)v21[0];
  v12 = v20;
  if ( v20[3] > 7u )
    v12 = (_QWORD *)v20[0];
  v13 = v10(v9, L"POST", v12, v11);
  if ( (int)(v13 + 0x80000000) < 0 || v13 == -2147023728 )
    v6 = 0;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28B,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)v13,
      (int)v19);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v21);
  Schema::Containers::Resources::MappedDirectory::~MappedDirectory((Schema::Containers::Resources::MappedDirectory *)v22);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  CoUninitialize();
}

```

## disassembly

```asm
0x1400edd94  mov     [rsp-8+arg_10], rbx
0x1400edd99  push    rbp
0x1400edd9a  push    rsi
0x1400edd9b  push    rdi
0x1400edd9c  lea     rbp, [rsp-30h]
0x1400edda1  sub     rsp, 130h
0x1400edda8  mov     rax, cs:__security_cookie
0x1400eddaf  xor     rax, rsp
0x1400eddb2  mov     [rbp+40h+var_20], rax
0x1400eddb6  mov     rdi, rdx
0x1400eddb9  mov     rbx, rcx
0x1400eddbc  xor     edx, edx; dwCoInit
0x1400eddbe  xor     ecx, ecx; pvReserved
0x1400eddc0  call    cs:__imp_CoInitializeEx
0x1400eddc7  nop     dword ptr [rax+rax+00h]
0x1400eddcc  mov     rcx, [rbp+48h]; this
0x1400eddd0  test    eax, eax
0x1400eddd2  jns     short loc_1400EDDE9
0x1400eddd4  mov     r9d, eax; char *
0x1400eddd7  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400eddde  mov     edx, 27Ch; void *
0x1400edde3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400edde9  mov     sil, 1
0x1400eddec  mov     [rsp+140h+var_10F], sil
0x1400eddf1  mov     [rsp+140h+var_C8], 0
0x1400eddfa  lea     rcx, [rsp+140h+var_C8]
0x1400eddff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400ede04  lea     rax, [rsp+140h+var_C8]
0x1400ede09  mov     qword ptr [rsp+140h+ppv], rax; int
0x1400ede0e  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x1400ede15  xor     edx, edx; pUnkOuter
0x1400ede17  lea     r8d, [rdx+17h]; dwClsContext
0x1400ede1b  lea     rcx, rclsid; rclsid
0x1400ede22  call    cs:__imp_CoCreateInstance
0x1400ede29  nop     dword ptr [rax+rax+00h]
0x1400ede2e  mov     rcx, [rbp+48h]; this
0x1400ede32  test    eax, eax
0x1400ede34  jns     short loc_1400EDE4B
0x1400ede36  mov     r9d, eax; char *
0x1400ede39  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400ede40  mov     edx, 280h; void *
0x1400ede45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ede4b  lea     rcx, [rbp+40h+var_70]; void *
0x1400ede4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400ede54  mov     [rbp+40h+var_50], 0
0x1400ede5c  lea     rcx, [rbp+40h+var_48]; void *
0x1400ede60  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400ede65  nop
0x1400ede66  mov     rdx, rdi
0x1400ede69  lea     rcx, [rsp+140h+var_108]
0x1400ede6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400ede73  mov     rdx, rax
0x1400ede76  lea     rcx, [rbp+40h+var_70]
0x1400ede7a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400ede7f  lea     rcx, [rsp+140h+var_108]; this
0x1400ede84  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400ede89  mov     dword ptr [rbp+40h+var_50], 0
0x1400ede90  lea     rdx, [rbp+40h+var_70]
0x1400ede94  lea     rcx, [rbp+40h+var_98]
0x1400ede98  call    ??$ToJson@AEAUEndpointAttachDetachRequest@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUEndpointAttachDetachRequest@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::EndpointAttachDetachRequest &,>(Config::Network::HNS::v2::EndpointAttachDetachRequest &,Marshal::MarshalFlags)
0x1400ede9d  nop
0x1400ede9e  mov     qword ptr [rbp+40h+var_C0], 0
0x1400edea6  xor     r8d, r8d
0x1400edea9  mov     rdx, rbx
0x1400edeac  lea     rcx, [rsp+140h+var_E8]
0x1400edeb1  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400edeb6  nop
0x1400edeb7  mov     r8, rax
0x1400edeba  lea     rdx, aEndpoints; "/endpoints/"
0x1400edec1  lea     rcx, [rsp+140h+var_108]; void *
0x1400edec6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1400edecb  nop
0x1400edecc  lea     r8, aDetach; "/detach"
0x1400eded3  mov     rdx, rax
0x1400eded6  lea     rcx, [rbp+40h+var_B8]; void *
0x1400ededa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1400ededf  nop
0x1400edee0  lea     rcx, [rsp+140h+var_108]; this
0x1400edee5  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edeea  nop
0x1400edeeb  lea     rcx, [rsp+140h+var_E8]; this
0x1400edef0  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edef5  mov     rdi, [rsp+140h+var_C8]
0x1400edefa  mov     rax, [rdi]
0x1400edefd  mov     rbx, [rax+38h]
0x1400edf01  xor     edx, edx
0x1400edf03  lea     rcx, [rbp+40h+var_C0]
0x1400edf07  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400edf0c  lea     r9, [rbp+40h+var_98]
0x1400edf10  cmp     [rbp+40h+var_80], 7
0x1400edf15  cmova   r9, [rbp+40h+var_98]
0x1400edf1a  lea     r8, [rbp+40h+var_B8]
0x1400edf1e  cmp     [rbp+40h+var_A0], 7
0x1400edf23  cmova   r8, [rbp+40h+var_B8]
0x1400edf28  lea     rax, [rbp+40h+var_C0]
0x1400edf2c  mov     qword ptr [rsp+140h+ppv], rax; int
0x1400edf31  lea     rdx, aPost; "POST"
0x1400edf38  mov     rcx, rdi
0x1400edf3b  mov     rax, rbx
0x1400edf3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400edf43  mov     edx, 80000000h
0x1400edf48  lea     ecx, [rax+rdx]
0x1400edf4b  test    edx, ecx
0x1400edf4d  jnz     short loc_1400EDF56
0x1400edf4f  cmp     eax, 80070490h
0x1400edf54  jnz     short loc_1400EDF59
0x1400edf56  xor     sil, sil
0x1400edf59  mov     rcx, [rbp+48h]; this
0x1400edf5d  test    sil, sil
0x1400edf60  jz      short loc_1400EDF77
0x1400edf62  mov     r9d, eax; char *
0x1400edf65  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400edf6c  mov     edx, 28Bh; void *
0x1400edf71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400edf77  lea     rcx, [rbp+40h+var_B8]; this
0x1400edf7b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edf80  nop
0x1400edf81  lea     rcx, [rbp+40h+var_C0]
0x1400edf85  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400edf8a  nop
0x1400edf8b  lea     rcx, [rbp+40h+var_98]; this
0x1400edf8f  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edf94  nop
0x1400edf95  lea     rcx, [rbp+40h+var_70]; this
0x1400edf99  call    ??1MappedDirectory@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedDirectory::~MappedDirectory(void)
0x1400edf9e  nop
0x1400edf9f  lea     rcx, [rsp+140h+var_C8]
0x1400edfa4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400edfa9  nop
0x1400edfaa  call    cs:__imp_CoUninitialize
0x1400edfb1  nop     dword ptr [rax+rax+00h]
0x1400edfb6  mov     rcx, [rbp+40h+var_20]
0x1400edfba  xor     rcx, rsp; StackCookie
0x1400edfbd  call    __security_check_cookie
0x1400edfc2  mov     rbx, [rsp+140h+arg_10]
0x1400edfca  add     rsp, 130h
0x1400edfd1  pop     rdi
0x1400edfd2  pop     rsi
0x1400edfd3  pop     rbp
0x1400edfd4  retn
```
