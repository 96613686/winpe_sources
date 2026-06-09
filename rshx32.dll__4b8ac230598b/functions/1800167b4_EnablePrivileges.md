# EnablePrivileges

- ea: `0x1800167b4`
- end: `0x180016959`
- name: `EnablePrivileges`
- size: `421`
- prototype: `__int64 __fastcall(DWORD *, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007e00`
- `0x18000a0e4`
- `0x18000a440`

## callees

- `0x1800167b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001686a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001686a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016939`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016939`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800167f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800167f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016855`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016855`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800168fa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800168fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001687b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001687b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016842`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016842`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001688b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001688b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016906`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016923`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016906`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016923`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800168e8`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800168e8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800168be`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800168be`

## pseudocode

```c
__int64 __fastcall EnablePrivileges(DWORD *a1, DWORD a2)
{
  DWORD *v3; // rdi
  struct _TOKEN_PRIVILEGES *v4; // rax
  struct _TOKEN_PRIVILEGES *v5; // r14
  DWORD v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // rax
  HANDLE CurrentThread; // rax
  BOOL v10; // esi
  void *v11; // rcx
  __int64 v12; // rbx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  HANDLE Token; // [rsp+70h] [rbp+40h] BYREF

  TokenHandle = 0;
  v3 = a1;
  if ( a1 )
  {
    v4 = (struct _TOKEN_PRIVILEGES *)LocalAlloc(0x40u, 12 * (a2 - 1) + 16);
    v5 = v4;
    if ( v4 )
    {
      v6 = 0;
      v4->PrivilegeCount = a2;
      if ( a2 )
      {
        v7 = 0;
        do
        {
          v8 = v7++;
          v5->Privileges[v8].Luid.LowPart = *v3;
          ++v6;
          v5->Privileges[v8].Luid.HighPart = 0;
          v5->Privileges[v8].Attributes = 2;
          ++v3;
        }
        while ( v6 < a2 );
      }
      TokenHandle = (void *)-1LL;
      CurrentThread = GetCurrentThread();
      v10 = OpenThreadToken(CurrentThread, 2u, 0, &TokenHandle);
      if ( v10 )
      {
        v11 = TokenHandle;
        v12 = (__int64)TokenHandle;
      }
      else
      {
        if ( GetLastError() != 1008 )
          goto LABEL_17;
        CurrentProcess = GetCurrentProcess();
        v10 = OpenProcessToken(CurrentProcess, 2u, &TokenHandle);
        v12 = -1;
        if ( !v10 )
          goto LABEL_17;
        v11 = TokenHandle;
      }
      Token = 0;
      v10 = DuplicateTokenEx(v11, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token);
      if ( v10 )
      {
        v10 = AdjustTokenPrivileges(Token, 0, v5, 0, 0, 0);
        if ( v10 )
          v10 = SetThreadToken(0, Token);
        CloseHandle(Token);
        if ( v10 )
        {
          if ( v12 != -1 )
          {
LABEL_21:
            if ( v12 == -1 )
              v12 = 0;
LABEL_23:
            LocalFree(v5);
            return v12;
          }
LABEL_18:
          if ( TokenHandle != (void *)-1LL )
            CloseHandle(TokenHandle);
          if ( !v10 )
            goto LABEL_23;
          goto LABEL_21;
        }
      }
LABEL_17:
      v12 = -1;
      goto LABEL_18;
    }
  }
  return -1;
}

```

## disassembly

