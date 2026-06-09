# WcGetSource

- ea: `0x1400024fc`
- end: `0x140002505`
- name: `WcGetSource`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1400148bc`
- `0x140017f64`
- `0x140018254`
- `0x1400231a0`
- `0x140024090`
- `0x140024c40`
- `0x140024fb0`
- `0x140026e30`
- `0x1400278a4`
- `0x1400286c0`
- `0x140028e50`
- `0x14002a11c`
- `0x14002f26c`
- `0x14002fa48`

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
