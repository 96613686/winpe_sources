# [thunk]:ATL::CComContainedObject<CRecoExt>::AddRef`adjustor{8}' (void)

- ea: `0x180003240`
- end: `0x180003249`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001c90`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CRecoExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180003240  sub     rcx, 8
0x180003244  jmp     ?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::AddRef(void)
```
