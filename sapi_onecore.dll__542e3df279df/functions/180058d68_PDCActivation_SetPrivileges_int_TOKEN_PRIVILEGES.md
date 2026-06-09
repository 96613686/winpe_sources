# PDCActivation::SetPrivileges(int,_TOKEN_PRIVILEGES *)

- ea: `0x180058d68`
- end: `0x180058f1c`
- name: `?SetPrivileges@PDCActivation@@AEAAJHPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `436`
- prototype: `int(PDCActivation *__hidden this, int, struct _TOKEN_PRIVILEGES *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058bc0`

## callees

- `0x180026508`
- `0x180058d68`
- `0x18005cd84`
- `0x180079e30`
- `0x1800c94dc`
- `0x1800c9534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ed0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058db8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058db8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180058dca`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180058dca`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180058ec6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180058ec6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180058e36`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180058e36`

## string_xrefs

- `0x180058e2f`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall PDCActivation::SetPrivileges(PDCActivation *this, int a2, struct _TOKEN_PRIVILEGES *a3)
{
  signed int v5; // ebx
  __int64 v6; // rdx
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  rsize_t v9; // rdx
  rsize_t v10; // r9
  signed int v11; // eax
  BOOL v12; // eax
  signed int LastError; // eax
  int PreviousState; // [rsp+20h] [rbp-40h]
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 391;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\pdcactivation.cpp",
      (const char *)(unsigned int)v5,
      PreviousState);
    goto LABEL_25;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v5 = -2147024890;
      v6 = 393;
      goto LABEL_8;
    }
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      if ( a2 )
      {
        Luid[0].LowPart = 1;
        Luid[1].HighPart = 2;
        ReturnLength = 0;
        *a3 = *(struct _TOKEN_PRIVILEGES *)&Luid[0].LowPart;
        v12 = AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, a3, &ReturnLength);
      }
      else
      {
        memcpy_s_0(Luid, v9, a3, v10);
        v12 = AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
      }
      if ( v12 )
      {
        v5 = 0;
        goto LABEL_25;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
      {
        v6 = 410;
        goto LABEL_8;
      }
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      if ( v5 < 0 )
      {
        v6 = 394;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = 392;
      goto LABEL_8;
    }
  }
