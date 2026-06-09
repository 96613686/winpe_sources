# ATL::CComMultiThreadModel::SafeDecrementReference(long *)

- ea: `0x180002f08`
- end: `0x180002f0d`
- name: `?SafeDecrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z`
- size: `5`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001560`
- `0x180005294`

## callees

- `0x180002f14`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall ATL::CComMultiThreadModel::SafeDecrementReference(int *a1)
{
  return ATL::SafeDecrementReferenceMultiThread(a1);
}

```

## disassembly

```asm
0x180002f08  jmp     ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
```
