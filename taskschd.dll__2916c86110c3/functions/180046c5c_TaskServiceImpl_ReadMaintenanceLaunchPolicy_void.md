# TaskServiceImpl::ReadMaintenanceLaunchPolicy(void)

- ea: `0x180046c5c`
- end: `0x180046d73`
- name: `?ReadMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJXZ`
- size: `279`
- prototype: `__int64 __fastcall(TaskServiceImpl *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046700`
- `0x180046e70`
- `0x180047520`
- `0x180047670`
- `0x1800477c0`
- `0x1800478b0`
- `0x180047940`
- `0x1800479d0`

## callees

- `0x180039ab0`
- `0x180046c5c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046d63`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180046cbf`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180046cbf`
- `POWRPROF!PowerReadACValueIndex` at `0x180046cfa`
- `POWRPROF!PowerReadACValueIndex` at `0x180046cfa`
- `POWRPROF!PowerReadDCValueIndex` at `0x180046d21`
- `POWRPROF!PowerReadDCValueIndex` at `0x180046d21`

## string_xrefs

- `0x180046c86`: `SOFTWARE\Policies\Microsoft\Windows\Task Scheduler\Maintenance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskServiceImpl::ReadMaintenanceLaunchPolicy(TaskServiceImpl *this)
{
  signed int MaintenanceLaunchPolicy; // ebx
  TaskServiceImpl *v3; // rcx
  signed int ActiveScheme; // eax
  bool v5; // cc
  bool v6; // al
  GUID *v7; // rcx
  DWORD AcValueIndex; // [rsp+50h] [rbp+20h] BYREF
  DWORD DcValueIndex; // [rsp+58h] [rbp+28h] BYREF
  GUID *ActivePolicyGuid; // [rsp+60h] [rbp+30h] BYREF

  MaintenanceLaunchPolicy = 0;
  ActivePolicyGuid = 0;
  AcValueIndex = 0;
  DcValueIndex = 0;
  if ( !*((_BYTE *)this + 232) )
  {
    MaintenanceLaunchPolicy = TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(
                                this,
                                (TaskServiceImpl *)((char *)this + 88),
                                L"SOFTWARE\\Policies\\Microsoft\\Windows\\Task Scheduler\\Maintenance");
    if ( MaintenanceLaunchPolicy >= 0 )
    {
      MaintenanceLaunchPolicy = TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(
                                  v3,
                                  (TaskServiceImpl *)((char *)this + 160),
                                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance");
      if ( MaintenanceLaunchPolicy >= 0 )
      {
        ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
        v5 = ActiveScheme <= 0;
        if ( ActiveScheme
          || (ActiveScheme = PowerReadACValueIndex(
                               0,
                               ActivePolicyGuid,
                               &GUID_SLEEP_SUBGROUP,
                               &GUID_ALLOW_RTC_WAKE,
                               &AcValueIndex),
              v5 = ActiveScheme <= 0,
              ActiveScheme)
          || (ActiveScheme = PowerReadDCValueIndex(
                               0,
                               ActivePolicyGuid,
                               &GUID_SLEEP_SUBGROUP,
                               &GUID_ALLOW_RTC_WAKE,
                               &DcValueIndex),
              v5 = ActiveScheme <= 0,
              ActiveScheme) )
        {
          if ( v5 )
            MaintenanceLaunchPolicy = ActiveScheme;
          else
            MaintenanceLaunchPolicy = (unsigned __int16)ActiveScheme | 0x80070000;
        }
        else
        {
          v6 = AcValueIndex && DcValueIndex;
          v7 = ActivePolicyGuid;
          *((_BYTE *)this + 234) = v6;
          LocalFree(v7);
          ActivePolicyGuid = 0;
          *((_BYTE *)this + 232) = 1;
        }
      }
    }
    if ( ActivePolicyGuid )
      LocalFree(ActivePolicyGuid);
  }
  return (unsigned int)MaintenanceLaunchPolicy;
}

```

