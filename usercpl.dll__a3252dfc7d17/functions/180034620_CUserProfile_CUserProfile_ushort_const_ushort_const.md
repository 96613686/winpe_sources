# CUserProfile::CUserProfile(ushort const *,ushort const *)

- ea: `0x180034620`
- end: `0x18003477b`
- name: `??0CUserProfile@@QEAA@PEBG0@Z`
- size: `347`
- prototype: `CUserProfile *__fastcall(_BYTE *phkResult, LPCWSTR lpAccountName, LPCWSTR DomainName)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e180`
- `0x18002f1f0`

## callees

- `0x180034620`
- `0x180034810`
- `0x1800348dc`
- `0x18006e628`
- `0x18006e6f8`
- `0x1800772c0`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x180034704`
- `SHLWAPI!PathAppendW` at `0x180034704`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003474e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003474e`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180034719`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180034719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800346ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003473b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800346ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003473b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180034684`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180034684`
- `KERNEL32!lstrlenW` at `0x1800346d1`
- `KERNEL32!lstrlenW` at `0x1800346d1`

## string_xrefs

- `0x1800346e7`: `SeRestorePrivilege`

## pseudocode

```c
CUserProfile *__fastcall CUserProfile::CUserProfile(_BYTE *phkResult, LPCWSTR lpAccountName, LPCWSTR DomainName)
{
  LPCWSTR *v3; // rdi
  void *v5; // rax
  void *v6; // rsi
  const WCHAR *v7; // rdx
  _BYTE v9[32]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-238h] BYREF

  *(_QWORD *)phkResult = 0;
  v3 = (LPCWSTR *)(phkResult + 8);
  *((_QWORD *)phkResult + 1) = 0;
  phkResult[16] = 0;
  if ( lpAccountName )
  {
    v5 = CUserProfile::UsernameToSID(lpAccountName, DomainName);
    v6 = v5;
    if ( v5 )
    {
      if ( ConvertSidToStringSidW(v5, (LPWSTR *)v3)
        && RegOpenKeyExW(HKEY_USERS, *v3, 0, 0xF003Fu, (PHKEY)phkResult)
        && CUserProfile::SIDStringToProfilePath(*v3, String)
        && (unsigned __int64)(lstrlenW(String) + 12LL) < 0x104 )
      {
        CAutoPrivilegeEnable::CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v9, L"SeRestorePrivilege");
        if ( PathAppendW(String, L"ntuser.dat") && !RegLoadKeyW(HKEY_USERS, *v3, String) )
        {
          v7 = *v3;
          phkResult[16] = 1;
          RegOpenKeyExW(HKEY_USERS, v7, 0, 0xF003Fu, (PHKEY)phkResult);
        }
        CAutoPrivilegeEnable::~CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v9);
      }
      LocalFree(v6);
    }
  }
  return (CUserProfile *)phkResult;
}

