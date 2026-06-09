# PfSvGetPrefetchServiceThreadPrivileges

- ea: `0x18005c148`
- end: `0x18005c237`
- name: `PfSvGetPrefetchServiceThreadPrivileges`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002afe0`
- `0x180055f70`
- `0x18005c08c`
- `0x18006c5a0`
- `0x1800737d4`
- `0x1800a3490`

## callees

- `0x18005c148`
- `0x18006168c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c16f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c215`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c215`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c194`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c17f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c17f`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005c162`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005c162`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c224`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c224`

## pseudocode

```c
__int64 __fastcall PfSvGetPrefetchServiceThreadPrivileges(char a1)
{
  char v2; // di
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( !ImpersonateSelf(SecurityImpersonation) )
  {
    v2 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_14;
  }
  v2 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20u, 0, &TokenHandle)
    || (a1 & 1) != 0
    && (!(unsigned int)PfSvSetPrivilege(TokenHandle, v5, 13)
     || !(unsigned int)PfSvSetPrivilege(TokenHandle, v6, 9)
     || !(unsigned int)PfSvSetPrivilege(TokenHandle, v7, 14)) )
  {
    goto LABEL_3;
  }
  if ( (a1 & 2) != 0 )
    PfSvSetPrivilege(TokenHandle, v5, 7);
  if ( (a1 & 4) != 0 )
    PfSvSetPrivilege(TokenHandle, v5, 20);
  LastError = 0;
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( LastError && v2 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x18005c148  mov     [rsp+arg_0], rbx
0x18005c14d  push    rdi
0x18005c14e  sub     rsp, 20h
0x18005c152  mov     ebx, ecx
0x18005c154  mov     [rsp+28h+TokenHandle], 0
0x18005c15d  mov     ecx, 2; ImpersonationLevel
0x18005c162  call    cs:__imp_ImpersonateSelf
0x18005c168  test    eax, eax
0x18005c16a  jnz     short loc_18005C17C
0x18005c16c  xor     dil, dil
0x18005c16f  call    cs:__imp_GetLastError
0x18005c175  mov     ebx, eax
0x18005c177  jmp     loc_18005C20B
0x18005c17c  mov     dil, 1
0x18005c17f  call    cs:__imp_GetCurrentThread
0x18005c185  xor     r8d, r8d; OpenAsSelf
0x18005c188  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18005c18d  mov     rcx, rax; ThreadHandle
0x18005c190  lea     edx, [r8+20h]; DesiredAccess
0x18005c194  call    cs:__imp_OpenThreadToken
0x18005c19a  test    eax, eax
0x18005c19c  jz      short loc_18005C16F
0x18005c19e  test    dil, bl
0x18005c1a1  jz      short loc_18005C1DF
0x18005c1a3  mov     rcx, [rsp+28h+TokenHandle]
0x18005c1a8  mov     r8d, 0Dh
0x18005c1ae  call    PfSvSetPrivilege
0x18005c1b3  test    eax, eax
0x18005c1b5  jz      short loc_18005C16F
0x18005c1b7  mov     rcx, [rsp+28h+TokenHandle]
0x18005c1bc  mov     r8d, 9
0x18005c1c2  call    PfSvSetPrivilege
0x18005c1c7  test    eax, eax
0x18005c1c9  jz      short loc_18005C16F
0x18005c1cb  mov     rcx, [rsp+28h+TokenHandle]
0x18005c1d0  mov     r8d, 0Eh
0x18005c1d6  call    PfSvSetPrivilege
0x18005c1db  test    eax, eax
0x18005c1dd  jz      short loc_18005C16F
0x18005c1df  test    bl, 2
0x18005c1e2  jz      short loc_18005C1F4
0x18005c1e4  mov     rcx, [rsp+28h+TokenHandle]
0x18005c1e9  mov     r8d, 7
0x18005c1ef  call    PfSvSetPrivilege
0x18005c1f4  test    bl, 4
0x18005c1f7  jz      short loc_18005C209
0x18005c1f9  mov     rcx, [rsp+28h+TokenHandle]
0x18005c1fe  mov     r8d, 14h
0x18005c204  call    PfSvSetPrivilege
0x18005c209  xor     ebx, ebx
0x18005c20b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18005c210  test    rcx, rcx
0x18005c213  jz      short loc_18005C21B
0x18005c215  call    cs:__imp_CloseHandle
0x18005c21b  test    ebx, ebx
0x18005c21d  jz      short loc_18005C22A
0x18005c21f  test    dil, dil
0x18005c222  jz      short loc_18005C22A
0x18005c224  call    cs:__imp_RevertToSelf
0x18005c22a  mov     eax, ebx
0x18005c22c  mov     rbx, [rsp+28h+arg_0]
0x18005c231  add     rsp, 20h
0x18005c235  pop     rdi
0x18005c236  retn
```
