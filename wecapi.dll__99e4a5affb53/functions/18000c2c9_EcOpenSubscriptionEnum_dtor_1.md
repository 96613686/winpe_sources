# EcOpenSubscriptionEnum$dtor$1

- ea: `0x18000c2c9`
- end: `0x18000c2d5`
- name: `EcOpenSubscriptionEnum$dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800032c8`

## pseudocode

```c
__int64 __fastcall EcOpenSubscriptionEnum_dtor_1(__int64 a1, __int64 a2)
{
  return wmi::AutoRef<Object>::~AutoRef<Object>(a2 + 312);
}

```

## disassembly

```asm
0x18000c2c9  lea     rcx, [rdx+138h]
0x18000c2d0  jmp     ??1?$AutoRef@VObject@@@wmi@@QEAA@XZ; wmi::AutoRef<Object>::~AutoRef<Object>(void)
```
