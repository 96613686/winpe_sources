# WxIsSystemService

- ea: `0x180073fc4`
- end: `0x1800741c0`
- name: `WxIsSystemService`
- size: `508`
- prototype: `__int64 __fastcall(LPBOOL AccessStatus)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013778`
- `0x18001de3c`
- `0x18001fb30`
- `0x18001fd20`
- `0x1800600c0`
- `0x1800a0974`

## callees

- `0x180073fc4`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18007408e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18007408e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800740d4`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800740d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007404b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007404b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007402a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007402a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074012`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007405d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007405d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007403a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007403a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800740ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800740ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074104`

## pseudocode

```c
__int64 __fastcall WxIsSystemService(LPBOOL AccessStatus)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  HANDLE hExistingToken; // [rsp+50h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-Dh] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-9h] BYREF

  TokenHandle = 0;
  hExistingToken = 0;
  PrivilegeSetLength = 44;
  GrantedAccess = 0;
  *AccessStatus = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    goto LABEL_5;
  if ( GetLastError() == 1008 )
    goto LABEL_3;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_3:
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2000Au, &hExistingToken) )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
      goto LABEL_7;
    }
    if ( !DuplicateTokenEx(hExistingToken, 0x2000Cu, 0, SecurityIdentification, TokenImpersonation, &TokenHandle) )
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
      goto LABEL_7;
    }
LABEL_5:
    if ( AccessCheck(
           c_rgbSystemServiceSd,
           TokenHandle,
           1u,
           (PGENERIC_MAPPING)&GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           AccessStatus) )
    {
      v4 = 0;
    }
    else
    {
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147418113;
    }
  }
LABEL_7:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( hExistingToken )
    CloseHandle(hExistingToken);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180073fc4  push    rbp
