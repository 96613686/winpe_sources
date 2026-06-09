# PnpInstallDisabled

- ea: `0x180012698`
- end: `0x1800126c4`
- name: `PnpInstallDisabled`
- size: `44`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000cf30`
- `0x180013fb0`

## callees

- `0x18000c050`

## string_xrefs

- `0x18001269c`: `DeviceInstallDisabled`
- `0x1800126aa`: `SYSTEM\CurrentControlSet\Services\DeviceInstall\Parameters`

## pseudocode

```c
_BOOL8 __fastcall PnpInstallDisabled(__int64 a1)
{
  return (unsigned int)pSetupGetPolicyValue(
                         a1,
                         L"SYSTEM\\CurrentControlSet\\Services\\DeviceInstall\\Parameters",
                         &qword_18001C3B0,
                         L"DeviceInstallDisabled") != 0;
}

```

## disassembly

```asm
0x180012698  sub     rsp, 38h
0x18001269c  lea     r9, aDeviceinstalld; "DeviceInstallDisabled"
0x1800126a3  lea     r8, qword_18001C3B0
0x1800126aa  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\De"...
0x1800126b1  call    pSetupGetPolicyValue
0x1800126b6  xor     ecx, ecx
0x1800126b8  test    eax, eax
0x1800126ba  setnz   cl
0x1800126bd  mov     eax, ecx
0x1800126bf  add     rsp, 38h
0x1800126c3  retn
```
