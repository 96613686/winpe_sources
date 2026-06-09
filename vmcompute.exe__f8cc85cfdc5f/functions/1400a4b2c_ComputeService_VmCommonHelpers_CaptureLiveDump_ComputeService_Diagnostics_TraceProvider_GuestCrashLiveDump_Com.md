# ComputeService::VmCommonHelpers::CaptureLiveDump(ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump &,ComputeService::VmCommonHelpers::GuestCrashLiveDump const &,void *,bool *)

- ea: `0x1400a4b2c`
- end: `0x1400a4d94`
- name: `?CaptureLiveDump@VmCommonHelpers@ComputeService@@YAJAEAVGuestCrashLiveDump@TraceProvider@Diagnostics@2@AEBU312@PEAXPEA_N@Z`
- size: `616`
- prototype: `__int64 __fastcall(ComputeService::VmCommonHelpers *__hidden this, struct ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump *, const struct ComputeService::VmCommonHelpers::GuestCrashLiveDump *, void *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1401f0380`

## callees

- `0x140024030`
- `0x140024f6c`
- `0x140080180`
- `0x1400a4b2c`
- `0x1400a6578`
- `0x1400a65a0`
- `0x1400b1dd0`
- `0x1400b2108`
- `0x1400efa40`
- `0x1401332f0`
- `0x140134048`
- `0x1401effc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400a4cbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400a4cbc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400a4b84`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400a4b84`
- `ntdll!NtSystemDebugControl` at `0x1400a4c8c`
- `ntdll!NtSystemDebugControl` at `0x1400a4c8c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400a4d1d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400a4d1d`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1400a4c18`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1400a4c18`

## string_xrefs

- `0x1400a4b98`: `onecore\vm\compute\management\orchestration\shared\vmcommon\diagnostics.cpp`
- `0x1400a4cd8`: `onecore\vm\compute\management\orchestration\shared\vmcommon\diagnostics.cpp`
- `0x1400a4cf4`: `onecore\vm\compute\management\orchestration\shared\vmcommon\diagnostics.cpp`
- `0x1400a4d50`: `onecore\vm\compute\management\orchestration\shared\vmcommon\diagnostics.cpp`

## pseudocode

```c
__int64 __fastcall ComputeService::VmCommonHelpers::CaptureLiveDump(
        ComputeService::VmCommonHelpers *this,
        struct ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump *a2,
        const struct ComputeService::VmCommonHelpers::GuestCrashLiveDump *a3,
        bool *a4)
{
  const char *v8; // r9
  struct ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump *v9; // rcx
  __int64 File2; // rax
  const char *v11; // r9
  HANDLE v12; // rdi
  NTSTATUS v13; // eax
  unsigned int LastError; // ebx
  int OutputBufferLength; // [rsp+20h] [rbp-99h]
  _QWORD v17[3]; // [rsp+30h] [rbp-89h] BYREF
  int v18; // [rsp+48h] [rbp-71h]
  __int64 v19; // [rsp+4Ch] [rbp-6Dh]
  int v20; // [rsp+54h] [rbp-65h]
  _QWORD *v21; // [rsp+58h] [rbp-61h]
  __int64 v22; // [rsp+60h] [rbp-59h]
  _DWORD InputBuffer[10]; // [rsp+70h] [rbp-49h] BYREF
  HANDLE v24; // [rsp+98h] [rbp-21h]
  const struct ComputeService::VmCommonHelpers::GuestCrashLiveDump *v25; // [rsp+A0h] [rbp-19h]
  int v26; // [rsp+A8h] [rbp-11h]
  int v27; // [rsp+ACh] [rbp-Dh]
  char FileInformation[8]; // [rsp+C0h] [rbp+7h] BYREF
  HANDLE hFile; // [rsp+C8h] [rbp+Fh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a4 = 0;
  SecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &SecurityDescriptor,
    0);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYD:P(A;;FA;;;SY)(A;;FA;;;BA)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\diagnostics.cpp",
      v8);
  v17[0] = 24;
  v17[2] = 0;
  v17[1] = SecurityDescriptor;
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v18 = 32;
  v21 = v17;
  hFile = (HANDLE)-1LL;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v9 = a2;
  else
    v9 = *(struct ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump **)a2;
  File2 = CreateFile2(v9, 2032127, 5);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    File2);
  v12 = hFile;
  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3F,
                  (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\diagnostics.cpp",
                  v11);
LABEL_18:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&SecurityDescriptor);
    return LastError;
  }
  else
  {
    memset_0(InputBuffer, 0, 0x48u);
    InputBuffer[0] = 2;
    v24 = v12;
    v25 = a3;
    v26 = *((_DWORD *)a2 + 8);
    v27 = *((_DWORD *)a2 + 9);
    while ( 1 )
    {
      while ( 1 )
      {
        v13 = NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgQueryTraceInformation, InputBuffer, 0x48u, 0, 0, 0);
        if ( v13 != -1073740972 )
          break;
        v26 &= ~4u;
      }
      if ( v13 != -1073741267 )
        break;
      ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump::GuestCrashLiveDump_Retry(this);
      if ( !WaitForSingleObject(a3, 0x3E8u) )
      {
        LastError = -2147023673;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\diagnostics.cpp",
          (const char *)0x800704C7LL,
          OutputBufferLength);
LABEL_15:
        FileInformation[0] = 1;
        SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u);
        goto LABEL_18;
      }
    }
    if ( v13 < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x6A,
                    (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\diagnostics.cpp",
                    (const char *)(unsigned int)v13,
                    OutputBufferLength);
      goto LABEL_15;
    }
    *a4 = (v26 & 4) != 0;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&SecurityDescriptor);
    return 0;
  }
}

