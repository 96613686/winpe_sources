# CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(void)

- ea: `0x1800213d0`
- end: `0x1800214f3`
- name: `?DoSuccesfulCompletionRegistryAndSQMWork@CWinSATTaskMangerTask@@AEAAXXZ`
- size: `291`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dcc`

## callees

- `0x18001c414`
- `0x1800213d0`
- `0x1800218c0`
- `0x18002bbb8`
- `0x18002bd2c`
- `0x18002bed4`

## import_xrefs

- `msvcrt!_time64` at `0x18002141c`
- `msvcrt!_time64` at `0x18002141c`

## string_xrefs

- `0x18002144a`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x1800214dc`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x1800213fe`: `Cannot incriment %s in the registry`
- `0x18002143b`: `Cannot save %s to the registry`
- `0x1800214c8`: `Cannot save %s to the registry`
- `0x180021488`: `Cannot read %s from the registry`
- `0x180021422`: `FirstIdleCompletionTimeDate`
- `0x1800213e0`: `IdleAssessmentCompletionCount`
- `0x1800214b5`: `FirstIdleAssessmentCompletionDuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWinSATTaskMangerTask::DoSuccesfulCompletionRegistryAndSQMWork(CWinSATTaskMangerTask *this)
{
  const wchar_t *v1; // rbx
  __time64_t v2; // rbx
  __int64 v3; // rcx
  CWinSATTaskMangerTask *v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  unsigned __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = HIDWORD(this);
  v1 = (const wchar_t *)L"IdleAssessmentCompletionCount";
  v6 = 0;
  if ( (unsigned int)RegHelper::IncrimentDWORDValue(this, L"IdleAssessmentCompletionCount", &v6) )
    goto LABEL_8;
  if ( v6 != 1 )
    return;
  v2 = _time64(0);
  if ( (unsigned int)RegHelper::WriteQWORDValue(v3, L"FirstIdleCompletionTimeDate", v2) )
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)L"FirstIdleCompletionTimeDate");
  v8 = 0;
  if ( (unsigned int)RegHelper::ReadQWORDValue(1, L"FirstIdleRunTimeDate", &v8) )
  {
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)L"FirstIdleRunTimeDate");
    return;
  }
  v6 = 0;
  CWinSATTaskMangerTask::SQMFirstCompletionDuration(v4, v8, v2, &v6);
  v1 = L"FirstIdleAssessmentCompletionDuration";
  if ( (unsigned int)RegHelper::WriteQWORDValue(v5, L"FirstIdleAssessmentCompletionDuration", v6) )
LABEL_8:
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)v1);
}

```

## disassembly

```asm
0x1800213d0  mov     rax, rsp
0x1800213d3  mov     [rax+18h], rbx
0x1800213d7  mov     [rax+8], rcx
0x1800213db  push    rsi
0x1800213dc  sub     rsp, 30h
0x1800213e0  lea     rbx, aIdleassessment; "IdleAssessmentCompletionCount"
0x1800213e7  mov     dword ptr [rax+8], 0
0x1800213ee  mov     rdx, rbx
0x1800213f1  lea     r8, [rax+8]
0x1800213f5  call    ?IncrimentDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAK@Z; RegHelper::IncrimentDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &)
0x1800213fa  test    eax, eax
0x1800213fc  jz      short loc_18002140F
0x1800213fe  lea     r9, aCannotIncrimen; "Cannot incriment %s in the registry"
0x180021405  mov     edx, 157h
0x18002140a  jmp     loc_1800214D4
0x18002140f  cmp     [rsp+38h+arg_0], 1
0x180021414  jnz     loc_1800214E8
0x18002141a  xor     ecx, ecx; Time
0x18002141c  call    cs:__imp__time64
0x180021422  lea     rsi, ValueName; "FirstIdleCompletionTimeDate"
0x180021429  mov     r8, rax
0x18002142c  mov     rdx, rsi
0x18002142f  mov     rbx, rax
0x180021432  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180021437  test    eax, eax
0x180021439  jz      short loc_18002145B
0x18002143b  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x180021442  mov     qword ptr [rsp+38h+var_18], rsi; char
0x180021447  mov     r8d, eax
0x18002144a  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021451  mov     edx, 168h
0x180021456  call    Record_Win32Error_w
0x18002145b  xor     r9d, r9d
0x18002145e  mov     [rsp+38h+arg_8], 0
0x180021467  lea     rsi, aFirstidlerunti; "FirstIdleRunTimeDate"
0x18002146e  lea     r8, [rsp+38h+arg_8]
0x180021473  mov     rdx, rsi
0x180021476  lea     ecx, [r9+1]
0x18002147a  call    ?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z; RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)
0x18002147f  test    eax, eax
0x180021481  jz      short loc_180021496
0x180021483  mov     qword ptr [rsp+38h+var_18], rsi
0x180021488  lea     r9, aCannotReadSFro; "Cannot read %s from the registry"
0x18002148f  mov     edx, 174h
0x180021494  jmp     short loc_1800214D9
0x180021496  mov     rdx, [rsp+38h+arg_8]; unsigned __int64
0x18002149b  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x1800214a0  mov     r8, rbx; unsigned __int64
0x1800214a3  mov     [rsp+38h+arg_0], 0
0x1800214ab  call    ?SQMFirstCompletionDuration@CWinSATTaskMangerTask@@AEAAX_K0AEAK@Z; CWinSATTaskMangerTask::SQMFirstCompletionDuration(unsigned __int64,unsigned __int64,ulong &)
0x1800214b0  mov     r8d, [rsp+38h+arg_0]
0x1800214b5  lea     rbx, aFirstidleasses; "FirstIdleAssessmentCompletionDuration"
0x1800214bc  mov     rdx, rbx
0x1800214bf  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x1800214c4  test    eax, eax
0x1800214c6  jz      short loc_1800214E8
0x1800214c8  lea     r9, aCannotSaveSToT; "Cannot save %s to the registry"
0x1800214cf  mov     edx, 181h
0x1800214d4  mov     qword ptr [rsp+38h+var_18], rbx; char
0x1800214d9  mov     r8d, eax
0x1800214dc  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800214e3  call    Record_Win32Error_w
0x1800214e8  mov     rbx, [rsp+38h+arg_10]
0x1800214ed  add     rsp, 30h
0x1800214f1  pop     rsi
0x1800214f2  retn
```
