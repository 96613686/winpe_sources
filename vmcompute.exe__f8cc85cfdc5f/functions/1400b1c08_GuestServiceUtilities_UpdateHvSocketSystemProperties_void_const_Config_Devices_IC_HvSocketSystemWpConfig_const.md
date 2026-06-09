# GuestServiceUtilities::UpdateHvSocketSystemProperties(void * const,Config::Devices::IC::HvSocketSystemWpConfig const &)

- ea: `0x1400b1c08`
- end: `0x1400b1dbc`
- name: `?UpdateHvSocketSystemProperties@GuestServiceUtilities@@YAXQEAXAEBUHvSocketSystemWpConfig@IC@Devices@Config@@@Z`
- size: `436`
- prototype: `void __fastcall(HANDLE hDevice, LPCWSTR StringSecurityDescriptor, const struct Config::Devices::IC::HvSocketSystemWpConfig *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140170834`
- `0x140203d74`

## callees

- `0x140080180`
- `0x1400b1c08`
- `0x1400b1dd0`
- `0x1400b20e4`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b1c80`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b1cee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b1c80`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400b1cee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400b1d64`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400b1d64`

## string_xrefs

- `0x1400b1c90`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400b1cfe`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400b1d74`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GuestServiceUtilities::UpdateHvSocketSystemProperties(
        HANDLE hDevice,
        const WCHAR *StringSecurityDescriptor,
        const struct Config::Devices::IC::HvSocketSystemWpConfig *a3)
{
  const WCHAR *v5; // rcx
  const char *v6; // r9
  LPCWSTR v7; // rcx
  const char *v8; // r9
  const char *v9; // r9
  __int64 *v10; // [rsp+40h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-1h] BYREF
  char v12; // [rsp+50h] [rbp+7h]
  __int128 InBuffer; // [rsp+58h] [rbp+Fh] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v15; // [rsp+70h] [rbp+27h] BYREF
  __int64 v16; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  InBuffer = 0;
  v16 = 0;
  v15 = 0;
  if ( *((_QWORD *)StringSecurityDescriptor + 2) )
  {
    v10 = &v16;
    SecurityDescriptor = 0;
    v12 = 1;
    if ( *((_QWORD *)StringSecurityDescriptor + 3) <= 7u )
      v5 = StringSecurityDescriptor;
    else
      v5 = *(const WCHAR **)StringSecurityDescriptor;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v5, 1u, &SecurityDescriptor, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
        v6);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v10);
    *(_QWORD *)&InBuffer = v16;
  }
  if ( *((_QWORD *)StringSecurityDescriptor + 6) )
  {
    v10 = &v15;
    SecurityDescriptor = 0;
    v12 = 1;
    v7 = StringSecurityDescriptor + 16;
    if ( *((_QWORD *)StringSecurityDescriptor + 7) > 7u )
      v7 = *(LPCWSTR *)v7;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
        v8);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v10);
    *((_QWORD *)&InBuffer + 1) = v15;
  }
  BytesReturned = 0;
  if ( !DeviceIoControl(hDevice, 0x21C008u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
      v9);
  Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&v15);
  Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&v16);
}

