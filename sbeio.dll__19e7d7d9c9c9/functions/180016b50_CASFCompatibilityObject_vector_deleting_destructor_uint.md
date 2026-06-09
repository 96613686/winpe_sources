# CASFCompatibilityObject::`vector deleting destructor'(uint)

- ea: `0x180016b50`
- end: `0x180016b7b`
- name: `??_ECASFCompatibilityObject@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(CASFCompatibilityObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001194`
- `0x180016b50`

## pseudocode

```c
CASFCompatibilityObject *__fastcall CASFCompatibilityObject::`vector deleting destructor'(
        CASFCompatibilityObject *this,
        char a2)
{
  *(_QWORD *)this = &CPersistentObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180016b50  push    rbx
0x180016b52  sub     rsp, 20h
0x180016b56  lea     rax, ??_7CPersistentObject@@6B@; const CPersistentObject::`vftable'
0x180016b5d  mov     rbx, rcx
0x180016b60  mov     [rcx], rax
0x180016b63  test    dl, 1
0x180016b66  jz      short loc_180016B72
0x180016b68  mov     edx, 40h ; '@'; unsigned __int64
0x180016b6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b72  mov     rax, rbx
0x180016b75  add     rsp, 20h
0x180016b79  pop     rbx
0x180016b7a  retn
```
