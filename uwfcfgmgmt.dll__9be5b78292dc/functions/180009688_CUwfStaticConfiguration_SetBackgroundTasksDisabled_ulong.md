# CUwfStaticConfiguration::SetBackgroundTasksDisabled(ulong)

- ea: `0x180009688`
- end: `0x180009752`
- name: `?SetBackgroundTasksDisabled@CUwfStaticConfiguration@@AEAAJK@Z`
- size: `202`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, unsigned int, HKEY)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cde0`
- `0x18000d040`

## callees

- `0x180009688`
- `0x180009a50`

## string_xrefs

- `0x180009696`: `NoAutoUpdate`
- `0x1800096a1`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x1800096af`: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x1800096fa`: `RegistryReorganizationLimitDays`
- `0x180009705`: `SYSTEM\CurrentControlSet\Control\Session Manager\Configuration Manager`
- `0x18000970c`: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Configuration Manager`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::SetBackgroundTasksDisabled(
        CUwfStaticConfiguration *this,
        unsigned int a2,
        HKEY a3)
{
  int result; // eax
  CUwfStaticConfiguration *v5; // rcx
  HKEY v6; // r8
  CUwfStaticConfiguration *v7; // rcx
  HKEY v8; // r8
  CUwfStaticConfiguration *v9; // rcx
  HKEY v10; // r8

  result = CUwfStaticConfiguration::SetRegDwordValueAndCommit(
             this,
             L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
             a3,
             L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
             L"NoAutoUpdate",
             a2,
             1u);
  if ( result >= 0 )
  {
    result = CUwfStaticConfiguration::SetRegDwordValueAndCommit(
               v5,
               L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\WindowsStore",
               v6,
               L"SOFTWARE\\Policies\\Microsoft\\WindowsStore",
               L"AutoDownload",
               a2,
               2u);
    if ( result >= 0 )
    {
      result = CUwfStaticConfiguration::SetRegDwordValueAndCommit(
                 v7,
                 L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Configuration Manager",
                 v8,
                 L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Configuration Manager",
                 L"RegistryReorganizationLimitDays",
                 a2,
                 0xFFFFFFFF);
      if ( result >= 0 )
        return CUwfStaticConfiguration::SetRegDwordValueAndCommit(
                 v9,
                 L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                 v10,
                 L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                 L"MaintenanceDisabled",
                 a2,
                 1u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009688  push    rbx
0x18000968a  sub     rsp, 40h
0x18000968e  mov     [rsp+48h+var_18], 1; unsigned int
0x180009696  lea     rax, aNoautoupdate; "NoAutoUpdate"
0x18000969d  mov     [rsp+48h+var_20], edx; unsigned int
0x1800096a1  lea     r9, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800096a8  mov     ebx, edx
0x1800096aa  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800096af  lea     rdx, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies"...
0x1800096b6  call    ?SetRegDwordValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00KK@Z; CUwfStaticConfiguration::SetRegDwordValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x1800096bb  test    eax, eax
0x1800096bd  js      loc_18000974C
0x1800096c3  mov     [rsp+48h+var_18], 2; unsigned int
0x1800096cb  lea     rax, aAutodownload; "AutoDownload"
0x1800096d2  mov     [rsp+48h+var_20], ebx; unsigned int
0x1800096d6  lea     r9, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\WindowsS"...
0x1800096dd  lea     rdx, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies"...
0x1800096e4  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800096e9  call    ?SetRegDwordValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00KK@Z; CUwfStaticConfiguration::SetRegDwordValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x1800096ee  test    eax, eax
0x1800096f0  js      short loc_18000974C
0x1800096f2  mov     [rsp+48h+var_18], 0FFFFFFFFh; unsigned int
0x1800096fa  lea     rax, aRegistryreorga; "RegistryReorganizationLimitDays"
0x180009701  mov     [rsp+48h+var_20], ebx; unsigned int
0x180009705  lea     r9, aSystemCurrentc_11; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x18000970c  lea     rdx, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x180009713  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180009718  call    ?SetRegDwordValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00KK@Z; CUwfStaticConfiguration::SetRegDwordValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x18000971d  test    eax, eax
0x18000971f  js      short loc_18000974C
0x180009721  mov     [rsp+48h+var_18], 1; unsigned int
0x180009729  lea     rax, aMaintenancedis; "MaintenanceDisabled"
0x180009730  mov     [rsp+48h+var_20], ebx; unsigned int
0x180009734  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000973b  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180009742  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180009747  call    ?SetRegDwordValueAndCommit@CUwfStaticConfiguration@@AEAAJPEBGPEAUHKEY__@@00KK@Z; CUwfStaticConfiguration::SetRegDwordValueAndCommit(ushort const *,HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x18000974c  add     rsp, 40h
0x180009750  pop     rbx
0x180009751  retn
```
