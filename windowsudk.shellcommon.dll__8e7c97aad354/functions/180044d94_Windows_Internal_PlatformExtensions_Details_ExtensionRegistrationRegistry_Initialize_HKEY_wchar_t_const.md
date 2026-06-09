# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,wchar_t const *)

- ea: `0x180044d94`
- end: `0x180044f67`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEB_W@Z`
- size: `467`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180044c20`

## callees

- `0x180044d94`
- `0x180044f70`
- `0x1800a5140`
- `0x1800e34bc`
- `0x1800e3660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044dde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044dde`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044e5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044ee7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044e5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044ee7`

## string_xrefs

- `0x180044e01`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180044e67`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180044e41`: `ExtensionClass`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        HKEY a2,
        const wchar_t *a3)
{
  HKEY *v3; // r14
  unsigned int v5; // ebx
  unsigned int ValueW; // eax
  const char *v8; // r9
  int RegValue; // edi
  __int64 v10; // rdx
  HKEY v11; // rcx
  unsigned int v12; // eax
  const char *v13; // r9
  HKEY v14; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  unsigned int phkResultc; // [rsp+20h] [rbp-40h]
  char *v19; // [rsp+40h] [rbp-20h]
  HKEY v20; // [rsp+48h] [rbp-18h] BYREF
  char v21; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD pcbData; // [rsp+80h] [rbp+20h] BYREF
  int pvData; // [rsp+98h] [rbp+38h] BYREF

  v3 = (HKEY *)((char *)this + 8);
  v20 = 0;
  v19 = (char *)this + 8;
  v21 = 1;
  v5 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &v20);
  if ( v21 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v19,
      v20);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE0,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)v5,
             phkResult);
  pcbData = 256;
  ValueW = RegGetValueW(*v3, 0, L"ExtensionClass", 2u, 0, (char *)this + 24, &pcbData);
  v8 = 0;
  if ( ValueW != 2 )
    v8 = (const char *)ValueW;
  if ( (_DWORD)v8 )
  {
    RegValue = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x118,
                 (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
                 v8,
                 phkResulta);
    if ( RegValue < 0 )
    {
      v10 = 227;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)RegValue,
        phkResultb);
      return (unsigned int)RegValue;
    }
  }
  v11 = *v3;
  pvData = 0;
  pcbData = 4;
  v12 = RegGetValueW(v11, 0, L"Test", 0x10u, 0, &pvData, &pcbData);
  v13 = 0;
  if ( v12 != 2 )
    v13 = (const char *)v12;
  if ( (_DWORD)v13 )
  {
    RegValue = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x118,
                 (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
                 v13,
                 phkResultc);
    if ( RegValue < 0 )
    {
      v10 = 231;
      goto LABEL_10;
    }
  }
  v14 = *v3;
  pcbData = 4;
  *((_BYTE *)this + 16) = pvData != 0;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               v14,
               L"VelocityFeatureId",
               0x10u,
               (char *)this + 20,
               &pcbData);
  if ( RegValue < 0 )
  {
    v10 = 235;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x180044d94  mov     [rsp-18h+arg_8], rbx
0x180044d99  mov     [rsp-18h+arg_10], rsi
0x180044d9e  push    rbp
0x180044d9f  push    rdi
0x180044da0  push    r14
0x180044da2  mov     rbp, rsp
0x180044da5  sub     rsp, 60h
0x180044da9  lea     r14, [rcx+8]
0x180044dad  mov     [rbp+var_18], 0
0x180044db5  mov     rsi, rcx
0x180044db8  mov     [rbp+var_20], r14
0x180044dbc  mov     rax, r8
0x180044dbf  mov     [rbp+var_10], 1
0x180044dc3  mov     r10, rdx
0x180044dc6  lea     rcx, [rbp+var_18]
0x180044dca  mov     [rsp+60h+phkResult], rcx; unsigned int
0x180044dcf  mov     r9d, 20019h; samDesired
0x180044dd5  mov     rcx, r10; hKey
0x180044dd8  xor     r8d, r8d; ulOptions
0x180044ddb  mov     rdx, rax; lpSubKey
0x180044dde  call    cs:__imp_RegOpenKeyExW
0x180044de4  cmp     [rbp+var_10], 0
0x180044de8  mov     ebx, eax
0x180044dea  jz      short loc_180044DF9
0x180044dec  mov     rdx, [rbp+var_18]
0x180044df0  mov     rcx, [rbp+var_20]
0x180044df4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180044df9  test    ebx, ebx
0x180044dfb  jz      short loc_180044E2A
0x180044dfd  mov     rcx, [rbp+18h]; this
0x180044e01  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180044e08  mov     r9d, ebx; char *
0x180044e0b  mov     edx, 0E0h; void *
0x180044e10  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044e15  lea     r11, [rsp+60h+var_s0]
0x180044e1a  mov     rbx, [r11+28h]
0x180044e1e  mov     rsi, [r11+30h]
0x180044e22  mov     rsp, r11
0x180044e25  pop     r14
0x180044e27  pop     rdi
0x180044e28  pop     rbp
0x180044e29  retn
0x180044e2a  lea     rcx, [rbp+arg_0]
0x180044e2e  mov     [rbp+arg_0], 100h
0x180044e35  mov     [rsp+60h+pcbData], rcx; pcbData
0x180044e3a  lea     rax, [rsi+18h]
0x180044e3e  mov     rcx, [r14]; hkey
0x180044e41  lea     r8, aExtensionclass; "ExtensionClass"
0x180044e48  mov     [rsp+60h+pvData], rax; pvData
0x180044e4d  mov     r9d, 2; dwFlags
0x180044e53  xor     edx, edx; lpSubKey
0x180044e55  mov     [rsp+60h+phkResult], 0; int
0x180044e5e  call    cs:__imp_RegGetValueW
0x180044e64  xor     r9d, r9d
0x180044e67  lea     rbx, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180044e6e  cmp     eax, 2
0x180044e71  cmovnz  r9d, eax; char *
0x180044e75  test    r9d, r9d
0x180044e78  jz      short loc_180044EAC
0x180044e7a  mov     rcx, [rbp+18h]; this
0x180044e7e  mov     r8, rbx; unsigned int
0x180044e81  mov     edx, 118h; void *
0x180044e86  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044e8b  mov     edi, eax
0x180044e8d  test    eax, eax
0x180044e8f  jns     short loc_180044EAC
0x180044e91  mov     edx, 0E3h; void *
0x180044e96  mov     rcx, [rbp+18h]; this
0x180044e9a  mov     r9d, edi; char *
0x180044e9d  mov     r8, rbx; unsigned int
0x180044ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044ea5  mov     eax, edi
0x180044ea7  jmp     loc_180044E15
0x180044eac  mov     rcx, [r14]; hkey
0x180044eaf  lea     rax, [rbp+arg_0]
0x180044eb3  mov     [rsp+60h+pcbData], rax; pcbData
0x180044eb8  lea     r8, aTest; "Test"
0x180044ebf  lea     rax, [rbp+arg_18]
0x180044ec3  mov     [rbp+arg_18], 0
0x180044eca  mov     [rsp+60h+pvData], rax; pvData
0x180044ecf  mov     r9d, 10h; dwFlags
0x180044ed5  xor     edx, edx; lpSubKey
0x180044ed7  mov     [rsp+60h+phkResult], 0; unsigned int
0x180044ee0  mov     [rbp+arg_0], 4
0x180044ee7  call    cs:__imp_RegGetValueW
0x180044eed  xor     r9d, r9d
0x180044ef0  cmp     eax, 2
0x180044ef3  cmovnz  r9d, eax; char *
0x180044ef7  test    r9d, r9d
0x180044efa  jz      short loc_180044F1D
0x180044efc  mov     rcx, [rbp+18h]; this
0x180044f00  mov     r8, rbx; unsigned int
0x180044f03  mov     edx, 118h; void *
0x180044f08  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044f0d  mov     edi, eax
0x180044f0f  test    eax, eax
0x180044f11  jns     short loc_180044F1D
0x180044f13  mov     edx, 0E7h
0x180044f18  jmp     loc_180044E96
0x180044f1d  cmp     [rbp+arg_18], 0
0x180044f21  lea     r9, [rsi+14h]; void *
0x180044f25  mov     rcx, [r14]; HKEY
0x180044f28  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x180044f2f  setnz   al
0x180044f32  mov     [rbp+arg_0], 4
0x180044f39  mov     [rsi+10h], al
0x180044f3c  mov     r8d, 10h; unsigned int
0x180044f42  lea     rax, [rbp+arg_0]
0x180044f46  mov     [rsp+60h+phkResult], rax; unsigned int *
0x180044f4b  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEB_WKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,wchar_t const *,ulong,void *,ulong *)
0x180044f50  mov     edi, eax
0x180044f52  test    eax, eax
0x180044f54  jns     short loc_180044F60
0x180044f56  mov     edx, 0EBh
0x180044f5b  jmp     loc_180044E96
0x180044f60  xor     eax, eax
0x180044f62  jmp     loc_180044E15
```
