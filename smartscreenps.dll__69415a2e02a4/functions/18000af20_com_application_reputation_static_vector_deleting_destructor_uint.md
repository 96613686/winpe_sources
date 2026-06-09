# com::application_reputation_static::`vector deleting destructor'(uint)

- ea: `0x18000af20`
- end: `0x18000af55`
- name: `??_Eapplication_reputation_static@com@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(com::application_reputation_static *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001960`
- `0x18000abc8`
- `0x18000af20`

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
0x18000af20  mov     [rsp+arg_0], rbx
0x18000af25  push    rdi
0x18000af26  sub     rsp, 20h
0x18000af2a  mov     ebx, edx
0x18000af2c  mov     rdi, rcx
0x18000af2f  call    ??1application_reputation_static@com@@UEAA@XZ; com::application_reputation_static::~application_reputation_static(void)
0x18000af34  test    bl, 1
0x18000af37  jz      short loc_18000AF46
0x18000af39  mov     edx, 100h; unsigned __int64
0x18000af3e  mov     rcx, rdi; void *
0x18000af41  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000af46  mov     rbx, [rsp+28h+arg_0]
0x18000af4b  mov     rax, rdi
0x18000af4e  add     rsp, 20h
0x18000af52  pop     rdi
0x18000af53  retn
```
