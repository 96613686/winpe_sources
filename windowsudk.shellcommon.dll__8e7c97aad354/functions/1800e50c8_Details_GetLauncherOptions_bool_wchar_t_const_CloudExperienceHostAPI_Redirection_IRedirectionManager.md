# Details::GetLauncherOptions(bool,wchar_t const *,CloudExperienceHostAPI::Redirection::IRedirectionManager *)

- ea: `0x1800e50c8`
- end: `0x1800e5286`
- name: `?GetLauncherOptions@Details@@YA?AV?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@_NPEB_WPEAUIRedirectionManager@Redirection@CloudExperienceHostAPI@@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18030940c`

## callees

- `0x180044668`
- `0x1800483f4`
- `0x1800529c8`
- `0x1800e488c`
- `0x1800e50c8`
- `0x18015cb00`
- `0x180308b24`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e517d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e517d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e5166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e5166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e510c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e510c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5260`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HSTRING __fastcall Details::GetLauncherOptions(HSTRING a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64); // rdi
  int v14; // eax
  int v16; // [rsp+20h] [rbp-50h]
  __int64 v17; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v18[2]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v18[1] = a1;
  v18[0] = 0;
  if ( a4 )
  {
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a4 + 56LL);
    WindowsDeleteString(0);
    v18[0] = 0;
    v7 = v6(a4, v18);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v7,
        0);
  }
  *(_QWORD *)a1 = 0;
  v16 = 1;
  if ( WindowsCreateStringReference(L"Windows.System.LauncherOptions", 0x1Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>(string, a1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v8,
      1);
  v17 = 0;
  v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a1;
  v10 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v11 = v10(v9, &GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49, &v17);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v11,
      1);
  v12 = v17;
  v13 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 56LL);
  if ( !v18[0] )
  {
    v16 = 3;
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, off_1804E6B60);
  }
  v14 = v13(v12);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v14,
      v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  WindowsDeleteString(v18[0]);
  return a1;
}

```

## disassembly

