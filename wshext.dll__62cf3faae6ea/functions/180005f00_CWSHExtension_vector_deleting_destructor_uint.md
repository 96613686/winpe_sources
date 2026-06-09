# CWSHExtension::`vector deleting destructor'(uint)

- ea: `0x180005f00`
- end: `0x180005f2f`
- name: `??_ECWSHExtension@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CWSHExtension *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180005ef0`

## callees

- `0x1800031f4`
- `0x180005e60`
- `0x180005f00`

## pseudocode

```c
CWSHExtension *__fastcall CWSHExtension::`vector deleting destructor'(CWSHExtension *this, char a2)
{
  CWSHExtension::~CWSHExtension(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005f00  mov     [rsp+arg_0], rbx
0x180005f05  push    rdi
0x180005f06  sub     rsp, 20h
0x180005f0a  mov     ebx, edx
0x180005f0c  mov     rdi, rcx
0x180005f0f  call    ??1CWSHExtension@@UEAA@XZ; CWSHExtension::~CWSHExtension(void)
0x180005f14  test    bl, 1
0x180005f17  jz      short loc_180005F21
0x180005f19  mov     rcx, rdi; Block
0x180005f1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005f21  mov     rbx, [rsp+28h+arg_0]
0x180005f26  mov     rax, rdi
0x180005f29  add     rsp, 20h
0x180005f2d  pop     rdi
0x180005f2e  retn
```
