# WxCheckRpcClientSessionMatchesServerSession(void)

- ea: `0x180040210`
- end: `0x180040407`
- name: `?WxCheckRpcClientSessionMatchesServerSession@@YAJXZ`
- size: `503`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041ea0`

## callees

- `0x180040210`
- `0x1800701d0`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004030e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004030e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004025d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004025d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040276`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004033d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004033d`
- `RPCRT4!RpcRevertToSelf` at `0x180040284`
- `RPCRT4!RpcRevertToSelf` at `0x180040380`
- `RPCRT4!RpcRevertToSelf` at `0x180040284`
- `RPCRT4!RpcRevertToSelf` at `0x180040380`
- `RPCRT4!RpcImpersonateClient` at `0x18004023d`
- `RPCRT4!RpcImpersonateClient` at `0x18004023d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800402d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800402d6`

## pseudocode

```c
__int64 WxCheckRpcClientSessionMatchesServerSession(void)
{
  RPC_STATUS v0; // eax
  int v1; // ebx
  HANDLE CurrentThread; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebp
  int v12; // eax
  int LastError; // eax
  int v14; // eax
  DWORD ReturnLength; // [rsp+38h] [rbp-50h] BYREF
  int v16; // [rsp+3Ch] [rbp-4Ch]
  int TokenInformation; // [rsp+40h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-40h] BYREF

  v16 = 0;
  TokenHandle = 0;
  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 < 0 )
  {
    v16 = 992;
    goto LABEL_13;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    RpcRevertToSelf();
    v16 = 0;
    TokenInformation = 0;
    ReturnLength = 0;
    if ( TokenHandle )
    {
      if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      {
        v7 = TokenInformation;
        v1 = 0;
        goto LABEL_8;
      }
      LastError = WxGetLastError(v6, v5);
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      v16 = 256;
      if ( v1 >= 0 )
        v1 = -2147418113;
    }
    else
    {
      v1 = -2147024809;
      v16 = 253;
    }
    v7 = 0;
LABEL_8:
    if ( v1 < 0 )
    {
      v16 = 1004;
    }
    else
    {
      v16 = 0;
      if ( InitOnceExecuteOnce(&g_ProcessUserSIDInitOnce, (PINIT_ONCE_FN)_ProcessUserSIDInitOnceCallback, 0, 0) )
      {
        v10 = g_dwProcessSessionId;
        v1 = 0;
      }
      else
      {
        v10 = 0;
        v14 = WxGetLastError(v9, v8);
        v1 = v14;
        if ( v14 > 0 )
          v1 = (unsigned __int16)v14 | 0x80070000;
        v16 = 281;
        if ( v1 >= 0 )
          v1 = -2147418113;
      }
      if ( v1 < 0 )
        v16 = 1010;
      else
        v1 = v10 != v7;
    }
    goto LABEL_13;
  }
  v12 = WxGetLastError(v4, v3);
  v1 = v12;
  if ( v12 > 0 )
    v1 = (unsigned __int16)v12 | 0x80070000;
  v16 = 995;
  if ( v1 >= 0 )
    v1 = -2147418113;
  RpcRevertToSelf();
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180040210  push    rbx
0x180040212  push    rbp
0x180040213  push    rsi
0x180040214  push    rdi
0x180040215  push    r15
0x180040217  sub     rsp, 60h
0x18004021b  mov     rax, cs:__security_cookie
0x180040222  xor     rax, rsp
0x180040225  mov     [rsp+88h+var_38], rax
0x18004022a  xor     ecx, ecx; BindingHandle
0x18004022c  mov     [rsp+88h+var_4C], 0
0x180040234  mov     [rsp+88h+TokenHandle], 0
0x18004023d  call    cs:__imp_RpcImpersonateClient
0x180040243  mov     ebx, eax
0x180040245  mov     r15d, 80070000h
0x18004024b  test    eax, eax
0x18004024d  jle     short loc_180040255
0x18004024f  movzx   ebx, ax
0x180040252  or      ebx, r15d
0x180040255  test    ebx, ebx
0x180040257  js      loc_1800403ED
0x18004025d  call    cs:__imp_GetCurrentThread
0x180040263  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180040268  mov     edx, 20008h; DesiredAccess
0x18004026d  mov     rcx, rax; ThreadHandle
0x180040270  mov     r8d, 1; OpenAsSelf
0x180040276  call    cs:__imp_OpenThreadToken
0x18004027c  test    eax, eax
0x18004027e  jz      loc_18004035D
0x180040284  call    cs:__imp_RpcRevertToSelf
0x18004028a  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x18004028f  mov     edi, 8000FFFFh
0x180040294  mov     [rsp+88h+var_4C], 0
0x18004029c  mov     [rsp+88h+TokenInformation], 0
0x1800402a4  mov     [rsp+88h+var_50], 0
0x1800402ac  mov     [rsp+88h+var_58], 0
0x1800402b4  test    rcx, rcx
0x1800402b7  jz      loc_180040392
0x1800402bd  mov     r9d, 4; TokenInformationLength
0x1800402c3  lea     rax, [rsp+88h+var_50]
0x1800402c8  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x1800402cd  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800402d2  lea     edx, [r9+8]; TokenInformationClass
0x1800402d6  call    cs:__imp_GetTokenInformation
0x1800402dc  test    eax, eax
0x1800402de  jz      loc_1800403A8
0x1800402e4  mov     esi, [rsp+88h+TokenInformation]
0x1800402e8  xor     ebx, ebx
0x1800402ea  test    ebx, ebx
0x1800402ec  js      loc_180040388
0x1800402f2  xor     r9d, r9d; Context
0x1800402f5  mov     [rsp+88h+var_4C], 0
0x1800402fd  xor     r8d, r8d; Parameter
0x180040300  lea     rdx, ?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180040307  lea     rcx, ?g_ProcessUserSIDInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18004030e  call    cs:__imp_InitOnceExecuteOnce
0x180040314  test    eax, eax
0x180040316  jz      loc_1800403C8
0x18004031c  mov     ebp, cs:?g_dwProcessSessionId@@3KA; ulong g_dwProcessSessionId
0x180040322  xor     ebx, ebx
0x180040324  test    ebx, ebx
0x180040326  js      loc_1800403FA
0x18004032c  xor     ebx, ebx
0x18004032e  cmp     ebp, esi
0x180040330  setnz   bl
0x180040333  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180040338  test    rcx, rcx
0x18004033b  jz      short loc_180040343
0x18004033d  call    cs:__imp_CloseHandle
0x180040343  mov     eax, ebx
0x180040345  mov     rcx, [rsp+88h+var_38]
0x18004034a  xor     rcx, rsp; StackCookie
0x18004034d  call    __security_check_cookie
0x180040352  add     rsp, 60h
0x180040356  pop     r15
0x180040358  pop     rdi
0x180040359  pop     rsi
0x18004035a  pop     rbp
0x18004035b  pop     rbx
0x18004035c  retn
0x18004035d  call    WxGetLastError
0x180040362  mov     ebx, eax
0x180040364  test    eax, eax
0x180040366  jle     short loc_18004036E
0x180040368  movzx   ebx, ax
0x18004036b  or      ebx, r15d
0x18004036e  test    ebx, ebx
0x180040370  mov     [rsp+88h+var_4C], 3E3h
0x180040378  mov     edi, 8000FFFFh
0x18004037d  cmovns  ebx, edi
0x180040380  call    cs:__imp_RpcRevertToSelf
0x180040386  jmp     short loc_180040333
0x180040388  mov     [rsp+88h+var_4C], 3ECh
0x180040390  jmp     short loc_180040333
0x180040392  mov     ebx, 80070057h
0x180040397  mov     [rsp+88h+var_4C], 0FDh
0x18004039f  mov     esi, [rsp+88h+var_58]
0x1800403a3  jmp     loc_1800402EA
0x1800403a8  call    WxGetLastError
0x1800403ad  mov     ebx, eax
0x1800403af  test    eax, eax
0x1800403b1  jle     short loc_1800403B9
0x1800403b3  movzx   ebx, ax
0x1800403b6  or      ebx, r15d
0x1800403b9  test    ebx, ebx
0x1800403bb  mov     [rsp+88h+var_4C], 100h
0x1800403c3  cmovns  ebx, edi
0x1800403c6  jmp     short loc_18004039F
0x1800403c8  xor     ebp, ebp
0x1800403ca  call    WxGetLastError
0x1800403cf  mov     ebx, eax
0x1800403d1  test    eax, eax
0x1800403d3  jle     short loc_1800403DB
0x1800403d5  movzx   ebx, ax
0x1800403d8  or      ebx, r15d
0x1800403db  test    ebx, ebx
0x1800403dd  mov     [rsp+88h+var_4C], 119h
0x1800403e5  cmovns  ebx, edi
0x1800403e8  jmp     loc_180040324
0x1800403ed  mov     [rsp+88h+var_4C], 3E0h
0x1800403f5  jmp     loc_180040333
0x1800403fa  mov     [rsp+88h+var_4C], 3F2h
0x180040402  jmp     loc_180040333
```
