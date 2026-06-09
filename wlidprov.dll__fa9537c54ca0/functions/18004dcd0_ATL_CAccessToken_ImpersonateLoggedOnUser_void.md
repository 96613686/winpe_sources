# ATL::CAccessToken::ImpersonateLoggedOnUser(void)

- ea: `0x18004dcd0`
- end: `0x18004dd78`
- name: `?ImpersonateLoggedOnUser@CAccessToken@ATL@@QEBA_NXZ`
- size: `168`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004dc60`

## callees

- `0x18001a0b4`
- `0x18001a120`
- `0x18004dcd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dcff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dcff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004dce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004dce2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004dcf5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004dcf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dd17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dd17`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd26`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004dd26`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004dd66`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004dd66`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
char __fastcall ATL::CAccessToken::ImpersonateLoggedOnUser(ATL::CAccessToken *this)
{
  HANDLE CurrentThread; // rax
  void *v3; // rcx
  void **v4; // rbx
  _QWORD *v5; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( (OpenThreadToken(CurrentThread, 0, 0, &TokenHandle) || GetLastError() == 1008) && TokenHandle != (void *)-1LL )
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
0x18004dcd0  push    rbx
0x18004dcd2  sub     rsp, 20h
0x18004dcd6  mov     rbx, rcx
0x18004dcd9  mov     [rsp+28h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18004dce2  call    cs:__imp_GetCurrentThread
0x18004dce8  mov     rcx, rax; ThreadHandle
0x18004dceb  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18004dcf0  xor     r8d, r8d; OpenAsSelf
0x18004dcf3  xor     edx, edx; DesiredAccess
0x18004dcf5  call    cs:__imp_OpenThreadToken
0x18004dcfb  test    eax, eax
0x18004dcfd  jnz     short loc_18004DD0C
0x18004dcff  call    cs:__imp_GetLastError
0x18004dd05  cmp     eax, 3F0h
0x18004dd0a  jnz     short loc_18004DD1D
0x18004dd0c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18004dd11  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004dd15  jz      short loc_18004DD1D
0x18004dd17  call    cs:__imp_CloseHandle
0x18004dd1d  mov     rcx, [rbx+8]; hToken
0x18004dd21  test    rcx, rcx
0x18004dd24  jz      short loc_18004DD6C
0x18004dd26  call    cs:__imp_ImpersonateLoggedOnUser
0x18004dd2c  test    eax, eax
0x18004dd2e  jz      short loc_18004DD6C
0x18004dd30  add     rbx, 18h
0x18004dd34  mov     [rsp+28h+TokenHandle], rbx
0x18004dd39  mov     rcx, [rbx]; Block
0x18004dd3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004dd41  nop
0x18004dd42  mov     ecx, 8; Size
0x18004dd47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004dd4c  lea     rcx, ??_7CRevertToSelf@CAccessToken@ATL@@6B@; const ATL::CAccessToken::CRevertToSelf::`vftable'
0x18004dd53  mov     [rax], rcx
0x18004dd56  mov     [rbx], rax
0x18004dd59  jmp     short loc_18004DD60
0x18004dd5b  mov     rbx, [rsp+28h+TokenHandle]
0x18004dd60  cmp     qword ptr [rbx], 0
0x18004dd64  jnz     short loc_18004DD74
0x18004dd66  call    cs:__imp_RevertToSelf
0x18004dd6c  xor     al, al
0x18004dd6e  add     rsp, 20h
0x18004dd72  pop     rbx
0x18004dd73  retn
0x18004dd74  mov     al, 1
0x18004dd76  jmp     short loc_18004DD6E
```
