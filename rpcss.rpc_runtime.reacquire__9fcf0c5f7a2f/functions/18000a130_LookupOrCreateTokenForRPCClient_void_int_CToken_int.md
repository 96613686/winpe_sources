# LookupOrCreateTokenForRPCClient(void *,int,CToken * *,int *)

- ea: `0x18000a130`
- end: `0x18000a403`
- name: `?LookupOrCreateTokenForRPCClient@@YAJPEAXHPEAPEAVCToken@@PEAH@Z`
- size: `723`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, int, struct CToken **, int *)`
- caller_count: `36`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009ff0`
- `0x18000a440`
- `0x18000a9f0`
- `0x18000ad70`
- `0x180025bc0`
- `0x180025df0`
- `0x1800562a0`
- `0x180073020`
- `0x18007aa60`
- `0x18007aef0`
- `0x18007f720`
- `0x1800835c0`
- `0x1800842d0`
- `0x18008c830`
- `0x18008e54c`
- `0x180093a10`
- `0x180097bb0`
- `0x18009baa0`
- `0x1800f2320`
- `0x1800f2430`
- `0x1800f27a0`
- `0x1800f28b0`
- `0x1800f2970`
- `0x1800f2fc0`
- `0x1800f3070`
- `0x1800f32b0`
- `0x1800f33e0`
- `0x1800f34b0`
- `0x1800f5234`
- `0x1800f65ec`
- `0x1800f7c60`
- `0x1800f7e60`
- `0x1800f7f40`
- `0x1800f8020`
- `0x180106240`
- `0x1801066cc`

## callees

