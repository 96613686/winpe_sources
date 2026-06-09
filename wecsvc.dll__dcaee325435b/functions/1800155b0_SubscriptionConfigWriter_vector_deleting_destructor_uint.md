# SubscriptionConfigWriter::`vector deleting destructor'(uint)

- ea: `0x1800155b0`
- end: `0x1800155df`
- name: `??_ESubscriptionConfigWriter@@UEAAPEAXI@Z`
- size: `47`
- prototype: `SubscriptionConfigWriter *__fastcall(SubscriptionConfigWriter *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800034f0`
- `0x1800154cc`
- `0x1800155b0`

## pseudocode

```c
SubscriptionConfigWriter *__fastcall SubscriptionConfigWriter::`vector deleting destructor'(
        SubscriptionConfigWriter *this,
        char a2)
{
  SubscriptionConfigWriter::~SubscriptionConfigWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800155b0  mov     [rsp+arg_0], rbx
0x1800155b5  push    rdi
0x1800155b6  sub     rsp, 20h
0x1800155ba  mov     ebx, edx
0x1800155bc  mov     rdi, rcx
0x1800155bf  call    ??1SubscriptionConfigWriter@@UEAA@XZ; SubscriptionConfigWriter::~SubscriptionConfigWriter(void)
0x1800155c4  test    bl, 1
0x1800155c7  jz      short loc_1800155D1
0x1800155c9  mov     rcx, rdi; void *
0x1800155cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800155d1  mov     rbx, [rsp+28h+arg_0]
0x1800155d6  mov     rax, rdi
0x1800155d9  add     rsp, 20h
0x1800155dd  pop     rdi
0x1800155de  retn
```
