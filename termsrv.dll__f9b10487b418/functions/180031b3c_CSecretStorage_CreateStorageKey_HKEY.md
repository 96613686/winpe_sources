# CSecretStorage::CreateStorageKey(HKEY__ * *)

- ea: `0x180031b3c`
- end: `0x180031dea`
- name: `?CreateStorageKey@CSecretStorage@@CAJPEAPEAUHKEY__@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a5c0`

## callees

- `0x18000a210`
- `0x180031b3c`
- `0x1800321f0`
- `0x1800330c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031da9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031db9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031dc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031da9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031db9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031dc9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031d6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031d6b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031cef`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180031cef`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031cb4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031cb4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180031bbd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180031c2a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180031bbd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180031c2a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180031c86`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180031c86`

## string_xrefs

- `0x180031d0e`: `SetSecurityDescriptorDacl failed: 0x%x`
- `0x180031bdc`: `AllocateAndInitializeSid failed: 0x%x`
- `0x180031cd3`: `InitializeSecurityDescriptor failed: 0x%x`
- `0x180031d8b`: `CSecretStorage::CreateStorageKey`
- `0x180031c9f`: `SetEntriesInAcl failed: 0x%x in %s`
- `0x180031d84`: `RegCreateKeyEx failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSecretStorage::CreateStorageKey(PHKEY phkResult)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int v4; // eax
  signed int v5; // eax
  signed int LastError; // eax
  LSTATUS v7; // eax
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-98h] BYREF
  PSID hMem; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-60h] BYREF
  int v15; // [rsp+D0h] [rbp-30h]
  int v16; // [rsp+D4h] [rbp-2Ch]
  int v17; // [rsp+ECh] [rbp-14h]
  PSID v18; // [rsp+F8h] [rbp-8h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+100h] [rbp+0h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+108h] [rbp+8h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  hMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  pSid = 0;
  NewAcl = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &hMem)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    memset_0(&pListOfExplicitEntries, 0, 0x60u);
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)hMem;
    pListOfExplicitEntries.grfAccessPermissions = 983103;
    v15 = 983103;
    pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    v16 = 1;
    v17 = 0;
    v18 = pSid;
    v4 = SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
    {
      if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
        {
          SecurityAttributes.nLength = 24;
          SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
          SecurityAttributes.bInheritHandle = 0;
          dwDisposition = 0;
          v7 = RegCreateKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"System\\CurrentControlSet\\Control\\Terminal Server\\RCM\\Secrets",
                 0,
                 0,
                 0,
                 0x20006u,
                 &SecurityAttributes,
                 phkResult,
                 &dwDisposition);
          v3 = v7;
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
          if ( (v3 & 0x80000000) != 0 )
            _DbgPrintMessage(8, "RegCreateKeyEx failed: 0x%x in %s", v3, "CSecretStorage::CreateStorageKey");
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(8, "SetSecurityDescriptorDacl failed: 0x%x", v3);
        }
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
        _DbgPrintMessage(8, "InitializeSecurityDescriptor failed: 0x%x", v3);
      }
    }
    else
    {
      _DbgPrintMessage(8, "SetEntriesInAcl failed: 0x%x in %s", v3, "CSecretStorage::CreateStorageKey");
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    _DbgPrintMessage(8, "AllocateAndInitializeSid failed: 0x%x", v3);
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( hMem )
    LocalFree(hMem);
  if ( pSid )
    LocalFree(pSid);
  return v3;
}

