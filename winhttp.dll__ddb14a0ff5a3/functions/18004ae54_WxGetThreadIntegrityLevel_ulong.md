# WxGetThreadIntegrityLevel(ulong *)

- ea: `0x18004ae54`
- end: `0x18004b003`
- name: `?WxGetThreadIntegrityLevel@@YAJPEAK@Z`
- size: `431`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021320`
- `0x18004b128`

## callees

- `0x18004ae54`
- `0x1800a1d10`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004aeea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004aeea`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18004aefe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18004aefe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004af0f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18004af0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004af57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004af57`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004aea5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004aea5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ae8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ae8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004af66`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004af66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004afcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004af2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004af2a`

## pseudocode

```c
__int64 __fastcall WxGetThreadIntegrityLevel(unsigned int *a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rbx
  signed int v4; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v6; // edi
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  int v13; // [rsp+34h] [rbp-55h]
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  PSID TokenInformation[14]; // [rsp+40h] [rbp-49h] BYREF

  v13 = 0;
  TokenHandle = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    goto LABEL_2;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
LABEL_2:
      v3 = TokenHandle;
      v13 = 0;
      memset_0(TokenInformation, 0, 0x6Cu);
      ReturnLength = 108;
      if ( GetTokenInformation(v3, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
      {
        v4 = 0;
        SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
        v6 = *GetSidSubAuthority(TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
      }
      else
      {
        v6 = 4096;
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v13 = 307;
        if ( v4 >= 0 )
          v4 = -2147418113;
      }
      if ( v4 < 0 )
        v13 = 222;
      else
        *a1 = v6;
      goto LABEL_6;
    }
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v13 = 219;
    if ( v4 >= 0 )
      v4 = -2147418113;
  }
  else
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    v13 = 217;
    if ( v4 >= 0 )
      v4 = -2147418113;
  }
LABEL_6:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004ae54  push    rbp
0x18004ae56  push    rbx
0x18004ae57  push    rsi
0x18004ae58  push    rdi
0x18004ae59  lea     rbp, [rsp-3Fh]
0x18004ae5e  sub     rsp, 0C8h
0x18004ae65  mov     rax, cs:__security_cookie
0x18004ae6c  xor     rax, rsp
0x18004ae6f  mov     [rbp+57h+var_30], rax
0x18004ae73  mov     rsi, rcx
0x18004ae76  mov     [rbp+57h+var_AC], 0
0x18004ae7d  mov     [rbp+57h+TokenHandle], 0
0x18004ae85  mov     dword ptr [rcx], 0
0x18004ae8b  call    cs:__imp_GetCurrentThread
0x18004ae91  mov     ebx, 20008h
0x18004ae96  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004ae9a  mov     edx, ebx; DesiredAccess
0x18004ae9c  mov     rcx, rax; ThreadHandle
0x18004ae9f  mov     r8d, 1; OpenAsSelf
0x18004aea5  call    cs:__imp_OpenThreadToken
0x18004aeab  test    eax, eax
0x18004aead  jz      loc_18004AF4A
0x18004aeb3  mov     rbx, [rbp+57h+TokenHandle]
0x18004aeb7  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18004aebb  mov     edi, 6Ch ; 'l'
0x18004aec0  mov     [rbp+57h+var_AC], 0
0x18004aec7  mov     r8d, edi; Size
0x18004aeca  xor     edx, edx; Val
0x18004aecc  call    memset_0
0x18004aed1  lea     rax, [rbp+57h+var_B0]
0x18004aed5  mov     [rbp+57h+var_B0], edi
0x18004aed8  mov     r9d, edi; TokenInformationLength
0x18004aedb  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18004aee0  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18004aee4  mov     rcx, rbx; TokenHandle
0x18004aee7  lea     edx, [rdi-53h]; TokenInformationClass
0x18004aeea  call    cs:__imp_GetTokenInformation
0x18004aef0  test    eax, eax
0x18004aef2  jz      loc_18004AFC7
0x18004aef8  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18004aefc  xor     ebx, ebx
0x18004aefe  call    cs:__imp_GetSidSubAuthorityCount
0x18004af04  mov     cl, [rax]
0x18004af06  dec     cl
0x18004af08  movzx   edx, cl; nSubAuthority
0x18004af0b  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18004af0f  call    cs:__imp_GetSidSubAuthority
0x18004af15  mov     edi, [rax]
0x18004af17  test    ebx, ebx
0x18004af19  js      loc_18004AFF7
0x18004af1f  mov     [rsi], edi
0x18004af21  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18004af25  test    rcx, rcx
0x18004af28  jz      short loc_18004AF30
0x18004af2a  call    cs:__imp_CloseHandle
0x18004af30  mov     eax, ebx
0x18004af32  mov     rcx, [rbp+57h+var_30]
0x18004af36  xor     rcx, rsp; StackCookie
0x18004af39  call    __security_check_cookie
0x18004af3e  add     rsp, 0C8h
0x18004af45  pop     rdi
0x18004af46  pop     rsi
0x18004af47  pop     rbx
0x18004af48  pop     rbp
0x18004af49  retn
0x18004af4a  call    cs:__imp_GetLastError
0x18004af50  cmp     eax, 3F0h
0x18004af55  jnz     short loc_18004AF9C
0x18004af57  call    cs:__imp_GetCurrentProcess
0x18004af5d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18004af61  mov     edx, ebx; DesiredAccess
0x18004af63  mov     rcx, rax; ProcessHandle
0x18004af66  call    cs:__imp_OpenProcessToken
0x18004af6c  test    eax, eax
0x18004af6e  jnz     loc_18004AEB3
0x18004af74  call    cs:__imp_GetLastError
0x18004af7a  mov     ebx, eax
0x18004af7c  test    eax, eax
0x18004af7e  jle     short loc_18004AF89
0x18004af80  movzx   ebx, ax
0x18004af83  or      ebx, 80070000h
0x18004af89  test    ebx, ebx
0x18004af8b  mov     [rbp+57h+var_AC], 0DBh
0x18004af92  mov     eax, 8000FFFFh
0x18004af97  cmovns  ebx, eax
0x18004af9a  jmp     short loc_18004AF21
0x18004af9c  call    cs:__imp_GetLastError
0x18004afa2  mov     ebx, eax
0x18004afa4  test    eax, eax
0x18004afa6  jle     short loc_18004AFB1
0x18004afa8  movzx   ebx, ax
0x18004afab  or      ebx, 80070000h
0x18004afb1  test    ebx, ebx
0x18004afb3  mov     [rbp+57h+var_AC], 0D9h
0x18004afba  mov     eax, 8000FFFFh
0x18004afbf  cmovns  ebx, eax
0x18004afc2  jmp     loc_18004AF21
0x18004afc7  mov     edi, 1000h
0x18004afcc  call    cs:__imp_GetLastError
0x18004afd2  mov     ebx, eax
0x18004afd4  test    eax, eax
0x18004afd6  jle     short loc_18004AFE1
0x18004afd8  movzx   ebx, ax
0x18004afdb  or      ebx, 80070000h
0x18004afe1  test    ebx, ebx
0x18004afe3  mov     [rbp+57h+var_AC], 133h
0x18004afea  mov     eax, 8000FFFFh
0x18004afef  cmovns  ebx, eax
0x18004aff2  jmp     loc_18004AF17
0x18004aff7  mov     [rbp+57h+var_AC], 0DEh
0x18004affe  jmp     loc_18004AF21
```
