# Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsAdmin(void)

- ea: `0x1802b48e4`
- end: `0x1802b4a68`
- name: `?CheckRpcCallerIsAdmin@ApiServer@Diagnostics@Microsoft@@IEAAJXZ`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ApiServer *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f68c0`
- `0x1801d1c08`
- `0x1801d1f3c`
- `0x1801d2204`
- `0x1801d3480`
- `0x1801e33b0`
- `0x1801e3c70`

## callees

- `0x180026ecc`
- `0x18008bd1c`
- `0x1800a0d08`
- `0x1802b4704`
- `0x1802b48e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802b4990`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802b4990`
- `RPCRT4!RpcImpersonateClient` at `0x1802b48f3`
- `RPCRT4!RpcImpersonateClient` at `0x1802b48f3`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4956`
- `RPCRT4!RpcRevertToSelf` at `0x1802b49b8`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4a08`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4a33`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4956`
- `RPCRT4!RpcRevertToSelf` at `0x1802b49b8`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4a08`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4a33`

## string_xrefs

- `0x1802b4908`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4942`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b496b`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b49a5`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b49d1`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b49ef`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4a21`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4a48`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsAdmin(Microsoft::Diagnostics::ApiServer *this)
{
  unsigned int LastError; // ebx
  int AdminSid; // eax
  const char *v5; // r9
  void *v6; // rdx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF

  if ( RpcImpersonateClient(0) )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    return LastError;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    AdminSid = Microsoft::Diagnostics::ApiServer::AllocateAdminSid(this);
    LastError = AdminSid;
    if ( AdminSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        (const char *)(unsigned int)AdminSid,
        v11);
      if ( RpcRevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xCB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
          v5);
      return LastError;
    }
  }
  v6 = (void *)*((_QWORD *)this + 1);
  IsMember = 0;
  if ( !CheckTokenMembership(0, v6, &IsMember) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD6,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
                  v7);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v8);
    return LastError;
  }
  if ( !IsMember )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v9);
    return LastError;
  }
  if ( RpcRevertToSelf() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      v10);
  return 0;
}

```

## disassembly

```asm
0x1802b48e4  mov     [rsp+arg_0], rbx
0x1802b48e9  push    rdi; int
0x1802b48ea  sub     rsp, 20h
0x1802b48ee  mov     rdi, rcx
0x1802b48f1  xor     ecx, ecx; BindingHandle
0x1802b48f3  call    cs:__imp_RpcImpersonateClient
0x1802b48fa  nop     dword ptr [rax+rax+00h]
0x1802b48ff  test    eax, eax
0x1802b4901  jz      short loc_1802B4928
0x1802b4903  mov     rcx, [rsp+28h]; this
0x1802b4908  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b490f  mov     ebx, 80070005h
0x1802b4914  mov     edx, 0C0h; void *
0x1802b4919  mov     r9d, ebx; char *
0x1802b491c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4921  mov     eax, ebx
0x1802b4923  jmp     loc_1802B4A5C
0x1802b4928  cmp     qword ptr [rdi+8], 0
0x1802b492d  jnz     short loc_1802B497D
0x1802b492f  mov     rcx, rdi; this
0x1802b4932  call    ?AllocateAdminSid@ApiServer@Diagnostics@Microsoft@@IEAAJXZ; Microsoft::Diagnostics::ApiServer::AllocateAdminSid(void)
0x1802b4937  mov     ebx, eax
0x1802b4939  test    eax, eax
0x1802b493b  jns     short loc_1802B497D
0x1802b493d  mov     rcx, [rsp+28h]; this
0x1802b4942  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4949  mov     r9d, eax; char *
0x1802b494c  mov     edx, 0D2h; void *
0x1802b4951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4956  call    cs:__imp_RpcRevertToSelf
0x1802b495d  nop     dword ptr [rax+rax+00h]
0x1802b4962  test    eax, eax
0x1802b4964  jz      short loc_1802B4921
0x1802b4966  mov     rcx, [rsp+28h]; this
0x1802b496b  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4972  mov     edx, 0CBh; void *
0x1802b4977  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b497d  mov     rdx, [rdi+8]; SidToCheck
0x1802b4981  lea     r8, [rsp+28h+IsMember]; IsMember
0x1802b4986  xor     ecx, ecx; TokenHandle
0x1802b4988  mov     [rsp+28h+IsMember], 0
0x1802b4990  call    cs:__imp_CheckTokenMembership
0x1802b4997  nop     dword ptr [rax+rax+00h]
0x1802b499c  test    eax, eax
0x1802b499e  jnz     short loc_1802B49E3
0x1802b49a0  mov     rcx, [rsp+28h]; this
0x1802b49a5  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b49ac  mov     edx, 0D6h; void *
0x1802b49b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b49b6  mov     ebx, eax
0x1802b49b8  call    cs:__imp_RpcRevertToSelf
0x1802b49bf  nop     dword ptr [rax+rax+00h]
0x1802b49c4  test    eax, eax
0x1802b49c6  jz      loc_1802B4921
0x1802b49cc  mov     rcx, [rsp+28h]; this
0x1802b49d1  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b49d8  mov     edx, 0CBh; void *
0x1802b49dd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b49e3  cmp     [rsp+28h+IsMember], 0
0x1802b49e8  jnz     short loc_1802B4A33
0x1802b49ea  mov     rcx, [rsp+28h]; this
0x1802b49ef  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b49f6  mov     ebx, 80070005h
0x1802b49fb  mov     edx, 0D9h; void *
0x1802b4a00  mov     r9d, ebx; char *
0x1802b4a03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4a08  call    cs:__imp_RpcRevertToSelf
0x1802b4a0f  nop     dword ptr [rax+rax+00h]
0x1802b4a14  test    eax, eax
0x1802b4a16  jz      loc_1802B4921
0x1802b4a1c  mov     rcx, [rsp+28h]; this
0x1802b4a21  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4a28  mov     edx, 0CBh; void *
0x1802b4a2d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b4a33  call    cs:__imp_RpcRevertToSelf
0x1802b4a3a  nop     dword ptr [rax+rax+00h]
0x1802b4a3f  test    eax, eax
0x1802b4a41  jz      short loc_1802B4A5A
0x1802b4a43  mov     rcx, [rsp+28h]; this
0x1802b4a48  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4a4f  mov     edx, 0CBh; void *
0x1802b4a54  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b4a5a  xor     eax, eax
0x1802b4a5c  mov     rbx, [rsp+28h+arg_0]
0x1802b4a61  add     rsp, 20h
0x1802b4a65  pop     rdi
0x1802b4a66  retn
```