```

## disassembly

```asm
0x1400a4b2c  push    rbp
0x1400a4b2e  push    rbx
0x1400a4b2f  push    rsi
0x1400a4b30  push    rdi
0x1400a4b31  push    r14
0x1400a4b33  push    r15
0x1400a4b35  lea     rbp, [rsp-2Fh]
0x1400a4b3a  sub     rsp, 0E8h
0x1400a4b41  mov     rax, cs:__security_cookie
0x1400a4b48  xor     rax, rsp
0x1400a4b4b  mov     [rbp+57h+var_38], rax
0x1400a4b4f  mov     r14, r9
0x1400a4b52  mov     rsi, r8
0x1400a4b55  mov     rbx, rdx
0x1400a4b58  mov     r15, rcx
0x1400a4b5b  mov     byte ptr [r9], 0
0x1400a4b5f  mov     [rbp+57h+SecurityDescriptor], 0
0x1400a4b67  xor     edx, edx
0x1400a4b69  lea     rcx, [rbp+57h+SecurityDescriptor]
0x1400a4b6d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1400a4b72  xor     r9d, r9d; SecurityDescriptorSize
0x1400a4b75  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400a4b79  lea     edx, [r9+1]; StringSDRevision
0x1400a4b7d  lea     rcx, aOSydPAFaSyAFaB; "O:SYD:P(A;;FA;;;SY)(A;;FA;;;BA)"
0x1400a4b84  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400a4b8b  nop     dword ptr [rax+rax+00h]
0x1400a4b90  test    eax, eax
0x1400a4b92  jnz     short loc_1400A4BA8
0x1400a4b94  mov     rcx, [rbp+5Fh]; this
0x1400a4b98  lea     r8, aOnecoreVmCompu_69; "onecore\\vm\\compute\\management\\orche"...
0x1400a4b9f  lea     edx, [rax+33h]; void *
0x1400a4ba2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a4ba8  mov     [rsp+110h+var_E0], 18h
0x1400a4bb1  mov     [rbp+57h+var_D0], 0
0x1400a4bb9  mov     rax, [rbp+57h+SecurityDescriptor]
0x1400a4bbd  mov     [rsp+110h+var_D8], rax
0x1400a4bc2  mov     [rbp+57h+var_C4], 0
0x1400a4bca  mov     [rbp+57h+var_BC], 0
0x1400a4bd1  mov     [rbp+57h+var_B0], 0
0x1400a4bd9  mov     [rbp+57h+var_C8], 20h ; ' '
0x1400a4be0  lea     rax, [rsp+110h+var_E0]
0x1400a4be5  mov     [rbp+57h+var_B8], rax
0x1400a4be9  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1400a4bf1  cmp     qword ptr [rbx+18h], 7
0x1400a4bf6  jbe     short loc_1400A4BFD
0x1400a4bf8  mov     rcx, [rbx]
0x1400a4bfb  jmp     short loc_1400A4C00
0x1400a4bfd  mov     rcx, rbx
0x1400a4c00  lea     rax, [rbp+57h+var_C8]
0x1400a4c04  mov     qword ptr [rsp+110h+OutputBufferLength], rax
0x1400a4c09  mov     edx, 1F01FFh
0x1400a4c0e  mov     r9d, 1
0x1400a4c14  lea     r8d, [r9+4]
0x1400a4c18  call    cs:__imp_CreateFile2
0x1400a4c1f  nop     dword ptr [rax+rax+00h]
0x1400a4c24  mov     rdx, rax
0x1400a4c27  lea     rcx, [rbp+57h+hFile]
0x1400a4c2b  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400a4c30  mov     rdi, [rbp+57h+hFile]
0x1400a4c34  lea     rax, [rdi-1]
0x1400a4c38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400a4c3c  ja      loc_1400A4D4C
0x1400a4c42  xor     edx, edx; Val
0x1400a4c44  lea     r8d, [rdx+48h]; Size
0x1400a4c48  lea     rcx, [rbp+57h+InputBuffer]; void *
0x1400a4c4c  call    memset_0
0x1400a4c51  mov     [rbp+57h+InputBuffer], 2
0x1400a4c58  mov     [rbp+57h+var_78], rdi
0x1400a4c5c  mov     [rbp+57h+var_70], rsi
0x1400a4c60  mov     eax, [rbx+20h]
0x1400a4c63  mov     [rbp+57h+var_68], eax
0x1400a4c66  mov     eax, [rbx+24h]
0x1400a4c69  mov     [rbp+57h+var_64], eax
0x1400a4c6c  mov     [rsp+110h+ReturnLength], 0; ReturnLength
0x1400a4c75  mov     [rsp+110h+OutputBufferLength], 0; int
0x1400a4c7d  xor     r9d, r9d; OutputBuffer
0x1400a4c80  lea     r8d, [r9+48h]; InputBufferLength
0x1400a4c84  lea     rdx, [rbp+57h+InputBuffer]; InputBuffer
0x1400a4c88  lea     ecx, [r9+25h]; ControlCode
0x1400a4c8c  call    cs:__imp_NtSystemDebugControl
0x1400a4c93  nop     dword ptr [rax+rax+00h]
0x1400a4c98  cmp     eax, 0C0000354h
0x1400a4c9d  jnz     short loc_1400A4CA5
0x1400a4c9f  and     [rbp+57h+var_68], 0FFFFFFFBh
0x1400a4ca3  jmp     short loc_1400A4C6C
0x1400a4ca5  cmp     eax, 0C000022Dh
0x1400a4caa  jnz     short loc_1400A4CE9
0x1400a4cac  mov     rcx, r15; this
0x1400a4caf  call    ?GuestCrashLiveDump_Retry@GuestCrashLiveDump@TraceProvider@Diagnostics@ComputeService@@QEAAXXZ; ComputeService::Diagnostics::TraceProvider::GuestCrashLiveDump::GuestCrashLiveDump_Retry(void)
0x1400a4cb4  mov     edx, 3E8h; dwMilliseconds
0x1400a4cb9  mov     rcx, rsi; hHandle
0x1400a4cbc  call    cs:__imp_WaitForSingleObject
0x1400a4cc3  nop     dword ptr [rax+rax+00h]
0x1400a4cc8  test    eax, eax
0x1400a4cca  jnz     short loc_1400A4C6C
0x1400a4ccc  mov     rcx, [rbp+5Fh]; this
0x1400a4cd0  mov     ebx, 800704C7h
0x1400a4cd5  mov     r9d, ebx; char *
0x1400a4cd8  lea     r8, aOnecoreVmCompu_69; "onecore\\vm\\compute\\management\\orche"...
0x1400a4cdf  lea     edx, [rax+66h]; void *
0x1400a4ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400a4ce7  jmp     short loc_1400A4D07
0x1400a4ce9  test    eax, eax
0x1400a4ceb  jns     short loc_1400A4D2B
0x1400a4ced  mov     rcx, [rbp+5Fh]; this
0x1400a4cf1  mov     r9d, eax; char *
0x1400a4cf4  lea     r8, aOnecoreVmCompu_69; "onecore\\vm\\compute\\management\\orche"...
0x1400a4cfb  mov     edx, 6Ah ; 'j'; void *
0x1400a4d00  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400a4d05  mov     ebx, eax
0x1400a4d07  mov     [rbp+57h+FileInformation], 1
0x1400a4d0b  mov     r9d, 1; dwBufferSize
0x1400a4d11  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1400a4d15  lea     edx, [r9+3]; FileInformationClass
0x1400a4d19  mov     rcx, [rbp+57h+hFile]; hFile
0x1400a4d1d  call    cs:__imp_SetFileInformationByHandle
0x1400a4d24  nop     dword ptr [rax+rax+00h]
0x1400a4d29  jmp     short loc_1400A4D63
0x1400a4d2b  mov     eax, [rbp+57h+var_68]
0x1400a4d2e  shr     eax, 2
0x1400a4d31  and     al, 1
0x1400a4d33  mov     [r14], al
0x1400a4d36  lea     rcx, [rbp+57h+hFile]; void *
0x1400a4d3a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400a4d3f  lea     rcx, [rbp+57h+SecurityDescriptor]
0x1400a4d43  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400a4d48  xor     eax, eax
0x1400a4d4a  jmp     short loc_1400A4D77
0x1400a4d4c  mov     rcx, [rbp+5Fh]; this
0x1400a4d50  lea     r8, aOnecoreVmCompu_69; "onecore\\vm\\compute\\management\\orche"...
0x1400a4d57  mov     edx, 3Fh ; '?'; void *
0x1400a4d5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400a4d61  mov     ebx, eax
0x1400a4d63  lea     rcx, [rbp+57h+hFile]; void *
0x1400a4d67  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400a4d6c  lea     rcx, [rbp+57h+SecurityDescriptor]
0x1400a4d70  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400a4d75  mov     eax, ebx
0x1400a4d77  mov     rcx, [rbp+57h+var_38]
0x1400a4d7b  xor     rcx, rsp; StackCookie
0x1400a4d7e  call    __security_check_cookie
0x1400a4d83  add     rsp, 0E8h
0x1400a4d8a  pop     r15
0x1400a4d8c  pop     r14
0x1400a4d8e  pop     rdi
0x1400a4d8f  pop     rsi
0x1400a4d90  pop     rbx
0x1400a4d91  pop     rbp
0x1400a4d92  retn
```
