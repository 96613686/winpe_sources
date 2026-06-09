# StRegisterCredProviders(void)

- ea: `0x1800d6f98`
- end: `0x1800d71e0`
- name: `?StRegisterCredProviders@@YAKXZ`
- size: `584`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800415c0`
- `0x1801ff77c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800d6f98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7072`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d70f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d716e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7072`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d70f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d716e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d717f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d718e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d719d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d717f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d718e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d719d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d703b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d70bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d713b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d703b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d70bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d713b`

## pseudocode

```c
__int64 StRegisterCredProviders(void)
{
  unsigned int v0; // ebx
  DWORD dwDisposition; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+38h] BYREF
  HKEY v5; // [rsp+98h] [rbp+40h] BYREF

  hKey = 0;
  phkResult = 0;
  v5 = 0;
  dwDisposition = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 74, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
  }
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{07AA0886-CC8D-4e19-A410-1C75AF686E62}",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         &dwDisposition);
  if ( !v0 && (dwDisposition != 1 || (v0 = RegSetValueExW(hKey, 0, 0, 1u, L"OnexCredentialProvider", 0x2Cu)) == 0) )
  {
    v0 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{33c86cd6-705f-4ba1-9adb-67070b837775}",
           0,
           0,
           0,
           0x20006u,
           0,
           &phkResult,
           &dwDisposition);
    if ( !v0
      && (dwDisposition != 1
       || (v0 = RegSetValueExW(phkResult, 0, 0, 1u, L"OnexPlapSmartcardCredentialProvider", 0x46u)) == 0) )
    {
      v0 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provider Filters\\{edd749de-2ef1-4"
              "a80-98d1-81f20e6df58e}",
             0,
             0,
             0,
             0x20006u,
             0,
             &v5,
             &dwDisposition);
      if ( !v0 && dwDisposition == 1 )
        v0 = RegSetValueExW(v5, 0, 0, 1u, L"PlapLogonProviderFilter", 0x2Eu);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    RegCloseKey(v5);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 75, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x1800d6f98  push    rbp
0x1800d6f9a  push    rbx
0x1800d6f9b  push    r12
0x1800d6f9d  push    r14
0x1800d6f9f  mov     rbp, rsp
0x1800d6fa2  sub     rsp, 58h
0x1800d6fa6  mov     [rbp+hKey], 0
0x1800d6fae  mov     [rbp+arg_10], 0
0x1800d6fb6  mov     [rbp+arg_18], 0
0x1800d6fbe  mov     [rbp+dwDisposition], 0
0x1800d6fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6fcc  lea     r14, WPP_GLOBAL_Control
0x1800d6fd3  cmp     rcx, r14
0x1800d6fd6  jz      short loc_1800D6FF9
0x1800d6fd8  cmp     byte ptr [rcx+69h], 4
0x1800d6fdc  jb      short loc_1800D6FF9
0x1800d6fde  test    byte ptr [rcx+6Ch], 1
0x1800d6fe2  jz      short loc_1800D6FF9
0x1800d6fe4  mov     rcx, [rcx+60h]
0x1800d6fe8  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800d6fef  mov     edx, 4Ah ; 'J'
0x1800d6ff4  call    WPP_SF_
0x1800d6ff9  lea     rax, [rbp+dwDisposition]
0x1800d6ffd  mov     r12, 0FFFFFFFF80000002h
0x1800d7004  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800d7009  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7010  lea     rax, [rbp+hKey]
0x1800d7014  xor     r9d, r9d; lpClass
0x1800d7017  mov     [rsp+58h+phkResult], rax; phkResult
0x1800d701c  xor     r8d, r8d; Reserved
0x1800d701f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d7028  mov     rcx, r12; hKey
0x1800d702b  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800d7033  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800d703b  call    cs:__imp_RegCreateKeyExW
0x1800d7041  mov     ebx, eax
0x1800d7043  test    eax, eax
0x1800d7045  jnz     loc_1800D7176
0x1800d704b  cmp     [rbp+dwDisposition], 1
0x1800d704f  jnz     short loc_1800D7082
0x1800d7051  mov     rcx, [rbp+hKey]; hKey
0x1800d7055  lea     rax, Data; "OnexCredentialProvider"
0x1800d705c  mov     [rsp+58h+samDesired], 2Ch ; ','; cbData
0x1800d7064  lea     r9d, [rbx+1]; dwType
0x1800d7068  xor     r8d, r8d; Reserved
0x1800d706b  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800d7070  xor     edx, edx; lpValueName
0x1800d7072  call    cs:__imp_RegSetValueExW
0x1800d7078  mov     ebx, eax
0x1800d707a  test    eax, eax
0x1800d707c  jnz     loc_1800D7176
0x1800d7082  lea     rax, [rbp+dwDisposition]
0x1800d7086  xor     r9d, r9d; lpClass
0x1800d7089  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800d708e  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7095  lea     rax, [rbp+arg_10]
0x1800d7099  xor     r8d, r8d; Reserved
0x1800d709c  mov     [rsp+58h+phkResult], rax; phkResult
0x1800d70a1  mov     rcx, r12; hKey
0x1800d70a4  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d70ad  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800d70b5  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800d70bd  call    cs:__imp_RegCreateKeyExW
0x1800d70c3  mov     ebx, eax
0x1800d70c5  test    eax, eax
0x1800d70c7  jnz     loc_1800D7176
0x1800d70cd  cmp     [rbp+dwDisposition], 1
0x1800d70d1  jnz     short loc_1800D7100
0x1800d70d3  mov     rcx, [rbp+arg_10]; hKey
0x1800d70d7  lea     rax, aOnexplapsmartc; "OnexPlapSmartcardCredentialProvider"
0x1800d70de  mov     [rsp+58h+samDesired], 46h ; 'F'; cbData
0x1800d70e6  lea     r9d, [rbx+1]; dwType
0x1800d70ea  xor     r8d, r8d; Reserved
0x1800d70ed  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800d70f2  xor     edx, edx; lpValueName
0x1800d70f4  call    cs:__imp_RegSetValueExW
0x1800d70fa  mov     ebx, eax
0x1800d70fc  test    eax, eax
0x1800d70fe  jnz     short loc_1800D7176
0x1800d7100  lea     rax, [rbp+dwDisposition]
0x1800d7104  xor     r9d, r9d; lpClass
0x1800d7107  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800d710c  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7113  lea     rax, [rbp+arg_18]
0x1800d7117  xor     r8d, r8d; Reserved
0x1800d711a  mov     [rsp+58h+phkResult], rax; phkResult
0x1800d711f  mov     rcx, r12; hKey
0x1800d7122  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d712b  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800d7133  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800d713b  call    cs:__imp_RegCreateKeyExW
0x1800d7141  mov     ebx, eax
0x1800d7143  test    eax, eax
0x1800d7145  jnz     short loc_1800D7176
0x1800d7147  cmp     [rbp+dwDisposition], 1
0x1800d714b  jnz     short loc_1800D7176
0x1800d714d  mov     rcx, [rbp+arg_18]; hKey
0x1800d7151  lea     rax, aPlaplogonprovi; "PlapLogonProviderFilter"
0x1800d7158  mov     [rsp+58h+samDesired], 2Eh ; '.'; cbData
0x1800d7160  lea     r9d, [rbx+1]; dwType
0x1800d7164  xor     r8d, r8d; Reserved
0x1800d7167  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800d716c  xor     edx, edx; lpValueName
0x1800d716e  call    cs:__imp_RegSetValueExW
0x1800d7174  mov     ebx, eax
0x1800d7176  mov     rcx, [rbp+hKey]; hKey
0x1800d717a  test    rcx, rcx
0x1800d717d  jz      short loc_1800D7185
0x1800d717f  call    cs:__imp_RegCloseKey
0x1800d7185  mov     rcx, [rbp+arg_10]; hKey
0x1800d7189  test    rcx, rcx
0x1800d718c  jz      short loc_1800D7194
0x1800d718e  call    cs:__imp_RegCloseKey
0x1800d7194  mov     rcx, [rbp+arg_18]; hKey
0x1800d7198  test    rcx, rcx
0x1800d719b  jz      short loc_1800D71A3
0x1800d719d  call    cs:__imp_RegCloseKey
0x1800d71a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d71aa  cmp     rcx, r14
0x1800d71ad  jz      short loc_1800D71D3
0x1800d71af  cmp     byte ptr [rcx+69h], 4
0x1800d71b3  jb      short loc_1800D71D3
0x1800d71b5  test    byte ptr [rcx+6Ch], 1
0x1800d71b9  jz      short loc_1800D71D3
0x1800d71bb  mov     rcx, [rcx+60h]
0x1800d71bf  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800d71c6  mov     edx, 4Bh ; 'K'
0x1800d71cb  mov     r9d, ebx
0x1800d71ce  call    WPP_SF_d
0x1800d71d3  mov     eax, ebx
0x1800d71d5  add     rsp, 58h
0x1800d71d9  pop     r14
0x1800d71db  pop     r12
0x1800d71dd  pop     rbx
0x1800d71de  pop     rbp
0x1800d71df  retn
```
