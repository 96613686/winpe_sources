# IsUserInAdminGroup(void)

- ea: `0x180116830`
- end: `0x1801169f7`
- name: `?IsUserInAdminGroup@@YAHXZ`
- size: `455`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010d020`
- `0x18010e5d0`

## callees

- `0x180116830`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011689b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011689b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180116871`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180116871`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801168b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801168b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011688b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011688b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801169ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801169cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801169ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801169cb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180116962`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180116962`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801168e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011691b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801168e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18011691b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180116981`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180116981`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18011693e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18011693e`

## pseudocode

```c
__int64 IsUserInAdminGroup(void)
{
  __int64 result; // rax
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-2Dh] BYREF
  WINBOOL IsMember; // [rsp+40h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-21h] BYREF
  DWORD cbSid[4]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF

  result = (unsigned int)dword_1801675A0;
  DuplicateTokenHandle = 0;
  TokenHandle = 0;
  if ( dword_1801675A0 == 2 )
  {
    v1 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle)
      || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle)) )
    {
      TokenInformation = 0;
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
      {
        if ( (TokenInformation != 3
           || GetTokenInformation(TokenHandle, TokenLinkedToken, &DuplicateTokenHandle, 8u, &ReturnLength))
          && (DuplicateTokenHandle || DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle)) )
        {
          cbSid[0] = 68;
          if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
          {
            IsMember = 0;
            if ( CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember) )
            {
              if ( IsMember )
              {
                dword_1801675A0 = 1;
                v1 = 1;
              }
            }
          }
        }
      }
    }
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( DuplicateTokenHandle )
      CloseHandle(DuplicateTokenHandle);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180116830  mov     [rsp-8+arg_0], rbx
0x180116835  push    rbp
0x180116836  lea     rbp, [rsp-57h]
0x18011683b  sub     rsp, 0C0h
0x180116842  mov     rax, cs:__security_cookie
0x180116849  xor     rax, rsp
0x18011684c  mov     [rbp+57h+var_10], rax
0x180116850  mov     eax, cs:dword_1801675A0
0x180116856  mov     [rbp+57h+DuplicateTokenHandle], 0
0x18011685e  mov     [rbp+57h+TokenHandle], 0
0x180116866  cmp     eax, 2
0x180116869  jnz     loc_1801169D9
0x18011686f  xor     ebx, ebx
0x180116871  call    cs:__imp_GetCurrentThread
0x180116878  nop     dword ptr [rax+rax+00h]
0x18011687d  mov     rcx, rax; ThreadHandle
0x180116880  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180116884  lea     edx, [rbx+0Ah]; DesiredAccess
0x180116887  lea     r8d, [rbx+1]; OpenAsSelf
0x18011688b  call    cs:__imp_OpenThreadToken
0x180116892  nop     dword ptr [rax+rax+00h]
0x180116897  test    eax, eax
0x180116899  jnz     short loc_1801168C5
0x18011689b  call    cs:__imp_GetCurrentProcess
0x1801168a2  nop     dword ptr [rax+rax+00h]
0x1801168a7  mov     rcx, rax; ProcessHandle
0x1801168aa  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1801168ae  lea     edx, [rbx+0Ah]; DesiredAccess
0x1801168b1  call    cs:__imp_OpenProcessToken
0x1801168b8  nop     dword ptr [rax+rax+00h]
0x1801168bd  test    eax, eax
0x1801168bf  jz      loc_1801169A5
0x1801168c5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801168c9  lea     rax, [rbp+57h+var_84]
0x1801168cd  mov     r9d, 4; TokenInformationLength
0x1801168d3  mov     [rbp+57h+TokenInformation], ebx
0x1801168d6  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1801168da  mov     [rbp+57h+var_84], ebx
0x1801168dd  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1801168e2  lea     edx, [r9+0Eh]; TokenInformationClass
0x1801168e6  call    cs:__imp_GetTokenInformation
0x1801168ed  nop     dword ptr [rax+rax+00h]
0x1801168f2  test    eax, eax
0x1801168f4  jz      loc_1801169A5
0x1801168fa  cmp     [rbp+57h+TokenInformation], 3
0x1801168fe  jnz     short loc_18011692B
0x180116900  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180116904  lea     rax, [rbp+57h+var_84]
0x180116908  mov     r9d, 8; TokenInformationLength
0x18011690e  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180116913  lea     r8, [rbp+57h+DuplicateTokenHandle]; TokenInformation
0x180116917  lea     edx, [r9+0Bh]; TokenInformationClass
0x18011691b  call    cs:__imp_GetTokenInformation
0x180116922  nop     dword ptr [rax+rax+00h]
0x180116927  test    eax, eax
0x180116929  jz      short loc_1801169A5
0x18011692b  cmp     [rbp+57h+DuplicateTokenHandle], rbx
0x18011692f  jnz     short loc_18011694E
0x180116931  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180116935  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180116939  mov     edx, 1; ImpersonationLevel
0x18011693e  call    cs:__imp_DuplicateToken
0x180116945  nop     dword ptr [rax+rax+00h]
0x18011694a  test    eax, eax
0x18011694c  jz      short loc_1801169A5
0x18011694e  xor     edx, edx; DomainSid
0x180116950  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180116957  lea     r9, [rbp+57h+cbSid]; cbSid
0x18011695b  lea     r8, [rbp+57h+pSid]; pSid
0x18011695f  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180116962  call    cs:__imp_CreateWellKnownSid
0x180116969  nop     dword ptr [rax+rax+00h]
0x18011696e  test    eax, eax
0x180116970  jz      short loc_1801169A5
0x180116972  mov     rcx, [rbp+57h+DuplicateTokenHandle]; TokenHandle
0x180116976  lea     r8, [rbp+57h+IsMember]; IsMember
0x18011697a  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18011697e  mov     [rbp+57h+IsMember], ebx
0x180116981  call    cs:__imp_CheckTokenMembership
0x180116988  nop     dword ptr [rax+rax+00h]
0x18011698d  test    eax, eax
0x18011698f  jz      short loc_1801169A5
0x180116991  cmp     [rbp+57h+IsMember], ebx
0x180116994  jz      short loc_1801169A5
0x180116996  mov     cs:dword_1801675A0, 1
0x1801169a0  mov     ebx, 1
0x1801169a5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1801169a9  test    rcx, rcx
0x1801169ac  jz      short loc_1801169C2
0x1801169ae  call    cs:__imp_CloseHandle
0x1801169b5  nop     dword ptr [rax+rax+00h]
0x1801169ba  mov     [rbp+57h+TokenHandle], 0
0x1801169c2  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x1801169c6  test    rcx, rcx
0x1801169c9  jz      short loc_1801169D7
0x1801169cb  call    cs:__imp_CloseHandle
0x1801169d2  nop     dword ptr [rax+rax+00h]
0x1801169d7  mov     eax, ebx
0x1801169d9  mov     rcx, [rbp+57h+var_10]
0x1801169dd  xor     rcx, rsp; StackCookie
0x1801169e0  call    __security_check_cookie
0x1801169e5  mov     rbx, [rsp+0C0h+arg_0]
0x1801169ed  add     rsp, 0C0h
0x1801169f4  pop     rbp
0x1801169f5  retn
```
