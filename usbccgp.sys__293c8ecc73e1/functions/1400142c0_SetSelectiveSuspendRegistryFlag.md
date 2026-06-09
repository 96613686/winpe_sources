# SetSelectiveSuspendRegistryFlag

- ea: `0x1400142c0`
- end: `0x1400142f5`
- name: `SetSelectiveSuspendRegistryFlag`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14002d9c4`

## pseudocode

```c
__int64 __fastcall SetSelectiveSuspendRegistryFlag(__int64 a1, __int64 a2)
{
  struct _DEVICE_OBJECT *v2; // rcx
  int v4; // [rsp+48h] [rbp+10h] BYREF

  v2 = *(struct _DEVICE_OBJECT **)(a2 + 224);
  v4 = 1;
  return SetPdoRegistryParameter(v2, L"DeviceSelectiveSuspended", &v4, 4u, 4u);
}

```

## disassembly

```asm
0x1400142c0  sub     rsp, 38h
0x1400142c4  mov     rcx, [rdx+0E0h]; DeviceObject
0x1400142cb  lea     r8, [rsp+38h+arg_8]
0x1400142d0  mov     r9d, 4
0x1400142d6  mov     [rsp+38h+arg_8], 1
0x1400142de  lea     rdx, aDeviceselectiv; "DeviceSelectiveSuspended"
0x1400142e5  mov     [rsp+38h+Type], r9d; Type
0x1400142ea  call    SetPdoRegistryParameter
0x1400142ef  add     rsp, 38h
0x1400142f3  retn
```
