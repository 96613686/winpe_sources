# CSecretStorage::CreateStorageKey(HKEY__ * *)

- ea: `0x180033854`
- end: `0x180033b4b`
- name: `?CreateStorageKey@CSecretStorage@@CAJPEAPEAUHKEY__@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bc98`

## callees

- `0x180009940`
- `0x180033854`
- `0x180033f60`
- `0x180034e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b23`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033ab3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033ab3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180033a2b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180033a2b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800339e4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800339e4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800338d5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003394e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800338d5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003394e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800339b0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800339b0`

## string_xrefs

- `0x180033a56`: `SetSecurityDescriptorDacl failed: 0x%x`
- `0x180033900`: `AllocateAndInitializeSid failed: 0x%x`
- `0x180033a0f`: `InitializeSecurityDescriptor failed: 0x%x`
- `0x180033ad9`: `CSecretStorage::CreateStorageKey`
- `0x1800339cf`: `SetEntriesInAcl failed: 0x%x in %s`
- `0x180033ad2`: `RegCreateKeyEx failed: 0x%x in %s`

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
0x180033854  push    rbp
0x180033856  push    rbx
0x180033857  push    rsi
0x180033858  push    r14
0x18003385a  lea     rbp, [rsp-48h]
0x18003385f  sub     rsp, 148h
0x180033866  mov     rax, cs:__security_cookie
0x18003386d  xor     rax, rsp
0x180033870  mov     [rbp+60h+var_30], rax
0x180033874  xor     r14d, r14d
0x180033877  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 500h
0x18003387d  xor     eax, eax
0x18003387f  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], r14d
0x180033883  mov     qword ptr [rbp+60h+SecurityAttributes.bInheritHandle], rax
0x180033887  mov     rsi, rcx
0x18003388a  lea     rax, [rsp+160h+hMem]
0x18003388f  mov     [rsp+160h+hMem], r14
0x180033894  mov     [rsp+160h+pSid], rax; pSid
0x180033899  lea     r8d, [r14+14h]; nSubAuthority0
0x18003389d  mov     [rsp+160h+nSubAuthority7], r14d; nSubAuthority7
0x1800338a2  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x1800338a6  mov     [rsp+160h+nSubAuthority6], r14d; nSubAuthority6
0x1800338ab  xorps   xmm0, xmm0
0x1800338ae  mov     [rsp+160h+nSubAuthority5], r14d; nSubAuthority5
0x1800338b3  xor     r9d, r9d; nSubAuthority1
0x1800338b6  mov     [rsp+160h+nSubAuthority4], r14d; nSubAuthority4
0x1800338bb  mov     dl, 1; nSubAuthorityCount
0x1800338bd  mov     [rsp+160h+nSubAuthority3], r14d; nSubAuthority3
0x1800338c2  mov     [rsp+160h+nSubAuthority2], r14d; nSubAuthority2
0x1800338c7  movups  xmmword ptr [rbp+60h+SecurityAttributes.nLength], xmm0
0x1800338cb  mov     [rsp+160h+var_E8], r14
0x1800338d0  mov     [rsp+160h+NewAcl], r14
0x1800338d5  call    cs:__imp_AllocateAndInitializeSid
0x1800338dc  nop     dword ptr [rax+rax+00h]
0x1800338e1  test    eax, eax
0x1800338e3  jnz     short loc_180033919
0x1800338e5  call    cs:__imp_GetLastError
0x1800338ec  nop     dword ptr [rax+rax+00h]
0x1800338f1  mov     ebx, eax
0x1800338f3  test    eax, eax
0x1800338f5  jle     short loc_180033900
0x1800338f7  movzx   ebx, ax
0x1800338fa  or      ebx, 80070000h
0x180033900  lea     rdx, aAllocateandini; "AllocateAndInitializeSid failed: 0x%x"
0x180033907  mov     r8d, ebx
0x18003390a  mov     ecx, 8; int
0x18003390f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033914  jmp     loc_180033AED
0x180033919  lea     rax, [rsp+160h+var_E8]
0x18003391e  xor     r9d, r9d; nSubAuthority1
0x180033921  mov     [rsp+160h+pSid], rax; pSid
0x180033926  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x18003392a  mov     [rsp+160h+nSubAuthority7], r14d; nSubAuthority7
0x18003392f  mov     dl, 1; nSubAuthorityCount
0x180033931  mov     [rsp+160h+nSubAuthority6], r14d; nSubAuthority6
0x180033936  mov     [rsp+160h+nSubAuthority5], r14d; nSubAuthority5
0x18003393b  lea     r8d, [r9+12h]; nSubAuthority0
0x18003393f  mov     [rsp+160h+nSubAuthority4], r14d; nSubAuthority4
0x180033944  mov     [rsp+160h+nSubAuthority3], r14d; nSubAuthority3
0x180033949  mov     [rsp+160h+nSubAuthority2], r14d; nSubAuthority2
0x18003394e  call    cs:__imp_AllocateAndInitializeSid
0x180033955  nop     dword ptr [rax+rax+00h]
0x18003395a  test    eax, eax
0x18003395c  jz      short loc_1800338E5
0x18003395e  xor     edx, edx; Val
0x180033960  lea     rcx, [rbp+60h+pListOfExplicitEntries]; void *
0x180033964  lea     r8d, [rdx+60h]; Size
0x180033968  call    memset_0
0x18003396d  mov     rax, [rsp+160h+hMem]
0x180033972  lea     r9, [rsp+160h+NewAcl]; NewAcl
0x180033977  mov     ecx, 0F003Fh
0x18003397c  mov     [rbp+60h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180033980  mov     rax, [rsp+160h+var_E8]
0x180033985  lea     rdx, [rbp+60h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180033989  xor     r8d, r8d; OldAcl
0x18003398c  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x18003398f  mov     [rbp+60h+var_90], ecx
0x180033992  mov     [rbp+60h+pListOfExplicitEntries.grfAccessMode], 1
0x180033999  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x18003399d  lea     ecx, [r8+2]; cCountOfExplicitEntries
0x1800339a1  mov     [rbp+60h+var_8C], 1
0x1800339a8  mov     [rbp+60h+var_74], r14d
0x1800339ac  mov     [rbp+60h+var_68], rax
0x1800339b0  call    cs:__imp_SetEntriesInAclW
0x1800339b7  nop     dword ptr [rax+rax+00h]
0x1800339bc  mov     ebx, eax
0x1800339be  test    eax, eax
0x1800339c0  jle     short loc_1800339CB
0x1800339c2  movzx   ebx, ax
0x1800339c5  or      ebx, 80070000h
0x1800339cb  test    ebx, ebx
0x1800339cd  jns     short loc_1800339DB
0x1800339cf  lea     rdx, aSetentriesinac_0; "SetEntriesInAcl failed: 0x%x in %s"
0x1800339d6  jmp     loc_180033AD9
0x1800339db  mov     edx, 1; dwRevision
0x1800339e0  lea     rcx, [rbp+60h+pSecurityDescriptor]; pSecurityDescriptor
0x1800339e4  call    cs:__imp_InitializeSecurityDescriptor
0x1800339eb  nop     dword ptr [rax+rax+00h]
0x1800339f0  test    eax, eax
0x1800339f2  jnz     short loc_180033A1B
0x1800339f4  call    cs:__imp_GetLastError
0x1800339fb  nop     dword ptr [rax+rax+00h]
0x180033a00  mov     ebx, eax
0x180033a02  test    eax, eax
0x180033a04  jle     short loc_180033A0F
0x180033a06  movzx   ebx, ax
0x180033a09  or      ebx, 80070000h
0x180033a0f  lea     rdx, aInitializesecu; "InitializeSecurityDescriptor failed: 0x"...
0x180033a16  jmp     loc_180033907
0x180033a1b  mov     r8, [rsp+160h+NewAcl]; pDacl
0x180033a20  lea     rcx, [rbp+60h+pSecurityDescriptor]; pSecurityDescriptor
0x180033a24  xor     r9d, r9d; bDaclDefaulted
0x180033a27  lea     edx, [r9+1]; bDaclPresent
0x180033a2b  call    cs:__imp_SetSecurityDescriptorDacl
0x180033a32  nop     dword ptr [rax+rax+00h]
0x180033a37  test    eax, eax
0x180033a39  jnz     short loc_180033A62
0x180033a3b  call    cs:__imp_GetLastError
0x180033a42  nop     dword ptr [rax+rax+00h]
0x180033a47  mov     ebx, eax
0x180033a49  test    eax, eax
0x180033a4b  jle     short loc_180033A56
0x180033a4d  movzx   ebx, ax
0x180033a50  or      ebx, 80070000h
0x180033a56  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorDacl failed: 0x%x"
0x180033a5d  jmp     loc_180033907
0x180033a62  lea     rax, [rbp+60h+pSecurityDescriptor]
0x180033a66  mov     [rbp+60h+SecurityAttributes.nLength], 18h
0x180033a6d  mov     [rbp+60h+SecurityAttributes.lpSecurityDescriptor], rax
0x180033a71  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x180033a78  lea     rax, [rsp+160h+dwDisposition]
0x180033a7d  mov     [rbp+60h+SecurityAttributes.bInheritHandle], r14d
0x180033a81  mov     qword ptr [rsp+160h+nSubAuthority6], rax; lpdwDisposition
0x180033a86  xor     r9d, r9d; lpClass
0x180033a89  mov     qword ptr [rsp+160h+nSubAuthority5], rsi; phkResult
0x180033a8e  lea     rax, [rbp+60h+SecurityAttributes]
0x180033a92  mov     qword ptr [rsp+160h+nSubAuthority4], rax; lpSecurityAttributes
0x180033a97  xor     r8d, r8d; Reserved
0x180033a9a  mov     [rsp+160h+nSubAuthority3], 20006h; samDesired
0x180033aa2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033aa9  mov     [rsp+160h+nSubAuthority2], r14d; dwOptions
0x180033aae  mov     [rsp+160h+dwDisposition], r14d
0x180033ab3  call    cs:__imp_RegCreateKeyExW
0x180033aba  nop     dword ptr [rax+rax+00h]
0x180033abf  mov     ebx, eax
0x180033ac1  test    eax, eax
0x180033ac3  jle     short loc_180033ACE
0x180033ac5  movzx   ebx, ax
0x180033ac8  or      ebx, 80070000h
0x180033ace  test    ebx, ebx
0x180033ad0  jns     short loc_180033AED
0x180033ad2  lea     rdx, aRegcreatekeyex; "RegCreateKeyEx failed: 0x%x in %s"
0x180033ad9  lea     r9, aCsecretstorage_0; "CSecretStorage::CreateStorageKey"
0x180033ae0  mov     r8d, ebx
0x180033ae3  mov     ecx, 8; int
0x180033ae8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033aed  mov     rcx, [rsp+160h+NewAcl]; hMem
0x180033af2  test    rcx, rcx
0x180033af5  jz      short loc_180033B03
0x180033af7  call    cs:__imp_LocalFree
0x180033afe  nop     dword ptr [rax+rax+00h]
0x180033b03  mov     rcx, [rsp+160h+hMem]; hMem
0x180033b08  test    rcx, rcx
0x180033b0b  jz      short loc_180033B19
0x180033b0d  call    cs:__imp_LocalFree
0x180033b14  nop     dword ptr [rax+rax+00h]
0x180033b19  mov     rcx, [rsp+160h+var_E8]; hMem
0x180033b1e  test    rcx, rcx
0x180033b21  jz      short loc_180033B2F
0x180033b23  call    cs:__imp_LocalFree
0x180033b2a  nop     dword ptr [rax+rax+00h]
0x180033b2f  mov     eax, ebx
0x180033b31  mov     rcx, [rbp+60h+var_30]
0x180033b35  xor     rcx, rsp; StackCookie
0x180033b38  call    __security_check_cookie
0x180033b3d  add     rsp, 148h
0x180033b44  pop     r14
0x180033b46  pop     rsi
0x180033b47  pop     rbx
0x180033b48  pop     rbp
0x180033b49  retn
```
