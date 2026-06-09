# RpcpCreateAndSaveAuthzContextFromToken(AUTHZ_CLIENT_CONTEXT_HANDLE__ * *,void *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x18007cf64`
- end: `0x18007d044`
- name: `?RpcpCreateAndSaveAuthzContextFromToken@@YAJPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAXPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@K10@Z`
- size: `224`
- prototype: `int(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **, void *, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *, union _LARGE_INTEGER *, struct _LUID, unsigned int, void *, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009e000`

## callees

- `0x18007cf64`
- `0x18007d1c0`
- `0x1800b98b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cfd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007cfdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007cfdd`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007cfa9`
- `ext-ms-win-authz-context-l1-1-0!AuthzInitializeContextFromToken` at `0x18007cfa9`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeContext` at `0x18007d00f`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeContext` at `0x18007d00f`

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
0x18007cf64  mov     r11, rsp
0x18007cf67  push    rbx
0x18007cf68  push    rbp
0x18007cf69  push    rsi
0x18007cf6a  push    rdi
0x18007cf6b  push    r14
0x18007cf6d  sub     rsp, 50h
0x18007cf71  mov     r14, [rsp+78h+arg_30]
0x18007cf79  lea     rax, [r11-38h]
0x18007cf7d  mov     rbx, qword ptr [rsp+78h+Identifier.LowPart]
0x18007cf85  mov     rdi, rcx
0x18007cf88  mov     ecx, [rsp+78h+Flags]; Flags
0x18007cf8f  mov     rbp, r9
0x18007cf92  mov     [r11-48h], rax
0x18007cf96  mov     rsi, r8
0x18007cf99  mov     [r11-50h], r14
0x18007cf9d  mov     [r11-58h], rbx
0x18007cfa1  mov     qword ptr [r11-38h], 0
0x18007cfa9  call    cs:__imp_AuthzInitializeContextFromToken
0x18007cfaf  test    eax, eax
0x18007cfb1  jz      short loc_18007CFD5
0x18007cfb3  test    rdi, rdi
0x18007cfb6  jnz     short loc_18007CFFC
0x18007cfb8  mov     rax, [rsp+78h+hAuthzClientContext]
0x18007cfbd  mov     rcx, [rsp+78h+arg_38]
0x18007cfc5  mov     [rcx], rax
0x18007cfc8  xor     eax, eax
0x18007cfca  add     rsp, 50h
0x18007cfce  pop     r14
0x18007cfd0  pop     rdi
0x18007cfd1  pop     rsi
0x18007cfd2  pop     rbp
0x18007cfd3  pop     rbx
0x18007cfd4  retn
0x18007cfd5  call    cs:__imp_GetLastError
0x18007cfdb  mov     ebx, eax
0x18007cfdd  call    cs:__imp_GetCurrentThreadId
0x18007cfe3  mov     r8d, 1CCh; unsigned __int16
0x18007cfe9  mov     [rsp+78h+var_58], rsi; unsigned __int64
0x18007cfee  mov     r9d, eax; unsigned int
0x18007cff1  mov     edx, ebx; unsigned int
0x18007cff3  call    ?CompRpcpErrorAddRecord@@YAXKKGK_K@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,unsigned __int64)
0x18007cff8  mov     eax, ebx
0x18007cffa  jmp     short loc_18007CFCA
0x18007cffc  mov     rcx, [rsp+78h+hAuthzClientContext]
0x18007d001  xor     eax, eax
0x18007d003  lock cmpxchg [rdi], rcx
0x18007d008  mov     rcx, [rsp+78h+hAuthzClientContext]; hAuthzClientContext
0x18007d00d  jz      short loc_18007D01D
0x18007d00f  call    cs:__imp_AuthzFreeContext
0x18007d015  mov     rcx, [rdi]; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *
0x18007d018  mov     [rsp+78h+hAuthzClientContext], rcx
0x18007d01d  mov     rax, [rsp+78h+arg_38]
0x18007d025  mov     r8, rbx; Identifier
0x18007d028  mov     r9d, [rsp+78h+Flags]; Flags
0x18007d030  mov     rdx, rbp; pExpirationTime
0x18007d033  mov     [rsp+78h+var_50], rax; PAUTHZ_CLIENT_CONTEXT_HANDLE
0x18007d038  mov     [rsp+78h+var_58], r14; PVOID
0x18007d03d  call    ?RpcpDuplicateAuthzContext@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@KPEAXPEAPEAU1@@Z; RpcpDuplicateAuthzContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_LARGE_INTEGER *,_LUID,ulong,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x18007d042  jmp     short loc_18007CFCA
```
