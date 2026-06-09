# CRegistryValueEventRequest::Execute(int)

- ea: `0x180013ff0`
- end: `0x180013ffa`
- name: `?Execute@CRegistryValueEventRequest@@UEAAJH@Z`
- size: `10`
- prototype: `__int64 __fastcall(CRegistryValueEventRequest *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008fe0`

## pseudocode

```c
__int64 __fastcall CRegistryValueEventRequest::Execute(CRegistryValueEventRequest *this)
{
  return CRegistryEventRequest::Execute(this, 1);
}

```

## disassembly

```asm
0x180013ff0  mov     edx, 1; int
0x180013ff5  jmp     ?Execute@CRegistryEventRequest@@UEAAJH@Z; CRegistryEventRequest::Execute(int)
```
