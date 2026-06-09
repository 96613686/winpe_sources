# ComputeService::Net::HnsAttachEndpoint(uint,_GUID const &,ushort const *)

- ea: `0x1400edb58`
- end: `0x1400edd8b`
- name: `?HnsAttachEndpoint@Net@ComputeService@@YAXIAEBU_GUID@@PEBG@Z`
- size: `563`
- prototype: `void __fastcall(ComputeService::Net *__hidden this, unsigned int, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140070d60`
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
- `0x1400edb58`
- `0x1400edfdc`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400edd5f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400edd5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400edbe5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400edbe5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400edb86`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400edb86`

## string_xrefs

- `0x1400edb9d`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400edbfc`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x1400edd1a`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ComputeService::Net::HnsAttachEndpoint(
        ComputeService::Net *this,
        __int64 a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4)
{
  __int16 v6; // bx
  HRESULT v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rax
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, const wchar_t *, _QWORD *, _QWORD *); // rbx
  _QWORD *v12; // r9
  _QWORD *v13; // r8
  int v14; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  _BYTE v17[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v19; // [rsp+78h] [rbp-88h] BYREF
  int v20[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v21[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v22[5]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v23[32]; // [rsp+D0h] [rbp-30h] BYREF
  int v24; // [rsp+F0h] [rbp-10h]
  __int16 v25; // [rsp+F4h] [rbp-Ch]
  __int16 v26; // [rsp+F6h] [rbp-Ah]
  _BYTE v27[40]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v6 = (__int16)this;
  v7 = CoInitializeEx(0, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v19 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v8 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v19);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v8,
      ppva);
  std::wstring::wstring(v23);
  v24 = 0;
  v26 = 0;
  std::wstring::wstring(v27);
  v25 = v6;
  v9 = std::wstring::wstring(v17, a3);
  std::wstring::operator=(v23, v9);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v17);
  v24 = 0;
  Marshal::ToJson<Config::Network::HNS::v2::EndpointAttachDetachRequest &,>(v22, v23);
  *(_QWORD *)v20 = 0;
  Vml::GuidToString(v18, a2, 0);
  std::operator+<unsigned short>(v17);
  std::operator+<unsigned short>(v21);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v17);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v18);
  v10 = v19;
  v11 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, _QWORD *))(*(_QWORD *)v19 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v20,
    0);
  v12 = v22;
  if ( v22[3] > 7u )
    v12 = (_QWORD *)v22[0];
  v13 = v21;
  if ( v21[3] > 7u )
    v13 = (_QWORD *)v21[0];
  v14 = v11(v10, L"POST", v13, v12);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v14,
      (int)v20);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v22);
  Schema::Containers::Resources::MappedDirectory::~MappedDirectory((Schema::Containers::Resources::MappedDirectory *)v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  CoUninitialize();
}

