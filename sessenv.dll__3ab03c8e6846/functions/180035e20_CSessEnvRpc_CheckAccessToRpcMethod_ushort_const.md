# CSessEnvRpc::CheckAccessToRpcMethod(ushort const *)

- ea: `0x180035e20`
- end: `0x180035fd4`
- name: `?CheckAccessToRpcMethod@CSessEnvRpc@@SAJPEBG@Z`
- size: `436`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e40`
- `0x180018650`
- `0x180037310`
- `0x1800377c0`
- `0x180037a30`
- `0x180037b50`
- `0x180037d10`
- `0x18003a510`

## callees

- `0x180003f30`
- `0x180035e20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fc1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035edf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035edf`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x180035eac`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x180035eac`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x180035fb2`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x180035fb2`
- `AUTHZ!AuthzAccessCheck` at `0x180035f65`
- `AUTHZ!AuthzAccessCheck` at `0x180035f65`

## string_xrefs

- `0x180035e64`: `CSessEnvRpc::CheckAccessToRpcMethod`
- `0x180035e6b`: `szSdToAllowAccess`
- `0x180035f75`: `AuthzAccessCheck failed - %d`
- `0x180035f92`: `The caller does not have the necessary access rights!`

## pseudocode

```c
__int64 __fastcall CSessEnvRpc::CheckAccessToRpcMethod(LPCWSTR StringSecurityDescriptor)
{
  unsigned int v2; // ebx
  unsigned int AuthorizationContextForClient; // eax
  DWORD v4; // eax
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-9h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+58h] [rbp-1h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+78h] [rbp+1Fh] BYREF
  int v10; // [rsp+C0h] [rbp+67h] BYREF
  int v11; // [rsp+C8h] [rbp+6Fh] BYREF
  ULONG SecurityDescriptorSize; // [rsp+D0h] [rbp+77h] BYREF
  PVOID pAuthzClientContext; // [rsp+D8h] [rbp+7Fh] BYREF

  pAuthzClientContext = 0;
  v11 = 0;
  v10 = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  memset(&pReply, 0, sizeof(pReply));
  if ( !StringSecurityDescriptor )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "szSdToAllowAccess", "CSessEnvRpc::CheckAccessToRpcMethod");
    v2 = -2147024809;
    goto LABEL_15;
  }
  AuthorizationContextForClient = RpcGetAuthorizationContextForClient(0, 0, 0, 0, 0, 0, 0, &pAuthzClientContext);
  if ( AuthorizationContextForClient )
  {
    _DbgPrintMessage(8, "RpcGetAuthorizationContextForClient failed - %d", AuthorizationContextForClient);
  }
  else if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
              StringSecurityDescriptor,
              1u,
              &SecurityDescriptor,
              &SecurityDescriptorSize) )
  {
    pReply.GrantedAccessMask = (PACCESS_MASK)&v11;
    pReply.Error = (PDWORD)&v10;
    pRequest.DesiredAccess = 1;
    pRequest.OptionalArguments = 0;
    memset(&pRequest.PrincipalSelfSid, 0, 20);
    pReply.ResultListLength = 1;
    if ( AuthzAccessCheck(
           0,
           (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext,
           &pRequest,
           0,
           SecurityDescriptor,
           0,
           0,
           &pReply,
           0) )
    {
      if ( !v10 && v11 == pRequest.DesiredAccess )
      {
        v2 = 0;
        goto LABEL_15;
      }
      _DbgPrintMessage(8, "The caller does not have the necessary access rights!");
    }
    else
    {
      LastError = GetLastError();
      _DbgPrintMessage(8, "AuthzAccessCheck failed - %d", LastError);
    }
  }
  else
  {
    v4 = GetLastError();
    _DbgPrintMessage(8, "Conv Str SD to SD failed - %d; Arg='%S'", v4, StringSecurityDescriptor);
  }
  v2 = -2147024891;
LABEL_15:
  if ( pAuthzClientContext )
    RpcFreeAuthorizationContext(&pAuthzClientContext);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x180035e20  push    rbp
0x180035e22  push    rbx
0x180035e23  push    rdi
0x180035e24  lea     rbp, [rsp-47h]
0x180035e29  sub     rsp, 0A0h
0x180035e30  xor     edi, edi
0x180035e32  xorps   xmm0, xmm0
0x180035e35  xor     eax, eax
0x180035e37  mov     [rbp+57h+arg_18], rdi
0x180035e3b  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180035e3f  mov     rbx, rcx
0x180035e42  mov     [rbp+57h+arg_8], edi
0x180035e45  mov     [rbp+57h+arg_0], edi
0x180035e48  mov     [rbp+57h+SecurityDescriptor], rdi
0x180035e4c  mov     [rbp+57h+SecurityDescriptorSize], edi
0x180035e4f  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x180035e53  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180035e57  movups  xmmword ptr [rbp+57h+pReply.ResultListLength], xmm0
0x180035e5b  movups  xmmword ptr [rbp+57h+pReply.SaclEvaluationResults], xmm0
0x180035e5f  test    rcx, rcx
0x180035e62  jnz     short loc_180035E8B
0x180035e64  lea     r9, aCsessenvrpcChe; "CSessEnvRpc::CheckAccessToRpcMethod"
0x180035e6b  lea     r8, aSzsdtoallowacc; "szSdToAllowAccess"
0x180035e72  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180035e79  lea     ecx, [rbx+8]; int
0x180035e7c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180035e81  mov     ebx, 80070057h
0x180035e86  jmp     loc_180035FA8
0x180035e8b  lea     rcx, [rbp+57h+arg_18]
0x180035e8f  xor     r9d, r9d; pExpirationTime
0x180035e92  mov     [rsp+0B0h+pAuthzClientContext], rcx; pAuthzClientContext
0x180035e97  xor     r8d, r8d; Reserved1
0x180035e9a  mov     [rsp+0B0h+Reserved4], rdi; Reserved4
0x180035e9f  xor     edx, edx; ImpersonateOnReturn
0x180035ea1  mov     [rsp+0B0h+Reserved3], edi; Reserved3
0x180035ea5  xor     ecx, ecx; ClientBinding
0x180035ea7  mov     qword ptr [rsp+0B0h+Reserved2.LowPart], rdi; Reserved2
0x180035eac  call    cs:__imp_RpcGetAuthorizationContextForClient
0x180035eb2  test    eax, eax
0x180035eb4  jz      short loc_180035ECF
0x180035eb6  lea     rdx, aRpcgetauthoriz_0; "RpcGetAuthorizationContextForClient fai"...
0x180035ebd  mov     r8d, eax
0x180035ec0  mov     ecx, 8; int
0x180035ec5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180035eca  jmp     loc_180035FA3
0x180035ecf  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180035ed3  mov     edx, 1; StringSDRevision
0x180035ed8  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180035edc  mov     rcx, rbx; StringSecurityDescriptor
0x180035edf  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180035ee5  test    eax, eax
0x180035ee7  jnz     short loc_180035F0B
0x180035ee9  call    cs:__imp_GetLastError
0x180035eef  mov     r9, rbx
0x180035ef2  lea     rdx, aConvStrSdToSdF; "Conv Str SD to SD failed - %d; Arg='%S'"
0x180035ef9  mov     r8d, eax
0x180035efc  mov     ecx, 8; int
0x180035f01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180035f06  jmp     loc_180035FA3
0x180035f0b  mov     rdx, [rbp+57h+arg_18]; hAuthzClientContext
0x180035f0f  lea     rax, [rbp+57h+arg_8]
0x180035f13  mov     [rbp+57h+pReply.GrantedAccessMask], rax
0x180035f17  lea     r8, [rbp+57h+pRequest]; pRequest
0x180035f1b  mov     [rsp+0B0h+phAccessCheckResults], rdi; phAccessCheckResults
0x180035f20  lea     rax, [rbp+57h+arg_0]
0x180035f24  mov     [rbp+57h+pReply.Error], rax
0x180035f28  xor     r9d, r9d; hAuditEvent
0x180035f2b  lea     rax, [rbp+57h+pReply]
0x180035f2f  mov     [rbp+57h+pRequest.DesiredAccess], 1
0x180035f36  mov     [rsp+0B0h+pAuthzClientContext], rax; pReply
0x180035f3b  xor     ecx, ecx; Flags
0x180035f3d  mov     rax, [rbp+57h+SecurityDescriptor]
0x180035f41  mov     dword ptr [rsp+0B0h+Reserved4], edi; OptionalSecurityDescriptorCount
0x180035f45  mov     qword ptr [rsp+0B0h+Reserved3], rdi; OptionalSecurityDescriptorArray
0x180035f4a  mov     qword ptr [rsp+0B0h+Reserved2.LowPart], rax; pSecurityDescriptor
0x180035f4f  mov     [rbp+57h+pRequest.ObjectTypeList], rdi
0x180035f53  mov     [rbp+57h+pRequest.ObjectTypeListLength], edi
0x180035f56  mov     [rbp+57h+pRequest.OptionalArguments], rdi
0x180035f5a  mov     [rbp+57h+pRequest.PrincipalSelfSid], rdi
0x180035f5e  mov     [rbp+57h+pReply.ResultListLength], 1
0x180035f65  call    cs:__imp_AuthzAccessCheck
0x180035f6b  test    eax, eax
0x180035f6d  jnz     short loc_180035F81
0x180035f6f  call    cs:__imp_GetLastError
0x180035f75  lea     rdx, aAuthzaccessche_0; "AuthzAccessCheck failed - %d"
0x180035f7c  jmp     loc_180035EBD
0x180035f81  cmp     [rbp+57h+arg_0], edi
0x180035f84  jnz     short loc_180035F92
0x180035f86  mov     eax, [rbp+57h+pRequest.DesiredAccess]
0x180035f89  cmp     [rbp+57h+arg_8], eax
0x180035f8c  jnz     short loc_180035F92
0x180035f8e  mov     ebx, edi
0x180035f90  jmp     short loc_180035FA8
0x180035f92  lea     rdx, aTheCallerDoesN; "The caller does not have the necessary "...
0x180035f99  mov     ecx, 8; int
0x180035f9e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180035fa3  mov     ebx, 80070005h
0x180035fa8  cmp     [rbp+57h+arg_18], rdi
0x180035fac  jz      short loc_180035FB8
0x180035fae  lea     rcx, [rbp+57h+arg_18]; pAuthzClientContext
0x180035fb2  call    cs:__imp_RpcFreeAuthorizationContext
0x180035fb8  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180035fbc  test    rcx, rcx
0x180035fbf  jz      short loc_180035FC7
0x180035fc1  call    cs:__imp_LocalFree
0x180035fc7  mov     eax, ebx
0x180035fc9  add     rsp, 0A0h
0x180035fd0  pop     rdi
0x180035fd1  pop     rbx
0x180035fd2  pop     rbp
0x180035fd3  retn
```
