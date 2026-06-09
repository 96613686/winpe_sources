# CErcLuaElevationHelper::SetMachineOptinLevel(ulong)

- ea: `0x1800042c0`
- end: `0x180004404`
- name: `?SetMachineOptinLevel@CErcLuaElevationHelper@@UEAAJK@Z`
- size: `324`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002850`
- `0x180002a18`
- `0x1800042c0`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004360`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800043bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800043bd`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::SetMachineOptinLevel(CErcLuaElevationHelper *this, int a2)
{
  signed int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  bool v5; // cc
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  if ( (unsigned int)(a2 - 1) <= 2 )
  {
    hKey = 0;
    Data = a2;
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
            0,
            0,
            0,
            0x20106u,
            0,
            phkResult,
            0);
    v2 = Key;
    v5 = Key <= 0;
    if ( Key
      || (Key = RegSetValueExW(hKey, L"DefaultConsent", 0, 4u, (const BYTE *)&Data, 4u), v2 = Key, v5 = Key <= 0, Key) )
    {
      if ( !v5 )
        v2 = (unsigned __int16)Key | 0x80070000;
      if ( v2 >= 0 )
        v2 = -2147467259;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v2 >= 0 )
    {
      return 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids,
        (unsigned int)v2);
    }
  }
  else
  {
    v2 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800042c0  push    rbx
0x1800042c2  sub     rsp, 50h
0x1800042c6  lea     eax, [rdx-1]
0x1800042c9  cmp     eax, 2
0x1800042cc  jbe     short loc_18000430E
0x1800042ce  mov     ebx, 80070057h
0x1800042d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042da  lea     rax, WPP_GLOBAL_Control
0x1800042e1  cmp     rcx, rax
0x1800042e4  jz      loc_1800043FC
0x1800042ea  test    byte ptr [rcx+1Ch], 2
0x1800042ee  jz      loc_1800043FC
0x1800042f4  mov     rcx, [rcx+10h]
0x1800042f8  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x1800042ff  mov     edx, 13h
0x180004304  call    WPP_SF_
0x180004309  jmp     loc_1800043FC
0x18000430e  lea     rcx, [rsp+58h+hKey]
0x180004313  mov     [rsp+58h+hKey], 0
0x18000431c  mov     [rsp+58h+Data], edx
0x180004320  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180004325  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000432e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x180004335  mov     [rsp+58h+phkResult], rax; phkResult
0x18000433a  xor     r9d, r9d; lpClass
0x18000433d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180004346  xor     r8d, r8d; Reserved
0x180004349  mov     [rsp+58h+samDesired], 20106h; samDesired
0x180004351  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004358  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180004360  call    cs:__imp_RegCreateKeyExW
0x180004366  mov     ebx, eax
0x180004368  test    eax, eax
0x18000436a  jz      short loc_180004383
0x18000436c  jle     short loc_180004377
0x18000436e  movzx   ebx, ax
0x180004371  or      ebx, 80070000h
0x180004377  test    ebx, ebx
0x180004379  mov     eax, 80004005h
0x18000437e  cmovns  ebx, eax
0x180004381  jmp     short loc_1800043B3
0x180004383  mov     rcx, [rsp+58h+hKey]; hKey
0x180004388  lea     rax, [rsp+58h+Data]
0x18000438d  mov     r9d, 4; dwType
0x180004393  lea     rdx, aDefaultconsent; "DefaultConsent"
0x18000439a  mov     [rsp+58h+samDesired], r9d; cbData
0x18000439f  xor     r8d, r8d; Reserved
0x1800043a2  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800043a7  call    cs:__imp_RegSetValueExW
0x1800043ad  mov     ebx, eax
0x1800043af  test    eax, eax
0x1800043b1  jnz     short loc_18000436C
0x1800043b3  mov     rcx, [rsp+58h+hKey]; hKey
0x1800043b8  test    rcx, rcx
0x1800043bb  jz      short loc_1800043C3
0x1800043bd  call    cs:__imp_RegCloseKey
0x1800043c3  test    ebx, ebx
0x1800043c5  jns     short loc_1800043FA
0x1800043c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043ce  lea     rax, WPP_GLOBAL_Control
0x1800043d5  cmp     rcx, rax
0x1800043d8  jz      short loc_1800043FC
0x1800043da  test    byte ptr [rcx+1Ch], 1
0x1800043de  jz      short loc_1800043FC
0x1800043e0  mov     rcx, [rcx+10h]
0x1800043e4  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x1800043eb  mov     edx, 14h
0x1800043f0  mov     r9d, ebx
0x1800043f3  call    WPP_SF_d
0x1800043f8  jmp     short loc_1800043FC
0x1800043fa  xor     ebx, ebx
0x1800043fc  mov     eax, ebx
0x1800043fe  add     rsp, 50h
0x180004402  pop     rbx
0x180004403  retn
```
