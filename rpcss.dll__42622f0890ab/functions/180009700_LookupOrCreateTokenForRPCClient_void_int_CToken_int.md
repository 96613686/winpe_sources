# LookupOrCreateTokenForRPCClient(void *,int,CToken * *,int *)

- ea: `0x180009700`
- end: `0x180009972`
- name: `?LookupOrCreateTokenForRPCClient@@YAJPEAXHPEAPEAVCToken@@PEAH@Z`
- size: `626`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, int, struct CToken **, int *)`
- caller_count: `36`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800095c0`
- `0x1800099b0`
- `0x18002fac0`
- `0x18002fce0`
- `0x18002ff10`
- `0x18004a4d0`
- `0x18006e800`
- `0x1800763b0`
- `0x180078c40`
- `0x1800790d0`
- `0x18007add0`
- `0x18007ec90`
- `0x18007f9a0`
- `0x180087d70`
- `0x1800899b0`
- `0x18008c8c0`
- `0x180096570`
- `0x1800ea980`
- `0x1800eaa90`
- `0x1800eae00`
- `0x1800eaf10`
- `0x1800eafd0`
- `0x1800eb620`
- `0x1800eb6c0`
- `0x1800eb8f0`
- `0x1800eba20`
- `0x1800ebaf0`
- `0x1800ed6a8`
- `0x1800eea08`
- `0x1800effb0`
- `0x1800f01a0`
- `0x1800f0280`
- `0x1800f0350`
- `0x1800f0400`
- `0x1800fdab0`
- `0x1800fdef8`

## callees

- `0x180009700`
- `0x180018344`
- `0x18002834c`
- `0x18002ed28`
- `0x180031ae0`
- `0x180059e50`
- `0x1800989b0`
- `0x1800a2570`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x1800097a6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800097b4`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800097a6`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800097b4`
- `RPCRT4!RpcImpersonateClient` at `0x18000972f`
- `RPCRT4!RpcImpersonateClient` at `0x18000972f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000975f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000975f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000974c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000974c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009954`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009783`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009865`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009783`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000976a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000984c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000976a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000984c`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x180009811`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x180009811`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009885`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800098f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009885`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800098f6`

## string_xrefs

- `0x180009792`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800097d3`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180009820`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180009874`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800098d2`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180009912`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180009931`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800098b9`: `Allowing unsecure client; impersonating anonymous user.`
- `0x1800098cb`: `LookupOrCreateTokenForRPCClient`

## pseudocode

```c
__int64 __fastcall LookupOrCreateTokenForRPCClient(
        RPC_BINDING_HANDLE BindingHandle,
        int a2,
        struct CToken **a3,
        int *a4)
{
  unsigned int v8; // eax
  HANDLE v9; // rsi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v12; // r9
  unsigned int v13; // ebx
  HANDLE v15; // rax
  const char *v16; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  unsigned int TokenFromHandle; // eax
  unsigned int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hObject; // [rsp+60h] [rbp+18h] BYREF

  hObject = 0;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = RpcImpersonateClient(BindingHandle);
  if ( !v8 )
  {
    v9 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v9);
      SetLastError(LastError);
    }
    hObject = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000000u, 1, &hObject) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x354,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        v12);
      RpcRevertToSelfEx(BindingHandle);
      goto LABEL_29;
    }
    RpcRevertToSelfEx(BindingHandle);
LABEL_25:
    TokenFromHandle = LookupOrCreateTokenFromHandle(hObject, a3);
    if ( !TokenFromHandle )
      return 0;
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x387,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)TokenFromHandle,
      v20);
    goto LABEL_29;
  }
  if ( v8 != 1764 )
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x383,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (const char *)v8,
      v20);
