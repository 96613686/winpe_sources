# CUwfStaticVolumeConfiguration::set_PartitionGUID(ushort const *)

- ea: `0x18000c540`
- end: `0x18000c589`
- name: `?set_PartitionGUID@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009f38`

## callees

- `0x18000a6e0`
- `0x18000c540`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_PartitionGUID(
        CUwfConfiguration **this,
        const unsigned __int16 *a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateSzValue(this[3], (struct CUwfRegKey *)(this + 2), L"PartitionGuid", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c540  push    rbx
0x18000c542  sub     rsp, 30h
0x18000c546  cmp     byte ptr [rcx+9], 0
0x18000c54a  mov     r9, rdx; unsigned __int16 *
0x18000c54d  mov     rbx, rcx
0x18000c550  jz      short loc_18000C566
0x18000c552  mov     edx, 80070005h
0x18000c557  mov     rax, [rbx+18h]
0x18000c55b  mov     [rax+10h], edx
0x18000c55e  mov     eax, edx
0x18000c560  add     rsp, 30h
0x18000c564  pop     rbx
0x18000c565  retn
0x18000c566  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000c56a  mov     [rsp+38h+var_18], 1; bool
0x18000c56f  mov     rcx, [rcx+18h]; this
0x18000c573  lea     r8, aPartitionguid; "PartitionGuid"
0x18000c57a  call    ?UpdateSzValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG1_N@Z; CUwfConfiguration::UpdateSzValue(CUwfRegKey &,ushort const *,ushort const *,bool)
0x18000c57f  mov     edx, eax
0x18000c581  test    eax, eax
0x18000c583  js      short loc_18000C557
0x18000c585  xor     edx, edx
0x18000c587  jmp     short loc_18000C55E
```
