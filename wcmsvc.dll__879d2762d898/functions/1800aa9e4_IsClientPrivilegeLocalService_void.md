# IsClientPrivilegeLocalService(void)

- ea: `0x1800aa9e4`
- end: `0x1800aaaab`
- name: `?IsClientPrivilegeLocalService@@YAHXZ`
- size: `199`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001fd50`
- `0x180062970`

## callees

- `0x1800119f0`
- `0x1800355b4`
- `0x18003a540`
- `0x180084f50`
- `0x1800aa9e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aaa34`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aaa52`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aaa70`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aaa34`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aaa52`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aaa70`

## pseudocode

```c
_BOOL8 IsClientPrivilegeLocalService(void)
{
  HANDLE v0; // rbx
  BOOL v1; // ebx
  HANDLE TokenHandle; // [rsp+20h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-18h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  v1 = 0;
  if ( !LocalQueryRpcClientToken(&TokenHandle) )
  {
    if ( (v0 = TokenHandle, IsMember = 0, CheckTokenMembership(TokenHandle, qword_18013F450, &IsMember)) && IsMember
      || CheckTokenMembership(v0, qword_18013F458, &IsMember) && IsMember
      || CheckTokenMembership(v0, qword_18013F460, &IsMember) && IsMember )
    {
      v1 = 1;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x1800aa9e4  mov     [rsp-8+arg_0], rbx
0x1800aa9e9  push    rbp
0x1800aa9ea  mov     rbp, rsp
0x1800aa9ed  sub     rsp, 40h
0x1800aa9f1  mov     rax, cs:__security_cookie
0x1800aa9f8  xor     rax, rsp
0x1800aa9fb  mov     [rbp+var_10], rax
0x1800aa9ff  xor     edx, edx
0x1800aaa01  mov     [rbp+TokenHandle], 0
0x1800aaa09  lea     rcx, [rbp+TokenHandle]
0x1800aaa0d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800aaa12  lea     rcx, [rbp+TokenHandle]; void **
0x1800aaa16  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x1800aaa1b  test    eax, eax
0x1800aaa1d  jnz     short loc_1800AAA87
0x1800aaa1f  mov     rbx, [rbp+TokenHandle]
0x1800aaa23  lea     r8, [rbp+IsMember]; IsMember
0x1800aaa27  mov     rdx, cs:qword_18013F450; SidToCheck
0x1800aaa2e  mov     rcx, rbx; TokenHandle
0x1800aaa31  mov     [rbp+IsMember], eax
0x1800aaa34  call    cs:__imp_CheckTokenMembership
0x1800aaa3a  test    eax, eax
0x1800aaa3c  jz      short loc_1800AAA44
0x1800aaa3e  cmp     [rbp+IsMember], 0
0x1800aaa42  jnz     short loc_1800AAA80
0x1800aaa44  mov     rdx, cs:qword_18013F458; SidToCheck
0x1800aaa4b  lea     r8, [rbp+IsMember]; IsMember
0x1800aaa4f  mov     rcx, rbx; TokenHandle
0x1800aaa52  call    cs:__imp_CheckTokenMembership
0x1800aaa58  test    eax, eax
0x1800aaa5a  jz      short loc_1800AAA62
0x1800aaa5c  cmp     [rbp+IsMember], 0
0x1800aaa60  jnz     short loc_1800AAA80
0x1800aaa62  mov     rdx, cs:qword_18013F460; SidToCheck
0x1800aaa69  lea     r8, [rbp+IsMember]; IsMember
0x1800aaa6d  mov     rcx, rbx; TokenHandle
0x1800aaa70  call    cs:__imp_CheckTokenMembership
0x1800aaa76  test    eax, eax
0x1800aaa78  jz      short loc_1800AAA87
0x1800aaa7a  cmp     [rbp+IsMember], 0
0x1800aaa7e  jz      short loc_1800AAA87
0x1800aaa80  mov     ebx, 1
0x1800aaa85  jmp     short loc_1800AAA89
0x1800aaa87  xor     ebx, ebx
0x1800aaa89  lea     rcx, [rbp+TokenHandle]
0x1800aaa8d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aaa92  mov     eax, ebx
0x1800aaa94  mov     rcx, [rbp+var_10]
0x1800aaa98  xor     rcx, rsp; StackCookie
0x1800aaa9b  call    __security_check_cookie
0x1800aaaa0  mov     rbx, [rsp+40h+arg_0]
0x1800aaaa5  add     rsp, 40h
0x1800aaaa9  pop     rbp
0x1800aaaaa  retn
```
