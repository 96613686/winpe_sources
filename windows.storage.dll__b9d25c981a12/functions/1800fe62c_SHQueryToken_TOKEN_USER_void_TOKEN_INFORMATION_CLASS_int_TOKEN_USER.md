# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800fe62c`
- end: `0x1800fe7c9`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `413`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800fe4fc`
- `0x1800fe5b0`
- `0x1802bfad4`
- `0x180560c18`
- `0x1805aeb78`
- `0x1805b4a30`
- `0x1805d90ec`

## callees

- `0x18004e06c`
- `0x1800fe62c`
- `0x18012ced0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1806672f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180667368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1806672f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180667368`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe755`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800fe6b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800fe6b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fe69f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fe69f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe673`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe770`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe673`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe729`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800fe6d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800fe6d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fe795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180667312`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fe795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180667312`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800fe709`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180667354`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800fe709`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180667354`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(__int64 a1, DWORD a2, int a3, _QWORD *a4)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  void *v9; // rsi
  void *v10; // rdi
  signed int v11; // ebx
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
          goto LABEL_6;
        result = ResultFromKnownLastError();
      }
      if ( (_DWORD)result == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
          goto LABEL_6;
        result = ResultFromKnownLastError();
      }
      if ( (int)result < 0 )
        return result;
    }
  }
