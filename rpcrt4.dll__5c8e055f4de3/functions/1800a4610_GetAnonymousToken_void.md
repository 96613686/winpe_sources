# GetAnonymousToken(void)

- ea: `0x1800a4610`
- end: `0x1800a465b`
- name: `?GetAnonymousToken@@YAPEAXXZ`
- size: `75`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800184d8`

## callees

- `0x1800a4610`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a4645`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a4645`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a461d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a4630`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a461d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a4630`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a464b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a464b`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x1800a4626`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x1800a4626`

## pseudocode

```c
void *GetAnonymousToken(void)
{
  HANDLE CurrentThread; // rax
  HANDLE v1; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( ImpersonateAnonymousToken(CurrentThread) )
  {
    v1 = GetCurrentThread();
    OpenThreadToken(v1, 8u, 0, &TokenHandle);
    RevertToSelf();
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x1800a4610  sub     rsp, 28h
0x1800a4614  mov     [rsp+28h+TokenHandle], 0
0x1800a461d  call    cs:__imp_GetCurrentThread
0x1800a4623  mov     rcx, rax; ThreadHandle
0x1800a4626  call    cs:__imp_ImpersonateAnonymousToken
0x1800a462c  test    eax, eax
0x1800a462e  jz      short loc_1800A4651
0x1800a4630  call    cs:__imp_GetCurrentThread
0x1800a4636  xor     r8d, r8d; OpenAsSelf
0x1800a4639  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800a463e  mov     rcx, rax; ThreadHandle
0x1800a4641  lea     edx, [r8+8]; DesiredAccess
0x1800a4645  call    cs:__imp_OpenThreadToken
0x1800a464b  call    cs:__imp_RevertToSelf
0x1800a4651  mov     rax, [rsp+28h+TokenHandle]
0x1800a4656  add     rsp, 28h
0x1800a465a  retn
```
