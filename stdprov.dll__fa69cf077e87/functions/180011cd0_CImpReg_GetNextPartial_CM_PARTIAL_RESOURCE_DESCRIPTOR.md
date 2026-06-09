# CImpReg::GetNextPartial(_CM_PARTIAL_RESOURCE_DESCRIPTOR *)

- ea: `0x180011cd0`
- end: `0x180011ce4`
- name: `?GetNextPartial@CImpReg@@QEAAPEAU_CM_PARTIAL_RESOURCE_DESCRIPTOR@@PEAU2@@Z`
- size: `20`
- prototype: `struct _CM_PARTIAL_RESOURCE_DESCRIPTOR::$0B1B57C3A77E1DBCBB55D6C1F13F5C7F::$08205AB7C2167E8C9C2BF0274334A928 *__fastcall(CImpReg *this, struct _CM_PARTIAL_RESOURCE_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011aa8`

## callees

- `0x180011cd0`

## pseudocode

```c
struct _CM_PARTIAL_RESOURCE_DESCRIPTOR::$0B1B57C3A77E1DBCBB55D6C1F13F5C7F::$08205AB7C2167E8C9C2BF0274334A928 *__fastcall CImpReg::GetNextPartial(
        CImpReg *this,
        struct _CM_PARTIAL_RESOURCE_DESCRIPTOR *a2)
{
  if ( a2->Type == 5 )
    return (struct _CM_PARTIAL_RESOURCE_DESCRIPTOR::$0B1B57C3A77E1DBCBB55D6C1F13F5C7F::$08205AB7C2167E8C9C2BF0274334A928 *)((char *)&a2->u.Memory48 + a2->u.Generic.Start.LowPart + 12);
  else
    return &a2->u.Memory48 + 1;
}

```

## disassembly

```asm
0x180011cd0  cmp     byte ptr [rdx], 5
0x180011cd3  lea     rcx, [rdx+10h]
0x180011cd7  jnz     short loc_180011CE0
0x180011cd9  mov     eax, [rdx+4]
0x180011cdc  add     rax, rcx
0x180011cdf  retn
0x180011ce0  mov     rax, rcx
0x180011ce3  retn
```
