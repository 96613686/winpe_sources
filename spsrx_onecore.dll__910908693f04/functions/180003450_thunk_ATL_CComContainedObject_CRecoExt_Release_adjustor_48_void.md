# [thunk]:ATL::CComContainedObject<CRecoExt>::Release`adjustor{48}' (void)

- ea: `0x180003450`
- end: `0x180003459`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@WDA@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::Release(a1 - 48);
}

```

## disassembly

```asm
0x180003450  sub     rcx, 30h ; '0'
0x180003454  jmp     ?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::Release(void)
```
