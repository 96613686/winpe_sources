# MSAClientTraceTelemetry::Provider(void)

- ea: `0x18000cea8`
- end: `0x18000cec1`
- name: `?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000c47c`
- `0x18000c508`
- `0x18000c590`
- `0x18000c618`
- `0x18000cae0`
- `0x18000ce9c`
- `0x18000d154`
- `0x18000d6dc`
- `0x18000d88c`
- `0x18000d960`

## callees

- `0x18000ec50`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall MSAClientTraceTelemetry::Provider(__int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<MSAClientTraceTelemetry>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x18000cea8  sub     rsp, 28h
0x18000ceac  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_@@CA@XZ; _lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_(void)
0x18000ceb3  call    ?get@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAAPEAVMSAClientTraceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<MSAClientTraceTelemetry>::get(void (*)(void))
0x18000ceb8  mov     rax, [rax+8]
0x18000cebc  add     rsp, 28h
0x18000cec0  retn
```
