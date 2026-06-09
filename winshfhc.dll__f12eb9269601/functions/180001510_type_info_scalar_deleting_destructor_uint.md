# type_info::`scalar deleting destructor'(uint)

- ea: `0x180001510`
- end: `0x180001540`
- name: `??_Gtype_info@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(type_info *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800014d6`
- `0x180001510`

## import_xrefs

- `msvcrt!??1type_info@@UEAA@XZ` at `0x18000151f`
- `msvcrt!??1type_info@@UEAA@XZ` at `0x18000151f`

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
0x180001510  mov     [rsp+arg_0], rbx
0x180001515  push    rdi
0x180001516  sub     rsp, 20h
0x18000151a  mov     ebx, edx
0x18000151c  mov     rdi, rcx
0x18000151f  call    cs:__imp_??1type_info@@UEAA@XZ; type_info::~type_info(void)
0x180001525  test    bl, 1
0x180001528  jz      short loc_180001532
0x18000152a  mov     rcx, rdi; void *
0x18000152d  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001532  mov     rbx, [rsp+28h+arg_0]
0x180001537  mov     rax, rdi
0x18000153a  add     rsp, 20h
0x18000153e  pop     rdi
0x18000153f  retn
```
