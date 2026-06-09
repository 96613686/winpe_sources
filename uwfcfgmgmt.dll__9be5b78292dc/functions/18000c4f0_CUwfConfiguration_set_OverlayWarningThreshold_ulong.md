# CUwfConfiguration::set_OverlayWarningThreshold(ulong)

- ea: `0x18000c4f0`
- end: `0x18000c539`
- name: `?set_OverlayWarningThreshold@CUwfConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017840`

## callees

- `0x18000a150`
- `0x18000a8c8`
- `0x18000c4f0`

## string_xrefs

- `0x18000c51c`: `HKLM\SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Dynamic`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_OverlayWarningThreshold(CUwfConfiguration *this, unsigned int a2)
{
  __int64 result; // rax
  CUwfConfiguration *v4; // rcx

  result = CUwfConfiguration::UpdateDWORDValue(
             this,
             (CUwfConfiguration *)((char *)this + 24),
             L"OverlayWarningThreshold",
             a2,
             1);
  if ( (int)result >= 0 )
  {
    result = CUwfConfiguration::commitRegKeyValue(
               v4,
               L"HKLM\\SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Dynamic",
               L"OverlayWarningThreshold");
    if ( (int)result >= 0 )
      return 0;
  }
  *((_DWORD *)this + 4) = result;
  return result;
}

```

## disassembly

```asm
0x18000c4f0  push    rbx
0x18000c4f2  sub     rsp, 30h
0x18000c4f6  mov     r9d, edx; unsigned int
0x18000c4f9  mov     [rsp+38h+var_18], 1; bool
0x18000c4fe  lea     rdx, [rcx+18h]; struct CUwfRegKey *
0x18000c502  mov     rbx, rcx
0x18000c505  lea     r8, aOverlaywarning; "OverlayWarningThreshold"
0x18000c50c  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c511  test    eax, eax
0x18000c513  js      short loc_18000C530
0x18000c515  lea     r8, aOverlaywarning; "OverlayWarningThreshold"
0x18000c51c  lea     rdx, aHklmSystemCurr_0; "HKLM\\SYSTEM\\CurrentControlSet\\Servic"...
0x18000c523  call    ?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z; CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)
0x18000c528  test    eax, eax
0x18000c52a  js      short loc_18000C530
0x18000c52c  xor     eax, eax
0x18000c52e  jmp     short loc_18000C533
0x18000c530  mov     [rbx+10h], eax
0x18000c533  add     rsp, 30h
0x18000c537  pop     rbx
0x18000c538  retn
```