```

## disassembly

```asm
0x180031b3c  push    rbp
0x180031b3e  push    rbx
0x180031b3f  push    rsi
0x180031b40  push    r14
0x180031b42  lea     rbp, [rsp-48h]
0x180031b47  sub     rsp, 148h
0x180031b4e  mov     rax, cs:__security_cookie
0x180031b55  xor     rax, rsp
0x180031b58  mov     [rbp+60h+var_30], rax
0x180031b5c  xor     r14d, r14d
0x180031b5f  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 500h
0x180031b65  xor     eax, eax
0x180031b67  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], r14d
0x180031b6b  mov     qword ptr [rbp+60h+SecurityAttributes.bInheritHandle], rax
0x180031b6f  mov     rsi, rcx
0x180031b72  lea     rax, [rsp+160h+hMem]
0x180031b77  mov     [rsp+160h+hMem], r14
0x180031b7c  mov     [rsp+160h+pSid], rax; pSid
0x180031b81  lea     r8d, [r14+14h]; nSubAuthority0
0x180031b85  mov     [rsp+160h+nSubAuthority7], r14d; nSubAuthority7
0x180031b8a  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x180031b8e  mov     [rsp+160h+nSubAuthority6], r14d; nSubAuthority6
0x180031b93  xorps   xmm0, xmm0
0x180031b96  mov     [rsp+160h+nSubAuthority5], r14d; nSubAuthority5
0x180031b9b  xor     r9d, r9d; nSubAuthority1
0x180031b9e  mov     [rsp+160h+nSubAuthority4], r14d; nSubAuthority4
0x180031ba3  mov     dl, 1; nSubAuthorityCount
0x180031ba5  mov     [rsp+160h+nSubAuthority3], r14d; nSubAuthority3
0x180031baa  mov     [rsp+160h+nSubAuthority2], r14d; nSubAuthority2
0x180031baf  movups  xmmword ptr [rbp+60h+SecurityAttributes.nLength], xmm0
0x180031bb3  mov     [rsp+160h+var_E8], r14
0x180031bb8  mov     [rsp+160h+NewAcl], r14
0x180031bbd  call    cs:__imp_AllocateAndInitializeSid
0x180031bc3  test    eax, eax
0x180031bc5  jnz     short loc_180031BF5
0x180031bc7  call    cs:__imp_GetLastError
0x180031bcd  mov     ebx, eax
0x180031bcf  test    eax, eax
0x180031bd1  jle     short loc_180031BDC
0x180031bd3  movzx   ebx, ax
0x180031bd6  or      ebx, 80070000h
0x180031bdc  lea     rdx, aAllocateandini; "AllocateAndInitializeSid failed: 0x%x"
0x180031be3  mov     r8d, ebx
0x180031be6  mov     ecx, 8; int
0x180031beb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031bf0  jmp     loc_180031D9F
0x180031bf5  lea     rax, [rsp+160h+var_E8]
0x180031bfa  xor     r9d, r9d; nSubAuthority1
0x180031bfd  mov     [rsp+160h+pSid], rax; pSid
0x180031c02  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x180031c06  mov     [rsp+160h+nSubAuthority7], r14d; nSubAuthority7
0x180031c0b  mov     dl, 1; nSubAuthorityCount
0x180031c0d  mov     [rsp+160h+nSubAuthority6], r14d; nSubAuthority6
0x180031c12  mov     [rsp+160h+nSubAuthority5], r14d; nSubAuthority5
0x180031c17  lea     r8d, [r9+12h]; nSubAuthority0
0x180031c1b  mov     [rsp+160h+nSubAuthority4], r14d; nSubAuthority4
0x180031c20  mov     [rsp+160h+nSubAuthority3], r14d; nSubAuthority3
0x180031c25  mov     [rsp+160h+nSubAuthority2], r14d; nSubAuthority2
0x180031c2a  call    cs:__imp_AllocateAndInitializeSid
0x180031c30  test    eax, eax
0x180031c32  jz      short loc_180031BC7
0x180031c34  xor     edx, edx; Val
0x180031c36  lea     rcx, [rbp+60h+pListOfExplicitEntries]; void *
0x180031c3a  lea     r8d, [rdx+60h]; Size
0x180031c3e  call    memset_0
0x180031c43  mov     rax, [rsp+160h+hMem]
0x180031c48  lea     r9, [rsp+160h+NewAcl]; NewAcl
0x180031c4d  mov     ecx, 0F003Fh
0x180031c52  mov     [rbp+60h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180031c56  mov     rax, [rsp+160h+var_E8]
0x180031c5b  lea     rdx, [rbp+60h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180031c5f  xor     r8d, r8d; OldAcl
0x180031c62  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180031c65  mov     [rbp+60h+var_90], ecx
0x180031c68  mov     [rbp+60h+pListOfExplicitEntries.grfAccessMode], 1
0x180031c6f  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180031c73  lea     ecx, [r8+2]; cCountOfExplicitEntries
0x180031c77  mov     [rbp+60h+var_8C], 1
0x180031c7e  mov     [rbp+60h+var_74], r14d
0x180031c82  mov     [rbp+60h+var_68], rax
0x180031c86  call    cs:__imp_SetEntriesInAclW
0x180031c8c  mov     ebx, eax
0x180031c8e  test    eax, eax
0x180031c90  jle     short loc_180031C9B
0x180031c92  movzx   ebx, ax
0x180031c95  or      ebx, 80070000h
0x180031c9b  test    ebx, ebx
0x180031c9d  jns     short loc_180031CAB
0x180031c9f  lea     rdx, aSetentriesinac_0; "SetEntriesInAcl failed: 0x%x in %s"
0x180031ca6  jmp     loc_180031D8B
0x180031cab  mov     edx, 1; dwRevision
0x180031cb0  lea     rcx, [rbp+60h+pSecurityDescriptor]; pSecurityDescriptor
0x180031cb4  call    cs:__imp_InitializeSecurityDescriptor
0x180031cba  test    eax, eax
0x180031cbc  jnz     short loc_180031CDF
0x180031cbe  call    cs:__imp_GetLastError
0x180031cc4  mov     ebx, eax
0x180031cc6  test    eax, eax
0x180031cc8  jle     short loc_180031CD3
0x180031cca  movzx   ebx, ax
0x180031ccd  or      ebx, 80070000h
0x180031cd3  lea     rdx, aInitializesecu; "InitializeSecurityDescriptor failed: 0x"...
0x180031cda  jmp     loc_180031BE3
0x180031cdf  mov     r8, [rsp+160h+NewAcl]; pDacl
0x180031ce4  lea     rcx, [rbp+60h+pSecurityDescriptor]; pSecurityDescriptor
0x180031ce8  xor     r9d, r9d; bDaclDefaulted
0x180031ceb  lea     edx, [r9+1]; bDaclPresent
0x180031cef  call    cs:__imp_SetSecurityDescriptorDacl
0x180031cf5  test    eax, eax
0x180031cf7  jnz     short loc_180031D1A
0x180031cf9  call    cs:__imp_GetLastError
0x180031cff  mov     ebx, eax
0x180031d01  test    eax, eax
0x180031d03  jle     short loc_180031D0E
0x180031d05  movzx   ebx, ax
0x180031d08  or      ebx, 80070000h
0x180031d0e  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorDacl failed: 0x%x"
0x180031d15  jmp     loc_180031BE3
0x180031d1a  lea     rax, [rbp+60h+pSecurityDescriptor]
0x180031d1e  mov     [rbp+60h+SecurityAttributes.nLength], 18h
0x180031d25  mov     [rbp+60h+SecurityAttributes.lpSecurityDescriptor], rax
0x180031d29  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x180031d30  lea     rax, [rsp+160h+dwDisposition]
0x180031d35  mov     [rbp+60h+SecurityAttributes.bInheritHandle], r14d
0x180031d39  mov     qword ptr [rsp+160h+nSubAuthority6], rax; lpdwDisposition
0x180031d3e  xor     r9d, r9d; lpClass
0x180031d41  mov     qword ptr [rsp+160h+nSubAuthority5], rsi; phkResult
0x180031d46  lea     rax, [rbp+60h+SecurityAttributes]
0x180031d4a  mov     qword ptr [rsp+160h+nSubAuthority4], rax; lpSecurityAttributes
0x180031d4f  xor     r8d, r8d; Reserved
0x180031d52  mov     [rsp+160h+nSubAuthority3], 20006h; samDesired
0x180031d5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031d61  mov     [rsp+160h+nSubAuthority2], r14d; dwOptions
0x180031d66  mov     [rsp+160h+dwDisposition], r14d
0x180031d6b  call    cs:__imp_RegCreateKeyExW
0x180031d71  mov     ebx, eax
0x180031d73  test    eax, eax
0x180031d75  jle     short loc_180031D80
0x180031d77  movzx   ebx, ax
0x180031d7a  or      ebx, 80070000h
0x180031d80  test    ebx, ebx
0x180031d82  jns     short loc_180031D9F
0x180031d84  lea     rdx, aRegcreatekeyex; "RegCreateKeyEx failed: 0x%x in %s"
0x180031d8b  lea     r9, aCsecretstorage_0; "CSecretStorage::CreateStorageKey"
0x180031d92  mov     r8d, ebx
0x180031d95  mov     ecx, 8; int
0x180031d9a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031d9f  mov     rcx, [rsp+160h+NewAcl]; hMem
0x180031da4  test    rcx, rcx
0x180031da7  jz      short loc_180031DAF
0x180031da9  call    cs:__imp_LocalFree
0x180031daf  mov     rcx, [rsp+160h+hMem]; hMem
0x180031db4  test    rcx, rcx
0x180031db7  jz      short loc_180031DBF
0x180031db9  call    cs:__imp_LocalFree
0x180031dbf  mov     rcx, [rsp+160h+var_E8]; hMem
0x180031dc4  test    rcx, rcx
0x180031dc7  jz      short loc_180031DCF
0x180031dc9  call    cs:__imp_LocalFree
0x180031dcf  mov     eax, ebx
0x180031dd1  mov     rcx, [rbp+60h+var_30]
0x180031dd5  xor     rcx, rsp; StackCookie
0x180031dd8  call    __security_check_cookie
0x180031ddd  add     rsp, 148h
0x180031de4  pop     r14
0x180031de6  pop     rsi
0x180031de7  pop     rbx
0x180031de8  pop     rbp
0x180031de9  retn
```
