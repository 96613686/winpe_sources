# Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsDeviceOwner(void)

- ea: `0x1802b4a70`
- end: `0x1802b4bf4`
- name: `?CheckRpcCallerIsDeviceOwner@ApiServer@Diagnostics@Microsoft@@IEAAJXZ`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ApiServer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f68c0`

## callees

- `0x180026ecc`
- `0x18008bd1c`
- `0x1800a0d08`
- `0x1802b47f4`
- `0x1802b4a70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802b4b1c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802b4b1c`
- `RPCRT4!RpcImpersonateClient` at `0x1802b4a7f`
- `RPCRT4!RpcImpersonateClient` at `0x1802b4a7f`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4ae2`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4b44`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4b94`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4bbf`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4ae2`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4b44`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4b94`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4bbf`

## string_xrefs

- `0x1802b4a94`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4ace`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4af7`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4b31`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4b5d`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4b7b`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4bad`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4bd4`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsDeviceOwner(
        Microsoft::Diagnostics::ApiServer *this)
{
  unsigned int LastError; // ebx
  int DeviceOwnerSid; // eax
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
      (void *)0xED,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    return LastError;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    DeviceOwnerSid = Microsoft::Diagnostics::ApiServer::AllocateDeviceOwnerSid(this);
    LastError = DeviceOwnerSid;
    if ( DeviceOwnerSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        (const char *)(unsigned int)DeviceOwnerSid,
        v11);
      if ( RpcRevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
          v5);
      return LastError;
    }
  }
  v6 = (void *)*((_QWORD *)this + 2);
  IsMember = 0;
  if ( !CheckTokenMembership(0, v6, &IsMember) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x103,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
                  v7);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v8);
    return LastError;
  }
  if ( !IsMember )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v9);
    return LastError;
  }
  if ( RpcRevertToSelf() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      v10);
  return 0;
}

```

## disassembly

```asm
0x1802b4a70  mov     [rsp+arg_0], rbx
0x1802b4a75  push    rdi; int
0x1802b4a76  sub     rsp, 20h
0x1802b4a7a  mov     rdi, rcx
0x1802b4a7d  xor     ecx, ecx; BindingHandle
0x1802b4a7f  call    cs:__imp_RpcImpersonateClient
0x1802b4a86  nop     dword ptr [rax+rax+00h]
0x1802b4a8b  test    eax, eax
0x1802b4a8d  jz      short loc_1802B4AB4
0x1802b4a8f  mov     rcx, [rsp+28h]; this
0x1802b4a94  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4a9b  mov     ebx, 80070005h
0x1802b4aa0  mov     edx, 0EDh; void *
0x1802b4aa5  mov     r9d, ebx; char *
0x1802b4aa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4aad  mov     eax, ebx
0x1802b4aaf  jmp     loc_1802B4BE8
0x1802b4ab4  cmp     qword ptr [rdi+10h], 0
0x1802b4ab9  jnz     short loc_1802B4B09
0x1802b4abb  mov     rcx, rdi; this
0x1802b4abe  call    ?AllocateDeviceOwnerSid@ApiServer@Diagnostics@Microsoft@@IEAAJXZ; Microsoft::Diagnostics::ApiServer::AllocateDeviceOwnerSid(void)
0x1802b4ac3  mov     ebx, eax
0x1802b4ac5  test    eax, eax
0x1802b4ac7  jns     short loc_1802B4B09
0x1802b4ac9  mov     rcx, [rsp+28h]; this
0x1802b4ace  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4ad5  mov     r9d, eax; char *
0x1802b4ad8  mov     edx, 0FFh; void *
0x1802b4add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4ae2  call    cs:__imp_RpcRevertToSelf
0x1802b4ae9  nop     dword ptr [rax+rax+00h]
0x1802b4aee  test    eax, eax
0x1802b4af0  jz      short loc_1802B4AAD
0x1802b4af2  mov     rcx, [rsp+28h]; this
0x1802b4af7  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4afe  mov     edx, 0F8h; void *
0x1802b4b03  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b4b09  mov     rdx, [rdi+10h]; SidToCheck
0x1802b4b0d  lea     r8, [rsp+28h+IsMember]; IsMember
0x1802b4b12  xor     ecx, ecx; TokenHandle
0x1802b4b14  mov     [rsp+28h+IsMember], 0
0x1802b4b1c  call    cs:__imp_CheckTokenMembership
0x1802b4b23  nop     dword ptr [rax+rax+00h]
0x1802b4b28  test    eax, eax
0x1802b4b2a  jnz     short loc_1802B4B6F
0x1802b4b2c  mov     rcx, [rsp+28h]; this
0x1802b4b31  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4b38  mov     edx, 103h; void *
0x1802b4b3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802b4b42  mov     ebx, eax
0x1802b4b44  call    cs:__imp_RpcRevertToSelf
0x1802b4b4b  nop     dword ptr [rax+rax+00h]
0x1802b4b50  test    eax, eax
0x1802b4b52  jz      loc_1802B4AAD
0x1802b4b58  mov     rcx, [rsp+28h]; this
0x1802b4b5d  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4b64  mov     edx, 0F8h; void *
0x1802b4b69  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b4b6f  cmp     [rsp+28h+IsMember], 0
0x1802b4b74  jnz     short loc_1802B4BBF
0x1802b4b76  mov     rcx, [rsp+28h]; this
0x1802b4b7b  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4b82  mov     ebx, 80070005h
0x1802b4b87  mov     edx, 106h; void *
0x1802b4b8c  mov     r9d, ebx; char *
0x1802b4b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4b94  call    cs:__imp_RpcRevertToSelf
0x1802b4b9b  nop     dword ptr [rax+rax+00h]
0x1802b4ba0  test    eax, eax
0x1802b4ba2  jz      loc_1802B4AAD
0x1802b4ba8  mov     rcx, [rsp+28h]; this
0x1802b4bad  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4bb4  mov     edx, 0F8h; void *
0x1802b4bb9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b4bbf  call    cs:__imp_RpcRevertToSelf
0x1802b4bc6  nop     dword ptr [rax+rax+00h]
0x1802b4bcb  test    eax, eax
0x1802b4bcd  jz      short loc_1802B4BE6
0x1802b4bcf  mov     rcx, [rsp+28h]; this
0x1802b4bd4  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4bdb  mov     edx, 0F8h; void *
0x1802b4be0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b4be6  xor     eax, eax
0x1802b4be8  mov     rbx, [rsp+28h+arg_0]
0x1802b4bed  add     rsp, 20h
0x1802b4bf1  pop     rdi
0x1802b4bf2  retn
```
