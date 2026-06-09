# CPasswordOnWakeSetting::IsRestrictedByGroupPolicy(_GUID *,int,int *)

- ea: `0x18002ba00`
- end: `0x18002ba73`
- name: `?IsRestrictedByGroupPolicy@CPasswordOnWakeSetting@@UEAAJPEAU_GUID@@HPEAH@Z`
- size: `115`
- prototype: `__int64 __fastcall(CPasswordOnWakeSetting *__hidden this, struct _GUID *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18002ba00`

## import_xrefs

- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba1c`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba2b`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba3e`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba56`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba1c`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba2b`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba3e`
- `POWRPROF!PowerSettingAccessCheck` at `0x18002ba56`

## pseudocode

```c
__int64 __fastcall CPasswordOnWakeSetting::IsRestrictedByGroupPolicy(
        CPasswordOnWakeSetting *this,
        struct _GUID *a2,
        int a3,
        int *a4)
{
  *a4 = 1;
  if ( !PowerSettingAccessCheck(ACCESS_SCHEME, a2)
    && !PowerSettingAccessCheck(ACCESS_ACTIVE_SCHEME, 0)
    && !PowerSettingAccessCheck(ACCESS_AC_POWER_SETTING_INDEX, &GUID_LOCK_CONSOLE_ON_WAKE)
    && (!a3 || !PowerSettingAccessCheck(ACCESS_DC_POWER_SETTING_INDEX, &GUID_LOCK_CONSOLE_ON_WAKE)) )
  {
    *a4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002ba00  mov     [rsp+arg_0], rbx
0x18002ba05  push    rdi
0x18002ba06  sub     rsp, 20h
0x18002ba0a  mov     ecx, 10h; AccessFlags
0x18002ba0f  mov     dword ptr [r9], 1
0x18002ba16  mov     rbx, r9
0x18002ba19  mov     edi, r8d
0x18002ba1c  call    cs:__imp_PowerSettingAccessCheck
0x18002ba22  test    eax, eax
0x18002ba24  jnz     short loc_18002BA66
0x18002ba26  xor     edx, edx; PowerGuid
0x18002ba28  lea     ecx, [rax+13h]; AccessFlags
0x18002ba2b  call    cs:__imp_PowerSettingAccessCheck
0x18002ba31  test    eax, eax
0x18002ba33  jnz     short loc_18002BA66
0x18002ba35  lea     rdx, GUID_LOCK_CONSOLE_ON_WAKE; PowerGuid
0x18002ba3c  xor     ecx, ecx; AccessFlags
0x18002ba3e  call    cs:__imp_PowerSettingAccessCheck
0x18002ba44  test    eax, eax
0x18002ba46  jnz     short loc_18002BA66
0x18002ba48  test    edi, edi
0x18002ba4a  jz      short loc_18002BA60
0x18002ba4c  lea     rdx, GUID_LOCK_CONSOLE_ON_WAKE; PowerGuid
0x18002ba53  lea     ecx, [rax+1]; AccessFlags
0x18002ba56  call    cs:__imp_PowerSettingAccessCheck
0x18002ba5c  test    eax, eax
0x18002ba5e  jnz     short loc_18002BA66
0x18002ba60  mov     dword ptr [rbx], 0
0x18002ba66  mov     rbx, [rsp+28h+arg_0]
0x18002ba6b  xor     eax, eax
0x18002ba6d  add     rsp, 20h
0x18002ba71  pop     rdi
0x18002ba72  retn
```
