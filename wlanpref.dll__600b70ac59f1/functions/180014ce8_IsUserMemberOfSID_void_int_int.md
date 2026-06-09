# IsUserMemberOfSID(void *,int *,int *)

- ea: `0x180014ce8`
- end: `0x180014ef1`
- name: `?IsUserMemberOfSID@@YAJPEAXPEAH1@Z`
- size: `521`
- prototype: `__int64 __fastcall(PSID pSid1, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014be8`

## callees

- `0x180014ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014d29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014d7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014d7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d3e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180014da8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180014da8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014e04`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014e6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014e04`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014e6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180014ea1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180014ea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ed3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014ec4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014e32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014eb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014e32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014eb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014e40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014e40`

## pseudocode

```c
__int64 __fastcall IsUserMemberOfSID(PSID pSid1, int *a2, int *a3)
{
  signed int v5; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v14; // rsi
  signed int v15; // eax
  unsigned int i; // ebx
  HANDLE v17; // rax
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+50h] BYREF
  int v21; // [rsp+84h] [rbp+54h]
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp+58h] BYREF

  v21 = HIDWORD(a3);
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !pSid1 || !a2 )
    return 2147942487LL;
  v5 = 0;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_17;
  TokenHandle = 0;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    ExistingTokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &ExistingTokenHandle) )
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_35;
    }
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
    {
      TokenHandle = 0;
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
    }
    CloseHandle(ExistingTokenHandle);
  }
  else if ( LastError > 0 )
  {
    v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v5 = LastError;
  }
  if ( v5 >= 0 )
  {
LABEL_17:
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_23;
    v11 = GetLastError();
    if ( v11 != 122 )
    {
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      else
        v5 = v11;
    }
    if ( v5 >= 0 )
    {
LABEL_23:
      v12 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v14 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v12);
      if ( v14 )
      {
        if ( GetTokenInformation(TokenHandle, TokenGroups, v14, TokenInformationLength, &TokenInformationLength) )
          goto LABEL_29;
        v15 = GetLastError();
        v5 = v15;
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_29:
          for ( i = 0; i < *v14; ++i )
          {
            if ( EqualSid(pSid1, *(PSID *)&v14[4 * i + 2]) )
            {
              *a2 = 1;
              break;
            }
          }
        }
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v14);
      }
      else
      {
        v5 = -2147024882;
      }
    }
  }
LABEL_35:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014ce8  mov     qword ptr [rsp-38h+TokenInformationLength], r8
0x180014ced  push    rbp
0x180014cee  push    rbx
0x180014cef  push    rsi
0x180014cf0  push    rdi
0x180014cf1  push    r13
0x180014cf3  push    r14
0x180014cf5  push    r15
0x180014cf7  mov     rbp, rsp
0x180014cfa  sub     rsp, 30h
0x180014cfe  mov     [rbp+TokenHandle], 0
0x180014d06  mov     r14, rdx
0x180014d09  mov     [rbp+TokenInformationLength], 0
0x180014d10  mov     r15, rcx
0x180014d13  test    rcx, rcx
0x180014d16  jz      loc_180014EDD
0x180014d1c  test    rdx, rdx
0x180014d1f  jz      loc_180014EDD
0x180014d25  xor     edi, edi
0x180014d27  mov     [rdx], edi
0x180014d29  call    cs:__imp_GetCurrentThread
0x180014d2f  lea     esi, [rdi+8]
0x180014d32  xor     r8d, r8d; OpenAsSelf
0x180014d35  mov     rcx, rax; ThreadHandle
0x180014d38  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180014d3c  mov     edx, esi; DesiredAccess
0x180014d3e  call    cs:__imp_OpenThreadToken
0x180014d44  lea     ebx, [rdi+2]
0x180014d47  mov     r13d, 80070000h
0x180014d4d  test    eax, eax
0x180014d4f  jnz     loc_180014DEE
0x180014d55  mov     [rbp+TokenHandle], rdi
0x180014d59  call    cs:__imp_GetLastError
0x180014d5f  cmp     eax, 3F0h
0x180014d64  jnz     short loc_180014DD8
0x180014d66  mov     [rbp+ExistingTokenHandle], rdi
0x180014d6a  call    cs:__imp_GetCurrentProcess
0x180014d70  mov     rcx, rax; ProcessHandle
0x180014d73  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x180014d77  lea     edx, [rdi+0Ah]; DesiredAccess
0x180014d7a  call    cs:__imp_OpenProcessToken
0x180014d80  test    eax, eax
0x180014d82  jnz     short loc_180014D9E
0x180014d84  call    cs:__imp_GetLastError
0x180014d8a  mov     edi, eax
0x180014d8c  test    eax, eax
0x180014d8e  jle     short loc_180014D96
0x180014d90  movzx   edi, ax
0x180014d93  or      edi, r13d
0x180014d96  test    edi, edi
0x180014d98  js      loc_180014ECA
0x180014d9e  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x180014da2  lea     r8, [rbp+TokenHandle]; DuplicateTokenHandle
0x180014da6  mov     edx, ebx; ImpersonationLevel
0x180014da8  call    cs:__imp_DuplicateToken
0x180014dae  test    eax, eax
0x180014db0  jnz     short loc_180014DCC
0x180014db2  mov     [rbp+TokenHandle], 0
0x180014dba  call    cs:__imp_GetLastError
0x180014dc0  mov     edi, eax
0x180014dc2  test    eax, eax
0x180014dc4  jle     short loc_180014DCC
0x180014dc6  movzx   edi, ax
0x180014dc9  or      edi, r13d
0x180014dcc  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x180014dd0  call    cs:__imp_CloseHandle
0x180014dd6  jmp     short loc_180014DE6
0x180014dd8  test    eax, eax
0x180014dda  jg      short loc_180014DE0
0x180014ddc  mov     edi, eax
0x180014dde  jmp     short loc_180014DE6
0x180014de0  movzx   edi, ax
0x180014de3  or      edi, r13d
0x180014de6  test    edi, edi
0x180014de8  js      loc_180014ECA
0x180014dee  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180014df2  lea     rax, [rbp+TokenInformationLength]
0x180014df6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180014dfa  xor     r8d, r8d; TokenInformation
0x180014dfd  mov     edx, ebx; TokenInformationClass
0x180014dff  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180014e04  call    cs:__imp_GetTokenInformation
0x180014e0a  test    eax, eax
0x180014e0c  jnz     short loc_180014E2F
0x180014e0e  call    cs:__imp_GetLastError
0x180014e14  cmp     eax, 7Ah ; 'z'
0x180014e17  jz      short loc_180014E27
0x180014e19  test    eax, eax
0x180014e1b  jg      short loc_180014E21
0x180014e1d  mov     edi, eax
0x180014e1f  jmp     short loc_180014E27
0x180014e21  movzx   edi, ax
0x180014e24  or      edi, r13d
0x180014e27  test    edi, edi
0x180014e29  js      loc_180014ECA
0x180014e2f  mov     ebx, [rbp+TokenInformationLength]
0x180014e32  call    cs:__imp_GetProcessHeap
0x180014e38  mov     r8d, ebx; dwBytes
0x180014e3b  mov     edx, esi; dwFlags
0x180014e3d  mov     rcx, rax; hHeap
0x180014e40  call    cs:__imp_HeapAlloc
0x180014e46  mov     rsi, rax
0x180014e49  test    rax, rax
0x180014e4c  jnz     short loc_180014E55
0x180014e4e  mov     edi, 8007000Eh
0x180014e53  jmp     short loc_180014ECA
0x180014e55  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180014e59  lea     rax, [rbp+TokenInformationLength]
0x180014e5d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180014e61  mov     r8, rsi; TokenInformation
0x180014e64  mov     edx, 2; TokenInformationClass
0x180014e69  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180014e6e  call    cs:__imp_GetTokenInformation
0x180014e74  test    eax, eax
0x180014e76  jnz     short loc_180014E8E
0x180014e78  call    cs:__imp_GetLastError
0x180014e7e  mov     edi, eax
0x180014e80  test    eax, eax
0x180014e82  jle     short loc_180014E8A
0x180014e84  movzx   edi, ax
0x180014e87  or      edi, r13d
0x180014e8a  test    edi, edi
0x180014e8c  js      short loc_180014EB6
0x180014e8e  xor     ebx, ebx
0x180014e90  cmp     ebx, [rsi]
0x180014e92  jnb     short loc_180014EB6
0x180014e94  mov     edx, ebx
0x180014e96  mov     rcx, r15; pSid1
0x180014e99  add     rdx, rdx
0x180014e9c  mov     rdx, [rsi+rdx*8+8]; pSid2
0x180014ea1  call    cs:__imp_EqualSid
0x180014ea7  test    eax, eax
0x180014ea9  jnz     short loc_180014EAF
0x180014eab  inc     ebx
0x180014ead  jmp     short loc_180014E90
0x180014eaf  mov     dword ptr [r14], 1
0x180014eb6  call    cs:__imp_GetProcessHeap
0x180014ebc  mov     r8, rsi; lpMem
0x180014ebf  xor     edx, edx; dwFlags
0x180014ec1  mov     rcx, rax; hHeap
0x180014ec4  call    cs:__imp_HeapFree
0x180014eca  mov     rcx, [rbp+TokenHandle]; hObject
0x180014ece  test    rcx, rcx
0x180014ed1  jz      short loc_180014ED9
0x180014ed3  call    cs:__imp_CloseHandle
0x180014ed9  mov     eax, edi
0x180014edb  jmp     short loc_180014EE2
0x180014edd  mov     eax, 80070057h
0x180014ee2  add     rsp, 30h
0x180014ee6  pop     r15
0x180014ee8  pop     r14
0x180014eea  pop     r13
0x180014eec  pop     rdi
0x180014eed  pop     rsi
0x180014eee  pop     rbx
0x180014eef  pop     rbp
0x180014ef0  retn
```