LABEL_29:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 5;
  }
  if ( a2 )
  {
    v15 = GetCurrentThread();
    if ( ImpersonateAnonymousToken(v15) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v17 = GetCurrentThread();
      if ( OpenThreadToken(v17, 0x2000000u, 1, &hObject) )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v20 = 1;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            "LookupOrCreateTokenForRPCClient",
            889);
        }
        if ( a4 )
          *a4 = 1;
        RevertToSelf();
        goto LABEL_25;
      }
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x375,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        v18);
      RevertToSelf();
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x36D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        v16);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    }
    return 5;
  }
  v13 = wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x35D,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (const char *)5,
          v20);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v13;
}

```

## disassembly

```asm
0x180009700  mov     [rsp+arg_0], rbx
0x180009705  mov     [rsp+arg_8], rbp
0x18000970a  push    rsi
0x18000970b  push    rdi
0x18000970c  push    r14
0x18000970e  sub     rsp, 30h
0x180009712  xor     ebp, ebp
0x180009714  mov     rbx, r9
0x180009717  mov     [rsp+48h+hObject], rbp
0x18000971c  mov     r14, r8
0x18000971f  mov     [r8], rbp
0x180009722  mov     esi, edx
0x180009724  mov     rdi, rcx
0x180009727  test    r9, r9
0x18000972a  jz      short loc_18000972F
0x18000972c  mov     [r9], ebp
0x18000972f  call    cs:__imp_RpcImpersonateClient
0x180009735  test    eax, eax
0x180009737  jnz     loc_1800097BF
0x18000973d  mov     rsi, [rsp+48h+hObject]
0x180009742  lea     rax, [rsi-1]
0x180009746  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000974a  ja      short loc_180009765
0x18000974c  call    cs:__imp_GetLastError
0x180009752  mov     rcx, rsi; hObject
0x180009755  mov     ebx, eax
0x180009757  call    cs:__imp_CloseHandle
0x18000975d  mov     ecx, ebx; dwErrCode
0x18000975f  call    cs:__imp_SetLastError
0x180009765  mov     [rsp+48h+hObject], rbp
0x18000976a  call    cs:__imp_GetCurrentThread
0x180009770  lea     r9, [rsp+48h+hObject]; TokenHandle
0x180009775  mov     edx, 2000000h; DesiredAccess
0x18000977a  mov     rcx, rax; ThreadHandle
0x18000977d  mov     r8d, 1; OpenAsSelf
0x180009783  call    cs:__imp_OpenThreadToken
0x180009789  test    eax, eax
0x18000978b  jnz     short loc_1800097B1
0x18000978d  mov     rcx, [rsp+48h]; this
0x180009792  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180009799  mov     edx, 354h; void *
0x18000979e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800097a3  mov     rcx, rdi; BindingHandle
0x1800097a6  call    cs:__imp_RpcRevertToSelfEx
0x1800097ac  jmp     loc_180009945
0x1800097b1  mov     rcx, rdi; BindingHandle
0x1800097b4  call    cs:__imp_RpcRevertToSelfEx
0x1800097ba  jmp     loc_1800098FC
0x1800097bf  cmp     eax, 6E4h
0x1800097c4  jnz     loc_18000992C
0x1800097ca  test    esi, esi
0x1800097cc  jnz     short loc_180009808
0x1800097ce  mov     rcx, [rsp+48h]; this
0x1800097d3  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x1800097da  mov     r9d, 5; char *
0x1800097e0  mov     edx, 35Dh; void *
0x1800097e5  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800097ea  mov     rcx, [rsp+48h+hObject]; hObject
0x1800097ef  mov     ebx, eax
0x1800097f1  lea     rdx, [rcx-1]
0x1800097f5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800097f9  ja      short loc_180009801
0x1800097fb  call    cs:__imp_CloseHandle
0x180009801  mov     eax, ebx
0x180009803  jmp     loc_18000995F
0x180009808  call    cs:__imp_GetCurrentThread
0x18000980e  mov     rcx, rax; ThreadHandle
0x180009811  call    cs:__imp_ImpersonateAnonymousToken
0x180009817  test    eax, eax
0x180009819  jnz     short loc_180009840
0x18000981b  mov     rcx, [rsp+48h]; this
0x180009820  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180009827  mov     edx, 36Dh; void *
0x18000982c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180009831  lea     rcx, [rsp+48h+hObject]
0x180009836  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000983b  jmp     loc_18000995A
0x180009840  xor     edx, edx
0x180009842  lea     rcx, [rsp+48h+hObject]
0x180009847  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000984c  call    cs:__imp_GetCurrentThread
0x180009852  lea     r9, [rsp+48h+hObject]; TokenHandle
0x180009857  mov     edx, 2000000h; DesiredAccess
0x18000985c  mov     rcx, rax; ThreadHandle
0x18000985f  mov     r8d, 1; OpenAsSelf
0x180009865  call    cs:__imp_OpenThreadToken
0x18000986b  test    eax, eax
0x18000986d  jnz     short loc_18000989A
0x18000986f  mov     rcx, [rsp+48h]; this
0x180009874  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000987b  mov     edx, 375h; void *
0x180009880  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180009885  call    cs:__imp_RevertToSelf
0x18000988b  lea     rcx, [rsp+48h+hObject]
0x180009890  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009895  jmp     loc_18000995A
0x18000989a  mov     eax, cs:dword_18014E4B8
0x1800098a0  test    eax, eax
0x1800098a2  jnz     short loc_1800098B9
0x1800098a4  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x1800098aa  jz      short loc_1800098EB
0x1800098ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800098b3  test    byte ptr [rax+1Ch], 2
0x1800098b7  jz      short loc_1800098EB
0x1800098b9  lea     rax, aAllowingUnsecu; "Allowing unsecure client; impersonating"...
0x1800098c0  mov     r9d, 379h
0x1800098c6  mov     [rsp+48h+var_20], rax
0x1800098cb  lea     r8, aLookuporcreate_0; "LookupOrCreateTokenForRPCClient"
0x1800098d2  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x1800098d9  mov     [rsp+48h+var_28], 1; unsigned int
0x1800098e1  mov     ecx, 0FFFFFFFFh
0x1800098e6  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800098eb  test    rbx, rbx
0x1800098ee  jz      short loc_1800098F6
0x1800098f0  mov     dword ptr [rbx], 1
0x1800098f6  call    cs:__imp_RevertToSelf
0x1800098fc  mov     rcx, [rsp+48h+hObject]; void *
0x180009901  mov     rdx, r14; struct CToken **
0x180009904  call    ?LookupOrCreateTokenFromHandle@@YAJPEAXPEAPEAVCToken@@@Z; LookupOrCreateTokenFromHandle(void *,CToken * *)
0x180009909  test    eax, eax
0x18000990b  jz      short loc_180009928
0x18000990d  mov     rcx, [rsp+48h]; this
0x180009912  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180009919  mov     r9d, eax; char *
0x18000991c  mov     edx, 387h; void *
0x180009921  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180009926  jmp     short loc_180009945
0x180009928  xor     eax, eax
0x18000992a  jmp     short loc_18000995F
0x18000992c  mov     rcx, [rsp+48h]; this
0x180009931  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180009938  mov     r9d, eax; char *
0x18000993b  mov     edx, 383h; void *
0x180009940  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180009945  mov     rcx, [rsp+48h+hObject]; hObject
0x18000994a  lea     rax, [rcx-1]
0x18000994e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009952  ja      short loc_18000995A
0x180009954  call    cs:__imp_CloseHandle
0x18000995a  mov     eax, 5
0x18000995f  mov     rbx, [rsp+48h+arg_0]
0x180009964  mov     rbp, [rsp+48h+arg_8]
0x180009969  add     rsp, 30h
0x18000996d  pop     r14
0x18000996f  pop     rdi
0x180009970  pop     rsi
0x180009971  retn
```
