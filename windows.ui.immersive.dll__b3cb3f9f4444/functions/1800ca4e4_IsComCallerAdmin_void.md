# IsComCallerAdmin(void)

- ea: `0x1800ca4e4`
- end: `0x1800ca611`
- name: `?IsComCallerAdmin@@YAHXZ`
- size: `301`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d0d10`

## callees

- `0x180024878`
- `0x18002bd44`
- `0x18002d7f0`
- `0x1800605a0`
- `0x1800ca4e4`
- `0x1800ca618`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca53e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ca53e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ca522`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca56d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca5a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca56d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ca5a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 IsComCallerAdmin(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax
  void *v2; // rdx
  HANDLE v4; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v5[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+28h] BYREF
  void *v10; // [rsp+88h] [rbp+30h] BYREF

  v0 = 0;
  TokenHandle = 0;
  v10 = 0;
  v4 = 0;
  v5[0] = 0;
  v6 = 0;
  if ( (int)CImpersonateCaller::Impersonate((CImpersonateCaller *)v5) >= 0 )
  {
    ReturnLength = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      TokenInformation = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength)
        && TokenInformation != 2
        && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &v10,
              0),
            GetTokenInformation(TokenHandle, TokenLinkedToken, &v10, 8u, &ReturnLength)) )
      {
        v2 = v10;
        v10 = 0;
      }
      else
      {
        v2 = TokenHandle;
        TokenHandle = 0;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v4,
        v2);
      v0 = IsInAdministratorGroup(v4);
    }
  }
  CImpersonateCaller::~CImpersonateCaller((CImpersonateCaller *)v5);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v4);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800ca4e4  push    rbp
0x1800ca4e6  push    rbx
0x1800ca4e7  mov     rbp, rsp
0x1800ca4ea  sub     rsp, 58h
0x1800ca4ee  xor     ebx, ebx
0x1800ca4f0  mov     [rbp+TokenHandle], rbx
0x1800ca4f4  mov     [rbp+arg_18], rbx
0x1800ca4f8  mov     [rbp+var_28], rbx
0x1800ca4fc  mov     [rbp+var_20], bl
0x1800ca4ff  mov     [rbp+var_18], rbx
0x1800ca503  lea     rcx, [rbp+var_20]; this
0x1800ca507  call    ?Impersonate@CImpersonateCaller@@QEAAJXZ; CImpersonateCaller::Impersonate(void)
0x1800ca50c  test    eax, eax
0x1800ca50e  js      loc_1800CA5E0
0x1800ca514  mov     [rbp+arg_8], ebx
0x1800ca517  xor     edx, edx
0x1800ca519  lea     rcx, [rbp+TokenHandle]
0x1800ca51d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ca522  call    cs:__imp_GetCurrentThread
0x1800ca529  nop     dword ptr [rax+rax+00h]
0x1800ca52e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ca532  mov     edx, 0F01FFh; DesiredAccess
0x1800ca537  lea     r8d, [rbx+1]; OpenAsSelf
0x1800ca53b  mov     rcx, rax; ThreadHandle
0x1800ca53e  call    cs:__imp_OpenThreadToken
0x1800ca545  nop     dword ptr [rax+rax+00h]
0x1800ca54a  test    eax, eax
0x1800ca54c  jz      loc_1800CA5E0
0x1800ca552  mov     [rbp+TokenInformation], ebx
0x1800ca555  lea     rax, [rbp+arg_8]
0x1800ca559  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800ca55e  lea     r9d, [rbx+4]; TokenInformationLength
0x1800ca562  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800ca566  lea     edx, [rbx+12h]; TokenInformationClass
0x1800ca569  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ca56d  call    cs:__imp_GetTokenInformation
0x1800ca574  nop     dword ptr [rax+rax+00h]
0x1800ca579  test    eax, eax
0x1800ca57b  jz      short loc_1800CA5C0
0x1800ca57d  cmp     [rbp+TokenInformation], 2
0x1800ca581  jz      short loc_1800CA5C0
0x1800ca583  xor     edx, edx
0x1800ca585  lea     rcx, [rbp+arg_18]
0x1800ca589  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ca58e  lea     rax, [rbp+arg_8]
0x1800ca592  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800ca597  lea     r9d, [rbx+8]; TokenInformationLength
0x1800ca59b  lea     r8, [rbp+arg_18]; TokenInformation
0x1800ca59f  lea     edx, [rbx+13h]; TokenInformationClass
0x1800ca5a2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ca5a6  call    cs:__imp_GetTokenInformation
0x1800ca5ad  nop     dword ptr [rax+rax+00h]
0x1800ca5b2  test    eax, eax
0x1800ca5b4  jz      short loc_1800CA5C0
0x1800ca5b6  mov     rdx, [rbp+arg_18]
0x1800ca5ba  mov     [rbp+arg_18], rbx
0x1800ca5be  jmp     short loc_1800CA5CC
0x1800ca5c0  mov     rdx, [rbp+TokenHandle]
0x1800ca5c4  mov     [rbp+TokenHandle], 0
0x1800ca5cc  lea     rcx, [rbp+var_28]
0x1800ca5d0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ca5d5  mov     rcx, [rbp+var_28]; TokenHandle
0x1800ca5d9  call    ?IsInAdministratorGroup@@YAHPEAX@Z; IsInAdministratorGroup(void *)
0x1800ca5de  mov     ebx, eax
0x1800ca5e0  lea     rcx, [rbp+var_20]; this
0x1800ca5e4  call    ??1CImpersonateCaller@@QEAA@XZ; CImpersonateCaller::~CImpersonateCaller(void)
0x1800ca5e9  nop
0x1800ca5ea  lea     rcx, [rbp+var_28]
0x1800ca5ee  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ca5f3  nop
0x1800ca5f4  lea     rcx, [rbp+arg_18]
0x1800ca5f8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ca5fd  nop
0x1800ca5fe  lea     rcx, [rbp+TokenHandle]
0x1800ca602  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ca607  mov     eax, ebx
0x1800ca609  add     rsp, 58h
0x1800ca60d  pop     rbx
0x1800ca60e  pop     rbp
0x1800ca60f  retn
```
