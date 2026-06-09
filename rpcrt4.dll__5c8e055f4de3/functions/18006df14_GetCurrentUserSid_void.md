# GetCurrentUserSid(void * *)

- ea: `0x18006df14`
- end: `0x18006e05a`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `326`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006dd4c`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18006df14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006dfb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e03d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006dfb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e03d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e052`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006e009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006e009`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006df4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006df4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006df2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006df2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006e018`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006e018`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006dfdd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006dfdd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006df73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006dfa3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006df73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006dfa3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006dfbe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006dfbe`

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
0x18006df14  mov     [rsp-18h+arg_0], rbx
0x18006df19  push    rbp
0x18006df1a  push    rsi
0x18006df1b  push    rdi
0x18006df1c  mov     rbp, rsp
0x18006df1f  sub     rsp, 30h
0x18006df23  mov     rsi, rcx
0x18006df26  mov     [rbp+TokenHandle], 0
0x18006df2e  call    cs:__imp_GetCurrentThread
0x18006df34  mov     ebx, 20008h
0x18006df39  mov     [rbp+TokenInformationLength], 0
0x18006df40  mov     edx, ebx; DesiredAccess
0x18006df42  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006df46  mov     rcx, rax; ThreadHandle
0x18006df49  xor     r8d, r8d; OpenAsSelf
0x18006df4c  call    cs:__imp_OpenThreadToken
0x18006df52  test    eax, eax
0x18006df54  jz      loc_18006DFFC
0x18006df5a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18006df5e  lea     rax, [rbp+TokenInformationLength]
0x18006df62  xor     r9d, r9d; TokenInformationLength
0x18006df65  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18006df6a  xor     r8d, r8d; TokenInformation
0x18006df6d  lea     ebx, [r9+1]
0x18006df71  mov     edx, ebx; TokenInformationClass
0x18006df73  call    cs:__imp_GetTokenInformation
0x18006df79  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x18006df7c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006df81  mov     rcx, [rbp+TokenHandle]; hObject
0x18006df85  mov     rdi, rax
0x18006df88  test    rax, rax
0x18006df8b  jz      loc_18006E052
0x18006df91  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18006df95  lea     rax, [rbp+TokenInformationLength]
0x18006df99  mov     r8, rdi; TokenInformation
0x18006df9c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18006dfa1  mov     edx, ebx; TokenInformationClass
0x18006dfa3  call    cs:__imp_GetTokenInformation
0x18006dfa9  mov     rcx, [rbp+TokenHandle]; hObject
0x18006dfad  test    eax, eax
0x18006dfaf  jz      loc_18006E03D
0x18006dfb5  call    cs:__imp_CloseHandle
0x18006dfbb  mov     rcx, [rdi]; pSid
0x18006dfbe  call    cs:__imp_GetLengthSid
0x18006dfc4  mov     ecx, eax; dwBytes
0x18006dfc6  mov     ebx, eax
0x18006dfc8  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006dfcd  mov     [rsi], rax
0x18006dfd0  test    rax, rax
0x18006dfd3  jz      short loc_18006E036
0x18006dfd5  mov     r8, [rdi]; pSourceSid
0x18006dfd8  mov     rdx, rax; pDestinationSid
0x18006dfdb  mov     ecx, ebx; nDestinationSidLength
0x18006dfdd  call    cs:__imp_CopySid
0x18006dfe3  xor     ebx, ebx
0x18006dfe5  mov     rcx, rdi; lpMem
0x18006dfe8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18006dfed  mov     eax, ebx
0x18006dfef  mov     rbx, [rsp+30h+arg_0]
0x18006dff4  add     rsp, 30h
0x18006dff8  pop     rdi
0x18006dff9  pop     rsi
0x18006dffa  pop     rbp
0x18006dffb  retn
0x18006dffc  call    cs:__imp_GetLastError
0x18006e002  cmp     eax, 3F0h
0x18006e007  jnz     short loc_18006E02C
0x18006e009  call    cs:__imp_GetCurrentProcess
0x18006e00f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18006e013  mov     edx, ebx; DesiredAccess
0x18006e015  mov     rcx, rax; ProcessHandle
0x18006e018  call    cs:__imp_OpenProcessToken
0x18006e01e  test    eax, eax
0x18006e020  jnz     loc_18006DF5A
0x18006e026  call    cs:__imp_GetLastError
0x18006e02c  test    eax, eax
0x18006e02e  jz      loc_18006DF5A
0x18006e034  jmp     short loc_18006E04B
0x18006e036  mov     ebx, 6B9h
0x18006e03b  jmp     short loc_18006DFE5
0x18006e03d  call    cs:__imp_CloseHandle
0x18006e043  mov     rcx, rdi; lpMem
0x18006e046  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18006e04b  mov     eax, 6B9h
0x18006e050  jmp     short loc_18006DFEF
0x18006e052  call    cs:__imp_CloseHandle
0x18006e058  jmp     short loc_18006E04B
```
