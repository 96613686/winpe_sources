# FetchAutoLogonCredentials(_WLSM_GLOBAL_CONTEXT *,ushort *,ulong,int *,ushort *,ulong,ushort *,ulong)

- ea: `0x140089ba0`
- end: `0x140089f21`
- name: `?FetchAutoLogonCredentials@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@PEAGKPEAH1K1K@Z`
- size: `897`
- prototype: `int(struct _WLSM_GLOBAL_CONTEXT *, unsigned __int16 *, unsigned int, int *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140016284`

## callees

- `0x140037b00`
- `0x140053720`
- `0x140089ba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140089dac`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140089dda`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140089dac`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140089dda`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140089dbc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140089dbc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089ce8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089d8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089e16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089ea8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089ce8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089d8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089e16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089ea8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140089c34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140089c34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140089c7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140089d26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140089c7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140089d26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140089e31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140089e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140089e41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140089e41`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140089ec0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140089ec0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140089f01`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140089f01`

## string_xrefs

- `0x140089e82`: `DefaultUserSid`

## pseudocode

```c
__int64 __fastcall FetchAutoLogonCredentials(
        CSession **a1,
        unsigned __int16 *a2,
        __int64 a3,
        int *a4,
        unsigned __int16 *pvData,
        unsigned int a6,
        unsigned __int16 *a7)
{
  unsigned int v10; // ebx
  int v11; // eax
  LSTATUS ValueW; // r15d
  wchar_t *v13; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+5Ch] [rbp-A4h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR StringSid[256]; // [rsp+70h] [rbp-90h] BYREF

  peUse = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cchReferencedDomainName = 0;
  cchName = 0;
  cbData = 0;
  hKey = 0;
  hMem = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 1u, &hKey) )
  {
    hKey = 0;
    v10 = 0;
    goto LABEL_23;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"ForceAutoLogon", 0, &Type, Data, &cbData) )
    goto LABEL_20;
  if ( Type == 1 )
  {
    if ( *(_WORD *)Data != 48 )
    {
      *(_DWORD *)Data = 1;
      goto LABEL_10;
    }
    v11 = 0;
    *(_DWORD *)Data = 0;
  }
  else
  {
    v11 = *(_DWORD *)Data;
  }
  if ( !v11 )
    goto LABEL_20;
LABEL_10:
  cbData = 520;
  ValueW = RegGetValueW(hKey, 0, L"DefaultUserName", 2u, 0, a2, &cbData);
  *(_DWORD *)Data = 0;
  cbData = 4;
  RegQueryValueExW(hKey, L"ForceDefaultUserName", 0, &Type, Data, &cbData);
  if ( (!(unsigned int)CSession::IsBoundToConsole(a1[2]) && !*((_DWORD *)a1[2] + 61) || *(_DWORD *)Data) && !ValueW )
  {
    cbData = 520;
    if ( RegGetValueW(hKey, 0, L"DefaultDomainName", 2u, 0, pvData, &cbData) )
    {
      _o_wcscpy_s(pvData, 260, a2);
      v13 = wcsstr(pvData, L"\\");
      if ( v13 )
      {
        *a4 = 1;
        *v13 = 0;
        _o_wcscpy_s(a2, 260, v13 + 1);
      }
      else
      {
        *pvData = 0;
        *a4 = 0;
      }
    }
    else
    {
      *a4 = 1;
    }
    cbData = 520;
    if ( RegGetValueW(hKey, 0, L"DefaultPassword", 2u, 0, a7, &cbData) )
      goto LABEL_20;
    goto LABEL_30;
  }
  cbData = 512;
  if ( RegGetValueW(hKey, 0, L"DefaultUserSid", 2u, 0, StringSid, &cbData) )
  {
LABEL_20:
    v10 = 0;
    goto LABEL_21;
  }
  v10 = ConvertStringSidToSidW(StringSid, &hMem);
  if ( v10 )
  {
    cchName = 260;
    cchReferencedDomainName = 260;
    v10 = LookupAccountSidLocalW(hMem, a2, &cchName, pvData, &cchReferencedDomainName, &peUse);
    if ( v10 )
    {
      *a4 = 1;
LABEL_30:
      v10 = 1;
    }
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_23:
  if ( hMem )
    LocalFree(hMem);
  return v10;
}

```

