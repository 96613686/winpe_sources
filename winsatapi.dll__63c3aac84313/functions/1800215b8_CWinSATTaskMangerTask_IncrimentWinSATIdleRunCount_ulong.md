# CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(ulong &)

- ea: `0x1800215b8`
- end: `0x18002165a`
- name: `?IncrimentWinSATIdleRunCount@CWinSATTaskMangerTask@@AEAA_NAEAK@Z`
- size: `162`
- prototype: `bool __fastcall(CWinSATTaskMangerTask *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020428`

## callees

- `0x18001c414`
- `0x1800214fc`
- `0x1800215b8`
- `0x18002bbb8`

## string_xrefs

- `0x180021639`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x18002162f`: `Cannot incriment %s in the registry`

## pseudocode

```c
bool __fastcall CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(CWinSATTaskMangerTask *this, unsigned int *a2)
{
  DWORD v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rcx
  DWORD v6; // eax
  bool v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = RegHelper::IncrimentDWORDValue(this, L"IdleWinSATRunCount", a2);
  v4 = v3;
  if ( v3 )
  {
    Record_Win32Error_w(
      "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
      222,
      v3,
      L"Cannot incriment %s in the registry",
      L"IdleWinSATRunCount");
  }
  else
  {
    v8 = 0;
    if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v8) )
    {
      if ( v8 )
      {
        v6 = RegHelper::IncrimentDWORDValue(v5, L"IdleWinSATRunAfterCount", &v8);
        v4 = v6;
        if ( v6 )
          Record_Win32Error_w(
            "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
            236,
            v6,
            L"Cannot incriment %s in the registry",
            L"IdleWinSATRunAfterCount");
      }
    }
  }
  return v4 == 0;
}

```

## disassembly

```asm
0x1800215b8  mov     [rsp+arg_0], rbx
0x1800215bd  mov     [rsp+arg_8], rsi
0x1800215c2  push    rdi
0x1800215c3  sub     rsp, 30h
0x1800215c7  mov     r8, rdx
0x1800215ca  lea     rsi, aIdlewinsatrunc; "IdleWinSATRunCount"
0x1800215d1  mov     rdx, rsi
0x1800215d4  mov     rdi, rcx
0x1800215d7  call    ?IncrimentDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAK@Z; RegHelper::IncrimentDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &)
0x1800215dc  mov     ebx, eax
0x1800215de  test    eax, eax
0x1800215e0  jz      short loc_1800215EE
0x1800215e2  mov     qword ptr [rsp+38h+var_18], rsi
0x1800215e7  mov     edx, 0DEh
0x1800215ec  jmp     short loc_18002162F
0x1800215ee  lea     rdx, [rsp+38h+arg_10]; bool *
0x1800215f3  mov     [rsp+38h+arg_10], 0
0x1800215f8  mov     rcx, rdi; this
0x1800215fb  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x180021600  test    al, al
0x180021602  jz      short loc_180021645
0x180021604  cmp     [rsp+38h+arg_10], 0
0x180021609  jz      short loc_180021645
0x18002160b  lea     rdi, aIdlewinsatruna; "IdleWinSATRunAfterCount"
0x180021612  mov     rdx, rdi
0x180021615  lea     r8, [rsp+38h+arg_10]
0x18002161a  call    ?IncrimentDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAK@Z; RegHelper::IncrimentDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &)
0x18002161f  mov     ebx, eax
0x180021621  test    eax, eax
0x180021623  jz      short loc_180021645
0x180021625  mov     qword ptr [rsp+38h+var_18], rdi; char
0x18002162a  mov     edx, 0ECh
0x18002162f  lea     r9, aCannotIncrimen; "Cannot incriment %s in the registry"
0x180021636  mov     r8d, eax
0x180021639  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021640  call    Record_Win32Error_w
0x180021645  mov     rsi, [rsp+38h+arg_8]
0x18002164a  test    ebx, ebx
0x18002164c  mov     rbx, [rsp+38h+arg_0]
0x180021651  setz    al
0x180021654  add     rsp, 30h
0x180021658  pop     rdi
0x180021659  retn
```