```

## disassembly

```asm
0x1400b1c08  mov     [rsp-8+arg_10], rbx
0x1400b1c0d  push    rbp
0x1400b1c0e  push    rsi
0x1400b1c0f  push    rdi
0x1400b1c10  lea     rbp, [rsp-47h]
0x1400b1c15  sub     rsp, 90h
0x1400b1c1c  mov     rax, cs:__security_cookie
0x1400b1c23  xor     rax, rsp
0x1400b1c26  mov     [rbp+57h+var_20], rax
0x1400b1c2a  mov     rbx, rdx
0x1400b1c2d  mov     rsi, rcx
0x1400b1c30  xorps   xmm0, xmm0
0x1400b1c33  movups  [rbp+57h+InBuffer], xmm0
0x1400b1c37  mov     [rbp+57h+var_28], 0
0x1400b1c3f  mov     [rbp+57h+var_30], 0
0x1400b1c47  cmp     qword ptr [rdx+10h], 0
0x1400b1c4c  jz      short loc_1400B1CB6
0x1400b1c4e  lea     rax, [rbp+57h+var_28]
0x1400b1c52  mov     [rbp+57h+var_60], rax
0x1400b1c56  mov     [rbp+57h+SecurityDescriptor], 0
0x1400b1c5e  mov     [rbp+57h+var_50], 1
0x1400b1c62  cmp     qword ptr [rdx+18h], 7
0x1400b1c67  jbe     short loc_1400B1C6E
0x1400b1c69  mov     rcx, [rdx]
0x1400b1c6c  jmp     short loc_1400B1C71
0x1400b1c6e  mov     rcx, rbx; StringSecurityDescriptor
0x1400b1c71  mov     rdi, [rbp+5Fh]
0x1400b1c75  xor     r9d, r9d; SecurityDescriptorSize
0x1400b1c78  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400b1c7c  lea     edx, [r9+1]; StringSDRevision
0x1400b1c80  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400b1c87  nop     dword ptr [rax+rax+00h]
0x1400b1c8c  test    eax, eax
0x1400b1c8e  jnz     short loc_1400B1CA5
0x1400b1c90  lea     r8, aOnecoreVmCommo_61; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400b1c97  mov     edx, 0A7h; void *
0x1400b1c9c  mov     rcx, rdi; this
0x1400b1c9f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1ca5  lea     rcx, [rbp+57h+var_60]
0x1400b1ca9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1400b1cae  mov     rax, [rbp+57h+var_28]
0x1400b1cb2  mov     qword ptr [rbp+57h+InBuffer], rax
0x1400b1cb6  cmp     qword ptr [rbx+30h], 0
0x1400b1cbb  jz      short loc_1400B1D24
0x1400b1cbd  lea     rax, [rbp+57h+var_30]
0x1400b1cc1  mov     [rbp+57h+var_60], rax
0x1400b1cc5  mov     [rbp+57h+SecurityDescriptor], 0
0x1400b1ccd  mov     [rbp+57h+var_50], 1
0x1400b1cd1  lea     rcx, [rbx+20h]
0x1400b1cd5  cmp     qword ptr [rcx+18h], 7
0x1400b1cda  jbe     short loc_1400B1CDF
0x1400b1cdc  mov     rcx, [rcx]; StringSecurityDescriptor
0x1400b1cdf  mov     rbx, [rbp+5Fh]
0x1400b1ce3  xor     r9d, r9d; SecurityDescriptorSize
0x1400b1ce6  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400b1cea  lea     edx, [r9+1]; StringSDRevision
0x1400b1cee  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400b1cf5  nop     dword ptr [rax+rax+00h]
0x1400b1cfa  test    eax, eax
0x1400b1cfc  jnz     short loc_1400B1D13
0x1400b1cfe  lea     r8, aOnecoreVmCommo_61; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400b1d05  mov     edx, 0B2h; void *
0x1400b1d0a  mov     rcx, rbx; this
0x1400b1d0d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1d13  lea     rcx, [rbp+57h+var_60]
0x1400b1d17  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1400b1d1c  mov     rax, [rbp+57h+var_30]
0x1400b1d20  mov     qword ptr [rbp+57h+InBuffer+8], rax
0x1400b1d24  mov     [rbp+57h+BytesReturned], 0
0x1400b1d2b  mov     rbx, [rbp+5Fh]
0x1400b1d2f  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x1400b1d38  lea     rax, [rbp+57h+BytesReturned]
0x1400b1d3c  mov     [rsp+0A0h+lpBytesReturned], rax; lpBytesReturned
0x1400b1d41  mov     [rsp+0A0h+nOutBufferSize], 0; nOutBufferSize
0x1400b1d49  mov     [rsp+0A0h+lpOutBuffer], 0; lpOutBuffer
0x1400b1d52  mov     r9d, 10h; nInBufferSize
0x1400b1d58  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1400b1d5c  mov     edx, 21C008h; dwIoControlCode
0x1400b1d61  mov     rcx, rsi; hDevice
0x1400b1d64  call    cs:__imp_DeviceIoControl
0x1400b1d6b  nop     dword ptr [rax+rax+00h]
0x1400b1d70  test    eax, eax
0x1400b1d72  jnz     short loc_1400B1D89
0x1400b1d74  lea     r8, aOnecoreVmCommo_61; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400b1d7b  mov     edx, 0C0h; void *
0x1400b1d80  mov     rcx, rbx; this
0x1400b1d83  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b1d89  lea     rcx, [rbp+57h+var_30]
0x1400b1d8d  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b1d92  nop
0x1400b1d93  lea     rcx, [rbp+57h+var_28]
0x1400b1d97  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b1d9c  mov     rcx, [rbp+57h+var_20]
0x1400b1da0  xor     rcx, rsp; StackCookie
0x1400b1da3  call    __security_check_cookie
0x1400b1da8  mov     rbx, [rsp+0A0h+arg_10]
0x1400b1db0  add     rsp, 90h
0x1400b1db7  pop     rdi
0x1400b1db8  pop     rsi
0x1400b1db9  pop     rbp
0x1400b1dba  retn
```
