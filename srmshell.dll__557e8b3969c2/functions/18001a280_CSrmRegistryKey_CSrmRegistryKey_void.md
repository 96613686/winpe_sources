# CSrmRegistryKey::~CSrmRegistryKey(void)

- ea: `0x18001a280`
- end: `0x18001a2ab`
- name: `??1CSrmRegistryKey@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800079e0`
- `0x18000a460`
- `0x18000a704`
- `0x18001cd34`

## callees

- `0x18001a384`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a297`

## pseudocode

```c
void __fastcall CSrmRegistryKey::~CSrmRegistryKey(LPVOID *this)
{
  CSrmRegistryKey::Close((CSrmRegistryKey *)this);
  CoTaskMemFree(this[2]);
  this[2] = 0;
}

```

## disassembly

```asm
0x18001a280  mov     [rsp+arg_0], rcx
0x18001a285  push    rbx
0x18001a286  sub     rsp, 20h
0x18001a28a  mov     rbx, rcx
0x18001a28d  call    ?Close@CSrmRegistryKey@@QEAAXXZ; CSrmRegistryKey::Close(void)
0x18001a292  nop
0x18001a293  mov     rcx, [rbx+10h]; pv
0x18001a297  call    cs:__imp_CoTaskMemFree
0x18001a29d  mov     qword ptr [rbx+10h], 0
0x18001a2a5  add     rsp, 20h
0x18001a2a9  pop     rbx
0x18001a2aa  retn
```
