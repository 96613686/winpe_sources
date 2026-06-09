# FlowEndpointBase::AreRunningLowIl(void)

- ea: `0x140054bac`
- end: `0x140054c9f`
- name: `?AreRunningLowIl@FlowEndpointBase@@IEAA_NXZ`
- size: `243`
- prototype: `bool __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140055274`

## callees

- `0x14000f804`
- `0x140052f60`
- `0x140052fbc`
- `0x140054bac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054bf1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140054c43`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140054c43`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140054c36`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140054c36`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140054c5b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140054c5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140054be3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140054c29`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140054be3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140054c29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall FlowEndpointBase::AreRunningLowIl(FlowEndpointBase *this)
{
  PSID *v1; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  char v3; // di
  PDWORD SidSubAuthority; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  PSID *v8; // [rsp+48h] [rbp+10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(this);
  v9 = -4;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
    || GetLastError() != 122 )
  {
    goto LABEL_10;
  }
  v1 = (PSID *)operator new(TokenInformationLength);
  v8 = v1;
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFCLL,
          TokenIntegrityLevel,
          v1,
          TokenInformationLength,
          &TokenInformationLength)
    || !IsValidSid(*v1)
    || (SidSubAuthorityCount = GetSidSubAuthorityCount(*v1)) == 0
    || (v3 = 1, (SidSubAuthority = GetSidSubAuthority(*v1, (unsigned int)*SidSubAuthorityCount - 1)) == 0)
    || *SidSubAuthority != 4096 )
  {
    std::unique_ptr<_TOKEN_MANDATORY_LABEL>::~unique_ptr<_TOKEN_MANDATORY_LABEL>(&v8);
LABEL_10:
    v3 = 0;
    goto LABEL_11;
  }
  std::unique_ptr<_TOKEN_MANDATORY_LABEL>::~unique_ptr<_TOKEN_MANDATORY_LABEL>(&v8);
LABEL_11:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return v3;
}

```

## disassembly

```asm
0x140054bac  mov     rax, rsp
0x140054baf  mov     [rax+20h], rbx
0x140054bb3  mov     [rax+8], rcx
0x140054bb7  push    rdi
0x140054bb8  sub     rsp, 30h
0x140054bbc  mov     rdi, 0FFFFFFFFFFFFFFFCh
0x140054bc3  mov     [rax+18h], rdi
0x140054bc7  mov     dword ptr [rax+8], 0
0x140054bce  lea     rax, [rax+8]
0x140054bd2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140054bd7  xor     r9d, r9d; TokenInformationLength
0x140054bda  xor     r8d, r8d; TokenInformation
0x140054bdd  lea     edx, [rdi+1Dh]; TokenInformationClass
0x140054be0  mov     rcx, rdi; TokenHandle
0x140054be3  call    cs:__imp_GetTokenInformation
0x140054be9  test    eax, eax
0x140054beb  jnz     loc_140054C84
0x140054bf1  call    cs:__imp_GetLastError
0x140054bf7  cmp     eax, 7Ah ; 'z'
0x140054bfa  jnz     loc_140054C84
0x140054c00  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x140054c04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140054c09  mov     rbx, rax
0x140054c0c  mov     [rsp+38h+arg_8], rax
0x140054c11  lea     rax, [rsp+38h+TokenInformationLength]
0x140054c16  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140054c1b  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140054c20  mov     r8, rbx; TokenInformation
0x140054c23  lea     edx, [rdi+1Dh]; TokenInformationClass
0x140054c26  mov     rcx, rdi; TokenHandle
0x140054c29  call    cs:__imp_GetTokenInformation
0x140054c2f  test    eax, eax
0x140054c31  jz      short loc_140054C7A
0x140054c33  mov     rcx, [rbx]; pSid
0x140054c36  call    cs:__imp_IsValidSid
0x140054c3c  test    eax, eax
0x140054c3e  jz      short loc_140054C7A
0x140054c40  mov     rcx, [rbx]; pSid
0x140054c43  call    cs:__imp_GetSidSubAuthorityCount
0x140054c49  test    rax, rax
0x140054c4c  jz      short loc_140054C7A
0x140054c4e  movzx   edx, byte ptr [rax]
0x140054c51  mov     edi, 1
0x140054c56  sub     edx, edi; nSubAuthority
0x140054c58  mov     rcx, [rbx]; pSid
0x140054c5b  call    cs:__imp_GetSidSubAuthority
0x140054c61  test    rax, rax
0x140054c64  jz      short loc_140054C7A
0x140054c66  cmp     dword ptr [rax], 1000h
0x140054c6c  jnz     short loc_140054C7A
0x140054c6e  lea     rcx, [rsp+38h+arg_8]
0x140054c73  call    ??1?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@U?$default_delete@U_TOKEN_MANDATORY_LABEL@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_MANDATORY_LABEL>::~unique_ptr<_TOKEN_MANDATORY_LABEL>(void)
0x140054c78  jmp     short loc_140054C87
0x140054c7a  lea     rcx, [rsp+38h+arg_8]
0x140054c7f  call    ??1?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@U?$default_delete@U_TOKEN_MANDATORY_LABEL@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_MANDATORY_LABEL>::~unique_ptr<_TOKEN_MANDATORY_LABEL>(void)
0x140054c84  xor     dil, dil
0x140054c87  lea     rcx, [rsp+38h+arg_10]
0x140054c8c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140054c91  mov     al, dil
0x140054c94  mov     rbx, [rsp+38h+arg_18]
0x140054c99  add     rsp, 30h
0x140054c9d  pop     rdi
0x140054c9e  retn
```
