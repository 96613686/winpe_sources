# [thunk]:CConfigServiceProvider2Impl::Release`adjustor{8}' (void)

- ea: `0x1800073f0`
- end: `0x1800073f9`
- name: `?Release@CConfigServiceProvider2Impl@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180019810`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::Release(__int64 a1)
{
  return CConfigServiceProvider2Impl::Release((CConfigServiceProvider2Impl *)(a1 - 8));
}

```

## disassembly

```asm
0x1800073f0  sub     rcx, 8; this
0x1800073f4  jmp     ?Release@CConfigServiceProvider2Impl@@UEAAKXZ; CConfigServiceProvider2Impl::Release(void)
```
