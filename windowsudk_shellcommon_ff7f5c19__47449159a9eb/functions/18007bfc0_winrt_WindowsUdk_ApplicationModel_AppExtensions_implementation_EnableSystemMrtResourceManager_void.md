# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::EnableSystemMrtResourceManager(void)

- ea: `0x18007bfc0`
- end: `0x18007c16c`
- name: `?EnableSystemMrtResourceManager@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YAXXZ`
- size: `428`
- prototype: `void __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1802a74ac`
- `0x1802a77f4`

## callees

- `0x180044668`
- `0x18007bfc0`
- `0x1800e488c`
- `0x18015cb00`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007c01a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007c01a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007c004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007c004`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007c03c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007c03c`

## string_xrefs

- `0x18007c04d`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\XamlExtensions.cpp`
- `0x18007c09c`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\XamlExtensions.cpp`
- `0x18007c0e4`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\XamlExtensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::EnableSystemMrtResourceManager(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *this)
{
  HRESULT v1; // eax
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rdi
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v16 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Resources.Core.ResourceManager",
         0x37u,
         &hstringHeader,
         &string);
  if ( v1 < 0 )
    RaiseException(v1, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7, &v16);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtensions.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
  v15 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  v5 = **v16;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v6 = v5(v4, &GUID_4a8eac58_b652_459d_8de1_239471e8b22b, &v15);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtensions.cpp",
      (const char *)(unsigned int)v6,
      (int)hstringHeader.Reserved.Reserved1);
  v17 = 0;
  v7 = v15;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v9 = v8(v7, &v17);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\XamlExtensions.cpp",
      (const char *)(unsigned int)v9,
      (int)hstringHeader.Reserved.Reserved1);
  v10 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  if ( v16 )
  {
    v16 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v12)[2])(v12);
  }
}

```

## disassembly

```asm
0x18007bfc0  mov     [rsp-8+arg_0], rbx
0x18007bfc5  mov     [rsp-8+arg_8], rdi
0x18007bfca  push    rbp
0x18007bfcb  mov     rbp, rsp
0x18007bfce  sub     rsp, 60h
0x18007bfd2  mov     rax, cs:__security_cookie
0x18007bfd9  xor     rax, rsp
0x18007bfdc  mov     [rbp+var_8], rax
0x18007bfe0  mov     [rbp+var_18], 0
0x18007bfe8  mov     [rbp+string], 0
0x18007bff0  lea     r9, [rbp+string]; string
0x18007bff4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007bff8  mov     edx, 37h ; '7'; length
0x18007bffd  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Resources_Core_ResourceManager@@3QB_WB; "Windows.ApplicationModel.Resources.Core"...
0x18007c004  call    cs:__imp_WindowsCreateStringReference
0x18007c00a  test    eax, eax
0x18007c00c  jns     short loc_18007C021
0x18007c00e  xor     r9d, r9d; lpArguments
0x18007c011  xor     r8d, r8d; nNumberOfArguments
0x18007c014  lea     edx, [r9+1]; dwExceptionFlags
0x18007c018  mov     ecx, eax; dwExceptionCode
0x18007c01a  call    cs:__imp_RaiseException
0x18007c020  nop
0x18007c021  mov     rbx, [rbp+string]
0x18007c025  lea     rcx, [rbp+var_18]
0x18007c029  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007c02e  lea     r8, [rbp+var_18]
0x18007c032  lea     rdx, _GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7
0x18007c039  mov     rcx, rbx
0x18007c03c  call    cs:__imp_RoGetActivationFactory
0x18007c042  mov     rcx, [rbp+8]; this
0x18007c046  test    eax, eax
0x18007c048  jns     short loc_18007C05F
0x18007c04a  mov     r9d, eax; char *
0x18007c04d  lea     r8, aShellcommonUnd_21; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18007c054  mov     edx, 2Ch ; ','; void *
0x18007c059  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007c05f  mov     [rbp+var_20], 0
0x18007c067  mov     rbx, [rbp+var_18]
0x18007c06b  mov     rax, [rbx]
0x18007c06e  mov     rdi, [rax]
0x18007c071  lea     rcx, [rbp+var_20]
0x18007c075  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007c07a  lea     r8, [rbp+var_20]
0x18007c07e  lea     rdx, _GUID_4a8eac58_b652_459d_8de1_239471e8b22b
0x18007c085  mov     rcx, rbx
0x18007c088  mov     rax, rdi
0x18007c08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c090  nop
0x18007c091  mov     rcx, [rbp+8]; this
0x18007c095  test    eax, eax
0x18007c097  jns     short loc_18007C0AE
0x18007c099  mov     r9d, eax; char *
0x18007c09c  lea     r8, aShellcommonUnd_21; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18007c0a3  mov     edx, 2Eh ; '.'; void *
0x18007c0a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007c0ae  mov     [rbp+var_10], 0
0x18007c0b6  mov     rdi, [rbp+var_20]
0x18007c0ba  mov     rax, [rdi]
0x18007c0bd  mov     rbx, [rax+38h]
0x18007c0c1  lea     rcx, [rbp+var_10]
0x18007c0c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007c0ca  lea     rdx, [rbp+var_10]
0x18007c0ce  mov     rcx, rdi
0x18007c0d1  mov     rax, rbx
0x18007c0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0d9  mov     rcx, [rbp+8]; this
0x18007c0dd  test    eax, eax
0x18007c0df  jns     short loc_18007C0F6
0x18007c0e1  mov     r9d, eax; char *
0x18007c0e4  lea     r8, aShellcommonUnd_21; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18007c0eb  mov     edx, 30h ; '0'; void *
0x18007c0f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007c0f6  mov     rcx, [rbp+var_10]
0x18007c0fa  test    rcx, rcx
0x18007c0fd  jz      short loc_18007C114
0x18007c0ff  mov     [rbp+var_10], 0
0x18007c107  mov     rax, [rcx]
0x18007c10a  mov     rax, [rax+10h]
0x18007c10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c113  nop
0x18007c114  mov     rcx, [rbp+var_20]
0x18007c118  test    rcx, rcx
0x18007c11b  jz      short loc_18007C132
0x18007c11d  mov     [rbp+var_20], 0
0x18007c125  mov     rax, [rcx]
0x18007c128  mov     rax, [rax+10h]
0x18007c12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c131  nop
0x18007c132  mov     rcx, [rbp+var_18]
0x18007c136  test    rcx, rcx
0x18007c139  jz      short loc_18007C150
0x18007c13b  mov     [rbp+var_18], 0
0x18007c143  mov     rax, [rcx]
0x18007c146  mov     rax, [rax+10h]
0x18007c14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c14f  nop
0x18007c150  mov     rcx, [rbp+var_8]
0x18007c154  xor     rcx, rsp; StackCookie
0x18007c157  call    __security_check_cookie
0x18007c15c  mov     rbx, [rsp+60h+arg_0]
0x18007c161  mov     rdi, [rsp+60h+arg_8]
0x18007c166  add     rsp, 60h
0x18007c16a  pop     rbp
0x18007c16b  retn
```
