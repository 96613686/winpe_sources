# GetCurrentUserSid(void * *,ulong *)

- ea: `0x1800121e0`
- end: `0x1800123a1`
- name: `?GetCurrentUserSid@@YAKPEAPEAXPEAK@Z`
- size: `449`
- prototype: `unsigned int __fastcall(void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180012150`

## callees

- `0x18000179c`
- `0x1800121e0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012230`
- `KERNEL32!GetLastError` at `0x180012270`
- `KERNEL32!GetLastError` at `0x1800122fa`
- `KERNEL32!GetLastError` at `0x180012230`
- `KERNEL32!GetLastError` at `0x180012270`
- `KERNEL32!GetLastError` at `0x1800122fa`
- `KERNEL32!CloseHandle` at `0x18001236d`
- `KERNEL32!CloseHandle` at `0x18001236d`
- `KERNEL32!GetCurrentThread` at `0x180012205`
- `KERNEL32!GetCurrentThread` at `0x180012205`
- `KERNEL32!GetCurrentProcess` at `0x180012249`
- `KERNEL32!GetCurrentProcess` at `0x180012249`
- `ADVAPI32!OpenThreadToken` at `0x180012220`
- `ADVAPI32!OpenThreadToken` at `0x180012220`
- `ADVAPI32!CopySid` at `0x18001233e`
- `ADVAPI32!CopySid` at `0x18001233e`
- `ADVAPI32!GetLengthSid` at `0x18001230d`
- `ADVAPI32!GetLengthSid` at `0x18001230d`
- `ADVAPI32!GetTokenInformation` at `0x18001229c`
- `ADVAPI32!GetTokenInformation` at `0x1800122ea`
- `ADVAPI32!GetTokenInformation` at `0x18001229c`
- `ADVAPI32!GetTokenInformation` at `0x1800122ea`
- `ADVAPI32!OpenProcessToken` at `0x180012260`
- `ADVAPI32!OpenProcessToken` at `0x180012260`

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
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

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
0x1800121e0  mov     rax, rsp
0x1800121e3  mov     [rax+8], rbx
0x1800121e7  mov     [rax+10h], rsi
0x1800121eb  push    rdi
0x1800121ec  push    r14
0x1800121ee  push    r15
0x1800121f0  sub     rsp, 30h
0x1800121f4  and     qword ptr [rax+20h], 0
0x1800121f9  mov     r14, rdx
0x1800121fc  and     dword ptr [rax+18h], 0
0x180012200  mov     r15, rcx
0x180012203  xor     edi, edi
0x180012205  call    cs:__imp_GetCurrentThread
0x18001220c  nop     dword ptr [rax+rax+00h]
0x180012211  mov     rcx, rax; ThreadHandle
0x180012214  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180012219  lea     edx, [rdi+8]; DesiredAccess
0x18001221c  lea     r8d, [rdi+1]; OpenAsSelf
0x180012220  call    cs:__imp_OpenThreadToken
0x180012227  nop     dword ptr [rax+rax+00h]
0x18001222c  test    eax, eax
0x18001222e  jnz     short loc_180012283
0x180012230  call    cs:__imp_GetLastError
0x180012237  nop     dword ptr [rax+rax+00h]
0x18001223c  mov     ebx, eax
0x18001223e  cmp     eax, 3F0h
0x180012243  jnz     loc_180012363
0x180012249  call    cs:__imp_GetCurrentProcess
0x180012250  nop     dword ptr [rax+rax+00h]
0x180012255  mov     rcx, rax; ProcessHandle
0x180012258  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18001225d  lea     edx, [rdi+8]; DesiredAccess
0x180012260  call    cs:__imp_OpenProcessToken
0x180012267  nop     dword ptr [rax+rax+00h]
0x18001226c  test    eax, eax
0x18001226e  jnz     short loc_180012283
0x180012270  call    cs:__imp_GetLastError
0x180012277  nop     dword ptr [rax+rax+00h]
0x18001227c  mov     ebx, eax
0x18001227e  jmp     loc_180012363
0x180012283  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180012288  lea     rax, [rsp+48h+TokenInformationLength]
0x18001228d  xor     r9d, r9d; TokenInformationLength
0x180012290  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180012295  xor     r8d, r8d; TokenInformation
0x180012298  lea     edx, [r9+1]; TokenInformationClass
0x18001229c  call    cs:__imp_GetTokenInformation
0x1800122a3  nop     dword ptr [rax+rax+00h]
0x1800122a8  mov     eax, [rsp+48h+TokenInformationLength]
0x1800122ac  test    eax, eax
0x1800122ae  jz      short loc_180012270
0x1800122b0  mov     ecx, eax; unsigned __int64
0x1800122b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800122b9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800122be  mov     rsi, rax
0x1800122c1  test    rax, rax
0x1800122c4  jnz     short loc_1800122CE
0x1800122c6  lea     ebx, [rax+8]
0x1800122c9  jmp     loc_180012363
0x1800122ce  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800122d3  lea     rax, [rsp+48h+TokenInformationLength]
0x1800122d8  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800122dd  mov     r8, rsi; TokenInformation
0x1800122e0  mov     edx, 1; TokenInformationClass
0x1800122e5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800122ea  call    cs:__imp_GetTokenInformation
0x1800122f1  nop     dword ptr [rax+rax+00h]
0x1800122f6  test    eax, eax
0x1800122f8  jnz     short loc_18001230A
0x1800122fa  call    cs:__imp_GetLastError
0x180012301  nop     dword ptr [rax+rax+00h]
0x180012306  mov     ebx, eax
0x180012308  jmp     short loc_18001235B
0x18001230a  mov     rcx, [rsi]; pSid
0x18001230d  call    cs:__imp_GetLengthSid
0x180012314  nop     dword ptr [rax+rax+00h]
0x180012319  mov     ecx, eax; unsigned __int64
0x18001231b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012322  mov     ebx, eax
0x180012324  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012329  mov     rdi, rax
0x18001232c  test    rax, rax
0x18001232f  jnz     short loc_180012336
0x180012331  lea     ebx, [rax+8]
0x180012334  jmp     short loc_18001235B
0x180012336  mov     r8, [rsi]; pSourceSid
0x180012339  mov     rdx, rdi; pDestinationSid
0x18001233c  mov     ecx, ebx; nDestinationSidLength
0x18001233e  call    cs:__imp_CopySid
0x180012345  nop     dword ptr [rax+rax+00h]
0x18001234a  test    eax, eax
0x18001234c  jz      short loc_1800122FA
0x18001234e  mov     [r15], rdi
0x180012351  test    r14, r14
0x180012354  jz      short loc_180012359
0x180012356  mov     [r14], ebx
0x180012359  xor     ebx, ebx
0x18001235b  mov     rcx, rsi; lpMem
0x18001235e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012363  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180012368  test    rcx, rcx
0x18001236b  jz      short loc_180012379
0x18001236d  call    cs:__imp_CloseHandle
0x180012374  nop     dword ptr [rax+rax+00h]
0x180012379  test    ebx, ebx
0x18001237b  jz      short loc_18001238A
0x18001237d  test    rdi, rdi
0x180012380  jz      short loc_18001238A
0x180012382  mov     rcx, rdi; lpMem
0x180012385  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001238a  mov     rsi, [rsp+48h+arg_8]
0x18001238f  mov     eax, ebx
0x180012391  mov     rbx, [rsp+48h+arg_0]
0x180012396  add     rsp, 30h
0x18001239a  pop     r15
0x18001239c  pop     r14
0x18001239e  pop     rdi
0x18001239f  retn
```
