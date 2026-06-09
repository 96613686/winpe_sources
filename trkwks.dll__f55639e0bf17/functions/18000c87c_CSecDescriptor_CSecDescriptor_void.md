# CSecDescriptor::CSecDescriptor(void)

- ea: `0x18000c87c`
- end: `0x18000c88e`
- name: `??0CSecDescriptor@@QEAA@XZ`
- size: `18`
- prototype: `CSecDescriptor *__fastcall(CSecDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180010638`

## pseudocode

```c
CSecDescriptor *__fastcall CSecDescriptor::CSecDescriptor(CSecDescriptor *this)
{
  CSecDescriptor *result; // rax

  result = this;
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x18000c87c  xorps   xmm0, xmm0
0x18000c87f  mov     rax, rcx
0x18000c882  movups  xmmword ptr [rcx], xmm0
0x18000c885  movups  xmmword ptr [rcx+10h], xmm0
0x18000c889  movups  xmmword ptr [rcx+20h], xmm0
0x18000c88d  retn
```
