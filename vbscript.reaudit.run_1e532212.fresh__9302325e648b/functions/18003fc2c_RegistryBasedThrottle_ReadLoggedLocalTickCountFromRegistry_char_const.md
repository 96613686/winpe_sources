# RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)

- ea: `0x18003fc2c`
- end: `0x18003fcfa`
- name: `?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z`
- size: `206`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800403a0`

## callees

- `0x18003fc2c`
- `0x180042290`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18003fc95`
- `ADVAPI32!RegOpenKeyExA` at `0x18003fc95`
- `ADVAPI32!RegCloseKey` at `0x18003fce0`
- `ADVAPI32!RegCloseKey` at `0x18003fcea`
- `ADVAPI32!RegCloseKey` at `0x18003fce0`
- `ADVAPI32!RegCloseKey` at `0x18003fcea`
- `ADVAPI32!RegQueryValueExA` at `0x18003fcc6`
- `ADVAPI32!RegQueryValueExA` at `0x18003fcc6`
- `ADVAPI32!RegOpenCurrentUser` at `0x18003fc6a`
- `ADVAPI32!RegOpenCurrentUser` at `0x18003fc6a`

## pseudocode

```c
__int64 __fastcall RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(BYTE *this, const char *a2)
{
  unsigned int v3; // ebx
  const CHAR *CurrentProcessTickCountRegistryKey; // rax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int v8; // [rsp+6Ch] [rbp+2Ch]
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  v8 = HIDWORD(a2);
  phkResult = 0;
  hKey = 0;
  cbData = 8;
  Type = 11;
  v3 = -2147467259;
  if ( !RegOpenCurrentUser(0x20119u, &phkResult) )
  {
    CurrentProcessTickCountRegistryKey = RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey((RegistryBasedThrottle *)this);
    if ( !RegOpenKeyExA(phkResult, CurrentProcessTickCountRegistryKey, 0, 0x20119u, &hKey) )
    {
      if ( !RegQueryValueExA(hKey, "VBScriptSetScriptStateStarted", 0, &Type, this + 296, &cbData) )
      {
        *((_DWORD *)this + 76) = 1;
        v3 = 0;
      }
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return v3;
}

```

## disassembly

```asm
0x18003fc2c  mov     qword ptr [rsp-18h+cbData], rdx
0x18003fc31  push    rbp
0x18003fc32  push    rbx
0x18003fc33  push    rdi
0x18003fc34  mov     rbp, rsp
0x18003fc37  sub     rsp, 40h
0x18003fc3b  mov     rdi, rcx
0x18003fc3e  mov     [rbp+phkResult], 0
0x18003fc46  mov     ecx, 20119h; samDesired
0x18003fc4b  mov     [rbp+hKey], 0
0x18003fc53  lea     rdx, [rbp+phkResult]; phkResult
0x18003fc57  mov     [rbp+cbData], 8
0x18003fc5e  mov     [rbp+Type], 0Bh
0x18003fc65  mov     ebx, 80004005h
0x18003fc6a  call    cs:__imp_RegOpenCurrentUser
0x18003fc70  test    eax, eax
0x18003fc72  jnz     short loc_18003FCF0
0x18003fc74  mov     rcx, rdi; this
0x18003fc77  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x18003fc7c  lea     rcx, [rbp+hKey]
0x18003fc80  mov     r9d, 20119h; samDesired
0x18003fc86  mov     [rsp+40h+var_20], rcx; phkResult
0x18003fc8b  xor     r8d, r8d; ulOptions
0x18003fc8e  mov     rcx, [rbp+phkResult]; hKey
0x18003fc92  mov     rdx, rax; lpSubKey
0x18003fc95  call    cs:__imp_RegOpenKeyExA
0x18003fc9b  test    eax, eax
0x18003fc9d  jnz     short loc_18003FCE6
0x18003fc9f  lea     rcx, [rbp+cbData]
0x18003fca3  xor     r8d, r8d; lpReserved
0x18003fca6  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18003fcab  lea     rax, [rdi+128h]
0x18003fcb2  mov     rcx, [rbp+hKey]; hKey
0x18003fcb6  lea     r9, [rbp+Type]; lpType
0x18003fcba  lea     rdx, aVbscriptsetscr; "VBScriptSetScriptStateStarted"
0x18003fcc1  mov     [rsp+40h+var_20], rax; lpData
0x18003fcc6  call    cs:__imp_RegQueryValueExA
0x18003fccc  test    eax, eax
0x18003fcce  jnz     short loc_18003FCDC
0x18003fcd0  mov     dword ptr [rdi+130h], 1
0x18003fcda  xor     ebx, ebx
0x18003fcdc  mov     rcx, [rbp+hKey]; hKey
0x18003fce0  call    cs:__imp_RegCloseKey
0x18003fce6  mov     rcx, [rbp+phkResult]; hKey
0x18003fcea  call    cs:__imp_RegCloseKey
0x18003fcf0  mov     eax, ebx
0x18003fcf2  add     rsp, 40h
0x18003fcf6  pop     rdi
0x18003fcf7  pop     rbx
0x18003fcf8  pop     rbp
0x18003fcf9  retn
```
