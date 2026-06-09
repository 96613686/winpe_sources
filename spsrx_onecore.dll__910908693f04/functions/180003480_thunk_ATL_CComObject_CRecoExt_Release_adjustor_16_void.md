# [thunk]:ATL::CComObject<CRecoExt>::Release`adjustor{16}' (void)

- ea: `0x180003480`
- end: `0x180003489`
- name: `?Release@?$CComObject@VCRecoExt@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CRecoExt>::Release(a1 - 16);
}

```

## disassembly

```asm
0x180003480  sub     rcx, 10h
0x180003484  jmp     ?Release@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::Release(void)
```
