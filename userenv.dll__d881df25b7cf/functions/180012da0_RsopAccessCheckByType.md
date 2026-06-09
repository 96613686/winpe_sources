# RsopAccessCheckByType

- ea: `0x180012da0`
- end: `0x180012e40`
- name: `RsopAccessCheckByType`
- size: `160`
- prototype: `HRESULT __stdcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PSID pPrincipalSelfSid, PRSOPTOKEN pRsopToken, DWORD dwDesiredAccessMask, POBJECT_TYPE_LIST pObjectTypeList, DWORD ObjectTypeListLength, PGENERIC_MAPPING pGenericMapping, PPRIVILEGE_SET pPrivilegeSet, LPDWORD pdwPrivilegeSetLength, LPDWORD pdwGrantedAccessMask, LPBOOL pbAccessStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000f670`
- `0x180012da0`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!RsopAccessCheckByTypeWorker` at `0x180012e23`
- `ext-ms-win-profile-userenv-l1-1-0!RsopAccessCheckByTypeWorker` at `0x180012e23`

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
0x180012da0  push    rbx
0x180012da2  push    rbp
0x180012da3  push    rsi
0x180012da4  push    rdi
0x180012da5  sub     rsp, 68h
0x180012da9  mov     ebx, r9d
0x180012dac  mov     rdi, r8
0x180012daf  mov     rsi, rdx
0x180012db2  mov     rbp, rcx
0x180012db5  call    IsDeleteLinkFileWorkerPresent
0x180012dba  test    al, al
0x180012dbc  jz      short loc_180012E31
0x180012dbe  mov     rax, [rsp+88h+pbAccessStatus]
0x180012dc6  mov     r9d, ebx
0x180012dc9  mov     [rsp+88h+var_38], rax
0x180012dce  mov     r8, rdi
0x180012dd1  mov     rax, [rsp+88h+pdwGrantedAccessMask]
0x180012dd9  mov     rdx, rsi
0x180012ddc  mov     [rsp+88h+var_40], rax
0x180012de1  mov     rcx, rbp
0x180012de4  mov     rax, [rsp+88h+pdwPrivilegeSetLength]
0x180012dec  mov     [rsp+88h+var_48], rax
0x180012df1  mov     rax, [rsp+88h+pPrivilegeSet]
0x180012df9  mov     [rsp+88h+var_50], rax
0x180012dfe  mov     rax, [rsp+88h+pGenericMapping]
0x180012e06  mov     [rsp+88h+var_58], rax
0x180012e0b  mov     eax, [rsp+88h+ObjectTypeListLength]
0x180012e12  mov     [rsp+88h+var_60], eax
0x180012e16  mov     rax, [rsp+88h+pObjectTypeList]
0x180012e1e  mov     [rsp+88h+var_68], rax
0x180012e23  call    cs:__imp_RsopAccessCheckByTypeWorker
0x180012e2a  nop     dword ptr [rax+rax+00h]
0x180012e2f  jmp     short loc_180012E36
0x180012e31  mov     eax, 80004001h
0x180012e36  add     rsp, 68h
0x180012e3a  pop     rdi
0x180012e3b  pop     rsi
0x180012e3c  pop     rbp
0x180012e3d  pop     rbx
0x180012e3e  retn
```
