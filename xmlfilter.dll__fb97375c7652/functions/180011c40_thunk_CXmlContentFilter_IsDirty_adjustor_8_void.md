# [thunk]:CXmlContentFilter::IsDirty`adjustor{8}' (void)

- ea: `0x180011c40`
- end: `0x180011c49`
- name: `?IsDirty@CXmlContentFilter@@W7EAAJXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180011c20`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::IsDirty(__int64 a1)
{
  return CXmlContentFilter::IsDirty((CXmlContentFilter *)(a1 - 8));
}

```

## disassembly

```asm
0x180011c40  sub     rcx, 8; this
0x180011c44  jmp     ?IsDirty@CXmlContentFilter@@UEAAJXZ; CXmlContentFilter::IsDirty(void)
```
