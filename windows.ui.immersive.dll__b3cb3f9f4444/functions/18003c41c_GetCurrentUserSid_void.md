# GetCurrentUserSid(void * *)

- ea: `0x18003c41c`
- end: `0x18003c53f`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023a14`
- `0x18003b4e8`
- `0x18003c324`
- `0x18004ad7c`
- `0x18004ca2c`

## callees

- `0x18003c41c`
- `0x18003d244`
- `0x180054130`
- `0x1800b5554`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003c46b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003c46b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c44e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003c44e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003c4a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003c4a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c50f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c50f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c4e0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c4e0`

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
0x18003c41c  mov     [rsp+arg_8], rbx
0x18003c421  push    rdi
0x18003c422  sub     rsp, 0B0h
0x18003c429  mov     rax, cs:__security_cookie
0x18003c430  xor     rax, rsp
0x18003c433  mov     [rsp+0B8h+var_18], rax
0x18003c43b  mov     rdi, rcx
0x18003c43e  mov     qword ptr [rcx], 0
0x18003c445  mov     [rsp+0B8h+TokenHandle], 0
0x18003c44e  call    cs:__imp_GetCurrentThread
0x18003c455  nop     dword ptr [rax+rax+00h]
0x18003c45a  mov     edx, 8; DesiredAccess
0x18003c45f  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18003c464  mov     rcx, rax; ThreadHandle
0x18003c467  lea     r8d, [rdx-7]; OpenAsSelf
0x18003c46b  call    cs:__imp_OpenThreadToken
0x18003c472  nop     dword ptr [rax+rax+00h]
0x18003c477  test    eax, eax
0x18003c479  jnz     short loc_18003C4BD
0x18003c47b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003c480  mov     ebx, eax
0x18003c482  cmp     eax, 800703F0h
0x18003c487  jnz     short loc_18003C4B9
0x18003c489  call    cs:__imp_GetCurrentProcess
0x18003c490  nop     dword ptr [rax+rax+00h]
0x18003c495  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x18003c49a  mov     edx, 8; DesiredAccess
0x18003c49f  mov     rcx, rax; ProcessHandle
0x18003c4a2  call    cs:__imp_OpenProcessToken
0x18003c4a9  nop     dword ptr [rax+rax+00h]
0x18003c4ae  test    eax, eax
0x18003c4b0  jnz     short loc_18003C4BD
0x18003c4b2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003c4b7  mov     ebx, eax
0x18003c4b9  test    ebx, ebx
0x18003c4bb  js      short loc_18003C51B
0x18003c4bd  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x18003c4c2  lea     rax, [rsp+0B8h+var_80]
0x18003c4c7  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18003c4cd  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18003c4d2  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18003c4d7  mov     [rsp+0B8h+var_80], r9d
0x18003c4dc  lea     edx, [r9-57h]; TokenInformationClass
0x18003c4e0  call    cs:__imp_GetTokenInformation
0x18003c4e7  nop     dword ptr [rax+rax+00h]
0x18003c4ec  test    eax, eax
0x18003c4ee  jnz     short loc_18003C4FB
0x18003c4f0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003c4f5  mov     ebx, eax
0x18003c4f7  test    eax, eax
0x18003c4f9  js      short loc_18003C50A
0x18003c4fb  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x18003c500  mov     rdx, rdi; void **
0x18003c503  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x18003c508  mov     ebx, eax
0x18003c50a  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18003c50f  call    cs:__imp_CloseHandle
0x18003c516  nop     dword ptr [rax+rax+00h]
0x18003c51b  mov     eax, ebx
0x18003c51d  mov     rcx, [rsp+0B8h+var_18]
0x18003c525  xor     rcx, rsp; StackCookie
0x18003c528  call    __security_check_cookie
0x18003c52d  mov     rbx, [rsp+0B8h+arg_8]
0x18003c535  add     rsp, 0B0h
0x18003c53c  pop     rdi
0x18003c53d  retn
```
