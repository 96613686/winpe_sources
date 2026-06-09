# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800f9eb8`
- end: `0x1800fa067`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `431`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f9e48`
- `0x1804e46b4`
- `0x1805141b8`

## callees

- `0x1800208d8`
- `0x1800aadec`
- `0x1800f9eb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f9f14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f9f14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9fb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9fb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa05a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f9f58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f9f58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f9f86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f9f86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f9ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f9fd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f9ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f9fd7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f9f95`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f9f95`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f9ef9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f9fec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f9ef9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f9fec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f9f3e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800fa04c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f9f3e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800fa04c`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(__int64 a1, DWORD a2, int a3, _QWORD *a4)
{
  HANDLE CurrentThread; // rax
  void *v7; // rsi
  void *v8; // rdi
  signed int v9; // ebx
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v12; // rax
  signed int LastError; // eax
  void *v14; // rcx
  int v15; // eax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a2;
  *a4 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    result = ResultFromKnownLastError();
    if ( (int)result < 0 )
    {
      if ( a3 && (_DWORD)result == -2147024891 )
      {
        v12 = GetCurrentThread();
        if ( OpenThreadToken(v12, 8u, 1, &TokenHandle) )
          goto LABEL_2;
        result = ResultFromKnownLastError();
      }
      if ( (_DWORD)result == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
          goto LABEL_2;
        result = ResultFromKnownLastError();
      }
      if ( (int)result < 0 )
        return result;
    }
  }
LABEL_2:
  v7 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v8 = TokenInformation;
  if ( !TokenInformation )
  {
    v9 = -2147024882;
    goto LABEL_5;
  }
  v9 = 0;
  if ( !GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v8);
      v15 = CTLocalAllocPolicy::Alloc(v14, 0x40u, TokenInformationLength, &TokenInformation);
      v8 = TokenInformation;
      v9 = v15;
      if ( v15 < 0 )
        goto LABEL_17;
      if ( GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_4;
      LastError = GetLastError();
      v9 = LastError;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_4;
LABEL_17:
    LocalFree(v8);
    goto LABEL_5;
  }
LABEL_4:
  *a4 = v8;
LABEL_5:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800f9eb8  mov     [rsp-28h+TokenInformationLength], edx
0x1800f9ebc  mov     [rsp-28h+TokenHandle], rcx
0x1800f9ec1  push    rbp
0x1800f9ec2  push    rbx
0x1800f9ec3  push    rsi
0x1800f9ec4  push    rdi
0x1800f9ec5  push    r14
0x1800f9ec7  mov     rbp, rsp
0x1800f9eca  sub     rsp, 30h
0x1800f9ece  mov     r14, r9
0x1800f9ed1  mov     qword ptr [r9], 0
0x1800f9ed8  mov     ebx, r8d
0x1800f9edb  mov     [rbp+TokenHandle], 0
0x1800f9ee3  call    cs:__imp_GetCurrentThread
0x1800f9ee9  xor     r8d, r8d; OpenAsSelf
0x1800f9eec  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f9ef0  mov     rcx, rax; ThreadHandle
0x1800f9ef3  lea     edi, [r8+8]
0x1800f9ef7  mov     edx, edi; DesiredAccess
0x1800f9ef9  call    cs:__imp_OpenThreadToken
0x1800f9eff  test    eax, eax
0x1800f9f01  jz      short loc_1800F9F72
0x1800f9f03  mov     rsi, [rbp+TokenHandle]
0x1800f9f07  mov     edx, 800h; uBytes
0x1800f9f0c  mov     ecx, 40h ; '@'; uFlags
0x1800f9f11  mov     [rbp+TokenInformationLength], edx
0x1800f9f14  call    cs:__imp_LocalAlloc
0x1800f9f1a  mov     [rbp+TokenInformation], rax
0x1800f9f1e  mov     rdi, rax
0x1800f9f21  test    rax, rax
0x1800f9f24  jz      short loc_1800F9F6B
0x1800f9f26  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800f9f2a  lea     rax, [rbp+TokenInformationLength]
0x1800f9f2e  xor     ebx, ebx
0x1800f9f30  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800f9f35  mov     r8, rdi; TokenInformation
0x1800f9f38  mov     rcx, rsi; TokenHandle
0x1800f9f3b  lea     edx, [rbx+1]; TokenInformationClass
0x1800f9f3e  call    cs:__imp_GetTokenInformation
0x1800f9f44  test    eax, eax
0x1800f9f46  jz      loc_1800FA004
0x1800f9f4c  mov     [r14], rdi
0x1800f9f4f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f9f53  test    rcx, rcx
0x1800f9f56  jz      short loc_1800F9F5E
0x1800f9f58  call    cs:__imp_CloseHandle
0x1800f9f5e  mov     eax, ebx
0x1800f9f60  add     rsp, 30h
0x1800f9f64  pop     r14
0x1800f9f66  pop     rdi
0x1800f9f67  pop     rsi
0x1800f9f68  pop     rbx
0x1800f9f69  pop     rbp
0x1800f9f6a  retn
0x1800f9f6b  mov     ebx, 8007000Eh
0x1800f9f70  jmp     short loc_1800F9F4F
0x1800f9f72  call    ResultFromKnownLastError
0x1800f9f77  test    eax, eax
0x1800f9f79  jns     short loc_1800F9F03
0x1800f9f7b  test    ebx, ebx
0x1800f9f7d  jnz     short loc_1800F9FD0
0x1800f9f7f  cmp     eax, 800703F0h
0x1800f9f84  jnz     short loc_1800F9FA8
0x1800f9f86  call    cs:__imp_GetCurrentProcess
0x1800f9f8c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800f9f90  mov     edx, edi; DesiredAccess
0x1800f9f92  mov     rcx, rax; ProcessHandle
0x1800f9f95  call    cs:__imp_OpenProcessToken
0x1800f9f9b  test    eax, eax
0x1800f9f9d  jnz     loc_1800F9F03
0x1800f9fa3  call    ResultFromKnownLastError
0x1800f9fa8  test    eax, eax
0x1800f9faa  jns     loc_1800F9F03
0x1800f9fb0  jmp     short loc_1800F9F60
0x1800f9fb2  test    ebx, ebx
0x1800f9fb4  jns     short loc_1800F9F4C
0x1800f9fb6  mov     rcx, rdi; hMem
0x1800f9fb9  call    cs:__imp_LocalFree
0x1800f9fbf  jmp     short loc_1800F9F4F
0x1800f9fc1  test    eax, eax
0x1800f9fc3  jle     short loc_1800F9FB2
0x1800f9fc5  movzx   ebx, ax
0x1800f9fc8  or      ebx, 80070000h
0x1800f9fce  jmp     short loc_1800F9FB2
0x1800f9fd0  cmp     eax, 80070005h
0x1800f9fd5  jnz     short loc_1800F9F7F
0x1800f9fd7  call    cs:__imp_GetCurrentThread
0x1800f9fdd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f9fe1  mov     r8d, 1; OpenAsSelf
0x1800f9fe7  mov     rcx, rax; ThreadHandle
0x1800f9fea  mov     edx, edi; DesiredAccess
0x1800f9fec  call    cs:__imp_OpenThreadToken
0x1800f9ff2  test    eax, eax
0x1800f9ff4  jnz     loc_1800F9F03
0x1800f9ffa  call    ResultFromKnownLastError
0x1800f9fff  jmp     loc_1800F9F7F
0x1800fa004  call    cs:__imp_GetLastError
0x1800fa00a  mov     ebx, eax
0x1800fa00c  cmp     eax, 7Ah ; 'z'
0x1800fa00f  jnz     short loc_1800F9FC1
0x1800fa011  mov     rcx, rdi; hMem
0x1800fa014  call    cs:__imp_LocalFree
0x1800fa01a  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1800fa01e  lea     r9, [rbp+TokenInformation]; void **
0x1800fa022  lea     edx, [rbx-3Ah]; unsigned int
0x1800fa025  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800fa02a  mov     rdi, [rbp+TokenInformation]
0x1800fa02e  mov     ebx, eax
0x1800fa030  test    eax, eax
0x1800fa032  js      short loc_1800F9FB6
0x1800fa034  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800fa038  lea     rax, [rbp+TokenInformationLength]
0x1800fa03c  mov     r8, rdi; TokenInformation
0x1800fa03f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800fa044  mov     edx, 1; TokenInformationClass
0x1800fa049  mov     rcx, rsi; TokenHandle
0x1800fa04c  call    cs:__imp_GetTokenInformation
0x1800fa052  test    eax, eax
0x1800fa054  jnz     loc_1800F9F4C
0x1800fa05a  call    cs:__imp_GetLastError
0x1800fa060  mov     ebx, eax
0x1800fa062  jmp     loc_1800F9FC1
```
