# [thunk]:ATL::CComContainedObject<CRecoExt>::Release`adjustor{16}' (void)

- ea: `0x180003410`
- end: `0x180003419`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::Release(a1 - 16);
}

```

## disassembly

```asm
0x180003410  sub     rcx, 10h
0x180003414  jmp     ?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::Release(void)
```
