# SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x1800313f0`
- end: `0x1800315a5`
- name: `??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003d278`

## callees

- `0x1800313f0`
- `0x180032e68`
- `0x18003d244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800314eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003154f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800314eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003154f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031437`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003141c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003141c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031470`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003145b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003145b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003158b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003158b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031501`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031571`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031501`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031571`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800314d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003153f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800314d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003153f`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_MANDATORY_LABEL>(HANDLE TokenHandle, __int64 a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  signed int v9; // ebx
  void *v10; // rdi
  signed int LastError; // eax
  void *v12; // rcx
  int v13; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  void *TokenHandlea; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  TokenHandlea = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandlea) )
    {
      result = ResultFromKnownLastError();
      if ( (int)result < 0 )
      {
        if ( (_DWORD)result != -2147023888 )
          return result;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandlea) )
        {
          result = ResultFromKnownLastError();
          if ( (int)result < 0 )
            return result;
        }
      }
    }
    v5 = TokenHandlea;
  }
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v9 = CTLocalAllocPolicy::Alloc(TokenHandle, 0x40u, 0x800u, &TokenInformation);
  if ( v9 >= 0 )
  {
    v10 = TokenInformation;
    if ( GetTokenInformation(v5, TokenIntegrityLevel, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_18;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v13 = CTLocalAllocPolicy::Alloc(v12, 0x40u, TokenInformationLength, &TokenInformation);
      v10 = TokenInformation;
      v9 = v13;
      if ( v13 < 0 )
      {
LABEL_17:
        LocalFree(v10);
        goto LABEL_19;
      }
      if ( GetTokenInformation(
             v5,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
LABEL_18:
        *a4 = v10;
        goto LABEL_19;
      }
      LastError = GetLastError();
      v9 = LastError;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_17;
    goto LABEL_18;
  }
LABEL_19:
  if ( TokenHandlea )
    CloseHandle(TokenHandlea);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800313f0  mov     [rsp-28h+TokenInformationLength], r8d
0x1800313f5  push    rbp
0x1800313f6  push    rbx
0x1800313f7  push    rsi
0x1800313f8  push    rdi
0x1800313f9  push    r14
0x1800313fb  mov     rbp, rsp
0x1800313fe  sub     rsp, 30h
0x180031402  mov     qword ptr [r9], 0
0x180031409  mov     r14, r9
0x18003140c  mov     [rbp+TokenHandle], 0
0x180031414  mov     rsi, rcx
0x180031417  test    rcx, rcx
0x18003141a  jnz     short loc_180031491
0x18003141c  call    cs:__imp_GetCurrentThread
0x180031423  nop     dword ptr [rax+rax+00h]
0x180031428  lea     ebx, [rsi+8]
0x18003142b  xor     r8d, r8d; OpenAsSelf
0x18003142e  mov     rcx, rax; ThreadHandle
0x180031431  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180031435  mov     edx, ebx; DesiredAccess
0x180031437  call    cs:__imp_OpenThreadToken
0x18003143e  nop     dword ptr [rax+rax+00h]
0x180031443  test    eax, eax
0x180031445  jnz     short loc_18003148D
0x180031447  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003144c  test    eax, eax
0x18003144e  jns     short loc_18003148D
0x180031450  cmp     eax, 800703F0h
0x180031455  jnz     loc_180031599
0x18003145b  call    cs:__imp_GetCurrentProcess
0x180031462  nop     dword ptr [rax+rax+00h]
0x180031467  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003146b  mov     edx, ebx; DesiredAccess
0x18003146d  mov     rcx, rax; ProcessHandle
0x180031470  call    cs:__imp_OpenProcessToken
0x180031477  nop     dword ptr [rax+rax+00h]
0x18003147c  test    eax, eax
0x18003147e  jnz     short loc_18003148D
0x180031480  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180031485  test    eax, eax
0x180031487  js      loc_180031599
0x18003148d  mov     rsi, [rbp+TokenHandle]
0x180031491  mov     r8d, 800h; unsigned __int64
0x180031497  mov     [rbp+TokenInformation], 0
0x18003149f  lea     r9, [rbp+TokenInformation]; void **
0x1800314a3  mov     [rbp+TokenInformationLength], r8d
0x1800314a7  mov     edx, 40h ; '@'; unsigned int
0x1800314ac  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800314b1  mov     ebx, eax
0x1800314b3  test    eax, eax
0x1800314b5  js      loc_180031582
0x1800314bb  mov     rdi, [rbp+TokenInformation]
0x1800314bf  lea     rax, [rbp+TokenInformationLength]
0x1800314c3  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800314c7  mov     r8, rdi; TokenInformation
0x1800314ca  mov     edx, 19h; TokenInformationClass
0x1800314cf  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800314d4  mov     rcx, rsi; TokenHandle
0x1800314d7  call    cs:__imp_GetTokenInformation
0x1800314de  nop     dword ptr [rax+rax+00h]
0x1800314e3  test    eax, eax
0x1800314e5  jnz     loc_18003157F
0x1800314eb  call    cs:__imp_GetLastError
0x1800314f2  nop     dword ptr [rax+rax+00h]
0x1800314f7  mov     ebx, eax
0x1800314f9  cmp     eax, 7Ah ; 'z'
0x1800314fc  jnz     short loc_18003155D
0x1800314fe  mov     rcx, rdi; hMem
0x180031501  call    cs:__imp_LocalFree
0x180031508  nop     dword ptr [rax+rax+00h]
0x18003150d  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180031511  lea     r9, [rbp+TokenInformation]; void **
0x180031515  lea     edx, [rbx-3Ah]; unsigned int
0x180031518  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003151d  mov     rdi, [rbp+TokenInformation]
0x180031521  mov     ebx, eax
0x180031523  test    eax, eax
0x180031525  js      short loc_18003156E
0x180031527  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003152b  lea     rax, [rbp+TokenInformationLength]
0x18003152f  mov     r8, rdi; TokenInformation
0x180031532  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180031537  mov     edx, 19h; TokenInformationClass
0x18003153c  mov     rcx, rsi; TokenHandle
0x18003153f  call    cs:__imp_GetTokenInformation
0x180031546  nop     dword ptr [rax+rax+00h]
0x18003154b  test    eax, eax
0x18003154d  jnz     short loc_18003157F
0x18003154f  call    cs:__imp_GetLastError
0x180031556  nop     dword ptr [rax+rax+00h]
0x18003155b  mov     ebx, eax
0x18003155d  test    eax, eax
0x18003155f  jle     short loc_18003156A
0x180031561  movzx   ebx, ax
0x180031564  or      ebx, 80070000h
0x18003156a  test    ebx, ebx
0x18003156c  jns     short loc_18003157F
0x18003156e  mov     rcx, rdi; hMem
0x180031571  call    cs:__imp_LocalFree
0x180031578  nop     dword ptr [rax+rax+00h]
0x18003157d  jmp     short loc_180031582
0x18003157f  mov     [r14], rdi
0x180031582  mov     rcx, [rbp+TokenHandle]; hObject
0x180031586  test    rcx, rcx
0x180031589  jz      short loc_180031597
0x18003158b  call    cs:__imp_CloseHandle
0x180031592  nop     dword ptr [rax+rax+00h]
0x180031597  mov     eax, ebx
0x180031599  add     rsp, 30h
0x18003159d  pop     r14
0x18003159f  pop     rdi
0x1800315a0  pop     rsi
0x1800315a1  pop     rbx
0x1800315a2  pop     rbp
0x1800315a3  retn
```
