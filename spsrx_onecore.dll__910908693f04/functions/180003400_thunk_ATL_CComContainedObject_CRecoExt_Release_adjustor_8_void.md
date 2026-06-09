# [thunk]:ATL::CComContainedObject<CRecoExt>::Release`adjustor{8}' (void)

- ea: `0x180003400`
- end: `0x180003409`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001cb0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CRecoExt>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180003400  sub     rcx, 8
0x180003404  jmp     ?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::Release(void)
```
