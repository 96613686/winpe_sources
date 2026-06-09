# RpcpDuplicateAuthzContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x1800b98b0`
- end: `0x1800b991e`
- name: `?RpcpDuplicateAuthzContext@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@KPEAXPEAPEAU1@@Z`
- size: `110`
- prototype: `__int64 __fastcall(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *, PLARGE_INTEGER pExpirationTime, LUID Identifier, DWORD Flags, PVOID, PAUTHZ_CLIENT_CONTEXT_HANDLE)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007cf64`
- `0x18009e000`

## callees

- `0x18007d1c0`
- `0x1800b98b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b98f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b98f2`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromAuthzContext` at `0x1800b98e0`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromAuthzContext` at `0x1800b98e0`

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
0x1800b98b0  mov     [rsp+arg_0], rbx
0x1800b98b5  push    rdi
0x1800b98b6  sub     rsp, 30h
0x1800b98ba  mov     rax, [rsp+38h+arg_28]
0x1800b98bf  mov     r10d, r9d
0x1800b98c2  mov     [rsp+38h+phNewAuthzClientContext], rax; phNewAuthzClientContext
0x1800b98c7  mov     r9, r8; Identifier
0x1800b98ca  mov     rax, [rsp+38h+arg_20]
0x1800b98cf  mov     r8, rdx; pExpirationTime
0x1800b98d2  mov     rdx, rcx; hAuthzClientContext
0x1800b98d5  mov     [rsp+38h+DynamicGroupArgs], rax; DynamicGroupArgs
0x1800b98da  mov     rdi, rcx
0x1800b98dd  mov     ecx, r10d; Flags
0x1800b98e0  call    cs:__imp_AuthzInitializeContextFromAuthzContext
0x1800b98e6  test    eax, eax
0x1800b98e8  jnz     short loc_1800B990F
0x1800b98ea  call    cs:__imp_GetLastError
0x1800b98f0  mov     ebx, eax
0x1800b98f2  call    cs:__imp_GetCurrentThreadId
0x1800b98f8  mov     r8d, 1C2h; unsigned __int16
0x1800b98fe  mov     [rsp+38h+DynamicGroupArgs], rdi; unsigned __int64
0x1800b9903  mov     r9d, eax; unsigned int
0x1800b9906  mov     edx, ebx; unsigned int
0x1800b9908  call    ?CompRpcpErrorAddRecord@@YAXKKGK_K@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,unsigned __int64)
0x1800b990d  jmp     short loc_1800B9911
0x1800b990f  xor     ebx, ebx
0x1800b9911  mov     eax, ebx
0x1800b9913  mov     rbx, [rsp+38h+arg_0]
0x1800b9918  add     rsp, 30h
0x1800b991c  pop     rdi
0x1800b991d  retn
```