0x180073fc6  push    rbx
0x180073fc7  push    rdi
0x180073fc8  push    r14
0x180073fca  lea     rbp, [rsp-3Fh]
0x180073fcf  sub     rsp, 0A8h
0x180073fd6  mov     rax, cs:__security_cookie
0x180073fdd  xor     rax, rsp
0x180073fe0  mov     [rbp+57h+var_30], rax
0x180073fe4  mov     rdi, rcx
0x180073fe7  mov     [rbp+57h+var_7C], 0
0x180073fee  mov     [rbp+57h+TokenHandle], 0
0x180073ff6  mov     [rbp+57h+hExistingToken], 0
0x180073ffe  mov     [rbp+57h+PrivilegeSetLength], 2Ch ; ','
0x180074005  mov     [rbp+57h+var_68], 0
0x18007400c  mov     dword ptr [rcx], 0
0x180074012  call    cs:__imp_GetCurrentThread
0x180074018  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18007401c  mov     edx, 2000Ch; DesiredAccess
0x180074021  mov     rcx, rax; ThreadHandle
0x180074024  mov     r8d, 1; OpenAsSelf
0x18007402a  call    cs:__imp_OpenThreadToken
0x180074030  mov     r14d, 80070000h
0x180074036  test    eax, eax
0x180074038  jnz     short loc_18007409C
0x18007403a  call    cs:__imp_GetLastError
0x180074040  cmp     eax, 3F0h
0x180074045  jnz     loc_180074125
0x18007404b  call    cs:__imp_GetCurrentProcess
0x180074051  lea     r8, [rbp+57h+hExistingToken]; TokenHandle
0x180074055  mov     edx, 2000Ah; DesiredAccess
0x18007405a  mov     rcx, rax; ProcessHandle
0x18007405d  call    cs:__imp_OpenProcessToken
0x180074063  test    eax, eax
0x180074065  jz      loc_180074148
0x18007406b  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x18007406f  lea     rax, [rbp+57h+TokenHandle]
0x180074073  mov     [rsp+0C0h+phNewToken], rax; phNewToken
0x180074078  mov     r9d, 1; ImpersonationLevel
0x18007407e  xor     r8d, r8d; lpTokenAttributes
0x180074081  mov     [rsp+0C0h+TokenType], 2; TokenType
0x180074089  mov     edx, 2000Ch; dwDesiredAccess
0x18007408e  call    cs:__imp_DuplicateTokenEx
0x180074094  test    eax, eax
0x180074096  jz      loc_180074170
0x18007409c  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800740a0  lea     rax, [rbp+57h+var_68]
0x1800740a4  mov     [rsp+0C0h+AccessStatus], rdi; AccessStatus
0x1800740a9  lea     r9, GenericMapping; GenericMapping
0x1800740b0  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x1800740b5  lea     rcx, c_rgbSystemServiceSd; pSecurityDescriptor
0x1800740bc  lea     rax, [rbp+57h+PrivilegeSetLength]
0x1800740c0  mov     r8d, 1; DesiredAccess
0x1800740c6  mov     [rsp+0C0h+phNewToken], rax; PrivilegeSetLength
0x1800740cb  lea     rax, [rbp+57h+PrivilegeSet]
0x1800740cf  mov     qword ptr [rsp+0C0h+TokenType], rax; PrivilegeSet
0x1800740d4  call    cs:__imp_AccessCheck
0x1800740da  test    eax, eax
0x1800740dc  jz      loc_180074198
0x1800740e2  xor     ebx, ebx
0x1800740e4  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800740e8  test    rcx, rcx
0x1800740eb  jz      short loc_1800740FB
0x1800740ed  call    cs:__imp_CloseHandle
0x1800740f3  mov     [rbp+57h+TokenHandle], 0
0x1800740fb  mov     rcx, [rbp+57h+hExistingToken]; hObject
0x1800740ff  test    rcx, rcx
0x180074102  jz      short loc_18007410A
0x180074104  call    cs:__imp_CloseHandle
0x18007410a  mov     eax, ebx
0x18007410c  mov     rcx, [rbp+57h+var_30]
0x180074110  xor     rcx, rsp; StackCookie
0x180074113  call    __security_check_cookie
0x180074118  add     rsp, 0A8h
0x18007411f  pop     r14
0x180074121  pop     rdi
0x180074122  pop     rbx
0x180074123  pop     rbp
0x180074124  retn
0x180074125  call    cs:__imp_GetLastError
0x18007412b  mov     ebx, eax
0x18007412d  test    eax, eax
0x18007412f  jle     short loc_180074137
0x180074131  movzx   ebx, ax
0x180074134  or      ebx, r14d
0x180074137  test    ebx, ebx
0x180074139  jns     loc_18007404B
0x18007413f  mov     [rbp+57h+var_7C], 289h
0x180074146  jmp     short loc_1800740E4
0x180074148  call    cs:__imp_GetLastError
0x18007414e  mov     ebx, eax
0x180074150  test    eax, eax
0x180074152  jle     short loc_18007415A
0x180074154  movzx   ebx, ax
0x180074157  or      ebx, r14d
0x18007415a  test    ebx, ebx
0x18007415c  mov     [rbp+57h+var_7C], 28Eh
0x180074163  mov     eax, 8000FFFFh
0x180074168  cmovns  ebx, eax
0x18007416b  jmp     loc_1800740E4
0x180074170  call    cs:__imp_GetLastError
0x180074176  mov     ebx, eax
0x180074178  test    eax, eax
0x18007417a  jle     short loc_180074182
0x18007417c  movzx   ebx, ax
0x18007417f  or      ebx, r14d
0x180074182  test    ebx, ebx
0x180074184  mov     [rbp+57h+var_7C], 29Ah
0x18007418b  mov     eax, 8000FFFFh
0x180074190  cmovns  ebx, eax
0x180074193  jmp     loc_1800740E4
0x180074198  call    cs:__imp_GetLastError
0x18007419e  mov     ebx, eax
0x1800741a0  test    eax, eax
0x1800741a2  jle     short loc_1800741AA
0x1800741a4  movzx   ebx, ax
0x1800741a7  or      ebx, r14d
0x1800741aa  test    ebx, ebx
0x1800741ac  mov     [rbp+57h+var_7C], 2A8h
0x1800741b3  mov     eax, 8000FFFFh
0x1800741b8  cmovns  ebx, eax
0x1800741bb  jmp     loc_1800740E4
```
