# GetTokenIL

- ea: `0x1800216bc`
- end: `0x18002186b`
- name: `GetTokenIL`
- size: `431`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023018`

## callees

- `0x1800208d8`
- `0x1800216bc`
- `0x1800aadec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800216fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800216fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002175a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021810`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002175a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021860`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800217b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800217b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002177a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002177a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800217c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800217c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021790`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021790`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002174c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002174c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021725`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021848`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021725`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021848`

## pseudocode

```c
__int64 __fastcall GetTokenIL(HANDLE TokenHandle, DWORD *a2)
{
  HANDLE v3; // rsi
  PSID *v4; // r14
  void *v5; // rdi
  signed int v6; // ebx
  HANDLE CurrentThread; // rax
  int Error; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  void *v12; // rcx
  int v13; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandlea; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  *a2 = 0;
  TokenHandlea = 0;
  v3 = TokenHandle;
  if ( !TokenHandle )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandlea) )
    {
      Error = ResultFromKnownLastError();
      v6 = Error;
      if ( Error < 0 )
      {
        if ( Error != -2147023888 )
          return (unsigned int)v6;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandlea) )
        {
          v6 = ResultFromKnownLastError();
          if ( v6 < 0 )
            return (unsigned int)v6;
        }
      }
    }
    v3 = TokenHandlea;
  }
  v4 = 0;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v5 = TokenInformation;
  if ( !TokenInformation )
  {
    v6 = -2147024882;
    goto LABEL_5;
  }
  v6 = 0;
  if ( !GetTokenInformation(v3, TokenIntegrityLevel, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v5);
      v13 = CTLocalAllocPolicy::Alloc(v12, 0x40u, TokenInformationLength, &TokenInformation);
      v5 = TokenInformation;
      v6 = v13;
      if ( v13 < 0 )
        goto LABEL_19;
      if ( GetTokenInformation(
             v3,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        goto LABEL_4;
      }
      LastError = GetLastError();
      v6 = LastError;
    }
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_4;
LABEL_19:
    LocalFree(v5);
    goto LABEL_5;
  }
LABEL_4:
  v4 = (PSID *)v5;
LABEL_5:
  if ( TokenHandlea )
    CloseHandle(TokenHandlea);
  if ( v6 >= 0 )
  {
    *a2 = *GetSidSubAuthority(*v4, 0);
    LocalFree(v4);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800216bc  mov     [rsp-28h+arg_18], rbx
0x1800216c1  push    rbp
0x1800216c2  push    rsi
0x1800216c3  push    rdi
0x1800216c4  push    r14
0x1800216c6  push    r15
0x1800216c8  mov     rbp, rsp
0x1800216cb  sub     rsp, 30h
0x1800216cf  mov     dword ptr [rdx], 0
0x1800216d5  mov     r15, rdx
0x1800216d8  mov     [rbp+TokenHandle], 0
0x1800216e0  mov     rsi, rcx
0x1800216e3  test    rcx, rcx
0x1800216e6  jz      loc_18002177A
0x1800216ec  mov     edx, 800h; uBytes
0x1800216f1  xor     r14d, r14d
0x1800216f4  mov     [rbp+TokenInformationLength], edx
0x1800216f7  lea     ecx, [r14+40h]; uFlags
0x1800216fb  call    cs:__imp_LocalAlloc
0x180021701  mov     [rbp+TokenInformation], rax
0x180021705  mov     rdi, rax
0x180021708  test    rax, rax
0x18002170b  jz      short loc_180021773
0x18002170d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180021711  lea     rax, [rbp+TokenInformationLength]
0x180021715  xor     ebx, ebx
0x180021717  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002171c  mov     r8, rdi; TokenInformation
0x18002171f  mov     rcx, rsi; TokenHandle
0x180021722  lea     edx, [rbx+19h]; TokenInformationClass
0x180021725  call    cs:__imp_GetTokenInformation
0x18002172b  test    eax, eax
0x18002172d  jz      loc_180021800
0x180021733  mov     r14, rdi
0x180021736  mov     rcx, [rbp+TokenHandle]; hObject
0x18002173a  test    rcx, rcx
0x18002173d  jnz     loc_180021860
0x180021743  test    ebx, ebx
0x180021745  js      short loc_180021760
0x180021747  mov     rcx, [r14]; pSid
0x18002174a  xor     edx, edx; nSubAuthority
0x18002174c  call    cs:__imp_GetSidSubAuthority
0x180021752  mov     rcx, r14; hMem
0x180021755  mov     edx, [rax]
0x180021757  mov     [r15], edx
0x18002175a  call    cs:__imp_LocalFree
0x180021760  mov     eax, ebx
0x180021762  mov     rbx, [rsp+30h+arg_18]
0x180021767  add     rsp, 30h
0x18002176b  pop     r15
0x18002176d  pop     r14
0x18002176f  pop     rdi
0x180021770  pop     rsi
0x180021771  pop     rbp
0x180021772  retn
0x180021773  mov     ebx, 8007000Eh
0x180021778  jmp     short loc_180021736
0x18002177a  call    cs:__imp_GetCurrentThread
0x180021780  xor     r8d, r8d; OpenAsSelf
0x180021783  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180021787  mov     rcx, rax; ThreadHandle
0x18002178a  lea     edi, [r8+8]
0x18002178e  mov     edx, edi; DesiredAccess
0x180021790  call    cs:__imp_OpenThreadToken
0x180021796  test    eax, eax
0x180021798  jz      short loc_1800217A3
0x18002179a  mov     rsi, [rbp+TokenHandle]
0x18002179e  jmp     loc_1800216EC
0x1800217a3  call    ResultFromKnownLastError
0x1800217a8  mov     ebx, eax
0x1800217aa  test    eax, eax
0x1800217ac  jns     short loc_18002179A
0x1800217ae  cmp     eax, 800703F0h
0x1800217b3  jnz     short loc_180021760
0x1800217b5  call    cs:__imp_GetCurrentProcess
0x1800217bb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800217bf  mov     edx, edi; DesiredAccess
0x1800217c1  mov     rcx, rax; ProcessHandle
0x1800217c4  call    cs:__imp_OpenProcessToken
0x1800217ca  test    eax, eax
0x1800217cc  jnz     short loc_18002179A
0x1800217ce  call    ResultFromKnownLastError
0x1800217d3  mov     ebx, eax
0x1800217d5  test    eax, eax
0x1800217d7  js      short loc_180021760
0x1800217d9  jmp     short loc_18002179A
0x1800217db  test    ebx, ebx
0x1800217dd  jns     loc_180021733
0x1800217e3  mov     rcx, rdi; hMem
0x1800217e6  call    cs:__imp_LocalFree
0x1800217ec  jmp     loc_180021736
0x1800217f1  test    eax, eax
0x1800217f3  jle     short loc_1800217DB
0x1800217f5  movzx   ebx, ax
0x1800217f8  or      ebx, 80070000h
0x1800217fe  jmp     short loc_1800217DB
0x180021800  call    cs:__imp_GetLastError
0x180021806  mov     ebx, eax
0x180021808  cmp     eax, 7Ah ; 'z'
0x18002180b  jnz     short loc_1800217F1
0x18002180d  mov     rcx, rdi; hMem
0x180021810  call    cs:__imp_LocalFree
0x180021816  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18002181a  lea     r9, [rbp+TokenInformation]; void **
0x18002181e  lea     edx, [rbx-3Ah]; unsigned int
0x180021821  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180021826  mov     rdi, [rbp+TokenInformation]
0x18002182a  mov     ebx, eax
0x18002182c  test    eax, eax
0x18002182e  js      short loc_1800217E3
0x180021830  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180021834  lea     rax, [rbp+TokenInformationLength]
0x180021838  mov     r8, rdi; TokenInformation
0x18002183b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180021840  mov     edx, 19h; TokenInformationClass
0x180021845  mov     rcx, rsi; TokenHandle
0x180021848  call    cs:__imp_GetTokenInformation
0x18002184e  test    eax, eax
0x180021850  jnz     loc_180021733
0x180021856  call    cs:__imp_GetLastError
0x18002185c  mov     ebx, eax
0x18002185e  jmp     short loc_1800217F1
0x180021860  call    cs:__imp_CloseHandle
0x180021866  jmp     loc_180021743
```
