# CUwfStaticVolumeConfiguration::set_DiskSignature(ulong)

- ea: `0x18000bf50`
- end: `0x18000bf99`
- name: `?set_DiskSignature@CUwfStaticVolumeConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009f38`

## callees

- `0x18000a150`
- `0x18000bf50`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_DiskSignature(CUwfConfiguration **this, unsigned int a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"DiskSignature", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000bf50  push    rbx
0x18000bf52  sub     rsp, 30h
0x18000bf56  cmp     byte ptr [rcx+9], 0
0x18000bf5a  mov     r9d, edx; unsigned int
0x18000bf5d  mov     rbx, rcx
0x18000bf60  jz      short loc_18000BF76
0x18000bf62  mov     edx, 80070005h
0x18000bf67  mov     rax, [rbx+18h]
0x18000bf6b  mov     [rax+10h], edx
0x18000bf6e  mov     eax, edx
0x18000bf70  add     rsp, 30h
0x18000bf74  pop     rbx
0x18000bf75  retn
0x18000bf76  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000bf7a  mov     [rsp+38h+var_18], 1; bool
0x18000bf7f  mov     rcx, [rcx+18h]; this
0x18000bf83  lea     r8, aDisksignature; "DiskSignature"
0x18000bf8a  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000bf8f  mov     edx, eax
0x18000bf91  test    eax, eax
0x18000bf93  js      short loc_18000BF67
0x18000bf95  xor     edx, edx
0x18000bf97  jmp     short loc_18000BF6E
```
