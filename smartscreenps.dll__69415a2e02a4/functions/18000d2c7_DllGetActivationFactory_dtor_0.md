# DllGetActivationFactory$dtor$0

- ea: `0x18000d2c7`
- end: `0x18000d2d3`
- name: `DllGetActivationFactory$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000aba0`

## pseudocode

```c
void __fastcall DllGetActivationFactory_dtor_0(__int64 a1, __int64 a2)
{
  api_guard::~api_guard((api_guard *)(a2 + 192));
}

```

## disassembly

```asm
0x18000d2c7  lea     rcx, [rdx+0C0h]; this
0x18000d2ce  jmp     ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
```
