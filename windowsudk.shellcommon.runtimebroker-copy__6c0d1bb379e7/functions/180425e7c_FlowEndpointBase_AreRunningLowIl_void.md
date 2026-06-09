# FlowEndpointBase::AreRunningLowIl(void)

- ea: `0x180425e7c`
- end: `0x180425f6f`
- name: `?AreRunningLowIl@FlowEndpointBase@@IEAA_NXZ`
- size: `243`
- prototype: `bool __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180426e20`

## callees

- `0x18009a4d4`
- `0x1800a14f8`
- `0x18015cfdc`
- `0x180425e7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180425ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180425ec1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180425f06`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180425f06`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180425f13`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180425f13`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180425f2b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180425f2b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180425eb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180425ef9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180425eb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180425ef9`

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
    std::unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>::~unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>(&v8);
LABEL_10:
    v3 = 0;
    goto LABEL_11;
  }
  std::unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>::~unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>(&v8);
LABEL_11:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return v3;
}

```

## disassembly

```asm
0x180425e7c  mov     rax, rsp
0x180425e7f  mov     [rax+20h], rbx
0x180425e83  mov     [rax+8], rcx
0x180425e87  push    rdi
0x180425e88  sub     rsp, 30h
0x180425e8c  mov     rdi, 0FFFFFFFFFFFFFFFCh
0x180425e93  mov     [rax+18h], rdi
0x180425e97  mov     dword ptr [rax+8], 0
0x180425e9e  lea     rax, [rax+8]
0x180425ea2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180425ea7  xor     r9d, r9d; TokenInformationLength
0x180425eaa  xor     r8d, r8d; TokenInformation
0x180425ead  lea     edx, [rdi+1Dh]; TokenInformationClass
0x180425eb0  mov     rcx, rdi; TokenHandle
0x180425eb3  call    cs:__imp_GetTokenInformation
0x180425eb9  test    eax, eax
0x180425ebb  jnz     loc_180425F54
0x180425ec1  call    cs:__imp_GetLastError
0x180425ec7  cmp     eax, 7Ah ; 'z'
0x180425eca  jnz     loc_180425F54
0x180425ed0  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x180425ed4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180425ed9  mov     rbx, rax
0x180425edc  mov     [rsp+38h+arg_8], rax
0x180425ee1  lea     rax, [rsp+38h+TokenInformationLength]
0x180425ee6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180425eeb  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180425ef0  mov     r8, rbx; TokenInformation
0x180425ef3  lea     edx, [rdi+1Dh]; TokenInformationClass
0x180425ef6  mov     rcx, rdi; TokenHandle
0x180425ef9  call    cs:__imp_GetTokenInformation
0x180425eff  test    eax, eax
0x180425f01  jz      short loc_180425F4A
0x180425f03  mov     rcx, [rbx]; pSid
0x180425f06  call    cs:__imp_IsValidSid
0x180425f0c  test    eax, eax
0x180425f0e  jz      short loc_180425F4A
0x180425f10  mov     rcx, [rbx]; pSid
0x180425f13  call    cs:__imp_GetSidSubAuthorityCount
0x180425f19  test    rax, rax
0x180425f1c  jz      short loc_180425F4A
0x180425f1e  movzx   edx, byte ptr [rax]
0x180425f21  mov     edi, 1
0x180425f26  sub     edx, edi; nSubAuthority
0x180425f28  mov     rcx, [rbx]; pSid
0x180425f2b  call    cs:__imp_GetSidSubAuthority
0x180425f31  test    rax, rax
0x180425f34  jz      short loc_180425F4A
0x180425f36  cmp     dword ptr [rax], 1000h
0x180425f3c  jnz     short loc_180425F4A
0x180425f3e  lea     rcx, [rsp+38h+arg_8]
0x180425f43  call    ??1?$unique_ptr@V?$tuple@V_lambda_8ec977b72ed93670989efc953948d14a_@@@std@@U?$default_delete@V?$tuple@V_lambda_8ec977b72ed93670989efc953948d14a_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>::~unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>(void)
0x180425f48  jmp     short loc_180425F57
0x180425f4a  lea     rcx, [rsp+38h+arg_8]
0x180425f4f  call    ??1?$unique_ptr@V?$tuple@V_lambda_8ec977b72ed93670989efc953948d14a_@@@std@@U?$default_delete@V?$tuple@V_lambda_8ec977b72ed93670989efc953948d14a_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>::~unique_ptr<std::tuple<_lambda_8ec977b72ed93670989efc953948d14a_>>(void)
0x180425f54  xor     dil, dil
0x180425f57  lea     rcx, [rsp+38h+arg_10]
0x180425f5c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180425f61  mov     al, dil
0x180425f64  mov     rbx, [rsp+38h+arg_18]
0x180425f69  add     rsp, 30h
0x180425f6d  pop     rdi
0x180425f6e  retn
```
