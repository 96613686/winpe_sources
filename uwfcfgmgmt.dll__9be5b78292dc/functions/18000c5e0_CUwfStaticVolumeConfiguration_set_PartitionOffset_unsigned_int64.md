# CUwfStaticVolumeConfiguration::set_PartitionOffset(unsigned __int64)

- ea: `0x18000c5e0`
- end: `0x18000c629`
- name: `?set_PartitionOffset@CUwfStaticVolumeConfiguration@@QEAAJ_K@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009f38`

## callees

- `0x18000a5f0`
- `0x18000c5e0`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_PartitionOffset(CUwfConfiguration **this, unsigned __int64 a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateQWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"PartitionOffset", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c5e0  push    rbx
0x18000c5e2  sub     rsp, 30h
0x18000c5e6  cmp     byte ptr [rcx+9], 0
0x18000c5ea  mov     r9, rdx; unsigned __int64
0x18000c5ed  mov     rbx, rcx
0x18000c5f0  jz      short loc_18000C606
0x18000c5f2  mov     edx, 80070005h
0x18000c5f7  mov     rax, [rbx+18h]
0x18000c5fb  mov     [rax+10h], edx
0x18000c5fe  mov     eax, edx
0x18000c600  add     rsp, 30h
0x18000c604  pop     rbx
0x18000c605  retn
0x18000c606  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000c60a  mov     [rsp+38h+var_18], 1; bool
0x18000c60f  mov     rcx, [rcx+18h]; this
0x18000c613  lea     r8, aPartitionoffse; "PartitionOffset"
0x18000c61a  call    ?UpdateQWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG_K_N@Z; CUwfConfiguration::UpdateQWORDValue(CUwfRegKey &,ushort const *,unsigned __int64,bool)
0x18000c61f  mov     edx, eax
0x18000c621  test    eax, eax
0x18000c623  js      short loc_18000C5F7
0x18000c625  xor     edx, edx
0x18000c627  jmp     short loc_18000C5FE
```
