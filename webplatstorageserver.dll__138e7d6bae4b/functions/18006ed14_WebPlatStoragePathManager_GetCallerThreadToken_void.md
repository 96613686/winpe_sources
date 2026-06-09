# WebPlatStoragePathManager::GetCallerThreadToken(void)

- ea: `0x18006ed14`
- end: `0x18006ed9c`
- name: `?GetCallerThreadToken@WebPlatStoragePathManager@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `136`
- prototype: `PHANDLE __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180040900`
- `0x18006ec04`

## callees

- `0x1800566a0`
- `0x180061c90`
- `0x18006ed14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ed47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ed47`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ed61`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ed61`
- `RPCRT4!RpcRevertToSelf` at `0x18006ed87`
- `RPCRT4!RpcRevertToSelf` at `0x18006ed87`

## string_xrefs

- `0x18006ed6b`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\webplatstoragepathmanager.cxx`

## pseudocode

```c
PHANDLE __fastcall WebPlatStoragePathManager::GetCallerThreadToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v6; // [rsp+48h] [rbp+10h] BYREF

  RpcHelper::ImpersonateClient(&v6);
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\webplatstoragepathmanager.cxx",
      v3);
  if ( v6 )
    RpcRevertToSelf();
  return TokenHandle;
}

```

## disassembly

```asm
0x18006ed14  mov     rax, rsp
0x18006ed17  mov     [rax+18h], rbx
0x18006ed1b  mov     [rax+8], rcx
0x18006ed1f  push    rdi
0x18006ed20  sub     rsp, 30h
0x18006ed24  mov     rbx, rcx
0x18006ed27  mov     dword ptr [rax-18h], 0
0x18006ed2e  lea     rcx, [rax+10h]
0x18006ed32  call    ?ImpersonateClient@RpcHelper@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@PEAX@Z; RpcHelper::ImpersonateClient(void *)
0x18006ed37  nop
0x18006ed38  mov     qword ptr [rbx], 0
0x18006ed3f  mov     [rsp+38h+var_18], 1
0x18006ed47  call    cs:__imp_GetCurrentThread
0x18006ed4d  mov     rdi, [rsp+38h]
0x18006ed52  mov     r9, rbx; TokenHandle
0x18006ed55  mov     edx, 8; DesiredAccess
0x18006ed5a  lea     r8d, [rdx-7]; OpenAsSelf
0x18006ed5e  mov     rcx, rax; ThreadHandle
0x18006ed61  call    cs:__imp_OpenThreadToken
0x18006ed67  test    eax, eax
0x18006ed69  jnz     short loc_18006ED80
0x18006ed6b  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006ed72  mov     edx, 89h; void *
0x18006ed77  mov     rcx, rdi; this
0x18006ed7a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006ed80  cmp     [rsp+38h+arg_8], 0
0x18006ed85  jz      short loc_18006ED8D
0x18006ed87  call    cs:__imp_RpcRevertToSelf
0x18006ed8d  mov     rax, rbx
0x18006ed90  mov     rbx, [rsp+38h+arg_10]
0x18006ed95  add     rsp, 30h
0x18006ed99  pop     rdi
0x18006ed9a  retn
```
