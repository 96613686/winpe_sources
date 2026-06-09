# GetActivationInfo(ushort const *,ushort const *,ushort const *,bool,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800759b0`
- end: `0x180075b87`
- name: `?GetActivationInfo@@YAXPEBG00_NPEAPEAUHSTRING__@@2@Z`
- size: `471`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool, HSTRING *, HSTRING *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800755c0`
- `0x1800891c8`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180024990`
- `0x180034ba0`
- `0x18006323c`
- `0x1800759b0`
- `0x180075bcc`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075aae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075aae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075b63`

## string_xrefs

- `0x180075a41`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180075a78`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall GetActivationInfo(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        HSTRING *a5,
        HSTRING *a6)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID); // rbx
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  const struct _GUID *v11; // rcx
  int QueryAssociationBrokerService; // eax
  void *v13; // r14
  int (__fastcall *v14)(void *, PVOID, PVOID, PVOID, char, HSTRING *, HSTRING *); // rsi
  PVOID Reserved1; // rdi
  PVOID v16; // rbx
  HSTRING_HEADER *v17; // rax
  HSTRING v18; // rax
  int v19; // [rsp+20h] [rbp-A9h]
  char v20; // [rsp+20h] [rbp-A9h]
  HSTRING v21; // [rsp+40h] [rbp-89h] BYREF
  HSTRING string; // [rsp+48h] [rbp-81h] BYREF
  void *v23; // [rsp+50h] [rbp-79h] BYREF
  __int64 v24; // [rsp+58h] [rbp-71h] BYREF
  const WCHAR *v25; // [rsp+60h] [rbp-69h] BYREF
  const WCHAR *v26; // [rsp+68h] [rbp-61h] BYREF
  const WCHAR *v27; // [rsp+70h] [rbp-59h] BYREF
  HSTRING_HEADER v28; // [rsp+78h] [rbp-51h] BYREF
  HSTRING_HEADER v29; // [rsp+98h] [rbp-31h] BYREF
  HSTRING_HEADER v30; // [rsp+B8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  v27 = a1;
  v26 = a2;
  v25 = a3;
  string = 0;
  v21 = 0;
  *a6 = 0;
  wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>((__int64)&v24);
  v7 = v24;
  v8 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v24 + 280LL);
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v28, &v25);
  v10 = v8(v7, v9[1].Reserved.Reserved1);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x684,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v10,
      v19);
  v23 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  QueryAssociationBrokerService = GetQueryAssociationBrokerService(v11, &v23);
  if ( QueryAssociationBrokerService < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x687,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)QueryAssociationBrokerService,
      v19);
  v13 = v23;
  v14 = *(int (__fastcall **)(void *, PVOID, PVOID, PVOID, char, HSTRING *, HSTRING *))(*(_QWORD *)v23 + 80LL);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v21);
  v21 = 0;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v28, &v25)[1].Reserved.Reserved1;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v29, &v26)[1].Reserved.Reserved1;
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v30, &v27);
  v20 = a4;
  if ( v14(v13, v17[1].Reserved.Reserved1, v16, Reserved1, v20, &v21, &string) >= 0 )
  {
    v18 = string;
    string = 0;
    *a6 = v18;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v24);
  WindowsDeleteString(v21);
  v21 = 0;
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x1800759b0  push    rbp
0x1800759b2  push    rbx
0x1800759b3  push    rsi
0x1800759b4  push    rdi
0x1800759b5  push    r12
0x1800759b7  push    r14
0x1800759b9  push    r15
0x1800759bb  lea     rbp, [rsp-17h]
0x1800759c0  sub     rsp, 0E0h
0x1800759c7  mov     rax, cs:__security_cookie
0x1800759ce  xor     rax, rsp
0x1800759d1  mov     [rbp+47h+var_38], rax
0x1800759d5  mov     r12b, r9b
0x1800759d8  mov     [rbp+47h+var_A0], rcx
0x1800759dc  mov     [rbp+47h+var_A8], rdx
0x1800759e0  mov     [rbp+47h+var_B0], r8
0x1800759e4  mov     r15, [rbp+47h+arg_28]
0x1800759e8  mov     [rsp+110h+string], 0
0x1800759f1  mov     [rsp+110h+var_D0], 0
0x1800759fa  mov     qword ptr [r15], 0
0x180075a01  lea     rcx, [rbp+47h+var_B8]
0x180075a05  call    ??$ActivateInstance@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(ushort const *)
0x180075a0a  nop
0x180075a0b  mov     rdi, [rbp+47h+var_B8]
0x180075a0f  mov     rax, [rdi]
0x180075a12  mov     rbx, [rax+118h]
0x180075a19  lea     rdx, [rbp+47h+var_B0]
0x180075a1d  lea     rcx, [rbp+47h+var_98]
0x180075a21  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180075a26  nop
0x180075a27  mov     rdx, [rax+18h]
0x180075a2b  mov     rcx, rdi
0x180075a2e  mov     rax, rbx
0x180075a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a36  mov     rcx, [rbp+4Fh]; this
0x180075a3a  test    eax, eax
0x180075a3c  jns     short loc_180075A53
0x180075a3e  mov     r9d, eax; char *
0x180075a41  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180075a48  mov     edx, 684h; void *
0x180075a4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075a53  mov     [rbp+47h+var_C0], 0
0x180075a5b  lea     rcx, [rbp+47h+var_C0]
0x180075a5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075a64  lea     rdx, [rbp+47h+var_C0]; void **
0x180075a68  call    ?GetQueryAssociationBrokerService@@YAJAEBU_GUID@@PEAPEAX@Z; GetQueryAssociationBrokerService(_GUID const &,void * *)
0x180075a6d  mov     rcx, [rbp+4Fh]; this
0x180075a71  test    eax, eax
0x180075a73  jns     short loc_180075A8A
0x180075a75  mov     r9d, eax; char *
0x180075a78  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180075a7f  mov     edx, 687h; void *
0x180075a84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075a8a  mov     r14, [rbp+47h+var_C0]
0x180075a8e  mov     rax, [r14]
0x180075a91  mov     rsi, [rax+50h]
0x180075a95  mov     rcx, [rsp+110h+string]; string
0x180075a9a  call    cs:__imp_WindowsDeleteString
0x180075aa0  mov     [rsp+110h+string], 0
0x180075aa9  mov     rcx, [rsp+110h+var_D0]; string
0x180075aae  call    cs:__imp_WindowsDeleteString
0x180075ab4  mov     [rsp+110h+var_D0], 0
0x180075abd  lea     rdx, [rbp+47h+var_B0]
0x180075ac1  lea     rcx, [rbp+47h+var_98]
0x180075ac5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180075aca  nop
0x180075acb  mov     rdi, [rax+18h]
0x180075acf  lea     rdx, [rbp+47h+var_A8]
0x180075ad3  lea     rcx, [rbp+47h+var_78]
0x180075ad7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180075adc  nop
0x180075add  mov     rbx, [rax+18h]
0x180075ae1  lea     rdx, [rbp+47h+var_A0]
0x180075ae5  lea     rcx, [rbp+47h+var_58]
0x180075ae9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180075aee  nop
0x180075aef  lea     rcx, [rsp+110h+string]
0x180075af4  mov     [rsp+110h+var_E0], rcx
0x180075af9  lea     rcx, [rsp+110h+var_D0]
0x180075afe  mov     [rsp+110h+var_E8], rcx
0x180075b03  mov     [rsp+110h+var_F0], r12b
0x180075b08  mov     r9, rdi
0x180075b0b  mov     r8, rbx
0x180075b0e  mov     rdx, [rax+18h]
0x180075b12  mov     rcx, r14
0x180075b15  mov     rax, rsi
0x180075b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b1d  nop
0x180075b1e  shr     eax, 1Fh
0x180075b21  test    al, al
0x180075b23  jnz     short loc_180075B36
0x180075b25  mov     rax, [rsp+110h+string]
0x180075b2a  mov     [rsp+110h+string], 0
0x180075b33  mov     [r15], rax
0x180075b36  lea     rcx, [rbp+47h+var_C0]
0x180075b3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075b3f  nop
0x180075b40  lea     rcx, [rbp+47h+var_B8]
0x180075b44  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180075b49  nop
0x180075b4a  mov     rcx, [rsp+110h+var_D0]; string
0x180075b4f  call    cs:__imp_WindowsDeleteString
0x180075b55  mov     [rsp+110h+var_D0], 0
0x180075b5e  mov     rcx, [rsp+110h+string]; string
0x180075b63  call    cs:__imp_WindowsDeleteString
0x180075b69  mov     rcx, [rbp+47h+var_38]
0x180075b6d  xor     rcx, rsp; StackCookie
0x180075b70  call    __security_check_cookie
0x180075b75  add     rsp, 0E0h
0x180075b7c  pop     r15
0x180075b7e  pop     r14
0x180075b80  pop     r12
0x180075b82  pop     rdi
0x180075b83  pop     rsi
0x180075b84  pop     rbx
0x180075b85  pop     rbp
0x180075b86  retn
```
