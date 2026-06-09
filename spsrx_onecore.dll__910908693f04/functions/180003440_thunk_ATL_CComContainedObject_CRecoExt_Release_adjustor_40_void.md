# [thunk]:ATL::CComContainedObject<CRecoExt>::Release`adjustor{40}' (void)

- ea: `0x180003440`
- end: `0x180003449`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@WCI@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::Release(a1 - 40);
}

```

## disassembly

```asm
0x180003440  sub     rcx, 28h ; '('
0x180003444  jmp     ?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::Release(void)
```
