# RegExists

- ea: `0x18000ce90`
- end: `0x18000cf2b`
- name: `RegExists`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c3f8`

## callees

- `0x18000ce90`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000cf16`
- `KERNEL32!SetLastError` at `0x18000cf16`
- `ADVAPI32!RegCloseKey` at `0x18000cf08`
- `ADVAPI32!RegCloseKey` at `0x18000cf08`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cec1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cec1`
- `ADVAPI32!RegQueryValueExW` at `0x18000cef2`
- `ADVAPI32!RegQueryValueExW` at `0x18000cef2`

## pseudocode

```c
__int64 RegExists()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey)
    && hKey )
  {
    LOBYTE(v0) = RegQueryValueExW(hKey, L"RegisteredOrganization", 0, 0, 0, 0) == 0;
    RegCloseKey(hKey);
  }
  SetLastError(0);
  return v0;
}

```

## disassembly

```asm
0x18000ce90  mov     r11, rsp
0x18000ce93  mov     [r11+18h], r8
0x18000ce97  push    rbx
0x18000ce98  sub     rsp, 30h
0x18000ce9c  lea     rax, [r11+18h]
0x18000cea0  xor     ebx, ebx
0x18000cea2  mov     r9d, 20019h; samDesired
0x18000cea8  mov     [r11+18h], rbx
0x18000ceac  xor     r8d, r8d; ulOptions
0x18000ceaf  mov     [r11-18h], rax
0x18000ceb3  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000ceba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cec1  call    cs:__imp_RegOpenKeyExW
0x18000cec8  nop     dword ptr [rax+rax+00h]
0x18000cecd  test    eax, eax
0x18000cecf  jnz     short loc_18000CF14
0x18000ced1  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ced6  test    rcx, rcx
0x18000ced9  jz      short loc_18000CF14
0x18000cedb  mov     [rsp+38h+lpcbData], rbx; lpcbData
0x18000cee0  lea     rdx, ValueName; "RegisteredOrganization"
0x18000cee7  xor     r9d, r9d; lpType
0x18000ceea  mov     [rsp+38h+lpData], rbx; lpData
0x18000ceef  xor     r8d, r8d; lpReserved
0x18000cef2  call    cs:__imp_RegQueryValueExW
0x18000cef9  nop     dword ptr [rax+rax+00h]
0x18000cefe  mov     rcx, [rsp+38h+hKey]; hKey
0x18000cf03  test    eax, eax
0x18000cf05  setz    bl
0x18000cf08  call    cs:__imp_RegCloseKey
0x18000cf0f  nop     dword ptr [rax+rax+00h]
0x18000cf14  xor     ecx, ecx; dwErrCode
0x18000cf16  call    cs:__imp_SetLastError
0x18000cf1d  nop     dword ptr [rax+rax+00h]
0x18000cf22  mov     eax, ebx
0x18000cf24  add     rsp, 30h
0x18000cf28  pop     rbx
0x18000cf29  retn
```