```

## disassembly

```asm
0x1400edb58  mov     [rsp-8+arg_18], rbx
0x1400edb5d  push    rbp
0x1400edb5e  push    rsi
0x1400edb5f  push    rdi
0x1400edb60  lea     rbp, [rsp-30h]
0x1400edb65  sub     rsp, 130h
0x1400edb6c  mov     rax, cs:__security_cookie
0x1400edb73  xor     rax, rsp
0x1400edb76  mov     [rbp+40h+var_20], rax
0x1400edb7a  mov     rsi, r8
0x1400edb7d  mov     rdi, rdx
0x1400edb80  mov     ebx, ecx
0x1400edb82  xor     edx, edx; dwCoInit
0x1400edb84  xor     ecx, ecx; pvReserved
0x1400edb86  call    cs:__imp_CoInitializeEx
0x1400edb8d  nop     dword ptr [rax+rax+00h]
0x1400edb92  mov     rcx, [rbp+48h]; this
0x1400edb96  test    eax, eax
0x1400edb98  jns     short loc_1400EDBAF
0x1400edb9a  mov     r9d, eax; char *
0x1400edb9d  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400edba4  mov     edx, 212h; void *
0x1400edba9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400edbaf  mov     [rsp+140h+var_10F], 1
0x1400edbb4  mov     [rsp+140h+var_C8], 0
0x1400edbbd  lea     rcx, [rsp+140h+var_C8]
0x1400edbc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400edbc7  lea     rax, [rsp+140h+var_C8]
0x1400edbcc  mov     qword ptr [rsp+140h+ppv], rax; int
0x1400edbd1  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x1400edbd8  xor     edx, edx; pUnkOuter
0x1400edbda  lea     r8d, [rdx+17h]; dwClsContext
0x1400edbde  lea     rcx, rclsid; rclsid
0x1400edbe5  call    cs:__imp_CoCreateInstance
0x1400edbec  nop     dword ptr [rax+rax+00h]
0x1400edbf1  mov     rcx, [rbp+48h]; this
0x1400edbf5  test    eax, eax
0x1400edbf7  jns     short loc_1400EDC0E
0x1400edbf9  mov     r9d, eax; char *
0x1400edbfc  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400edc03  mov     edx, 216h; void *
0x1400edc08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400edc0e  lea     rcx, [rbp+40h+var_70]; void *
0x1400edc12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400edc17  mov     [rbp+40h+var_50], 0
0x1400edc1e  xor     eax, eax
0x1400edc20  mov     [rbp+40h+var_4A], ax
0x1400edc24  lea     rcx, [rbp+40h+var_48]; void *
0x1400edc28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400edc2d  nop
0x1400edc2e  mov     [rbp+40h+var_4C], bx
0x1400edc32  mov     rdx, rsi
0x1400edc35  lea     rcx, [rsp+140h+var_108]
0x1400edc3a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400edc3f  mov     rdx, rax
0x1400edc42  lea     rcx, [rbp+40h+var_70]
0x1400edc46  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400edc4b  lea     rcx, [rsp+140h+var_108]; this
0x1400edc50  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edc55  mov     [rbp+40h+var_50], 0
0x1400edc5c  lea     rdx, [rbp+40h+var_70]
0x1400edc60  lea     rcx, [rbp+40h+var_98]
0x1400edc64  call    ??$ToJson@AEAUEndpointAttachDetachRequest@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUEndpointAttachDetachRequest@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::EndpointAttachDetachRequest &,>(Config::Network::HNS::v2::EndpointAttachDetachRequest &,Marshal::MarshalFlags)
0x1400edc69  nop
0x1400edc6a  mov     qword ptr [rbp+40h+var_C0], 0
0x1400edc72  xor     r8d, r8d
0x1400edc75  mov     rdx, rdi
0x1400edc78  lea     rcx, [rsp+140h+var_E8]
0x1400edc7d  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400edc82  nop
0x1400edc83  mov     r8, rax
0x1400edc86  lea     rdx, aEndpoints; "/endpoints/"
0x1400edc8d  lea     rcx, [rsp+140h+var_108]; void *
0x1400edc92  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1400edc97  nop
0x1400edc98  lea     r8, aAttach; "/attach"
0x1400edc9f  mov     rdx, rax
0x1400edca2  lea     rcx, [rbp+40h+var_B8]; void *
0x1400edca6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1400edcab  nop
0x1400edcac  lea     rcx, [rsp+140h+var_108]; this
0x1400edcb1  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edcb6  nop
0x1400edcb7  lea     rcx, [rsp+140h+var_E8]; this
0x1400edcbc  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edcc1  mov     rdi, [rsp+140h+var_C8]
0x1400edcc6  mov     rax, [rdi]
0x1400edcc9  mov     rbx, [rax+38h]
0x1400edccd  xor     edx, edx
0x1400edccf  lea     rcx, [rbp+40h+var_C0]
0x1400edcd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400edcd8  lea     r9, [rbp+40h+var_98]
0x1400edcdc  cmp     [rbp+40h+var_80], 7
0x1400edce1  cmova   r9, [rbp+40h+var_98]
0x1400edce6  lea     r8, [rbp+40h+var_B8]
0x1400edcea  cmp     [rbp+40h+var_A0], 7
0x1400edcef  cmova   r8, [rbp+40h+var_B8]
0x1400edcf4  lea     rax, [rbp+40h+var_C0]
0x1400edcf8  mov     qword ptr [rsp+140h+ppv], rax; int
0x1400edcfd  lea     rdx, aPost; "POST"
0x1400edd04  mov     rcx, rdi
0x1400edd07  mov     rax, rbx
0x1400edd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400edd0f  mov     rcx, [rbp+48h]; this
0x1400edd13  test    eax, eax
0x1400edd15  jns     short loc_1400EDD2C
0x1400edd17  mov     r9d, eax; char *
0x1400edd1a  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x1400edd21  mov     edx, 220h; void *
0x1400edd26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400edd2c  lea     rcx, [rbp+40h+var_B8]; this
0x1400edd30  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edd35  nop
0x1400edd36  lea     rcx, [rbp+40h+var_C0]
0x1400edd3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400edd3f  nop
0x1400edd40  lea     rcx, [rbp+40h+var_98]; this
0x1400edd44  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400edd49  nop
0x1400edd4a  lea     rcx, [rbp+40h+var_70]; this
0x1400edd4e  call    ??1MappedDirectory@Resources@Containers@Schema@@QEAA@XZ; Schema::Containers::Resources::MappedDirectory::~MappedDirectory(void)
0x1400edd53  nop
0x1400edd54  lea     rcx, [rsp+140h+var_C8]
0x1400edd59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400edd5e  nop
0x1400edd5f  call    cs:__imp_CoUninitialize
0x1400edd66  nop     dword ptr [rax+rax+00h]
0x1400edd6b  mov     rcx, [rbp+40h+var_20]
0x1400edd6f  xor     rcx, rsp; StackCookie
0x1400edd72  call    __security_check_cookie
0x1400edd77  mov     rbx, [rsp+140h+arg_18]
0x1400edd7f  add     rsp, 130h
0x1400edd86  pop     rdi
0x1400edd87  pop     rsi
0x1400edd88  pop     rbp
0x1400edd89  retn
```
