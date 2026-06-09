# GetCurrentUserSid(void * *,ulong *)

- ea: `0x1800255f4`
- end: `0x180025769`
- name: `?GetCurrentUserSid@@YAKPEAPEAXPEAK@Z`
- size: `373`
- prototype: `unsigned int __fastcall(void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800156f0`

## callees

- `0x18001a9a8`
- `0x1800255f4`
- `0x180026694`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18002564b`
- `KERNEL32!GetCurrentProcess` at `0x18002564b`
- `KERNEL32!CloseHandle` at `0x18002573c`
- `KERNEL32!CloseHandle` at `0x18002573c`
- `KERNEL32!GetLastError` at `0x180025638`
- `KERNEL32!GetLastError` at `0x180025666`
- `KERNEL32!GetLastError` at `0x1800256db`
- `KERNEL32!GetLastError` at `0x180025638`
- `KERNEL32!GetLastError` at `0x180025666`
- `KERNEL32!GetLastError` at `0x1800256db`
- `KERNEL32!GetCurrentThread` at `0x180025619`
- `KERNEL32!GetCurrentThread` at `0x180025619`
- `ADVAPI32!OpenProcessToken` at `0x18002565c`
- `ADVAPI32!OpenProcessToken` at `0x18002565c`
- `ADVAPI32!GetTokenInformation` at `0x18002568c`
- `ADVAPI32!GetTokenInformation` at `0x1800256d1`
- `ADVAPI32!GetTokenInformation` at `0x18002568c`
- `ADVAPI32!GetTokenInformation` at `0x1800256d1`
- `ADVAPI32!GetLengthSid` at `0x1800256e8`
- `ADVAPI32!GetLengthSid` at `0x1800256e8`
- `ADVAPI32!CopySid` at `0x180025713`
- `ADVAPI32!CopySid` at `0x180025713`
- `ADVAPI32!OpenThreadToken` at `0x18002562e`
- `ADVAPI32!OpenThreadToken` at `0x18002562e`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1, unsigned int *a2)
{
  void *v4; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  PSID *v8; // rsi
  unsigned int LengthSid; // ebx
  void *v10; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  v4 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_17;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_4;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( !TokenInformationLength )
  {
LABEL_4:
    LastError = GetLastError();
    goto LABEL_17;
  }
  v8 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
  {
    LastError = 8;
    goto LABEL_17;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
  {
    LengthSid = GetLengthSid(*v8);
    v10 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
    v4 = v10;
    if ( !v10 )
    {
      LastError = 8;
      goto LABEL_16;
    }
    if ( CopySid(LengthSid, v10, *v8) )
    {
      *a1 = v4;
      if ( a2 )
        *a2 = LengthSid;
      LastError = 0;
      goto LABEL_16;
    }
  }
  LastError = GetLastError();
LABEL_16:
  operator delete(v8);
LABEL_17:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( LastError && v4 )
    operator delete(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800255f4  mov     rax, rsp
0x1800255f7  mov     [rax+8], rbx
0x1800255fb  mov     [rax+10h], rsi
0x1800255ff  push    rdi
0x180025600  push    r14
0x180025602  push    r15
0x180025604  sub     rsp, 30h
0x180025608  and     qword ptr [rax+20h], 0
0x18002560d  mov     r14, rdx
0x180025610  and     dword ptr [rax+18h], 0
0x180025614  mov     r15, rcx
0x180025617  xor     edi, edi
0x180025619  call    cs:__imp_GetCurrentThread
0x18002561f  mov     rcx, rax; ThreadHandle
0x180025622  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180025627  lea     edx, [rdi+8]; DesiredAccess
0x18002562a  lea     r8d, [rdi+1]; OpenAsSelf
0x18002562e  call    cs:__imp_OpenThreadToken
0x180025634  test    eax, eax
0x180025636  jnz     short loc_180025673
0x180025638  call    cs:__imp_GetLastError
0x18002563e  mov     ebx, eax
0x180025640  cmp     eax, 3F0h
0x180025645  jnz     loc_180025732
0x18002564b  call    cs:__imp_GetCurrentProcess
0x180025651  mov     rcx, rax; ProcessHandle
0x180025654  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180025659  lea     edx, [rdi+8]; DesiredAccess
0x18002565c  call    cs:__imp_OpenProcessToken
0x180025662  test    eax, eax
0x180025664  jnz     short loc_180025673
0x180025666  call    cs:__imp_GetLastError
0x18002566c  mov     ebx, eax
0x18002566e  jmp     loc_180025732
0x180025673  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180025678  lea     rax, [rsp+48h+TokenInformationLength]
0x18002567d  xor     r9d, r9d; TokenInformationLength
0x180025680  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180025685  xor     r8d, r8d; TokenInformation
0x180025688  lea     edx, [r9+1]; TokenInformationClass
0x18002568c  call    cs:__imp_GetTokenInformation
0x180025692  mov     eax, [rsp+48h+TokenInformationLength]
0x180025696  test    eax, eax
0x180025698  jz      short loc_180025666
0x18002569a  mov     ecx, eax; unsigned __int64
0x18002569c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800256a3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800256a8  mov     rsi, rax
0x1800256ab  test    rax, rax
0x1800256ae  jnz     short loc_1800256B5
0x1800256b0  lea     ebx, [rax+8]
0x1800256b3  jmp     short loc_180025732
0x1800256b5  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800256ba  lea     rax, [rsp+48h+TokenInformationLength]
0x1800256bf  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800256c4  mov     r8, rsi; TokenInformation
0x1800256c7  mov     edx, 1; TokenInformationClass
0x1800256cc  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800256d1  call    cs:__imp_GetTokenInformation
0x1800256d7  test    eax, eax
0x1800256d9  jnz     short loc_1800256E5
0x1800256db  call    cs:__imp_GetLastError
0x1800256e1  mov     ebx, eax
0x1800256e3  jmp     short loc_18002572A
0x1800256e5  mov     rcx, [rsi]; pSid
0x1800256e8  call    cs:__imp_GetLengthSid
0x1800256ee  mov     ecx, eax; unsigned __int64
0x1800256f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800256f7  mov     ebx, eax
0x1800256f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800256fe  mov     rdi, rax
0x180025701  test    rax, rax
0x180025704  jnz     short loc_18002570B
0x180025706  lea     ebx, [rax+8]
0x180025709  jmp     short loc_18002572A
0x18002570b  mov     r8, [rsi]; pSourceSid
0x18002570e  mov     rdx, rdi; pDestinationSid
0x180025711  mov     ecx, ebx; nDestinationSidLength
0x180025713  call    cs:__imp_CopySid
0x180025719  test    eax, eax
0x18002571b  jz      short loc_1800256DB
0x18002571d  mov     [r15], rdi
0x180025720  test    r14, r14
0x180025723  jz      short loc_180025728
0x180025725  mov     [r14], ebx
0x180025728  xor     ebx, ebx
0x18002572a  mov     rcx, rsi; void *
0x18002572d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025732  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180025737  test    rcx, rcx
0x18002573a  jz      short loc_180025742
0x18002573c  call    cs:__imp_CloseHandle
0x180025742  test    ebx, ebx
0x180025744  jz      short loc_180025753
0x180025746  test    rdi, rdi
0x180025749  jz      short loc_180025753
0x18002574b  mov     rcx, rdi; void *
0x18002574e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025753  mov     rsi, [rsp+48h+arg_8]
0x180025758  mov     eax, ebx
0x18002575a  mov     rbx, [rsp+48h+arg_0]
0x18002575f  add     rsp, 30h
0x180025763  pop     r15
0x180025765  pop     r14
0x180025767  pop     rdi
0x180025768  retn
```
