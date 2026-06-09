# pWdsImgAccessCheckBySDDL(void *,ushort *,int *)

- ea: `0x18000c590`
- end: `0x18000c694`
- name: `?pWdsImgAccessCheckBySDDL@@YAKPEAXPEAGPEAH@Z`
- size: `260`
- prototype: `unsigned int __fastcall(HANDLE ClientToken, LPCWSTR StringSecurityDescriptor, LPBOOL AccessStatus)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000891c`

## callees

- `0x18000c590`
- `0x180016020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c64f`
- `KERNEL32!GetLastError` at `0x18000c64f`
- `KERNEL32!LocalFree` at `0x18000c666`
- `KERNEL32!LocalFree` at `0x18000c666`
- `ADVAPI32!AccessCheck` at `0x18000c63f`
- `ADVAPI32!AccessCheck` at `0x18000c63f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c5fe`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c5fe`

## pseudocode

```c
__int64 __fastcall pWdsImgAccessCheckBySDDL(HANDLE ClientToken, LPCWSTR StringSecurityDescriptor, LPBOOL AccessStatus)
{
  DWORD LastError; // ebx
  DWORD GrantedAccess; // [rsp+40h] [rbp-40h] BYREF
  DWORD PrivilegeSetLength; // [rsp+44h] [rbp-3Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-38h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-30h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-20h] BYREF

  LastError = 0;
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
    || !AccessCheck(
          SecurityDescriptor,
          ClientToken,
          0x120089u,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          AccessStatus) )
  {
    LastError = GetLastError();
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18000c590  mov     [rsp-18h+arg_18], rbx
0x18000c595  push    rbp
0x18000c596  push    rsi
0x18000c597  push    rdi
0x18000c598  mov     rbp, rsp
0x18000c59b  sub     rsp, 80h
0x18000c5a2  mov     rax, cs:__security_cookie
0x18000c5a9  xor     rax, rsp
0x18000c5ac  mov     [rbp+var_8], rax
0x18000c5b0  xor     ebx, ebx
0x18000c5b2  mov     [rbp+var_3C], 14h
0x18000c5b9  and     [rbp+var_40], ebx
0x18000c5bc  mov     rdi, rcx
0x18000c5bf  and     [rbp+SecurityDescriptor], rbx
0x18000c5c3  xor     ecx, ecx
0x18000c5c5  mov     rax, rdx
0x18000c5c8  mov     [rbp+var_20.Privilege.Attributes], ecx
0x18000c5cb  mov     rsi, r8
0x18000c5ce  mov     [rbp+GenericMapping.GenericRead], 120089h
0x18000c5d5  xorps   xmm0, xmm0
0x18000c5d8  mov     [rbp+GenericMapping.GenericWrite], 120116h
0x18000c5df  lea     edx, [rbx+1]; StringSDRevision
0x18000c5e2  mov     [rbp+GenericMapping.GenericExecute], 1200A0h
0x18000c5e9  xor     r9d, r9d; SecurityDescriptorSize
0x18000c5ec  mov     [rbp+GenericMapping.GenericAll], 1F01FFh
0x18000c5f3  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000c5f7  mov     rcx, rax; StringSecurityDescriptor
0x18000c5fa  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm0
0x18000c5fe  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000c605  nop     dword ptr [rax+rax+00h]
0x18000c60a  test    eax, eax
0x18000c60c  jz      short loc_18000C64F
0x18000c60e  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18000c612  lea     rax, [rbp+var_40]
0x18000c616  mov     [rsp+80h+AccessStatus], rsi; AccessStatus
0x18000c61b  lea     r9, [rbp+GenericMapping]; GenericMapping
0x18000c61f  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x18000c624  mov     r8d, 120089h; DesiredAccess
0x18000c62a  lea     rax, [rbp+var_3C]
0x18000c62e  mov     rdx, rdi; ClientToken
0x18000c631  mov     [rsp+80h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000c636  lea     rax, [rbp+var_20]
0x18000c63a  mov     [rsp+80h+PrivilegeSet], rax; PrivilegeSet
0x18000c63f  call    cs:__imp_AccessCheck
0x18000c646  nop     dword ptr [rax+rax+00h]
0x18000c64b  test    eax, eax
0x18000c64d  jnz     short loc_18000C65D
0x18000c64f  call    cs:__imp_GetLastError
0x18000c656  nop     dword ptr [rax+rax+00h]
0x18000c65b  mov     ebx, eax
0x18000c65d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000c661  test    rcx, rcx
0x18000c664  jz      short loc_18000C672
0x18000c666  call    cs:__imp_LocalFree
0x18000c66d  nop     dword ptr [rax+rax+00h]
0x18000c672  mov     eax, ebx
0x18000c674  mov     rcx, [rbp+var_8]
0x18000c678  xor     rcx, rsp; StackCookie
0x18000c67b  call    __security_check_cookie
0x18000c680  mov     rbx, [rsp+80h+arg_18]
0x18000c688  add     rsp, 80h
0x18000c68f  pop     rdi
0x18000c690  pop     rsi
0x18000c691  pop     rbp
0x18000c692  retn
```
