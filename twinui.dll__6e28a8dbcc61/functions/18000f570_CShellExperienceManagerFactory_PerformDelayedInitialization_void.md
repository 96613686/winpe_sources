# CShellExperienceManagerFactory::PerformDelayedInitialization(void)

- ea: `0x18000f570`
- end: `0x18000f861`
- name: `?PerformDelayedInitialization@CShellExperienceManagerFactory@@UEAAJXZ`
- size: `753`
- prototype: `__int64 __fastcall(CShellExperienceManagerFactory *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18000f570`
- `0x180010370`
- `0x18003c5e4`
- `0x18003c898`
- `0x18008d06c`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f5d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f6ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f71c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f78b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f7fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f5d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f6ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f71c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f78b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f7fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f7e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellExperienceManagerFactory::PerformDelayedInitialization(CShellExperienceManagerFactory *this)
{
  HRESULT v2; // eax
  CShellExperienceManagerFactory *v3; // rdi
  int ExperienceManager; // eax
  ExperienceManagerUtils *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HRESULT v9; // eax
  int v10; // eax
  HRESULT v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  HRESULT v15; // eax
  int v16; // eax
  struct IInspectable *v17; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v17 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.Host", 0x25u, &hstringHeader, &string);
  if ( v2 < 0 )
    RaiseException(v2, 1u, 0, 0);
  v3 = (CShellExperienceManagerFactory *)((char *)this + 72);
  ExperienceManager = CShellExperienceManagerFactory::GetExperienceManager(v3, string, &v17);
  v6 = ExperienceManager;
  if ( ExperienceManager < 0 )
  {
    v7 = 206;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\factory.cpp",
      (const char *)(unsigned int)ExperienceManager,
      (int)v17);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
    return v6;
  }
  if ( ExperienceManagerUtils::IsPreReleaseExperience(v5) )
  {
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.ShellExperience.Test",
      0x26u,
      0x25u);
    ExperienceManager = CShellExperienceManagerFactory::GetExperienceManager(v3, string, &v17);
    v6 = ExperienceManager;
    if ( ExperienceManager < 0 )
    {
      v7 = 209;
      goto LABEL_8;
    }
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.ScreenClipping", 0x2Fu, &hstringHeader, &string);
  if ( v9 < 0 )
    RaiseException(v9, 1u, 0, 0);
  v10 = CShellExperienceManagerFactory::GetExperienceManager(v3, string, &v17);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\factory.cpp",
      (const char *)(unsigned int)v10,
      (int)v17);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.PenWorkspace", 0x2Du, &hstringHeader, &string);
  if ( v11 < 0 )
    RaiseException(v11, 1u, 0, 0);
  v12 = CShellExperienceManagerFactory::GetExperienceManager(v3, string, &v17);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\factory.cpp",
      (const char *)(unsigned int)v12,
      (int)v17);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.Insights", 0x29u, &hstringHeader, &string);
  if ( v13 < 0 )
    RaiseException(v13, 1u, 0, 0);
  v14 = CShellExperienceManagerFactory::GetExperienceManager(v3, string, &v17);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\factory.cpp",
      (const char *)(unsigned int)v14,
      (int)v17);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
  string = 0;
  v15 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.NetworkFlyout", 0x2Eu, &hstringHeader, &string);
  if ( v15 < 0 )
    RaiseException(v15, 1u, 0, 0);
  v16 = CShellExperienceManagerFactory::GetExperienceManager(v3, string, &v17);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\factory.cpp",
      (const char *)(unsigned int)v16,
      (int)v17);
  if ( v17 )
    ((void (__fastcall *)(struct IInspectable *))v17->lpVtbl->Release)(v17);
  return 0;
}

