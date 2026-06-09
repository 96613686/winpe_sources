# RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)

- ea: `0x1800412e0`
- end: `0x1800413d1`
- name: `?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z`
- size: `241`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180041a70`

## callees

- `0x1800412e0`
- `0x180043964`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180041353`
- `ADVAPI32!RegOpenKeyExA` at `0x180041353`
- `ADVAPI32!RegCloseKey` at `0x1800413aa`
- `ADVAPI32!RegCloseKey` at `0x1800413ba`
- `ADVAPI32!RegCloseKey` at `0x1800413aa`
- `ADVAPI32!RegCloseKey` at `0x1800413ba`
- `ADVAPI32!RegQueryValueExA` at `0x18004138a`
- `ADVAPI32!RegQueryValueExA` at `0x18004138a`
- `ADVAPI32!RegOpenCurrentUser` at `0x18004131e`
- `ADVAPI32!RegOpenCurrentUser` at `0x18004131e`

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
0x1800412e0  mov     qword ptr [rsp-18h+cbData], rdx
0x1800412e5  push    rbp
0x1800412e6  push    rbx
0x1800412e7  push    rdi
0x1800412e8  mov     rbp, rsp
0x1800412eb  sub     rsp, 40h
0x1800412ef  mov     rdi, rcx
0x1800412f2  mov     [rbp+phkResult], 0
0x1800412fa  mov     ecx, 20119h; samDesired
0x1800412ff  mov     [rbp+hKey], 0
0x180041307  lea     rdx, [rbp+phkResult]; phkResult
0x18004130b  mov     [rbp+cbData], 8
0x180041312  mov     [rbp+Type], 0Bh
0x180041319  mov     ebx, 80004005h
0x18004131e  call    cs:__imp_RegOpenCurrentUser
0x180041325  nop     dword ptr [rax+rax+00h]
0x18004132a  test    eax, eax
0x18004132c  jnz     loc_1800413C6
0x180041332  mov     rcx, rdi; this
0x180041335  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x18004133a  lea     rcx, [rbp+hKey]
0x18004133e  mov     r9d, 20119h; samDesired
0x180041344  mov     [rsp+40h+var_20], rcx; phkResult
0x180041349  xor     r8d, r8d; ulOptions
0x18004134c  mov     rcx, [rbp+phkResult]; hKey
0x180041350  mov     rdx, rax; lpSubKey
0x180041353  call    cs:__imp_RegOpenKeyExA
0x18004135a  nop     dword ptr [rax+rax+00h]
0x18004135f  test    eax, eax
0x180041361  jnz     short loc_1800413B6
0x180041363  lea     rcx, [rbp+cbData]
0x180041367  xor     r8d, r8d; lpReserved
0x18004136a  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18004136f  lea     rax, [rdi+128h]
0x180041376  mov     rcx, [rbp+hKey]; hKey
0x18004137a  lea     r9, [rbp+Type]; lpType
0x18004137e  lea     rdx, aVbscriptsetscr; "VBScriptSetScriptStateStarted"
0x180041385  mov     [rsp+40h+var_20], rax; lpData
0x18004138a  call    cs:__imp_RegQueryValueExA
0x180041391  nop     dword ptr [rax+rax+00h]
0x180041396  test    eax, eax
0x180041398  jnz     short loc_1800413A6
0x18004139a  mov     dword ptr [rdi+130h], 1
0x1800413a4  xor     ebx, ebx
0x1800413a6  mov     rcx, [rbp+hKey]; hKey
0x1800413aa  call    cs:__imp_RegCloseKey
0x1800413b1  nop     dword ptr [rax+rax+00h]
0x1800413b6  mov     rcx, [rbp+phkResult]; hKey
0x1800413ba  call    cs:__imp_RegCloseKey
0x1800413c1  nop     dword ptr [rax+rax+00h]
0x1800413c6  mov     eax, ebx
0x1800413c8  add     rsp, 40h
0x1800413cc  pop     rdi
0x1800413cd  pop     rbx
0x1800413ce  pop     rbp
0x1800413cf  retn
```
