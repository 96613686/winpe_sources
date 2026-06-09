# CUwfStaticVolumeConfiguration::set_VolumeGuid(ushort const *)

- ea: `0x18000d130`
- end: `0x18000d185`
- name: `?set_VolumeGuid@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z`
- size: `85`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180006c80`

## callees

- `0x18000a6e0`
- `0x18000d130`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_VolumeGuid(CUwfConfiguration **this, const unsigned __int16 *a2)
{
  int updated; // edx

  if ( a2 )
  {
    if ( *((_BYTE *)this + 9) )
    {
      updated = -2147024891;
    }
    else
    {
      updated = CUwfConfiguration::UpdateSzValue(this[3], (struct CUwfRegKey *)(this + 2), L"VolumeName", a2, 1);
      if ( updated >= 0 )
        return 0;
    }
  }
  else
  {
    updated = -2147467261;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000d130  push    rbx
0x18000d132  sub     rsp, 30h
0x18000d136  mov     r9, rdx; unsigned __int16 *
0x18000d139  mov     rbx, rcx
0x18000d13c  test    rdx, rdx
0x18000d13f  jnz     short loc_18000D155
0x18000d141  mov     edx, 80004003h
0x18000d146  mov     rax, [rbx+18h]
0x18000d14a  mov     [rax+10h], edx
0x18000d14d  mov     eax, edx
0x18000d14f  add     rsp, 30h
0x18000d153  pop     rbx
0x18000d154  retn
0x18000d155  cmp     byte ptr [rcx+9], 0
0x18000d159  jz      short loc_18000D162
0x18000d15b  mov     edx, 80070005h
0x18000d160  jmp     short loc_18000D146
0x18000d162  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000d166  mov     [rsp+38h+var_18], 1; bool
0x18000d16b  mov     rcx, [rcx+18h]; this
0x18000d16f  lea     r8, aVolumename; "VolumeName"
0x18000d176  call    ?UpdateSzValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG1_N@Z; CUwfConfiguration::UpdateSzValue(CUwfRegKey &,ushort const *,ushort const *,bool)
0x18000d17b  mov     edx, eax
0x18000d17d  test    eax, eax
0x18000d17f  js      short loc_18000D146
0x18000d181  xor     edx, edx
0x18000d183  jmp     short loc_18000D14D
```
