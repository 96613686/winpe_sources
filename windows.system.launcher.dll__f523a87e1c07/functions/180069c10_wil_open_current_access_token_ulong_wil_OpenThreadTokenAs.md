# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x180069c10`
- end: `0x180069cb8`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180069b08`
- `0x180069b90`

## callees

- `0x18000f194`
- `0x180069c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069c22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069c22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069c37`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069c5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069c5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180069c6d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180069c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c77`

## string_xrefs

- `0x180069c92`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void **__fastcall wil::open_current_access_token(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  bool v5; // sf
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_11;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_11;
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v5 = LastError < 0;
LABEL_9:
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)(unsigned int)LastError,
      v7);
LABEL_11:
  *a1 = TokenHandle;
  return a1;
}

```

## disassembly

```asm
0x180069c10  push    rbx
0x180069c12  sub     rsp, 30h
0x180069c16  mov     rbx, rcx
0x180069c19  mov     [rsp+38h+TokenHandle], 0
0x180069c22  call    cs:__imp_GetCurrentThread
0x180069c28  xor     r8d, r8d; OpenAsSelf
0x180069c2b  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180069c30  mov     rcx, rax; ThreadHandle
0x180069c33  lea     edx, [r8+8]; DesiredAccess
0x180069c37  call    cs:__imp_OpenThreadToken
0x180069c3d  test    eax, eax
0x180069c3f  jnz     short loc_180069CA7
0x180069c41  call    cs:__imp_GetLastError
0x180069c47  test    eax, eax
0x180069c49  jle     short loc_180069C53
0x180069c4b  movzx   eax, ax
0x180069c4e  or      eax, 80070000h
0x180069c53  cmp     eax, 800703F0h
0x180069c58  jnz     short loc_180069C89
0x180069c5a  call    cs:__imp_GetCurrentProcess
0x180069c60  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180069c65  mov     edx, 8; DesiredAccess
0x180069c6a  mov     rcx, rax; ProcessHandle
0x180069c6d  call    cs:__imp_OpenProcessToken
0x180069c73  test    eax, eax
0x180069c75  jnz     short loc_180069CA7
0x180069c77  call    cs:__imp_GetLastError
0x180069c7d  test    eax, eax
0x180069c7f  jle     short loc_180069C8B
0x180069c81  movzx   eax, ax
0x180069c84  or      eax, 80070000h
0x180069c89  test    eax, eax
0x180069c8b  jns     short loc_180069CA7
0x180069c8d  mov     rcx, [rsp+38h]; this
0x180069c92  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180069c99  mov     r9d, eax; char *
0x180069c9c  mov     edx, 0E1h; void *
0x180069ca1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069ca7  mov     rax, [rsp+38h+TokenHandle]
0x180069cac  mov     [rbx], rax
0x180069caf  mov     rax, rbx
0x180069cb2  add     rsp, 30h
0x180069cb6  pop     rbx
0x180069cb7  retn
```
