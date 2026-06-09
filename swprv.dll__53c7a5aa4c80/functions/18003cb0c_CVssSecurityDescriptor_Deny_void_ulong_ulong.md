# CVssSecurityDescriptor::Deny(void *,ulong,ulong)

- ea: `0x18003cb0c`
- end: `0x18003cb53`
- name: `?Deny@CVssSecurityDescriptor@@QEAAJPEAXKK@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct _ACL **this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bc08`

## callees

- `0x18003bae4`
- `0x18003cb0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003cb3b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003cb3b`

## pseudocode

```c
__int64 __fastcall CVssSecurityDescriptor::Deny(struct _ACL **this, void *a2)
{
  int v3; // ebx

  v3 = CVssSecurityDescriptor::AddAccessDeniedACEToACL(this + 3, a2);
  if ( v3 >= 0 )
    SetSecurityDescriptorDacl(*this, 1, this[3], 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003cb0c  mov     [rsp+arg_0], rbx
0x18003cb11  mov     [rsp+arg_8], rsi
0x18003cb16  push    rdi
0x18003cb17  sub     rsp, 20h
0x18003cb1b  mov     rdi, rcx
0x18003cb1e  add     rcx, 18h; struct _ACL **
0x18003cb22  call    ?AddAccessDeniedACEToACL@CVssSecurityDescriptor@@CAJPEAPEAU_ACL@@PEAXKK@Z; CVssSecurityDescriptor::AddAccessDeniedACEToACL(_ACL * *,void *,ulong,ulong)
0x18003cb27  mov     ebx, eax
0x18003cb29  test    eax, eax
0x18003cb2b  js      short loc_18003CB41
0x18003cb2d  mov     r8, [rdi+18h]; pDacl
0x18003cb31  xor     r9d, r9d; bDaclDefaulted
0x18003cb34  mov     rcx, [rdi]; pSecurityDescriptor
0x18003cb37  lea     edx, [r9+1]; bDaclPresent
0x18003cb3b  call    cs:__imp_SetSecurityDescriptorDacl
0x18003cb41  mov     rsi, [rsp+28h+arg_8]
0x18003cb46  mov     eax, ebx
0x18003cb48  mov     rbx, [rsp+28h+arg_0]
0x18003cb4d  add     rsp, 20h
0x18003cb51  pop     rdi
0x18003cb52  retn
```
