# [thunk]:ATL::CComContainedObject<CRecoExt>::AddRef`adjustor{16}' (void)

- ea: `0x180003250`
- end: `0x180003259`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180003250  sub     rcx, 10h
0x180003254  jmp     ?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::AddRef(void)
```
