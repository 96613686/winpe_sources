# CSecDescriptor::~CSecDescriptor(void)

- ea: `0x18000d1d0`
- end: `0x18000d1f5`
- name: `??1CSecDescriptor@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CSecDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000ad70`
- `0x180010638`

## callees

- `0x18000d1fc`
- `0x18000d228`

## pseudocode

```c
void __fastcall CSecDescriptor::~CSecDescriptor(CSecDescriptor *this)
{
  CSecDescriptor::UnInitialize(this);
  CACL::UnInitialize((CSecDescriptor *)((char *)this + 32));
  CACL::UnInitialize((CSecDescriptor *)((char *)this + 16));
}

```

## disassembly

```asm
0x18000d1d0  push    rbx
0x18000d1d2  sub     rsp, 20h
0x18000d1d6  mov     rbx, rcx
0x18000d1d9  call    ?UnInitialize@CSecDescriptor@@QEAAXXZ; CSecDescriptor::UnInitialize(void)
0x18000d1de  lea     rcx, [rbx+20h]; this
0x18000d1e2  call    ?UnInitialize@CACL@@QEAAXXZ; CACL::UnInitialize(void)
0x18000d1e7  lea     rcx, [rbx+10h]; this
0x18000d1eb  add     rsp, 20h
0x18000d1ef  pop     rbx
0x18000d1f0  jmp     ?UnInitialize@CACL@@QEAAXXZ; CACL::UnInitialize(void)
```
