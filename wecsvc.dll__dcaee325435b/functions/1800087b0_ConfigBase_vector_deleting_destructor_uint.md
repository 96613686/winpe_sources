# ConfigBase::`vector deleting destructor'(uint)

- ea: `0x1800087b0`
- end: `0x1800087df`
- name: `??_EConfigBase@@UEAAPEAXI@Z`
- size: `47`
- prototype: `ConfigBase *__fastcall(ConfigBase *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800034f0`
- `0x180003be8`
- `0x1800087b0`

## pseudocode

```c
ConfigBase *__fastcall ConfigBase::`vector deleting destructor'(ConfigBase *this, char a2)
{
  ConfigBase::~ConfigBase(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800087b0  mov     [rsp+arg_0], rbx
0x1800087b5  push    rdi
0x1800087b6  sub     rsp, 20h
0x1800087ba  mov     ebx, edx
0x1800087bc  mov     rdi, rcx
0x1800087bf  call    ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
0x1800087c4  test    bl, 1
0x1800087c7  jz      short loc_1800087D1
0x1800087c9  mov     rcx, rdi; void *
0x1800087cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800087d1  mov     rbx, [rsp+28h+arg_0]
0x1800087d6  mov     rax, rdi
0x1800087d9  add     rsp, 20h
0x1800087dd  pop     rdi
0x1800087de  retn
```
