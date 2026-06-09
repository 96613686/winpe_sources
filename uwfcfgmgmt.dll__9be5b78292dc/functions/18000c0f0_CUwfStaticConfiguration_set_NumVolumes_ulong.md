# CUwfStaticConfiguration::set_NumVolumes(ulong)

- ea: `0x18000c0f0`
- end: `0x18000c139`
- name: `?set_NumVolumes@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180006c80`
- `0x180007420`

## callees

- `0x18000a150`
- `0x18000c0f0`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_NumVolumes(CUwfConfiguration **this, unsigned int a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[4], (struct CUwfRegKey *)(this + 3), L"NumVolumes", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[4] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c0f0  push    rbx
0x18000c0f2  sub     rsp, 30h
0x18000c0f6  cmp     byte ptr [rcx+9], 0
0x18000c0fa  mov     r9d, edx; unsigned int
0x18000c0fd  mov     rbx, rcx
0x18000c100  jz      short loc_18000C116
0x18000c102  mov     edx, 80070005h
0x18000c107  mov     rax, [rbx+20h]
0x18000c10b  mov     [rax+10h], edx
0x18000c10e  mov     eax, edx
0x18000c110  add     rsp, 30h
0x18000c114  pop     rbx
0x18000c115  retn
0x18000c116  lea     rdx, [rcx+18h]; struct CUwfRegKey *
0x18000c11a  mov     [rsp+38h+var_18], 1; bool
0x18000c11f  mov     rcx, [rcx+20h]; this
0x18000c123  lea     r8, aNumvolumes; "NumVolumes"
0x18000c12a  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c12f  mov     edx, eax
0x18000c131  test    eax, eax
0x18000c133  js      short loc_18000C107
0x18000c135  xor     edx, edx
0x18000c137  jmp     short loc_18000C10E
```
