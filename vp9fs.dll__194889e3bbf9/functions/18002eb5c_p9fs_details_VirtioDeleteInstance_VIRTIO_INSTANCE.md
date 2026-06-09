# p9fs::details::VirtioDeleteInstance(_VIRTIO_INSTANCE * &)

- ea: `0x18002eb5c`
- end: `0x18002eb63`
- name: `?VirtioDeleteInstance@details@p9fs@@YAXAEAPEAU_VIRTIO_INSTANCE@@@Z`
- size: `7`
- prototype: `void __fastcall(p9fs::details *__hidden this, struct _VIRTIO_INSTANCE **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002d530`
- `0x18002dd30`
- `0x18002ea30`

## import_xrefs

- `vmvirtio!VirtioDeleteInstance` at `0x18002eb5c`

## pseudocode

```c
// attributes: thunk
void __fastcall p9fs::details::VirtioDeleteInstance(p9fs::details *this, struct _VIRTIO_INSTANCE **a2)
{
  VirtioDeleteInstance(this, a2);
}

```

## disassembly

```asm
0x18002eb5c  jmp     cs:__imp_VirtioDeleteInstance
```
