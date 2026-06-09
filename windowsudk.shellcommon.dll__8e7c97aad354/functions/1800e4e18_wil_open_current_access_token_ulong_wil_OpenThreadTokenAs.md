# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x1800e4e18`
- end: `0x1800e4ec0`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800e48ac`

## callees

- `0x1800e488c`
- `0x1800e4e18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4e7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4e7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e4e62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e4e62`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e4e75`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e4e75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e4e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e4e2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e4e3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e4e3f`

## string_xrefs

- `0x1800e4e9a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
    goto LABEL_11;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
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
0x1800e4e18  push    rbx
0x1800e4e1a  sub     rsp, 30h
0x1800e4e1e  mov     rbx, rcx
0x1800e4e21  mov     [rsp+38h+TokenHandle], 0
0x1800e4e2a  call    cs:__imp_GetCurrentThread
0x1800e4e30  xor     r8d, r8d; OpenAsSelf
0x1800e4e33  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800e4e38  mov     rcx, rax; ThreadHandle
0x1800e4e3b  lea     edx, [r8+0Ch]; DesiredAccess
0x1800e4e3f  call    cs:__imp_OpenThreadToken
0x1800e4e45  test    eax, eax
0x1800e4e47  jnz     short loc_1800E4EAF
0x1800e4e49  call    cs:__imp_GetLastError
0x1800e4e4f  test    eax, eax
0x1800e4e51  jle     short loc_1800E4E5B
0x1800e4e53  movzx   eax, ax
0x1800e4e56  or      eax, 80070000h
0x1800e4e5b  cmp     eax, 800703F0h
0x1800e4e60  jnz     short loc_1800E4E91
0x1800e4e62  call    cs:__imp_GetCurrentProcess
0x1800e4e68  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800e4e6d  mov     edx, 0Ch; DesiredAccess
0x1800e4e72  mov     rcx, rax; ProcessHandle
0x1800e4e75  call    cs:__imp_OpenProcessToken
0x1800e4e7b  test    eax, eax
0x1800e4e7d  jnz     short loc_1800E4EAF
0x1800e4e7f  call    cs:__imp_GetLastError
0x1800e4e85  test    eax, eax
0x1800e4e87  jle     short loc_1800E4E93
0x1800e4e89  movzx   eax, ax
0x1800e4e8c  or      eax, 80070000h
0x1800e4e91  test    eax, eax
0x1800e4e93  jns     short loc_1800E4EAF
0x1800e4e95  mov     rcx, [rsp+38h]; this
0x1800e4e9a  lea     r8, aOnecoreInterna_21; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800e4ea1  mov     r9d, eax; char *
0x1800e4ea4  mov     edx, 0E1h; void *
0x1800e4ea9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e4eaf  mov     rax, [rsp+38h+TokenHandle]
0x1800e4eb4  mov     [rbx], rax
0x1800e4eb7  mov     rax, rbx
0x1800e4eba  add     rsp, 30h
0x1800e4ebe  pop     rbx
0x1800e4ebf  retn
```
