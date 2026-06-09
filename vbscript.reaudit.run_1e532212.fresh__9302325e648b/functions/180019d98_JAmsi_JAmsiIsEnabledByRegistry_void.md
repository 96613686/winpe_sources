# JAmsi::JAmsiIsEnabledByRegistry(void)

- ea: `0x180019d98`
- end: `0x180019e71`
- name: `?JAmsiIsEnabledByRegistry@JAmsi@@QEAA_NXZ`
- size: `217`
- prototype: `bool __fastcall(JAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b008`

## callees

- `0x180019d98`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180019df7`
- `ADVAPI32!RegOpenKeyExW` at `0x180019df7`
- `ADVAPI32!RegCloseKey` at `0x180019e38`
- `ADVAPI32!RegCloseKey` at `0x180019e38`
- `ADVAPI32!RegQueryValueExW` at `0x180019e2c`
- `ADVAPI32!RegQueryValueExW` at `0x180019e2c`

## string_xrefs

- `0x180019e25`: `AmsiEnable`

## pseudocode

```c
bool __fastcall JAmsi::JAmsiIsEnabledByRegistry(JAmsi *this)
{
  LSTATUS v1; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  int v4; // [rsp+54h] [rbp+1Ch]
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v4 = HIDWORD(this);
  Data = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  if ( !g_AmsiEnabled )
    return 0;
  if ( g_AmsiEnabled > 0 )
    return 1;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Script\\Settings", 0, 0x20019u, &hKey) )
    return 1;
  cbData = 4;
  v1 = RegQueryValueExW(hKey, L"AmsiEnable", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( v1 )
    return 1;
  if ( Type != 4 )
    return 1;
  g_AmsiEnabled = Data != 0;
  if ( Data == 1 )
    return 1;
  return Data != 0;
}

```

## disassembly

```asm
0x180019d98  mov     qword ptr [rsp-10h+cbData], rcx
0x180019d9d  push    rbp
0x180019d9e  push    rbx
0x180019d9f  mov     rbp, rsp
0x180019da2  sub     rsp, 38h
0x180019da6  mov     eax, cs:?g_AmsiEnabled@@3HA; int g_AmsiEnabled
0x180019dac  mov     [rbp+Data], 0
0x180019db3  mov     [rbp+Type], 0
0x180019dba  mov     [rbp+cbData], 0
0x180019dc1  mov     [rbp+hKey], 0
0x180019dc9  test    eax, eax
0x180019dcb  jz      loc_180019E68
0x180019dd1  jg      loc_180019E64
0x180019dd7  lea     rax, [rbp+hKey]
0x180019ddb  mov     r9d, 20019h; samDesired
0x180019de1  xor     r8d, r8d; ulOptions
0x180019de4  mov     [rsp+38h+phkResult], rax; phkResult
0x180019de9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Script\\Se"...
0x180019df0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019df7  call    cs:__imp_RegOpenKeyExW
0x180019dfd  test    eax, eax
0x180019dff  jnz     short loc_180019E64
0x180019e01  mov     rcx, [rbp+hKey]; hKey
0x180019e05  lea     rax, [rbp+cbData]
0x180019e09  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180019e0e  lea     r9, [rbp+Type]; lpType
0x180019e12  lea     rax, [rbp+Data]
0x180019e16  mov     [rbp+cbData], 4
0x180019e1d  xor     r8d, r8d; lpReserved
0x180019e20  mov     [rsp+38h+phkResult], rax; lpData
0x180019e25  lea     rdx, ValueName; "AmsiEnable"
0x180019e2c  call    cs:__imp_RegQueryValueExW
0x180019e32  mov     rcx, [rbp+hKey]; hKey
0x180019e36  mov     ebx, eax
0x180019e38  call    cs:__imp_RegCloseKey
0x180019e3e  test    ebx, ebx
0x180019e40  jnz     short loc_180019E64
0x180019e42  cmp     [rbp+Type], 4
0x180019e46  jnz     short loc_180019E64
0x180019e48  mov     ecx, [rbp+Data]
0x180019e4b  xor     eax, eax
0x180019e4d  test    ecx, ecx
0x180019e4f  setnz   al
0x180019e52  mov     cs:?g_AmsiEnabled@@3HA, eax; int g_AmsiEnabled
0x180019e58  cmp     ecx, 1
0x180019e5b  jz      short loc_180019E64
0x180019e5d  test    ecx, ecx
0x180019e5f  setnz   al
0x180019e62  jmp     short loc_180019E6A
0x180019e64  mov     al, 1
0x180019e66  jmp     short loc_180019E6A
0x180019e68  xor     al, al
0x180019e6a  add     rsp, 38h
0x180019e6e  pop     rbx
0x180019e6f  pop     rbp
0x180019e70  retn
```
