# CErcLuaElevationHelper::DeleteMachineDisable(void)

- ea: `0x180002ff0`
- end: `0x1800030c1`
- name: `?DeleteMachineDisable@CErcLuaElevationHelper@@UEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a18`
- `0x180002ff0`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003025`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003054`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000306a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000306a`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::DeleteMachineDisable(CErcLuaElevationHelper *this)
{
  HKEY *phkResult; // rax
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting",
         0,
         0x20106u,
         phkResult);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 || (v2 = RegDeleteValueW(hKey, L"Disabled"), v3 = v2, v4 = v2 <= 0, v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2147467259;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147024894 )
  {
    return 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180002ff0  push    rbx
0x180002ff2  sub     rsp, 30h
0x180002ff6  lea     rcx, [rsp+38h+hKey]
0x180002ffb  mov     [rsp+38h+hKey], 0
0x180003004  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180003009  mov     r9d, 20106h; samDesired
0x18000300f  mov     [rsp+38h+phkResult], rax; phkResult
0x180003014  xor     r8d, r8d; ulOptions
0x180003017  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Windows E"...
0x18000301e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003025  call    cs:__imp_RegOpenKeyExW
0x18000302b  mov     ebx, eax
0x18000302d  test    eax, eax
0x18000302f  jz      short loc_180003048
0x180003031  jle     short loc_18000303C
0x180003033  movzx   ebx, ax
0x180003036  or      ebx, 80070000h
0x18000303c  test    ebx, ebx
0x18000303e  mov     eax, 80004005h
0x180003043  cmovns  ebx, eax
0x180003046  jmp     short loc_180003060
0x180003048  mov     rcx, [rsp+38h+hKey]; hKey
0x18000304d  lea     rdx, ValueName; "Disabled"
0x180003054  call    cs:__imp_RegDeleteValueW
0x18000305a  mov     ebx, eax
0x18000305c  test    eax, eax
0x18000305e  jnz     short loc_180003031
0x180003060  mov     rcx, [rsp+38h+hKey]; hKey
0x180003065  test    rcx, rcx
0x180003068  jz      short loc_180003070
0x18000306a  call    cs:__imp_RegCloseKey
0x180003070  mov     ecx, 80000000h
0x180003075  lea     eax, [rbx+rcx]
0x180003078  test    ecx, eax
0x18000307a  jnz     short loc_1800030B7
0x18000307c  cmp     ebx, 80070002h
0x180003082  jz      short loc_1800030B7
0x180003084  mov     rcx, cs:WPP_GLOBAL_Control
0x18000308b  lea     rax, WPP_GLOBAL_Control
0x180003092  cmp     rcx, rax
0x180003095  jz      short loc_1800030B9
0x180003097  test    byte ptr [rcx+1Ch], 1
0x18000309b  jz      short loc_1800030B9
0x18000309d  mov     rcx, [rcx+10h]
0x1800030a1  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x1800030a8  mov     edx, 11h
0x1800030ad  mov     r9d, ebx
0x1800030b0  call    WPP_SF_d
0x1800030b5  jmp     short loc_1800030B9
0x1800030b7  xor     ebx, ebx
0x1800030b9  mov     eax, ebx
0x1800030bb  add     rsp, 30h
0x1800030bf  pop     rbx
0x1800030c0  retn
```
