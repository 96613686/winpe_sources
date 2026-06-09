# ComputeService::Net::HnsCleanEndpoint(_GUID const &)

- ea: `0x14021a284`
- end: `0x14021a423`
- name: `?HnsCleanEndpoint@Net@ComputeService@@YAXAEBU_GUID@@@Z`
- size: `415`
- prototype: `void __fastcall(ComputeService::Net *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14028a6b0`

## callees

- `0x140017040`
- `0x14002450c`
- `0x14004249c`
- `0x140071d04`
- `0x1400c40e0`
- `0x1400ee8cc`
- `0x1400eee68`
- `0x1401332f0`
- `0x14021a284`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14021a3fe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14021a3fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14021a308`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14021a308`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14021a2aa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14021a2aa`

## string_xrefs

- `0x14021a2c1`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x14021a31f`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x14021a3ce`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x14021a39a`: `DELETE`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ComputeService::Net::HnsCleanEndpoint(ComputeService::Net *this, const struct _GUID *a2)
{
  HRESULT v3; // eax
  char v4; // si
  HRESULT v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, const wchar_t *, _QWORD *, const WCHAR *); // rbx
  _QWORD *v8; // r8
  unsigned int v9; // eax
  int ppv; // [rsp+20h] [rbp-39h]
  int ppva; // [rsp+20h] [rbp-39h]
  _BYTE v12[32]; // [rsp+38h] [rbp-21h] BYREF
  LPVOID v13; // [rsp+58h] [rbp-1h] BYREF
  int v14[2]; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v15[4]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v3 = CoInitializeEx(0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v4 = 1;
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v5 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v13);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  *(_QWORD *)v14 = 0;
  Vml::GuidToString(v12, this, 0);
  std::operator+<unsigned short>(v15);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v12);
  v6 = v13;
  v7 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *, const WCHAR *))(*(_QWORD *)v13 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v14,
    0);
  v8 = v15;
  if ( v15[3] > 7u )
    v8 = (_QWORD *)v15[0];
  v9 = v7(v6, L"DELETE", v8, &szPassword);
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023728 )
    v4 = 0;
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)v9,
      (int)v14);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  CoUninitialize();
}

```

## disassembly

```asm
0x14021a284  push    rbp
0x14021a286  push    rbx
0x14021a287  push    rsi
0x14021a288  push    rdi
0x14021a289  lea     rbp, [rsp-3Fh]
0x14021a28e  sub     rsp, 98h
0x14021a295  mov     rax, cs:__security_cookie
0x14021a29c  xor     rax, rsp
0x14021a29f  mov     [rbp+57h+var_28], rax
0x14021a2a3  mov     rbx, rcx
0x14021a2a6  xor     edx, edx; dwCoInit
0x14021a2a8  xor     ecx, ecx; pvReserved
0x14021a2aa  call    cs:__imp_CoInitializeEx
0x14021a2b1  nop     dword ptr [rax+rax+00h]
0x14021a2b6  mov     rcx, [rbp+5Fh]; this
0x14021a2ba  test    eax, eax
0x14021a2bc  jns     short loc_14021A2D3
0x14021a2be  mov     r9d, eax; char *
0x14021a2c1  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14021a2c8  mov     edx, 192h; void *
0x14021a2cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14021a2d3  mov     sil, 1
0x14021a2d6  mov     [rbp+57h+var_7F], sil
0x14021a2da  mov     [rbp+57h+var_58], 0
0x14021a2e2  lea     rcx, [rbp+57h+var_58]
0x14021a2e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14021a2eb  lea     rax, [rbp+57h+var_58]
0x14021a2ef  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x14021a2f4  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x14021a2fb  xor     edx, edx; pUnkOuter
0x14021a2fd  lea     r8d, [rdx+17h]; dwClsContext
0x14021a301  lea     rcx, rclsid; rclsid
0x14021a308  call    cs:__imp_CoCreateInstance
0x14021a30f  nop     dword ptr [rax+rax+00h]
0x14021a314  mov     rcx, [rbp+5Fh]; this
0x14021a318  test    eax, eax
0x14021a31a  jns     short loc_14021A331
0x14021a31c  mov     r9d, eax; char *
0x14021a31f  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14021a326  mov     edx, 196h; void *
0x14021a32b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14021a331  mov     qword ptr [rbp+57h+var_50], 0
0x14021a339  xor     r8d, r8d
0x14021a33c  mov     rdx, rbx
0x14021a33f  lea     rcx, [rbp+57h+var_78]
0x14021a343  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14021a348  nop
0x14021a349  mov     r8, rax
0x14021a34c  lea     rdx, aEndpoints; "/endpoints/"
0x14021a353  lea     rcx, [rbp+57h+var_48]; void *
0x14021a357  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x14021a35c  nop
0x14021a35d  lea     rcx, [rbp+57h+var_78]; this
0x14021a361  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14021a366  mov     rdi, [rbp+57h+var_58]
0x14021a36a  mov     rax, [rdi]
0x14021a36d  mov     rbx, [rax+38h]
0x14021a371  xor     edx, edx
0x14021a373  lea     rcx, [rbp+57h+var_50]
0x14021a377  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14021a37c  lea     r8, [rbp+57h+var_48]
0x14021a380  cmp     [rbp+57h+var_30], 7
0x14021a385  cmova   r8, [rbp+57h+var_48]
0x14021a38a  lea     rax, [rbp+57h+var_50]
0x14021a38e  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x14021a393  lea     r9, szPassword
0x14021a39a  lea     rdx, aDelete_0; "DELETE"
0x14021a3a1  mov     rcx, rdi
0x14021a3a4  mov     rax, rbx
0x14021a3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14021a3ac  mov     edx, 80000000h
0x14021a3b1  lea     ecx, [rax+rdx]
0x14021a3b4  test    edx, ecx
0x14021a3b6  jnz     short loc_14021A3BF
0x14021a3b8  cmp     eax, 80070490h
0x14021a3bd  jnz     short loc_14021A3C2
0x14021a3bf  xor     sil, sil
0x14021a3c2  mov     rcx, [rbp+5Fh]; this
0x14021a3c6  test    sil, sil
0x14021a3c9  jz      short loc_14021A3E0
0x14021a3cb  mov     r9d, eax; char *
0x14021a3ce  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14021a3d5  mov     edx, 19Ch; void *
0x14021a3da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14021a3e0  lea     rcx, [rbp+57h+var_48]; this
0x14021a3e4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14021a3e9  nop
0x14021a3ea  lea     rcx, [rbp+57h+var_50]
0x14021a3ee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14021a3f3  nop
0x14021a3f4  lea     rcx, [rbp+57h+var_58]
0x14021a3f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14021a3fd  nop
0x14021a3fe  call    cs:__imp_CoUninitialize
0x14021a405  nop     dword ptr [rax+rax+00h]
0x14021a40a  mov     rcx, [rbp+57h+var_28]
0x14021a40e  xor     rcx, rsp; StackCookie
0x14021a411  call    __security_check_cookie
0x14021a416  add     rsp, 98h
0x14021a41d  pop     rdi
0x14021a41e  pop     rsi
0x14021a41f  pop     rbx
0x14021a420  pop     rbp
0x14021a421  retn
```
