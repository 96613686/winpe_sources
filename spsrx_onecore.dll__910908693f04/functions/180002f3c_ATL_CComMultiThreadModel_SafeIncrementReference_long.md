# ATL::CComMultiThreadModel::SafeIncrementReference(long *)

- ea: `0x180002f3c`
- end: `0x180002f41`
- name: `?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z`
- size: `5`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001af0`
- `0x180004d90`
- `0x180004dd0`
- `0x180005d90`
- `0x18000ad18`
- `0x18000ae6c`

## callees

- `0x180002f48`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall ATL::CComMultiThreadModel::SafeIncrementReference(int *a1)
{
  return ATL::SafeIncrementReferenceMultiThread(a1);
}

```

## disassembly

```asm
0x180002f3c  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