```asm
0x1800e50c8  mov     [rsp-18h+arg_8], rbx
0x1800e50cd  push    rbp
0x1800e50ce  push    rsi
0x1800e50cf  push    rdi
0x1800e50d0  mov     rbp, rsp
0x1800e50d3  sub     rsp, 70h
0x1800e50d7  mov     rax, cs:__security_cookie
0x1800e50de  xor     rax, rsp
0x1800e50e1  mov     [rbp+var_10], rax
0x1800e50e5  mov     rdi, r9
0x1800e50e8  mov     rsi, rcx
0x1800e50eb  mov     [rbp+var_38], rcx
0x1800e50ef  mov     [rbp+var_50], 0
0x1800e50f6  mov     [rbp+var_40], 0
0x1800e50fe  test    r9, r9
0x1800e5101  jz      short loc_1800E5145
0x1800e5103  mov     rax, [r9]
0x1800e5106  mov     rbx, [rax+38h]
0x1800e510a  xor     ecx, ecx; string
0x1800e510c  call    cs:__imp_WindowsDeleteString
0x1800e5112  mov     [rbp+var_40], 0
0x1800e511a  lea     rdx, [rbp+var_40]
0x1800e511e  mov     rcx, rdi
0x1800e5121  mov     rax, rbx
0x1800e5124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5129  mov     rcx, [rbp+18h]; this
0x1800e512d  test    eax, eax
0x1800e512f  jns     short loc_1800E5145
0x1800e5131  mov     r9d, eax; char *
0x1800e5134  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800e513b  mov     edx, 35h ; '5'; void *
0x1800e5140  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e5145  mov     qword ptr [rsi], 0
0x1800e514c  mov     ebx, 1
0x1800e5151  mov     [rbp+var_50], ebx
0x1800e5154  lea     r9, [rbp+string]; string
0x1800e5158  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800e515c  lea     edx, [rbx+1Dh]; length
0x1800e515f  lea     rcx, ?RuntimeClass_Windows_System_LauncherOptions@@3QB_WB; "Windows.System.LauncherOptions"
0x1800e5166  call    cs:__imp_WindowsCreateStringReference
0x1800e516c  test    eax, eax
0x1800e516e  jns     short loc_1800E5183
0x1800e5170  xor     r9d, r9d; lpArguments
0x1800e5173  xor     r8d, r8d; nNumberOfArguments
0x1800e5176  mov     edx, ebx; dwExceptionFlags
0x1800e5178  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800e517d  call    cs:__imp_RaiseException
0x1800e5183  mov     rdx, rsi
0x1800e5186  mov     rcx, [rbp+string]
0x1800e518a  call    ??$ActivateInstance@V?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherOptions@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherOptions>>)
0x1800e518f  mov     rcx, [rbp+18h]; this
0x1800e5193  test    eax, eax
0x1800e5195  jns     short loc_1800E51AC
0x1800e5197  mov     r9d, eax; char *
0x1800e519a  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800e51a1  mov     edx, 3Ch ; '<'; void *
0x1800e51a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e51ac  mov     [rbp+var_48], 0
0x1800e51b4  mov     rdi, [rsi]
0x1800e51b7  mov     rax, [rdi]
0x1800e51ba  mov     rbx, [rax]
0x1800e51bd  lea     rcx, [rbp+var_48]
0x1800e51c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e51c6  lea     r8, [rbp+var_48]
0x1800e51ca  lea     rdx, _GUID_3ba08eb4_6e40_4dce_a1a3_2f53950afb49
0x1800e51d1  mov     rcx, rdi
0x1800e51d4  mov     rax, rbx
0x1800e51d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e51dc  nop
0x1800e51dd  mov     rcx, [rbp+18h]; this
0x1800e51e1  test    eax, eax
0x1800e51e3  jns     short loc_1800E51FA
0x1800e51e5  mov     r9d, eax; char *
0x1800e51e8  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800e51ef  mov     edx, 3Eh ; '>'; void *
0x1800e51f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e51fa  mov     rbx, [rbp+var_48]
0x1800e51fe  mov     rax, [rbx]
0x1800e5201  mov     rdi, [rax+38h]
0x1800e5205  mov     rdx, [rbp+var_40]
0x1800e5209  test    rdx, rdx
0x1800e520c  jnz     short loc_1800E522A
0x1800e520e  lea     rdx, off_1804E6B60; "Microsoft.Windows.CloudExperienceHost_c"...
0x1800e5215  lea     rcx, [rbp+string]
0x1800e5219  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800e521e  nop
0x1800e521f  mov     [rbp+var_50], 3
0x1800e5226  mov     rdx, [rax+18h]
0x1800e522a  mov     rcx, rbx
0x1800e522d  mov     rax, rdi
0x1800e5230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5235  mov     rcx, [rbp+18h]; this
0x1800e5239  test    eax, eax
0x1800e523b  jns     short loc_1800E5252
0x1800e523d  mov     r9d, eax; char *
0x1800e5240  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800e5247  mov     edx, 40h ; '@'; void *
0x1800e524c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e5252  lea     rcx, [rbp+var_48]
0x1800e5256  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e525b  nop
0x1800e525c  mov     rcx, [rbp+var_40]; string
0x1800e5260  call    cs:__imp_WindowsDeleteString
0x1800e5266  mov     rax, rsi
0x1800e5269  mov     rcx, [rbp+var_10]
0x1800e526d  xor     rcx, rsp; StackCookie
0x1800e5270  call    __security_check_cookie
0x1800e5275  mov     rbx, [rsp+70h+arg_8]
0x1800e527d  add     rsp, 70h
0x1800e5281  pop     rdi
0x1800e5282  pop     rsi
0x1800e5283  pop     rbp
0x1800e5284  retn
```
