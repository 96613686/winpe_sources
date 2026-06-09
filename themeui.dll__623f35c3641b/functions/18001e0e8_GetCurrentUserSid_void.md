# GetCurrentUserSid(void * *)

- ea: `0x18001e0e8`
- end: `0x18001e1e6`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dfc4`

## callees

- `0x18001e0e8`
- `0x180030f64`
- `0x1800358c0`
- `0x1800537f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e131`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e131`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e11a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e11a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e15c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e15c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e1bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e1bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e194`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e194`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147023888 )
      goto LABEL_5;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
LABEL_5:
      if ( Error < 0 )
        return (unsigned int)Error;
    }
  }
  ReturnLength = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = AllocAndCopySid(TokenInformation[0], a1);
  }
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001e0e8  mov     [rsp+arg_8], rbx
0x18001e0ed  push    rdi
0x18001e0ee  sub     rsp, 0B0h
0x18001e0f5  mov     rax, cs:__security_cookie
0x18001e0fc  xor     rax, rsp
0x18001e0ff  mov     [rsp+0B8h+var_18], rax
0x18001e107  mov     rdi, rcx
0x18001e10a  mov     qword ptr [rcx], 0
0x18001e111  mov     [rsp+0B8h+TokenHandle], 0
0x18001e11a  call    cs:__imp_GetCurrentThread
0x18001e120  mov     edx, 8; DesiredAccess
0x18001e125  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18001e12a  mov     rcx, rax; ThreadHandle
0x18001e12d  lea     r8d, [rdx-7]; OpenAsSelf
0x18001e131  call    cs:__imp_OpenThreadToken
0x18001e137  test    eax, eax
0x18001e139  jnz     short loc_18001E171
0x18001e13b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e140  mov     ebx, eax
0x18001e142  cmp     eax, 800703F0h
0x18001e147  jnz     short loc_18001E16D
0x18001e149  call    cs:__imp_GetCurrentProcess
0x18001e14f  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x18001e154  mov     edx, 8; DesiredAccess
0x18001e159  mov     rcx, rax; ProcessHandle
0x18001e15c  call    cs:__imp_OpenProcessToken
0x18001e162  test    eax, eax
0x18001e164  jnz     short loc_18001E171
0x18001e166  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e16b  mov     ebx, eax
0x18001e16d  test    ebx, ebx
0x18001e16f  js      short loc_18001E1C3
0x18001e171  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x18001e176  lea     rax, [rsp+0B8h+var_80]
0x18001e17b  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18001e181  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18001e186  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18001e18b  mov     [rsp+0B8h+var_80], r9d
0x18001e190  lea     edx, [r9-57h]; TokenInformationClass
0x18001e194  call    cs:__imp_GetTokenInformation
0x18001e19a  test    eax, eax
0x18001e19c  jnz     short loc_18001E1A9
0x18001e19e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e1a3  mov     ebx, eax
0x18001e1a5  test    eax, eax
0x18001e1a7  js      short loc_18001E1B8
0x18001e1a9  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x18001e1ae  mov     rdx, rdi; void **
0x18001e1b1  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x18001e1b6  mov     ebx, eax
0x18001e1b8  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18001e1bd  call    cs:__imp_CloseHandle
0x18001e1c3  mov     eax, ebx
0x18001e1c5  mov     rcx, [rsp+0B8h+var_18]
0x18001e1cd  xor     rcx, rsp; StackCookie
0x18001e1d0  call    __security_check_cookie
0x18001e1d5  mov     rbx, [rsp+0B8h+arg_8]
0x18001e1dd  add     rsp, 0B0h
0x18001e1e4  pop     rdi
0x18001e1e5  retn
```
