# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800bb2a0`
- end: `0x1800bb3be`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `286`
- prototype: `int __fastcall(HANDLE TokenHandle, unsigned int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bb4f4`

## callees

- `0x1800bb2a0`
- `0x1800bb3c4`
- `0x1800bb3f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb37b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb3ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb3ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb397`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bb322`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bb371`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bb322`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bb371`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_USER>(HANDLE TokenHandle, unsigned int a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  int result; // eax
  signed int v7; // ebx
  void *v8; // rdi
  signed int LastError; // eax
  unsigned int v10; // edx
  void *v11; // rcx
  int v12; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  hObject = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    result = SHOpenEffectiveToken(0, a2, &hObject);
    if ( result < 0 )
      return result;
    v5 = hObject;
  }
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v7 = CTLocalAllocPolicy::Alloc(TokenHandle, a2, 0x800u, &TokenInformation);
  if ( v7 >= 0 )
  {
    v8 = TokenInformation;
    if ( GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_14;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v8);
      v12 = CTLocalAllocPolicy::Alloc(v11, v10, TokenInformationLength, &TokenInformation);
      v8 = TokenInformation;
      v7 = v12;
      if ( v12 < 0 )
      {
LABEL_13:
        LocalFree(v8);
        goto LABEL_15;
      }
      if ( GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
LABEL_14:
        *a4 = v8;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v7 = LastError;
    }
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_13;
    goto LABEL_14;
  }
LABEL_15:
  if ( hObject )
    CloseHandle(hObject);
  return v7;
}

```

## disassembly

```asm
0x1800bb2a0  mov     [rsp-28h+TokenInformationLength], r8d
0x1800bb2a5  push    rbp
0x1800bb2a6  push    rbx
0x1800bb2a7  push    rsi
0x1800bb2a8  push    rdi
0x1800bb2a9  push    r14
0x1800bb2ab  mov     rbp, rsp
0x1800bb2ae  sub     rsp, 30h
0x1800bb2b2  mov     qword ptr [r9], 0
0x1800bb2b9  mov     r14, r9
0x1800bb2bc  mov     [rbp+hObject], 0
0x1800bb2c4  mov     rsi, rcx
0x1800bb2c7  test    rcx, rcx
0x1800bb2ca  jnz     short loc_1800BB2E1
0x1800bb2cc  lea     r8, [rbp+hObject]; void **
0x1800bb2d0  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800bb2d5  test    eax, eax
0x1800bb2d7  js      loc_1800BB3B3
0x1800bb2dd  mov     rsi, [rbp+hObject]
0x1800bb2e1  mov     r8d, 800h; unsigned __int64
0x1800bb2e7  mov     [rbp+TokenInformation], 0
0x1800bb2ef  lea     r9, [rbp+TokenInformation]; void **
0x1800bb2f3  mov     [rbp+TokenInformationLength], r8d
0x1800bb2f7  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800bb2fc  mov     ebx, eax
0x1800bb2fe  test    eax, eax
0x1800bb300  js      loc_1800BB3A2
0x1800bb306  mov     rdi, [rbp+TokenInformation]
0x1800bb30a  lea     rax, [rbp+TokenInformationLength]
0x1800bb30e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800bb312  mov     r8, rdi; TokenInformation
0x1800bb315  mov     edx, 1; TokenInformationClass
0x1800bb31a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800bb31f  mov     rcx, rsi; TokenHandle
0x1800bb322  call    cs:__imp_GetTokenInformation
0x1800bb328  test    eax, eax
0x1800bb32a  jnz     short loc_1800BB39F
0x1800bb32c  call    cs:__imp_GetLastError
0x1800bb332  mov     ebx, eax
0x1800bb334  cmp     eax, 7Ah ; 'z'
0x1800bb337  jnz     short loc_1800BB383
0x1800bb339  mov     rcx, rdi; hMem
0x1800bb33c  call    cs:__imp_LocalFree
0x1800bb342  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1800bb346  lea     r9, [rbp+TokenInformation]; void **
0x1800bb34a  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800bb34f  mov     rdi, [rbp+TokenInformation]
0x1800bb353  mov     ebx, eax
0x1800bb355  test    eax, eax
0x1800bb357  js      short loc_1800BB394
0x1800bb359  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800bb35d  lea     rax, [rbp+TokenInformationLength]
0x1800bb361  mov     r8, rdi; TokenInformation
0x1800bb364  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800bb369  mov     edx, 1; TokenInformationClass
0x1800bb36e  mov     rcx, rsi; TokenHandle
0x1800bb371  call    cs:__imp_GetTokenInformation
0x1800bb377  test    eax, eax
0x1800bb379  jnz     short loc_1800BB39F
0x1800bb37b  call    cs:__imp_GetLastError
0x1800bb381  mov     ebx, eax
0x1800bb383  test    eax, eax
0x1800bb385  jle     short loc_1800BB390
0x1800bb387  movzx   ebx, ax
0x1800bb38a  or      ebx, 80070000h
0x1800bb390  test    ebx, ebx
0x1800bb392  jns     short loc_1800BB39F
0x1800bb394  mov     rcx, rdi; hMem
0x1800bb397  call    cs:__imp_LocalFree
0x1800bb39d  jmp     short loc_1800BB3A2
0x1800bb39f  mov     [r14], rdi
0x1800bb3a2  mov     rcx, [rbp+hObject]; hObject
0x1800bb3a6  test    rcx, rcx
0x1800bb3a9  jz      short loc_1800BB3B1
0x1800bb3ab  call    cs:__imp_CloseHandle
0x1800bb3b1  mov     eax, ebx
0x1800bb3b3  add     rsp, 30h
0x1800bb3b7  pop     r14
0x1800bb3b9  pop     rdi
0x1800bb3ba  pop     rsi
0x1800bb3bb  pop     rbx
0x1800bb3bc  pop     rbp
0x1800bb3bd  retn
```
