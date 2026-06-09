# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x180021c00`
- end: `0x180021e27`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `551`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021c00`
- `0x180022520`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021c96`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021cdf`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021c96`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180021cdf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021d62`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021d83`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021d62`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d96`
- `iisutil!PuDbgPrint` at `0x180021d27`
- `iisutil!PuDbgPrint` at `0x180021dc7`
- `iisutil!PuDbgPrint` at `0x180021d27`
- `iisutil!PuDbgPrint` at `0x180021dc7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180021ddd`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180021ddd`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180021cb6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180021cb6`
- `iisutil!DisableTokenBackupPrivilege` at `0x180021e02`
- `iisutil!DisableTokenBackupPrivilege` at `0x180021e02`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180021de6`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180021de6`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180021c43`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180021c43`

## string_xrefs

- `0x180021d0e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180021dae`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180021d15`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x180021d03`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180021da3`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180021db5`: `DuplicateTokenEx failed, GetLastError = %lx\n`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetImpersonationToken(TOKEN_ENTRY *this)
{
  void **phNewToken; // rdi
  CSmallSpinLock *v3; // r15
  void *v4; // rcx
  _QWORD *v5; // r14
  DWORD LastError; // eax
  void *v7; // rcx
  DWORD v8; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-39h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+38h] [rbp-31h] BYREF
  _QWORD pSecurityDescriptor[4]; // [rsp+50h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR v13; // [rsp+70h] [rbp+7h]
  int v14; // [rsp+78h] [rbp+Fh]
  __int16 v15; // [rsp+7Ch] [rbp+13h]

  phNewToken = (void **)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    v3 = (TOKEN_ENTRY *)((char *)this + 248);
    CSmallSpinLock::WriteLock((TOKEN_ENTRY *)((char *)this + 248));
    if ( *phNewToken )
      goto LABEL_17;
    v4 = (void *)*((_QWORD *)this + 3);
    pSecurityDescriptor[0] = 0;
    v13 = pSecurityDescriptor;
    v14 = 32;
    v15 = 256;
    nLengthNeeded = 32;
    memset(&TokenAttributes, 0, sizeof(TokenAttributes));
    if ( GetKernelObjectSecurity(v4, 4u, pSecurityDescriptor, 0x20u, &nLengthNeeded) )
    {
      v5 = pSecurityDescriptor;
    }
    else
    {
      if ( GetLastError() != 122 )
        goto LABEL_7;
      if ( !BUFFER::Resize((BUFFER *)pSecurityDescriptor, nLengthNeeded) )
      {
LABEL_16:
        BUFFER::~BUFFER((BUFFER *)pSecurityDescriptor);
LABEL_17:
        CSmallSpinLock::WriteUnlock(v3);
        if ( !*phNewToken )
          return *phNewToken;
        goto LABEL_18;
      }
      v5 = v13;
      if ( !GetKernelObjectSecurity(*((HANDLE *)this + 3), 4u, v13, nLengthNeeded, &nLengthNeeded) )
      {
LABEL_7:
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LastError = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
            1095,
            "TOKEN_ENTRY::GetImpersonationToken",
            "Failed to get primary token security descriptor, GetLastError = %lx\n",
            LastError);
        }
        goto LABEL_16;
      }
    }
    v7 = (void *)*((_QWORD *)this + 3);
    TokenAttributes.lpSecurityDescriptor = v5;
    TokenAttributes.nLength = 24;
    TokenAttributes.bInheritHandle = 1;
    if ( !DuplicateTokenEx(v7, 0, &TokenAttributes, SecurityDelegation, TokenImpersonation, phNewToken)
      && !DuplicateTokenEx(
            *((HANDLE *)this + 3),
            0,
            &TokenAttributes,
            SecurityImpersonation,
            TokenImpersonation,
            phNewToken)
      && (g_dwDebugFlags & 3) != 0 )
    {
      v8 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
        1124,
        "TOKEN_ENTRY::GetImpersonationToken",
        "DuplicateTokenEx failed, GetLastError = %lx\n",
        v8);
    }
    if ( *phNewToken )
      *((_DWORD *)this + 65) |= 1u;
    goto LABEL_16;
  }
LABEL_18:
  if ( !*((_DWORD *)this + 29) && !_InterlockedExchange((volatile __int32 *)this + 29, 1) )
    DisableTokenBackupPrivilege(*phNewToken);
  return *phNewToken;
}

