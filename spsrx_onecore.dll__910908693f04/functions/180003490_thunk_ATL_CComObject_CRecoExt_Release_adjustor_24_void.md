# [thunk]:ATL::CComObject<CRecoExt>::Release`adjustor{24}' (void)

- ea: `0x180003490`
- end: `0x180003499`
- name: `?Release@?$CComObject@VCRecoExt@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ec0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRecoExt>::Release(__int64 a1)
{
  return ATL::CComObject<CRecoExt>::Release(a1 - 24);
}

```

## disassembly

```asm
0x180003490  sub     rcx, 18h
0x180003494  jmp     ?Release@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::Release(void)
```
