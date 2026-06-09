# CRegistryKeyEventRequest::ComputeCRC(ulong &)

- ea: `0x180013ea0`
- end: `0x180013eaf`
- name: `?ComputeCRC@CRegistryKeyEventRequest@@UEAAJAEAK@Z`
- size: `15`
- prototype: `__int64 __fastcall(HKEY *this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013904`

## pseudocode

```c
__int64 __fastcall CRegistryKeyEventRequest::ComputeCRC(HKEY *this, unsigned int *a2)
{
  return CRegCRC::ComputeKeyCRC(this[18], (unsigned int)a2, a2);
}

```

## disassembly

```asm
0x180013ea0  mov     rcx, [rcx+90h]; hKey
0x180013ea7  mov     r8, rdx; unsigned int *
0x180013eaa  jmp     ?ComputeKeyCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z; CRegCRC::ComputeKeyCRC(HKEY__ *,ulong,ulong &)
```
