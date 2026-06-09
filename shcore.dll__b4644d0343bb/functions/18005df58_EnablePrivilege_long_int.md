# EnablePrivilege(long,int)

- ea: `0x18005df58`
- end: `0x18005dfd6`
- name: `?EnablePrivilege@@YAHJH@Z`
- size: `126`
- prototype: `int(int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002009c`

## callees

- `0x18005df58`
- `0x180066910`
- `0x180091c40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005df8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005df8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005df7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dfb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dfb6`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(__int64 a1, int a2)
{
  unsigned int v2; // ebx
  HANDLE CurrentProcess; // rax
  int v5; // edx
  void *TokenHandle; // [rsp+20h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES v8; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v8 = 0;
    v2 = EnableTokenPrivilege(TokenHandle, v5, &v8, a2);
    CloseHandle(TokenHandle);
  }
  return v2;
}

```

## disassembly

```asm
0x18005df58  mov     [rsp+arg_0], rbx
0x18005df5d  push    rdi
0x18005df5e  sub     rsp, 40h
0x18005df62  mov     rax, cs:__security_cookie
0x18005df69  xor     rax, rsp
0x18005df6c  mov     [rsp+48h+var_10], rax
0x18005df71  xor     ebx, ebx
0x18005df73  mov     edi, edx
0x18005df75  mov     [rsp+48h+TokenHandle], rbx
0x18005df7a  call    cs:__imp_GetCurrentProcess
0x18005df80  mov     rcx, rax; ProcessHandle
0x18005df83  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18005df88  lea     edx, [rbx+28h]; DesiredAccess
0x18005df8b  call    cs:__imp_OpenProcessToken
0x18005df91  test    eax, eax
0x18005df93  jz      short loc_18005DFBC
0x18005df95  mov     rcx, [rsp+48h+TokenHandle]; void *
0x18005df9a  lea     r8, [rsp+48h+var_20]; struct _TOKEN_PRIVILEGES *
0x18005df9f  xorps   xmm0, xmm0
0x18005dfa2  mov     r9d, edi; int
0x18005dfa5  movups  xmmword ptr [rsp+48h+var_20.PrivilegeCount], xmm0
0x18005dfaa  call    ?EnableTokenPrivilege@@YAHPEAXJAEAU_TOKEN_PRIVILEGES@@H@Z; EnableTokenPrivilege(void *,long,_TOKEN_PRIVILEGES &,int)
0x18005dfaf  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18005dfb4  mov     ebx, eax
0x18005dfb6  call    cs:__imp_CloseHandle
0x18005dfbc  mov     eax, ebx
0x18005dfbe  mov     rcx, [rsp+48h+var_10]
0x18005dfc3  xor     rcx, rsp; StackCookie
0x18005dfc6  call    __security_check_cookie
0x18005dfcb  mov     rbx, [rsp+48h+arg_0]
0x18005dfd0  add     rsp, 40h
0x18005dfd4  pop     rdi
0x18005dfd5  retn
```
