# ComputeService::Net::HnsAttachEndpointVNic(_GUID const &,_GUID const &)

- ea: `0x140097b5c`
- end: `0x140097ced`
- name: `?HnsAttachEndpointVNic@Net@ComputeService@@YAXAEBU_GUID@@0@Z`
- size: `401`
- prototype: `void __fastcall(ComputeService::Net *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140098b98`
- `0x1400b3570`

## callees

- `0x140017040`
- `0x14002450c`
- `0x14004249c`
- `0x14006be0c`
- `0x140097b5c`
- `0x1400c40e0`
- `0x1400d6a88`
- `0x1401332f0`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140097cc1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140097cc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140097be3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140097be3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140097b88`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140097b88`

## string_xrefs

- `0x140097b9f`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140097bfa`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x140097c9b`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ComputeService::Net::HnsAttachEndpointVNic(
        ComputeService::Net *this,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  HRESULT v5; // eax
  HRESULT v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // r8
  int v11; // eax
  int ppv; // [rsp+20h] [rbp-69h]
  int ppva; // [rsp+20h] [rbp-69h]
  _BYTE v14[32]; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v16[32]; // [rsp+78h] [rbp-11h] BYREF
  LPVOID v17; // [rsp+98h] [rbp+Fh] BYREF
  _QWORD v18[4]; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v6 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v17);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23F,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v6,
      ppva);
  v7 = Vml::GuidToString(v16, this, 0);
  Vml::GuidToString(v15, a2, 0);
  v8 = std::operator+<unsigned short>(v14);
  std::wstring::wstring(v18, v9, v8, v7);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v14);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v15);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v16);
  v10 = v18;
  if ( v18[3] > 7u )
    v10 = (_QWORD *)v18[0];
  v11 = (*(__int64 (__fastcall **)(LPVOID, ComputeService::Net *, _QWORD *))(*(_QWORD *)v17 + 80LL))(v17, this, v10);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v11,
      ppva);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  CoUninitialize();
}

```

## disassembly

```asm
0x140097b5c  mov     [rsp-8+arg_10], rbx
0x140097b61  push    rbp
0x140097b62  push    rsi
0x140097b63  push    rdi
0x140097b64  lea     rbp, [rsp-47h]
0x140097b69  sub     rsp, 0D0h
0x140097b70  mov     rax, cs:__security_cookie
0x140097b77  xor     rax, rsp
0x140097b7a  mov     [rbp+57h+var_20], rax
0x140097b7e  mov     rsi, rdx
0x140097b81  mov     rdi, rcx
0x140097b84  xor     edx, edx; dwCoInit
0x140097b86  xor     ecx, ecx; pvReserved
0x140097b88  call    cs:__imp_CoInitializeEx
0x140097b8f  nop     dword ptr [rax+rax+00h]
0x140097b94  mov     rcx, [rbp+5Fh]; this
0x140097b98  test    eax, eax
0x140097b9a  jns     short loc_140097BB1
0x140097b9c  mov     r9d, eax; char *
0x140097b9f  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140097ba6  mov     edx, 23Bh; void *
0x140097bab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097bb1  mov     [rbp+57h+var_AF], 1
0x140097bb5  mov     [rbp+57h+var_48], 0
0x140097bbd  lea     rcx, [rbp+57h+var_48]
0x140097bc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140097bc6  lea     rax, [rbp+57h+var_48]
0x140097bca  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x140097bcf  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x140097bd6  xor     edx, edx; pUnkOuter
0x140097bd8  lea     r8d, [rdx+17h]; dwClsContext
0x140097bdc  lea     rcx, rclsid; rclsid
0x140097be3  call    cs:__imp_CoCreateInstance
0x140097bea  nop     dword ptr [rax+rax+00h]
0x140097bef  mov     rcx, [rbp+5Fh]; this
0x140097bf3  test    eax, eax
0x140097bf5  jns     short loc_140097C0C
0x140097bf7  mov     r9d, eax; char *
0x140097bfa  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140097c01  mov     edx, 23Fh; void *
0x140097c06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097c0c  xor     r8d, r8d
0x140097c0f  mov     rdx, rdi
0x140097c12  lea     rcx, [rbp+57h+var_68]
0x140097c16  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x140097c1b  mov     rbx, rax
0x140097c1e  xor     r8d, r8d
0x140097c21  mov     rdx, rsi
0x140097c24  lea     rcx, [rbp+57h+var_88]
0x140097c28  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x140097c2d  nop
0x140097c2e  lea     r8, asc_1402FEE20; "--"
0x140097c35  mov     rdx, rax
0x140097c38  lea     rcx, [rbp+57h+var_A8]; void *
0x140097c3c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140097c41  nop
0x140097c42  mov     r9, rbx
0x140097c45  mov     r8, rax
0x140097c48  lea     rcx, [rbp+57h+var_40]
0x140097c4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x140097c51  nop
0x140097c52  lea     rcx, [rbp+57h+var_A8]; this
0x140097c56  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140097c5b  nop
0x140097c5c  lea     rcx, [rbp+57h+var_88]; this
0x140097c60  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140097c65  nop
0x140097c66  lea     rcx, [rbp+57h+var_68]; this
0x140097c6a  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140097c6f  mov     rcx, [rbp+57h+var_48]
0x140097c73  mov     rax, [rcx]
0x140097c76  lea     r8, [rbp+57h+var_40]
0x140097c7a  cmp     [rbp+57h+var_28], 7
0x140097c7f  cmova   r8, [rbp+57h+var_40]
0x140097c84  mov     rdx, rdi
0x140097c87  mov     rax, [rax+50h]
0x140097c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097c90  mov     rcx, [rbp+5Fh]; this
0x140097c94  test    eax, eax
0x140097c96  jns     short loc_140097CAD
0x140097c98  mov     r9d, eax; char *
0x140097c9b  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x140097ca2  mov     edx, 246h; void *
0x140097ca7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097cad  lea     rcx, [rbp+57h+var_40]; this
0x140097cb1  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140097cb6  nop
0x140097cb7  lea     rcx, [rbp+57h+var_48]
0x140097cbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140097cc0  nop
0x140097cc1  call    cs:__imp_CoUninitialize
0x140097cc8  nop     dword ptr [rax+rax+00h]
0x140097ccd  mov     rcx, [rbp+57h+var_20]
0x140097cd1  xor     rcx, rsp; StackCookie
0x140097cd4  call    __security_check_cookie
0x140097cd9  mov     rbx, [rsp+0E0h+arg_10]
0x140097ce1  add     rsp, 0D0h
0x140097ce8  pop     rdi
0x140097ce9  pop     rsi
0x140097cea  pop     rbp
0x140097ceb  retn
```
