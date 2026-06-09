# [thunk]:ATL::CComContainedObject<CRecoExt>::Release`adjustor{32}' (void)

- ea: `0x180003430`
- end: `0x180003439`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@WCA@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::Release(a1 - 32);
}

```

## disassembly

```asm
0x180003430  sub     rcx, 20h ; ' '
0x180003434  jmp     ?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::Release(void)
```