LABEL_25:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180058d68  mov     [rsp-8+arg_0], rbx
0x180058d6d  mov     [rsp-8+arg_8], rdi
0x180058d72  push    rbp
0x180058d73  mov     rbp, rsp
0x180058d76  sub     rsp, 60h
0x180058d7a  mov     rax, cs:__security_cookie
0x180058d81  xor     rax, rsp
0x180058d84  mov     [rbp+var_10], rax
0x180058d88  mov     [rbp+TokenHandle], 0
0x180058d90  xorps   xmm0, xmm0
0x180058d93  mov     rbx, r8
0x180058d96  mov     edi, edx
0x180058d98  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x180058d9c  test    r8, r8
0x180058d9f  jnz     short loc_180058DAD
0x180058da1  mov     ebx, 80004003h
0x180058da6  mov     edx, 187h
0x180058dab  jmp     short loc_180058DF6
0x180058dad  xor     edx, edx
0x180058daf  lea     rcx, [rbp+TokenHandle]
0x180058db3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180058db8  call    cs:__imp_GetCurrentProcess
0x180058dbe  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180058dc2  mov     edx, 28h ; '('; DesiredAccess
0x180058dc7  mov     rcx, rax; ProcessHandle
0x180058dca  call    cs:__imp_OpenProcessToken
0x180058dd0  test    eax, eax
0x180058dd2  jnz     short loc_180058E0E
0x180058dd4  call    cs:__imp_GetLastError
0x180058dda  mov     ebx, eax
0x180058ddc  test    eax, eax
0x180058dde  jle     short loc_180058DE9
0x180058de0  movzx   ebx, ax
0x180058de3  or      ebx, 80070000h
0x180058de9  test    ebx, ebx
0x180058deb  jns     loc_180058EF5
0x180058df1  mov     edx, 188h; void *
0x180058df6  mov     rcx, [rbp+8]; this
0x180058dfa  lea     r8, aOnecoreuapEndu_63; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180058e01  mov     r9d, ebx; char *
0x180058e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e09  jmp     loc_180058EF5
0x180058e0e  mov     rax, [rbp+TokenHandle]
0x180058e12  inc     rax
0x180058e15  test    rax, 0FFFFFFFFFFFFFFFEh
0x180058e1b  jnz     short loc_180058E29
0x180058e1d  mov     ebx, 80070006h
0x180058e22  mov     edx, 189h
0x180058e27  jmp     short loc_180058DF6
0x180058e29  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x180058e2d  xor     ecx, ecx; lpSystemName
0x180058e2f  lea     rdx, Name; "SeShutdownPrivilege"
0x180058e36  call    cs:__imp_LookupPrivilegeValueW
0x180058e3c  test    eax, eax
0x180058e3e  jnz     short loc_180058E64
0x180058e40  call    cs:__imp_GetLastError
0x180058e46  mov     ebx, eax
0x180058e48  test    eax, eax
0x180058e4a  jle     short loc_180058E55
0x180058e4c  movzx   ebx, ax
0x180058e4f  or      ebx, 80070000h
0x180058e55  test    ebx, ebx
0x180058e57  jns     loc_180058EF5
0x180058e5d  mov     edx, 18Ah
0x180058e62  jmp     short loc_180058DF6
0x180058e64  test    edi, edi
0x180058e66  jz      short loc_180058E9B
0x180058e68  mov     [rbp+Luid.LowPart], 1
0x180058e6f  lea     rax, [rbp+var_28]
0x180058e73  mov     [rbp+Luid.HighPart+8], 2
0x180058e7a  mov     r9d, 10h
0x180058e80  movups  xmm0, xmmword ptr [rbp+Luid.LowPart]
0x180058e84  mov     [rsp+60h+ReturnLength], rax
0x180058e89  mov     [rbp+var_28], 0
0x180058e90  movdqu  xmmword ptr [rbx], xmm0
0x180058e94  mov     [rsp+60h+PreviousState], rbx
0x180058e99  jmp     short loc_180058EBC
0x180058e9b  mov     r8, rbx; Source
0x180058e9e  lea     rcx, [rbp+Luid]; Destination
0x180058ea2  call    memcpy_s_0
0x180058ea7  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x180058eb0  xor     r9d, r9d; BufferLength
0x180058eb3  mov     [rsp+60h+PreviousState], 0; PreviousState
0x180058ebc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180058ec0  lea     r8, [rbp+Luid]; NewState
0x180058ec4  xor     edx, edx; DisableAllPrivileges
0x180058ec6  call    cs:__imp_AdjustTokenPrivileges
0x180058ecc  test    eax, eax
0x180058ece  jnz     short loc_180058EF3
0x180058ed0  call    cs:__imp_GetLastError
0x180058ed6  mov     ebx, eax
0x180058ed8  test    eax, eax
0x180058eda  jle     short loc_180058EE5
0x180058edc  movzx   ebx, ax
0x180058edf  or      ebx, 80070000h
0x180058ee5  test    ebx, ebx
0x180058ee7  jns     short loc_180058EF5
0x180058ee9  mov     edx, 19Ah
0x180058eee  jmp     loc_180058DF6
0x180058ef3  xor     ebx, ebx
0x180058ef5  lea     rcx, [rbp+TokenHandle]
0x180058ef9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180058efe  mov     eax, ebx
0x180058f00  mov     rcx, [rbp+var_10]
0x180058f04  xor     rcx, rsp; StackCookie
0x180058f07  call    __security_check_cookie
0x180058f0c  mov     rbx, [rsp+60h+arg_0]
0x180058f11  mov     rdi, [rsp+60h+arg_8]
0x180058f16  add     rsp, 60h
0x180058f1a  pop     rbp
0x180058f1b  retn
```
