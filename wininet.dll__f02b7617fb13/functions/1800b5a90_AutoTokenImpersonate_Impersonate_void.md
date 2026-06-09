# AutoTokenImpersonate::Impersonate(void *)

- ea: `0x1800b5a90`
- end: `0x1800b5bd5`
- name: `?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z`
- size: `325`
- prototype: `int(AutoTokenImpersonate *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b58e4`
- `0x18011f850`

## callees

- `0x1800701d0`
- `0x1800b5a90`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5ae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b5ac0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b5ac0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b5ad9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b5ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5b05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5b05`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b5bc9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b5bc9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800b5b31`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800b5b31`

## pseudocode

```c
__int64 __fastcall AutoTokenImpersonate::Impersonate(AutoTokenImpersonate *this, void *a2)
{
  HANDLE CurrentThread; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  signed int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  int LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    if ( !a2 )
    {
      if ( !RevertToSelf() )
      {
        LastError = WxGetLastError(v15, v14);
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_12;
      }
LABEL_15:
      *(_QWORD *)this = TokenHandle;
      TokenHandle = 0;
      *((_DWORD *)this + 2) = 1;
      goto LABEL_4;
    }
LABEL_9:
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      v11 = WxGetLastError(v10, v9);
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
LABEL_12:
      if ( v7 >= 0 )
        v7 = -2147418113;
      goto LABEL_5;
    }
    goto LABEL_15;
  }
  if ( GetLastError() == 1008 )
  {
    if ( !a2 )
    {
LABEL_4:
      v7 = 0;
      goto LABEL_5;
    }
    goto LABEL_9;
  }
  v12 = WxGetLastError(v6, v5);
  v7 = v12;
  if ( v12 > 0 )
    v7 = (unsigned __int16)v12 | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2147418113;
LABEL_5:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b5a90  mov     [rsp+arg_10], rbx
0x1800b5a95  push    rdi
0x1800b5a96  sub     rsp, 40h
0x1800b5a9a  mov     rax, cs:__security_cookie
0x1800b5aa1  xor     rax, rsp
0x1800b5aa4  mov     [rsp+48h+var_18], rax
0x1800b5aa9  mov     rbx, rdx
0x1800b5aac  mov     [rsp+48h+var_24], 0
0x1800b5ab4  mov     rdi, rcx
0x1800b5ab7  mov     [rsp+48h+TokenHandle], 0
0x1800b5ac0  call    cs:__imp_GetCurrentThread
0x1800b5ac6  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800b5acb  mov     edx, 2000Eh; DesiredAccess
0x1800b5ad0  mov     rcx, rax; ThreadHandle
0x1800b5ad3  mov     r8d, 1; OpenAsSelf
0x1800b5ad9  call    cs:__imp_OpenThreadToken
0x1800b5adf  test    eax, eax
0x1800b5ae1  jnz     short loc_1800B5B25
0x1800b5ae3  call    cs:__imp_GetLastError
0x1800b5ae9  cmp     eax, 3F0h
0x1800b5aee  jnz     loc_1800B5B80
0x1800b5af4  test    rbx, rbx
0x1800b5af7  jnz     short loc_1800B5B2E
0x1800b5af9  xor     ebx, ebx
0x1800b5afb  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800b5b00  test    rcx, rcx
0x1800b5b03  jz      short loc_1800B5B0B
0x1800b5b05  call    cs:__imp_CloseHandle
0x1800b5b0b  mov     eax, ebx
0x1800b5b0d  mov     rcx, [rsp+48h+var_18]
0x1800b5b12  xor     rcx, rsp; StackCookie
0x1800b5b15  call    __security_check_cookie
0x1800b5b1a  mov     rbx, [rsp+48h+arg_10]
0x1800b5b1f  add     rsp, 40h
0x1800b5b23  pop     rdi
0x1800b5b24  retn
0x1800b5b25  test    rbx, rbx
0x1800b5b28  jz      loc_1800B5BC9
0x1800b5b2e  mov     rcx, rbx; hToken
0x1800b5b31  call    cs:__imp_ImpersonateLoggedOnUser
0x1800b5b37  test    eax, eax
0x1800b5b39  jnz     short loc_1800B5B63
0x1800b5b3b  call    WxGetLastError
0x1800b5b40  mov     ebx, eax
0x1800b5b42  test    eax, eax
0x1800b5b44  jle     short loc_1800B5B4F
0x1800b5b46  movzx   ebx, ax
0x1800b5b49  or      ebx, 80070000h
0x1800b5b4f  mov     [rsp+48h+var_24], 193h
0x1800b5b57  test    ebx, ebx
0x1800b5b59  mov     eax, 8000FFFFh
0x1800b5b5e  cmovns  ebx, eax
0x1800b5b61  jmp     short loc_1800B5AFB
0x1800b5b63  mov     rcx, [rsp+48h+TokenHandle]
0x1800b5b68  mov     [rdi], rcx
0x1800b5b6b  mov     [rsp+48h+TokenHandle], 0
0x1800b5b74  mov     dword ptr [rdi+8], 1
0x1800b5b7b  jmp     loc_1800B5AF9
0x1800b5b80  call    WxGetLastError
0x1800b5b85  mov     ebx, eax
0x1800b5b87  test    eax, eax
0x1800b5b89  jle     short loc_1800B5B94
0x1800b5b8b  movzx   ebx, ax
0x1800b5b8e  or      ebx, 80070000h
0x1800b5b94  test    ebx, ebx
0x1800b5b96  mov     [rsp+48h+var_24], 184h
0x1800b5b9e  mov     eax, 8000FFFFh
0x1800b5ba3  cmovns  ebx, eax
0x1800b5ba6  jmp     loc_1800B5AFB
0x1800b5bab  call    WxGetLastError
0x1800b5bb0  mov     ebx, eax
0x1800b5bb2  test    eax, eax
0x1800b5bb4  jle     short loc_1800B5BBF
0x1800b5bb6  movzx   ebx, ax
0x1800b5bb9  or      ebx, 80070000h
0x1800b5bbf  mov     [rsp+48h+var_24], 197h
0x1800b5bc7  jmp     short loc_1800B5B57
0x1800b5bc9  call    cs:__imp_RevertToSelf
0x1800b5bcf  test    eax, eax
0x1800b5bd1  jnz     short loc_1800B5B63
0x1800b5bd3  jmp     short loc_1800B5BAB
```
