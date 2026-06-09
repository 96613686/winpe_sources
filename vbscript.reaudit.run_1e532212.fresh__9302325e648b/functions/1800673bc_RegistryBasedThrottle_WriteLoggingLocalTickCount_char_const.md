# RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)

- ea: `0x1800673bc`
- end: `0x1800674ad`
- name: `?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z`
- size: `241`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800546d4`

## callees

- `0x180042290`
- `0x1800673bc`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1800673df`
- `KERNEL32!GetTickCount64` at `0x1800673df`
- `ADVAPI32!RegSetValueExA` at `0x18006747a`
- `ADVAPI32!RegSetValueExA` at `0x18006747a`
- `ADVAPI32!RegCreateKeyExA` at `0x180067449`
- `ADVAPI32!RegCreateKeyExA` at `0x180067449`
- `ADVAPI32!RegCloseKey` at `0x18006748f`
- `ADVAPI32!RegCloseKey` at `0x18006749a`
- `ADVAPI32!RegCloseKey` at `0x18006748f`
- `ADVAPI32!RegCloseKey` at `0x18006749a`
- `ADVAPI32!RegOpenCurrentUser` at `0x1800673f9`
- `ADVAPI32!RegOpenCurrentUser` at `0x1800673f9`

## pseudocode

```c
__int64 __fastcall RegistryBasedThrottle::WriteLoggingLocalTickCount(RegistryBasedThrottle *this, const char *a2)
{
  unsigned int v3; // ebx
  const CHAR *CurrentProcessTickCountRegistryKey; // rax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  ULONGLONG Data; // [rsp+78h] [rbp+20h] BYREF

  phkResult = 0;
  hKey = 0;
  Data = GetTickCount64();
  v3 = -2147467259;
  if ( !RegOpenCurrentUser(0x20106u, &phkResult) )
  {
    CurrentProcessTickCountRegistryKey = RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(this);
    if ( !RegCreateKeyExA(phkResult, CurrentProcessTickCountRegistryKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
    {
      v3 = RegSetValueExA(hKey, "VBScriptSetScriptStateStarted", 0, 0xBu, (const BYTE *)&Data, 8u) != 0 ? 0x80004005 : 0;
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return v3;
}

```

## disassembly

```asm
0x1800673bc  mov     rax, rsp
0x1800673bf  mov     [rax+8], rbx
0x1800673c3  mov     [rax+10h], rdx
0x1800673c7  push    rdi
0x1800673c8  sub     rsp, 50h
0x1800673cc  mov     rdi, rcx
0x1800673cf  mov     qword ptr [rax+18h], 0
0x1800673d7  mov     qword ptr [rax+10h], 0
0x1800673df  call    cs:__imp_GetTickCount64
0x1800673e5  lea     rdx, [rsp+58h+phkResult]; phkResult
0x1800673ea  mov     ecx, 20106h; samDesired
0x1800673ef  mov     [rsp+58h+Data], rax
0x1800673f4  mov     ebx, 80004005h
0x1800673f9  call    cs:__imp_RegOpenCurrentUser
0x1800673ff  test    eax, eax
0x180067401  jnz     loc_1800674A0
0x180067407  mov     rcx, rdi; this
0x18006740a  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x18006740f  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180067418  lea     rcx, [rsp+58h+hKey]
0x18006741d  mov     [rsp+58h+var_20], rcx; phkResult
0x180067422  xor     r9d, r9d; lpClass
0x180067425  mov     rcx, [rsp+58h+phkResult]; hKey
0x18006742a  xor     r8d, r8d; Reserved
0x18006742d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180067436  mov     rdx, rax; lpSubKey
0x180067439  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x180067441  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180067449  call    cs:__imp_RegCreateKeyExA
0x18006744f  test    eax, eax
0x180067451  jnz     short loc_180067495
0x180067453  mov     rcx, [rsp+58h+hKey]; hKey
0x180067458  lea     rax, [rsp+58h+Data]
0x18006745d  mov     [rsp+58h+samDesired], 8; cbData
0x180067465  lea     rdx, aVbscriptsetscr; "VBScriptSetScriptStateStarted"
0x18006746c  mov     r9d, 0Bh; dwType
0x180067472  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180067477  xor     r8d, r8d; Reserved
0x18006747a  call    cs:__imp_RegSetValueExA
0x180067480  xor     ecx, ecx
0x180067482  sub     ecx, eax
0x180067484  neg     ecx
0x180067486  mov     rcx, [rsp+58h+hKey]; hKey
0x18006748b  sbb     eax, eax
0x18006748d  and     ebx, eax
0x18006748f  call    cs:__imp_RegCloseKey
0x180067495  mov     rcx, [rsp+58h+phkResult]; hKey
0x18006749a  call    cs:__imp_RegCloseKey
0x1800674a0  mov     eax, ebx
0x1800674a2  mov     rbx, [rsp+58h+arg_0]
0x1800674a7  add     rsp, 50h
0x1800674ab  pop     rdi
0x1800674ac  retn
```