## disassembly

```asm
0x140089ba0  mov     [rsp-8+arg_0], rbx
0x140089ba5  push    rbp
0x140089ba6  push    rsi
0x140089ba7  push    rdi
0x140089ba8  push    r12
0x140089baa  push    r13
0x140089bac  push    r14
0x140089bae  push    r15
0x140089bb0  lea     rbp, [rsp-180h]
0x140089bb8  sub     rsp, 280h
0x140089bbf  mov     rax, cs:__security_cookie
0x140089bc6  xor     rax, rsp
0x140089bc9  mov     [rbp+1B0h+var_40], rax
0x140089bd0  mov     rsi, [rbp+1B0h+pvData]
0x140089bd7  lea     rax, [rsp+2B0h+hKey]
0x140089bdc  mov     r12, [rbp+1B0h+arg_30]
0x140089be3  xor     r13d, r13d
0x140089be6  mov     rdi, r9
0x140089be9  mov     [rsp+2B0h+peUse], r13d
0x140089bee  mov     r14, rdx
0x140089bf1  mov     dword ptr [rsp+2B0h+Data], r13d
0x140089bf6  mov     rbx, rcx
0x140089bf9  mov     [rsp+2B0h+Type], r13d
0x140089bfe  lea     r15d, [r13+1]
0x140089c02  mov     [rsp+2B0h+cchReferencedDomainName], r13d
0x140089c07  mov     r9d, r15d; samDesired
0x140089c0a  mov     [rsp+2B0h+cchName], r13d
0x140089c0f  xor     r8d, r8d; ulOptions
0x140089c12  mov     [rsp+2B0h+cbData], r13d
0x140089c17  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140089c1e  mov     [rsp+2B0h+hKey], r13
0x140089c23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140089c2a  mov     [rsp+2B0h+hMem], r13
0x140089c2f  mov     [rsp+2B0h+phkResult], rax; phkResult
0x140089c34  call    cs:__imp_RegOpenKeyExW
0x140089c3a  test    eax, eax
0x140089c3c  jz      short loc_140089C4B
0x140089c3e  mov     [rsp+2B0h+hKey], r13
0x140089c43  mov     ebx, r13d
0x140089c46  jmp     loc_140089E37
0x140089c4b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140089c50  lea     rax, [rsp+2B0h+cbData]
0x140089c55  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x140089c5a  lea     r9, [rsp+2B0h+Type]; lpType
0x140089c5f  lea     rax, [rsp+2B0h+Data]
0x140089c64  mov     [rsp+2B0h+cbData], 4
0x140089c6c  xor     r8d, r8d; lpReserved
0x140089c6f  mov     [rsp+2B0h+phkResult], rax; lpData
0x140089c74  lea     rdx, aForceautologon; "ForceAutoLogon"
0x140089c7b  call    cs:__imp_RegQueryValueExW
0x140089c81  test    eax, eax
0x140089c83  jnz     loc_140089E24
0x140089c89  cmp     [rsp+2B0h+Type], r15d
0x140089c8e  jnz     short loc_140089CAC
0x140089c90  mov     eax, 30h ; '0'
0x140089c95  cmp     ax, word ptr [rsp+2B0h+Data]
0x140089c9a  jz      short loc_140089CA3
0x140089c9c  mov     dword ptr [rsp+2B0h+Data], r15d
0x140089ca1  jmp     short loc_140089CB8
0x140089ca3  mov     eax, r13d
0x140089ca6  mov     dword ptr [rsp+2B0h+Data], eax
0x140089caa  jmp     short loc_140089CB0
0x140089cac  mov     eax, dword ptr [rsp+2B0h+Data]
0x140089cb0  test    eax, eax
0x140089cb2  jz      loc_140089E24
0x140089cb8  mov     rcx, [rsp+2B0h+hKey]; hkey
0x140089cbd  lea     rax, [rsp+2B0h+cbData]
0x140089cc2  mov     [rsp+2B0h+pcbData], rax; pcbData
0x140089cc7  lea     r8, aDefaultusernam; "DefaultUserName"
0x140089cce  mov     [rsp+2B0h+lpcbData], r14; pvData
0x140089cd3  mov     r9d, 2; dwFlags
0x140089cd9  xor     edx, edx; lpSubKey
0x140089cdb  mov     [rsp+2B0h+phkResult], r13; pdwType
0x140089ce0  mov     [rsp+2B0h+cbData], 208h
0x140089ce8  call    cs:__imp_RegGetValueW
0x140089cee  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140089cf3  lea     r9, [rsp+2B0h+Type]; lpType
0x140089cf8  mov     r15d, eax
0x140089cfb  mov     dword ptr [rsp+2B0h+Data], r13d
0x140089d00  lea     rax, [rsp+2B0h+cbData]
0x140089d05  mov     [rsp+2B0h+cbData], 4
0x140089d0d  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x140089d12  lea     rdx, aForcedefaultus; "ForceDefaultUserName"
0x140089d19  lea     rax, [rsp+2B0h+Data]
0x140089d1e  xor     r8d, r8d; lpReserved
0x140089d21  mov     [rsp+2B0h+phkResult], rax; lpData
0x140089d26  call    cs:__imp_RegQueryValueExW
0x140089d2c  mov     rcx, [rbx+10h]; this
0x140089d30  call    ?IsBoundToConsole@CSession@@QEAAHXZ; CSession::IsBoundToConsole(void)
0x140089d35  test    eax, eax
0x140089d37  jnz     short loc_140089D46
0x140089d39  mov     rax, [rbx+10h]
0x140089d3d  cmp     [rax+0F4h], r13d
0x140089d44  jz      short loc_140089D51
0x140089d46  cmp     dword ptr [rsp+2B0h+Data], r13d
0x140089d4b  jz      loc_140089E73
0x140089d51  test    r15d, r15d
0x140089d54  jnz     loc_140089E73
0x140089d5a  mov     rcx, [rsp+2B0h+hKey]; hkey
0x140089d5f  lea     rax, [rsp+2B0h+cbData]
0x140089d64  mov     [rsp+2B0h+pcbData], rax; pcbData
0x140089d69  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x140089d70  mov     r15d, 208h
0x140089d76  mov     [rsp+2B0h+lpcbData], rsi; pvData
0x140089d7b  mov     r9d, 2; dwFlags
0x140089d81  mov     [rsp+2B0h+phkResult], r13; pdwType
0x140089d86  xor     edx, edx; lpSubKey
0x140089d88  mov     [rsp+2B0h+cbData], r15d
0x140089d8d  call    cs:__imp_RegGetValueW
0x140089d93  test    eax, eax
0x140089d95  jnz     short loc_140089D9F
0x140089d97  mov     dword ptr [rdi], 1
0x140089d9d  jmp     short loc_140089DE9
0x140089d9f  mov     ebx, 104h
0x140089da4  mov     r8, r14
0x140089da7  mov     edx, ebx
0x140089da9  mov     rcx, rsi
0x140089dac  call    cs:__imp__o_wcscpy_s
0x140089db2  lea     rdx, SubStr; "\\"
0x140089db9  mov     rcx, rsi; Str
0x140089dbc  call    cs:__imp_wcsstr
0x140089dc2  test    rax, rax
0x140089dc5  jz      short loc_140089DE2
0x140089dc7  mov     dword ptr [rdi], 1
0x140089dcd  lea     r8, [rax+2]
0x140089dd1  mov     edx, ebx
0x140089dd3  mov     [rax], r13w
0x140089dd7  mov     rcx, r14
0x140089dda  call    cs:__imp__o_wcscpy_s
0x140089de0  jmp     short loc_140089DE9
0x140089de2  mov     [rsi], r13w
0x140089de6  mov     [rdi], r13d
0x140089de9  mov     rcx, [rsp+2B0h+hKey]; hkey
0x140089dee  lea     rax, [rsp+2B0h+cbData]
0x140089df3  mov     [rsp+2B0h+pcbData], rax; pcbData
0x140089df8  lea     r8, aDefaultpasswor; "DefaultPassword"
0x140089dff  mov     [rsp+2B0h+lpcbData], r12; pvData
0x140089e04  mov     r9d, 2; dwFlags
0x140089e0a  xor     edx, edx; lpSubKey
0x140089e0c  mov     [rsp+2B0h+phkResult], r13; pdwType
0x140089e11  mov     [rsp+2B0h+cbData], r15d
0x140089e16  call    cs:__imp_RegGetValueW
0x140089e1c  test    eax, eax
0x140089e1e  jz      loc_140089F17
0x140089e24  mov     ebx, r13d
0x140089e27  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140089e2c  test    rcx, rcx
0x140089e2f  jz      short loc_140089E37
0x140089e31  call    cs:__imp_RegCloseKey
0x140089e37  mov     rcx, [rsp+2B0h+hMem]; hMem
0x140089e3c  test    rcx, rcx
0x140089e3f  jz      short loc_140089E47
0x140089e41  call    cs:__imp_LocalFree
0x140089e47  mov     eax, ebx
0x140089e49  mov     rcx, [rbp+1B0h+var_40]
0x140089e50  xor     rcx, rsp; StackCookie
0x140089e53  call    __security_check_cookie
0x140089e58  mov     rbx, [rsp+2B0h+arg_0]
0x140089e60  add     rsp, 280h
0x140089e67  pop     r15
0x140089e69  pop     r14
0x140089e6b  pop     r13
0x140089e6d  pop     r12
0x140089e6f  pop     rdi
0x140089e70  pop     rsi
0x140089e71  pop     rbp
0x140089e72  retn
0x140089e73  mov     rcx, [rsp+2B0h+hKey]; hkey
0x140089e78  lea     rax, [rsp+2B0h+cbData]
0x140089e7d  mov     [rsp+2B0h+pcbData], rax; pcbData
0x140089e82  lea     r8, aDefaultusersid; "DefaultUserSid"
0x140089e89  lea     rax, [rsp+2B0h+StringSid]
0x140089e8e  mov     [rsp+2B0h+cbData], 200h
0x140089e96  mov     [rsp+2B0h+lpcbData], rax; pvData
0x140089e9b  mov     r9d, 2; dwFlags
0x140089ea1  xor     edx, edx; lpSubKey
0x140089ea3  mov     [rsp+2B0h+phkResult], r13; pdwType
0x140089ea8  call    cs:__imp_RegGetValueW
0x140089eae  test    eax, eax
0x140089eb0  jnz     loc_140089E24
0x140089eb6  lea     rdx, [rsp+2B0h+hMem]; Sid
0x140089ebb  lea     rcx, [rsp+2B0h+StringSid]; StringSid
0x140089ec0  call    cs:__imp_ConvertStringSidToSidW
0x140089ec6  mov     ebx, eax
0x140089ec8  test    eax, eax
0x140089eca  jz      loc_140089E27
0x140089ed0  mov     rcx, [rsp+2B0h+hMem]; Sid
0x140089ed5  lea     rax, [rsp+2B0h+peUse]
0x140089eda  mov     [rsp+2B0h+lpcbData], rax; peUse
0x140089edf  lea     r8, [rsp+2B0h+cchName]; cchName
0x140089ee4  lea     rax, [rsp+2B0h+cchReferencedDomainName]
0x140089ee9  mov     ebx, 104h
0x140089eee  mov     r9, rsi; ReferencedDomainName
0x140089ef1  mov     [rsp+2B0h+phkResult], rax; cchReferencedDomainName
0x140089ef6  mov     rdx, r14; Name
0x140089ef9  mov     [rsp+2B0h+cchName], ebx
0x140089efd  mov     [rsp+2B0h+cchReferencedDomainName], ebx
0x140089f01  call    cs:__imp_LookupAccountSidLocalW
0x140089f07  mov     ebx, eax
0x140089f09  test    eax, eax
0x140089f0b  jz      loc_140089E27
0x140089f11  mov     dword ptr [rdi], 1
0x140089f17  mov     ebx, 1
0x140089f1c  jmp     loc_140089E27
```
