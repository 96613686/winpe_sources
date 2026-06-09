# CSecuredObject::SetDACL(CAccessControlList &)

- ea: `0x180004848`
- end: `0x18000489a`
- name: `?SetDACL@CSecuredObject@@AEBAJAEAVCAccessControlList@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(CSecuredObject *__hidden this, struct CAccessControlList *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000eee8`

## callees

- `0x1800048a0`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000487d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000487d`

## pseudocode

```c
__int64 __fastcall CSecuredObject::SetDACL(CSecuredObject *this, struct CAccessControlList *a2)
{
  struct _ACL *pDacl; // rax
  DWORD v4; // edx
  __int64 result; // rax

  pDacl = (struct _ACL *)CAccessControlList::operator _ACL *(a2);
  v4 = SetSecurityInfo(*(HANDLE *)this, *((SE_OBJECT_TYPE *)this + 2), 4u, 0, 0, pDacl, 0);
  result = 0;
  if ( v4 )
    return v4 | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004848  push    rbx
0x18000484a  sub     rsp, 40h
0x18000484e  mov     rbx, rcx
0x180004851  mov     rcx, rdx
0x180004854  call    ??BCAccessControlList@@QEAAPEAU_ACL@@XZ; CAccessControlList::operator _ACL *(void)
0x180004859  mov     edx, [rbx+8]; ObjectType
0x18000485c  xor     r9d, r9d; psidOwner
0x18000485f  mov     rcx, [rbx]; handle
0x180004862  mov     [rsp+48h+pSacl], 0; pSacl
0x18000486b  mov     [rsp+48h+pDacl], rax; pDacl
0x180004870  lea     r8d, [r9+4]; SecurityInfo
0x180004874  mov     [rsp+48h+psidGroup], 0; psidGroup
0x18000487d  call    cs:__imp_SetSecurityInfo
0x180004883  mov     ecx, eax
0x180004885  mov     edx, eax
0x180004887  or      ecx, 80070000h
0x18000488d  xor     eax, eax
0x18000488f  test    edx, edx
0x180004891  cmovnz  eax, ecx
0x180004894  add     rsp, 40h
0x180004898  pop     rbx
0x180004899  retn
```
