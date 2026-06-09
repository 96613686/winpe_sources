# VerifyClaim

- ea: `0x180027e94`
- end: `0x180027fa3`
- name: `VerifyClaim`
- size: `271`
- prototype: `int __fastcall(HANDLE ClientToken)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029040`

## callees

- `0x180021ec0`
- `0x180027e94`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f14`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180027f51`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180027f51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027f0a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180027f0a`

## pseudocode

```c
int __fastcall VerifyClaim(HANDLE ClientToken)
{
  DWORD GrantedAccess; // [rsp+40h] [rbp+7h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp+Bh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp+Fh] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp+17h] BYREF
  DWORD PrivilegeSetLength; // [rsp+54h] [rbp+1Bh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp+1Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+2Fh] BYREF

  AccessStatus = 0;
  GenericMapping.GenericRead = 131073;
  GenericMapping.GenericWrite = 131073;
  GenericMapping.GenericExecute = 131073;
  GrantedAccess = 0;
  GenericMapping.GenericAll = 2031617;
  SecurityDescriptor = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;OICI;0x1;;;AC)(XA;;0x1;;;WD;(exists WIN://PKG))",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
    return GetLastError();
  if ( !AccessCheck(
          SecurityDescriptor,
          ClientToken,
          1u,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    LocalFree(SecurityDescriptor);
    return GetLastError();
  }
  LocalFree(SecurityDescriptor);
  if ( GrantedAccess == 1 )
    return AccessStatus == 0 ? 5 : 0;
  else
    return 5;
}

```

## disassembly

```asm
0x180027e94  mov     [rsp-8+arg_8], rbx
0x180027e99  push    rbp
0x180027e9a  lea     rbp, [rsp-57h]
0x180027e9f  sub     rsp, 90h
0x180027ea6  mov     rax, cs:__security_cookie
0x180027ead  xor     rax, rsp
0x180027eb0  mov     [rbp+57h+var_10], rax
0x180027eb4  mov     eax, 20001h
0x180027eb9  mov     [rbp+57h+var_4C], 0
0x180027ec0  mov     [rbp+57h+GenericMapping.GenericRead], eax
0x180027ec3  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180027ec7  mov     [rbp+57h+GenericMapping.GenericWrite], eax
0x180027eca  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180027ece  mov     [rbp+57h+GenericMapping.GenericExecute], eax
0x180027ed1  mov     rbx, rcx
0x180027ed4  xor     eax, eax
0x180027ed6  mov     [rbp+57h+var_50], 0
0x180027edd  xorps   xmm0, xmm0
0x180027ee0  mov     [rbp+57h+GenericMapping.GenericAll], 1F0001h
0x180027ee7  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;OICI;0x1;;;AC)(XA;;0x1;;;W"...
0x180027eee  mov     [rbp+57h+SecurityDescriptor], 0
0x180027ef6  movups  xmmword ptr [rbp+57h+var_28.PrivilegeCount], xmm0
0x180027efa  lea     edx, [rax+1]; StringSDRevision
0x180027efd  mov     [rbp+57h+var_28.Privilege.Attributes], eax
0x180027f00  mov     [rbp+57h+var_3C], 14h
0x180027f07  mov     [rbp+57h+SecurityDescriptorSize], eax
0x180027f0a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180027f10  test    eax, eax
0x180027f12  jnz     short loc_180027F1C
0x180027f14  call    cs:__imp_GetLastError
0x180027f1a  jmp     short loc_180027F86
0x180027f1c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180027f20  lea     rax, [rbp+57h+var_4C]
0x180027f24  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x180027f29  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180027f2d  lea     rax, [rbp+57h+var_50]
0x180027f31  mov     r8d, 1; DesiredAccess
0x180027f37  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x180027f3c  mov     rdx, rbx; ClientToken
0x180027f3f  lea     rax, [rbp+57h+var_3C]
0x180027f43  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180027f48  lea     rax, [rbp+57h+var_28]
0x180027f4c  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x180027f51  call    cs:__imp_AccessCheck
0x180027f57  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180027f5b  test    eax, eax
0x180027f5d  jnz     short loc_180027F67
0x180027f5f  call    cs:__imp_LocalFree
0x180027f65  jmp     short loc_180027F14
0x180027f67  call    cs:__imp_LocalFree
0x180027f6d  cmp     [rbp+57h+var_50], 1
0x180027f71  jnz     short loc_180027F81
0x180027f73  mov     eax, [rbp+57h+var_4C]
0x180027f76  neg     eax
0x180027f78  sbb     eax, eax
0x180027f7a  not     eax
0x180027f7c  and     eax, 5
0x180027f7f  jmp     short loc_180027F86
0x180027f81  mov     eax, 5
0x180027f86  mov     rcx, [rbp+57h+var_10]
0x180027f8a  xor     rcx, rsp; StackCookie
0x180027f8d  call    __security_check_cookie
0x180027f92  mov     rbx, [rsp+90h+arg_8]
0x180027f9a  add     rsp, 90h
0x180027fa1  pop     rbp
0x180027fa2  retn
```
