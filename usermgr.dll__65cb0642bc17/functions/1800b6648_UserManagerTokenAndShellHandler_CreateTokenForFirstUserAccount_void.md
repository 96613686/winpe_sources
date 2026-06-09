# UserManagerTokenAndShellHandler::CreateTokenForFirstUserAccount(void)

- ea: `0x1800b6648`
- end: `0x1800b6730`
- name: `?CreateTokenForFirstUserAccount@UserManagerTokenAndShellHandler@@AEAAKXZ`
- size: `232`
- prototype: `unsigned int __fastcall(UserManagerTokenAndShellHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b68e4`

## callees

- `0x1800356f8`
- `0x1800b6288`
- `0x1800b6648`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b6674`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b6674`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b6700`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b6700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b670a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b670a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b66bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b66bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b66d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b66d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b671d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b671d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserManagerTokenAndShellHandler::CreateTokenForFirstUserAccount(
        UserManagerTokenAndShellHandler *this)
{
  DWORD LastError; // ebx
  int User; // eax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v6; // [rsp+48h] [rbp+10h] BYREF

  LastError = 0;
  TokenHandle = (void *)-1LL;
  if ( (_BYTE)dword_18014828C )
  {
    AcquireSRWLockExclusive(&stru_180148210);
    v6 = &stru_180148210;
    User = UserManagerTokenAndShellHandler::AutoLogonDefaultAccountAndCreateUser(
             (PSRWLOCK)&g_UserManagerTokenAndShellHandler,
             &TargetHandle);
    if ( User < 0 )
    {
      LastError = (unsigned __int16)User;
      if ( (User & 0x1FFF0000) != 0x70000 )
        LastError = User;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v6);
  }
  else
  {
    if ( !BYTE1(dword_18014828C) )
      return LastError;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)
      || !DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &phNewToken) )
    {
      LastError = GetLastError();
    }
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800b6648  mov     [rsp+arg_10], rbx
0x1800b664d  mov     [rsp+TokenHandle], rcx
0x1800b6652  push    rdi
0x1800b6653  sub     rsp, 30h
0x1800b6657  xor     ebx, ebx
0x1800b6659  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800b6662  cmp     byte ptr cs:dword_18014828C, bl
0x1800b6668  jz      short loc_1800B66B5
0x1800b666a  lea     rdi, stru_180148210
0x1800b6671  mov     rcx, rdi; SRWLock
0x1800b6674  call    cs:__imp_AcquireSRWLockExclusive
0x1800b667a  mov     [rsp+38h+arg_8], rdi
0x1800b667f  lea     rdx, TargetHandle; lpTargetHandle
0x1800b6686  lea     rcx, ?g_UserManagerTokenAndShellHandler@@3VUserManagerTokenAndShellHandler@@A; SRWLock
0x1800b668d  call    ?AutoLogonDefaultAccountAndCreateUser@UserManagerTokenAndShellHandler@@AEAAJPEAPEAX@Z; UserManagerTokenAndShellHandler::AutoLogonDefaultAccountAndCreateUser(void * *)
0x1800b6692  mov     ecx, eax
0x1800b6694  test    eax, eax
0x1800b6696  jns     short loc_1800B66A9
0x1800b6698  and     eax, 1FFF0000h
0x1800b669d  cmp     eax, 70000h
0x1800b66a2  movzx   ebx, cx
0x1800b66a5  jz      short loc_1800B66A9
0x1800b66a7  mov     ebx, ecx
0x1800b66a9  lea     rcx, [rsp+38h+arg_8]
0x1800b66ae  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800b66b3  jmp     short loc_1800B6712
0x1800b66b5  cmp     byte ptr cs:dword_18014828C+1, bl
0x1800b66bb  jz      short loc_1800B6723
0x1800b66bd  call    cs:__imp_GetCurrentProcess
0x1800b66c3  mov     rcx, rax; ProcessHandle
0x1800b66c6  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800b66cb  mov     edi, 2
0x1800b66d0  mov     edx, edi; DesiredAccess
0x1800b66d2  call    cs:__imp_OpenProcessToken
0x1800b66d8  test    eax, eax
0x1800b66da  jz      short loc_1800B670A
0x1800b66dc  lea     rax, phNewToken
0x1800b66e3  mov     [rsp+38h+phNewToken], rax; phNewToken
0x1800b66e8  mov     [rsp+38h+TokenType], 1; TokenType
0x1800b66f0  mov     r9d, edi; ImpersonationLevel
0x1800b66f3  xor     r8d, r8d; lpTokenAttributes
0x1800b66f6  mov     edx, 0F01FFh; dwDesiredAccess
0x1800b66fb  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800b6700  call    cs:__imp_DuplicateTokenEx
0x1800b6706  test    eax, eax
0x1800b6708  jnz     short loc_1800B6712
0x1800b670a  call    cs:__imp_GetLastError
0x1800b6710  mov     ebx, eax
0x1800b6712  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800b6717  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b671b  jz      short loc_1800B6723
0x1800b671d  call    cs:__imp_CloseHandle
0x1800b6723  mov     eax, ebx
0x1800b6725  mov     rbx, [rsp+38h+arg_10]
0x1800b672a  add     rsp, 30h
0x1800b672e  pop     rdi
0x1800b672f  retn
```
