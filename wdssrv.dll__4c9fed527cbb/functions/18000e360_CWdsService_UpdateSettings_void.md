# CWdsService::UpdateSettings(void)

- ea: `0x18000e360`
- end: `0x18000e470`
- name: `?UpdateSettings@CWdsService@@AEAAKXZ`
- size: `272`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009da4`
- `0x18000ac40`
- `0x18000cc30`

## callees

- `0x180008158`
- `0x18000e360`
- `0x18000f0dc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000e398`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e398`
- `ADVAPI32!RegCloseKey` at `0x18000e456`
- `ADVAPI32!RegCloseKey` at `0x18000e456`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000e41b`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000e41b`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000e3d2`
- `WdsServerCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000e3d2`

## string_xrefs

- `0x18000e38a`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x18000e3c6`: `UpdateTime`
- `0x18000e408`: `Dynamic Update Timer: %u ms`

## pseudocode

```c
__int64 __fastcall CWdsService::UpdateSettings(CWdsService *this)
{
  __int64 ValueDwordWithDefault; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v10; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  hKey = 0;
  LODWORD(ValueDwordWithDefault) = RegOpenKeyExW(
                                     HKEY_LOCAL_MACHINE,
                                     L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                                     0,
                                     0x20119u,
                                     &hKey);
  if ( !(unsigned int)ElValidateWin32_0((unsigned int)ValueDwordWithDefault, v3, v4, 381) )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"UpdateTime", 0xDBBA0u, &v10);
    if ( !(unsigned int)ElValidateWin32_0(ValueDwordWithDefault, v5, v6, 388) )
    {
      v10 *= 1000;
      if ( v10 != *((_DWORD *)this + 16814) )
      {
        CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Dynamic Update Timer: %u ms");
        *((_DWORD *)this + 16814) = v10;
        LODWORD(ValueDwordWithDefault) = CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Change((char *)this + 67264);
        ElValidateWin32_0((unsigned int)ValueDwordWithDefault, v7, v8, 397);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ValueDwordWithDefault;
}

```

## disassembly

```asm
0x18000e360  mov     rax, rsp
0x18000e363  mov     [rax+8], rbx
0x18000e367  push    rdi
0x18000e368  sub     rsp, 30h
0x18000e36c  and     dword ptr [rax+10h], 0
0x18000e370  mov     rdi, rcx
0x18000e373  and     qword ptr [rax+18h], 0
0x18000e378  lea     rax, [rax+18h]
0x18000e37c  mov     r9d, 20119h; samDesired
0x18000e382  mov     [rsp+38h+phkResult], rax; phkResult
0x18000e387  xor     r8d, r8d; ulOptions
0x18000e38a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000e391  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e398  call    cs:__imp_RegOpenKeyExW
0x18000e39f  nop     dword ptr [rax+rax+00h]
0x18000e3a4  mov     ecx, eax
0x18000e3a6  mov     r9d, 17Dh
0x18000e3ac  mov     ebx, eax
0x18000e3ae  call    ElValidateWin32_0
0x18000e3b3  test    eax, eax
0x18000e3b5  jnz     loc_18000E44C
0x18000e3bb  lea     r9, [rsp+38h+arg_8]
0x18000e3c0  mov     r8d, 0DBBA0h
0x18000e3c6  lea     rdx, aUpdatetime; "UpdateTime"
0x18000e3cd  lea     rcx, [rsp+38h+hKey]
0x18000e3d2  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000e3d9  nop     dword ptr [rax+rax+00h]
0x18000e3de  mov     ecx, eax
0x18000e3e0  mov     r9d, 184h
0x18000e3e6  mov     ebx, eax
0x18000e3e8  call    ElValidateWin32_0
0x18000e3ed  test    eax, eax
0x18000e3ef  jnz     short loc_18000E44C
0x18000e3f1  imul    r9d, [rsp+38h+arg_8], 3E8h
0x18000e3fa  mov     [rsp+38h+arg_8], r9d
0x18000e3ff  cmp     r9d, [rdi+106B8h]
0x18000e406  jz      short loc_18000E44C
0x18000e408  lea     r8, aDynamicUpdateT; "Dynamic Update Timer: %u ms"
0x18000e40f  mov     edx, 20000h
0x18000e414  lea     rcx, qword_180039310
0x18000e41b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000e422  nop     dword ptr [rax+rax+00h]
0x18000e427  mov     edx, [rsp+38h+arg_8]
0x18000e42b  lea     rcx, [rdi+106C0h]
0x18000e432  mov     [rdi+106B8h], edx
0x18000e438  call    ?Change@?$CTimer@V?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@@@QEAAKKK@Z; CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Change(ulong,ulong)
0x18000e43d  mov     r9d, 18Dh
0x18000e443  mov     ecx, eax
0x18000e445  mov     ebx, eax
0x18000e447  call    ElValidateWin32_0
0x18000e44c  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e451  test    rcx, rcx
0x18000e454  jz      short loc_18000E462
0x18000e456  call    cs:__imp_RegCloseKey
0x18000e45d  nop     dword ptr [rax+rax+00h]
0x18000e462  mov     eax, ebx
0x18000e464  mov     rbx, [rsp+38h+arg_0]
0x18000e469  add     rsp, 30h
0x18000e46d  pop     rdi
0x18000e46e  retn
```