```

## disassembly

```asm
0x180034620  mov     [rsp+arg_18], rbx
0x180034625  push    rsi
0x180034626  push    rdi
0x180034627  push    r14
0x180034629  sub     rsp, 270h
0x180034630  mov     rax, cs:__security_cookie
0x180034637  xor     rax, rsp
0x18003463a  mov     [rsp+288h+var_28], rax
0x180034642  mov     qword ptr [rcx], 0
0x180034649  lea     rdi, [rcx+8]
0x18003464d  mov     qword ptr [rdi], 0
0x180034654  mov     rax, rdx
0x180034657  mov     byte ptr [rcx+10h], 0
0x18003465b  mov     rbx, rcx
0x18003465e  test    rdx, rdx
0x180034661  jz      loc_180034754
0x180034667  mov     rdx, r8; DomainName
0x18003466a  mov     rcx, rax; lpAccountName
0x18003466d  call    ?UsernameToSID@CUserProfile@@CAPEAXPEBG0@Z; CUserProfile::UsernameToSID(ushort const *,ushort const *)
0x180034672  mov     rsi, rax
0x180034675  test    rax, rax
0x180034678  jz      loc_180034754
0x18003467e  mov     rdx, rdi; StringSid
0x180034681  mov     rcx, rax; Sid
0x180034684  call    cs:__imp_ConvertSidToStringSidW
0x18003468a  test    eax, eax
0x18003468c  jz      loc_18003474B
0x180034692  mov     rdx, [rdi]; lpSubKey
0x180034695  mov     r14, 0FFFFFFFF80000003h
0x18003469c  mov     rcx, r14; hKey
0x18003469f  mov     [rsp+288h+phkResult], rbx; phkResult
0x1800346a4  mov     r9d, 0F003Fh; samDesired
0x1800346aa  xor     r8d, r8d; ulOptions
0x1800346ad  call    cs:__imp_RegOpenKeyExW
0x1800346b3  test    eax, eax
0x1800346b5  jz      loc_18003474B
0x1800346bb  mov     rcx, [rdi]; pszSubKey
0x1800346be  lea     rdx, [rsp+288h+String]; pvData
0x1800346c3  call    ?SIDStringToProfilePath@CUserProfile@@CA_NPEBGPEAG@Z; CUserProfile::SIDStringToProfilePath(ushort const *,ushort *)
0x1800346c8  test    al, al
0x1800346ca  jz      short loc_18003474B
0x1800346cc  lea     rcx, [rsp+288h+String]; lpString
0x1800346d1  call    cs:__imp_lstrlenW
0x1800346d7  movsxd  rcx, eax
0x1800346da  add     rcx, 0Ch
0x1800346de  cmp     rcx, 104h
0x1800346e5  jnb     short loc_18003474B
0x1800346e7  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x1800346ee  lea     rcx, [rsp+288h+var_258]; this
0x1800346f3  call    ??0CAutoPrivilegeEnable@@QEAA@PEBG@Z; CAutoPrivilegeEnable::CAutoPrivilegeEnable(ushort const *)
0x1800346f8  lea     rdx, ?s_szUserHiveFilename@CUserProfile@@0QBGB; "ntuser.dat"
0x1800346ff  lea     rcx, [rsp+288h+String]; pszPath
0x180034704  call    cs:__imp_PathAppendW
0x18003470a  test    eax, eax
0x18003470c  jz      short loc_180034741
0x18003470e  mov     rdx, [rdi]; lpSubKey
0x180034711  lea     r8, [rsp+288h+String]; lpFile
0x180034716  mov     rcx, r14; hKey
0x180034719  call    cs:__imp_RegLoadKeyW
0x18003471f  test    eax, eax
0x180034721  jnz     short loc_180034741
0x180034723  mov     rdx, [rdi]; lpSubKey
0x180034726  mov     r9d, 0F003Fh; samDesired
0x18003472c  xor     r8d, r8d; ulOptions
0x18003472f  mov     byte ptr [rbx+10h], 1
0x180034733  mov     rcx, r14; hKey
0x180034736  mov     [rsp+288h+phkResult], rbx; phkResult
0x18003473b  call    cs:__imp_RegOpenKeyExW
0x180034741  lea     rcx, [rsp+288h+var_258]; this
0x180034746  call    ??1CAutoPrivilegeEnable@@QEAA@XZ; CAutoPrivilegeEnable::~CAutoPrivilegeEnable(void)
0x18003474b  mov     rcx, rsi; hMem
0x18003474e  call    cs:__imp_LocalFree
0x180034754  mov     rax, rbx
0x180034757  mov     rcx, [rsp+288h+var_28]
0x18003475f  xor     rcx, rsp; StackCookie
0x180034762  call    __security_check_cookie
0x180034767  mov     rbx, [rsp+288h+arg_18]
0x18003476f  add     rsp, 270h
0x180034776  pop     r14
0x180034778  pop     rdi
0x180034779  pop     rsi
0x18003477a  retn
```
