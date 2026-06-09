# CVssSecurityDescriptor::Allow(void *,ulong,ulong)

- ea: `0x18003c7b8`
- end: `0x18003c7ff`
- name: `?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct _ACL **this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bc08`

## callees

- `0x18003b9bc`
- `0x18003c7b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003c7e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003c7e7`

## pseudocode

```c
__int64 __fastcall CVssSecurityDescriptor::Allow(struct _ACL **this, void *a2)
{
  int v3; // ebx

  v3 = CVssSecurityDescriptor::AddAccessAllowedACEToACL(this + 3, a2);
  if ( v3 >= 0 )
    SetSecurityDescriptorDacl(*this, 1, this[3], 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003c7b8  mov     [rsp+arg_0], rbx
0x18003c7bd  mov     [rsp+arg_8], rsi
0x18003c7c2  push    rdi
0x18003c7c3  sub     rsp, 20h
0x18003c7c7  mov     rdi, rcx
0x18003c7ca  add     rcx, 18h; struct _ACL **
0x18003c7ce  call    ?AddAccessAllowedACEToACL@CVssSecurityDescriptor@@CAJPEAPEAU_ACL@@PEAXKK@Z; CVssSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong,ulong)
0x18003c7d3  mov     ebx, eax
0x18003c7d5  test    eax, eax
0x18003c7d7  js      short loc_18003C7ED
0x18003c7d9  mov     r8, [rdi+18h]; pDacl
0x18003c7dd  xor     r9d, r9d; bDaclDefaulted
0x18003c7e0  mov     rcx, [rdi]; pSecurityDescriptor
0x18003c7e3  lea     edx, [r9+1]; bDaclPresent
0x18003c7e7  call    cs:__imp_SetSecurityDescriptorDacl
0x18003c7ed  mov     rsi, [rsp+28h+arg_8]
0x18003c7f2  mov     eax, ebx
0x18003c7f4  mov     rbx, [rsp+28h+arg_0]
0x18003c7f9  add     rsp, 20h
0x18003c7fd  pop     rdi
0x18003c7fe  retn
```
