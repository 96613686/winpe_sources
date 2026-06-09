# ImpersonateToken(void *,void * *)

- ea: `0x18006df88`
- end: `0x18006e071`
- name: `?ImpersonateToken@@YAKPEAXPEAPEAX@Z`
- size: `233`
- prototype: `unsigned int __fastcall(HANDLE Token, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001db1c`
- `0x180027880`
- `0x18006d23c`
- `0x18006d3cc`

## callees

- `0x18006df88`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dfd0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dfd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dfbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dfbb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006e008`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006e008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dfdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dfdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e05c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e069`

## pseudocode

```c
__int64 __fastcall ImpersonateToken(HANDLE Token, void **a2)
{
  __int64 v2; // rsi
  HANDLE CurrentThread; // rax
  __int64 v6; // rbx
  DWORD LastError; // edi
  void *TokenHandle; // [rsp+20h] [rbp-28h] BYREF

  v2 = -1;
  *a2 = (void *)-1LL;
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    v6 = (__int64)TokenHandle;
    goto LABEL_4;
  }
  v6 = -1;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    v6 = 0;
LABEL_4:
    TokenHandle = (void *)-1LL;
    LastError = 0;
    goto LABEL_5;
  }
  v2 = (__int64)TokenHandle;
LABEL_5:
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v2);
  if ( !LastError )
  {
    if ( SetThreadToken(0, Token) )
    {
      *a2 = (void *)v6;
      return LastError;
    }
    LastError = GetLastError();
  }
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  return LastError;
}

```

## disassembly

```asm
0x18006df88  mov     [rsp+arg_10], rbx
0x18006df8d  mov     [rsp+arg_18], rbp
0x18006df92  push    rsi
0x18006df93  push    rdi
0x18006df94  push    r14
0x18006df96  sub     rsp, 30h
0x18006df9a  mov     rax, cs:__security_cookie
0x18006dfa1  xor     rax, rsp
0x18006dfa4  mov     [rsp+48h+var_20], rax
0x18006dfa9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006dfad  mov     r14, rdx
0x18006dfb0  mov     [rdx], rsi
0x18006dfb3  mov     rbp, rcx
0x18006dfb6  mov     [rsp+48h+TokenHandle], rsi
0x18006dfbb  call    cs:__imp_GetCurrentThread
0x18006dfc1  mov     rcx, rax; ThreadHandle
0x18006dfc4  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18006dfc9  lea     edx, [rsi+5]; DesiredAccess
0x18006dfcc  lea     r8d, [rsi+2]; OpenAsSelf
0x18006dfd0  call    cs:__imp_OpenThreadToken
0x18006dfd6  test    eax, eax
0x18006dfd8  jnz     short loc_18006E043
0x18006dfda  mov     rbx, rsi
0x18006dfdd  call    cs:__imp_GetLastError
0x18006dfe3  mov     edi, eax
0x18006dfe5  cmp     eax, 3F0h
0x18006dfea  jnz     short loc_18006E04A
0x18006dfec  xor     ebx, ebx
0x18006dfee  mov     [rsp+48h+TokenHandle], rsi
0x18006dff3  xor     edi, edi
0x18006dff5  lea     rax, [rsi-1]
0x18006dff9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006dffd  jbe     short loc_18006E051
0x18006dfff  test    edi, edi
0x18006e001  jnz     short loc_18006E017
0x18006e003  mov     rdx, rbp; Token
0x18006e006  xor     ecx, ecx; Thread
0x18006e008  call    cs:__imp_SetThreadToken
0x18006e00e  test    eax, eax
0x18006e010  jz      short loc_18006E05C
0x18006e012  mov     [r14], rbx
0x18006e015  jmp     short loc_18006E021
0x18006e017  lea     rax, [rbx-1]
0x18006e01b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006e01f  jbe     short loc_18006E066
0x18006e021  mov     eax, edi
0x18006e023  mov     rcx, [rsp+48h+var_20]
0x18006e028  xor     rcx, rsp; StackCookie
0x18006e02b  call    __security_check_cookie
0x18006e030  mov     rbx, [rsp+48h+arg_10]
0x18006e035  mov     rbp, [rsp+48h+arg_18]
0x18006e03a  add     rsp, 30h
0x18006e03e  pop     r14
0x18006e040  pop     rdi
0x18006e041  pop     rsi
0x18006e042  retn
0x18006e043  mov     rbx, [rsp+48h+TokenHandle]
0x18006e048  jmp     short loc_18006DFEE
0x18006e04a  mov     rsi, [rsp+48h+TokenHandle]
0x18006e04f  jmp     short loc_18006DFF5
0x18006e051  mov     rcx, rsi; hObject
0x18006e054  call    cs:__imp_CloseHandle
0x18006e05a  jmp     short loc_18006DFFF
0x18006e05c  call    cs:__imp_GetLastError
0x18006e062  mov     edi, eax
0x18006e064  jmp     short loc_18006E017
0x18006e066  mov     rcx, rbx; hObject
0x18006e069  call    cs:__imp_CloseHandle
0x18006e06f  jmp     short loc_18006E021
```
