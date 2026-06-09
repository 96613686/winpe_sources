# CImmersiveColorImpl::SetColorPreferenceToRegistry(IMMERSIVE_COLOR_PREFERENCE const *)

- ea: `0x18011d88c`
- end: `0x18011d9b0`
- name: `?SetColorPreferenceToRegistry@CImmersiveColorImpl@@CAJPEBUIMMERSIVE_COLOR_PREFERENCE@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011e218`

## callees

- `0x18011d88c`
- `0x18011e33c`
- `0x18011e374`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011d993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011d993`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011d93a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011d979`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011d93a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011d979`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011d8fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18011d8fb`

## pseudocode

```c
__int64 __fastcall CImmersiveColorImpl::SetColorPreferenceToRegistry(BYTE *lpData)
{
  signed int v1; // ebx
  HKEY v3; // rcx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  HKEY v8[3]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  if ( !g_dwIsColorSelectionDisabledByPolicy )
  {
    hKey = 0;
    CCurrentColorUser::CCurrentColorUser(v8, 0x2001Fu);
    v3 = v8[0];
    if ( CCurrentColorUser::_overrideCurrentUser )
      v3 = CCurrentColorUser::_overrideCurrentUser;
    v4 = RegCreateKeyExW(
           v3,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    v1 = v4;
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    if ( v1 >= 0 )
    {
      v5 = RegSetValueExW(hKey, L"StartColorMenu", 0, 4u, lpData, 4u);
      v1 = v5;
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
      if ( v1 >= 0 )
      {
        v6 = RegSetValueExW(hKey, L"AccentColorMenu", 0, 4u, lpData + 4, 4u);
        v1 = v6;
        if ( v6 > 0 )
          v1 = (unsigned __int16)v6 | 0x80070000;
      }
      RegCloseKey(hKey);
    }
    CCurrentUser::~CCurrentUser((CCurrentUser *)v8);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18011d88c  mov     [rsp+arg_0], rbx
0x18011d891  push    rdi
0x18011d892  sub     rsp, 60h
0x18011d896  xor     ebx, ebx
0x18011d898  mov     rdi, rcx
0x18011d89b  cmp     cs:?g_dwIsColorSelectionDisabledByPolicy@@3KA, ebx; ulong g_dwIsColorSelectionDisabledByPolicy
0x18011d8a1  jnz     loc_18011D9A3
0x18011d8a7  mov     edx, 2001Fh; samDesired
0x18011d8ac  mov     [rsp+68h+hKey], rbx
0x18011d8b1  lea     rcx, [rsp+68h+var_18]; phkResult
0x18011d8b6  call    ??0CCurrentColorUser@@QEAA@K@Z; CCurrentColorUser::CCurrentColorUser(ulong)
0x18011d8bb  mov     rax, cs:?_overrideCurrentUser@CCurrentColorUser@@0PEAUHKEY__@@EA; HKEY__ * CCurrentColorUser::_overrideCurrentUser
0x18011d8c2  lea     rdx, aSoftwareMicros_28; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011d8c9  mov     rcx, [rsp+68h+var_18]
0x18011d8ce  test    rax, rax
0x18011d8d1  mov     [rsp+68h+lpdwDisposition], rbx; lpdwDisposition
0x18011d8d6  cmovnz  rcx, rax; hKey
0x18011d8da  lea     rax, [rsp+68h+hKey]
0x18011d8df  mov     [rsp+68h+phkResult], rax; phkResult
0x18011d8e4  xor     r9d, r9d; lpClass
0x18011d8e7  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18011d8ec  xor     r8d, r8d; Reserved
0x18011d8ef  mov     [rsp+68h+samDesired], 2; samDesired
0x18011d8f7  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x18011d8fb  call    cs:__imp_RegCreateKeyExW
0x18011d901  mov     ebx, eax
0x18011d903  test    eax, eax
0x18011d905  jle     short loc_18011D910
0x18011d907  movzx   ebx, ax
0x18011d90a  or      ebx, 80070000h
0x18011d910  test    ebx, ebx
0x18011d912  js      loc_18011D999
0x18011d918  mov     rcx, [rsp+68h+hKey]; hKey
0x18011d91d  lea     rdx, aStartcolormenu; "StartColorMenu"
0x18011d924  mov     [rsp+68h+samDesired], 4; cbData
0x18011d92c  mov     r9d, 4; dwType
0x18011d932  xor     r8d, r8d; Reserved
0x18011d935  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x18011d93a  call    cs:__imp_RegSetValueExW
0x18011d940  mov     ebx, eax
0x18011d942  test    eax, eax
0x18011d944  jle     short loc_18011D94F
0x18011d946  movzx   ebx, ax
0x18011d949  or      ebx, 80070000h
0x18011d94f  test    ebx, ebx
0x18011d951  js      short loc_18011D98E
0x18011d953  mov     rcx, [rsp+68h+hKey]; hKey
0x18011d958  lea     rax, [rdi+4]
0x18011d95c  mov     [rsp+68h+samDesired], 4; cbData
0x18011d964  lea     rdx, aAccentcolormen; "AccentColorMenu"
0x18011d96b  mov     r9d, 4; dwType
0x18011d971  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18011d976  xor     r8d, r8d; Reserved
0x18011d979  call    cs:__imp_RegSetValueExW
0x18011d97f  mov     ebx, eax
0x18011d981  test    eax, eax
0x18011d983  jle     short loc_18011D98E
0x18011d985  movzx   ebx, ax
0x18011d988  or      ebx, 80070000h
0x18011d98e  mov     rcx, [rsp+68h+hKey]; hKey
0x18011d993  call    cs:__imp_RegCloseKey
0x18011d999  lea     rcx, [rsp+68h+var_18]; this
0x18011d99e  call    ??1CCurrentUser@@QEAA@XZ; CCurrentUser::~CCurrentUser(void)
0x18011d9a3  mov     eax, ebx
0x18011d9a5  mov     rbx, [rsp+68h+arg_0]
0x18011d9aa  add     rsp, 60h
0x18011d9ae  pop     rdi
0x18011d9af  retn
```
