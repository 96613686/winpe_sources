# FontEmbeddingTelemetryProvider::Provider(void)

- ea: `0x18001c024`
- end: `0x18001c03d`
- name: `?Provider@FontEmbeddingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bc80`
- `0x18001c2fc`
- `0x18001c41c`
- `0x18001c53c`
- `0x1800252c0`
- `0x180025f60`
- `0x180025ffc`
- `0x180026098`
- `0x180026140`
- `0x180026380`
- `0x1800265c0`
- `0x180026800`

## callees

- `0x18001bb28`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall FontEmbeddingTelemetryProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<FontEmbeddingTelemetryProvider>::get(
                                             a1,
                                             _lambda_744b78a7a8fdc0abb948537d5c2200d0_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x18001c024  sub     rsp, 28h
0x18001c028  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_744b78a7a8fdc0abb948537d5c2200d0_@@CA@XZ; _lambda_744b78a7a8fdc0abb948537d5c2200d0_::_lambda_invoker_cdecl_(void)
0x18001c02f  call    ?get@?$static_lazy@VFontEmbeddingTelemetryProvider@@@details@wil@@QEAAPEAVFontEmbeddingTelemetryProvider@@P6AXXZ@Z; wil::details::static_lazy<FontEmbeddingTelemetryProvider>::get(void (*)(void))
0x18001c034  mov     rax, [rax+8]
0x18001c038  add     rsp, 28h
0x18001c03c  retn
```
