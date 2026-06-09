# CPasswordOnWakeSetting::UpdateSetting(int,int)

- ea: `0x18002bf30`
- end: `0x18002bffe`
- name: `?UpdateSetting@CPasswordOnWakeSetting@@UEAAJHH@Z`
- size: `206`
- prototype: `__int64 __fastcall(CPasswordOnWakeSetting *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18002bf30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfed`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002bfc2`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002bfc2`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002bf8c`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002bf8c`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x18002bfe2`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x18002bfe2`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18002bf4e`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18002bf4e`

## pseudocode

```c
__int64 __fastcall CPasswordOnWakeSetting::UpdateSetting(CPasswordOnWakeSetting *this, int a2, int a3)
{
  signed int ActiveScheme; // eax
  signed int v6; // ebx
  signed int v7; // eax
  signed int v8; // eax
  GUID *ActivePolicyGuid; // [rsp+78h] [rbp+20h] BYREF

  ActivePolicyGuid = 0;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  v6 = ActiveScheme;
  if ( ActiveScheme > 0 )
    v6 = (unsigned __int16)ActiveScheme | 0x80070000;
  if ( v6 >= 0 )
  {
    v7 = PowerWriteACValueIndex(0, ActivePolicyGuid, &NO_SUBGROUP_GUID, &GUID_LOCK_CONSOLE_ON_WAKE, a2 != 0);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
      if ( !a3 )
        goto LABEL_11;
      v8 = PowerWriteDCValueIndex(0, ActivePolicyGuid, &NO_SUBGROUP_GUID, &GUID_LOCK_CONSOLE_ON_WAKE, a2 != 0);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
LABEL_11:
        PowerSetActiveScheme(0, ActivePolicyGuid);
    }
    LocalFree(ActivePolicyGuid);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002bf30  push    rbx
0x18002bf32  push    rbp
0x18002bf33  push    rsi
0x18002bf34  push    rdi
0x18002bf35  sub     rsp, 38h
0x18002bf39  mov     ebp, edx
0x18002bf3b  mov     [rsp+58h+ActivePolicyGuid], 0
0x18002bf44  lea     rdx, [rsp+58h+ActivePolicyGuid]; ActivePolicyGuid
0x18002bf49  xor     ecx, ecx; UserRootPowerKey
0x18002bf4b  mov     esi, r8d
0x18002bf4e  call    cs:__imp_PowerGetActiveScheme
0x18002bf54  mov     ebx, eax
0x18002bf56  test    eax, eax
0x18002bf58  jle     short loc_18002BF63
0x18002bf5a  movzx   ebx, ax
0x18002bf5d  or      ebx, 80070000h
0x18002bf63  test    ebx, ebx
0x18002bf65  js      loc_18002BFF3
0x18002bf6b  mov     rdx, [rsp+58h+ActivePolicyGuid]; SchemeGuid
0x18002bf70  lea     r9, GUID_LOCK_CONSOLE_ON_WAKE; PowerSettingGuid
0x18002bf77  xor     edi, edi
0x18002bf79  lea     r8, NO_SUBGROUP_GUID; SubGroupOfPowerSettingsGuid
0x18002bf80  test    ebp, ebp
0x18002bf82  setnz   dil
0x18002bf86  xor     ecx, ecx; RootPowerKey
0x18002bf88  mov     [rsp+58h+AcValueIndex], edi; AcValueIndex
0x18002bf8c  call    cs:__imp_PowerWriteACValueIndex
0x18002bf92  mov     ebx, eax
0x18002bf94  test    eax, eax
0x18002bf96  jle     short loc_18002BFA1
0x18002bf98  movzx   ebx, ax
0x18002bf9b  or      ebx, 80070000h
0x18002bfa1  test    ebx, ebx
0x18002bfa3  js      short loc_18002BFE8
0x18002bfa5  test    esi, esi
0x18002bfa7  jz      short loc_18002BFDB
0x18002bfa9  mov     rdx, [rsp+58h+ActivePolicyGuid]; SchemeGuid
0x18002bfae  lea     r9, GUID_LOCK_CONSOLE_ON_WAKE; PowerSettingGuid
0x18002bfb5  lea     r8, NO_SUBGROUP_GUID; SubGroupOfPowerSettingsGuid
0x18002bfbc  mov     [rsp+58h+AcValueIndex], edi; DcValueIndex
0x18002bfc0  xor     ecx, ecx; RootPowerKey
0x18002bfc2  call    cs:__imp_PowerWriteDCValueIndex
0x18002bfc8  mov     ebx, eax
0x18002bfca  test    eax, eax
0x18002bfcc  jle     short loc_18002BFD7
0x18002bfce  movzx   ebx, ax
0x18002bfd1  or      ebx, 80070000h
0x18002bfd7  test    ebx, ebx
0x18002bfd9  js      short loc_18002BFE8
0x18002bfdb  mov     rdx, [rsp+58h+ActivePolicyGuid]; SchemeGuid
0x18002bfe0  xor     ecx, ecx; UserRootPowerKey
0x18002bfe2  call    cs:__imp_PowerSetActiveScheme
0x18002bfe8  mov     rcx, [rsp+58h+ActivePolicyGuid]; hMem
0x18002bfed  call    cs:__imp_LocalFree
0x18002bff3  mov     eax, ebx
0x18002bff5  add     rsp, 38h
0x18002bff9  pop     rdi
0x18002bffa  pop     rsi
0x18002bffb  pop     rbp
0x18002bffc  pop     rbx
0x18002bffd  retn
```
