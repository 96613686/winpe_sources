# CSecDescriptor::operator void * const(void)

- ea: `0x18000d440`
- end: `0x18000d473`
- name: `??BCSecDescriptor@@QEAAQEAXXZ`
- size: `51`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000a65c`
- `0x18000e8a8`
- `0x180010638`

## callees

- `0x18000d440`
- `0x18000fe2c`

## pseudocode

```c
__int64 __fastcall CSecDescriptor::operator void *(__int64 a1) const
{
  if ( (*(_BYTE *)(a1 + 28) & 2) != 0 )
    CSecDescriptor::_ReloadAcl(a1, 1);
  if ( (*(_BYTE *)(a1 + 44) & 2) != 0 )
    CSecDescriptor::_ReloadAcl(a1, 0);
  return *(_QWORD *)(a1 + 8);
}

```

## disassembly

```asm
0x18000d440  push    rbx
0x18000d442  sub     rsp, 20h
0x18000d446  test    byte ptr [rcx+1Ch], 2
0x18000d44a  mov     rbx, rcx
0x18000d44d  jz      short loc_18000D459
0x18000d44f  mov     edx, 1
0x18000d454  call    ?_ReloadAcl@CSecDescriptor@@AEAAXW4enumAclType@1@@Z; CSecDescriptor::_ReloadAcl(CSecDescriptor::enumAclType)
0x18000d459  test    byte ptr [rbx+2Ch], 2
0x18000d45d  jz      short loc_18000D469
0x18000d45f  xor     edx, edx
0x18000d461  mov     rcx, rbx
0x18000d464  call    ?_ReloadAcl@CSecDescriptor@@AEAAXW4enumAclType@1@@Z; CSecDescriptor::_ReloadAcl(CSecDescriptor::enumAclType)
0x18000d469  mov     rax, [rbx+8]
0x18000d46d  add     rsp, 20h
0x18000d471  pop     rbx
0x18000d472  retn
```
