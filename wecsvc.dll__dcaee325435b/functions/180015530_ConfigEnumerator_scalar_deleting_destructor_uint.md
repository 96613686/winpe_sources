# ConfigEnumerator::`scalar deleting destructor'(uint)

- ea: `0x180015530`
- end: `0x18001555f`
- name: `??_GConfigEnumerator@@UEAAPEAXI@Z`
- size: `47`
- prototype: `ConfigEnumerator *__fastcall(ConfigEnumerator *this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x1800034f0`
- `0x180003c10`
- `0x180015530`

## pseudocode

```c
ConfigEnumerator *__fastcall ConfigEnumerator::`scalar deleting destructor'(ConfigEnumerator *this, __int64 a2)
{
  char v2; // bl

  v2 = a2;
  ConfigEnumerator::~ConfigEnumerator(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180015530  mov     [rsp+arg_0], rbx
0x180015535  push    rdi
0x180015536  sub     rsp, 20h
0x18001553a  mov     ebx, edx
0x18001553c  mov     rdi, rcx
0x18001553f  call    ??1ConfigEnumerator@@UEAA@XZ; ConfigEnumerator::~ConfigEnumerator(void)
0x180015544  test    bl, 1
0x180015547  jz      short loc_180015551
0x180015549  mov     rcx, rdi; void *
0x18001554c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015551  mov     rbx, [rsp+28h+arg_0]
0x180015556  mov     rax, rdi
0x180015559  add     rsp, 20h
0x18001555d  pop     rdi
0x18001555e  retn
```
