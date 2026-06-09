# IsCallerSameAsUser(ulong)

- ea: `0x18000e3a4`
- end: `0x18000e4fb`
- name: `?IsCallerSameAsUser@@YAHK@Z`
- size: `343`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800065d0`

## callees

- `0x18000bd44`
- `0x18000e2e0`
- `0x18000e3a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e41f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e45e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e454`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e454`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e43a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e43a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e3e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e3dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e3dc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000e495`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000e495`
- `RPCRT4!RpcImpersonateClient` at `0x18000e430`
- `RPCRT4!RpcImpersonateClient` at `0x18000e430`
- `RPCRT4!RpcRevertToSelf` at `0x18000e4a7`
- `RPCRT4!RpcRevertToSelf` at `0x18000e4a7`
- `WINSTA!WinStationQueryInformationW` at `0x18000e413`
- `WINSTA!WinStationQueryInformationW` at `0x18000e413`

## pseudocode

```c
__int64 __fastcall IsCallerSameAsUser(unsigned int a1)
{
  unsigned int v1; // r14d
  struct _TOKEN_USER *v2; // rdi
  struct _TOKEN_USER *v3; // rsi
  HANDLE v5; // rbx
  HANDLE CurrentThread; // rax
  int TokenInfo; // eax
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v11; // [rsp+48h] [rbp-8h]
  int v12; // [rsp+88h] [rbp+38h] BYREF
  struct _TOKEN_USER *v13; // [rsp+90h] [rbp+40h] BYREF
  struct _TOKEN_USER *v14; // [rsp+98h] [rbp+48h] BYREF

  v1 = 0;
  v11 = 0;
  v2 = 0;
  TokenHandle = 0;
  v3 = 0;
  v13 = 0;
  v14 = 0;
  v12 = 0;
  v10[0] = (int)GetCurrentProcessId();
  v10[1] = (int)GetCurrentThreadId();
  if ( (unsigned __int8)WinStationQueryInformationW(0, a1, 14, v10, 24, &v12) )
  {
    v5 = v11;
    if ( !RpcImpersonateClient(0) )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        if ( (int)GetTokenInfo(v5, &v13) < 0 )
        {
          v2 = v13;
        }
        else
        {
          TokenInfo = GetTokenInfo(TokenHandle, &v14);
          v3 = v14;
          v2 = v13;
          if ( TokenInfo >= 0 )
            v1 = EqualSid(v13->User.Sid, v14->User.Sid);
        }
      }
      else
      {
        GetLastError();
      }
      RpcRevertToSelf();
    }
  }
  else
  {
    v5 = 0;
    GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 )
    CloseHandle(v5);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  return v1;
}

```

## disassembly