```

## disassembly

```asm
0x18000f570  mov     [rsp-8+arg_8], rbx
0x18000f575  mov     [rsp-8+arg_10], rdi
0x18000f57a  push    rbp
0x18000f57b  mov     rbp, rsp
0x18000f57e  sub     rsp, 50h
0x18000f582  mov     rax, cs:__security_cookie
0x18000f589  xor     rax, rsp
0x18000f58c  mov     [rbp+var_8], rax
0x18000f590  mov     rdi, rcx
0x18000f593  mov     [rbp+var_30], 0
0x18000f59b  lea     rcx, [rbp+var_30]
0x18000f59f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f5a4  mov     [rbp+string], 0
0x18000f5ac  lea     r9, [rbp+string]; string
0x18000f5b0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f5b4  mov     edx, 25h ; '%'; length
0x18000f5b9  lea     rcx, aWindowsInterna_34; "Windows.Internal.ShellExperience.Host"
0x18000f5c0  call    cs:__imp_WindowsCreateStringReference
0x18000f5c6  test    eax, eax
0x18000f5c8  jns     short loc_18000F5DD
0x18000f5ca  xor     r9d, r9d; lpArguments
0x18000f5cd  xor     r8d, r8d; nNumberOfArguments
0x18000f5d0  lea     edx, [r9+1]; dwExceptionFlags
0x18000f5d4  mov     ecx, eax; dwExceptionCode
0x18000f5d6  call    cs:__imp_RaiseException
0x18000f5dc  nop
0x18000f5dd  add     rdi, 48h ; 'H'
0x18000f5e1  lea     r8, [rbp+var_30]; struct IInspectable **
0x18000f5e5  mov     rdx, [rbp+string]; HSTRING
0x18000f5e9  mov     rcx, rdi; this
0x18000f5ec  call    ?GetExperienceManager@CShellExperienceManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; CShellExperienceManagerFactory::GetExperienceManager(HSTRING__ *,IInspectable * *)
0x18000f5f1  mov     ebx, eax
0x18000f5f3  test    eax, eax
0x18000f5f5  jns     short loc_18000F5FE
0x18000f5f7  mov     edx, 0CEh
0x18000f5fc  jmp     short loc_18000F64E
0x18000f5fe  call    ?IsPreReleaseExperience@ExperienceManagerUtils@@YA_NXZ; ExperienceManagerUtils::IsPreReleaseExperience(void)
0x18000f603  test    al, al
0x18000f605  jz      short loc_18000F672
0x18000f607  lea     rcx, [rbp+var_30]
0x18000f60b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f610  mov     [rbp+string], 0
0x18000f618  mov     r9d, 25h ; '%'; unsigned int
0x18000f61e  lea     r8d, [r9+1]; unsigned int
0x18000f622  lea     rdx, aWindowsInterna_2; "Windows.Internal.ShellExperience.Test"
0x18000f629  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000f62d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000f632  nop
0x18000f633  lea     r8, [rbp+var_30]; struct IInspectable **
0x18000f637  mov     rdx, [rbp+string]; HSTRING
0x18000f63b  mov     rcx, rdi; this
0x18000f63e  call    ?GetExperienceManager@CShellExperienceManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; CShellExperienceManagerFactory::GetExperienceManager(HSTRING__ *,IInspectable * *)
0x18000f643  mov     ebx, eax
0x18000f645  test    eax, eax
0x18000f647  jns     short loc_18000F672
0x18000f649  mov     edx, 0D1h; void *
0x18000f64e  mov     r9d, eax; char *
0x18000f651  lea     r8, aShellTwinuiExp; "shell\\twinui\\experiencemanagers\\lib"...
0x18000f658  mov     rcx, [rbp+8]; this
0x18000f65c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f661  nop
0x18000f662  lea     rcx, [rbp+var_30]
0x18000f666  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f66b  mov     eax, ebx
0x18000f66d  jmp     loc_18000F845
0x18000f672  lea     rcx, [rbp+var_30]
0x18000f676  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f67b  mov     [rbp+string], 0
0x18000f683  lea     r9, [rbp+string]; string
0x18000f687  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f68b  mov     edx, 2Fh ; '/'; length
0x18000f690  lea     rcx, aWindowsInterna_7; "Windows.Internal.ShellExperience.Screen"...
0x18000f697  call    cs:__imp_WindowsCreateStringReference
0x18000f69d  test    eax, eax
0x18000f69f  jns     short loc_18000F6B4
0x18000f6a1  xor     r9d, r9d; lpArguments
0x18000f6a4  xor     r8d, r8d; nNumberOfArguments
0x18000f6a7  lea     edx, [r9+1]; dwExceptionFlags
0x18000f6ab  mov     ecx, eax; dwExceptionCode
0x18000f6ad  call    cs:__imp_RaiseException
0x18000f6b3  nop
0x18000f6b4  lea     r8, [rbp+var_30]; struct IInspectable **
0x18000f6b8  mov     rdx, [rbp+string]; HSTRING
0x18000f6bc  mov     rcx, rdi; this
0x18000f6bf  call    ?GetExperienceManager@CShellExperienceManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; CShellExperienceManagerFactory::GetExperienceManager(HSTRING__ *,IInspectable * *)
0x18000f6c4  mov     rcx, [rbp+8]; this
0x18000f6c8  test    eax, eax
0x18000f6ca  jns     short loc_18000F6E1
0x18000f6cc  mov     r9d, eax; char *
0x18000f6cf  lea     r8, aShellTwinuiExp; "shell\\twinui\\experiencemanagers\\lib"...
0x18000f6d6  mov     edx, 0D4h; void *
0x18000f6db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f6e0  nop
0x18000f6e1  lea     rcx, [rbp+var_30]
0x18000f6e5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f6ea  mov     [rbp+string], 0
0x18000f6f2  lea     r9, [rbp+string]; string
0x18000f6f6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f6fa  mov     edx, 2Dh ; '-'; length
0x18000f6ff  lea     rcx, aWindowsInterna_18; "Windows.Internal.ShellExperience.PenWor"...
0x18000f706  call    cs:__imp_WindowsCreateStringReference
0x18000f70c  test    eax, eax
0x18000f70e  jns     short loc_18000F723
0x18000f710  xor     r9d, r9d; lpArguments
0x18000f713  xor     r8d, r8d; nNumberOfArguments
0x18000f716  lea     edx, [r9+1]; dwExceptionFlags
0x18000f71a  mov     ecx, eax; dwExceptionCode
0x18000f71c  call    cs:__imp_RaiseException
0x18000f722  nop
0x18000f723  lea     r8, [rbp+var_30]; struct IInspectable **
0x18000f727  mov     rdx, [rbp+string]; HSTRING
0x18000f72b  mov     rcx, rdi; this
0x18000f72e  call    ?GetExperienceManager@CShellExperienceManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; CShellExperienceManagerFactory::GetExperienceManager(HSTRING__ *,IInspectable * *)
0x18000f733  mov     rcx, [rbp+8]; this
0x18000f737  test    eax, eax
0x18000f739  jns     short loc_18000F750
0x18000f73b  mov     r9d, eax; char *
0x18000f73e  lea     r8, aShellTwinuiExp; "shell\\twinui\\experiencemanagers\\lib"...
0x18000f745  mov     edx, 0DAh; void *
0x18000f74a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f74f  nop
0x18000f750  lea     rcx, [rbp+var_30]
0x18000f754  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f759  mov     [rbp+string], 0
0x18000f761  lea     r9, [rbp+string]; string
0x18000f765  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f769  mov     edx, 29h ; ')'; length
0x18000f76e  lea     rcx, aWindowsInterna_25; "Windows.Internal.ShellExperience.Insigh"...
0x18000f775  call    cs:__imp_WindowsCreateStringReference
0x18000f77b  test    eax, eax
0x18000f77d  jns     short loc_18000F792
0x18000f77f  xor     r9d, r9d; lpArguments
0x18000f782  xor     r8d, r8d; nNumberOfArguments
0x18000f785  lea     edx, [r9+1]; dwExceptionFlags
0x18000f789  mov     ecx, eax; dwExceptionCode
0x18000f78b  call    cs:__imp_RaiseException
0x18000f791  nop
0x18000f792  lea     r8, [rbp+var_30]; struct IInspectable **
0x18000f796  mov     rdx, [rbp+string]; HSTRING
0x18000f79a  mov     rcx, rdi; this
0x18000f79d  call    ?GetExperienceManager@CShellExperienceManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; CShellExperienceManagerFactory::GetExperienceManager(HSTRING__ *,IInspectable * *)
0x18000f7a2  mov     rcx, [rbp+8]; this
0x18000f7a6  test    eax, eax
0x18000f7a8  jns     short loc_18000F7BF
0x18000f7aa  mov     r9d, eax; char *
0x18000f7ad  lea     r8, aShellTwinuiExp; "shell\\twinui\\experiencemanagers\\lib"...
0x18000f7b4  mov     edx, 0DCh; void *
0x18000f7b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f7be  nop
0x18000f7bf  lea     rcx, [rbp+var_30]
0x18000f7c3  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000f7c8  mov     [rbp+string], 0
0x18000f7d0  lea     r9, [rbp+string]; string
0x18000f7d4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f7d8  mov     edx, 2Eh ; '.'; length
0x18000f7dd  lea     rcx, aWindowsInterna_39; "Windows.Internal.ShellExperience.Networ"...
0x18000f7e4  call    cs:__imp_WindowsCreateStringReference
0x18000f7ea  test    eax, eax
0x18000f7ec  jns     short loc_18000F801
0x18000f7ee  xor     r9d, r9d; lpArguments
0x18000f7f1  xor     r8d, r8d; nNumberOfArguments
0x18000f7f4  lea     edx, [r9+1]; dwExceptionFlags
0x18000f7f8  mov     ecx, eax; dwExceptionCode
0x18000f7fa  call    cs:__imp_RaiseException
0x18000f800  nop
0x18000f801  lea     r8, [rbp+var_30]; struct IInspectable **
0x18000f805  mov     rdx, [rbp+string]; HSTRING
0x18000f809  mov     rcx, rdi; this
0x18000f80c  call    ?GetExperienceManager@CShellExperienceManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; CShellExperienceManagerFactory::GetExperienceManager(HSTRING__ *,IInspectable * *)
0x18000f811  mov     rcx, [rbp+8]; this
0x18000f815  test    eax, eax
0x18000f817  jns     short loc_18000F82E
0x18000f819  mov     r9d, eax; char *
0x18000f81c  lea     r8, aShellTwinuiExp; "shell\\twinui\\experiencemanagers\\lib"...
0x18000f823  mov     edx, 0DDh; void *
0x18000f828  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f82d  nop
0x18000f82e  mov     rcx, [rbp+var_30]
0x18000f832  test    rcx, rcx
0x18000f835  jz      short loc_18000F843
0x18000f837  mov     rax, [rcx]
0x18000f83a  mov     rax, [rax+10h]
0x18000f83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f843  xor     eax, eax
0x18000f845  mov     rcx, [rbp+var_8]
0x18000f849  xor     rcx, rsp; StackCookie
0x18000f84c  call    __security_check_cookie
0x18000f851  mov     rbx, [rsp+50h+arg_8]
0x18000f856  mov     rdi, [rsp+50h+arg_10]
0x18000f85b  add     rsp, 50h
0x18000f85f  pop     rbp
0x18000f860  retn
```