## disassembly

```asm
0x180046c5c  push    rbp
0x180046c5e  push    rbx
0x180046c5f  push    rdi
0x180046c60  mov     rbp, rsp
0x180046c63  sub     rsp, 30h
0x180046c67  xor     ebx, ebx
0x180046c69  mov     rdi, rcx
0x180046c6c  mov     [rbp+ActivePolicyGuid], rbx
0x180046c70  mov     [rbp+arg_0], ebx
0x180046c73  mov     [rbp+DcValueIndex], ebx
0x180046c76  cmp     [rcx+0E8h], bl
0x180046c7c  jnz     loc_180046D69
0x180046c82  lea     rdx, [rcx+58h]; struct TaskServiceImpl::_MAINTENANCE_POLICY *
0x180046c86  lea     r8, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180046c8d  call    ?RetrieveMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z; TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)
0x180046c92  mov     ebx, eax
0x180046c94  test    eax, eax
0x180046c96  js      loc_180046D5A
0x180046c9c  lea     rdx, [rdi+0A0h]; struct TaskServiceImpl::_MAINTENANCE_POLICY *
0x180046ca3  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180046caa  call    ?RetrieveMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z; TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)
0x180046caf  mov     ebx, eax
0x180046cb1  test    eax, eax
0x180046cb3  js      loc_180046D5A
0x180046cb9  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x180046cbd  xor     ecx, ecx; UserRootPowerKey
0x180046cbf  call    cs:__imp_PowerGetActiveScheme
0x180046cc5  test    eax, eax
0x180046cc7  jz      short loc_180046CDD
0x180046cc9  jg      short loc_180046CD2
0x180046ccb  mov     ebx, eax
0x180046ccd  jmp     loc_180046D5A
0x180046cd2  movzx   ebx, ax
0x180046cd5  or      ebx, 80070000h
0x180046cdb  jmp     short loc_180046D5A
0x180046cdd  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x180046ce1  lea     rax, [rbp+arg_0]
0x180046ce5  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180046cec  mov     [rsp+30h+AcValueIndex], rax; AcValueIndex
0x180046cf1  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180046cf8  xor     ecx, ecx; RootPowerKey
0x180046cfa  call    cs:__imp_PowerReadACValueIndex
0x180046d00  test    eax, eax
0x180046d02  jnz     short loc_180046CC9
0x180046d04  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x180046d08  lea     rax, [rbp+DcValueIndex]
0x180046d0c  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x180046d13  mov     [rsp+30h+AcValueIndex], rax; DcValueIndex
0x180046d18  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180046d1f  xor     ecx, ecx; RootPowerKey
0x180046d21  call    cs:__imp_PowerReadDCValueIndex
0x180046d27  test    eax, eax
0x180046d29  jnz     short loc_180046CC9
0x180046d2b  cmp     [rbp+arg_0], eax
0x180046d2e  jz      short loc_180046D39
0x180046d30  cmp     [rbp+DcValueIndex], eax
0x180046d33  jz      short loc_180046D39
0x180046d35  mov     al, 1
0x180046d37  jmp     short loc_180046D3B
0x180046d39  xor     eax, eax
0x180046d3b  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x180046d3f  mov     [rdi+0EAh], al
0x180046d45  call    cs:__imp_LocalFree
0x180046d4b  mov     [rbp+ActivePolicyGuid], 0
0x180046d53  mov     byte ptr [rdi+0E8h], 1
0x180046d5a  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x180046d5e  test    rcx, rcx
0x180046d61  jz      short loc_180046D69
0x180046d63  call    cs:__imp_LocalFree
0x180046d69  mov     eax, ebx
0x180046d6b  add     rsp, 30h
0x180046d6f  pop     rdi
0x180046d70  pop     rbx
0x180046d71  pop     rbp
0x180046d72  retn
```
