# type_info::`scalar deleting destructor'(uint)

- ea: `0x180002130`
- end: `0x180002160`
- name: `??_Gtype_info@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(type_info *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002080`
- `0x180002130`

## import_xrefs

- `msvcrt!??1type_info@@UEAA@XZ` at `0x18000213f`
- `msvcrt!??1type_info@@UEAA@XZ` at `0x18000213f`

## pseudocode

```c
type_info *__fastcall type_info::`scalar deleting destructor'(type_info *this, char a2)
{
  type_info::~type_info(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_0], rbx
0x180002135  push    rdi
0x180002136  sub     rsp, 20h
0x18000213a  mov     ebx, edx
0x18000213c  mov     rdi, rcx
0x18000213f  call    cs:__imp_??1type_info@@UEAA@XZ; type_info::~type_info(void)
0x180002145  test    bl, 1
0x180002148  jz      short loc_180002152
0x18000214a  mov     rcx, rdi; Block
0x18000214d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002152  mov     rax, rdi
0x180002155  mov     rbx, [rsp+28h+arg_0]
0x18000215a  add     rsp, 20h
0x18000215e  pop     rdi
0x18000215f  retn
```
