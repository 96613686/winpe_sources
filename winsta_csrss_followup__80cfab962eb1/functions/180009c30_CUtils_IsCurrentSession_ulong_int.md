# CUtils::IsCurrentSession(ulong,int *)

- ea: `0x180009c30`
- end: `0x180009de6`
- name: `?IsCurrentSession@CUtils@@SAJKPEAH@Z`
- size: `438`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800096c0`
- `0x18000a670`
- `0x18000a9e0`

## callees

- `0x180005b40`
- `0x180009c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009da5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009ca8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009ca8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009c81`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009c81`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009cc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009cc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009c62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d1b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009cf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009cf4`

## string_xrefs

- `0x180009d5e`: `GetTokenInformation failed: 0x%x`
- `0x180009d8f`: `OpenProcessToken failed: 0x%x`
- `0x180009dc3`: `OpenThreadToken failed: 0x%x`

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
0x180009c30  push    rbx
0x180009c32  push    rsi
0x180009c33  push    rdi
0x180009c34  sub     rsp, 30h
0x180009c38  xor     esi, esi
0x180009c3a  mov     [rsp+48h+TokenInformation], 0FFFFFFFFh
0x180009c42  mov     [rsp+48h+TokenHandle], rsi
0x180009c47  mov     rdi, rdx
0x180009c4a  mov     [rsp+48h+arg_10], esi
0x180009c4e  mov     ebx, ecx
0x180009c50  test    rdx, rdx
0x180009c53  jz      loc_180009D32
0x180009c59  cmp     ecx, 0FFFFFFFFh
0x180009c5c  jz      loc_180009DD9
0x180009c62  call    cs:__imp_GetCurrentThread
0x180009c69  nop     dword ptr [rax+rax+00h]
0x180009c6e  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180009c73  mov     edx, 8; DesiredAccess
0x180009c78  mov     rcx, rax; ThreadHandle
0x180009c7b  mov     r8d, 1; OpenAsSelf
0x180009c81  call    cs:__imp_OpenThreadToken
0x180009c88  nop     dword ptr [rax+rax+00h]
0x180009c8d  test    eax, eax
0x180009c8f  jnz     short loc_180009CD5
0x180009c91  call    cs:__imp_GetLastError
0x180009c98  nop     dword ptr [rax+rax+00h]
0x180009c9d  cmp     eax, 3F0h
0x180009ca2  jnz     loc_180009DA5
0x180009ca8  call    cs:__imp_GetCurrentProcess
0x180009caf  nop     dword ptr [rax+rax+00h]
0x180009cb4  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180009cb9  mov     edx, 8; DesiredAccess
0x180009cbe  mov     rcx, rax; ProcessHandle
0x180009cc1  call    cs:__imp_OpenProcessToken
0x180009cc8  nop     dword ptr [rax+rax+00h]
0x180009ccd  test    eax, eax
0x180009ccf  jz      loc_180009D71
0x180009cd5  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180009cda  lea     rax, [rsp+48h+arg_10]
0x180009cdf  mov     r9d, 4; TokenInformationLength
0x180009ce5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180009cea  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180009cef  mov     edx, 0Ch; TokenInformationClass
0x180009cf4  call    cs:__imp_GetTokenInformation
0x180009cfb  nop     dword ptr [rax+rax+00h]
0x180009d00  test    eax, eax
0x180009d02  jz      short loc_180009D40
0x180009d04  cmp     [rsp+48h+TokenInformation], ebx
0x180009d08  mov     eax, esi
0x180009d0a  mov     ebx, esi
0x180009d0c  setz    al
0x180009d0f  mov     [rdi], eax
0x180009d11  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180009d16  test    rcx, rcx
0x180009d19  jz      short loc_180009D27
0x180009d1b  call    cs:__imp_CloseHandle
0x180009d22  nop     dword ptr [rax+rax+00h]
0x180009d27  mov     eax, ebx
0x180009d29  add     rsp, 30h
0x180009d2d  pop     rdi
0x180009d2e  pop     rsi
0x180009d2f  pop     rbx
0x180009d30  retn
0x180009d32  mov     eax, 80070057h
0x180009d37  add     rsp, 30h
0x180009d3b  pop     rdi
0x180009d3c  pop     rsi
0x180009d3d  pop     rbx
0x180009d3e  retn
0x180009d40  call    cs:__imp_GetLastError
0x180009d47  nop     dword ptr [rax+rax+00h]
0x180009d4c  mov     ebx, eax
0x180009d4e  test    eax, eax
0x180009d50  jle     short loc_180009D5B
0x180009d52  movzx   ebx, ax
0x180009d55  or      ebx, 80070000h
0x180009d5b  mov     r8d, ebx
0x180009d5e  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x180009d65  mov     ecx, 8; int
0x180009d6a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009d6f  jmp     short loc_180009D11
0x180009d71  call    cs:__imp_GetLastError
0x180009d78  nop     dword ptr [rax+rax+00h]
0x180009d7d  mov     ebx, eax
0x180009d7f  test    eax, eax
0x180009d81  jle     short loc_180009D8C
0x180009d83  movzx   ebx, ax
0x180009d86  or      ebx, 80070000h
0x180009d8c  mov     r8d, ebx
0x180009d8f  lea     rdx, aOpenprocesstok_0; "OpenProcessToken failed: 0x%x"
0x180009d96  mov     ecx, 8; int
0x180009d9b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009da0  jmp     loc_180009D11
0x180009da5  call    cs:__imp_GetLastError
0x180009dac  nop     dword ptr [rax+rax+00h]
0x180009db1  mov     ebx, eax
0x180009db3  test    eax, eax
0x180009db5  jle     short loc_180009DC0
0x180009db7  movzx   ebx, ax
0x180009dba  or      ebx, 80070000h
0x180009dc0  mov     r8d, ebx
0x180009dc3  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x"
0x180009dca  mov     ecx, 8; int
0x180009dcf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009dd4  jmp     loc_180009D11
0x180009dd9  mov     dword ptr [rdx], 1
0x180009ddf  mov     eax, esi
0x180009de1  jmp     loc_180009D29
```
