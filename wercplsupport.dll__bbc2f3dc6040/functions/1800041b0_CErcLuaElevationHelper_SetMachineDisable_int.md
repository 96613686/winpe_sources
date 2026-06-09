# CErcLuaElevationHelper::SetMachineDisable(int)

- ea: `0x1800041b0`
- end: `0x1800042b3`
- name: `?SetMachineDisable@CErcLuaElevationHelper@@UEAAJH@Z`
- size: `259`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a18`
- `0x1800041b0`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004256`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004256`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000420f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000420f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000426c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000426c`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::SetMachineDisable(CErcLuaElevationHelper *this, int a2)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v4; // ebx
  bool v5; // cc
  BOOL Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  Data = a2 != 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0,
          0,
          0x20106u,
          0,
          phkResult,
          0);
  v4 = Key;
  v5 = Key <= 0;
  if ( Key || (Key = RegSetValueExW(hKey, L"Disabled", 0, 4u, (const BYTE *)&Data, 4u), v4 = Key, v5 = Key <= 0, Key) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)Key | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 >= 0 )
  {
    return 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800041b0  push    rbx
0x1800041b2  sub     rsp, 50h
0x1800041b6  xor     eax, eax
0x1800041b8  mov     [rsp+58h+hKey], 0
0x1800041c1  test    edx, edx
0x1800041c3  lea     rcx, [rsp+58h+hKey]
0x1800041c8  setnz   al
0x1800041cb  mov     [rsp+58h+Data], eax
0x1800041cf  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800041d4  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800041dd  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Windows E"...
0x1800041e4  mov     [rsp+58h+phkResult], rax; phkResult
0x1800041e9  xor     r9d, r9d; lpClass
0x1800041ec  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800041f5  xor     r8d, r8d; Reserved
0x1800041f8  mov     [rsp+58h+samDesired], 20106h; samDesired
0x180004200  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004207  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000420f  call    cs:__imp_RegCreateKeyExW
0x180004215  mov     ebx, eax
0x180004217  test    eax, eax
0x180004219  jz      short loc_180004232
0x18000421b  jle     short loc_180004226
0x18000421d  movzx   ebx, ax
0x180004220  or      ebx, 80070000h
0x180004226  test    ebx, ebx
0x180004228  mov     eax, 80004005h
0x18000422d  cmovns  ebx, eax
0x180004230  jmp     short loc_180004262
0x180004232  mov     rcx, [rsp+58h+hKey]; hKey
0x180004237  lea     rax, [rsp+58h+Data]
0x18000423c  mov     r9d, 4; dwType
0x180004242  lea     rdx, ValueName; "Disabled"
0x180004249  mov     [rsp+58h+samDesired], r9d; cbData
0x18000424e  xor     r8d, r8d; Reserved
0x180004251  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180004256  call    cs:__imp_RegSetValueExW
0x18000425c  mov     ebx, eax
0x18000425e  test    eax, eax
0x180004260  jnz     short loc_18000421B
0x180004262  mov     rcx, [rsp+58h+hKey]; hKey
0x180004267  test    rcx, rcx
0x18000426a  jz      short loc_180004272
0x18000426c  call    cs:__imp_RegCloseKey
0x180004272  test    ebx, ebx
0x180004274  jns     short loc_1800042A9
0x180004276  mov     rcx, cs:WPP_GLOBAL_Control
0x18000427d  lea     rax, WPP_GLOBAL_Control
0x180004284  cmp     rcx, rax
0x180004287  jz      short loc_1800042AB
0x180004289  test    byte ptr [rcx+1Ch], 1
0x18000428d  jz      short loc_1800042AB
0x18000428f  mov     rcx, [rcx+10h]
0x180004293  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x18000429a  mov     edx, 12h
0x18000429f  mov     r9d, ebx
0x1800042a2  call    WPP_SF_d
0x1800042a7  jmp     short loc_1800042AB
0x1800042a9  xor     ebx, ebx
0x1800042ab  mov     eax, ebx
0x1800042ad  add     rsp, 50h
0x1800042b1  pop     rbx
0x1800042b2  retn
```
