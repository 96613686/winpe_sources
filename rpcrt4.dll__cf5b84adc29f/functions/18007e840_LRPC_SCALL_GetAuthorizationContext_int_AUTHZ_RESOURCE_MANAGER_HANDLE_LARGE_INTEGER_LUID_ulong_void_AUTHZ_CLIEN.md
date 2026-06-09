# LRPC_SCALL::GetAuthorizationContext(int,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x18007e840`
- end: `0x18007e9d7`
- name: `?GetAuthorizationContext@LRPC_SCALL@@UEAAJHPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@KPEAXPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(LRPC_SCALL *this, int, AUTHZ_RESOURCE_MANAGER_HANDLE, union _LARGE_INTEGER *, LUID Identifier, DWORD Flags, PVOID DynamicGroupArgs, PAUTHZ_CLIENT_CONTEXT_HANDLE)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001f9e0`
- `0x1800295d8`
- `0x18007e840`
- `0x18007e9e0`
- `0x18007ea80`
- `0x1800a7738`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e99e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e8e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e9ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e8e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e9ac`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007e8b0`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007e8b0`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromSid` at `0x18007e98a`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromSid` at `0x18007e98a`

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
0x18007e840  push    rbx
0x18007e842  push    rbp
0x18007e843  push    rsi
0x18007e844  push    rdi
0x18007e845  push    r12
0x18007e847  push    r14
0x18007e849  push    r15
0x18007e84b  sub     rsp, 60h
0x18007e84f  mov     r12d, edx
0x18007e852  mov     r14, r9
0x18007e855  mov     edx, 1; unsigned int
0x18007e85a  mov     rsi, r8
0x18007e85d  mov     rbp, rcx
0x18007e860  call    ?ImpersonateClient@LRPC_SCALL@@UEAAJK@Z; LRPC_SCALL::ImpersonateClient(ulong)
0x18007e865  mov     edi, eax
0x18007e867  test    eax, eax
0x18007e869  jnz     loc_18007E94F
0x18007e86f  mov     r15, [rsp+98h+arg_30]
0x18007e877  lea     rax, [rsp+98h+var_58]
0x18007e87c  mov     rbx, qword ptr [rsp+98h+arg_20.LowPart]
0x18007e884  mov     r9, r14; pExpirationTime
0x18007e887  mov     ecx, [rsp+98h+Flags]; Flags
0x18007e88e  mov     r8, rsi; hAuthzResourceManager
0x18007e891  mov     [rsp+98h+phAuthzClientContext], rax; phAuthzClientContext
0x18007e896  mov     rdx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18007e89d  mov     [rsp+98h+DynamicGroupArgs], r15; DynamicGroupArgs
0x18007e8a2  mov     qword ptr [rsp+98h+Identifier.LowPart], rbx; Identifier
0x18007e8a7  mov     [rsp+98h+var_58], 0
0x18007e8b0  call    cs:__imp_AuthzInitializeContextFromToken
0x18007e8b7  nop     dword ptr [rax+rax+00h]
0x18007e8bc  test    eax, eax
0x18007e8be  jz      short loc_18007E8D2
0x18007e8c0  mov     rcx, [rsp+98h+arg_38]
0x18007e8c8  mov     rax, [rsp+98h+var_58]
0x18007e8cd  mov     [rcx], rax
0x18007e8d0  jmp     short loc_18007E909
0x18007e8d2  call    cs:__imp_GetLastError
0x18007e8d9  nop     dword ptr [rax+rax+00h]
0x18007e8de  mov     edi, eax
0x18007e8e0  call    cs:__imp_GetCurrentThreadId
0x18007e8e7  nop     dword ptr [rax+rax+00h]
0x18007e8ec  mov     r8d, 1CCh; unsigned __int16
0x18007e8f2  mov     qword ptr [rsp+98h+Identifier.LowPart], rsi; unsigned __int64
0x18007e8f7  mov     r9d, eax; unsigned int
0x18007e8fa  mov     edx, edi; unsigned int
0x18007e8fc  call    ?CompRpcpErrorAddRecord@@YAXKKGK_K@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,unsigned __int64)
0x18007e901  cmp     edi, 543h
0x18007e907  jz      short loc_18007E961
0x18007e909  mov     [rsp+98h+var_50], 3
0x18007e911  call    cs:__imp_GetCurrentThreadId
0x18007e918  nop     dword ptr [rax+rax+00h]
0x18007e91d  mov     r9d, 1; int
0x18007e923  mov     [rsp+98h+var_48], eax
0x18007e927  lea     rax, [rsp+98h+var_50]
0x18007e92c  mov     r8d, 1B9h; unsigned __int16
0x18007e932  mov     edx, edi; int
0x18007e934  mov     qword ptr [rsp+98h+Identifier.LowPart], rax; struct tagParam *
0x18007e939  lea     ecx, [r9+1]; unsigned int
0x18007e93d  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18007e942  test    r12d, r12d
0x18007e945  jnz     short loc_18007E94F
0x18007e947  mov     rcx, rbp; this
0x18007e94a  call    ?RevertToSelf@LRPC_SCALL@@UEAAJXZ; LRPC_SCALL::RevertToSelf(void)
0x18007e94f  mov     eax, edi
0x18007e951  add     rsp, 60h
0x18007e955  pop     r15
0x18007e957  pop     r14
0x18007e959  pop     r12
0x18007e95b  pop     rdi
0x18007e95c  pop     rsi
0x18007e95d  pop     rbp
0x18007e95e  pop     rbx
0x18007e95f  retn
0x18007e961  mov     rax, [rsp+98h+arg_38]
0x18007e969  lea     rdx, ?AnonymousSid@@3U_SID@@B; UserSid
0x18007e970  mov     [rsp+98h+phAuthzClientContext], rax; phAuthzClientContext
0x18007e975  mov     r9, r14; pExpirationTime
0x18007e978  mov     [rsp+98h+DynamicGroupArgs], r15; DynamicGroupArgs
0x18007e97d  mov     r8, rsi; hAuthzResourceManager
0x18007e980  mov     ecx, 2; Flags
0x18007e985  mov     qword ptr [rsp+98h+Identifier.LowPart], rbx; Identifier
0x18007e98a  call    cs:__imp_AuthzInitializeContextFromSid
0x18007e991  nop     dword ptr [rax+rax+00h]
0x18007e996  test    eax, eax
0x18007e998  jz      short loc_18007E99E
0x18007e99a  xor     edi, edi
0x18007e99c  jmp     short loc_18007E942
0x18007e99e  call    cs:__imp_GetLastError
0x18007e9a5  nop     dword ptr [rax+rax+00h]
0x18007e9aa  mov     edi, eax
0x18007e9ac  call    cs:__imp_GetCurrentThreadId
0x18007e9b3  nop     dword ptr [rax+rax+00h]
0x18007e9b8  mov     r8d, 1BAh; unsigned __int16
0x18007e9be  mov     qword ptr [rsp+98h+Identifier.LowPart], rsi; unsigned __int64
0x18007e9c3  mov     r9d, eax; unsigned int
0x18007e9c6  mov     edx, edi; int
0x18007e9c8  mov     ecx, 13h; unsigned int
0x18007e9cd  call    ?RpcpErrorAddRecord@@YAXKJGK_K@Z; RpcpErrorAddRecord(ulong,long,ushort,ulong,unsigned __int64)
0x18007e9d2  jmp     loc_18007E942
```
