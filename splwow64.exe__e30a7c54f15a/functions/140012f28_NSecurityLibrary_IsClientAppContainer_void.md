# NSecurityLibrary::IsClientAppContainer(void)

- ea: `0x140012f28`
- end: `0x140012fd4`
- name: `?IsClientAppContainer@NSecurityLibrary@@YA_NXZ`
- size: `172`
- prototype: `bool __fastcall(NSecurityLibrary *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006f98`
- `0x1400077fc`
- `0x14000d9e0`
- `0x14000ed78`
- `0x14000ef6c`
- `0x14000f42c`
- `0x14000f5c4`

## callees

- `0x140012f28`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140012fc6`
- `KERNEL32!CloseHandle` at `0x140012fc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140012f3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140012f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140012f3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140012f5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140012f50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140012f6e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140012f50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140012f6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012fa9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012fa9`

## pseudocode

```c
bool __fastcall NSecurityLibrary::IsClientAppContainer(NSecurityLibrary *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  HANDLE v3; // rax
  void *v4; // rcx
  BOOL v5; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v1 = 1;
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v3 = GetCurrentThread();
    OpenThreadToken(v3, 8u, 0, &TokenHandle);
  }
  v4 = TokenHandle;
  if ( TokenHandle != (void *)-1LL )
  {
    if ( TokenHandle )
    {
      TokenInformation = 1;
      ReturnLength = 0;
      v5 = GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      v4 = TokenHandle;
      if ( v5 )
        v1 = TokenInformation != 0;
    }
    if ( v4 != (void *)-1LL )
      CloseHandle(v4);
  }
  return v1;
}

```

## disassembly

```asm
0x140012f28  push    rbx
0x140012f2a  sub     rsp, 30h
0x140012f2e  mov     ebx, 1
0x140012f33  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140012f3c  call    cs:__imp_GetCurrentThread
0x140012f42  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x140012f47  mov     r8d, ebx; OpenAsSelf
0x140012f4a  mov     rcx, rax; ThreadHandle
0x140012f4d  lea     edx, [rbx+7]; DesiredAccess
0x140012f50  call    cs:__imp_OpenThreadToken
0x140012f56  test    eax, eax
0x140012f58  jnz     short loc_140012F74
0x140012f5a  call    cs:__imp_GetCurrentThread
0x140012f60  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x140012f65  xor     r8d, r8d; OpenAsSelf
0x140012f68  mov     rcx, rax; ThreadHandle
0x140012f6b  lea     edx, [rbx+7]; DesiredAccess
0x140012f6e  call    cs:__imp_OpenThreadToken
0x140012f74  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x140012f79  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140012f7d  jz      short loc_140012FCC
0x140012f7f  test    rcx, rcx
0x140012f82  jz      short loc_140012FC0
0x140012f84  mov     r9d, 4; TokenInformationLength
0x140012f8a  mov     [rsp+38h+TokenInformation], ebx
0x140012f8e  lea     rax, [rsp+38h+arg_8]
0x140012f93  mov     [rsp+38h+arg_8], 0
0x140012f9b  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x140012fa0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140012fa5  lea     edx, [r9+19h]; TokenInformationClass
0x140012fa9  call    cs:__imp_GetTokenInformation
0x140012faf  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x140012fb4  test    eax, eax
0x140012fb6  jz      short loc_140012FC0
0x140012fb8  cmp     [rsp+38h+TokenInformation], 0
0x140012fbd  setnz   bl
0x140012fc0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140012fc4  jz      short loc_140012FCC
0x140012fc6  call    cs:__imp_CloseHandle
0x140012fcc  mov     al, bl
0x140012fce  add     rsp, 30h
0x140012fd2  pop     rbx
0x140012fd3  retn
```
