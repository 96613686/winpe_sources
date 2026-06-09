# CallNextDriverSync

- ea: `0x140029b30`
- end: `0x140029b47`
- name: `CallNextDriverSync`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000159c`
- `0x14000b40c`
- `0x14000f558`
- `0x1400142fc`

## callees

- `0x140029b50`

## pseudocode

```c
__int64 __fastcall CallNextDriverSync(__int64 a1, IRP *a2, char a3)
{
  return CallDriverSync(*(PDEVICE_OBJECT *)(a1 + 40), a2, a3, *(struct _DEVICE_OBJECT **)(a1 + 32));
}

```

## disassembly

```asm
0x140029b30  sub     rsp, 28h
0x140029b34  mov     r9, [rcx+20h]
0x140029b38  mov     rcx, [rcx+28h]; DeviceObject
0x140029b3c  call    CallDriverSync
0x140029b41  add     rsp, 28h
0x140029b45  retn
```
