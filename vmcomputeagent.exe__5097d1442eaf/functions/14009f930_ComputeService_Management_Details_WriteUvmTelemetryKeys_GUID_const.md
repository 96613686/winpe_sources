# ComputeService::Management::Details::WriteUvmTelemetryKeys(_GUID const &)

- ea: `0x14009f930`
- end: `0x14009fb74`
- name: `?WriteUvmTelemetryKeys@Details@Management@ComputeService@@YAXAEBU_GUID@@@Z`
- size: `580`
- prototype: `void __fastcall(ComputeService::Management::Details *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14009b0c0`

## callees

- `0x140005360`
- `0x140008760`
- `0x1400341ac`
- `0x14008ae64`
- `0x14009f930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009face`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fae8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009face`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009fae8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14009fa56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14009fa56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009f9a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009f9fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009faad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009f9a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009f9fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14009faad`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14009f96d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14009f96d`

## string_xrefs

- `0x14009fb0e`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerorchestrator.cpp`
- `0x14009fb23`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerorchestrator.cpp`
- `0x14009fb38`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerorchestrator.cpp`
- `0x14009fb4d`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerorchestrator.cpp`
- `0x14009fb62`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerorchestrator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ComputeService::Management::Details::WriteUvmTelemetryKeys(
        ComputeService::Management::Details *this,
        const struct _GUID *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  const BYTE *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // r8
  const BYTE *v9; // rcx
  unsigned int v10; // eax
  unsigned int lpData; // [rsp+20h] [rbp-39h]
  unsigned int lpDataa; // [rsp+20h] [rbp-39h]
  unsigned int lpDatab; // [rsp+20h] [rbp-39h]
  unsigned int lpDatac; // [rsp+20h] [rbp-39h]
  unsigned int lpDatad; // [rsp+20h] [rbp-39h]
  HKEY phkResult; // [rsp+50h] [rbp-9h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+7h] BYREF
  BYTE *v19[2]; // [rsp+68h] [rbp+Fh] BYREF
  int v20; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v21; // [rsp+80h] [rbp+27h]
  BYTE *v22[2]; // [rsp+88h] [rbp+2Fh] BYREF
  int v23; // [rsp+98h] [rbp+3Fh]
  unsigned __int64 v24; // [rsp+A0h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  phkResult = 0;
  v3 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control", &phkResult);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerorchestrator.cpp",
      (const char *)v3,
      lpData);
  *(_DWORD *)Data = 3;
  v4 = RegSetValueExW(phkResult, L"ContainerType", 0, 4u, Data, 4u);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerorchestrator.cpp",
      (const char *)v4,
      lpDataa);
  Vml::GuidToString(v22, this, 0);
  v5 = (const BYTE *)v22;
  if ( v24 > 7 )
    v5 = v22[0];
  v6 = RegSetValueExW(phkResult, L"ContainerId", 0, 1u, v5, 2 * v23 + 2);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerorchestrator.cpp",
      (const char *)v6,
      lpDatab);
  hKey = 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerorchestrator.cpp",
      (const char *)v7,
      lpDatac);
  LOBYTE(v8) = 1;
  Vml::GuidToString(v19, this, v8);
  v9 = (const BYTE *)v19;
  if ( v21 > 7 )
    v9 = v19[0];
  v10 = RegSetValueExW(hKey, L"MachineId", 0, 1u, v9, 2 * v20 + 2);
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerorchestrator.cpp",
      (const char *)v10,
      lpDatad);
  std::wstring::~wstring(v19);
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(v22);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x14009f930  mov     [rsp-8+arg_8], rbx
0x14009f935  push    rbp
0x14009f936  lea     rbp, [rsp-57h]
0x14009f93b  sub     rsp, 0B0h
0x14009f942  mov     rax, cs:__security_cookie
0x14009f949  xor     rax, rsp
0x14009f94c  mov     [rbp+57h+var_8], rax
0x14009f950  mov     rbx, rcx
0x14009f953  mov     [rbp+57h+phkResult], 0
0x14009f95b  lea     r8, [rbp+57h+phkResult]; phkResult
0x14009f95f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control"
0x14009f966  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14009f96d  call    cs:__imp_RegOpenKeyW
0x14009f973  mov     rcx, [rbp+5Fh]; this
0x14009f977  test    eax, eax
0x14009f979  jnz     loc_14009FB20
0x14009f97f  mov     dword ptr [rbp+57h+Data], 3
0x14009f986  lea     r9d, [rax+4]; dwType
0x14009f98a  mov     [rsp+0B0h+cbData], r9d; cbData
0x14009f98f  lea     rax, [rbp+57h+Data]
0x14009f993  mov     [rsp+0B0h+lpData], rax; unsigned int
0x14009f998  xor     r8d, r8d; Reserved
0x14009f99b  lea     rdx, aContainertype; "ContainerType"
0x14009f9a2  mov     rcx, [rbp+57h+phkResult]; hKey
0x14009f9a6  call    cs:__imp_RegSetValueExW
0x14009f9ac  mov     rcx, [rbp+5Fh]; this
0x14009f9b0  test    eax, eax
0x14009f9b2  jnz     loc_14009FB35
0x14009f9b8  xor     r8d, r8d
0x14009f9bb  mov     rdx, rbx
0x14009f9be  lea     rcx, [rbp+57h+var_28]
0x14009f9c2  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14009f9c7  nop
0x14009f9c8  mov     eax, [rbp+57h+var_18]
0x14009f9cb  lea     rcx, [rbp+57h+var_28]
0x14009f9cf  cmp     [rbp+57h+var_10], 7
0x14009f9d4  cmova   rcx, [rbp+57h+var_28]
0x14009f9d9  lea     eax, ds:2[rax*2]
0x14009f9e0  mov     [rsp+0B0h+cbData], eax; cbData
0x14009f9e4  mov     [rsp+0B0h+lpData], rcx; unsigned int
0x14009f9e9  mov     r9d, 1; dwType
0x14009f9ef  xor     r8d, r8d; Reserved
0x14009f9f2  lea     rdx, aContainerid; "ContainerId"
0x14009f9f9  mov     rcx, [rbp+57h+phkResult]; hKey
0x14009f9fd  call    cs:__imp_RegSetValueExW
0x14009fa03  mov     rcx, [rbp+5Fh]; this
0x14009fa07  test    eax, eax
0x14009fa09  jnz     loc_14009FB4A
0x14009fa0f  mov     [rbp+57h+hKey], 0
0x14009fa17  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x14009fa20  lea     rax, [rbp+57h+hKey]
0x14009fa24  mov     [rsp+0B0h+var_78], rax; phkResult
0x14009fa29  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14009fa32  mov     [rsp+0B0h+cbData], 20006h; samDesired
0x14009fa3a  mov     dword ptr [rsp+0B0h+lpData], 0; unsigned int
0x14009fa42  xor     r9d, r9d; lpClass
0x14009fa45  xor     r8d, r8d; Reserved
0x14009fa48  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\SQMClient"
0x14009fa4f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14009fa56  call    cs:__imp_RegCreateKeyExW
0x14009fa5c  mov     rcx, [rbp+5Fh]; this
0x14009fa60  test    eax, eax
0x14009fa62  jnz     loc_14009FB5F
0x14009fa68  mov     r8b, 1
0x14009fa6b  mov     rdx, rbx
0x14009fa6e  lea     rcx, [rbp+57h+var_48]
0x14009fa72  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14009fa77  nop
0x14009fa78  mov     eax, [rbp+57h+var_38]
0x14009fa7b  lea     rcx, [rbp+57h+var_48]
0x14009fa7f  cmp     [rbp+57h+var_30], 7
0x14009fa84  cmova   rcx, [rbp+57h+var_48]
0x14009fa89  lea     eax, ds:2[rax*2]
0x14009fa90  mov     [rsp+0B0h+cbData], eax; cbData
0x14009fa94  mov     [rsp+0B0h+lpData], rcx; unsigned int
0x14009fa99  mov     r9d, 1; dwType
0x14009fa9f  xor     r8d, r8d; Reserved
0x14009faa2  lea     rdx, aMachineid; "MachineId"
0x14009faa9  mov     rcx, [rbp+57h+hKey]; hKey
0x14009faad  call    cs:__imp_RegSetValueExW
0x14009fab3  mov     rcx, [rbp+5Fh]; this
0x14009fab7  test    eax, eax
0x14009fab9  jnz     short loc_14009FB0B
0x14009fabb  lea     rcx, [rbp+57h+var_48]; void *
0x14009fabf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009fac4  nop
0x14009fac5  mov     rcx, [rbp+57h+hKey]; hKey
0x14009fac9  test    rcx, rcx
0x14009facc  jz      short loc_14009FAD5
0x14009face  call    cs:__imp_RegCloseKey
0x14009fad4  nop
0x14009fad5  lea     rcx, [rbp+57h+var_28]; void *
0x14009fad9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009fade  nop
0x14009fadf  mov     rcx, [rbp+57h+phkResult]; hKey
0x14009fae3  test    rcx, rcx
0x14009fae6  jz      short loc_14009FAEE
0x14009fae8  call    cs:__imp_RegCloseKey
0x14009faee  mov     rcx, [rbp+57h+var_8]
0x14009faf2  xor     rcx, rsp; StackCookie
0x14009faf5  call    __security_check_cookie
0x14009fafa  mov     rbx, [rsp+0B0h+arg_8]
0x14009fb02  add     rsp, 0B0h
0x14009fb09  pop     rbp
0x14009fb0a  retn
0x14009fb0b  mov     r9d, eax; char *
0x14009fb0e  lea     r8, aOnecoreVmCompu_25; "onecore\\vm\\compute\\management\\orche"...
0x14009fb15  mov     edx, 6Eh ; 'n'; void *
0x14009fb1a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009fb20  mov     r9d, eax; char *
0x14009fb23  lea     r8, aOnecoreVmCompu_25; "onecore\\vm\\compute\\management\\orche"...
0x14009fb2a  mov     edx, 58h ; 'X'; void *
0x14009fb2f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009fb35  mov     r9d, eax; char *
0x14009fb38  lea     r8, aOnecoreVmCompu_25; "onecore\\vm\\compute\\management\\orche"...
0x14009fb3f  mov     edx, 5Eh ; '^'; void *
0x14009fb44  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009fb4a  mov     r9d, eax; char *
0x14009fb4d  lea     r8, aOnecoreVmCompu_25; "onecore\\vm\\compute\\management\\orche"...
0x14009fb54  mov     edx, 64h ; 'd'; void *
0x14009fb59  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009fb5f  mov     r9d, eax; char *
0x14009fb62  lea     r8, aOnecoreVmCompu_25; "onecore\\vm\\compute\\management\\orche"...
0x14009fb69  mov     edx, 68h ; 'h'; void *
0x14009fb6e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
