# DisableAutoDumpSetting

- ea: `0x140005cec`
- end: `0x140005e27`
- name: `DisableAutoDumpSetting`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140004e18`

## callees

- `0x140005cec`
- `0x140008c40`
- `0x14000daa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140005d2a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140005d2a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140005d58`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140005dc1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140005d58`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140005dc1`

## string_xrefs

- `0x140005d88`: `Failed to delete PreviousTelemetryMode KeyValue`
- `0x140005ddc`: `Failed to delete PreviousRing KeyValue`

## pseudocode

```c
LSTATUS DisableAutoDumpSetting()
{
  LSTATUS result; // eax
  int v1; // ebx
  int v2; // eax
  wil::details *lpData; // [rsp+20h] [rbp-18h]
  const char *v4; // [rsp+30h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+38h] [rbp+0h]
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  result = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"ChangeDumpTypeByTelemetryLevel",
             4u,
             &v6,
             4u);
  if ( !result )
  {
    v1 = RegDeleteKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\Windows Error Reporting",
           L"PreviousTelemetryMode");
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl'::`2'::impl) )
    {
      if ( v1 )
      {
        if ( v1 > 0 )
          v1 = (unsigned __int16)v1 | 0x80070000;
        LODWORD(lpData) = v1;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x5EF,
          (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
          "DisableAutoDumpSetting",
          lpData,
          (int)"Failed to delete PreviousTelemetryMode KeyValue",
          v4);
      }
      v2 = RegDeleteKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"PreviousRing");
      v1 = v2;
      if ( v2 )
      {
        if ( v2 > 0 )
          v2 = (unsigned __int16)v2 | 0x80070000;
        LODWORD(lpData) = v2;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x5F9,
          (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
          "DisableAutoDumpSetting",
          lpData,
          (int)"Failed to delete PreviousRing KeyValue",
          v4);
      }
    }
    else if ( v1 == 2 )
    {
      return 0;
    }
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
    return v1;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140005cec  mov     rax, rsp
0x140005cef  mov     [rax+10h], rbx
0x140005cf3  push    rbp; char *
0x140005cf4  sub     rsp, 30h
0x140005cf8  mov     r9d, 4; dwType
0x140005cfe  mov     dword ptr [rax+8], 0
0x140005d05  mov     [rax-10h], r9d
0x140005d09  lea     rax, [rax+8]
0x140005d0d  mov     rbp, 0FFFFFFFF80000002h
0x140005d14  mov     [rsp+38h+lpData], rax; lpData
0x140005d19  lea     r8, Value; "ChangeDumpTypeByTelemetryLevel"
0x140005d20  mov     rcx, rbp; hKey
0x140005d23  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140005d2a  call    cs:__imp_RegSetKeyValueW
0x140005d30  test    eax, eax
0x140005d32  jz      short loc_140005D47
0x140005d34  jle     loc_140005E13
0x140005d3a  movzx   eax, ax
0x140005d3d  or      eax, 80070000h
0x140005d42  jmp     loc_140005E13
0x140005d47  lea     r8, ValueName; "PreviousTelemetryMode"
0x140005d4e  mov     rcx, rbp; hKey
0x140005d51  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140005d58  call    cs:__imp_RegDeleteKeyValueW
0x140005d5e  mov     ebx, eax
0x140005d60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange> `wil::Feature<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetImpl(void)'::`2'::impl
0x140005d67  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(void)
0x140005d6c  test    al, al
0x140005d6e  jz      loc_140005E1E
0x140005d74  test    ebx, ebx
0x140005d76  jz      short loc_140005DB0
0x140005d78  jle     short loc_140005D83
0x140005d7a  movzx   ebx, bx
0x140005d7d  or      ebx, 80070000h
0x140005d83  mov     rcx, [rsp+38h]; this
0x140005d88  lea     rax, aFailedToDelete; "Failed to delete PreviousTelemetryMode "...
0x140005d8f  mov     qword ptr [rsp+38h+var_10], rax; int
0x140005d94  lea     r9, aDisableautodum; "DisableAutoDumpSetting"
0x140005d9b  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005da2  mov     dword ptr [rsp+38h+lpData], ebx; wil::details *
0x140005da6  mov     edx, 5EFh; void *
0x140005dab  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005db0  lea     r8, aPreviousring; "PreviousRing"
0x140005db7  mov     rcx, rbp; hKey
0x140005dba  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x140005dc1  call    cs:__imp_RegDeleteKeyValueW
0x140005dc7  mov     ebx, eax
0x140005dc9  test    eax, eax
0x140005dcb  jz      short loc_140005E04
0x140005dcd  jle     short loc_140005DD7
0x140005dcf  movzx   eax, ax
0x140005dd2  or      eax, 80070000h
0x140005dd7  mov     rcx, [rsp+38h]; this
0x140005ddc  lea     rdx, aFailedToDelete_0; "Failed to delete PreviousRing KeyValue"
0x140005de3  mov     qword ptr [rsp+38h+var_10], rdx; int
0x140005de8  lea     r9, aDisableautodum; "DisableAutoDumpSetting"
0x140005def  mov     edx, 5F9h; void *
0x140005df4  mov     dword ptr [rsp+38h+lpData], eax; wil::details *
0x140005df8  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005dff  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005e04  test    ebx, ebx
0x140005e06  jle     short loc_140005E11
0x140005e08  movzx   ebx, bx
0x140005e0b  or      ebx, 80070000h
0x140005e11  mov     eax, ebx
0x140005e13  mov     rbx, [rsp+38h+arg_8]
0x140005e18  add     rsp, 30h
0x140005e1c  pop     rbp
0x140005e1d  retn
0x140005e1e  cmp     ebx, 2
0x140005e21  jnz     short loc_140005E04
0x140005e23  xor     ebx, ebx
0x140005e25  jmp     short loc_140005E11
```
