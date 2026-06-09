# GetCurrentThreadImpersonationToken

- ea: `0x180033b64`
- end: `0x180033c0d`
- name: `GetCurrentThreadImpersonationToken`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180033af4`
- `0x1800347e0`

## callees

- `0x180033b64`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033ba6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033ba6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033b91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033c05`

## pseudocode

```c
__int64 __fastcall GetCurrentThreadImpersonationToken(_QWORD *a1)
{
  __int64 v1; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // edi
  void *v5; // rax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  v1 = -1;
  TokenHandle = (void *)-1LL;
  *a1 = -1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    v5 = TokenHandle;
    goto LABEL_4;
  }
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    v5 = 0;
LABEL_4:
    *a1 = v5;
    LastError = 0;
    TokenHandle = (void *)-1LL;
    goto LABEL_5;
  }
  v1 = (__int64)TokenHandle;
LABEL_5:
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v1);
  return LastError;
}

```

## disassembly

```asm
0x180033b64  mov     [rsp+arg_8], rbx
0x180033b69  mov     [rsp+arg_10], rsi
0x180033b6e  push    rdi
0x180033b6f  sub     rsp, 30h
0x180033b73  mov     rax, cs:__security_cookie
0x180033b7a  xor     rax, rsp
0x180033b7d  mov     [rsp+38h+var_10], rax
0x180033b82  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180033b86  mov     rsi, rcx
0x180033b89  mov     [rsp+38h+TokenHandle], rbx
0x180033b8e  mov     [rcx], rbx
0x180033b91  call    cs:__imp_GetCurrentThread
0x180033b97  mov     rcx, rax; ThreadHandle
0x180033b9a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180033b9f  lea     edx, [rbx+5]; DesiredAccess
0x180033ba2  lea     r8d, [rbx+2]; OpenAsSelf
0x180033ba6  call    cs:__imp_OpenThreadToken
0x180033bac  test    eax, eax
0x180033bae  jnz     short loc_180033BF4
0x180033bb0  call    cs:__imp_GetLastError
0x180033bb6  mov     edi, eax
0x180033bb8  cmp     eax, 3F0h
0x180033bbd  jnz     short loc_180033BFB
0x180033bbf  xor     eax, eax
0x180033bc1  mov     [rsi], rax
0x180033bc4  xor     edi, edi
0x180033bc6  mov     [rsp+38h+TokenHandle], rbx
0x180033bcb  lea     rax, [rbx-1]
0x180033bcf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033bd3  jbe     short loc_180033C02
0x180033bd5  mov     eax, edi
0x180033bd7  mov     rcx, [rsp+38h+var_10]
0x180033bdc  xor     rcx, rsp; StackCookie
0x180033bdf  call    __security_check_cookie
0x180033be4  mov     rbx, [rsp+38h+arg_8]
0x180033be9  mov     rsi, [rsp+38h+arg_10]
0x180033bee  add     rsp, 30h
0x180033bf2  pop     rdi
0x180033bf3  retn
0x180033bf4  mov     rax, [rsp+38h+TokenHandle]
0x180033bf9  jmp     short loc_180033BC1
0x180033bfb  mov     rbx, [rsp+38h+TokenHandle]
0x180033c00  jmp     short loc_180033BCB
0x180033c02  mov     rcx, rbx; hObject
0x180033c05  call    cs:__imp_CloseHandle
0x180033c0b  jmp     short loc_180033BD5
```
