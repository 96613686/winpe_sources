# CScriptedDiag::ImpersonateActiveUser(void)

- ea: `0x18000cd40`
- end: `0x18000cefa`
- name: `?ImpersonateActiveUser@CScriptedDiag@@AEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d63c`

## callees

- `0x18000cd40`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cde8`
- `KERNEL32!GetLastError` at `0x18000ce0f`
- `KERNEL32!GetLastError` at `0x18000ce4a`
- `KERNEL32!GetLastError` at `0x18000ce88`
- `KERNEL32!GetLastError` at `0x18000ceaa`
- `KERNEL32!GetLastError` at `0x18000cde8`
- `KERNEL32!GetLastError` at `0x18000ce0f`
- `KERNEL32!GetLastError` at `0x18000ce4a`
- `KERNEL32!GetLastError` at `0x18000ce88`
- `KERNEL32!GetLastError` at `0x18000ceaa`
- `KERNEL32!CloseHandle` at `0x18000ced7`
- `KERNEL32!CloseHandle` at `0x18000cee6`
- `KERNEL32!CloseHandle` at `0x18000ced7`
- `KERNEL32!CloseHandle` at `0x18000cee6`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x18000cddb`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x18000cddb`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000cea0`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000cea0`
- `ADVAPI32!DuplicateTokenEx` at `0x18000ce7e`
- `ADVAPI32!DuplicateTokenEx` at `0x18000ce7e`
- `ADVAPI32!GetTokenInformation` at `0x18000ce40`
- `ADVAPI32!GetTokenInformation` at `0x18000ce40`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18000cd87`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18000cd87`
- `WTSAPI32!WTSFreeMemory` at `0x18000cd9e`
- `WTSAPI32!WTSFreeMemory` at `0x18000cdd0`
- `WTSAPI32!WTSFreeMemory` at `0x18000cd9e`
- `WTSAPI32!WTSFreeMemory` at `0x18000cdd0`
- `WTSAPI32!WTSQueryUserToken` at `0x18000ce05`
- `WTSAPI32!WTSQueryUserToken` at `0x18000ce05`

## string_xrefs

- `0x18000cebf`: `CScriptedDiag::ImpersonateActiveUser`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::ImpersonateActiveUser(CScriptedDiag *this)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  ULONG i; // edi
  signed int LastError; // eax
  int v5; // r8d
  HANDLE hToken; // [rsp+30h] [rbp-10h] BYREF
  HANDLE TokenInformation; // [rsp+38h] [rbp-8h] BYREF
  DWORD pCount; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+74h] [rbp+34h]
  DWORD ReturnLength; // [rsp+78h] [rbp+38h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+80h] [rbp+40h] BYREF
  void *phToken; // [rsp+88h] [rbp+48h] BYREF

  v10 = HIDWORD(this);
  v1 = 0;
  ReturnLength = 8;
  phToken = 0;
  hToken = 0;
  TokenInformation = 0;
  ppSessionInfo = 0;
  pCount = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v2 = 0;
    for ( i = -1; (unsigned int)v2 < pCount; v2 = (unsigned int)(v2 + 1) )
    {
      if ( ppSessionInfo[v2].State == WTSActive )
      {
        if ( i != -1 )
          goto LABEL_3;
        i = ppSessionInfo[v2].SessionId;
      }
    }
    WTSFreeMemory(ppSessionInfo);
    if ( i != -1 )
      goto LABEL_13;
  }
  else if ( ppSessionInfo )
  {
LABEL_3:
    WTSFreeMemory(ppSessionInfo);
  }
  i = WTSGetActiveConsoleSessionId();
  if ( i == -1 )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError < 0 )
    {
      v5 = 1007;
LABEL_25:
      SdpDebugTrace(1u, L"CScriptedDiag::ImpersonateActiveUser", v5, LastError);
      goto LABEL_26;
    }
  }
LABEL_13:
  if ( !WTSQueryUserToken(i, &phToken) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError < 0 )
    {
      v5 = 1013;
      goto LABEL_25;
    }
  }
  if ( !GetTokenInformation(phToken, TokenLinkedToken, &TokenInformation, ReturnLength, &ReturnLength) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError < 0 )
    {
      v5 = 1025;
      goto LABEL_25;
    }
  }
  if ( !DuplicateTokenEx(TokenInformation, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError < 0 )
    {
      v5 = 1037;
      goto LABEL_25;
    }
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError < 0 )
    {
      v5 = 1043;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( phToken )
    CloseHandle(phToken);
  if ( hToken )
    CloseHandle(hToken);
  return v1;
}

```

