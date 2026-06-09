# wil::ActivateInstance<Windows::Management::Deployment::IPackageManager2>(ushort const *)

- ea: `0x180012b74`
- end: `0x180012c0f`
- name: `??$ActivateInstance@UIPackageManager2@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManager2@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006c3c`

## callees

- `0x1800065e4`
- `0x180008320`
- `0x180012420`
- `0x180012b74`
- `0x180013d80`
- `0x18001a610`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180012bbd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180012bbd`

## string_xrefs

- `0x180012bcf`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::ActivateInstance<Windows::Management::Deployment::IPackageManager2>(__int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v5[4]; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = L"Windows.Management.Deployment.PackageManager";
  *(_QWORD *)v5 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6);
  v3 = RoActivateInstance(*(_QWORD *)(v2 + 24), v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x74D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v3,
      v5[0]);
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Management::Deployment::IPackageManager2>(
    v5,
    a1);
  wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(v5);
  return a1;
}

```

## disassembly

```asm
0x180012b74  mov     r11, rsp
0x180012b77  push    rbx
0x180012b78  sub     rsp, 70h
0x180012b7c  mov     rax, cs:__security_cookie
0x180012b83  xor     rax, rsp
0x180012b86  mov     [rsp+78h+var_10], rax
0x180012b8b  mov     rbx, rcx
0x180012b8e  mov     [rsp+78h+var_48], rcx
0x180012b93  lea     rax, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180012b9a  mov     [r11-48h], rax
0x180012b9e  mov     qword ptr [r11-58h], 0
0x180012ba6  lea     rdx, [r11-48h]
0x180012baa  lea     rcx, [r11-30h]
0x180012bae  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180012bb3  nop
0x180012bb4  lea     rdx, [rsp+78h+var_58]
0x180012bb9  mov     rcx, [rax+18h]
0x180012bbd  call    cs:__imp_RoActivateInstance
0x180012bc3  mov     rcx, [rsp+78h]; this
0x180012bc8  test    eax, eax
0x180012bca  jns     short loc_180012BE1
0x180012bcc  mov     r9d, eax; char *
0x180012bcf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012bd6  mov     edx, 74Dh; void *
0x180012bdb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012be1  mov     rdx, rbx
0x180012be4  lea     rcx, [rsp+78h+var_58]
0x180012be9  call    ??$query@UIPackageManager2@Deployment@Management@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackageManager2@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Management::Deployment::IPackageManager2>(void)
0x180012bee  nop
0x180012bef  lea     rcx, [rsp+78h+var_58]
0x180012bf4  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180012bf9  mov     rax, rbx
0x180012bfc  mov     rcx, [rsp+78h+var_10]
0x180012c01  xor     rcx, rsp; StackCookie
0x180012c04  call    __security_check_cookie
0x180012c09  add     rsp, 70h
0x180012c0d  pop     rbx
0x180012c0e  retn
```
