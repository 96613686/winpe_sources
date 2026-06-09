# [thunk]:XMLScrSite::AddRef`adjustor{8}' (void)

- ea: `0x14000bd80`
- end: `0x14000bd89`
- name: `?AddRef@XMLScrSite@@W7EAAKXZ`
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
  return XMLScrSite::AddRef((XMLScrSite *)(a1 - 8));
}

```

## disassembly

```asm
0x14000bd80  sub     rcx, 8; this
0x14000bd84  jmp     ?AddRef@XMLScrSite@@UEAAKXZ; XMLScrSite::AddRef(void)
```
