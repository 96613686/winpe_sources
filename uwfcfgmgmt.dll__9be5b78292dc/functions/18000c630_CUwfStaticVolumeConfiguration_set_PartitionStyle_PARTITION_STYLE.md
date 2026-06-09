# CUwfStaticVolumeConfiguration::set_PartitionStyle(_PARTITION_STYLE)

- ea: `0x18000c630`
- end: `0x18000c679`
- name: `?set_PartitionStyle@CUwfStaticVolumeConfiguration@@QEAAJW4_PARTITION_STYLE@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009f38`

## callees

- `0x18000a150`
- `0x18000c630`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_PartitionStyle(CUwfConfiguration **this, unsigned int a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"PartitionStyle", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c630  push    rbx
0x18000c632  sub     rsp, 30h
0x18000c636  cmp     byte ptr [rcx+9], 0
0x18000c63a  mov     r9d, edx; unsigned int
0x18000c63d  mov     rbx, rcx
0x18000c640  jz      short loc_18000C656
0x18000c642  mov     edx, 80070005h
0x18000c647  mov     rax, [rbx+18h]
0x18000c64b  mov     [rax+10h], edx
0x18000c64e  mov     eax, edx
0x18000c650  add     rsp, 30h
0x18000c654  pop     rbx
0x18000c655  retn
0x18000c656  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000c65a  mov     [rsp+38h+var_18], 1; bool
0x18000c65f  mov     rcx, [rcx+18h]; this
0x18000c663  lea     r8, aPartitionstyle; "PartitionStyle"
0x18000c66a  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c66f  mov     edx, eax
0x18000c671  test    eax, eax
0x18000c673  js      short loc_18000C647
0x18000c675  xor     edx, edx
0x18000c677  jmp     short loc_18000C64E
```
