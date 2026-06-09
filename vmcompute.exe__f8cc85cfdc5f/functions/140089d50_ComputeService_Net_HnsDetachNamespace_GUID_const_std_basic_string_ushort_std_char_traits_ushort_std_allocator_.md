# ComputeService::Net::HnsDetachNamespace(_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140089d50`
- end: `0x140089f6a`
- name: `?HnsDetachNamespace@Net@ComputeService@@YAXAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `538`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140089c30`
- `0x140288b20`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14002450c`
- `0x1400421f0`
- `0x14004249c`
- `0x140071d04`
- `0x140089d50`
- `0x1400c40e0`
- `0x1400d6a88`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x140219ce8`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140089f3e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140089f3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140089ddb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140089ddb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140089d7c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140089d7c`

## string_xrefs

- `0x140089d93`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140089df2`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140089efa`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ComputeService::Net::HnsDetachNamespace(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  char v5; // si
  HRESULT v6; // eax
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, const wchar_t *, _QWORD *, _QWORD *); // rbx
  _QWORD *v9; // r9
  _QWORD *v10; // r8
  unsigned int v11; // eax
  int ppv; // [rsp+20h] [rbp-99h]
  int ppva; // [rsp+20h] [rbp-99h]
  _BYTE v14[32]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-61h] BYREF
  LPVOID v16; // [rsp+78h] [rbp-41h] BYREF
  int v17[2]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v18[32]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h]
  _QWORD v20[4]; // [rsp+B0h] [rbp-9h] BYREF
  _QWORD v21[4]; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = CoInitializeEx(0, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v5 = 1;
  v16 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  v6 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v16);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v6,
      ppva);
  std::wstring::wstring(v18);
  v19 = 0;
  std::wstring::operator=(v18, a2);
  LODWORD(v19) = 0;
  Marshal::ToJson<Config::Network::HNS::v2::NamespaceAttachDetachRequest &,>(v21, v18);
  *(_QWORD *)v17 = 0;
  Vml::GuidToString(v15, a1, 0);
  std::operator+<unsigned short>(v14);
  std::operator+<unsigned short>(v20);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v14);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v15);
  v7 = v16;
  v8 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, _QWORD *))(*(_QWORD *)v16 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v17,
    0);
  v9 = v21;
  if ( v21[3] > 7u )
    v9 = (_QWORD *)v21[0];
  v10 = v20;
  if ( v20[3] > 7u )
    v10 = (_QWORD *)v20[0];
  v11 = v8(v7, L"POST", v10, v9);
  if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147023728 )
    v5 = 0;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)v11,
      (int)v17);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v17);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v21);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  CoUninitialize();
}

```

## disassembly

