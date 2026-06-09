# CUwfStaticConfiguration::ClearBackgroundTasksDisabled(ulong)

- ea: `0x180006144`
- end: `0x1800061ef`
- name: `?ClearBackgroundTasksDisabled@CUwfStaticConfiguration@@AEAAJK@Z`
- size: `171`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, unsigned int, HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cde0`
- `0x18000d040`

## callees

- `0x180006144`
- `0x1800092a8`

## string_xrefs

- `0x180006155`: `NoAutoUpdate`
- `0x180006168`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x18000615c`: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x18000619f`: `RegistryReorganizationLimitDays`
- `0x1800061aa`: `SYSTEM\CurrentControlSet\Control\Session Manager\Configuration Manager`
- `0x1800061b6`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Configuration Manager`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::ClearBackgroundTasksDisabled(
        CUwfStaticConfiguration *this,
        unsigned int a2,
        HKEY a3)
{
  int result; // eax
  CUwfStaticConfiguration *v5; // rcx
  HKEY v6; // r8
  CUwfStaticConfiguration *v7; // rcx
  HKEY v8; // r8

  if ( (a2 & 4) == 0
    || (result = CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(
                   this,
                   L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
                   a3,
                   L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
                   L"NoAutoUpdate",
                   a2),
        result >= 0) )
  {
    result = CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(
               this,
               L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\WindowsStore",
               a3,
               L"SOFTWARE\\Policies\\Microsoft\\WindowsStore",
               L"AutoDownload",
               a2);
    if ( result >= 0 )
    {
      result = CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(
                 v5,
                 L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Configuration Manager",
                 v6,
                 L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Configuration Manager",
                 L"RegistryReorganizationLimitDays",
                 a2);
      if ( result >= 0 )
        return CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(
                 v7,
                 L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                 v8,
                 L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                 L"MaintenanceDisabled",
                 a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006144  push    rbx
0x180006146  sub     rsp, 30h
0x18000614a  mov     ebx, edx
0x18000614c  test    dl, 4
0x18000614f  jz      short loc_180006178
0x180006151  mov     [rsp+38h+var_10], edx; unsigned int
0x180006155  lea     rax, aNoautoupdate; "NoAutoUpdate"
0x18000615c  lea     rdx, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies"...
0x180006163  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x180006168  lea     r9, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000616f  call    ?RestoreOrDeleteRegValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00K@Z; CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong)
0x180006174  test    eax, eax
0x180006176  js      short loc_1800061E9
0x180006178  lea     rax, aAutodownload; "AutoDownload"
0x18000617f  mov     [rsp+38h+var_10], ebx; unsigned int
0x180006183  lea     r9, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\WindowsS"...
0x18000618a  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18000618f  lea     rdx, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies"...
0x180006196  call    ?RestoreOrDeleteRegValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00K@Z; CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong)
0x18000619b  test    eax, eax
0x18000619d  js      short loc_1800061E9
0x18000619f  lea     rax, aRegistryreorga; "RegistryReorganizationLimitDays"
0x1800061a6  mov     [rsp+38h+var_10], ebx; unsigned int
0x1800061aa  lea     r9, aSystemCurrentc_11; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x1800061b1  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1800061b6  lea     rdx, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x1800061bd  call    ?RestoreOrDeleteRegValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00K@Z; CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong)
0x1800061c2  test    eax, eax
0x1800061c4  js      short loc_1800061E9
0x1800061c6  lea     rax, aMaintenancedis; "MaintenanceDisabled"
0x1800061cd  mov     [rsp+38h+var_10], ebx; unsigned int
0x1800061d1  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800061d8  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1800061dd  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800061e4  call    ?RestoreOrDeleteRegValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00K@Z; CUwfStaticConfiguration::RestoreOrDeleteRegValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong)
0x1800061e9  add     rsp, 30h
0x1800061ed  pop     rbx
0x1800061ee  retn
```
