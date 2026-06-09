# JsonHelper::`vector deleting destructor'(uint)

- ea: `0x1800125d0`
- end: `0x1800125ff`
- name: `??_EJsonHelper@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(JsonHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180012580`

## callees

- `0x180006734`
- `0x18001247c`
- `0x1800125d0`

## pseudocode

```c
JsonHelper *__fastcall JsonHelper::`vector deleting destructor'(JsonHelper *this, char a2)
{
  JsonHelper::~JsonHelper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800125d0  mov     [rsp+arg_0], rbx
0x1800125d5  push    rdi
0x1800125d6  sub     rsp, 20h
0x1800125da  mov     ebx, edx
0x1800125dc  mov     rdi, rcx
0x1800125df  call    ??1JsonHelper@@UEAA@XZ; JsonHelper::~JsonHelper(void)
0x1800125e4  test    bl, 1
0x1800125e7  jz      short loc_1800125F1
0x1800125e9  mov     rcx, rdi; Block
0x1800125ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800125f1  mov     rbx, [rsp+28h+arg_0]
0x1800125f6  mov     rax, rdi
0x1800125f9  add     rsp, 20h
0x1800125fd  pop     rdi
0x1800125fe  retn
```
