# ServiceMain(ulong,ushort * *)

- ea: `0x18000f040`
- end: `0x18000f045`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `5`
- prototype: `void __fastcall(__int64, unsigned __int16 **, struct _SVCHOST_GLOBAL_DATA *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180001d4c`

## pseudocode

```c
// attributes: thunk
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2, struct _SVCHOST_GLOBAL_DATA *a3, void *a4)
{
  ServiceEntry(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f040  jmp     ?ServiceEntry@@YAXKPEAPEAGPEAU_SVCHOST_GLOBAL_DATA@@PEAX@Z; ServiceEntry(ulong,ushort * *,_SVCHOST_GLOBAL_DATA *,void *)
```
