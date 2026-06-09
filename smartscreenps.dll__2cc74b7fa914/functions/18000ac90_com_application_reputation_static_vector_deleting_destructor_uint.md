# com::application_reputation_static::`vector deleting destructor'(uint)

- ea: `0x18000ac90`
- end: `0x18000acc4`
- name: `??_Eapplication_reputation_static@com@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(com::application_reputation_static *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001960`
- `0x18000a940`
- `0x18000ac90`

## pseudocode

```c
com::application_reputation_static *__fastcall com::application_reputation_static::`vector deleting destructor'(
        com::application_reputation_static *this,
        char a2)
{
  com::application_reputation_static::~application_reputation_static(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ac90  mov     [rsp+arg_0], rbx
0x18000ac95  push    rdi
0x18000ac96  sub     rsp, 20h
0x18000ac9a  mov     ebx, edx
0x18000ac9c  mov     rdi, rcx
0x18000ac9f  call    ??1application_reputation_static@com@@UEAA@XZ; com::application_reputation_static::~application_reputation_static(void)
0x18000aca4  test    bl, 1
0x18000aca7  jz      short loc_18000ACB6
0x18000aca9  mov     edx, 100h; unsigned __int64
0x18000acae  mov     rcx, rdi; void *
0x18000acb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000acb6  mov     rbx, [rsp+28h+arg_0]
0x18000acbb  mov     rax, rdi
0x18000acbe  add     rsp, 20h
0x18000acc2  pop     rdi
0x18000acc3  retn
```
