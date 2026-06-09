# GuestServiceUtilities::UpdateHvSocketSystemProperties(void * const,Config::Devices::IC::HvSocketSystemWpConfig const &)

- ea: `0x1400ed844`
- end: `0x1400eda3e`
- name: `?UpdateHvSocketSystemProperties@GuestServiceUtilities@@YAXQEAXAEBUHvSocketSystemWpConfig@IC@Devices@Config@@@Z`
- size: `506`
- prototype: `void __fastcall(HANDLE hDevice, LPCWSTR StringSecurityDescriptor, const struct Config::Devices::IC::HvSocketSystemWpConfig *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140087720`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x1400ed844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed8f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed96c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed8f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ed96c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ed959`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed8e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed964`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed9c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed9d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed8e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed964`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed9c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400ed9d2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400ed9af`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400ed9af`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed8ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed935`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed8ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ed935`

## string_xrefs

- `0x1400ed9ff`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400eda14`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`
- `0x1400eda29`: `onecore\vm\common\vdev\guestservice\guestserviceutilities.cpp`

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
  PSECURITY_DESCRIPTOR v7; // r15
  HLOCAL v8; // r14
  DWORD LastError; // ebx
  LPCWSTR v10; // rcx
  const char *v11; // r9
  PSECURITY_DESCRIPTOR v12; // r14
  HLOCAL v13; // rsi
  DWORD v14; // ebx
  const char *v15; // r9
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-21h] BYREF
  char v17; // [rsp+50h] [rbp-19h]
  __int128 InBuffer; // [rsp+58h] [rbp-11h] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp-1h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+7h]
  HLOCAL v21; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  InBuffer = 0;
  v21 = 0;
  hMem = 0;
  if ( *((_QWORD *)StringSecurityDescriptor + 2) )
  {
    SecurityDescriptor = 0;
    v17 = 1;
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
    if ( v17 )
    {
      v7 = SecurityDescriptor;
      v8 = v21;
      if ( v21 )
      {
        LastError = GetLastError();
        LocalFree(v8);
        SetLastError(LastError);
      }
      v21 = v7;
    }
    *(_QWORD *)&InBuffer = v21;
  }
  if ( *((_QWORD *)StringSecurityDescriptor + 6) )
  {
    SecurityDescriptor = 0;
    v17 = 1;
    v10 = StringSecurityDescriptor + 16;
    if ( *((_QWORD *)StringSecurityDescriptor + 7) > 7u )
      v10 = *(LPCWSTR *)v10;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v10, 1u, &SecurityDescriptor, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
        v11);
    if ( v17 )
    {
      v12 = SecurityDescriptor;
      v13 = hMem;
      if ( hMem )
      {
        v14 = GetLastError();
        LocalFree(v13);
        SetLastError(v14);
      }
      hMem = v12;
    }
    *((_QWORD *)&InBuffer + 1) = hMem;
  }
  BytesReturned = 0;
  if ( !DeviceIoControl(hDevice, 0x21C008u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\vm\\common\\vdev\\guestservice\\guestserviceutilities.cpp",
      v15);
  if ( hMem )
    LocalFree(hMem);
  if ( v21 )
    LocalFree(v21);
}

```

## disassembly

