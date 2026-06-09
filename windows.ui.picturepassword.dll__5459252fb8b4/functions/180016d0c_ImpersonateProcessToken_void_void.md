# _ImpersonateProcessToken(void *,void * *)

- ea: `0x180016d0c`
- end: `0x180016df6`
- name: `?_ImpersonateProcessToken@@YAJPEAXPEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016fac`

## callees

- `0x1800092b8`
- `0x180016d0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016d31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016d31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016d48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016d48`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016d85`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dde`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016d9f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016d9f`

## pseudocode

```c
__int64 __fastcall _ImpersonateProcessToken(HANDLE ProcessHandle, void **a2)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  int v6; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hToken; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v6 = Error;
    if ( Error == -2147023888 )
    {
      TokenHandle = 0;
    }
    else if ( Error < 0 )
    {
      return (unsigned int)v6;
    }
  }
  hToken = 0;
  if ( OpenProcessToken(ProcessHandle, 0xEu, &hToken) || (v6 = ResultFromKnownLastError(), v6 >= 0) )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v6 = 0;
    }
    else
    {
      v6 = ResultFromKnownLastError();
      if ( v6 < 0 )
      {
LABEL_11:
        CloseHandle(hToken);
        goto LABEL_12;
      }
    }
    *a2 = TokenHandle;
    TokenHandle = 0;
    goto LABEL_11;
  }
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016d0c  mov     [rsp+arg_0], rbx
0x180016d11  mov     [rsp+arg_18], rsi
0x180016d16  push    rdi
0x180016d17  sub     rsp, 20h
0x180016d1b  mov     rdi, rdx
0x180016d1e  mov     qword ptr [rdx], 0
0x180016d25  mov     rsi, rcx
0x180016d28  mov     [rsp+28h+TokenHandle], 0
0x180016d31  call    cs:__imp_GetCurrentThread
0x180016d37  mov     edx, 0Eh; DesiredAccess
0x180016d3c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180016d41  mov     rcx, rax; ThreadHandle
0x180016d44  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180016d48  call    cs:__imp_OpenThreadToken
0x180016d4e  test    eax, eax
0x180016d50  jnz     short loc_180016D6F
0x180016d52  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016d57  mov     ebx, eax
0x180016d59  cmp     eax, 800703F0h
0x180016d5e  jnz     short loc_180016D6B
0x180016d60  mov     [rsp+28h+TokenHandle], 0
0x180016d69  jmp     short loc_180016D6F
0x180016d6b  test    eax, eax
0x180016d6d  js      short loc_180016DE4
0x180016d6f  lea     r8, [rsp+28h+hToken]; TokenHandle
0x180016d74  mov     [rsp+28h+hToken], 0
0x180016d7d  mov     edx, 0Eh; DesiredAccess
0x180016d82  mov     rcx, rsi; ProcessHandle
0x180016d85  call    cs:__imp_OpenProcessToken
0x180016d8b  test    eax, eax
0x180016d8d  jnz     short loc_180016D9A
0x180016d8f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016d94  mov     ebx, eax
0x180016d96  test    eax, eax
0x180016d98  js      short loc_180016DD4
0x180016d9a  mov     rcx, [rsp+28h+hToken]; hToken
0x180016d9f  call    cs:__imp_ImpersonateLoggedOnUser
0x180016da5  test    eax, eax
0x180016da7  jz      short loc_180016DAD
0x180016da9  xor     ebx, ebx
0x180016dab  jmp     short loc_180016DB8
0x180016dad  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016db2  mov     ebx, eax
0x180016db4  test    eax, eax
0x180016db6  js      short loc_180016DC9
0x180016db8  mov     rax, [rsp+28h+TokenHandle]
0x180016dbd  mov     [rdi], rax
0x180016dc0  mov     [rsp+28h+TokenHandle], 0
0x180016dc9  mov     rcx, [rsp+28h+hToken]; hObject
0x180016dce  call    cs:__imp_CloseHandle
0x180016dd4  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180016dd9  test    rcx, rcx
0x180016ddc  jz      short loc_180016DE4
0x180016dde  call    cs:__imp_CloseHandle
0x180016de4  mov     rsi, [rsp+28h+arg_18]
0x180016de9  mov     eax, ebx
0x180016deb  mov     rbx, [rsp+28h+arg_0]
0x180016df0  add     rsp, 20h
0x180016df4  pop     rdi
0x180016df5  retn
```
