# CUtils::IsCurrentSession(ulong,int *)

- ea: `0x180004570`
- end: `0x1800046e5`
- name: `?IsCurrentSession@CUtils@@SAJKPEAH@Z`
- size: `373`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003e30`
- `0x180004450`

## callees

- `0x180004570`
- `0x180007890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800045d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800045d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800045bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800045bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800045e9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800045e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800045a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800045a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004637`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004616`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004616`

## string_xrefs

- `0x18000466c`: `GetTokenInformation failed: 0x%x`
- `0x180004697`: `OpenProcessToken failed: 0x%x`
- `0x1800046c2`: `OpenThreadToken failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CUtils::IsCurrentSession(int a1, int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  bool v6; // zf
  unsigned int v7; // ebx
  signed int v9; // eax
  signed int v10; // eax
  signed int LastError; // eax
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  TokenInformation = -1;
  TokenHandle = 0;
  ReturnLength = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( a1 == -1 )
  {
    *a2 = 1;
    return 0;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_24;
  if ( GetLastError() != 1008 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x", v7);
    goto LABEL_8;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_24:
    if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    {
      v6 = TokenInformation == a1;
      v7 = 0;
      *a2 = v6;
    }
    else
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x", v7);
    }
  }
  else
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x", v7);
  }
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x180004570  push    rbx
0x180004572  push    rsi
0x180004573  push    rdi
0x180004574  sub     rsp, 30h
0x180004578  xor     esi, esi
0x18000457a  mov     [rsp+48h+TokenInformation], 0FFFFFFFFh
0x180004582  mov     [rsp+48h+TokenHandle], rsi
0x180004587  mov     rdi, rdx
0x18000458a  mov     [rsp+48h+arg_10], esi
0x18000458e  mov     ebx, ecx
0x180004590  test    rdx, rdx
0x180004593  jz      loc_180004647
0x180004599  cmp     ecx, 0FFFFFFFFh
0x18000459c  jz      loc_1800046D8
0x1800045a2  call    cs:__imp_GetCurrentThread
0x1800045a8  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800045ad  mov     edx, 8; DesiredAccess
0x1800045b2  mov     rcx, rax; ThreadHandle
0x1800045b5  mov     r8d, 1; OpenAsSelf
0x1800045bb  call    cs:__imp_OpenThreadToken
0x1800045c1  test    eax, eax
0x1800045c3  jnz     short loc_1800045F7
0x1800045c5  call    cs:__imp_GetLastError
0x1800045cb  cmp     eax, 3F0h
0x1800045d0  jnz     loc_1800046AA
0x1800045d6  call    cs:__imp_GetCurrentProcess
0x1800045dc  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800045e1  mov     edx, 8; DesiredAccess
0x1800045e6  mov     rcx, rax; ProcessHandle
0x1800045e9  call    cs:__imp_OpenProcessToken
0x1800045ef  test    eax, eax
0x1800045f1  jz      loc_18000467F
0x1800045f7  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800045fc  lea     rax, [rsp+48h+arg_10]
0x180004601  mov     r9d, 4; TokenInformationLength
0x180004607  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000460c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180004611  mov     edx, 0Ch; TokenInformationClass
0x180004616  call    cs:__imp_GetTokenInformation
0x18000461c  test    eax, eax
0x18000461e  jz      short loc_180004654
0x180004620  cmp     [rsp+48h+TokenInformation], ebx
0x180004624  mov     eax, esi
0x180004626  mov     ebx, esi
0x180004628  setz    al
0x18000462b  mov     [rdi], eax
0x18000462d  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180004632  test    rcx, rcx
0x180004635  jz      short loc_18000463D
0x180004637  call    cs:__imp_CloseHandle
0x18000463d  mov     eax, ebx
0x18000463f  add     rsp, 30h
0x180004643  pop     rdi
0x180004644  pop     rsi
0x180004645  pop     rbx
0x180004646  retn
0x180004647  mov     eax, 80070057h
0x18000464c  add     rsp, 30h
0x180004650  pop     rdi
0x180004651  pop     rsi
0x180004652  pop     rbx
0x180004653  retn
0x180004654  call    cs:__imp_GetLastError
0x18000465a  mov     ebx, eax
0x18000465c  test    eax, eax
0x18000465e  jle     short loc_180004669
0x180004660  movzx   ebx, ax
0x180004663  or      ebx, 80070000h
0x180004669  mov     r8d, ebx
0x18000466c  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x180004673  mov     ecx, 8; int
0x180004678  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000467d  jmp     short loc_18000462D
0x18000467f  call    cs:__imp_GetLastError
0x180004685  mov     ebx, eax
0x180004687  test    eax, eax
0x180004689  jle     short loc_180004694
0x18000468b  movzx   ebx, ax
0x18000468e  or      ebx, 80070000h
0x180004694  mov     r8d, ebx
0x180004697  lea     rdx, aOpenprocesstok_0; "OpenProcessToken failed: 0x%x"
0x18000469e  mov     ecx, 8; int
0x1800046a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800046a8  jmp     short loc_18000462D
0x1800046aa  call    cs:__imp_GetLastError
0x1800046b0  mov     ebx, eax
0x1800046b2  test    eax, eax
0x1800046b4  jle     short loc_1800046BF
0x1800046b6  movzx   ebx, ax
0x1800046b9  or      ebx, 80070000h
0x1800046bf  mov     r8d, ebx
0x1800046c2  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x"
0x1800046c9  mov     ecx, 8; int
0x1800046ce  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800046d3  jmp     loc_18000462D
0x1800046d8  mov     dword ptr [rdx], 1
0x1800046de  mov     eax, esi
0x1800046e0  jmp     loc_18000463F
```
