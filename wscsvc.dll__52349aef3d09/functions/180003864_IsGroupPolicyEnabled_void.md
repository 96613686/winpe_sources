# _IsGroupPolicyEnabled(void)

- ea: `0x180003864`
- end: `0x180003910`
- name: `?_IsGroupPolicyEnabled@@YAHXZ`
- size: `172`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800037ac`

## callees

- `0x180003864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003901`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038e0`

## string_xrefs

- `0x18000388c`: `Software\Policies\Microsoft\Windows NT\Security Center`
- `0x1800038d9`: `SecurityCenterInDomain`

## pseudocode

```c
__int64 _IsGroupPolicyEnabled(void)
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Type = 0;
  v0 = 0;
  cbData = 0;
  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Security Center", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"SecurityCenterInDomain", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      LOBYTE(v0) = Data == 1;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180003864  push    rbp
0x180003866  push    rbx
0x180003867  mov     rbp, rsp
0x18000386a  sub     rsp, 38h
0x18000386e  lea     rax, [rbp+hKey]
0x180003872  mov     [rbp+Type], 0
0x180003879  xor     ebx, ebx
0x18000387b  mov     [rbp+cbData], 0
0x180003882  xor     r8d, r8d; ulOptions
0x180003885  mov     [rbp+Data], 0
0x18000388c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180003893  mov     [rbp+hKey], 0
0x18000389b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800038a2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800038a7  lea     r9d, [rbx+1]; samDesired
0x1800038ab  call    cs:__imp_RegOpenKeyExW
0x1800038b1  test    eax, eax
0x1800038b3  jnz     short loc_180003907
0x1800038b5  mov     rcx, [rbp+hKey]; hKey
0x1800038b9  lea     rax, [rbp+cbData]
0x1800038bd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800038c2  lea     r9, [rbp+Type]; lpType
0x1800038c6  lea     rax, [rbp+Data]
0x1800038ca  mov     [rbp+cbData], 4
0x1800038d1  xor     r8d, r8d; lpReserved
0x1800038d4  mov     [rsp+38h+phkResult], rax; lpData
0x1800038d9  lea     rdx, ValueName; "SecurityCenterInDomain"
0x1800038e0  call    cs:__imp_RegQueryValueExW
0x1800038e6  test    eax, eax
0x1800038e8  jnz     short loc_1800038FD
0x1800038ea  cmp     [rbp+Type], 4
0x1800038ee  jnz     short loc_1800038FD
0x1800038f0  cmp     [rbp+cbData], 4
0x1800038f4  jnz     short loc_1800038FD
0x1800038f6  cmp     [rbp+Data], 1
0x1800038fa  setz    bl
0x1800038fd  mov     rcx, [rbp+hKey]; hKey
0x180003901  call    cs:__imp_RegCloseKey
0x180003907  mov     eax, ebx
0x180003909  add     rsp, 38h
0x18000390d  pop     rbx
0x18000390e  pop     rbp
0x18000390f  retn
```
