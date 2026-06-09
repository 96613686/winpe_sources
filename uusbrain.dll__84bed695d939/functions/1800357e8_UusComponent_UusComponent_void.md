# UusComponent::~UusComponent(void)

- ea: `0x1800357e8`
- end: `0x180035807`
- name: `??1UusComponent@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(UusComponent *__hidden this)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004ae1a`
- `0x18004ae86`
- `0x18004ca63`
- `0x18004caab`
- `0x18004caf3`
- `0x18004cb3b`
- `0x18004cb83`
- `0x18004cbcb`
- `0x18004cc13`
- `0x18004cc5b`
- `0x18004cca3`
- `0x18004cceb`
- `0x18004cd33`
- `0x18004cd7b`
- `0x18004cdc3`
- `0x18004ce0b`
- `0x18004ce53`
- `0x18004ce9b`
- `0x18004cee3`
- `0x18004cf2b`
- `0x18004cf73`

## callees

- `0x18000f84c`
- `0x180029644`

## pseudocode

```c
void __fastcall UusComponent::~UusComponent(UusComponent *this)
{
  std::vector<enum UusCapability>::~vector<enum UusCapability>((__int64)this + 32);
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x1800357e8  push    rbx
0x1800357ea  sub     rsp, 20h
0x1800357ee  mov     rbx, rcx
0x1800357f1  add     rcx, 20h ; ' '
0x1800357f5  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x1800357fa  mov     rcx, rbx
0x1800357fd  add     rsp, 20h
0x180035801  pop     rbx
0x180035802  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
