# [thunk]:ATL::CComContainedObject<CRecoExt>::Release`adjustor{24}' (void)

- ea: `0x180003420`
- end: `0x180003429`
- name: `?Release@?$CComContainedObject@VCRecoExt@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::Release(a1 - 24);
}

```

## disassembly

```asm
0x180003420  sub     rcx, 18h
0x180003424  jmp     ?Release@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::Release(void)
```