```asm
0x1400ed844  mov     [rsp-8+arg_10], rbx
0x1400ed849  push    rbp
0x1400ed84a  push    rsi
0x1400ed84b  push    rdi
0x1400ed84c  push    r12
0x1400ed84e  push    r13
0x1400ed850  push    r14
0x1400ed852  push    r15
0x1400ed854  lea     rbp, [rsp-27h]
0x1400ed859  sub     rsp, 90h
0x1400ed860  mov     rax, cs:__security_cookie
0x1400ed867  xor     rax, rsp
0x1400ed86a  mov     [rbp+57h+var_40], rax
0x1400ed86e  mov     rdi, rdx
0x1400ed871  mov     r12, rcx
0x1400ed874  xorps   xmm0, xmm0
0x1400ed877  movups  [rbp+57h+InBuffer], xmm0
0x1400ed87b  xor     r13d, r13d
0x1400ed87e  mov     [rbp+57h+var_48], r13
0x1400ed882  mov     [rbp+57h+hMem], r13
0x1400ed886  cmp     [rdx+10h], r13
0x1400ed88a  jz      short loc_1400ED902
0x1400ed88c  lea     rax, [rbp+57h+var_48]
0x1400ed890  mov     [rbp+57h+var_80], rax
0x1400ed894  mov     [rbp+57h+SecurityDescriptor], r13
0x1400ed898  mov     [rbp+57h+var_70], 1
0x1400ed89c  cmp     qword ptr [rdx+18h], 7
0x1400ed8a1  jbe     short loc_1400ED8A8
0x1400ed8a3  mov     rcx, [rdx]
0x1400ed8a6  jmp     short loc_1400ED8AB
0x1400ed8a8  mov     rcx, rdi; StringSecurityDescriptor
0x1400ed8ab  mov     rbx, [rbp+5Fh]
0x1400ed8af  xor     r9d, r9d; SecurityDescriptorSize
0x1400ed8b2  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400ed8b6  lea     edx, [r9+1]; StringSDRevision
0x1400ed8ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400ed8c0  test    eax, eax
0x1400ed8c2  jz      loc_1400EDA14
0x1400ed8c8  cmp     [rbp+57h+var_70], r13b
0x1400ed8cc  jz      short loc_1400ED8FA
0x1400ed8ce  mov     r15, [rbp+57h+SecurityDescriptor]
0x1400ed8d2  mov     rsi, [rbp+57h+var_80]
0x1400ed8d6  mov     r14, [rsi]
0x1400ed8d9  test    r14, r14
0x1400ed8dc  jz      short loc_1400ED8F7
0x1400ed8de  call    cs:__imp_GetLastError
0x1400ed8e4  mov     ebx, eax
0x1400ed8e6  mov     rcx, r14; hMem
0x1400ed8e9  call    cs:__imp_LocalFree
0x1400ed8ef  mov     ecx, ebx; dwErrCode
0x1400ed8f1  call    cs:__imp_SetLastError
0x1400ed8f7  mov     [rsi], r15
0x1400ed8fa  mov     rax, [rbp+57h+var_48]
0x1400ed8fe  mov     qword ptr [rbp+57h+InBuffer], rax
0x1400ed902  cmp     [rdi+30h], r13
0x1400ed906  jz      short loc_1400ED97D
0x1400ed908  lea     rax, [rbp+57h+hMem]
0x1400ed90c  mov     [rbp+57h+var_80], rax
0x1400ed910  mov     [rbp+57h+SecurityDescriptor], r13
0x1400ed914  mov     [rbp+57h+var_70], 1
0x1400ed918  lea     rcx, [rdi+20h]
0x1400ed91c  cmp     qword ptr [rcx+18h], 7
0x1400ed921  jbe     short loc_1400ED926
0x1400ed923  mov     rcx, [rcx]; StringSecurityDescriptor
0x1400ed926  mov     rbx, [rbp+5Fh]
0x1400ed92a  xor     r9d, r9d; SecurityDescriptorSize
0x1400ed92d  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400ed931  lea     edx, [r9+1]; StringSDRevision
0x1400ed935  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400ed93b  test    eax, eax
0x1400ed93d  jz      loc_1400EDA29
0x1400ed943  cmp     [rbp+57h+var_70], r13b
0x1400ed947  jz      short loc_1400ED975
0x1400ed949  mov     r14, [rbp+57h+SecurityDescriptor]
0x1400ed94d  mov     rdi, [rbp+57h+var_80]
0x1400ed951  mov     rsi, [rdi]
0x1400ed954  test    rsi, rsi
0x1400ed957  jz      short loc_1400ED972
0x1400ed959  call    cs:__imp_GetLastError
0x1400ed95f  mov     ebx, eax
0x1400ed961  mov     rcx, rsi; hMem
0x1400ed964  call    cs:__imp_LocalFree
0x1400ed96a  mov     ecx, ebx; dwErrCode
0x1400ed96c  call    cs:__imp_SetLastError
0x1400ed972  mov     [rdi], r14
0x1400ed975  mov     rax, [rbp+57h+hMem]
0x1400ed979  mov     qword ptr [rbp+57h+InBuffer+8], rax
0x1400ed97d  mov     [rbp+57h+BytesReturned], r13d
0x1400ed981  mov     rbx, [rbp+5Fh]
0x1400ed985  mov     [rsp+0C0h+lpOverlapped], r13; lpOverlapped
0x1400ed98a  lea     rax, [rbp+57h+BytesReturned]
0x1400ed98e  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x1400ed993  mov     [rsp+0C0h+nOutBufferSize], r13d; nOutBufferSize
0x1400ed998  mov     [rsp+0C0h+lpOutBuffer], r13; lpOutBuffer
0x1400ed99d  mov     r9d, 10h; nInBufferSize
0x1400ed9a3  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1400ed9a7  mov     edx, 21C008h; dwIoControlCode
0x1400ed9ac  mov     rcx, r12; hDevice
0x1400ed9af  call    cs:__imp_DeviceIoControl
0x1400ed9b5  test    eax, eax
0x1400ed9b7  jz      short loc_1400ED9FF
0x1400ed9b9  mov     rcx, [rbp+57h+hMem]; hMem
0x1400ed9bd  test    rcx, rcx
0x1400ed9c0  jz      short loc_1400ED9C9
0x1400ed9c2  call    cs:__imp_LocalFree
0x1400ed9c8  nop
0x1400ed9c9  mov     rcx, [rbp+57h+var_48]; hMem
0x1400ed9cd  test    rcx, rcx
0x1400ed9d0  jz      short loc_1400ED9D8
0x1400ed9d2  call    cs:__imp_LocalFree
0x1400ed9d8  mov     rcx, [rbp+57h+var_40]
0x1400ed9dc  xor     rcx, rsp; StackCookie
0x1400ed9df  call    __security_check_cookie
0x1400ed9e4  mov     rbx, [rsp+0C0h+arg_10]
0x1400ed9ec  add     rsp, 90h
0x1400ed9f3  pop     r15
0x1400ed9f5  pop     r14
0x1400ed9f7  pop     r13
0x1400ed9f9  pop     r12
0x1400ed9fb  pop     rdi
0x1400ed9fc  pop     rsi
0x1400ed9fd  pop     rbp
0x1400ed9fe  retn
0x1400ed9ff  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400eda06  mov     edx, 0C0h; void *
0x1400eda0b  mov     rcx, rbx; this
0x1400eda0e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400eda14  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400eda1b  mov     edx, 0A7h; void *
0x1400eda20  mov     rcx, rbx; this
0x1400eda23  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400eda29  lea     r8, aOnecoreVmCommo_13; "onecore\\vm\\common\\vdev\\guestservice"...
0x1400eda30  mov     edx, 0B2h; void *
0x1400eda35  mov     rcx, rbx; this
0x1400eda38  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
