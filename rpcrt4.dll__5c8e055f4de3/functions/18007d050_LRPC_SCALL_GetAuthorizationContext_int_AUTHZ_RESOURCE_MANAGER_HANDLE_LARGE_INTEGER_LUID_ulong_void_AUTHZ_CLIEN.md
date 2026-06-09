# LRPC_SCALL::GetAuthorizationContext(int,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x18007d050`
- end: `0x18007d1b9`
- name: `?GetAuthorizationContext@LRPC_SCALL@@UEAAJHPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@KPEAXPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z`
- size: `361`
- prototype: `__int64 __usercall@<rax>(LRPC_SCALL *__hidden this@<rcx>, int@<edx>, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *@<r8>, union _LARGE_INTEGER *@<r9>, LUID, unsigned int, void *, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001e930`
- `0x1800283bc`
- `0x18007d050`
- `0x18007d1c0`
- `0x18007d260`
- `0x1800a4188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d18f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d0dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d18f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d0e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d10f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d0e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d10f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d197`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007d0c0`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007d0c0`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromSid` at `0x18007d181`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromSid` at `0x18007d181`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::GetAuthorizationContext(
        LRPC_SCALL *this,
        int a2,
        AUTHZ_RESOURCE_MANAGER_HANDLE a3,
        union _LARGE_INTEGER *a4,
        LUID Identifier,
        DWORD Flags,
        PVOID DynamicGroupArgs,
        PAUTHZ_CLIENT_CONTEXT_HANDLE a8)
{
  unsigned int LastError; // edi
  DWORD CurrentThreadId; // eax
  unsigned int v14; // ecx
  DWORD v16; // eax
  AUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext; // [rsp+40h] [rbp-58h] BYREF
  _DWORD v18[20]; // [rsp+48h] [rbp-50h] BYREF

  LastError = LRPC_SCALL::ImpersonateClient(this, 1);
  if ( LastError )
    return LastError;
  phAuthzClientContext = 0;
  if ( AuthzInitializeContextFromToken(
         Flags,
         (HANDLE)0xFFFFFFFFFFFFFFFBLL,
         a3,
         a4,
         Identifier,
         DynamicGroupArgs,
         &phAuthzClientContext) )
  {
    *a8 = phAuthzClientContext;
LABEL_5:
    v18[0] = 3;
    v18[2] = GetCurrentThreadId();
    RpcpErrorAddRecord(2u, LastError, 0x1B9u, 1, (struct tagParam *)v18);
    goto LABEL_6;
  }
  LastError = GetLastError();
  CurrentThreadId = GetCurrentThreadId();
  CompRpcpErrorAddRecord(v14, LastError, 0x1CCu, CurrentThreadId, (unsigned __int64)a3);
  if ( LastError != 1347 )
    goto LABEL_5;
  if ( AuthzInitializeContextFromSid(2u, &AnonymousSid, a3, a4, Identifier, DynamicGroupArgs, a8) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    v16 = GetCurrentThreadId();
    RpcpErrorAddRecord(0x13u, LastError, 0x1BAu, v16, (unsigned __int64)a3);
  }
LABEL_6:
  if ( !a2 )
    LRPC_SCALL::RevertToSelf(this);
  return LastError;
}

