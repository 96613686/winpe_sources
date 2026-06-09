# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(void)

- ea: `0x180005294`
- end: `0x180005299`
- name: `?InternalRelease@?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAAKXZ`
- size: `5`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001660`
- `0x180005284`
- `0x180005650`
- `0x180006f0c`
- `0x180007ec0`
- `0x18000df60`
- `0x18000dfd0`

## callees

- `0x180002f08`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::InternalRelease(int *a1)
{
  return ATL::CComMultiThreadModel::SafeDecrementReference(a1);
}

```

## disassembly

```asm
0x180005294  jmp     ?SafeDecrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeDecrementReference(long *)
```