```asm
0x18000e3a4  mov     [rsp-28h+arg_0], rbx
0x18000e3a9  push    rbp
0x18000e3aa  push    rsi
0x18000e3ab  push    rdi
0x18000e3ac  push    r14
0x18000e3ae  push    r15
0x18000e3b0  mov     rbp, rsp
0x18000e3b3  sub     rsp, 50h
0x18000e3b7  xor     eax, eax
0x18000e3b9  xorps   xmm0, xmm0
0x18000e3bc  xor     r14d, r14d
0x18000e3bf  mov     [rbp+var_8], rax
0x18000e3c3  xor     edi, edi
0x18000e3c5  mov     [rbp+TokenHandle], r14
0x18000e3c9  xor     esi, esi
0x18000e3cb  mov     [rbp+arg_10], rdi
0x18000e3cf  mov     [rbp+arg_18], rsi
0x18000e3d3  mov     ebx, ecx
0x18000e3d5  movups  [rbp+var_18], xmm0
0x18000e3d9  mov     [rbp+arg_8], eax
0x18000e3dc  call    cs:__imp_GetCurrentProcessId
0x18000e3e2  movsxd  rcx, eax
0x18000e3e5  mov     qword ptr [rbp+var_18], rcx
0x18000e3e9  call    cs:__imp_GetCurrentThreadId
0x18000e3ef  movsxd  rcx, eax
0x18000e3f2  lea     r9, [rbp+var_18]
0x18000e3f6  mov     qword ptr [rbp+var_18+8], rcx
0x18000e3fa  mov     edx, ebx
0x18000e3fc  lea     rax, [rbp+arg_8]
0x18000e400  xor     ecx, ecx
0x18000e402  mov     [rsp+50h+var_28], rax
0x18000e407  lea     r8d, [r14+0Eh]
0x18000e40b  mov     [rsp+50h+var_30], 18h
0x18000e413  call    cs:__imp_WinStationQueryInformationW
0x18000e419  test    al, al
0x18000e41b  jnz     short loc_18000E42A
0x18000e41d  xor     ebx, ebx
0x18000e41f  call    cs:__imp_GetLastError
0x18000e425  jmp     loc_18000E4AD
0x18000e42a  mov     rbx, [rbp+var_8]
0x18000e42e  xor     ecx, ecx; BindingHandle
0x18000e430  call    cs:__imp_RpcImpersonateClient
0x18000e436  test    eax, eax
0x18000e438  jnz     short loc_18000E4AD
0x18000e43a  call    cs:__imp_GetCurrentThread
0x18000e440  mov     r15d, 1
0x18000e446  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000e44a  mov     rcx, rax; ThreadHandle
0x18000e44d  mov     r8d, r15d; OpenAsSelf
0x18000e450  lea     edx, [r15+7]; DesiredAccess
0x18000e454  call    cs:__imp_OpenThreadToken
0x18000e45a  test    eax, eax
0x18000e45c  jnz     short loc_18000E466
0x18000e45e  call    cs:__imp_GetLastError
0x18000e464  jmp     short loc_18000E4A7
0x18000e466  lea     rdx, [rbp+arg_10]; struct _TOKEN_USER **
0x18000e46a  mov     rcx, rbx; TokenHandle
0x18000e46d  call    ?GetTokenInfo@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenInfo(void *,_TOKEN_USER * *)
0x18000e472  test    eax, eax
0x18000e474  js      short loc_18000E4A3
0x18000e476  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000e47a  lea     rdx, [rbp+arg_18]; struct _TOKEN_USER **
0x18000e47e  call    ?GetTokenInfo@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenInfo(void *,_TOKEN_USER * *)
0x18000e483  mov     rsi, [rbp+arg_18]
0x18000e487  mov     rdi, [rbp+arg_10]
0x18000e48b  test    eax, eax
0x18000e48d  js      short loc_18000E4A7
0x18000e48f  mov     rdx, [rsi]; pSid2
0x18000e492  mov     rcx, [rdi]; pSid1
0x18000e495  call    cs:__imp_EqualSid
0x18000e49b  test    eax, eax
0x18000e49d  cmovnz  r14d, r15d
0x18000e4a1  jmp     short loc_18000E4A7
0x18000e4a3  mov     rdi, [rbp+arg_10]
0x18000e4a7  call    cs:__imp_RpcRevertToSelf
0x18000e4ad  mov     rcx, [rbp+TokenHandle]; hObject
0x18000e4b1  test    rcx, rcx
0x18000e4b4  jz      short loc_18000E4BC
0x18000e4b6  call    cs:__imp_CloseHandle
0x18000e4bc  test    rbx, rbx
0x18000e4bf  jz      short loc_18000E4CA
0x18000e4c1  mov     rcx, rbx; hObject
0x18000e4c4  call    cs:__imp_CloseHandle
0x18000e4ca  test    rdi, rdi
0x18000e4cd  jz      short loc_18000E4D7
0x18000e4cf  mov     rcx, rdi; Block
0x18000e4d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e4d7  test    rsi, rsi
0x18000e4da  jz      short loc_18000E4E4
0x18000e4dc  mov     rcx, rsi; Block
0x18000e4df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e4e4  mov     rbx, [rsp+50h+arg_0]
0x18000e4ec  mov     eax, r14d
0x18000e4ef  add     rsp, 50h
0x18000e4f3  pop     r15
0x18000e4f5  pop     r14
0x18000e4f7  pop     rdi
0x18000e4f8  pop     rsi
0x18000e4f9  pop     rbp
0x18000e4fa  retn
```