```

## disassembly

```asm
0x18007d050  push    rbx
0x18007d052  push    rbp
0x18007d053  push    rsi
0x18007d054  push    rdi
0x18007d055  push    r12
0x18007d057  push    r14
0x18007d059  push    r15
0x18007d05b  sub     rsp, 60h
0x18007d05f  mov     r12d, edx
0x18007d062  mov     r14, r9
0x18007d065  mov     edx, 1; unsigned int
0x18007d06a  mov     rsi, r8
0x18007d06d  mov     rbp, rcx
0x18007d070  call    ?ImpersonateClient@LRPC_SCALL@@UEAAJK@Z; LRPC_SCALL::ImpersonateClient(ulong)
0x18007d075  mov     edi, eax
0x18007d077  test    eax, eax
0x18007d079  jnz     loc_18007D147
0x18007d07f  mov     r15, [rsp+98h+arg_30]
0x18007d087  lea     rax, [rsp+98h+var_58]
0x18007d08c  mov     rbx, qword ptr [rsp+98h+arg_20.LowPart]
0x18007d094  mov     r9, r14; pExpirationTime
0x18007d097  mov     ecx, [rsp+98h+Flags]; Flags
0x18007d09e  mov     r8, rsi; hAuthzResourceManager
0x18007d0a1  mov     [rsp+98h+phAuthzClientContext], rax; phAuthzClientContext
0x18007d0a6  mov     rdx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18007d0ad  mov     [rsp+98h+DynamicGroupArgs], r15; DynamicGroupArgs
0x18007d0b2  mov     qword ptr [rsp+98h+Identifier.LowPart], rbx; Identifier
0x18007d0b7  mov     [rsp+98h+var_58], 0
0x18007d0c0  call    cs:__imp_AuthzInitializeContextFromToken
0x18007d0c6  test    eax, eax
0x18007d0c8  jz      short loc_18007D0DC
0x18007d0ca  mov     rcx, [rsp+98h+arg_38]
0x18007d0d2  mov     rax, [rsp+98h+var_58]
0x18007d0d7  mov     [rcx], rax
0x18007d0da  jmp     short loc_18007D107
0x18007d0dc  call    cs:__imp_GetLastError
0x18007d0e2  mov     edi, eax
0x18007d0e4  call    cs:__imp_GetCurrentThreadId
0x18007d0ea  mov     r8d, 1CCh; unsigned __int16
0x18007d0f0  mov     qword ptr [rsp+98h+Identifier.LowPart], rsi; unsigned __int64
0x18007d0f5  mov     r9d, eax; unsigned int
0x18007d0f8  mov     edx, edi; unsigned int
0x18007d0fa  call    ?CompRpcpErrorAddRecord@@YAXKKGK_K@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,unsigned __int64)
0x18007d0ff  cmp     edi, 543h
0x18007d105  jz      short loc_18007D158
0x18007d107  mov     [rsp+98h+var_50], 3
0x18007d10f  call    cs:__imp_GetCurrentThreadId
0x18007d115  mov     r9d, 1; int
0x18007d11b  mov     [rsp+98h+var_48], eax
0x18007d11f  lea     rax, [rsp+98h+var_50]
0x18007d124  mov     r8d, 1B9h; unsigned __int16
0x18007d12a  mov     edx, edi; int
0x18007d12c  mov     qword ptr [rsp+98h+Identifier.LowPart], rax; struct tagParam *
0x18007d131  lea     ecx, [r9+1]; unsigned int
0x18007d135  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18007d13a  test    r12d, r12d
0x18007d13d  jnz     short loc_18007D147
0x18007d13f  mov     rcx, rbp; this
0x18007d142  call    ?RevertToSelf@LRPC_SCALL@@UEAAJXZ; LRPC_SCALL::RevertToSelf(void)
0x18007d147  mov     eax, edi
0x18007d149  add     rsp, 60h
0x18007d14d  pop     r15
0x18007d14f  pop     r14
0x18007d151  pop     r12
0x18007d153  pop     rdi
0x18007d154  pop     rsi
0x18007d155  pop     rbp
0x18007d156  pop     rbx
0x18007d157  retn
0x18007d158  mov     rax, [rsp+98h+arg_38]
0x18007d160  lea     rdx, ?AnonymousSid@@3U_SID@@B; UserSid
0x18007d167  mov     [rsp+98h+phAuthzClientContext], rax; phAuthzClientContext
0x18007d16c  mov     r9, r14; pExpirationTime
0x18007d16f  mov     [rsp+98h+DynamicGroupArgs], r15; DynamicGroupArgs
0x18007d174  mov     r8, rsi; hAuthzResourceManager
0x18007d177  mov     ecx, 2; Flags
0x18007d17c  mov     qword ptr [rsp+98h+Identifier.LowPart], rbx; Identifier
0x18007d181  call    cs:__imp_AuthzInitializeContextFromSid
0x18007d187  test    eax, eax
0x18007d189  jz      short loc_18007D18F
0x18007d18b  xor     edi, edi
0x18007d18d  jmp     short loc_18007D13A
0x18007d18f  call    cs:__imp_GetLastError
0x18007d195  mov     edi, eax
0x18007d197  call    cs:__imp_GetCurrentThreadId
0x18007d19d  mov     r8d, 1BAh; unsigned __int16
0x18007d1a3  mov     qword ptr [rsp+98h+Identifier.LowPart], rsi; unsigned __int64
0x18007d1a8  mov     r9d, eax; unsigned int
0x18007d1ab  mov     edx, edi; int
0x18007d1ad  mov     ecx, 13h; unsigned int
0x18007d1b2  call    ?RpcpErrorAddRecord@@YAXKJGK_K@Z; RpcpErrorAddRecord(ulong,long,ushort,ulong,unsigned __int64)
0x18007d1b7  jmp     short loc_18007D13A
```
