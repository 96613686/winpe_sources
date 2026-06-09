# CConfigServiceProvider2Impl::AddRef(void)

- ea: `0x1800194c0`
- end: `0x1800194cd`
- name: `?AddRef@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x1800072f0`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::AddRef(CConfigServiceProvider2Impl *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 10);
}

```

## disassembly

```asm
0x1800194c0  mov     eax, 1
0x1800194c5  lock xadd [rcx+28h], eax
0x1800194ca  inc     eax
0x1800194cc  retn
```
