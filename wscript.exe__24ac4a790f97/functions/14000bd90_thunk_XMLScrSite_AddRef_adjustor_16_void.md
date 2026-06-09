# [thunk]:XMLScrSite::AddRef`adjustor{16}' (void)

- ea: `0x14000bd90`
- end: `0x14000bd99`
- name: `?AddRef@XMLScrSite@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000bd60`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRef(__int64 a1)
{
  return XMLScrSite::AddRef((XMLScrSite *)(a1 - 16));
}

```

## disassembly

```asm
0x14000bd90  sub     rcx, 10h; this
0x14000bd94  jmp     ?AddRef@XMLScrSite@@UEAAKXZ; XMLScrSite::AddRef(void)
```
