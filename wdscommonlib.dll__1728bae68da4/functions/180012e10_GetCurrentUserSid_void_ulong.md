# GetCurrentUserSid(void * *,ulong *)

- ea: `0x180012e10`
- end: `0x180012fdf`
- name: `?GetCurrentUserSid@@YAKPEAPEAXPEAK@Z`
- size: `463`
- prototype: `unsigned int __fastcall(void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180012d70`

## callees

- `0x18000214c`
- `0x180012e10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012f8e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012fbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012f8e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012fbc`
- `KERNEL32!GetLastError` at `0x180012e60`
- `KERNEL32!GetLastError` at `0x180012ea0`
- `KERNEL32!GetLastError` at `0x180012f2a`
- `KERNEL32!GetLastError` at `0x180012e60`
- `KERNEL32!GetLastError` at `0x180012ea0`
- `KERNEL32!GetLastError` at `0x180012f2a`
- `KERNEL32!CloseHandle` at `0x180012fa4`
- `KERNEL32!CloseHandle` at `0x180012fa4`
- `KERNEL32!GetCurrentThread` at `0x180012e35`
- `KERNEL32!GetCurrentThread` at `0x180012e35`
- `KERNEL32!GetCurrentProcess` at `0x180012e79`
- `KERNEL32!GetCurrentProcess` at `0x180012e79`
- `ADVAPI32!GetTokenInformation` at `0x180012ecc`
- `ADVAPI32!GetTokenInformation` at `0x180012f1a`
- `ADVAPI32!GetTokenInformation` at `0x180012ecc`
- `ADVAPI32!GetTokenInformation` at `0x180012f1a`
- `ADVAPI32!OpenProcessToken` at `0x180012e90`
- `ADVAPI32!OpenProcessToken` at `0x180012e90`
- `ADVAPI32!OpenThreadToken` at `0x180012e50`
- `ADVAPI32!OpenThreadToken` at `0x180012e50`
- `ADVAPI32!CopySid` at `0x180012f6e`
- `ADVAPI32!CopySid` at `0x180012f6e`
- `ADVAPI32!GetLengthSid` at `0x180012f3d`
- `ADVAPI32!GetLengthSid` at `0x180012f3d`

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
0x180012e10  mov     rax, rsp
0x180012e13  mov     [rax+8], rbx
0x180012e17  mov     [rax+10h], rsi
0x180012e1b  push    rdi
0x180012e1c  push    r14
0x180012e1e  push    r15
0x180012e20  sub     rsp, 30h
0x180012e24  and     qword ptr [rax+20h], 0
0x180012e29  mov     r14, rdx
0x180012e2c  and     dword ptr [rax+18h], 0
0x180012e30  mov     r15, rcx
0x180012e33  xor     edi, edi
0x180012e35  call    cs:__imp_GetCurrentThread
0x180012e3c  nop     dword ptr [rax+rax+00h]
0x180012e41  mov     rcx, rax; ThreadHandle
0x180012e44  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180012e49  lea     edx, [rdi+8]; DesiredAccess
0x180012e4c  lea     r8d, [rdi+1]; OpenAsSelf
0x180012e50  call    cs:__imp_OpenThreadToken
0x180012e57  nop     dword ptr [rax+rax+00h]
0x180012e5c  test    eax, eax
0x180012e5e  jnz     short loc_180012EB3
0x180012e60  call    cs:__imp_GetLastError
0x180012e67  nop     dword ptr [rax+rax+00h]
0x180012e6c  mov     ebx, eax
0x180012e6e  cmp     eax, 3F0h
0x180012e73  jnz     loc_180012F9A
0x180012e79  call    cs:__imp_GetCurrentProcess
0x180012e80  nop     dword ptr [rax+rax+00h]
0x180012e85  mov     rcx, rax; ProcessHandle
0x180012e88  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180012e8d  lea     edx, [rdi+8]; DesiredAccess
0x180012e90  call    cs:__imp_OpenProcessToken
0x180012e97  nop     dword ptr [rax+rax+00h]
0x180012e9c  test    eax, eax
0x180012e9e  jnz     short loc_180012EB3
0x180012ea0  call    cs:__imp_GetLastError
0x180012ea7  nop     dword ptr [rax+rax+00h]
0x180012eac  mov     ebx, eax
0x180012eae  jmp     loc_180012F9A
0x180012eb3  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180012eb8  lea     rax, [rsp+48h+TokenInformationLength]
0x180012ebd  xor     r9d, r9d; TokenInformationLength
0x180012ec0  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180012ec5  xor     r8d, r8d; TokenInformation
0x180012ec8  lea     edx, [r9+1]; TokenInformationClass
0x180012ecc  call    cs:__imp_GetTokenInformation
0x180012ed3  nop     dword ptr [rax+rax+00h]
0x180012ed8  mov     eax, [rsp+48h+TokenInformationLength]
0x180012edc  test    eax, eax
0x180012ede  jz      short loc_180012EA0
0x180012ee0  mov     ecx, eax; unsigned __int64
0x180012ee2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012ee9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012eee  mov     rsi, rax
0x180012ef1  test    rax, rax
0x180012ef4  jnz     short loc_180012EFE
0x180012ef6  lea     ebx, [rax+8]
0x180012ef9  jmp     loc_180012F9A
0x180012efe  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180012f03  lea     rax, [rsp+48h+TokenInformationLength]
0x180012f08  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180012f0d  mov     r8, rsi; TokenInformation
0x180012f10  mov     edx, 1; TokenInformationClass
0x180012f15  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180012f1a  call    cs:__imp_GetTokenInformation
0x180012f21  nop     dword ptr [rax+rax+00h]
0x180012f26  test    eax, eax
0x180012f28  jnz     short loc_180012F3A
0x180012f2a  call    cs:__imp_GetLastError
0x180012f31  nop     dword ptr [rax+rax+00h]
0x180012f36  mov     ebx, eax
0x180012f38  jmp     short loc_180012F8B
0x180012f3a  mov     rcx, [rsi]; pSid
0x180012f3d  call    cs:__imp_GetLengthSid
0x180012f44  nop     dword ptr [rax+rax+00h]
0x180012f49  mov     ecx, eax; unsigned __int64
0x180012f4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012f52  mov     ebx, eax
0x180012f54  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012f59  mov     rdi, rax
0x180012f5c  test    rax, rax
0x180012f5f  jnz     short loc_180012F66
0x180012f61  lea     ebx, [rax+8]
0x180012f64  jmp     short loc_180012F8B
0x180012f66  mov     r8, [rsi]; pSourceSid
0x180012f69  mov     rdx, rdi; pDestinationSid
0x180012f6c  mov     ecx, ebx; nDestinationSidLength
0x180012f6e  call    cs:__imp_CopySid
0x180012f75  nop     dword ptr [rax+rax+00h]
0x180012f7a  test    eax, eax
0x180012f7c  jz      short loc_180012F2A
0x180012f7e  mov     [r15], rdi
0x180012f81  test    r14, r14
0x180012f84  jz      short loc_180012F89
0x180012f86  mov     [r14], ebx
0x180012f89  xor     ebx, ebx
0x180012f8b  mov     rcx, rsi
0x180012f8e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012f95  nop     dword ptr [rax+rax+00h]
0x180012f9a  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180012f9f  test    rcx, rcx
0x180012fa2  jz      short loc_180012FB0
0x180012fa4  call    cs:__imp_CloseHandle
0x180012fab  nop     dword ptr [rax+rax+00h]
0x180012fb0  test    ebx, ebx
0x180012fb2  jz      short loc_180012FC8
0x180012fb4  test    rdi, rdi
0x180012fb7  jz      short loc_180012FC8
0x180012fb9  mov     rcx, rdi
0x180012fbc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012fc3  nop     dword ptr [rax+rax+00h]
0x180012fc8  mov     rsi, [rsp+48h+arg_8]
0x180012fcd  mov     eax, ebx
0x180012fcf  mov     rbx, [rsp+48h+arg_0]
0x180012fd4  add     rsp, 30h
0x180012fd8  pop     r15
0x180012fda  pop     r14
0x180012fdc  pop     rdi
0x180012fdd  retn
```
