# ScCheckDependentAccess(void * *,CServiceRecord *,ulong,int *)

- ea: `0x14000498c`
- end: `0x140004b0a`
- name: `?ScCheckDependentAccess@@YAHPEAPEAXPEAVCServiceRecord@@KPEAH@Z`
- size: `382`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, struct CServiceRecord *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x140004e58`

## callees

- `0x14000498c`
- `0x140004b10`
- `0x140004c58`
- `0x140013b0c`
- `0x140029228`
- `0x14004401c`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004a92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140004a26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140004a26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004a12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004a12`
- `RPCRT4!RpcImpersonateClient` at `0x1400049de`
- `RPCRT4!RpcImpersonateClient` at `0x1400049de`
- `RPCRT4!RpcRevertToSelf` at `0x140004a30`
- `RPCRT4!RpcRevertToSelf` at `0x140004a30`

## pseudocode

```c
__int64 __fastcall ScCheckDependentAccess(PHANDLE TokenHandle, void **a2, unsigned int a3, int *a4)
{
  unsigned int v7; // edi
  RPC_STATUS v9; // eax
  DWORD v10; // ebp
  HANDLE CurrentThread; // rax
  unsigned int v12; // eax
  unsigned int v13; // esi
  DWORD LastError; // eax

  if ( !TokenHandle )
    return 1;
  v7 = 0;
  if ( *TokenHandle )
    goto LABEL_3;
  v9 = RpcImpersonateClient(0);
  if ( v9 )
  {
    ScLogImpersonateFailureEvent(v9);
    return v7;
  }
  v10 = 0;
  if ( ((unsigned __int16 (*)(void))g_pScExtFunctionPointers[7])() == g_SystemLanguageId )
  {
    *a4 = 1;
  }
  else
  {
    *a4 = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 118, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 119, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, LastError);
  }
  v12 = RpcRevertToSelf();
  v13 = v12;
  if ( !v12 )
  {
    if ( v10 )
      return v7;
LABEL_3:
    if ( !ScAccessCheck(a2[18], *TokenHandle, a3) )
      return 1;
    return v7;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 120, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v12);
  ScLogEvent(5u, L"RpcRevertToSelf", v13);
  return v7;
}

```

## disassembly

```asm
0x14000498c  push    rbx
0x14000498e  push    rbp
0x14000498f  push    rsi
0x140004990  push    rdi
0x140004991  push    r12
0x140004993  push    r14
0x140004995  push    r15
0x140004997  sub     rsp, 30h
0x14000499b  mov     rsi, r9
0x14000499e  mov     r15, rdx
0x1400049a1  mov     r14, rcx
0x1400049a4  test    rcx, rcx
0x1400049a7  jz      loc_140004A4A
0x1400049ad  xor     edi, edi
0x1400049af  lea     ebx, [rdi+1]
0x1400049b2  cmp     [rcx], rdi
0x1400049b5  jz      short loc_1400049DC
0x1400049b7  mov     rdx, [r14]; void *
0x1400049ba  mov     rcx, [r15+90h]; void *
0x1400049c1  call    ?ScAccessCheck@@YAKPEAX0K@Z; ScAccessCheck(void *,void *,ulong)
0x1400049c6  test    eax, eax
0x1400049c8  cmovz   edi, ebx
0x1400049cb  mov     eax, edi
0x1400049cd  add     rsp, 30h
0x1400049d1  pop     r15
0x1400049d3  pop     r14
0x1400049d5  pop     r12
0x1400049d7  pop     rdi
0x1400049d8  pop     rsi
0x1400049d9  pop     rbp
0x1400049da  pop     rbx
0x1400049db  retn
0x1400049dc  xor     ecx, ecx; BindingHandle
0x1400049de  call    cs:__imp_RpcImpersonateClient
0x1400049e4  test    eax, eax
0x1400049e6  jnz     short loc_140004A54
0x1400049e8  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x1400049ef  xor     ebp, ebp
0x1400049f1  mov     rax, [rax+38h]
0x1400049f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049fa  movzx   edx, ax
0x1400049fd  lea     r12, WPP_GLOBAL_Control
0x140004a04  movzx   eax, cs:?g_SystemLanguageId@@3GA; ushort g_SystemLanguageId
0x140004a0b  cmp     dx, ax
0x140004a0e  jnz     short loc_140004A60
0x140004a10  mov     [rsi], ebx
0x140004a12  call    cs:__imp_GetCurrentThread
0x140004a18  mov     r9, r14; TokenHandle
0x140004a1b  mov     r8d, ebx; OpenAsSelf
0x140004a1e  mov     rcx, rax; ThreadHandle
0x140004a21  mov     edx, 8; DesiredAccess
0x140004a26  call    cs:__imp_OpenThreadToken
0x140004a2c  test    eax, eax
0x140004a2e  jz      short loc_140004A92
0x140004a30  call    cs:__imp_RpcRevertToSelf
0x140004a36  mov     esi, eax
0x140004a38  test    eax, eax
0x140004a3a  jnz     loc_140004AC8
0x140004a40  test    ebp, ebp
0x140004a42  jz      loc_1400049B7
0x140004a48  jmp     short loc_1400049CB
0x140004a4a  mov     edi, 1
0x140004a4f  jmp     loc_1400049CB
0x140004a54  mov     ecx, eax; int
0x140004a56  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x140004a5b  jmp     loc_1400049CB
0x140004a60  mov     [rsi], edi
0x140004a62  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a69  cmp     rcx, r12
0x140004a6c  jz      short loc_140004A12
0x140004a6e  test    byte ptr [rcx+1Ch], 4
0x140004a72  jz      short loc_140004A12
0x140004a74  mov     rcx, [rcx+10h]
0x140004a78  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140004a7f  mov     r9d, edx
0x140004a82  mov     [rsp+68h+var_48], eax
0x140004a86  mov     edx, 76h ; 'v'
0x140004a8b  call    WPP_SF_Dd
0x140004a90  jmp     short loc_140004A12
0x140004a92  call    cs:__imp_GetLastError
0x140004a98  mov     ebp, eax
0x140004a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004aa1  cmp     rcx, r12
0x140004aa4  jz      short loc_140004A30
0x140004aa6  test    [rcx+1Ch], bl
0x140004aa9  jz      short loc_140004A30
0x140004aab  mov     rcx, [rcx+10h]
0x140004aaf  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140004ab6  mov     edx, 77h ; 'w'
0x140004abb  mov     r9d, eax
0x140004abe  call    WPP_SF_d
0x140004ac3  jmp     loc_140004A30
0x140004ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x140004acf  cmp     rcx, r12
0x140004ad2  jz      short loc_140004AF1
0x140004ad4  test    [rcx+1Ch], bl
0x140004ad7  jz      short loc_140004AF1
0x140004ad9  mov     rcx, [rcx+10h]
0x140004add  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140004ae4  mov     edx, 78h ; 'x'
0x140004ae9  mov     r9d, esi
0x140004aec  call    WPP_SF_d
0x140004af1  mov     r8d, esi
0x140004af4  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140004afb  mov     ecx, 5; unsigned int
0x140004b00  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140004b05  jmp     loc_1400049CB
```
