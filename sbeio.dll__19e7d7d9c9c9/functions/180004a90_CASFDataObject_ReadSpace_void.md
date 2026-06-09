# CASFDataObject::ReadSpace(void)

- ea: `0x180004a90`
- end: `0x180004aa7`
- name: `?ReadSpace@CASFDataObject@@UEAA_KXZ`
- size: `23`
- prototype: `unsigned __int64 __fastcall(CASFDataObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002b010`

## pseudocode

```c
unsigned __int64 __fastcall CASFDataObject::ReadSpace(CASFDataObject *this)
{
  return (*(unsigned int (__fastcall **)(CASFDataObject *))(*(_QWORD *)this + 24LL))(this);
}

```

## disassembly

```asm
0x180004a90  sub     rsp, 28h
0x180004a94  mov     rax, [rcx]
0x180004a97  mov     rax, [rax+18h]
0x180004a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa0  mov     eax, eax
0x180004aa2  add     rsp, 28h
0x180004aa6  retn
```
