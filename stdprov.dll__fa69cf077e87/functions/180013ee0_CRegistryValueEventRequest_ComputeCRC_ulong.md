# CRegistryValueEventRequest::ComputeCRC(ulong &)

- ea: `0x180013ee0`
- end: `0x180013efa`
- name: `?ComputeCRC@CRegistryValueEventRequest@@UEAAJAEAK@Z`
- size: `26`
- prototype: `__int64 __fastcall(CRegistryValueEventRequest *this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009dd0`

## pseudocode

```c
__int64 __fastcall CRegistryValueEventRequest::ComputeCRC(CRegistryValueEventRequest *this, unsigned int *a2)
{
  return CRegCRC::ComputeValueCRC(*((HKEY *)this + 18), *((LPCWSTR *)this + 28), 0xFFFFFFFF, a2);
}

```

## disassembly

```asm
0x180013ee0  mov     r9, rdx; unsigned int *
0x180013ee3  or      r8d, 0FFFFFFFFh; unsigned int
0x180013ee7  mov     rdx, [rcx+0E0h]; lpValueName
0x180013eee  mov     rcx, [rcx+90h]; hKey
0x180013ef5  jmp     ?ComputeValueCRC@CRegCRC@@SAJPEAUHKEY__@@PEBGKAEAK@Z; CRegCRC::ComputeValueCRC(HKEY__ *,ushort const *,ulong,ulong &)
```
