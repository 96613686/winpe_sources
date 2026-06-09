# CHardwareManager::RegisterPowerNotifications(void)

- ea: `0x180036b00`
- end: `0x180036d43`
- name: `?RegisterPowerNotifications@CHardwareManager@@QEAAJXZ`
- size: `579`
- prototype: `__int64 __fastcall(CHardwareManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800447b0`

## callees

- `0x1800119c4`
- `0x180011d90`
- `0x180036b00`
- `0x18005388c`
- `0x1800538b0`
- `0x1800549a0`
- `0x180056358`
- `0x180068f60`
- `0x180069cc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036b29`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036b3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036b6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036b6e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180036b8f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180036b8f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180036bc9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180036bc9`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180036cf6`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180036cf6`
- `UMPDC!PdcSignalClientRegister` at `0x180036cad`
- `UMPDC!PdcSignalClientRegister` at `0x180036cad`

## string_xrefs

- `0x180036b49`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180036bd7`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180036c8e`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180036cbe`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180036d07`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180036b86`: `SeShutdownPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHardwareManager::RegisterPowerNotifications(CHardwareManager *this)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rax
  const wchar_t *v10; // rcx
  __int64 v11; // rdx
  wchar_t *v12; // r8
  wchar_t v13; // r9
  wchar_t *v14; // rcx
  int v15; // eax
  struct CHardwareManager *v16; // rax
  DWORD v17; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+58h] [rbp-A8h]
  __int128 v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[132]; // [rsp+7Ch] [rbp-84h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v4 = 1136;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
                  v3);
    goto LABEL_4;
  }
  *(_OWORD *)&Luid[0].LowPart = 0;
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
  {
    v4 = 1139;
    goto LABEL_3;
  }
  Luid[0].LowPart = 1;
  Luid[1].HighPart = 2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x476,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
           v7);
LABEL_20:
    v6 = v8;
    goto LABEL_24;
  }
  memset_0(v26, 0, 0x80u);
  v22[0] = 1;
  v24 = PDC_SIGNAL_PROVIDER_WINBIO;
  v22[1] = 1;
  v23 = PDC_SIGNAL_CLASS_WAKE;
  v25 = 0;
  v9 = 2147483646;
  v10 = L"Windows Biometric Framework Fingerprint Wake";
  v11 = 64;
  v12 = (wchar_t *)v26;
  do
  {
    if ( !v9 )
      break;
    v13 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v12++ = v13;
    --v9;
    --v11;
  }
  while ( v11 );
  v6 = v11 == 0 ? 0x8007007A : 0;
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x482,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)v6,
      PreviousState);
LABEL_24:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v6;
  }
  v15 = PdcSignalClientRegister(v22, (char *)this + 168);
  if ( v15 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x484,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
           (const char *)(unsigned int)v15,
           PreviousState);
    goto LABEL_20;
  }
  *((_BYTE *)this + 184) = 0;
  v16 = CHardwareManager::Instance();
  v17 = PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 1u, *((HANDLE *)v16 + 8), (PHPOWERNOTIFY)this + 22);
  if ( !v17 )
  {
    v6 = 0;
    goto LABEL_24;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x48D,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
                (const char *)v17,
                PreviousState);
LABEL_4:
  v6 = LastError;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x180036b00  push    rbp
0x180036b02  push    rbx
0x180036b03  push    rsi
0x180036b04  push    rdi
0x180036b05  lea     rbp, [rsp-18h]
0x180036b0a  sub     rsp, 118h
0x180036b11  mov     rax, cs:__security_cookie
0x180036b18  xor     rax, rsp
0x180036b1b  mov     [rbp+30h+var_30], rax
0x180036b1f  mov     rdi, rcx
0x180036b22  xor     esi, esi
0x180036b24  mov     [rsp+130h+TokenHandle], rsi
0x180036b29  call    cs:__imp_GetCurrentProcess
0x180036b2f  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x180036b34  lea     edx, [rsi+28h]; DesiredAccess
0x180036b37  mov     rcx, rax; ProcessHandle
0x180036b3a  call    cs:__imp_OpenProcessToken
0x180036b40  test    eax, eax
0x180036b42  jnz     short loc_180036B79
0x180036b44  mov     edx, 470h; void *
0x180036b49  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180036b50  mov     rcx, [rbp+38h]; this
0x180036b54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036b59  mov     ebx, eax
0x180036b5b  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x180036b60  lea     rdx, [rcx-1]
0x180036b64  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180036b68  ja      loc_180036D29
0x180036b6e  call    cs:__imp_CloseHandle
0x180036b74  jmp     loc_180036D29
0x180036b79  xorps   xmm0, xmm0
0x180036b7c  movups  xmmword ptr [rsp+130h+Luid.LowPart], xmm0
0x180036b81  lea     r8, [rsp+130h+Luid.HighPart]; lpLuid
0x180036b86  lea     rdx, Name; "SeShutdownPrivilege"
0x180036b8d  xor     ecx, ecx; lpSystemName
0x180036b8f  call    cs:__imp_LookupPrivilegeValueW
0x180036b95  test    eax, eax
0x180036b97  jnz     short loc_180036BA0
0x180036b99  mov     edx, 473h
0x180036b9e  jmp     short loc_180036B49
0x180036ba0  mov     [rsp+130h+Luid.LowPart], 1
0x180036ba8  mov     [rsp+130h+Luid.HighPart+8], 2
0x180036bb0  mov     [rsp+130h+ReturnLength], rsi; ReturnLength
0x180036bb5  mov     [rsp+130h+PreviousState], rsi; unsigned int
0x180036bba  xor     r9d, r9d; BufferLength
0x180036bbd  lea     r8, [rsp+130h+Luid]; NewState
0x180036bc2  xor     edx, edx; DisableAllPrivileges
0x180036bc4  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180036bc9  call    cs:__imp_AdjustTokenPrivileges
0x180036bcf  test    eax, eax
0x180036bd1  jnz     short loc_180036BED
0x180036bd3  mov     rcx, [rbp+38h]; this
0x180036bd7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180036bde  mov     edx, 476h; void *
0x180036be3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036be8  jmp     loc_180036CCF
0x180036bed  xor     edx, edx; Val
0x180036bef  mov     r8d, 80h; Size
0x180036bf5  lea     rcx, [rsp+130h+var_B4]; void *
0x180036bfa  call    memset_0
0x180036bff  mov     [rsp+130h+var_E0], 1
0x180036c07  movups  xmm0, cs:PDC_SIGNAL_PROVIDER_WINBIO
0x180036c0e  movdqu  [rsp+130h+var_C8], xmm0
0x180036c14  mov     [rsp+130h+var_DC], 1
0x180036c1c  movups  xmm1, cs:PDC_SIGNAL_CLASS_WAKE
0x180036c23  movdqu  [rsp+130h+var_D8], xmm1
0x180036c29  mov     [rsp+130h+var_B8], esi
0x180036c2d  mov     eax, 7FFFFFFEh
0x180036c32  lea     rcx, aWindowsBiometr; "Windows Biometric Framework Fingerprint"...
0x180036c39  mov     edx, 40h ; '@'
0x180036c3e  lea     r8, [rsp+130h+var_B4]
0x180036c43  test    rax, rax
0x180036c46  jz      short loc_180036C67
0x180036c48  movzx   r9d, word ptr [rcx]
0x180036c4c  test    r9w, r9w
0x180036c50  jz      short loc_180036C67
0x180036c52  add     rcx, 2
0x180036c56  mov     [r8], r9w
0x180036c5a  add     r8, 2
0x180036c5e  dec     rax
0x180036c61  sub     rdx, 1
0x180036c65  jnz     short loc_180036C43
0x180036c67  mov     rax, rdx
0x180036c6a  neg     rax
0x180036c6d  sbb     ebx, ebx
0x180036c6f  not     ebx
0x180036c71  and     ebx, 8007007Ah
0x180036c77  lea     rcx, [r8-2]
0x180036c7b  test    rdx, rdx
0x180036c7e  cmovnz  rcx, r8
0x180036c82  mov     [rcx], si
0x180036c85  jnz     short loc_180036CA1
0x180036c87  mov     rcx, [rbp+38h]; this
0x180036c8b  mov     r9d, ebx; char *
0x180036c8e  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180036c95  mov     edx, 482h; void *
0x180036c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c9f  jmp     short loc_180036D1F
0x180036ca1  lea     rdx, [rdi+0A8h]
0x180036ca8  lea     rcx, [rsp+130h+var_E0]
0x180036cad  call    cs:__imp_PdcSignalClientRegister
0x180036cb3  test    eax, eax
0x180036cb5  jns     short loc_180036CD3
0x180036cb7  mov     rcx, [rbp+38h]; this
0x180036cbb  mov     r9d, eax; char *
0x180036cbe  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180036cc5  mov     edx, 484h; void *
0x180036cca  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036ccf  mov     ebx, eax
0x180036cd1  jmp     short loc_180036D1F
0x180036cd3  mov     [rdi+0B8h], sil
0x180036cda  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180036cdf  lea     r9, [rdi+0B0h]; RegistrationHandle
0x180036ce6  mov     r8, [rax+40h]; Recipient
0x180036cea  mov     edx, 1; Flags
0x180036cef  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x180036cf6  call    cs:__imp_PowerSettingRegisterNotification
0x180036cfc  test    eax, eax
0x180036cfe  jz      short loc_180036D1D
0x180036d00  mov     rcx, [rbp+38h]; this
0x180036d04  mov     r9d, eax; char *
0x180036d07  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180036d0e  mov     edx, 48Dh; void *
0x180036d13  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036d18  jmp     loc_180036B59
0x180036d1d  mov     ebx, esi
0x180036d1f  lea     rcx, [rsp+130h+TokenHandle]
0x180036d24  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180036d29  mov     eax, ebx
0x180036d2b  mov     rcx, [rbp+30h+var_30]
0x180036d2f  xor     rcx, rsp; StackCookie
0x180036d32  call    __security_check_cookie
0x180036d37  add     rsp, 118h
0x180036d3e  pop     rdi
0x180036d3f  pop     rsi
0x180036d40  pop     rbx
0x180036d41  pop     rbp
0x180036d42  retn
```
