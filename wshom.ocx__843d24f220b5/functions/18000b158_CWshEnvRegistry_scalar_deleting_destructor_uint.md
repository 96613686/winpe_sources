# CWshEnvRegistry::`scalar deleting destructor'(uint)

- ea: `0x18000b158`
- end: `0x18000b187`
- name: `??_GCWshEnvRegistry@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CWshEnvRegistry *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000b0f0`

## callees

- `0x180006124`
- `0x18000b090`
- `0x18000b158`

## pseudocode

```c
CWshEnvRegistry *__fastcall CWshEnvRegistry::`scalar deleting destructor'(CWshEnvRegistry *this, char a2)
{
  CWshEnvRegistry::~CWshEnvRegistry(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b158  mov     [rsp+arg_0], rbx
0x18000b15d  push    rdi
0x18000b15e  sub     rsp, 20h
0x18000b162  mov     ebx, edx
0x18000b164  mov     rdi, rcx
0x18000b167  call    ??1CWshEnvRegistry@@EEAA@XZ; CWshEnvRegistry::~CWshEnvRegistry(void)
0x18000b16c  test    bl, 1
0x18000b16f  jz      short loc_18000B179
0x18000b171  mov     rcx, rdi; Block
0x18000b174  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b179  mov     rbx, [rsp+28h+arg_0]
0x18000b17e  mov     rax, rdi
0x18000b181  add     rsp, 20h
0x18000b185  pop     rdi
0x18000b186  retn
```
