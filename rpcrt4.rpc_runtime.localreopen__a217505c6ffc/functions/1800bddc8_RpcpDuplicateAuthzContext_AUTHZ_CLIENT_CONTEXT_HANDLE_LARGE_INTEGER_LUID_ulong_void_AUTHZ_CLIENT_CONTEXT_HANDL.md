# RpcpDuplicateAuthzContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x1800bddc8`
- end: `0x1800bde49`
- name: `?RpcpDuplicateAuthzContext@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@KPEAXPEAPEAU1@@Z`
- size: `129`
- prototype: `__int64 __fastcall(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *, PLARGE_INTEGER pExpirationTime, LUID Identifier, DWORD Flags, PVOID, PAUTHZ_CLIENT_CONTEXT_HANDLE)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e730`
- `0x1800a19f0`

## callees

- `0x18007e9e0`
- `0x1800bddc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bde08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bde08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bde16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bde16`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromAuthzContext` at `0x1800bddf8`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromAuthzContext` at `0x1800bddf8`

## pseudocode

```c
__int64 __fastcall RpcpDuplicateAuthzContext(
        AUTHZ_CLIENT_CONTEXT_HANDLE a1,
        PLARGE_INTEGER pExpirationTime,
        LUID Identifier,
        DWORD Flags,
        PVOID DynamicGroupArgs,
        PAUTHZ_CLIENT_CONTEXT_HANDLE phNewAuthzClientContext)
{
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v9; // ecx

  if ( AuthzInitializeContextFromAuthzContext(
         Flags,
         a1,
         pExpirationTime,
         Identifier,
         DynamicGroupArgs,
         phNewAuthzClientContext) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    CurrentThreadId = GetCurrentThreadId();
    CompRpcpErrorAddRecord(v9, LastError, 0x1C2u, CurrentThreadId, (unsigned __int64)a1);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800bddc8  mov     [rsp+arg_0], rbx
0x1800bddcd  push    rdi
0x1800bddce  sub     rsp, 30h
0x1800bddd2  mov     rax, [rsp+38h+arg_28]
0x1800bddd7  mov     r10d, r9d
0x1800bddda  mov     [rsp+38h+phNewAuthzClientContext], rax; phNewAuthzClientContext
0x1800bdddf  mov     r9, r8; Identifier
0x1800bdde2  mov     rax, [rsp+38h+arg_20]
0x1800bdde7  mov     r8, rdx; pExpirationTime
0x1800bddea  mov     rdx, rcx; hAuthzClientContext
0x1800bdded  mov     [rsp+38h+DynamicGroupArgs], rax; DynamicGroupArgs
0x1800bddf2  mov     rdi, rcx
0x1800bddf5  mov     ecx, r10d; Flags
0x1800bddf8  call    cs:__imp_AuthzInitializeContextFromAuthzContext
0x1800bddff  nop     dword ptr [rax+rax+00h]
0x1800bde04  test    eax, eax
0x1800bde06  jnz     short loc_1800BDE39
0x1800bde08  call    cs:__imp_GetLastError
0x1800bde0f  nop     dword ptr [rax+rax+00h]
0x1800bde14  mov     ebx, eax
0x1800bde16  call    cs:__imp_GetCurrentThreadId
0x1800bde1d  nop     dword ptr [rax+rax+00h]
0x1800bde22  mov     r8d, 1C2h; unsigned __int16
0x1800bde28  mov     [rsp+38h+DynamicGroupArgs], rdi; unsigned __int64
0x1800bde2d  mov     r9d, eax; unsigned int
0x1800bde30  mov     edx, ebx; unsigned int
0x1800bde32  call    ?CompRpcpErrorAddRecord@@YAXKKGK_K@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,unsigned __int64)
0x1800bde37  jmp     short loc_1800BDE3B
0x1800bde39  xor     ebx, ebx
0x1800bde3b  mov     eax, ebx
0x1800bde3d  mov     rbx, [rsp+38h+arg_0]
0x1800bde42  add     rsp, 30h
0x1800bde46  pop     rdi
0x1800bde47  retn
```