LABEL_6:
  v9 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v10 = TokenInformation;
  if ( !TokenInformation )
  {
    v11 = -2147024882;
    goto LABEL_9;
  }
  v11 = 0;
  if ( !GetTokenInformation(v9, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v15 = CTLocalAllocPolicy::Alloc(v14, 0x40u, TokenInformationLength, &TokenInformation);
      v10 = TokenInformation;
      v11 = v15;
      if ( v15 < 0 )
        goto LABEL_17;
      if ( GetTokenInformation(v9, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_8;
      LastError = GetLastError();
      v11 = LastError;
    }
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_8;
LABEL_17:
    LocalFree(v10);
    goto LABEL_9;
  }
LABEL_8:
  *a4 = v10;
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800fe62c  mov     [rsp-28h+TokenInformationLength], edx
0x1800fe630  mov     [rsp-28h+TokenHandle], rcx
0x1800fe635  push    rbp
0x1800fe636  push    rbx
0x1800fe637  push    rsi
0x1800fe638  push    rdi
0x1800fe639  push    r14
0x1800fe63b  mov     rbp, rsp
0x1800fe63e  sub     rsp, 30h
0x1800fe642  mov     r14, r9
0x1800fe645  mov     qword ptr [r9], 0
0x1800fe64c  mov     ebx, r8d
0x1800fe64f  mov     [rbp+TokenHandle], 0
0x1800fe657  call    cs:__imp_GetCurrentThread
0x1800fe65e  nop     dword ptr [rax+rax+00h]
0x1800fe663  xor     r8d, r8d; OpenAsSelf
0x1800fe666  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800fe66a  mov     rcx, rax; ThreadHandle
0x1800fe66d  lea     edi, [r8+8]
0x1800fe671  mov     edx, edi; DesiredAccess
0x1800fe673  call    cs:__imp_OpenThreadToken
0x1800fe67a  nop     dword ptr [rax+rax+00h]
0x1800fe67f  test    eax, eax
0x1800fe681  jnz     short loc_1800FE6C8
0x1800fe683  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800fe688  test    eax, eax
0x1800fe68a  jns     short loc_1800FE6C8
0x1800fe68c  test    ebx, ebx
0x1800fe68e  jnz     loc_1800FE74A
0x1800fe694  cmp     eax, 800703F0h
0x1800fe699  jnz     loc_1800FE7B5
0x1800fe69f  call    cs:__imp_GetCurrentProcess
0x1800fe6a6  nop     dword ptr [rax+rax+00h]
0x1800fe6ab  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800fe6af  mov     edx, edi; DesiredAccess
0x1800fe6b1  mov     rcx, rax; ProcessHandle
0x1800fe6b4  call    cs:__imp_OpenProcessToken
0x1800fe6bb  nop     dword ptr [rax+rax+00h]
0x1800fe6c0  test    eax, eax
0x1800fe6c2  jz      loc_1800FE7C2
0x1800fe6c8  mov     rsi, [rbp+TokenHandle]
0x1800fe6cc  mov     edx, 800h; uBytes
0x1800fe6d1  mov     ecx, 40h ; '@'; uFlags
0x1800fe6d6  mov     [rbp+TokenInformationLength], edx
0x1800fe6d9  call    cs:__imp_LocalAlloc
0x1800fe6e0  nop     dword ptr [rax+rax+00h]
0x1800fe6e5  mov     [rbp+TokenInformation], rax
0x1800fe6e9  mov     rdi, rax
0x1800fe6ec  test    rax, rax
0x1800fe6ef  jz      short loc_1800FE743
0x1800fe6f1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800fe6f5  lea     rax, [rbp+TokenInformationLength]
0x1800fe6f9  xor     ebx, ebx
0x1800fe6fb  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800fe700  mov     r8, rdi; TokenInformation
0x1800fe703  mov     rcx, rsi; TokenHandle
0x1800fe706  lea     edx, [rbx+1]; TokenInformationClass
0x1800fe709  call    cs:__imp_GetTokenInformation
0x1800fe710  nop     dword ptr [rax+rax+00h]
0x1800fe715  test    eax, eax
0x1800fe717  jz      loc_1806672F8
0x1800fe71d  mov     [r14], rdi
0x1800fe720  mov     rcx, [rbp+TokenHandle]; hObject
0x1800fe724  test    rcx, rcx
0x1800fe727  jz      short loc_1800FE735
0x1800fe729  call    cs:__imp_CloseHandle
0x1800fe730  nop     dword ptr [rax+rax+00h]
0x1800fe735  mov     eax, ebx
0x1800fe737  add     rsp, 30h
0x1800fe73b  pop     r14
0x1800fe73d  pop     rdi
0x1800fe73e  pop     rsi
0x1800fe73f  pop     rbx
0x1800fe740  pop     rbp
0x1800fe741  retn
0x1800fe743  mov     ebx, 8007000Eh
0x1800fe748  jmp     short loc_1800FE720
0x1800fe74a  cmp     eax, 80070005h
0x1800fe74f  jnz     loc_1800FE694
0x1800fe755  call    cs:__imp_GetCurrentThread
0x1800fe75c  nop     dword ptr [rax+rax+00h]
0x1800fe761  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800fe765  mov     r8d, 1; OpenAsSelf
0x1800fe76b  mov     rcx, rax; ThreadHandle
0x1800fe76e  mov     edx, edi; DesiredAccess
0x1800fe770  call    cs:__imp_OpenThreadToken
0x1800fe777  nop     dword ptr [rax+rax+00h]
0x1800fe77c  test    eax, eax
0x1800fe77e  jnz     loc_1800FE6C8
0x1800fe784  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800fe789  jmp     loc_1800FE694
0x1800fe78e  test    ebx, ebx
0x1800fe790  jns     short loc_1800FE71D
0x1800fe792  mov     rcx, rdi; hMem
0x1800fe795  call    cs:__imp_LocalFree
0x1800fe79c  nop     dword ptr [rax+rax+00h]
0x1800fe7a1  jmp     loc_1800FE720
0x1800fe7a6  test    eax, eax
0x1800fe7a8  jle     short loc_1800FE78E
0x1800fe7aa  movzx   ebx, ax
0x1800fe7ad  or      ebx, 80070000h
0x1800fe7b3  jmp     short loc_1800FE78E
0x1800fe7b5  test    eax, eax
0x1800fe7b7  jns     loc_1800FE6C8
0x1800fe7bd  jmp     loc_1800FE737
0x1800fe7c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800fe7c7  jmp     short loc_1800FE7B5
0x1806672f8  call    cs:__imp_GetLastError
0x1806672ff  nop     dword ptr [rax+rax+00h]
0x180667304  mov     ebx, eax
0x180667306  cmp     eax, 7Ah ; 'z'
0x180667309  jnz     loc_1800FE7A6
0x18066730f  mov     rcx, rdi; hMem
0x180667312  call    cs:__imp_LocalFree
0x180667319  nop     dword ptr [rax+rax+00h]
0x18066731e  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180667322  lea     r9, [rbp+TokenInformation]; void **
0x180667326  lea     edx, [rbx-3Ah]; unsigned int
0x180667329  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18066732e  mov     rdi, [rbp+TokenInformation]
0x180667332  mov     ebx, eax
0x180667334  test    eax, eax
0x180667336  js      loc_1800FE792
0x18066733c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180667340  lea     rax, [rbp+TokenInformationLength]
0x180667344  mov     r8, rdi; TokenInformation
0x180667347  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18066734c  mov     edx, 1; TokenInformationClass
0x180667351  mov     rcx, rsi; TokenHandle
0x180667354  call    cs:__imp_GetTokenInformation
0x18066735b  nop     dword ptr [rax+rax+00h]
0x180667360  test    eax, eax
0x180667362  jnz     loc_1800FE71D
0x180667368  call    cs:__imp_GetLastError
0x18066736f  nop     dword ptr [rax+rax+00h]
0x180667374  mov     ebx, eax
0x180667376  jmp     loc_1800FE7A6
```
