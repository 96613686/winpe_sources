# LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180021e20`
- end: `0x180021e40`
- name: `??_GLB_RESOURCE_ID_CONFIG_ENTRY@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180022770`
- `0x180023144`

## callees

- `0x180021cb0`

## import_xrefs

- `RPCRT4!I_RpcFree` at `0x180021e31`
- `RPCRT4!I_RpcFree` at `0x180021e31`

## pseudocode

```c
LB_RESOURCE_ID_CONFIG_ENTRY *__fastcall LB_RESOURCE_ID_CONFIG_ENTRY::`scalar deleting destructor'(
        LB_RESOURCE_ID_CONFIG_ENTRY *this)
{
  LB_RESOURCE_ID_CONFIG_ENTRY::~LB_RESOURCE_ID_CONFIG_ENTRY(this);
  I_RpcFree(this);
  return this;
}

```

## disassembly

```asm
0x180021e20  push    rbx
0x180021e22  sub     rsp, 20h
0x180021e26  mov     rbx, rcx
0x180021e29  call    ??1LB_RESOURCE_ID_CONFIG_ENTRY@@QEAA@XZ; LB_RESOURCE_ID_CONFIG_ENTRY::~LB_RESOURCE_ID_CONFIG_ENTRY(void)
0x180021e2e  mov     rcx, rbx; Object
0x180021e31  call    cs:__imp_I_RpcFree
0x180021e37  mov     rax, rbx
0x180021e3a  add     rsp, 20h
0x180021e3e  pop     rbx
0x180021e3f  retn
```
