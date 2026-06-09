# [thunk]:XMLScrSite::Release`adjustor{8}' (void)

- ea: `0x14000c720`
- end: `0x14000c729`
- name: `?Release@XMLScrSite@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000c6d0`

## pseudocode

```c
__int64 __fastcall XMLScrSite::Release(__int64 a1)
{
  return XMLScrSite::Release((XMLScrSite *)(a1 - 8));
}

```

## disassembly

```asm
0x14000c720  sub     rcx, 8; this
0x14000c724  jmp     ?Release@XMLScrSite@@UEAAKXZ; XMLScrSite::Release(void)
```
