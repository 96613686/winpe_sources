# CUwfConfiguration::set_UwfEnabledBeforeServicing(ulong)

- ea: `0x18000d0e0`
- end: `0x18000d129`
- name: `?set_UwfEnabledBeforeServicing@CUwfConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a150`
- `0x18000a8c8`
- `0x18000d0e0`

## string_xrefs

- `0x18000d10c`: `HKLM\SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Dynamic`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::set_UwfEnabledBeforeServicing(CUwfConfiguration *this, unsigned int a2)
{
  __int64 result; // rax
  CUwfConfiguration *v4; // rcx

  result = CUwfConfiguration::UpdateDWORDValue(
             this,
             (CUwfConfiguration *)((char *)this + 24),
             L"UwfEnabledBeforeServicing",
             a2,
             1);
  if ( (int)result >= 0 )
  {
    result = CUwfConfiguration::commitRegKeyValue(
               v4,
               L"HKLM\\SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Dynamic",
               L"UwfEnabledBeforeServicing");
    if ( (int)result >= 0 )
      return 0;
  }
  *((_DWORD *)this + 4) = result;
  return result;
}

```

## disassembly

```asm
0x18000d0e0  push    rbx
0x18000d0e2  sub     rsp, 30h
0x18000d0e6  mov     r9d, edx; unsigned int
0x18000d0e9  mov     [rsp+38h+var_18], 1; bool
0x18000d0ee  lea     rdx, [rcx+18h]; struct CUwfRegKey *
0x18000d0f2  mov     rbx, rcx
0x18000d0f5  lea     r8, aUwfenabledbefo; "UwfEnabledBeforeServicing"
0x18000d0fc  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000d101  test    eax, eax
0x18000d103  js      short loc_18000D120
0x18000d105  lea     r8, aUwfenabledbefo; "UwfEnabledBeforeServicing"
0x18000d10c  lea     rdx, aHklmSystemCurr_0; "HKLM\\SYSTEM\\CurrentControlSet\\Servic"...
0x18000d113  call    ?commitRegKeyValue@CUwfConfiguration@@AEAAJPEBG0@Z; CUwfConfiguration::commitRegKeyValue(ushort const *,ushort const *)
0x18000d118  test    eax, eax
0x18000d11a  js      short loc_18000D120
0x18000d11c  xor     eax, eax
0x18000d11e  jmp     short loc_18000D123
0x18000d120  mov     [rbx+10h], eax
0x18000d123  add     rsp, 30h
0x18000d127  pop     rbx
0x18000d128  retn
```