- `0x18000a130`
- `0x18000b100`
- `0x18001c624`
- `0x180024590`
- `0x18002aa10`
- `0x1800375e0`
- `0x18009dfb4`
- `0x1800a7b14`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x18000a1fa`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000a20e`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000a1fa`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000a20e`
- `RPCRT4!RpcImpersonateClient` at `0x18000a15f`
- `RPCRT4!RpcImpersonateClient` at `0x18000a15f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a25b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a25b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3de`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a1d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a2dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a1d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a2dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a1b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a26e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a2be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a1b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a26e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a2be`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18000a27d`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18000a27d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a303`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a37a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a303`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a37a`

## string_xrefs

- `0x18000a1e6`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a233`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a292`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a2f2`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a356`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a39c`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a3bb`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000a33d`: `Allowing unsecure client; impersonating anonymous user.`
- `0x18000a34f`: `LookupOrCreateTokenForRPCClient`

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
  __int64 v20; // [rsp+20h] [rbp-28h]
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
        if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LODWORD(v20) = 1;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            "LookupOrCreateTokenForRPCClient",
            889,
            v20,
            L"Allowing unsecure client; impersonating anonymous user.");
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
0x18000a130  mov     [rsp+arg_0], rbx
0x18000a135  mov     [rsp+arg_8], rbp
0x18000a13a  push    rsi
0x18000a13b  push    rdi
0x18000a13c  push    r14
0x18000a13e  sub     rsp, 30h
0x18000a142  xor     ebp, ebp
0x18000a144  mov     rbx, r9
0x18000a147  mov     [rsp+48h+hObject], rbp
0x18000a14c  mov     r14, r8
0x18000a14f  mov     [r8], rbp
0x18000a152  mov     esi, edx
0x18000a154  mov     rdi, rcx
0x18000a157  test    r9, r9
0x18000a15a  jz      short loc_18000A15F
0x18000a15c  mov     [r9], ebp
0x18000a15f  call    cs:__imp_RpcImpersonateClient
0x18000a166  nop     dword ptr [rax+rax+00h]
0x18000a16b  test    eax, eax
0x18000a16d  jnz     loc_18000A21F
0x18000a173  mov     rsi, [rsp+48h+hObject]
0x18000a178  lea     rax, [rsi-1]
0x18000a17c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a180  ja      short loc_18000A1AD
0x18000a182  call    cs:__imp_GetLastError
0x18000a189  nop     dword ptr [rax+rax+00h]
0x18000a18e  mov     rcx, rsi; hObject
0x18000a191  mov     ebx, eax
0x18000a193  call    cs:__imp_CloseHandle
0x18000a19a  nop     dword ptr [rax+rax+00h]
0x18000a19f  mov     ecx, ebx; dwErrCode
0x18000a1a1  call    cs:__imp_SetLastError
0x18000a1a8  nop     dword ptr [rax+rax+00h]
0x18000a1ad  mov     [rsp+48h+hObject], rbp
0x18000a1b2  call    cs:__imp_GetCurrentThread
0x18000a1b9  nop     dword ptr [rax+rax+00h]
0x18000a1be  lea     r9, [rsp+48h+hObject]; TokenHandle
0x18000a1c3  mov     edx, 2000000h; DesiredAccess
0x18000a1c8  mov     rcx, rax; ThreadHandle
0x18000a1cb  mov     r8d, 1; OpenAsSelf
0x18000a1d1  call    cs:__imp_OpenThreadToken
0x18000a1d8  nop     dword ptr [rax+rax+00h]
0x18000a1dd  test    eax, eax
0x18000a1df  jnz     short loc_18000A20B
0x18000a1e1  mov     rcx, [rsp+48h]; this
0x18000a1e6  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a1ed  mov     edx, 354h; void *
0x18000a1f2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000a1f7  mov     rcx, rdi; BindingHandle
0x18000a1fa  call    cs:__imp_RpcRevertToSelfEx
0x18000a201  nop     dword ptr [rax+rax+00h]
0x18000a206  jmp     loc_18000A3CF
0x18000a20b  mov     rcx, rdi; BindingHandle
0x18000a20e  call    cs:__imp_RpcRevertToSelfEx
0x18000a215  nop     dword ptr [rax+rax+00h]
0x18000a21a  jmp     loc_18000A386
0x18000a21f  cmp     eax, 6E4h
0x18000a224  jnz     loc_18000A3B6
0x18000a22a  test    esi, esi
0x18000a22c  jnz     short loc_18000A26E
0x18000a22e  mov     rcx, [rsp+48h]; this
0x18000a233  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a23a  mov     r9d, 5; char *
0x18000a240  mov     edx, 35Dh; void *
0x18000a245  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000a24a  mov     rcx, [rsp+48h+hObject]; hObject
0x18000a24f  mov     ebx, eax
0x18000a251  lea     rdx, [rcx-1]
0x18000a255  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a259  ja      short loc_18000A267
0x18000a25b  call    cs:__imp_CloseHandle
0x18000a262  nop     dword ptr [rax+rax+00h]
0x18000a267  mov     eax, ebx
0x18000a269  jmp     loc_18000A3EF
0x18000a26e  call    cs:__imp_GetCurrentThread
0x18000a275  nop     dword ptr [rax+rax+00h]
0x18000a27a  mov     rcx, rax; ThreadHandle
0x18000a27d  call    cs:__imp_ImpersonateAnonymousToken
0x18000a284  nop     dword ptr [rax+rax+00h]
0x18000a289  test    eax, eax
0x18000a28b  jnz     short loc_18000A2B2
0x18000a28d  mov     rcx, [rsp+48h]; this
0x18000a292  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a299  mov     edx, 36Dh; void *
0x18000a29e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000a2a3  lea     rcx, [rsp+48h+hObject]
0x18000a2a8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a2ad  jmp     loc_18000A3EA
0x18000a2b2  xor     edx, edx
0x18000a2b4  lea     rcx, [rsp+48h+hObject]
0x18000a2b9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000a2be  call    cs:__imp_GetCurrentThread
0x18000a2c5  nop     dword ptr [rax+rax+00h]
0x18000a2ca  lea     r9, [rsp+48h+hObject]; TokenHandle
0x18000a2cf  mov     edx, 2000000h; DesiredAccess
0x18000a2d4  mov     rcx, rax; ThreadHandle
0x18000a2d7  mov     r8d, 1; OpenAsSelf
0x18000a2dd  call    cs:__imp_OpenThreadToken
0x18000a2e4  nop     dword ptr [rax+rax+00h]
0x18000a2e9  test    eax, eax
0x18000a2eb  jnz     short loc_18000A31E
0x18000a2ed  mov     rcx, [rsp+48h]; this
0x18000a2f2  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a2f9  mov     edx, 375h; void *
0x18000a2fe  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000a303  call    cs:__imp_RevertToSelf
0x18000a30a  nop     dword ptr [rax+rax+00h]
0x18000a30f  lea     rcx, [rsp+48h+hObject]
0x18000a314  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a319  jmp     loc_18000A3EA
0x18000a31e  mov     eax, cs:dword_1801574B8
0x18000a324  test    eax, eax
0x18000a326  jnz     short loc_18000A33D
0x18000a328  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x18000a32e  jz      short loc_18000A36F
0x18000a330  mov     rax, cs:WPP_GLOBAL_Control
0x18000a337  test    byte ptr [rax+1Ch], 2
0x18000a33b  jz      short loc_18000A36F
0x18000a33d  lea     rax, aAllowingUnsecu; "Allowing unsecure client; impersonating"...
0x18000a344  mov     r9d, 379h
0x18000a34a  mov     [rsp+48h+var_20], rax
0x18000a34f  lea     r8, aLookuporcreate_0; "LookupOrCreateTokenForRPCClient"
0x18000a356  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a35d  mov     dword ptr [rsp+48h+var_28], 1; unsigned int
0x18000a365  mov     ecx, 0FFFFFFFFh
0x18000a36a  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18000a36f  test    rbx, rbx
0x18000a372  jz      short loc_18000A37A
0x18000a374  mov     dword ptr [rbx], 1
0x18000a37a  call    cs:__imp_RevertToSelf
0x18000a381  nop     dword ptr [rax+rax+00h]
0x18000a386  mov     rcx, [rsp+48h+hObject]; void *
0x18000a38b  mov     rdx, r14; struct CToken **
0x18000a38e  call    ?LookupOrCreateTokenFromHandle@@YAJPEAXPEAPEAVCToken@@@Z; LookupOrCreateTokenFromHandle(void *,CToken * *)
0x18000a393  test    eax, eax
0x18000a395  jz      short loc_18000A3B2
0x18000a397  mov     rcx, [rsp+48h]; this
0x18000a39c  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a3a3  mov     r9d, eax; char *
0x18000a3a6  mov     edx, 387h; void *
0x18000a3ab  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000a3b0  jmp     short loc_18000A3CF
0x18000a3b2  xor     eax, eax
0x18000a3b4  jmp     short loc_18000A3EF
0x18000a3b6  mov     rcx, [rsp+48h]; this
0x18000a3bb  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000a3c2  mov     r9d, eax; char *
0x18000a3c5  mov     edx, 383h; void *
0x18000a3ca  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000a3cf  mov     rcx, [rsp+48h+hObject]; hObject
0x18000a3d4  lea     rax, [rcx-1]
0x18000a3d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a3dc  ja      short loc_18000A3EA
0x18000a3de  call    cs:__imp_CloseHandle
0x18000a3e5  nop     dword ptr [rax+rax+00h]
0x18000a3ea  mov     eax, 5
0x18000a3ef  mov     rbx, [rsp+48h+arg_0]
0x18000a3f4  mov     rbp, [rsp+48h+arg_8]
0x18000a3f9  add     rsp, 30h
0x18000a3fd  pop     r14
0x18000a3ff  pop     rdi
0x18000a400  pop     rsi
0x18000a401  retn
```
