# CLogonUser::_GetExpiryDays(HKEY__ *)

- ea: `0x18002d1dc`
- end: `0x18002d308`
- name: `?_GetExpiryDays@CLogonUser@@AEAAKPEAUHKEY__@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CLogonUser *this, HKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e180`
- `0x18002f1f0`

## callees

- `0x18002d1dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d262`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d2d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d262`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d2d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d22d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d2a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d22d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d2a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d27e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d27e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2f5`

## string_xrefs

- `0x18002d208`: `Software\Microsoft\Windows\CurrentVersion\UnreadMail`
- `0x18002d296`: `Software\Microsoft\Windows\CurrentVersion\UnreadMail`

## pseudocode

```c
__int64 __fastcall CLogonUser::_GetExpiryDays(CLogonUser *this, HKEY a2)
{
  unsigned int v2; // ebx
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+10h] BYREF
  int v6; // [rsp+54h] [rbp+14h]
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  v6 = HIDWORD(this);
  Type = 0;
  Data = 0;
  v2 = 3;
  cbData = 0;
  hKey[0] = 0;
  if ( !RegOpenKeyExW(a2, L"Software\\Microsoft\\Windows\\CurrentVersion\\UnreadMail", 0, 1u, hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"MessageExpiryDays", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data <= 0x1E )
      v2 = Data;
    RegCloseKey(hKey[0]);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\UnreadMail", 0, 1u, hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"MessageExpiryDays", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data <= 0x1E )
      v2 = Data;
    RegCloseKey(hKey[0]);
  }
  return v2;
}

```

## disassembly

```asm
0x18002d1dc  mov     [rsp-8+arg_8], rbx
0x18002d1e1  mov     qword ptr [rsp-8+Data], rcx
0x18002d1e6  push    rbp
0x18002d1e7  mov     rbp, rsp
0x18002d1ea  sub     rsp, 40h
0x18002d1ee  mov     rax, rdx
0x18002d1f1  mov     [rbp+Type], 0
0x18002d1f8  lea     rcx, [rbp+hKey]
0x18002d1fc  mov     [rbp+Data], 0
0x18002d203  mov     [rsp+40h+phkResult], rcx; phkResult
0x18002d208  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d20f  mov     ebx, 3
0x18002d214  mov     [rbp+cbData], 0
0x18002d21b  xor     r8d, r8d; ulOptions
0x18002d21e  mov     [rbp+hKey], 0
0x18002d226  mov     rcx, rax; hKey
0x18002d229  lea     r9d, [rbx-2]; samDesired
0x18002d22d  call    cs:__imp_RegOpenKeyExW
0x18002d233  test    eax, eax
0x18002d235  jnz     short loc_18002D284
0x18002d237  mov     rcx, [rbp+hKey]; hKey
0x18002d23b  lea     rax, [rbp+cbData]
0x18002d23f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002d244  lea     r9, [rbp+Type]; lpType
0x18002d248  lea     rax, [rbp+Data]
0x18002d24c  mov     [rbp+cbData], 4
0x18002d253  xor     r8d, r8d; lpReserved
0x18002d256  mov     [rsp+40h+phkResult], rax; lpData
0x18002d25b  lea     rdx, ValueName; "MessageExpiryDays"
0x18002d262  call    cs:__imp_RegQueryValueExW
0x18002d268  test    eax, eax
0x18002d26a  jnz     short loc_18002D27A
0x18002d26c  cmp     [rbp+Type], 4
0x18002d270  jnz     short loc_18002D27A
0x18002d272  cmp     [rbp+Data], 1Eh
0x18002d276  cmovbe  ebx, [rbp+Data]
0x18002d27a  mov     rcx, [rbp+hKey]; hKey
0x18002d27e  call    cs:__imp_RegCloseKey
0x18002d284  lea     rax, [rbp+hKey]
0x18002d288  mov     r9d, 1; samDesired
0x18002d28e  xor     r8d, r8d; ulOptions
0x18002d291  mov     [rsp+40h+phkResult], rax; phkResult
0x18002d296  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d29d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d2a4  call    cs:__imp_RegOpenKeyExW
0x18002d2aa  test    eax, eax
0x18002d2ac  jnz     short loc_18002D2FB
0x18002d2ae  mov     rcx, [rbp+hKey]; hKey
0x18002d2b2  lea     rax, [rbp+cbData]
0x18002d2b6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002d2bb  lea     r9, [rbp+Type]; lpType
0x18002d2bf  lea     rax, [rbp+Data]
0x18002d2c3  mov     [rbp+cbData], 4
0x18002d2ca  xor     r8d, r8d; lpReserved
0x18002d2cd  mov     [rsp+40h+phkResult], rax; lpData
0x18002d2d2  lea     rdx, ValueName; "MessageExpiryDays"
0x18002d2d9  call    cs:__imp_RegQueryValueExW
0x18002d2df  test    eax, eax
0x18002d2e1  jnz     short loc_18002D2F1
0x18002d2e3  cmp     [rbp+Type], 4
0x18002d2e7  jnz     short loc_18002D2F1
0x18002d2e9  cmp     [rbp+Data], 1Eh
0x18002d2ed  cmovbe  ebx, [rbp+Data]
0x18002d2f1  mov     rcx, [rbp+hKey]; hKey
0x18002d2f5  call    cs:__imp_RegCloseKey
0x18002d2fb  mov     eax, ebx
0x18002d2fd  mov     rbx, [rsp+40h+arg_8]
0x18002d302  add     rsp, 40h
0x18002d306  pop     rbp
0x18002d307  retn
```
