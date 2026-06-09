# RpcpCreateAndSaveAuthzContextFromToken(AUTHZ_CLIENT_CONTEXT_HANDLE__ * *,void *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x18007e730`
- end: `0x18007e82c`
- name: `?RpcpCreateAndSaveAuthzContextFromToken@@YAJPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAXPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@K10@Z`
- size: `252`
- prototype: `int(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **, void *, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *, union _LARGE_INTEGER *, struct _LUID, unsigned int, void *, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a19f0`

## callees

- `0x18007e730`
- `0x18007e9e0`
- `0x1800bddc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e7a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e7b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e7b6`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007e775`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007e775`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeContext` at `0x18007e7ee`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeContext` at `0x18007e7ee`

## pseudocode

```c
__int64 __fastcall RpcpCreateAndSaveAuthzContextFromToken(
        struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **a1,
        void *a2,
        AUTHZ_RESOURCE_MANAGER_HANDLE a3,
        union _LARGE_INTEGER *a4,
        LUID Identifier,
        DWORD Flags,
        PVOID a7,
        PAUTHZ_CLIENT_CONTEXT_HANDLE a8)
{
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v14; // ecx
  signed __int64 v15; // rax
  AUTHZ_CLIENT_CONTEXT_HANDLE v16; // rcx
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+40h] [rbp-38h] BYREF

  hAuthzClientContext = 0;
  if ( AuthzInitializeContextFromToken(Flags, a2, a3, a4, Identifier, a7, &hAuthzClientContext) )
  {
    if ( a1 )
    {
      v15 = _InterlockedCompareExchange64((volatile signed __int64 *)a1, (signed __int64)hAuthzClientContext, 0);
      v16 = hAuthzClientContext;
      if ( v15 )
      {
        AuthzFreeContext(hAuthzClientContext);
        v16 = *a1;
        hAuthzClientContext = *a1;
      }
      return RpcpDuplicateAuthzContext(v16, a4, Identifier, Flags, a7, a8);
    }
    else
    {
      *a8 = hAuthzClientContext;
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    CurrentThreadId = GetCurrentThreadId();
    CompRpcpErrorAddRecord(v14, LastError, 0x1CCu, CurrentThreadId, (unsigned __int64)a3);
    return LastError;
  }
}

```

## disassembly

```asm
0x18007e730  mov     r11, rsp
0x18007e733  push    rbx
0x18007e734  push    rbp
0x18007e735  push    rsi
0x18007e736  push    rdi
0x18007e737  push    r14
0x18007e739  sub     rsp, 50h
0x18007e73d  mov     r14, [rsp+78h+arg_30]
0x18007e745  lea     rax, [r11-38h]
0x18007e749  mov     rbx, qword ptr [rsp+78h+Identifier.LowPart]
0x18007e751  mov     rdi, rcx
0x18007e754  mov     ecx, [rsp+78h+Flags]; Flags
0x18007e75b  mov     rbp, r9
0x18007e75e  mov     [r11-48h], rax
0x18007e762  mov     rsi, r8
0x18007e765  mov     [r11-50h], r14
0x18007e769  mov     [r11-58h], rbx
0x18007e76d  mov     qword ptr [r11-38h], 0
0x18007e775  call    cs:__imp_AuthzInitializeContextFromToken
0x18007e77c  nop     dword ptr [rax+rax+00h]
0x18007e781  test    eax, eax
0x18007e783  jz      short loc_18007E7A8
0x18007e785  test    rdi, rdi
0x18007e788  jnz     short loc_18007E7DB
0x18007e78a  mov     rax, [rsp+78h+hAuthzClientContext]
0x18007e78f  mov     rcx, [rsp+78h+arg_38]
0x18007e797  mov     [rcx], rax
0x18007e79a  xor     eax, eax
0x18007e79c  add     rsp, 50h
0x18007e7a0  pop     r14
0x18007e7a2  pop     rdi
0x18007e7a3  pop     rsi
0x18007e7a4  pop     rbp
0x18007e7a5  pop     rbx
0x18007e7a6  retn
0x18007e7a8  call    cs:__imp_GetLastError
0x18007e7af  nop     dword ptr [rax+rax+00h]
0x18007e7b4  mov     ebx, eax
0x18007e7b6  call    cs:__imp_GetCurrentThreadId
0x18007e7bd  nop     dword ptr [rax+rax+00h]
0x18007e7c2  mov     r8d, 1CCh; unsigned __int16
0x18007e7c8  mov     [rsp+78h+var_58], rsi; unsigned __int64
0x18007e7cd  mov     r9d, eax; unsigned int
0x18007e7d0  mov     edx, ebx; unsigned int
0x18007e7d2  call    ?CompRpcpErrorAddRecord@@YAXKKGK_K@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,unsigned __int64)
0x18007e7d7  mov     eax, ebx
0x18007e7d9  jmp     short loc_18007E79C
0x18007e7db  mov     rcx, [rsp+78h+hAuthzClientContext]
0x18007e7e0  xor     eax, eax
0x18007e7e2  lock cmpxchg [rdi], rcx
0x18007e7e7  mov     rcx, [rsp+78h+hAuthzClientContext]; hAuthzClientContext
0x18007e7ec  jz      short loc_18007E802
0x18007e7ee  call    cs:__imp_AuthzFreeContext
0x18007e7f5  nop     dword ptr [rax+rax+00h]
0x18007e7fa  mov     rcx, [rdi]; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *
0x18007e7fd  mov     [rsp+78h+hAuthzClientContext], rcx
0x18007e802  mov     rax, [rsp+78h+arg_38]
0x18007e80a  mov     r8, rbx; Identifier
0x18007e80d  mov     r9d, [rsp+78h+Flags]; Flags
0x18007e815  mov     rdx, rbp; pExpirationTime
0x18007e818  mov     [rsp+78h+var_50], rax; PAUTHZ_CLIENT_CONTEXT_HANDLE
0x18007e81d  mov     [rsp+78h+var_58], r14; PVOID
0x18007e822  call    ?RpcpDuplicateAuthzContext@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@KPEAXPEAPEAU1@@Z; RpcpDuplicateAuthzContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x18007e827  jmp     loc_18007E79C
```
