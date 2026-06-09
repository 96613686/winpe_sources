# CLogConfigurableFilter::DestroyObject(void)

- ea: `0x1800259b0`
- end: `0x1800259d1`
- name: `?DestroyObject@CLogConfigurableFilter@@UEAAXXZ`
- size: `33`
- prototype: `void __fastcall(CLogConfigurableFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180001184`
- `0x180025604`
- `0x1800259b0`

## pseudocode

```c
void __fastcall CLogConfigurableFilter::DestroyObject(CLogConfigurableFilter *this)
{
  if ( this )
  {
    CLogConfigurableFilter::~CLogConfigurableFilter(this);
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800259b0  test    rcx, rcx
0x1800259b3  jz      short locret_1800259CF
0x1800259b5  push    rbx
0x1800259b6  sub     rsp, 20h
0x1800259ba  mov     rbx, rcx
0x1800259bd  call    ??1CLogConfigurableFilter@@QEAA@XZ
0x1800259c2  mov     rcx, rbx; Block
0x1800259c5  call    ??3@YAXPEAX@Z
0x1800259ca  add     rsp, 20h
0x1800259ce  pop     rbx
0x1800259cf  retn
```
