# [thunk]:XMLScrSite::Release`adjustor{16}' (void)

- ea: `0x14000c730`
- end: `0x14000c739`
- name: `?Release@XMLScrSite@@WBA@EAAKXZ`
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
  return XMLScrSite::Release((XMLScrSite *)(a1 - 16));
}

```

## disassembly

```asm
0x14000c730  sub     rcx, 10h; this
0x14000c734  jmp     ?Release@XMLScrSite@@UEAAKXZ; XMLScrSite::Release(void)
```
