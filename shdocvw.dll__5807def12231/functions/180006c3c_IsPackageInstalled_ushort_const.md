# IsPackageInstalled(ushort const *)

- ea: `0x180006c3c`
- end: `0x180006d71`
- name: `?IsPackageInstalled@@YA_NPEBG@Z`
- size: `309`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005914`

## callees

- `0x1800065e4`
- `0x180006c3c`
- `0x180006d78`
- `0x180008320`
- `0x180012420`
- `0x180012b74`
- `0x180014884`
- `0x18001a610`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall IsPackageInstalled(const unsigned __int16 *a1)
{
  __int64 v1; // rdi
  __int64 (__fastcall *v2)(__int64, _QWORD, _QWORD, __int64); // rbx
  __int64 v3; // rax
  int v4; // eax
  bool v5; // bl
  const char *v6; // r9
  bool result; // al
  int v8[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+38h] [rbp-60h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-48h] BYREF
  int v12; // [rsp+58h] [rbp-40h]
  __int64 v13; // [rsp+60h] [rbp-38h]
  __int64 v14; // [rsp+68h] [rbp-30h] BYREF
  int v15; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v10 = L"Microsoft.StorePurchaseApp_8wekyb3d8bbwe";
    wil::ActivateInstance<Windows::Management::Deployment::IPackageManager2>((__int64)&v9);
    *(_QWORD *)v8 = 0;
    v1 = v9;
    v2 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 112LL);
    v3 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v14, &v10);
    v4 = v2(v1, 0, *(_QWORD *)(v3 + 24), 1);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9B9,
        (unsigned int)"shell\\shdocvw\\download.cpp",
        (const char *)(unsigned int)v4,
        (int)v8);
    wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
      &v14,
      *(__int64 *)v8);
    v11 = 0;
    v12 = -1;
    v13 = 0;
    v5 = v15 != -1;
    wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v11);
    wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v14);
    wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(&v9);
    result = v5;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x9BF,
      (unsigned int)"shell\\shdocvw\\download.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006c3c  mov     [rsp+arg_0], rbx
0x180006c41  push    rdi
0x180006c42  sub     rsp, 90h
0x180006c49  mov     rax, cs:__security_cookie
0x180006c50  xor     rax, rsp
0x180006c53  mov     [rsp+98h+var_10], rax
0x180006c5b  lea     rax, aMicrosoftStore; "Microsoft.StorePurchaseApp_8wekyb3d8bbw"...
0x180006c62  mov     [rsp+98h+var_58], rax
0x180006c67  lea     rcx, [rsp+98h+var_60]
0x180006c6c  call    ??$ActivateInstance@UIPackageManager2@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManager2@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Management::Deployment::IPackageManager2>(ushort const *)
0x180006c71  nop
0x180006c72  mov     qword ptr [rsp+98h+var_68], 0
0x180006c7b  mov     rdi, [rsp+98h+var_60]
0x180006c80  mov     rax, [rdi]
0x180006c83  mov     rbx, [rax+70h]
0x180006c87  lea     rdx, [rsp+98h+var_58]
0x180006c8c  lea     rcx, [rsp+98h+var_30]
0x180006c91  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180006c96  nop
0x180006c97  lea     rcx, [rsp+98h+var_68]
0x180006c9c  mov     qword ptr [rsp+98h+var_78], rcx; int
0x180006ca1  mov     r9d, 1
0x180006ca7  mov     r8, [rax+18h]
0x180006cab  xor     edx, edx
0x180006cad  mov     rcx, rdi
0x180006cb0  mov     rax, rbx
0x180006cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb8  mov     rcx, [rsp+98h]; this
0x180006cc0  test    eax, eax
0x180006cc2  jns     short loc_180006CD9
0x180006cc4  mov     r9d, eax; char *
0x180006cc7  lea     r8, aShellShdocvwDo_0; "shell\\shdocvw\\download.cpp"
0x180006cce  mov     edx, 9B9h; void *
0x180006cd3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006cd9  mov     rdx, qword ptr [rsp+98h+var_68]
0x180006cde  lea     rcx, [rsp+98h+var_30]
0x180006ce3  call    ??0iterable_iterator@?$iterable_range@PEAVPackage@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAVPackage@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Package *> *)
0x180006ce8  mov     [rsp+98h+var_48], 0
0x180006cf1  mov     [rsp+98h+var_40], 0FFFFFFFFh
0x180006cf9  mov     [rsp+98h+var_38], 0
0x180006d02  cmp     [rsp+98h+var_28], 0FFFFFFFFh
0x180006d07  setnz   bl
0x180006d0a  lea     rcx, [rsp+98h+var_48]
0x180006d0f  call    ??1iterable_iterator@?$iterable_range@PEAVPackage@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180006d14  lea     rcx, [rsp+98h+var_30]
0x180006d19  call    ??1iterable_iterator@?$iterable_range@PEAVPackage@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::ApplicationModel::Package *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180006d1e  nop
0x180006d1f  mov     rcx, qword ptr [rsp+98h+var_68]
0x180006d24  test    rcx, rcx
0x180006d27  jz      short loc_180006D3F
0x180006d29  mov     qword ptr [rsp+98h+var_68], 0
0x180006d32  mov     rdx, [rcx]
0x180006d35  mov     rax, [rdx+10h]
0x180006d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d3e  nop
0x180006d3f  lea     rcx, [rsp+98h+var_60]
0x180006d44  call    ??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)
0x180006d49  mov     al, bl
0x180006d4b  jmp     short loc_180006D4F
0x180006d4d  xor     al, al
0x180006d4f  mov     rcx, [rsp+98h+var_10]
0x180006d57  xor     rcx, rsp; StackCookie
0x180006d5a  call    __security_check_cookie
0x180006d5f  mov     rbx, [rsp+98h+arg_0]
0x180006d67  add     rsp, 90h
0x180006d6e  pop     rdi
0x180006d6f  retn
```
