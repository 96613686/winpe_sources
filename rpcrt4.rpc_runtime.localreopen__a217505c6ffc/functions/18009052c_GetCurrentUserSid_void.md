# GetCurrentUserSid(void * *)

- ea: `0x18009052c`
- end: `0x1800906c8`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `412`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180090320`

## callees

- `0x180023020`
- `0x180023a40`
- `0x18009052c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009067f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009067f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800905e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009069c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800906ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800905e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009069c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800906ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180090656`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180090656`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009056a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009056a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180090546`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180090546`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009066b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009066b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009061d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009061d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180090597`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800905cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180090597`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800905cd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800905f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800905f4`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  PSID *v3; // rax
  PSID *v4; // rdi
  DWORD LengthSid; // ebx
  void *v6; // rax
  unsigned int v7; // ebx
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  TokenInformationLength = 0;
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
        goto LABEL_2;
      LastError = GetLastError();
    }
    if ( LastError )
      return 1721;
  }
LABEL_2:
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v3 = (PSID *)AllocWrapper(TokenInformationLength);
  v4 = v3;
  if ( !v3 )
  {
    CloseHandle(TokenHandle);
    return 1721;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
  {
    CloseHandle(TokenHandle);
    FreeWrapper(v4);
    return 1721;
  }
  CloseHandle(TokenHandle);
  LengthSid = GetLengthSid(*v4);
  v6 = AllocWrapper(LengthSid);
  *a1 = v6;
  if ( v6 )
  {
    CopySid(LengthSid, v6, *v4);
    v7 = 0;
  }
  else
  {
    v7 = 1721;
  }
  FreeWrapper(v4);
  return v7;
}

```

## disassembly

```asm
0x18009052c  mov     [rsp-18h+arg_0], rbx
0x180090531  push    rbp
0x180090532  push    rsi
0x180090533  push    rdi
0x180090534  mov     rbp, rsp
0x180090537  sub     rsp, 30h
0x18009053b  mov     rsi, rcx
0x18009053e  mov     [rbp+TokenHandle], 0
0x180090546  call    cs:__imp_GetCurrentThread
0x18009054d  nop     dword ptr [rax+rax+00h]
0x180090552  mov     ebx, 20008h
0x180090557  mov     [rbp+TokenInformationLength], 0
0x18009055e  mov     edx, ebx; DesiredAccess
0x180090560  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180090564  mov     rcx, rax; ThreadHandle
0x180090567  xor     r8d, r8d; OpenAsSelf
0x18009056a  call    cs:__imp_OpenThreadToken
0x180090571  nop     dword ptr [rax+rax+00h]
0x180090576  test    eax, eax
0x180090578  jz      loc_180090643
0x18009057e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180090582  lea     rax, [rbp+TokenInformationLength]
0x180090586  xor     r9d, r9d; TokenInformationLength
0x180090589  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18009058e  xor     r8d, r8d; TokenInformation
0x180090591  lea     ebx, [r9+1]
0x180090595  mov     edx, ebx; TokenInformationClass
0x180090597  call    cs:__imp_GetTokenInformation
0x18009059e  nop     dword ptr [rax+rax+00h]
0x1800905a3  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x1800905a6  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800905ab  mov     rcx, [rbp+TokenHandle]; hObject
0x1800905af  mov     rdi, rax
0x1800905b2  test    rax, rax
0x1800905b5  jz      loc_1800906BA
0x1800905bb  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800905bf  lea     rax, [rbp+TokenInformationLength]
0x1800905c3  mov     r8, rdi; TokenInformation
0x1800905c6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800905cb  mov     edx, ebx; TokenInformationClass
0x1800905cd  call    cs:__imp_GetTokenInformation
0x1800905d4  nop     dword ptr [rax+rax+00h]
0x1800905d9  mov     rcx, [rbp+TokenHandle]; hObject
0x1800905dd  test    eax, eax
0x1800905df  jz      loc_18009069C
0x1800905e5  call    cs:__imp_CloseHandle
0x1800905ec  nop     dword ptr [rax+rax+00h]
0x1800905f1  mov     rcx, [rdi]; pSid
0x1800905f4  call    cs:__imp_GetLengthSid
0x1800905fb  nop     dword ptr [rax+rax+00h]
0x180090600  mov     ecx, eax; dwBytes
0x180090602  mov     ebx, eax
0x180090604  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180090609  mov     [rsi], rax
0x18009060c  test    rax, rax
0x18009060f  jz      loc_180090695
0x180090615  mov     r8, [rdi]; pSourceSid
0x180090618  mov     rdx, rax; pDestinationSid
0x18009061b  mov     ecx, ebx; nDestinationSidLength
0x18009061d  call    cs:__imp_CopySid
0x180090624  nop     dword ptr [rax+rax+00h]
0x180090629  xor     ebx, ebx
0x18009062b  mov     rcx, rdi; lpMem
0x18009062e  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180090633  mov     eax, ebx
0x180090635  mov     rbx, [rsp+30h+arg_0]
0x18009063a  add     rsp, 30h
0x18009063e  pop     rdi
0x18009063f  pop     rsi
0x180090640  pop     rbp
0x180090641  retn
0x180090643  call    cs:__imp_GetLastError
0x18009064a  nop     dword ptr [rax+rax+00h]
0x18009064f  cmp     eax, 3F0h
0x180090654  jnz     short loc_18009068B
0x180090656  call    cs:__imp_GetCurrentProcess
0x18009065d  nop     dword ptr [rax+rax+00h]
0x180090662  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180090666  mov     edx, ebx; DesiredAccess
0x180090668  mov     rcx, rax; ProcessHandle
0x18009066b  call    cs:__imp_OpenProcessToken
0x180090672  nop     dword ptr [rax+rax+00h]
0x180090677  test    eax, eax
0x180090679  jnz     loc_18009057E
0x18009067f  call    cs:__imp_GetLastError
0x180090686  nop     dword ptr [rax+rax+00h]
0x18009068b  test    eax, eax
0x18009068d  jz      loc_18009057E
0x180090693  jmp     short loc_1800906B0
0x180090695  mov     ebx, 6B9h
0x18009069a  jmp     short loc_18009062B
0x18009069c  call    cs:__imp_CloseHandle
0x1800906a3  nop     dword ptr [rax+rax+00h]
0x1800906a8  mov     rcx, rdi; lpMem
0x1800906ab  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800906b0  mov     eax, 6B9h
0x1800906b5  jmp     loc_180090635
0x1800906ba  call    cs:__imp_CloseHandle
0x1800906c1  nop     dword ptr [rax+rax+00h]
0x1800906c6  jmp     short loc_1800906B0
```