```

## disassembly

```asm
0x180021c00  push    rbp
0x180021c02  push    rbx
0x180021c03  push    rsi
0x180021c04  push    rdi
0x180021c05  push    r14
0x180021c07  push    r15
0x180021c09  lea     rbp, [rsp-2Fh]
0x180021c0e  sub     rsp, 98h
0x180021c15  mov     rax, cs:__security_cookie
0x180021c1c  xor     rax, rsp
0x180021c1f  mov     [rbp+57h+var_40], rax
0x180021c23  lea     rdi, [rcx+10h]
0x180021c27  mov     rbx, rcx
0x180021c2a  cmp     qword ptr [rdi], 0
0x180021c2e  mov     esi, 1
0x180021c33  jnz     loc_180021DF2
0x180021c39  lea     r15, [rcx+0F8h]
0x180021c40  mov     rcx, r15
0x180021c43  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180021c49  cmp     qword ptr [rdi], 0
0x180021c4d  jnz     loc_180021DE3
0x180021c53  mov     rcx, [rbx+18h]; Handle
0x180021c57  lea     r9d, [rsi+1Fh]; nLength
0x180021c5b  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180021c5f  mov     [rbp+57h+pSecurityDescriptor], 0
0x180021c67  mov     [rbp+57h+var_50], rax
0x180021c6b  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180021c6f  xor     eax, eax
0x180021c71  mov     [rbp+57h+var_48], r9d
0x180021c75  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rax
0x180021c79  lea     edx, [rsi+3]; RequestedInformation
0x180021c7c  lea     rax, [rbp+57h+nLengthNeeded]
0x180021c80  mov     [rbp+57h+var_44], 100h
0x180021c86  xorps   xmm0, xmm0
0x180021c89  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180021c8e  mov     [rbp+57h+nLengthNeeded], r9d
0x180021c92  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x180021c96  call    cs:__imp_GetKernelObjectSecurity
0x180021c9c  test    eax, eax
0x180021c9e  jnz     loc_180021D32
0x180021ca4  call    cs:__imp_GetLastError
0x180021caa  cmp     eax, 7Ah ; 'z'
0x180021cad  jnz     short loc_180021CE9
0x180021caf  mov     edx, [rbp+57h+nLengthNeeded]
0x180021cb2  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180021cb6  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180021cbc  test    al, al
0x180021cbe  jz      loc_180021DD9
0x180021cc4  mov     r14, [rbp+57h+var_50]
0x180021cc8  lea     rax, [rbp+57h+nLengthNeeded]
0x180021ccc  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180021cd0  lea     edx, [rsi+3]; RequestedInformation
0x180021cd3  mov     rcx, [rbx+18h]; Handle
0x180021cd7  mov     r8, r14; pSecurityDescriptor
0x180021cda  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180021cdf  call    cs:__imp_GetKernelObjectSecurity
0x180021ce5  test    eax, eax
0x180021ce7  jnz     short loc_180021D36
0x180021ce9  test    byte ptr cs:g_dwDebugFlags, 3
0x180021cf0  jz      loc_180021DD9
0x180021cf6  call    cs:__imp_GetLastError
0x180021cfc  mov     rcx, cs:g_pDebug
0x180021d03  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180021d0a  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x180021d0e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021d15  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x180021d1c  mov     r8d, 447h
0x180021d22  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180021d27  call    cs:__imp_PuDbgPrint
0x180021d2d  jmp     loc_180021DD9
0x180021d32  lea     r14, [rbp+57h+pSecurityDescriptor]
0x180021d36  mov     rcx, [rbx+18h]; hExistingToken
0x180021d3a  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180021d3e  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r14
0x180021d42  xor     edx, edx; dwDesiredAccess
0x180021d44  mov     r14d, 2
0x180021d4a  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180021d4f  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x180021d56  mov     [rbp+57h+TokenAttributes.bInheritHandle], esi
0x180021d59  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r14d; TokenType
0x180021d5e  lea     r9d, [r14+1]; ImpersonationLevel
0x180021d62  call    cs:__imp_DuplicateTokenEx
0x180021d68  test    eax, eax
0x180021d6a  jnz     short loc_180021DCD
0x180021d6c  mov     rcx, [rbx+18h]; hExistingToken
0x180021d70  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180021d74  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180021d79  mov     r9d, r14d; ImpersonationLevel
0x180021d7c  xor     edx, edx; dwDesiredAccess
0x180021d7e  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r14d; TokenType
0x180021d83  call    cs:__imp_DuplicateTokenEx
0x180021d89  test    eax, eax
0x180021d8b  jnz     short loc_180021DCD
0x180021d8d  test    byte ptr cs:g_dwDebugFlags, 3
0x180021d94  jz      short loc_180021DCD
0x180021d96  call    cs:__imp_GetLastError
0x180021d9c  mov     rcx, cs:g_pDebug
0x180021da3  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180021daa  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x180021dae  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021db5  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180021dbc  mov     r8d, 464h
0x180021dc2  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180021dc7  call    cs:__imp_PuDbgPrint
0x180021dcd  cmp     qword ptr [rdi], 0
0x180021dd1  jz      short loc_180021DD9
0x180021dd3  or      [rbx+104h], esi
0x180021dd9  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180021ddd  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180021de3  mov     rcx, r15
0x180021de6  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x180021dec  cmp     qword ptr [rdi], 0
0x180021df0  jz      short loc_180021E08
0x180021df2  cmp     dword ptr [rbx+74h], 0
0x180021df6  jnz     short loc_180021E08
0x180021df8  xchg    esi, [rbx+74h]
0x180021dfb  test    esi, esi
0x180021dfd  jnz     short loc_180021E08
0x180021dff  mov     rcx, [rdi]
0x180021e02  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180021e08  mov     rax, [rdi]
0x180021e0b  mov     rcx, [rbp+57h+var_40]
0x180021e0f  xor     rcx, rsp; StackCookie
0x180021e12  call    __security_check_cookie
0x180021e17  add     rsp, 98h
0x180021e1e  pop     r15
0x180021e20  pop     r14
0x180021e22  pop     rdi
0x180021e23  pop     rsi
0x180021e24  pop     rbx
0x180021e25  pop     rbp
0x180021e26  retn
```
