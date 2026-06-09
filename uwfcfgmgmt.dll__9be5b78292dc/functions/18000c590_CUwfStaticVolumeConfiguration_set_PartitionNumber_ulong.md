# CUwfStaticVolumeConfiguration::set_PartitionNumber(ulong)

- ea: `0x18000c590`
- end: `0x18000c5d9`
- name: `?set_PartitionNumber@CUwfStaticVolumeConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009758`

## callees

- `0x18000a150`
- `0x18000c590`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_PartitionNumber(CUwfConfiguration **this, unsigned int a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"PartitionNumber", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c590  push    rbx
0x18000c592  sub     rsp, 30h
0x18000c596  cmp     byte ptr [rcx+9], 0
0x18000c59a  mov     r9d, edx; unsigned int
0x18000c59d  mov     rbx, rcx
0x18000c5a0  jz      short loc_18000C5B6
0x18000c5a2  mov     edx, 80070005h
0x18000c5a7  mov     rax, [rbx+18h]
0x18000c5ab  mov     [rax+10h], edx
0x18000c5ae  mov     eax, edx
0x18000c5b0  add     rsp, 30h
0x18000c5b4  pop     rbx
0x18000c5b5  retn
0x18000c5b6  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000c5ba  mov     [rsp+38h+var_18], 1; bool
0x18000c5bf  mov     rcx, [rcx+18h]; this
0x18000c5c3  lea     r8, aPartitionnumbe; "PartitionNumber"
0x18000c5ca  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c5cf  mov     edx, eax
0x18000c5d1  test    eax, eax
0x18000c5d3  js      short loc_18000C5A7
0x18000c5d5  xor     edx, edx
0x18000c5d7  jmp     short loc_18000C5AE
```
