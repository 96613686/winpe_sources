# WxGetUserToken(int,void * *)

- ea: `0x18006aba4`
- end: `0x18006ac71`
- name: `?WxGetUserToken@@YAJHPEAPEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18006a9a8`

## callees

- `0x18006aba4`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006abf0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006abf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006abd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006abd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ac34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ac34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ac10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ac10`

## pseudocode

```c
__int64 __fastcall WxGetUserToken(__int64 a1, void **a2)
{
  void *v2; // rcx
  HANDLE CurrentThread; // rax
  signed int v5; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  TokenHandle = 0;
  if ( a2 )
  {
    *a2 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
    {
      v2 = 0;
      *a2 = TokenHandle;
      v5 = 0;
      TokenHandle = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v2 = TokenHandle;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v2 )
  {
    CloseHandle(v2);
    TokenHandle = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006aba4  push    rbx
0x18006aba6  sub     rsp, 40h
0x18006abaa  mov     rax, cs:__security_cookie
0x18006abb1  xor     rax, rsp
0x18006abb4  mov     [rsp+48h+var_18], rax
0x18006abb9  xor     ecx, ecx
0x18006abbb  mov     [rsp+48h+var_24], 0
0x18006abc3  mov     [rsp+48h+TokenHandle], rcx
0x18006abc8  mov     rbx, rdx
0x18006abcb  test    rdx, rdx
0x18006abce  jz      loc_18006AC62
0x18006abd4  mov     [rdx], rcx
0x18006abd7  call    cs:__imp_GetCurrentThread
0x18006abdd  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18006abe2  mov     edx, 2000Eh; DesiredAccess
0x18006abe7  mov     rcx, rax; ThreadHandle
0x18006abea  mov     r8d, 1; OpenAsSelf
0x18006abf0  call    cs:__imp_OpenThreadToken
0x18006abf6  test    eax, eax
0x18006abf8  jz      short loc_18006AC34
0x18006abfa  mov     rax, [rsp+48h+TokenHandle]
0x18006abff  xor     ecx, ecx; hObject
0x18006ac01  mov     [rbx], rax
0x18006ac04  xor     ebx, ebx
0x18006ac06  mov     [rsp+48h+TokenHandle], rcx
0x18006ac0b  test    rcx, rcx
0x18006ac0e  jz      short loc_18006AC1F
0x18006ac10  call    cs:__imp_CloseHandle
0x18006ac16  mov     [rsp+48h+TokenHandle], 0
0x18006ac1f  mov     eax, ebx
0x18006ac21  mov     rcx, [rsp+48h+var_18]
0x18006ac26  xor     rcx, rsp; StackCookie
0x18006ac29  call    __security_check_cookie
0x18006ac2e  add     rsp, 40h
0x18006ac32  pop     rbx
0x18006ac33  retn
0x18006ac34  call    cs:__imp_GetLastError
0x18006ac3a  mov     ebx, eax
0x18006ac3c  test    eax, eax
0x18006ac3e  jle     short loc_18006AC49
0x18006ac40  movzx   ebx, ax
0x18006ac43  or      ebx, 80070000h
0x18006ac49  mov     rcx, [rsp+48h+TokenHandle]
0x18006ac4e  test    ebx, ebx
0x18006ac50  mov     eax, 8000FFFFh
0x18006ac55  mov     [rsp+48h+var_24], 55h ; 'U'
0x18006ac5d  cmovns  ebx, eax
0x18006ac60  jmp     short loc_18006AC0B
0x18006ac62  mov     ebx, 80070057h
0x18006ac67  mov     [rsp+48h+var_24], 47h ; 'G'
0x18006ac6f  jmp     short loc_18006AC0B
```