```asm
0x140089d50  mov     [rsp-8+arg_10], rbx
0x140089d55  push    rbp
0x140089d56  push    rsi
0x140089d57  push    rdi
0x140089d58  lea     rbp, [rsp-47h]
0x140089d5d  sub     rsp, 100h
0x140089d64  mov     rax, cs:__security_cookie
0x140089d6b  xor     rax, rsp
0x140089d6e  mov     [rbp+57h+var_20], rax
0x140089d72  mov     rdi, rdx
0x140089d75  mov     rbx, rcx
0x140089d78  xor     edx, edx; dwCoInit
0x140089d7a  xor     ecx, ecx; pvReserved
0x140089d7c  call    cs:__imp_CoInitializeEx
0x140089d83  nop     dword ptr [rax+rax+00h]
0x140089d88  mov     rcx, [rbp+5Fh]; this
0x140089d8c  test    eax, eax
0x140089d8e  jns     short loc_140089DA5
0x140089d90  mov     r9d, eax; char *
0x140089d93  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140089d9a  mov     edx, 1E7h; void *
0x140089d9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140089da5  mov     sil, 1
0x140089da8  mov     [rsp+110h+var_DF], sil
0x140089dad  mov     [rbp+57h+var_98], 0
0x140089db5  lea     rcx, [rbp+57h+var_98]
0x140089db9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140089dbe  lea     rax, [rbp+57h+var_98]
0x140089dc2  mov     qword ptr [rsp+110h+ppv], rax; int
0x140089dc7  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x140089dce  xor     edx, edx; pUnkOuter
0x140089dd0  lea     r8d, [rdx+17h]; dwClsContext
0x140089dd4  lea     rcx, rclsid; rclsid
0x140089ddb  call    cs:__imp_CoCreateInstance
0x140089de2  nop     dword ptr [rax+rax+00h]
0x140089de7  mov     rcx, [rbp+5Fh]; this
0x140089deb  test    eax, eax
0x140089ded  jns     short loc_140089E04
0x140089def  mov     r9d, eax; char *
0x140089df2  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140089df9  mov     edx, 1EBh; void *
0x140089dfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140089e04  lea     rcx, [rbp+57h+var_88]; void *
0x140089e08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140089e0d  mov     [rbp+57h+var_68], 0
0x140089e15  mov     rdx, rdi
0x140089e18  lea     rcx, [rbp+57h+var_88]
0x140089e1c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140089e21  mov     dword ptr [rbp+57h+var_68], 0
0x140089e28  lea     rdx, [rbp+57h+var_88]
0x140089e2c  lea     rcx, [rbp+57h+var_40]
0x140089e30  call    ??$ToJson@AEAUNamespaceAttachDetachRequest@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUNamespaceAttachDetachRequest@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::NamespaceAttachDetachRequest &,>(Config::Network::HNS::v2::NamespaceAttachDetachRequest &,Marshal::MarshalFlags)
0x140089e35  nop
0x140089e36  mov     qword ptr [rbp+57h+var_90], 0
0x140089e3e  xor     r8d, r8d
0x140089e41  mov     rdx, rbx
0x140089e44  lea     rcx, [rbp+57h+var_B8]
0x140089e48  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x140089e4d  nop
0x140089e4e  mov     r8, rax
0x140089e51  lea     rdx, aNamespaces; "/namespaces/"
0x140089e58  lea     rcx, [rsp+110h+var_D8]; void *
0x140089e5d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x140089e62  nop
0x140089e63  lea     r8, aDetach; "/detach"
0x140089e6a  mov     rdx, rax
0x140089e6d  lea     rcx, [rbp+57h+var_60]; void *
0x140089e71  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140089e76  nop
0x140089e77  lea     rcx, [rsp+110h+var_D8]; this
0x140089e7c  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140089e81  nop
0x140089e82  lea     rcx, [rbp+57h+var_B8]; this
0x140089e86  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140089e8b  mov     rdi, [rbp+57h+var_98]
0x140089e8f  mov     rax, [rdi]
0x140089e92  mov     rbx, [rax+38h]
0x140089e96  xor     edx, edx
0x140089e98  lea     rcx, [rbp+57h+var_90]
0x140089e9c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140089ea1  lea     r9, [rbp+57h+var_40]
0x140089ea5  cmp     [rbp+57h+var_28], 7
0x140089eaa  cmova   r9, [rbp+57h+var_40]
0x140089eaf  lea     r8, [rbp+57h+var_60]
0x140089eb3  cmp     [rbp+57h+var_48], 7
0x140089eb8  cmova   r8, [rbp+57h+var_60]
0x140089ebd  lea     rax, [rbp+57h+var_90]
0x140089ec1  mov     qword ptr [rsp+110h+ppv], rax; int
0x140089ec6  lea     rdx, aPost; "POST"
0x140089ecd  mov     rcx, rdi
0x140089ed0  mov     rax, rbx
0x140089ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089ed8  mov     edx, 80000000h
0x140089edd  lea     ecx, [rax+rdx]
0x140089ee0  test    edx, ecx
0x140089ee2  jnz     short loc_140089EEB
0x140089ee4  cmp     eax, 80070490h
0x140089ee9  jnz     short loc_140089EEE
0x140089eeb  xor     sil, sil
0x140089eee  mov     rcx, [rbp+5Fh]; this
0x140089ef2  test    sil, sil
0x140089ef5  jz      short loc_140089F0C
0x140089ef7  mov     r9d, eax; char *
0x140089efa  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140089f01  mov     edx, 1F6h; void *
0x140089f06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140089f0c  lea     rcx, [rbp+57h+var_60]; this
0x140089f10  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140089f15  nop
0x140089f16  lea     rcx, [rbp+57h+var_90]
0x140089f1a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140089f1f  nop
0x140089f20  lea     rcx, [rbp+57h+var_40]; this
0x140089f24  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140089f29  nop
0x140089f2a  lea     rcx, [rbp+57h+var_88]; this
0x140089f2e  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140089f33  nop
0x140089f34  lea     rcx, [rbp+57h+var_98]
0x140089f38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140089f3d  nop
0x140089f3e  call    cs:__imp_CoUninitialize
0x140089f45  nop     dword ptr [rax+rax+00h]
0x140089f4a  mov     rcx, [rbp+57h+var_20]
0x140089f4e  xor     rcx, rsp; StackCookie
0x140089f51  call    __security_check_cookie
0x140089f56  mov     rbx, [rsp+110h+arg_10]
0x140089f5e  add     rsp, 100h
0x140089f65  pop     rdi
0x140089f66  pop     rsi
0x140089f67  pop     rbp
0x140089f68  retn
```
