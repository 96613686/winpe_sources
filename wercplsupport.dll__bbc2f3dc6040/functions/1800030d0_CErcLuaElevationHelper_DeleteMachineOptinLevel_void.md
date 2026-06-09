# CErcLuaElevationHelper::DeleteMachineOptinLevel(void)

- ea: `0x1800030d0`
- end: `0x1800031b3`
- name: `?DeleteMachineOptinLevel@CErcLuaElevationHelper@@UEAAJXZ`
- size: `227`
- prototype: `__int64 __fastcall(CErcLuaElevationHelper *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a18`
- `0x1800030d0`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003105`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003105`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003134`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000314c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003134`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000314c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000315c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000315c`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelper::DeleteMachineOptinLevel(CErcLuaElevationHelper *this)
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
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
         0,
         0x20106u,
         phkResult);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 || (v2 = RegDeleteValueW(hKey, L"DefaultConsent"), v3 = v2, v4 = v2 <= 0, v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2147467259;
  }
  else
  {
    RegDeleteValueW(hKey, L"NewUserDefaultConsent");
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147024894 )
  {
    return 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1800030d0  push    rbx
0x1800030d2  sub     rsp, 30h
0x1800030d6  lea     rcx, [rsp+38h+hKey]
0x1800030db  mov     [rsp+38h+hKey], 0
0x1800030e4  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800030e9  mov     r9d, 20106h; samDesired
0x1800030ef  mov     [rsp+38h+phkResult], rax; phkResult
0x1800030f4  xor     r8d, r8d; ulOptions
0x1800030f7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x1800030fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003105  call    cs:__imp_RegOpenKeyExW
0x18000310b  mov     ebx, eax
0x18000310d  test    eax, eax
0x18000310f  jz      short loc_180003128
0x180003111  jle     short loc_18000311C
0x180003113  movzx   ebx, ax
0x180003116  or      ebx, 80070000h
0x18000311c  test    ebx, ebx
0x18000311e  mov     eax, 80004005h
0x180003123  cmovns  ebx, eax
0x180003126  jmp     short loc_180003152
0x180003128  mov     rcx, [rsp+38h+hKey]; hKey
0x18000312d  lea     rdx, aDefaultconsent; "DefaultConsent"
0x180003134  call    cs:__imp_RegDeleteValueW
0x18000313a  mov     ebx, eax
0x18000313c  test    eax, eax
0x18000313e  jnz     short loc_180003111
0x180003140  mov     rcx, [rsp+38h+hKey]; hKey
0x180003145  lea     rdx, aNewuserdefault; "NewUserDefaultConsent"
0x18000314c  call    cs:__imp_RegDeleteValueW
0x180003152  mov     rcx, [rsp+38h+hKey]; hKey
0x180003157  test    rcx, rcx
0x18000315a  jz      short loc_180003162
0x18000315c  call    cs:__imp_RegCloseKey
0x180003162  mov     ecx, 80000000h
0x180003167  lea     eax, [rbx+rcx]
0x18000316a  test    ecx, eax
0x18000316c  jnz     short loc_1800031A9
0x18000316e  cmp     ebx, 80070002h
0x180003174  jz      short loc_1800031A9
0x180003176  mov     rcx, cs:WPP_GLOBAL_Control
0x18000317d  lea     rax, WPP_GLOBAL_Control
0x180003184  cmp     rcx, rax
0x180003187  jz      short loc_1800031AB
0x180003189  test    byte ptr [rcx+1Ch], 1
0x18000318d  jz      short loc_1800031AB
0x18000318f  mov     rcx, [rcx+10h]
0x180003193  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x18000319a  mov     edx, 10h
0x18000319f  mov     r9d, ebx
0x1800031a2  call    WPP_SF_d
0x1800031a7  jmp     short loc_1800031AB
0x1800031a9  xor     ebx, ebx
0x1800031ab  mov     eax, ebx
0x1800031ad  add     rsp, 30h
0x1800031b1  pop     rbx
0x1800031b2  retn
```
