# CWallpaperCore::_OnPauseEnabled(bool)

- ea: `0x180042590`
- end: `0x1800426e7`
- name: `?_OnPauseEnabled@CWallpaperCore@@AEAAX_N@Z`
- size: `343`
- prototype: `void __fastcall(CWallpaperCore *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003c7dc`

## callees

- `0x180042590`
- `0x180043148`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426c6`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18004269a`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18004269a`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180042650`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18004267a`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x180042650`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18004267a`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800425b9`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800425b9`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x1800426ac`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x1800426ac`
- `POWRPROF!PowerReadDCValueIndex` at `0x1800425f6`
- `POWRPROF!PowerReadDCValueIndex` at `0x1800425f6`
- `POWRPROF!PowerReadACValueIndex` at `0x18004261f`
- `POWRPROF!PowerReadACValueIndex` at `0x18004261f`

## pseudocode

```c
void __fastcall CWallpaperCore::_OnPauseEnabled(CWallpaperCore *this, bool a2)
{
  GUID *ActivePolicyGuid; // [rsp+30h] [rbp-10h] BYREF
  DWORD AcValueIndex; // [rsp+70h] [rbp+30h] BYREF
  DWORD DcValueIndex; // [rsp+78h] [rbp+38h] BYREF

  ActivePolicyGuid = 0;
  if ( !PowerGetActiveScheme(0, &ActivePolicyGuid) )
  {
    AcValueIndex = 0;
    DcValueIndex = 0;
    if ( PowerReadDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, &DcValueIndex)
      || PowerReadACValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, &AcValueIndex) )
    {
      goto LABEL_13;
    }
    if ( AcValueIndex && DcValueIndex )
    {
      if ( !a2 )
      {
        PowerWriteDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 0);
        PowerWriteACValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 0);
        goto LABEL_12;
      }
    }
    else if ( !a2 )
    {
      PowerWriteDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 0);
LABEL_12:
      PowerSetActiveScheme(0, ActivePolicyGuid);
      CWallpaperCore::_SetPaused(this, a2);
LABEL_13:
      LocalFree(ActivePolicyGuid);
      return;
    }
    PowerWriteDCValueIndex(0, ActivePolicyGuid, &SubGroupOfPowerSettingsGuid, &PowerSettingGuid, 1u);
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180042590  mov     [rsp-18h+arg_0], rbx
0x180042595  mov     [rsp-18h+arg_8], rdi
0x18004259a  push    rbp
0x18004259b  push    r14
0x18004259d  push    r15
0x18004259f  mov     rbp, rsp
0x1800425a2  sub     rsp, 40h
0x1800425a6  mov     bl, dl
0x1800425a8  mov     [rbp+ActivePolicyGuid], 0
0x1800425b0  mov     rdi, rcx
0x1800425b3  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x1800425b7  xor     ecx, ecx; UserRootPowerKey
0x1800425b9  call    cs:__imp_PowerGetActiveScheme
0x1800425c0  nop     dword ptr [rax+rax+00h]
0x1800425c5  test    eax, eax
0x1800425c7  jnz     loc_1800426D2
0x1800425cd  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x1800425d1  lea     r14, PowerSettingGuid
0x1800425d8  mov     [rbp+AcValueIndex], eax
0x1800425db  lea     r15, SubGroupOfPowerSettingsGuid
0x1800425e2  mov     [rbp+arg_18], eax
0x1800425e5  mov     r9, r14; PowerSettingGuid
0x1800425e8  lea     rax, [rbp+arg_18]
0x1800425ec  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x1800425ef  xor     ecx, ecx; RootPowerKey
0x1800425f1  mov     [rsp+40h+DcValueIndex], rax; DcValueIndex
0x1800425f6  call    cs:__imp_PowerReadDCValueIndex
0x1800425fd  nop     dword ptr [rax+rax+00h]
0x180042602  test    eax, eax
0x180042604  jnz     loc_1800426C2
0x18004260a  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18004260e  lea     rax, [rbp+AcValueIndex]
0x180042612  mov     r9, r14; PowerSettingGuid
0x180042615  mov     [rsp+40h+DcValueIndex], rax; AcValueIndex
0x18004261a  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x18004261d  xor     ecx, ecx; RootPowerKey
0x18004261f  call    cs:__imp_PowerReadACValueIndex
0x180042626  nop     dword ptr [rax+rax+00h]
0x18004262b  test    eax, eax
0x18004262d  jnz     loc_1800426C2
0x180042633  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x180042637  xor     ecx, ecx; RootPowerKey
0x180042639  mov     r9, r14; PowerSettingGuid
0x18004263c  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x18004263f  cmp     [rbp+AcValueIndex], ecx
0x180042642  jnz     short loc_180042668
0x180042644  test    bl, bl
0x180042646  jz      short loc_18004265E
0x180042648  mov     dword ptr [rsp+40h+DcValueIndex], 1; DcValueIndex
0x180042650  call    cs:__imp_PowerWriteDCValueIndex
0x180042657  nop     dword ptr [rax+rax+00h]
0x18004265c  jmp     short loc_1800426A6
0x18004265e  mov     dword ptr [rsp+40h+DcValueIndex], 0
0x180042666  jmp     short loc_180042650
0x180042668  cmp     [rbp+arg_18], 0
0x18004266c  jz      short loc_180042644
0x18004266e  test    bl, bl
0x180042670  jnz     short loc_180042648
0x180042672  mov     dword ptr [rsp+40h+DcValueIndex], 0; DcValueIndex
0x18004267a  call    cs:__imp_PowerWriteDCValueIndex
0x180042681  nop     dword ptr [rax+rax+00h]
0x180042686  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x18004268a  mov     r9, r14; PowerSettingGuid
0x18004268d  mov     r8, r15; SubGroupOfPowerSettingsGuid
0x180042690  mov     dword ptr [rsp+40h+DcValueIndex], 0; AcValueIndex
0x180042698  xor     ecx, ecx; RootPowerKey
0x18004269a  call    cs:__imp_PowerWriteACValueIndex
0x1800426a1  nop     dword ptr [rax+rax+00h]
0x1800426a6  mov     rdx, [rbp+ActivePolicyGuid]; SchemeGuid
0x1800426aa  xor     ecx, ecx; UserRootPowerKey
0x1800426ac  call    cs:__imp_PowerSetActiveScheme
0x1800426b3  nop     dword ptr [rax+rax+00h]
0x1800426b8  mov     dl, bl; bool
0x1800426ba  mov     rcx, rdi; this
0x1800426bd  call    ?_SetPaused@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetPaused(bool)
0x1800426c2  mov     rcx, [rbp+ActivePolicyGuid]; hMem
0x1800426c6  call    cs:__imp_LocalFree
0x1800426cd  nop     dword ptr [rax+rax+00h]
0x1800426d2  mov     rbx, [rsp+40h+arg_0]
0x1800426d7  mov     rdi, [rsp+40h+arg_8]
0x1800426dc  add     rsp, 40h
0x1800426e0  pop     r15
0x1800426e2  pop     r14
0x1800426e4  pop     rbp
0x1800426e5  retn
```
