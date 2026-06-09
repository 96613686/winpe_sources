# JAmsi::JAmsiIsEnabledByRegistry(void)

- ea: `0x180014a0c`
- end: `0x180014af8`
- name: `?JAmsiIsEnabledByRegistry@JAmsi@@QEAA_NXZ`
- size: `236`
- prototype: `bool __fastcall(JAmsi *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015cfc`

## callees

- `0x180014a0c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180014a6b`
- `ADVAPI32!RegOpenKeyExW` at `0x180014a6b`
- `ADVAPI32!RegCloseKey` at `0x180014ab8`
- `ADVAPI32!RegCloseKey` at `0x180014ab8`
- `ADVAPI32!RegQueryValueExW` at `0x180014aa6`
- `ADVAPI32!RegQueryValueExW` at `0x180014aa6`

## string_xrefs

- `0x180014a9f`: `AmsiEnable`

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
0x180014a0c  mov     qword ptr [rsp-10h+cbData], rcx
0x180014a11  push    rbp
0x180014a12  push    rbx
0x180014a13  mov     rbp, rsp
0x180014a16  sub     rsp, 38h
0x180014a1a  mov     eax, cs:?g_AmsiEnabled@@3HA; int g_AmsiEnabled
0x180014a20  mov     [rbp+Data], 0
0x180014a27  mov     [rbp+Type], 0
0x180014a2e  mov     [rbp+cbData], 0
0x180014a35  mov     [rbp+hKey], 0
0x180014a3d  test    eax, eax
0x180014a3f  jz      loc_180014AEE
0x180014a45  jg      loc_180014AEA
0x180014a4b  lea     rax, [rbp+hKey]
0x180014a4f  mov     r9d, 20019h; samDesired
0x180014a55  xor     r8d, r8d; ulOptions
0x180014a58  mov     [rsp+38h+phkResult], rax; phkResult
0x180014a5d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Script\\Se"...
0x180014a64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014a6b  call    cs:__imp_RegOpenKeyExW
0x180014a72  nop     dword ptr [rax+rax+00h]
0x180014a77  test    eax, eax
0x180014a79  jnz     short loc_180014AEA
0x180014a7b  mov     rcx, [rbp+hKey]; hKey
0x180014a7f  lea     rax, [rbp+cbData]
0x180014a83  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180014a88  lea     r9, [rbp+Type]; lpType
0x180014a8c  lea     rax, [rbp+Data]
0x180014a90  mov     [rbp+cbData], 4
0x180014a97  xor     r8d, r8d; lpReserved
0x180014a9a  mov     [rsp+38h+phkResult], rax; lpData
0x180014a9f  lea     rdx, ValueName; "AmsiEnable"
0x180014aa6  call    cs:__imp_RegQueryValueExW
0x180014aad  nop     dword ptr [rax+rax+00h]
0x180014ab2  mov     rcx, [rbp+hKey]; hKey
0x180014ab6  mov     ebx, eax
0x180014ab8  call    cs:__imp_RegCloseKey
0x180014abf  nop     dword ptr [rax+rax+00h]
0x180014ac4  test    ebx, ebx
0x180014ac6  jnz     short loc_180014AEA
0x180014ac8  cmp     [rbp+Type], 4
0x180014acc  jnz     short loc_180014AEA
0x180014ace  mov     ecx, [rbp+Data]
0x180014ad1  xor     eax, eax
0x180014ad3  test    ecx, ecx
0x180014ad5  setnz   al
0x180014ad8  mov     cs:?g_AmsiEnabled@@3HA, eax; int g_AmsiEnabled
0x180014ade  cmp     ecx, 1
0x180014ae1  jz      short loc_180014AEA
0x180014ae3  test    ecx, ecx
0x180014ae5  setnz   al
0x180014ae8  jmp     short loc_180014AF0
0x180014aea  mov     al, 1
0x180014aec  jmp     short loc_180014AF0
0x180014aee  xor     al, al
0x180014af0  add     rsp, 38h
0x180014af4  pop     rbx
0x180014af5  pop     rbp
0x180014af6  retn
```
