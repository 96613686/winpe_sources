# TaskServiceImpl::ReadMaintenanceLaunchPolicy(void)

- ea: `0x18004a5ac`
- end: `0x18004a6e5`
- name: `?ReadMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(TaskServiceImpl *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049fa0`
- `0x18004a810`
- `0x18004af20`
- `0x18004b0a0`
- `0x18004b220`
- `0x18004b340`
- `0x18004b3e0`
- `0x18004b480`

## callees

- `0x18003cc50`
- `0x18004a5ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a6aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a6ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a6aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a6ce`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18004a60f`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18004a60f`
- `POWRPROF!PowerReadACValueIndex` at `0x18004a653`
- `POWRPROF!PowerReadACValueIndex` at `0x18004a653`
- `POWRPROF!PowerReadDCValueIndex` at `0x18004a680`
- `POWRPROF!PowerReadDCValueIndex` at `0x18004a680`

## string_xrefs

- `0x18004a5d6`: `SOFTWARE\Policies\Microsoft\Windows\Task Scheduler\Maintenance`

## pseudocode

```c
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
0x18004a5ac  push    rbp
0x18004a5ae  push    rbx
0x18004a5af  push    rdi
0x18004a5b0  mov     rbp, rsp
0x18004a5b3  sub     rsp, 30h
0x18004a5b7  xor     ebx, ebx
0x18004a5b9  mov     rdi, rcx
0x18004a5bc  mov     [rbp+ActivePolicyGuid], rbx
0x18004a5c0  mov     [rbp+arg_0], ebx
0x18004a5c3  mov     [rbp+DcValueIndex], ebx
0x18004a5c6  cmp     [rcx+0E8h], bl
0x18004a5cc  jnz     loc_18004A6DA
0x18004a5d2  lea     rdx, [rcx+58h]; struct TaskServiceImpl::_MAINTENANCE_POLICY *
0x18004a5d6  lea     r8, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18004a5dd  call    ?RetrieveMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z; TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)
0x18004a5e2  mov     ebx, eax
0x18004a5e4  test    eax, eax
0x18004a5e6  js      loc_18004A6C5
0x18004a5ec  lea     rdx, [rdi+0A0h]; struct TaskServiceImpl::_MAINTENANCE_POLICY *
0x18004a5f3  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004a5fa  call    ?RetrieveMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z; TaskServiceImpl::RetrieveMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)
0x18004a5ff  mov     ebx, eax
0x18004a601  test    eax, eax
0x18004a603  js      loc_18004A6C5
0x18004a609  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x18004a60d  xor     ecx, ecx; UserRootPowerKey
0x18004a60f  call    cs:__imp_PowerGetActiveScheme
0x18004a616  nop     dword ptr [rax+rax+00h]
0x18004a61b  test    eax, eax
0x18004a61d  jz      short loc_18004A636
0x18004a61f  jg      short loc_18004A628
0x18004a621  mov     ebx, eax
0x18004a623  jmp     loc_18004A6C5
0x18004a628  movzx   ebx, ax
0x18004a62b  or      ebx, 80070000h
0x18004a631  jmp     loc_18004A6C5
0x18004a636  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18004a63a  lea     rax, [rbp+arg_0]
0x18004a63e  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x18004a645  mov     [rsp+30h+AcValueIndex], rax; AcValueIndex
0x18004a64a  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18004a651  xor     ecx, ecx; RootPowerKey
0x18004a653  call    cs:__imp_PowerReadACValueIndex
0x18004a65a  nop     dword ptr [rax+rax+00h]
0x18004a65f  test    eax, eax
0x18004a661  jnz     short loc_18004A61F
0x18004a663  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18004a667  lea     rax, [rbp+DcValueIndex]
0x18004a66b  lea     r9, GUID_ALLOW_RTC_WAKE; PowerSettingGuid
0x18004a672  mov     [rsp+30h+AcValueIndex], rax; DcValueIndex
0x18004a677  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18004a67e  xor     ecx, ecx; RootPowerKey
0x18004a680  call    cs:__imp_PowerReadDCValueIndex
0x18004a687  nop     dword ptr [rax+rax+00h]
0x18004a68c  test    eax, eax
0x18004a68e  jnz     short loc_18004A61F
0x18004a690  cmp     [rbp+arg_0], eax
0x18004a693  jz      short loc_18004A69E
0x18004a695  cmp     [rbp+DcValueIndex], eax
0x18004a698  jz      short loc_18004A69E
0x18004a69a  mov     al, 1
0x18004a69c  jmp     short loc_18004A6A0
0x18004a69e  xor     eax, eax
0x18004a6a0  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x18004a6a4  mov     [rdi+0EAh], al
0x18004a6aa  call    cs:__imp_LocalFree
0x18004a6b1  nop     dword ptr [rax+rax+00h]
0x18004a6b6  mov     [rbp+ActivePolicyGuid], 0
0x18004a6be  mov     byte ptr [rdi+0E8h], 1
0x18004a6c5  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x18004a6c9  test    rcx, rcx
0x18004a6cc  jz      short loc_18004A6DA
0x18004a6ce  call    cs:__imp_LocalFree
0x18004a6d5  nop     dword ptr [rax+rax+00h]
0x18004a6da  mov     eax, ebx
0x18004a6dc  add     rsp, 30h
0x18004a6e0  pop     rdi
0x18004a6e1  pop     rbx
0x18004a6e2  pop     rbp
0x18004a6e3  retn
```
