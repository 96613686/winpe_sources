# EcOpenSubscriptionEnum$dtor$0

- ea: `0x18000c2b7`
- end: `0x18000c2c3`
- name: `EcOpenSubscriptionEnum$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003380`

## pseudocode

```c
__int64 __fastcall EcOpenSubscriptionEnum_dtor_0(__int64 a1, __int64 a2)
{
  return wmi::ScopeGuardImpl3<void (*)(unsigned long,unsigned short * *,bool),unsigned long,unsigned short * *,bool>::~ScopeGuardImpl3<void (*)(unsigned long,unsigned short * *,bool),unsigned long,unsigned short * *,bool>(a2 + 72);
}

```

## disassembly

```asm
0x18000c2b7  lea     rcx, [rdx+48h]
0x18000c2be  jmp     ??1?$ScopeGuardImpl3@P6AXKPEAPEAG_N@ZKPEAPEAG_N@wmi@@QEAA@XZ; wmi::ScopeGuardImpl3<void (*)(ulong,ushort * *,bool),ulong,ushort * *,bool>::~ScopeGuardImpl3<void (*)(ulong,ushort * *,bool),ulong,ushort * *,bool>(void)
```
