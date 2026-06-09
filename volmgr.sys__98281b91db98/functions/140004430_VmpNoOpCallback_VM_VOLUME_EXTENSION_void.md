# VmpNoOpCallback(VM_VOLUME_EXTENSION *,void *)

- ea: `0x140004430`
- end: `0x140004433`
- name: `?VmpNoOpCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z`
- size: `3`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall VmpNoOpCallback(struct VM_VOLUME_EXTENSION *a1, void *a2)
{
  return 0;
}

```

## disassembly

```asm
0x140004430  xor     eax, eax
0x140004432  retn
```
