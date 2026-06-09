# ComputeService::Net::HnsDetachEndpointVNic(_GUID const &)

- ea: `0x14021a42c`
- end: `0x14021a54e`
- name: `?HnsDetachEndpointVNic@Net@ComputeService@@YAXAEBU_GUID@@@Z`
- size: `290`
- prototype: `void __fastcall(ComputeService::Net *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140098ed0`
- `0x1400cd9bc`

## callees

- `0x14002450c`
- `0x1400c40e0`
- `0x1401332f0`
- `0x14021a42c`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14021a529`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14021a529`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14021a4ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14021a4ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14021a44c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14021a44c`

## string_xrefs

- `0x14021a464`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x14021a4c5`: `onecore\vm\compute\shared\net\networkutilities.cpp`
- `0x14021a50c`: `onecore\vm\compute\shared\net\networkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ComputeService::Net::HnsDetachEndpointVNic(ComputeService::Net *this, const struct _GUID *a2)
{
  HRESULT v3; // eax
  char v4; // bl
  HRESULT v5; // eax
  unsigned int v6; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  LPVOID v9; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = CoInitializeEx(0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v4 = 1;
  v9 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  v5 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01, &v9);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)(unsigned int)v5,
      ppva);
  v6 = (*(__int64 (__fastcall **)(LPVOID, ComputeService::Net *))(*(_QWORD *)v9 + 72LL))(v9, this);
  if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147023728 )
    v4 = 0;
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecore\\vm\\compute\\shared\\net\\networkutilities.cpp",
      (const char *)v6,
      ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  CoUninitialize();
}

```

## disassembly

```asm
0x14021a42c  mov     [rsp+arg_8], rbx
0x14021a431  push    rdi
0x14021a432  sub     rsp, 50h
0x14021a436  mov     rax, cs:__security_cookie
0x14021a43d  xor     rax, rsp
0x14021a440  mov     [rsp+58h+var_18], rax
0x14021a445  mov     rdi, rcx
0x14021a448  xor     edx, edx; dwCoInit
0x14021a44a  xor     ecx, ecx; pvReserved
0x14021a44c  call    cs:__imp_CoInitializeEx
0x14021a453  nop     dword ptr [rax+rax+00h]
0x14021a458  mov     rcx, [rsp+58h]; this
0x14021a45d  test    eax, eax
0x14021a45f  jns     short loc_14021A476
0x14021a461  mov     r9d, eax; char *
0x14021a464  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14021a46b  mov     edx, 25Ch; void *
0x14021a470  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14021a476  mov     bl, 1
0x14021a478  mov     [rsp+58h+var_27], bl
0x14021a47c  mov     [rsp+58h+var_20], 0
0x14021a485  lea     rcx, [rsp+58h+var_20]
0x14021a48a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14021a48f  lea     rax, [rsp+58h+var_20]
0x14021a494  mov     qword ptr [rsp+58h+ppv], rax; int
0x14021a499  lea     r9, _GUID_0b43d888_341a_4d8c_8c3a_f9ef5045df01; riid
0x14021a4a0  xor     edx, edx; pUnkOuter
0x14021a4a2  lea     r8d, [rdx+17h]; dwClsContext
0x14021a4a6  lea     rcx, rclsid; rclsid
0x14021a4ad  call    cs:__imp_CoCreateInstance
0x14021a4b4  nop     dword ptr [rax+rax+00h]
0x14021a4b9  mov     rcx, [rsp+58h]; this
0x14021a4be  test    eax, eax
0x14021a4c0  jns     short loc_14021A4D7
0x14021a4c2  mov     r9d, eax; char *
0x14021a4c5  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14021a4cc  mov     edx, 260h; void *
0x14021a4d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14021a4d7  mov     rcx, [rsp+58h+var_20]
0x14021a4dc  mov     rax, [rcx]
0x14021a4df  mov     rdx, rdi
0x14021a4e2  mov     rax, [rax+48h]
0x14021a4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14021a4eb  mov     edx, 80000000h
0x14021a4f0  lea     ecx, [rax+rdx]
0x14021a4f3  test    edx, ecx
0x14021a4f5  jnz     short loc_14021A4FE
0x14021a4f7  cmp     eax, 80070490h
0x14021a4fc  jnz     short loc_14021A500
0x14021a4fe  xor     bl, bl
0x14021a500  mov     rcx, [rsp+58h]; this
0x14021a505  test    bl, bl
0x14021a507  jz      short loc_14021A51E
0x14021a509  mov     r9d, eax; char *
0x14021a50c  lea     r8, aOnecoreVmCompu_140; "onecore\\vm\\compute\\shared\\net\\netw"...
0x14021a513  mov     edx, 263h; void *
0x14021a518  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14021a51e  lea     rcx, [rsp+58h+var_20]
0x14021a523  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14021a528  nop
0x14021a529  call    cs:__imp_CoUninitialize
0x14021a530  nop     dword ptr [rax+rax+00h]
0x14021a535  mov     rcx, [rsp+58h+var_18]
0x14021a53a  xor     rcx, rsp; StackCookie
0x14021a53d  call    __security_check_cookie
0x14021a542  mov     rbx, [rsp+58h+arg_8]
0x14021a547  add     rsp, 50h
0x14021a54b  pop     rdi
0x14021a54c  retn
```
