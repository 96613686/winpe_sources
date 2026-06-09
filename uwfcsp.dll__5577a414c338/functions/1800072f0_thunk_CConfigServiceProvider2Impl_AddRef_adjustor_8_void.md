# [thunk]:CConfigServiceProvider2Impl::AddRef`adjustor{8}' (void)

- ea: `0x1800072f0`
- end: `0x1800072f9`
- name: `?AddRef@CConfigServiceProvider2Impl@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x1800194c0`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::AddRef(__int64 a1)
{
  return CConfigServiceProvider2Impl::AddRef((CConfigServiceProvider2Impl *)(a1 - 8));
}

```

## disassembly

```asm
0x1800072f0  sub     rcx, 8; this
0x1800072f4  jmp     ?AddRef@CConfigServiceProvider2Impl@@UEAAKXZ; CConfigServiceProvider2Impl::AddRef(void)
```
