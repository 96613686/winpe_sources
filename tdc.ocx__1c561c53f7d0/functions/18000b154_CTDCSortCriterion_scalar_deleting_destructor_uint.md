# CTDCSortCriterion::`scalar deleting destructor'(uint)

- ea: `0x18000b154`
- end: `0x18000b181`
- name: `??_GCTDCSortCriterion@@QEAAPEAXI@Z`
- size: `45`
- prototype: `void *__fastcall(CTDCSortCriterion *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000af64`
- `0x18000b154`
- `0x18000b370`
- `0x18000b6f8`

## callees

- `0x180001194`
- `0x18000b154`

## pseudocode

```c
CTDCSortCriterion *__fastcall CTDCSortCriterion::`scalar deleting destructor'(CTDCSortCriterion *this)
{
  CTDCSortCriterion *v2; // rcx

  v2 = (CTDCSortCriterion *)*((_QWORD *)this + 1);
  if ( v2 )
    CTDCSortCriterion::`scalar deleting destructor'(v2, 1u);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b154  push    rbx
0x18000b156  sub     rsp, 20h
0x18000b15a  mov     rbx, rcx
0x18000b15d  mov     rcx, [rcx+8]; this
0x18000b161  test    rcx, rcx
0x18000b164  jz      short loc_18000B170
0x18000b166  mov     edx, 1; unsigned int
0x18000b16b  call    ??_GCTDCSortCriterion@@QEAAPEAXI@Z; CTDCSortCriterion::`scalar deleting destructor'(uint)
0x18000b170  mov     rcx, rbx; Block
0x18000b173  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b178  mov     rax, rbx
0x18000b17b  add     rsp, 20h
0x18000b17f  pop     rbx
0x18000b180  retn
```
