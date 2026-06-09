# RsopAccessCheckByType

- ea: `0x180011df0`
- end: `0x180011e89`
- name: `RsopAccessCheckByType`
- size: `153`
- prototype: `HRESULT __stdcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PSID pPrincipalSelfSid, PRSOPTOKEN pRsopToken, DWORD dwDesiredAccessMask, POBJECT_TYPE_LIST pObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING pGenericMapping, PPRIVILEGE_SET pPrivilegeSet, LPDWORD pdwPrivilegeSetLength, LPDWORD pdwGrantedAccessMask, LPBOOL pbAccessStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e9c0`
- `0x180011df0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!RsopAccessCheckByTypeWorker` at `0x180011e73`
- `ext-ms-win-profile-userenv-l1-1-0!RsopAccessCheckByTypeWorker` at `0x180011e73`

## pseudocode

```c
HRESULT __stdcall RsopAccessCheckByType(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PSID pPrincipalSelfSid,
        PRSOPTOKEN pRsopToken,
        DWORD dwDesiredAccessMask,
        POBJECT_TYPE_LIST pObjectTypeList,
        DWORD ObjectTypeListLength,
        PGENERIC_MAPPING pGenericMapping,
        PPRIVILEGE_SET pPrivilegeSet,
        LPDWORD pdwPrivilegeSetLength,
        LPDWORD pdwGrantedAccessMask,
        LPBOOL pbAccessStatus)
{
  if ( (unsigned __int8)IsDeleteLinkFileWorkerPresent() )
    return RsopAccessCheckByTypeWorker(
             pSecurityDescriptor,
             pPrincipalSelfSid,
             pRsopToken,
             dwDesiredAccessMask,
             pObjectTypeList,
             ObjectTypeListLength,
             pGenericMapping,
             pPrivilegeSet,
             pdwPrivilegeSetLength,
             pdwGrantedAccessMask,
             pbAccessStatus);
  else
    return -2147467263;
}

```

## disassembly

```asm
0x180011df0  push    rbx
0x180011df2  push    rbp
0x180011df3  push    rsi
0x180011df4  push    rdi
0x180011df5  sub     rsp, 68h
0x180011df9  mov     ebx, r9d
0x180011dfc  mov     rdi, r8
0x180011dff  mov     rsi, rdx
0x180011e02  mov     rbp, rcx
0x180011e05  call    IsDeleteLinkFileWorkerPresent
0x180011e0a  test    al, al
0x180011e0c  jz      short loc_180011E7B
0x180011e0e  mov     rax, [rsp+88h+pbAccessStatus]
0x180011e16  mov     r9d, ebx
0x180011e19  mov     [rsp+88h+var_38], rax
0x180011e1e  mov     r8, rdi
0x180011e21  mov     rax, [rsp+88h+pdwGrantedAccessMask]
0x180011e29  mov     rdx, rsi
0x180011e2c  mov     [rsp+88h+var_40], rax
0x180011e31  mov     rcx, rbp
0x180011e34  mov     rax, [rsp+88h+pdwPrivilegeSetLength]
0x180011e3c  mov     [rsp+88h+var_48], rax
0x180011e41  mov     rax, [rsp+88h+pPrivilegeSet]
0x180011e49  mov     [rsp+88h+var_50], rax
0x180011e4e  mov     rax, [rsp+88h+pGenericMapping]
0x180011e56  mov     [rsp+88h+var_58], rax
0x180011e5b  mov     eax, [rsp+88h+ObjectTypeListLength]
0x180011e62  mov     [rsp+88h+var_60], eax
0x180011e66  mov     rax, [rsp+88h+pObjectTypeList]
0x180011e6e  mov     [rsp+88h+var_68], rax
0x180011e73  call    cs:__imp_RsopAccessCheckByTypeWorker
0x180011e79  jmp     short loc_180011E80
0x180011e7b  mov     eax, 80004001h
0x180011e80  add     rsp, 68h
0x180011e84  pop     rdi
0x180011e85  pop     rsi
0x180011e86  pop     rbp
0x180011e87  pop     rbx
0x180011e88  retn
```
