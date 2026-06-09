# CDialMon::RefreshTimeoutSettings(void)

- ea: `0x180025998`
- end: `0x180025bf0`
- name: `?RefreshTimeoutSettings@CDialMon@@AEAAHXZ`
- size: `600`
- prototype: `__int64 __fastcall(CDialMon *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800256a8`

## callees

- `0x180008320`
- `0x18000bf78`
- `0x180025998`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025bc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025bc0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025a4c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025a4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025b6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025b93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025b6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025b93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025bb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025a89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025ac8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025b0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025a89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025ac8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025b0d`

## string_xrefs

- `0x1800259f1`: `RemoteAccess`

## pseudocode

```c
__int64 __fastcall CDialMon::RefreshTimeoutSettings(CDialMon *this)
{
  unsigned int v1; // edi
  BYTE *v2; // r14
  HKEY v4; // rcx
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = 0;
  hKey = 0;
  v2 = (BYTE *)this + 4;
  *((_DWORD *)this + 4) = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  dwDisposition[0] = 0;
  *((_DWORD *)this + 1) = 0;
  StringCchPrintfW(SubKey, 0x104u, L"%s\\Profile\\%s", L"RemoteAccess", (char *)this + 24);
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, (LPWSTR)&Class, 0, 3u, 0, &hKey, dwDisposition) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"EnableAutodisconnect", 0, 0, Data, &cbData) )
    {
      v4 = hKey;
      v1 = 1;
      *(_DWORD *)Data = 1;
      *(_DWORD *)v2 = 20;
      *((_DWORD *)this + 4) = 1;
      RegSetValueExW(v4, L"EnableAutodisconnect", 0, 4u, Data, 4u);
      RegSetValueExW(hKey, L"EnableExitDisconnect", 0, 4u, Data, 4u);
      RegSetValueExW(hKey, L"DisconnectIdleTime", 0, 4u, v2, 4u);
    }
    else
    {
      if ( *(_DWORD *)Data )
      {
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"DisconnectIdleTime", 0, 0, Data, &cbData) )
        {
          if ( *(_DWORD *)Data )
          {
            *(_DWORD *)v2 = *(_DWORD *)Data;
            v1 = 1;
          }
        }
      }
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"EnableExitDisconnect", 0, 0, Data, &cbData) && *(_DWORD *)Data )
      {
        *((_DWORD *)this + 4) = 1;
        v1 = 1;
      }
    }
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x180025998  mov     [rsp-8+arg_8], rsi
0x18002599d  mov     [rsp-8+arg_10], rdi
0x1800259a2  push    rbp
0x1800259a3  push    r12
0x1800259a5  push    r14
0x1800259a7  lea     rbp, [rsp-190h]
0x1800259af  sub     rsp, 290h
0x1800259b6  mov     rax, cs:__security_cookie
0x1800259bd  xor     rax, rsp
0x1800259c0  mov     [rbp+1A0h+var_20], rax
0x1800259c7  xor     edi, edi
0x1800259c9  mov     [rsp+2A0h+hKey], 0
0x1800259d2  lea     r14, [rcx+4]
0x1800259d6  mov     [rcx+10h], edi
0x1800259d9  lea     rax, [rcx+18h]
0x1800259dd  mov     dword ptr [rsp+2A0h+Data], edi
0x1800259e1  mov     rsi, rcx
0x1800259e4  mov     [rsp+2A0h+cbData], edi
0x1800259e8  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800259ed  mov     [rsp+2A0h+dwDisposition], edi
0x1800259f1  lea     r9, aRemoteaccess; "RemoteAccess"
0x1800259f8  mov     [r14], edi
0x1800259fb  lea     r8, aSProfileS; "%s\\Profile\\%s"
0x180025a02  mov     qword ptr [rsp+2A0h+dwOptions], rax
0x180025a07  mov     edx, 104h; unsigned __int64
0x180025a0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025a11  lea     rax, [rsp+2A0h+dwDisposition]
0x180025a16  xor     r8d, r8d; Reserved
0x180025a19  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x180025a1e  lea     r9, Class; lpClass
0x180025a25  lea     rax, [rsp+2A0h+hKey]
0x180025a2a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180025a31  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180025a36  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180025a3b  mov     [rsp+2A0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180025a40  mov     [rsp+2A0h+samDesired], 3; samDesired
0x180025a48  mov     [rsp+2A0h+dwOptions], edi; dwOptions
0x180025a4c  call    cs:__imp_RegCreateKeyExW
0x180025a52  test    eax, eax
0x180025a54  jnz     loc_180025BC6
0x180025a5a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025a5f  lea     rax, [rsp+2A0h+cbData]
0x180025a64  mov     qword ptr [rsp+2A0h+samDesired], rax; lpcbData
0x180025a69  lea     r12d, [rdi+4]
0x180025a6d  lea     rax, [rsp+2A0h+Data]
0x180025a72  mov     [rsp+2A0h+cbData], r12d
0x180025a77  xor     r9d, r9d; lpType
0x180025a7a  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180025a7f  xor     r8d, r8d; lpReserved
0x180025a82  lea     rdx, ValueName; "EnableAutodisconnect"
0x180025a89  call    cs:__imp_RegQueryValueExW
0x180025a8f  test    eax, eax
0x180025a91  jnz     loc_180025B34
0x180025a97  cmp     dword ptr [rsp+2A0h+Data], edi
0x180025a9b  jz      short loc_180025AE2
0x180025a9d  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025aa2  lea     rax, [rsp+2A0h+cbData]
0x180025aa7  mov     qword ptr [rsp+2A0h+samDesired], rax; lpcbData
0x180025aac  lea     rdx, aDisconnectidle; "DisconnectIdleTime"
0x180025ab3  lea     rax, [rsp+2A0h+Data]
0x180025ab8  mov     [rsp+2A0h+cbData], r12d
0x180025abd  xor     r9d, r9d; lpType
0x180025ac0  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180025ac5  xor     r8d, r8d; lpReserved
0x180025ac8  call    cs:__imp_RegQueryValueExW
0x180025ace  test    eax, eax
0x180025ad0  jnz     short loc_180025AE2
0x180025ad2  mov     eax, dword ptr [rsp+2A0h+Data]
0x180025ad6  test    eax, eax
0x180025ad8  jz      short loc_180025AE2
0x180025ada  mov     [r14], eax
0x180025add  lea     edi, [r12-3]
0x180025ae2  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025ae7  lea     rax, [rsp+2A0h+cbData]
0x180025aec  mov     qword ptr [rsp+2A0h+samDesired], rax; lpcbData
0x180025af1  lea     rdx, aEnableexitdisc; "EnableExitDisconnect"
0x180025af8  lea     rax, [rsp+2A0h+Data]
0x180025afd  mov     [rsp+2A0h+cbData], r12d
0x180025b02  xor     r9d, r9d; lpType
0x180025b05  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180025b0a  xor     r8d, r8d; lpReserved
0x180025b0d  call    cs:__imp_RegQueryValueExW
0x180025b13  test    eax, eax
0x180025b15  jnz     loc_180025BBB
0x180025b1b  cmp     dword ptr [rsp+2A0h+Data], eax
0x180025b1f  jz      loc_180025BBB
0x180025b25  mov     dword ptr [rsi+10h], 1
0x180025b2c  lea     edi, [rax+1]
0x180025b2f  jmp     loc_180025BBB
0x180025b34  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025b39  lea     rax, [rsp+2A0h+Data]
0x180025b3e  mov     edi, 1
0x180025b43  mov     [rsp+2A0h+samDesired], r12d; cbData
0x180025b48  mov     r9d, r12d; dwType
0x180025b4b  mov     dword ptr [rsp+2A0h+Data], edi
0x180025b4f  xor     r8d, r8d; Reserved
0x180025b52  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180025b57  lea     rdx, ValueName; "EnableAutodisconnect"
0x180025b5e  mov     dword ptr [r14], 14h
0x180025b65  mov     dword ptr [rsi+10h], 1
0x180025b6c  call    cs:__imp_RegSetValueExW
0x180025b72  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025b77  lea     rax, [rsp+2A0h+Data]
0x180025b7c  mov     [rsp+2A0h+samDesired], r12d; cbData
0x180025b81  lea     rdx, aEnableexitdisc; "EnableExitDisconnect"
0x180025b88  mov     r9d, r12d; dwType
0x180025b8b  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180025b90  xor     r8d, r8d; Reserved
0x180025b93  call    cs:__imp_RegSetValueExW
0x180025b99  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025b9e  lea     rdx, aDisconnectidle; "DisconnectIdleTime"
0x180025ba5  mov     r9d, r12d; dwType
0x180025ba8  mov     [rsp+2A0h+samDesired], r12d; cbData
0x180025bad  xor     r8d, r8d; Reserved
0x180025bb0  mov     qword ptr [rsp+2A0h+dwOptions], r14; lpData
0x180025bb5  call    cs:__imp_RegSetValueExW
0x180025bbb  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180025bc0  call    cs:__imp_RegCloseKey
0x180025bc6  mov     eax, edi
0x180025bc8  mov     rcx, [rbp+1A0h+var_20]
0x180025bcf  xor     rcx, rsp; StackCookie
0x180025bd2  call    __security_check_cookie
0x180025bd7  lea     r11, [rsp+2A0h+var_10]
0x180025bdf  mov     rsi, [r11+28h]
0x180025be3  mov     rdi, [r11+30h]
0x180025be7  mov     rsp, r11
0x180025bea  pop     r14
0x180025bec  pop     r12
0x180025bee  pop     rbp
0x180025bef  retn
```
