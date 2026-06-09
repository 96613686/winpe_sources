# WcGetSource

- ea: `0x1400024fc`
- end: `0x140002505`
- name: `WcGetSource`
- size: `9`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1400148bc`
- `0x140017f64`
- `0x140018254`
- `0x140023150`
- `0x140024040`
- `0x140024bf0`
- `0x140024f60`
- `0x140026de0`
- `0x140027854`
- `0x140028670`
- `0x140028e00`
- `0x14002a0cc`
- `0x14002f21c`
- `0x14002f9f8`

## pseudocode

```c
__int64 __fastcall WcGetSource(__int64 a1)
{
  return *(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL);
}

```

## disassembly

```asm
0x1400024fc  mov     rax, [rcx+38h]
0x140002500  mov     rax, [rax+18h]
0x140002504  retn
```
