# GetCurrentUserSid(void * *)

- ea: `0x1800b0dc8`
- end: `0x1800b0ec6`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c0e8`
- `0x18046bee4`

## callees

- `0x1800b0dc8`
- `0x18015cb00`
- `0x18033ae8c`
- `0x18033b018`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b0e29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b0e29`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b0e3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b0e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b0dfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b0dfa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b0e11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b0e11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0e9d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b0e74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b0e74`

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
0x1800b0dc8  mov     [rsp+arg_8], rbx
0x1800b0dcd  push    rdi
0x1800b0dce  sub     rsp, 0B0h
0x1800b0dd5  mov     rax, cs:__security_cookie
0x1800b0ddc  xor     rax, rsp
0x1800b0ddf  mov     [rsp+0B8h+var_18], rax
0x1800b0de7  mov     rdi, rcx
0x1800b0dea  mov     qword ptr [rcx], 0
0x1800b0df1  mov     [rsp+0B8h+TokenHandle], 0
0x1800b0dfa  call    cs:__imp_GetCurrentThread
0x1800b0e00  mov     edx, 8; DesiredAccess
0x1800b0e05  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800b0e0a  mov     rcx, rax; ThreadHandle
0x1800b0e0d  lea     r8d, [rdx-7]; OpenAsSelf
0x1800b0e11  call    cs:__imp_OpenThreadToken
0x1800b0e17  test    eax, eax
0x1800b0e19  jnz     short loc_1800B0E51
0x1800b0e1b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b0e20  mov     ebx, eax
0x1800b0e22  cmp     eax, 800703F0h
0x1800b0e27  jnz     short loc_1800B0E4D
0x1800b0e29  call    cs:__imp_GetCurrentProcess
0x1800b0e2f  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800b0e34  mov     edx, 8; DesiredAccess
0x1800b0e39  mov     rcx, rax; ProcessHandle
0x1800b0e3c  call    cs:__imp_OpenProcessToken
0x1800b0e42  test    eax, eax
0x1800b0e44  jnz     short loc_1800B0E51
0x1800b0e46  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b0e4b  mov     ebx, eax
0x1800b0e4d  test    ebx, ebx
0x1800b0e4f  js      short loc_1800B0EA3
0x1800b0e51  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800b0e56  lea     rax, [rsp+0B8h+var_80]
0x1800b0e5b  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800b0e61  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800b0e66  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800b0e6b  mov     [rsp+0B8h+var_80], r9d
0x1800b0e70  lea     edx, [r9-57h]; TokenInformationClass
0x1800b0e74  call    cs:__imp_GetTokenInformation
0x1800b0e7a  test    eax, eax
0x1800b0e7c  jnz     short loc_1800B0E89
0x1800b0e7e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b0e83  mov     ebx, eax
0x1800b0e85  test    eax, eax
0x1800b0e87  js      short loc_1800B0E98
0x1800b0e89  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x1800b0e8e  mov     rdx, rdi; void **
0x1800b0e91  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x1800b0e96  mov     ebx, eax
0x1800b0e98  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800b0e9d  call    cs:__imp_CloseHandle
0x1800b0ea3  mov     eax, ebx
0x1800b0ea5  mov     rcx, [rsp+0B8h+var_18]
0x1800b0ead  xor     rcx, rsp; StackCookie
0x1800b0eb0  call    __security_check_cookie
0x1800b0eb5  mov     rbx, [rsp+0B8h+arg_8]
0x1800b0ebd  add     rsp, 0B0h
0x1800b0ec4  pop     rdi
0x1800b0ec5  retn
```
