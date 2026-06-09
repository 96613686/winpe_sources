# CUwfConfiguration::set_OverlayCriticalThreshold(ulong)

- ea: `0x18000c140`
- end: `0x18000c189`
- name: `?set_OverlayCriticalThreshold@CUwfConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017500`

## callees

- `0x18000a150`
- `0x18000a8c8`
- `0x18000c140`

## string_xrefs

- `0x18000c16c`: `HKLM\SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Dynamic`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_OverlayCriticalThreshold(CUwfConfiguration *this, unsigned int a2)
{
  __int64 result; // rax
  CUwfConfiguration *v4; // rcx

  result = CUwfConfiguration::UpdateDWORDValue(
             this,
             (CUwfConfiguration *)((char *)this + 24),
             L"OverlayCriticalThreshold",
             a2,
             1);
  if ( (int)result >= 0 )
  {
    result = CUwfConfiguration::commitRegKeyValue(
               v4,
               L"HKLM\\SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Dynamic",
               L"OverlayCriticalThreshold");
    if ( (int)result >= 0 )
      return 0;
  }
  *((_DWORD *)this + 4) = result;
  return result;
}

```

## disassembly

```asm
0x18000c140  push    rbx
0x18000c142  sub     rsp, 30h
0x18000c146  mov     r9d, edx; unsigned int
0x18000c149  mov     [rsp+38h+var_18], 1; bool
0x18000c14e  lea     rdx, [rcx+18h]; struct CUwfRegKey *
0x18000c152  mov     rbx, rcx
0x18000c155  lea     r8, aOverlaycritica; "OverlayCriticalThreshold"
0x18000c15c  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c161  test    eax, eax
0x18000c163  js      short loc_18000C180
0x18000c165  lea     r8, aOverlaycritica; "OverlayCriticalThreshold"
0x18000c16c  lea     rdx, aHklmSystemCurr_0; "HKLM\\SYSTEM\\CurrentControlSet\\Servic"...
0x18000c173  call    ?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z; CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)
0x18000c178  test    eax, eax
0x18000c17a  js      short loc_18000C180
0x18000c17c  xor     eax, eax
0x18000c17e  jmp     short loc_18000C183
0x18000c180  mov     [rbx+10h], eax
0x18000c183  add     rsp, 30h
0x18000c187  pop     rbx
0x18000c188  retn
```
