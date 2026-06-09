# WinApiLite::SetNamedSecurityInfoW(ushort *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)

- ea: `0x180044590`
- end: `0x1800445da`
- name: `?SetNamedSecurityInfoW@WinApiLite@@UEAAKPEAGW4_SE_OBJECT_TYPE@@KPEAX2PEAU_ACL@@3@Z`
- size: `74`
- prototype: `unsigned int(WinApiLite *__hidden this, unsigned __int16 *, enum _SE_OBJECT_TYPE, unsigned int, void *, void *, struct _ACL *, struct _ACL *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800445ce`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800445ce`

## pseudocode

```c
DWORD __fastcall WinApiLite::SetNamedSecurityInfoW(
        WinApiLite *this,
        unsigned __int16 *a2,
        SE_OBJECT_TYPE a3,
        SECURITY_INFORMATION a4,
        PSID psidOwner,
        PSID psidGroup,
        struct _ACL *pDacl,
        struct _ACL *pSacl)
{
  return SetNamedSecurityInfoW(a2, a3, a4, psidOwner, psidGroup, pDacl, pSacl);
}

```

## disassembly

```asm
0x180044590  push    rbx
0x180044592  sub     rsp, 40h
0x180044596  mov     rax, [rsp+48h+arg_38]
0x18004459e  mov     r10d, r9d
0x1800445a1  mov     r9, [rsp+48h+psidOwner]; psidOwner
0x1800445a6  mov     r11d, r8d
0x1800445a9  mov     [rsp+48h+pSacl], rax; pSacl
0x1800445ae  mov     rcx, rdx; pObjectName
0x1800445b1  mov     rax, [rsp+48h+arg_30]
0x1800445b9  mov     r8d, r10d; SecurityInfo
0x1800445bc  mov     [rsp+48h+pDacl], rax; pDacl
0x1800445c1  mov     edx, r11d; ObjectType
0x1800445c4  mov     rax, [rsp+48h+arg_28]
0x1800445c9  mov     [rsp+48h+psidGroup], rax; psidGroup
0x1800445ce  call    cs:__imp_SetNamedSecurityInfoW
0x1800445d4  add     rsp, 40h
0x1800445d8  pop     rbx
0x1800445d9  retn
```
