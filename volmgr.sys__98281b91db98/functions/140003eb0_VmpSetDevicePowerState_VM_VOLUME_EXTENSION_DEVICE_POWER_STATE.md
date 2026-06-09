# VmpSetDevicePowerState(VM_VOLUME_EXTENSION *,_DEVICE_POWER_STATE)

- ea: `0x140003eb0`
- end: `0x140003eea`
- name: `?VmpSetDevicePowerState@@YAXPEAVVM_VOLUME_EXTENSION@@W4_DEVICE_POWER_STATE@@@Z`
- size: `58`
- prototype: `void(struct VM_VOLUME_EXTENSION *, enum _DEVICE_POWER_STATE)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003000`
- `0x140003ff0`
- `0x1400046a4`
- `0x14000eba0`

## callees

- `0x140003eb0`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x140003ed8`
- `ntoskrnl!PoSetPowerState` at `0x140003ed8`

## pseudocode

```c
void __fastcall VmpSetDevicePowerState(POWER_STATE *a1, POWER_STATE a2)
{
  if ( LOBYTE(a1[39].SystemState) )
  {
    if ( a1[76].SystemState != a2.SystemState )
    {
      a1[76].SystemState = a2.SystemState;
      PoSetPowerState(*(PDEVICE_OBJECT *)&a1->SystemState, DevicePowerState, a2);
    }
  }
}

```

## disassembly

```asm
0x140003eb0  sub     rsp, 28h
0x140003eb4  movzx   eax, byte ptr [rcx+9Ch]
0x140003ebb  test    al, al
0x140003ebd  jz      short loc_140003EE4
0x140003ebf  cmp     [rcx+130h], edx
0x140003ec5  jz      short loc_140003EE4
0x140003ec7  mov     [rcx+130h], edx
0x140003ecd  mov     r8d, edx; State
0x140003ed0  mov     rcx, [rcx]; DeviceObject
0x140003ed3  mov     edx, 1; Type
0x140003ed8  call    cs:__imp_PoSetPowerState
0x140003edf  nop     dword ptr [rax+rax+00h]
0x140003ee4  add     rsp, 28h
0x140003ee8  retn
```
