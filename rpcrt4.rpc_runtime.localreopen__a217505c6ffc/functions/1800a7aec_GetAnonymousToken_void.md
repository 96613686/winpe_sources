# GetAnonymousToken(void)

- ea: `0x1800a7aec`
- end: `0x1800a7b56`
- name: `?GetAnonymousToken@@YAPEAXXZ`
- size: `106`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180085260`

## callees

- `0x1800a7aec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a7b33`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a7b33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7af9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7b18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7af9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a7b18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a7b3f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a7b3f`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x1800a7b08`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x1800a7b08`

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
0x1800a7aec  sub     rsp, 28h
0x1800a7af0  mov     [rsp+28h+TokenHandle], 0
0x1800a7af9  call    cs:__imp_GetCurrentThread
0x1800a7b00  nop     dword ptr [rax+rax+00h]
0x1800a7b05  mov     rcx, rax; ThreadHandle
0x1800a7b08  call    cs:__imp_ImpersonateAnonymousToken
0x1800a7b0f  nop     dword ptr [rax+rax+00h]
0x1800a7b14  test    eax, eax
0x1800a7b16  jz      short loc_1800A7B4B
0x1800a7b18  call    cs:__imp_GetCurrentThread
0x1800a7b1f  nop     dword ptr [rax+rax+00h]
0x1800a7b24  xor     r8d, r8d; OpenAsSelf
0x1800a7b27  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800a7b2c  mov     rcx, rax; ThreadHandle
0x1800a7b2f  lea     edx, [r8+8]; DesiredAccess
0x1800a7b33  call    cs:__imp_OpenThreadToken
0x1800a7b3a  nop     dword ptr [rax+rax+00h]
0x1800a7b3f  call    cs:__imp_RevertToSelf
0x1800a7b46  nop     dword ptr [rax+rax+00h]
0x1800a7b4b  mov     rax, [rsp+28h+TokenHandle]
0x1800a7b50  add     rsp, 28h
0x1800a7b54  retn
```
