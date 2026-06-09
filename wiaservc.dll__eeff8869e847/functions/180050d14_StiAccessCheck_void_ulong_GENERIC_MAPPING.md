# StiAccessCheck(void *,ulong,_GENERIC_MAPPING *)

- ea: `0x180050d14`
- end: `0x180050e1e`
- name: `?StiAccessCheck@@YAKPEAXKPEAU_GENERIC_MAPPING@@@Z`
- size: `266`
- prototype: `RPC_STATUS __fastcall(void *, __int64, struct _GENERIC_MAPPING *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180051eb0`
- `0x1800522f0`
- `0x180052430`
- `0x180052520`
- `0x180052750`
- `0x180052a10`
- `0x180052b50`

## callees

- `0x180033cc0`
- `0x180050d14`
- `0x180059d34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180050d88`
- `KERNEL32!GetLastError` at `0x180050d88`
- `KERNEL32!CloseHandle` at `0x180050dfd`
- `KERNEL32!CloseHandle` at `0x18007789e`
- `KERNEL32!CloseHandle` at `0x180050dfd`
- `KERNEL32!CloseHandle` at `0x18007789e`
- `RPCRT4!RpcImpersonateClient` at `0x180050d59`
- `RPCRT4!RpcImpersonateClient` at `0x180050d59`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180050d7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180050d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180050d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180050d67`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180050dd7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180050dd7`

## pseudocode

```c
RPC_STATUS __fastcall StiAccessCheck(void *a1, __int64 a2, struct _GENERIC_MAPPING *a3)
{
  PSECURITY_DESCRIPTOR v3; // rbx
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  DWORD PrivilegeSetLength; // [rsp+40h] [rbp-238h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-234h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-230h] BYREF
  DWORD GrantedAccess[4]; // [rsp+50h] [rbp-228h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-218h] BYREF

  v3 = sdApiObject;
  TokenHandle = 0;
  GrantedAccess[0] = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 0;
  result = RpcImpersonateClient(0);
  if ( !result )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
      && (PrivilegeSetLength = 500,
          AccessCheck(
            v3,
            TokenHandle,
            0x20015u,
            &ApiObjectMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            GrantedAccess,
            &AccessStatus)) )
    {
      LastError = AccessStatus == 0 ? 5 : 0;
    }
    else
    {
      LastError = GetLastError();
    }
    SafeRpcRevertToSelf();
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180050d14  push    rbx
0x180050d16  sub     rsp, 270h
0x180050d1d  mov     rax, cs:__security_cookie
0x180050d24  xor     rax, rsp
0x180050d27  mov     [rsp+278h+var_18], rax
0x180050d2f  mov     rbx, cs:?sdApiObject@@3PEAXEA; void * sdApiObject
0x180050d36  mov     [rsp+278h+TokenHandle], 0
0x180050d3f  mov     [rsp+278h+var_228], 0
0x180050d47  mov     [rsp+278h+var_234], 0
0x180050d4f  mov     [rsp+278h+var_238], 0
0x180050d57  xor     ecx, ecx; BindingHandle
0x180050d59  call    cs:__imp_RpcImpersonateClient
0x180050d5f  test    eax, eax
0x180050d61  jnz     loc_180050E05
0x180050d67  call    cs:__imp_GetCurrentThread
0x180050d6d  mov     rcx, rax; ThreadHandle
0x180050d70  lea     r9, [rsp+278h+TokenHandle]; TokenHandle
0x180050d75  mov     edx, 8; DesiredAccess
0x180050d7a  lea     r8d, [rdx-7]; OpenAsSelf
0x180050d7e  call    cs:__imp_OpenThreadToken
0x180050d84  test    eax, eax
0x180050d86  jnz     short loc_180050D92
0x180050d88  call    cs:__imp_GetLastError
0x180050d8e  mov     ebx, eax
0x180050d90  jmp     short loc_180050DEE
0x180050d92  mov     [rsp+278h+var_238], 1F4h
0x180050d9a  lea     rax, [rsp+278h+var_234]
0x180050d9f  mov     [rsp+278h+AccessStatus], rax; AccessStatus
0x180050da4  lea     rax, [rsp+278h+var_228]
0x180050da9  mov     [rsp+278h+GrantedAccess], rax; GrantedAccess
0x180050dae  lea     rax, [rsp+278h+var_238]
0x180050db3  mov     [rsp+278h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180050db8  lea     rax, [rsp+278h+var_218]
0x180050dbd  mov     [rsp+278h+PrivilegeSet], rax; PrivilegeSet
0x180050dc2  lea     r9, ?ApiObjectMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x180050dc9  mov     r8d, 20015h; DesiredAccess
0x180050dcf  mov     rdx, [rsp+278h+TokenHandle]; ClientToken
0x180050dd4  mov     rcx, rbx; pSecurityDescriptor
0x180050dd7  call    cs:__imp_AccessCheck
0x180050ddd  test    eax, eax
0x180050ddf  jz      short loc_180050D88
0x180050de1  mov     eax, [rsp+278h+var_234]
0x180050de5  neg     eax
0x180050de7  sbb     ebx, ebx
0x180050de9  not     ebx
0x180050deb  and     ebx, 5
0x180050dee  call    ?SafeRpcRevertToSelf@@YAKXZ; SafeRpcRevertToSelf(void)
0x180050df3  mov     rcx, [rsp+278h+TokenHandle]; hObject
0x180050df8  test    rcx, rcx
0x180050dfb  jz      short loc_180050E03
0x180050dfd  call    cs:__imp_CloseHandle
0x180050e03  mov     eax, ebx
0x180050e05  mov     rcx, [rsp+278h+var_18]
0x180050e0d  xor     rcx, rsp; StackCookie
0x180050e10  call    __security_check_cookie
0x180050e15  add     rsp, 270h
0x180050e1c  pop     rbx
0x180050e1d  retn
0x180077887  push    rbp
0x180077889  sub     rsp, 40h
0x18007788d  mov     rbp, rdx
0x180077890  call    ?SafeRpcRevertToSelf@@YAKXZ; SafeRpcRevertToSelf(void)
0x180077895  mov     rcx, [rbp+48h]; hObject
0x180077899  test    rcx, rcx
0x18007789c  jz      short loc_1800778A5
0x18007789e  call    cs:__imp_CloseHandle
0x1800778a4  nop
0x1800778a5  add     rsp, 40h
0x1800778a9  pop     rbp
0x1800778aa  retn
```
