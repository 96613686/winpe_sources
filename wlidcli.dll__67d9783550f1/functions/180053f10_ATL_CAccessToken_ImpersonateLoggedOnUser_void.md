# ATL::CAccessToken::ImpersonateLoggedOnUser(void)

- ea: `0x180053f10`
- end: `0x180053fb8`
- name: `?ImpersonateLoggedOnUser@CAccessToken@ATL@@QEBA_NXZ`
- size: `168`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180053ea0`

## callees

- `0x180002d84`
- `0x180003298`
- `0x180053f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053f35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053f35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053f57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053f57`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053f66`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053f66`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180053fa6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180053fa6`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
char __fastcall ATL::CAccessToken::ImpersonateLoggedOnUser(ATL::CAccessToken *this)
{
  HANDLE CurrentThread; // rax
  void *v3; // rcx
  void **v4; // rbx
  _QWORD *v5; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = (HANDLE)-1LL;
  CurrentThread = GetCurrentThread();
  if ( (OpenThreadToken(CurrentThread, 0, 0, &TokenHandle) || GetLastError() == 1008) && TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( !v3 || !ImpersonateLoggedOnUser(v3) )
    return 0;
  v4 = (void **)((char *)this + 24);
  TokenHandle = v4;
  operator delete(*v4);
  v5 = operator new(8u);
  *v5 = &ATL::CAccessToken::CRevertToSelf::`vftable';
  *v4 = v5;
  if ( !*v4 )
  {
    RevertToSelf();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180053f10  push    rbx
0x180053f12  sub     rsp, 20h
0x180053f16  mov     rbx, rcx
0x180053f19  mov     [rsp+28h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180053f22  call    cs:__imp_GetCurrentThread
0x180053f28  mov     rcx, rax; ThreadHandle
0x180053f2b  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180053f30  xor     r8d, r8d; OpenAsSelf
0x180053f33  xor     edx, edx; DesiredAccess
0x180053f35  call    cs:__imp_OpenThreadToken
0x180053f3b  test    eax, eax
0x180053f3d  jnz     short loc_180053F4C
0x180053f3f  call    cs:__imp_GetLastError
0x180053f45  cmp     eax, 3F0h
0x180053f4a  jnz     short loc_180053F5D
0x180053f4c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180053f51  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180053f55  jz      short loc_180053F5D
0x180053f57  call    cs:__imp_CloseHandle
0x180053f5d  mov     rcx, [rbx+8]; hToken
0x180053f61  test    rcx, rcx
0x180053f64  jz      short loc_180053FAC
0x180053f66  call    cs:__imp_ImpersonateLoggedOnUser
0x180053f6c  test    eax, eax
0x180053f6e  jz      short loc_180053FAC
0x180053f70  add     rbx, 18h
0x180053f74  mov     [rsp+28h+TokenHandle], rbx
0x180053f79  mov     rcx, [rbx]; Block
0x180053f7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053f81  nop
0x180053f82  mov     ecx, 8; Size
0x180053f87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053f8c  lea     rcx, ??_7CRevertToSelf@CAccessToken@ATL@@6B@; const ATL::CAccessToken::CRevertToSelf::`vftable'
0x180053f93  mov     [rax], rcx
0x180053f96  mov     [rbx], rax
0x180053f99  jmp     short loc_180053FA0
0x180053f9b  mov     rbx, [rsp+28h+TokenHandle]
0x180053fa0  cmp     qword ptr [rbx], 0
0x180053fa4  jnz     short loc_180053FB4
0x180053fa6  call    cs:__imp_RevertToSelf
0x180053fac  xor     al, al
0x180053fae  add     rsp, 20h
0x180053fb2  pop     rbx
0x180053fb3  retn
0x180053fb4  mov     al, 1
0x180053fb6  jmp     short loc_180053FAE
```
