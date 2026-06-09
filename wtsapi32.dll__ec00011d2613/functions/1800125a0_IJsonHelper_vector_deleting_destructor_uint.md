# IJsonHelper::`vector deleting destructor'(uint)

- ea: `0x1800125a0`
- end: `0x1800125c6`
- name: `??_EIJsonHelper@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(IJsonHelper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180006734`
- `0x1800125a0`

## pseudocode

```c
IJsonHelper *__fastcall IJsonHelper::`vector deleting destructor'(IJsonHelper *this, char a2)
{
  *(_QWORD *)this = &IJsonHelper::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800125a0  push    rbx
0x1800125a2  sub     rsp, 20h
0x1800125a6  lea     rax, ??_7IJsonHelper@@6B@; const IJsonHelper::`vftable'
0x1800125ad  mov     rbx, rcx
0x1800125b0  mov     [rcx], rax
0x1800125b3  test    dl, 1
0x1800125b6  jz      short loc_1800125BD
0x1800125b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800125bd  mov     rax, rbx
0x1800125c0  add     rsp, 20h
0x1800125c4  pop     rbx
0x1800125c5  retn
```