## disassembly

```asm
0x18000cd40  mov     qword ptr [rsp-28h+arg_0], rcx
0x18000cd45  push    rbp
0x18000cd46  push    rbx
0x18000cd47  push    rdi
0x18000cd48  push    r14
0x18000cd4a  push    r15
0x18000cd4c  mov     rbp, rsp
0x18000cd4f  sub     rsp, 40h
0x18000cd53  xor     ebx, ebx
0x18000cd55  mov     [rbp+ReturnLength], 8
0x18000cd5c  lea     rax, [rbp+arg_0]
0x18000cd60  mov     [rbp+phToken], rbx
0x18000cd64  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18000cd68  mov     [rbp+hToken], rbx
0x18000cd6c  xor     edx, edx; Reserved
0x18000cd6e  mov     [rbp+TokenInformation], rbx
0x18000cd72  lea     r14d, [rbx+1]
0x18000cd76  mov     [rbp+ppSessionInfo], rbx
0x18000cd7a  mov     r8d, r14d; Version
0x18000cd7d  mov     [rbp+arg_0], ebx
0x18000cd80  xor     ecx, ecx; hServer
0x18000cd82  mov     [rsp+40h+pCount], rax; pCount
0x18000cd87  call    cs:__imp_WTSEnumerateSessionsW
0x18000cd8d  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18000cd91  or      r15d, 0FFFFFFFFh
0x18000cd95  test    eax, eax
0x18000cd97  jnz     short loc_18000CDA6
0x18000cd99  test    rcx, rcx
0x18000cd9c  jz      short loc_18000CDDB
0x18000cd9e  call    cs:__imp_WTSFreeMemory
0x18000cda4  jmp     short loc_18000CDDB
0x18000cda6  mov     r8d, [rbp+arg_0]
0x18000cdaa  xor     edx, edx
0x18000cdac  mov     edi, r15d
0x18000cdaf  test    r8d, r8d
0x18000cdb2  jz      short loc_18000CDD0
0x18000cdb4  lea     r9, [rdx+rdx*2]
0x18000cdb8  cmp     [rcx+r9*8+10h], ebx
0x18000cdbd  jnz     short loc_18000CDC8
0x18000cdbf  cmp     edi, r15d
0x18000cdc2  jnz     short loc_18000CD9E
0x18000cdc4  mov     edi, [rcx+r9*8]
0x18000cdc8  add     edx, r14d
0x18000cdcb  cmp     edx, r8d
0x18000cdce  jb      short loc_18000CDB4
0x18000cdd0  call    cs:__imp_WTSFreeMemory
0x18000cdd6  cmp     edi, r15d
0x18000cdd9  jnz     short loc_18000CDFF
0x18000cddb  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18000cde1  mov     edi, eax
0x18000cde3  cmp     eax, r15d
0x18000cde6  jnz     short loc_18000CDFF
0x18000cde8  call    cs:__imp_GetLastError
0x18000cdee  mov     ebx, eax
0x18000cdf0  test    eax, eax
0x18000cdf2  jns     short loc_18000CDFF
0x18000cdf4  mov     r8d, 3EFh
0x18000cdfa  jmp     loc_18000CEBC
0x18000cdff  lea     rdx, [rbp+phToken]; phToken
0x18000ce03  mov     ecx, edi; SessionId
0x18000ce05  call    cs:__imp_WTSQueryUserToken
0x18000ce0b  test    eax, eax
0x18000ce0d  jnz     short loc_18000CE26
0x18000ce0f  call    cs:__imp_GetLastError
0x18000ce15  mov     ebx, eax
0x18000ce17  test    eax, eax
0x18000ce19  jns     short loc_18000CE26
0x18000ce1b  mov     r8d, 3F5h
0x18000ce21  jmp     loc_18000CEBC
0x18000ce26  mov     r9d, [rbp+ReturnLength]; TokenInformationLength
0x18000ce2a  lea     rax, [rbp+ReturnLength]
0x18000ce2e  mov     rcx, [rbp+phToken]; TokenHandle
0x18000ce32  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000ce36  mov     edx, 13h; TokenInformationClass
0x18000ce3b  mov     [rsp+40h+pCount], rax; ReturnLength
0x18000ce40  call    cs:__imp_GetTokenInformation
0x18000ce46  test    eax, eax
0x18000ce48  jnz     short loc_18000CE5E
0x18000ce4a  call    cs:__imp_GetLastError
0x18000ce50  mov     ebx, eax
0x18000ce52  test    eax, eax
0x18000ce54  jns     short loc_18000CE5E
0x18000ce56  mov     r8d, 401h
0x18000ce5c  jmp     short loc_18000CEBC
0x18000ce5e  mov     rcx, [rbp+TokenInformation]; hExistingToken
0x18000ce62  lea     rax, [rbp+hToken]
0x18000ce66  mov     [rsp+40h+phNewToken], rax; phNewToken
0x18000ce6b  mov     r9d, 2; ImpersonationLevel
0x18000ce71  xor     r8d, r8d; lpTokenAttributes
0x18000ce74  mov     dword ptr [rsp+40h+pCount], r14d; TokenType
0x18000ce79  mov     edx, 2000000h; dwDesiredAccess
0x18000ce7e  call    cs:__imp_DuplicateTokenEx
0x18000ce84  test    eax, eax
0x18000ce86  jnz     short loc_18000CE9C
0x18000ce88  call    cs:__imp_GetLastError
0x18000ce8e  mov     ebx, eax
0x18000ce90  test    eax, eax
0x18000ce92  jns     short loc_18000CE9C
0x18000ce94  mov     r8d, 40Dh
0x18000ce9a  jmp     short loc_18000CEBC
0x18000ce9c  mov     rcx, [rbp+hToken]; hToken
0x18000cea0  call    cs:__imp_ImpersonateLoggedOnUser
0x18000cea6  test    eax, eax
0x18000cea8  jnz     short loc_18000CECE
0x18000ceaa  call    cs:__imp_GetLastError
0x18000ceb0  mov     ebx, eax
0x18000ceb2  test    eax, eax
0x18000ceb4  jns     short loc_18000CECE
0x18000ceb6  mov     r8d, 413h; int
0x18000cebc  mov     r9d, eax; int
0x18000cebf  lea     rdx, aCscripteddiagI_5; "CScriptedDiag::ImpersonateActiveUser"
0x18000cec6  mov     ecx, r14d; Level
0x18000cec9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000cece  mov     rcx, [rbp+phToken]; hObject
0x18000ced2  test    rcx, rcx
0x18000ced5  jz      short loc_18000CEDD
0x18000ced7  call    cs:__imp_CloseHandle
0x18000cedd  mov     rcx, [rbp+hToken]; hObject
0x18000cee1  test    rcx, rcx
0x18000cee4  jz      short loc_18000CEEC
0x18000cee6  call    cs:__imp_CloseHandle
0x18000ceec  mov     eax, ebx
0x18000ceee  add     rsp, 40h
0x18000cef2  pop     r15
0x18000cef4  pop     r14
0x18000cef6  pop     rdi
0x18000cef7  pop     rbx
0x18000cef8  pop     rbp
0x18000cef9  retn
```
