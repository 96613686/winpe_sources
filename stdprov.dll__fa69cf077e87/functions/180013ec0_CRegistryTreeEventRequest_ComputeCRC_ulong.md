# CRegistryTreeEventRequest::ComputeCRC(ulong &)

- ea: `0x180013ec0`
- end: `0x180013ed2`
- name: `?ComputeCRC@CRegistryTreeEventRequest@@UEAAJAEAK@Z`
- size: `18`
- prototype: `__int64 __fastcall(HKEY *this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013bb4`

## pseudocode

```c
__int64 __fastcall CRegistryTreeEventRequest::ComputeCRC(HKEY *this, unsigned int *a2)
{
  return CRegCRC::ComputeTreeCRC(this[18], 0xFFFFFFFF, a2);
}

```

## disassembly

```asm
0x180013ec0  mov     rcx, [rcx+90h]; HKEY
0x180013ec7  mov     r8, rdx; unsigned int *
0x180013eca  or      edx, 0FFFFFFFFh; unsigned int
0x180013ecd  jmp     ?ComputeTreeCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z; CRegCRC::ComputeTreeCRC(HKEY__ *,ulong,ulong &)
```