```asm
0x1800167b4  mov     [rsp-28h+arg_8], rbx
0x1800167b9  push    rbp
0x1800167ba  push    rsi
0x1800167bb  push    rdi
0x1800167bc  push    r12
0x1800167be  push    r14
0x1800167c0  mov     rbp, rsp
0x1800167c3  sub     rsp, 30h
0x1800167c7  mov     [rbp+TokenHandle], 0
0x1800167cf  mov     ebx, edx
0x1800167d1  mov     rdi, rcx
0x1800167d4  test    rcx, rcx
0x1800167d7  jz      loc_180016944
0x1800167dd  lea     eax, [rdx-1]
0x1800167e0  mov     ecx, 40h ; '@'; uFlags
0x1800167e5  lea     r8d, [rax+rax*2]
0x1800167e9  lea     edx, ds:10h[r8*4]; uBytes
0x1800167f1  call    cs:__imp_LocalAlloc
0x1800167f7  mov     r14, rax
0x1800167fa  test    rax, rax
0x1800167fd  jz      loc_180016944
0x180016803  xor     r8d, r8d
0x180016806  mov     [rax], ebx
0x180016808  lea     r12d, [r8+2]
0x18001680c  test    ebx, ebx
0x18001680e  jz      short loc_18001683A
0x180016810  xor     edx, edx
0x180016812  mov     ecx, [rdi]
0x180016814  lea     rax, [rdx+rdx*2]
0x180016818  inc     rdx
0x18001681b  mov     [r14+rax*4+4], ecx
0x180016820  inc     r8d
0x180016823  mov     dword ptr [r14+rax*4+8], 0
0x18001682c  mov     [r14+rax*4+0Ch], r12d
0x180016831  lea     rdi, [rdi+4]
0x180016835  cmp     r8d, ebx
0x180016838  jb      short loc_180016812
0x18001683a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001683e  mov     [rbp+TokenHandle], rdi
0x180016842  call    cs:__imp_GetCurrentThread
0x180016848  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001684c  xor     r8d, r8d; OpenAsSelf
0x18001684f  mov     rcx, rax; ThreadHandle
0x180016852  mov     edx, r12d; DesiredAccess
0x180016855  call    cs:__imp_OpenThreadToken
0x18001685b  mov     esi, eax
0x18001685d  test    eax, eax
0x18001685f  jz      short loc_18001686A
0x180016861  mov     rcx, [rbp+TokenHandle]
0x180016865  mov     rbx, rcx
0x180016868  jmp     short loc_18001689E
0x18001686a  call    cs:__imp_GetLastError
0x180016870  cmp     eax, 3F0h
0x180016875  jnz     loc_180016917
0x18001687b  call    cs:__imp_GetCurrentProcess
0x180016881  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180016885  mov     edx, r12d; DesiredAccess
0x180016888  mov     rcx, rax; ProcessHandle
0x18001688b  call    cs:__imp_OpenProcessToken
0x180016891  mov     esi, eax
0x180016893  mov     rbx, rdi
0x180016896  test    eax, eax
0x180016898  jz      short loc_180016917
0x18001689a  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18001689e  xor     r8d, r8d; lpTokenAttributes
0x1800168a1  mov     [rbp+Token], 0
0x1800168a9  lea     rax, [rbp+Token]
0x1800168ad  mov     r9d, r12d; ImpersonationLevel
0x1800168b0  mov     [rsp+30h+phNewToken], rax; phNewToken
0x1800168b5  mov     [rsp+30h+TokenType], r12d; TokenType
0x1800168ba  lea     edx, [r8+2Ch]; dwDesiredAccess
0x1800168be  call    cs:__imp_DuplicateTokenEx
0x1800168c4  mov     esi, eax
0x1800168c6  test    eax, eax
0x1800168c8  jz      short loc_180016917
0x1800168ca  mov     rcx, [rbp+Token]; TokenHandle
0x1800168ce  xor     r9d, r9d; BufferLength
0x1800168d1  mov     [rsp+30h+phNewToken], 0; ReturnLength
0x1800168da  mov     r8, r14; NewState
0x1800168dd  xor     edx, edx; DisableAllPrivileges
0x1800168df  mov     qword ptr [rsp+30h+TokenType], 0; PreviousState
0x1800168e8  call    cs:__imp_AdjustTokenPrivileges
0x1800168ee  mov     esi, eax
0x1800168f0  test    eax, eax
0x1800168f2  jz      short loc_180016902
0x1800168f4  mov     rdx, [rbp+Token]; Token
0x1800168f8  xor     ecx, ecx; Thread
0x1800168fa  call    cs:__imp_SetThreadToken
0x180016900  mov     esi, eax
0x180016902  mov     rcx, [rbp+Token]; hObject
0x180016906  call    cs:__imp_CloseHandle
0x18001690c  test    esi, esi
0x18001690e  jz      short loc_180016917
0x180016910  cmp     rbx, rdi
0x180016913  jnz     short loc_18001692D
0x180016915  jmp     short loc_18001691A
0x180016917  mov     rbx, rdi
0x18001691a  mov     rcx, [rbp+TokenHandle]; hObject
0x18001691e  cmp     rcx, rdi
0x180016921  jz      short loc_180016929
0x180016923  call    cs:__imp_CloseHandle
0x180016929  test    esi, esi
0x18001692b  jz      short loc_180016936
0x18001692d  xor     ecx, ecx
0x18001692f  cmp     rbx, rdi
0x180016932  cmovz   rbx, rcx
0x180016936  mov     rcx, r14; hMem
0x180016939  call    cs:__imp_LocalFree
0x18001693f  mov     rax, rbx
0x180016942  jmp     short loc_180016948
0x180016944  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016948  mov     rbx, [rsp+30h+arg_8]
0x18001694d  add     rsp, 30h
0x180016951  pop     r14
0x180016953  pop     r12
0x180016955  pop     rdi
0x180016956  pop     rsi
0x180016957  pop     rbp
0x180016958  retn
```
