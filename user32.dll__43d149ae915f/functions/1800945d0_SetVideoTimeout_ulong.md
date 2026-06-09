# SetVideoTimeout(ulong)

- ea: `0x1800945d0`
- end: `0x180094664`
- name: `?SetVideoTimeout@@YAHK@Z`
- size: `148`
- prototype: `__int64 __fastcall(DWORD DcValueIndex)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180048ca0`
- `0x18004d5d0`

## callees

- `0x1800945d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094656`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094656`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x18009463f`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x18009463f`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18009462e`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18009462e`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800945e8`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800945e8`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18009460b`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18009460b`

## pseudocode

```c
_BOOL8 __fastcall SetVideoTimeout(DWORD DcValueIndex)
{
  DWORD ActiveScheme; // eax
  BOOL v3; // ebx
  GUID *ActivePolicyGuid; // [rsp+48h] [rbp+10h] BYREF

  ActivePolicyGuid = 0;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  if ( !ActiveScheme )
  {
    ActiveScheme = PowerWriteACValueIndex(
                     0,
                     ActivePolicyGuid,
                     &GUID_VIDEO_SUBGROUP,
                     &GUID_VIDEO_POWERDOWN_TIMEOUT,
                     DcValueIndex);
    if ( !ActiveScheme )
    {
      ActiveScheme = PowerWriteDCValueIndex(
                       0,
                       ActivePolicyGuid,
                       &GUID_VIDEO_SUBGROUP,
                       &GUID_VIDEO_POWERDOWN_TIMEOUT,
                       DcValueIndex);
      if ( !ActiveScheme )
        ActiveScheme = PowerSetActiveScheme(0, ActivePolicyGuid);
    }
  }
  v3 = ActiveScheme == 0;
  if ( ActivePolicyGuid )
    LocalFree(ActivePolicyGuid);
  return v3;
}

```

## disassembly

```asm
0x1800945d0  push    rbx
0x1800945d2  sub     rsp, 30h
0x1800945d6  mov     ebx, ecx
0x1800945d8  mov     [rsp+38h+ActivePolicyGuid], 0
0x1800945e1  xor     ecx, ecx; UserRootPowerKey
0x1800945e3  lea     rdx, [rsp+38h+ActivePolicyGuid]; ActivePolicyGuid
0x1800945e8  call    cs:__imp_PowerGetActiveScheme
0x1800945ee  test    eax, eax
0x1800945f0  jnz     short loc_180094645
0x1800945f2  mov     rdx, [rsp+38h+ActivePolicyGuid]; SchemeGuid
0x1800945f7  lea     r9, GUID_VIDEO_POWERDOWN_TIMEOUT; PowerSettingGuid
0x1800945fe  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180094605  mov     [rsp+38h+AcValueIndex], ebx; AcValueIndex
0x180094609  xor     ecx, ecx; RootPowerKey
0x18009460b  call    cs:__imp_PowerWriteACValueIndex
0x180094611  test    eax, eax
0x180094613  jnz     short loc_180094645
0x180094615  mov     rdx, [rsp+38h+ActivePolicyGuid]; SchemeGuid
0x18009461a  lea     r9, GUID_VIDEO_POWERDOWN_TIMEOUT; PowerSettingGuid
0x180094621  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180094628  mov     [rsp+38h+AcValueIndex], ebx; DcValueIndex
0x18009462c  xor     ecx, ecx; RootPowerKey
0x18009462e  call    cs:__imp_PowerWriteDCValueIndex
0x180094634  test    eax, eax
0x180094636  jnz     short loc_180094645
0x180094638  mov     rdx, [rsp+38h+ActivePolicyGuid]; SchemeGuid
0x18009463d  xor     ecx, ecx; UserRootPowerKey
0x18009463f  call    cs:__imp_PowerSetActiveScheme
0x180094645  mov     rcx, [rsp+38h+ActivePolicyGuid]; hMem
0x18009464a  xor     ebx, ebx
0x18009464c  test    eax, eax
0x18009464e  setz    bl
0x180094651  test    rcx, rcx
0x180094654  jz      short loc_18009465C
0x180094656  call    cs:__imp_LocalFree
0x18009465c  mov     eax, ebx
0x18009465e  add     rsp, 30h
0x180094662  pop     rbx
0x180094663  retn
```
