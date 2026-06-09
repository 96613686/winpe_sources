# SubscriptionConfigSnapshot::`vector deleting destructor'(uint)

- ea: `0x180015570`
- end: `0x18001559f`
- name: `??_ESubscriptionConfigSnapshot@@UEAAPEAXI@Z`
- size: `47`
- prototype: `SubscriptionConfigSnapshot *__fastcall(SubscriptionConfigSnapshot *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800034f0`
- `0x180003c94`
- `0x180015570`

## pseudocode

```c
SubscriptionConfigSnapshot *__fastcall SubscriptionConfigSnapshot::`vector deleting destructor'(
        SubscriptionConfigSnapshot *this,
        char a2)
{
  SubscriptionConfigSnapshot::~SubscriptionConfigSnapshot(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180015570  mov     [rsp+arg_0], rbx
0x180015575  push    rdi
0x180015576  sub     rsp, 20h
0x18001557a  mov     ebx, edx
0x18001557c  mov     rdi, rcx
0x18001557f  call    ??1SubscriptionConfigSnapshot@@UEAA@XZ; SubscriptionConfigSnapshot::~SubscriptionConfigSnapshot(void)
0x180015584  test    bl, 1
0x180015587  jz      short loc_180015591
0x180015589  mov     rcx, rdi; void *
0x18001558c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015591  mov     rbx, [rsp+28h+arg_0]
0x180015596  mov     rax, rdi
0x180015599  add     rsp, 20h
0x18001559d  pop     rdi
0x18001559e  retn
```
