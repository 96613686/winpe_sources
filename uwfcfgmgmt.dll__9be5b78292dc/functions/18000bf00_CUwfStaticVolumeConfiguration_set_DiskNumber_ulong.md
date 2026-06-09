# CUwfStaticVolumeConfiguration::set_DiskNumber(ulong)

- ea: `0x18000bf00`
- end: `0x18000bf49`
- name: `?set_DiskNumber@CUwfStaticVolumeConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009758`

## callees

- `0x18000a150`
- `0x18000bf00`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_DiskNumber(CUwfConfiguration **this, unsigned int a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"DiskNumber", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000bf00  push    rbx
0x18000bf02  sub     rsp, 30h
0x18000bf06  cmp     byte ptr [rcx+9], 0
0x18000bf0a  mov     r9d, edx; unsigned int
0x18000bf0d  mov     rbx, rcx
0x18000bf10  jz      short loc_18000BF26
0x18000bf12  mov     edx, 80070005h
0x18000bf17  mov     rax, [rbx+18h]
0x18000bf1b  mov     [rax+10h], edx
0x18000bf1e  mov     eax, edx
0x18000bf20  add     rsp, 30h
0x18000bf24  pop     rbx
0x18000bf25  retn
0x18000bf26  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000bf2a  mov     [rsp+38h+var_18], 1; bool
0x18000bf2f  mov     rcx, [rcx+18h]; this
0x18000bf33  lea     r8, aDisknumber; "DiskNumber"
0x18000bf3a  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000bf3f  mov     edx, eax
0x18000bf41  test    eax, eax
0x18000bf43  js      short loc_18000BF17
0x18000bf45  xor     edx, edx
0x18000bf47  jmp     short loc_18000BF1E
```
