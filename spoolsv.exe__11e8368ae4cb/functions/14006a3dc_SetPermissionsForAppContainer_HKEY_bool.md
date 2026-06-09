# SetPermissionsForAppContainer(HKEY__ *,bool)

- ea: `0x14006a3dc`
- end: `0x14006a680`
- name: `?SetPermissionsForAppContainer@@YAKPEAUHKEY__@@_N@Z`
- size: `676`
- prototype: `unsigned int __fastcall(HKEY, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14006a910`

## callees

- `0x14000a398`
- `0x140016d54`
- `0x14002a870`
- `0x14002abc0`
- `0x14002bbcc`
- `0x1400694d8`
- `0x140069ba4`
- `0x14006a3dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006a646`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a41f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a459`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a41f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a459`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14006a48f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14006a48f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14006a4cc`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14006a4cc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14006a502`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14006a502`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14006a604`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14006a604`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14006a61b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14006a61b`
- `ADVAPI32!EqualSid` at `0x14006a52f`
- `ADVAPI32!EqualSid` at `0x14006a554`
- `ADVAPI32!EqualSid` at `0x14006a52f`
- `ADVAPI32!EqualSid` at `0x14006a554`

## pseudocode

```c
__int64 __fastcall SetPermissionsForAppContainer(HKEY a1)
{
  PSECURITY_DESCRIPTOR v1; // rdi
  unsigned int KeySecurity; // ebx
  void *v4; // rax
  BOOL v5; // esi
  BOOL v6; // r14d
  DWORD i; // r12d
  _DWORD *v8; // r15
  PSID v9; // rax
  unsigned int v10; // r8d
  unsigned __int64 v11; // rdx
  DWORD LastError; // eax
  DWORD cbSecurityDescriptor; // [rsp+30h] [rbp-69h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-61h] BYREF
  WINBOOL bDaclPresent; // [rsp+40h] [rbp-59h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-51h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+50h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-41h] BYREF
  void *v20[2]; // [rsp+60h] [rbp-39h] BYREF
  _OWORD v21[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v22; // [rsp+90h] [rbp-9h]
  __int64 pAclInformation; // [rsp+98h] [rbp-1h] BYREF
  int v24; // [rsp+A0h] [rbp+7h]

  v1 = 0;
  cbSecurityDescriptor = 0;
  pSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(a1, 4u, 0, &cbSecurityDescriptor);
  if ( KeySecurity == 122 )
  {
    v4 = operator new[](cbSecurityDescriptor);
    NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(&pSecurityDescriptor, v4);
    v1 = pSecurityDescriptor;
    if ( !pSecurityDescriptor )
    {
      KeySecurity = 8;
      goto LABEL_39;
    }
    KeySecurity = RegGetKeySecurity(a1, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
  }
  if ( !KeySecurity )
  {
    bDaclPresent = 0;
    pAclInformation = 0;
    v24 = 0;
    pDacl = 0;
    bDaclDefaulted = 0;
    if ( !GetSecurityDescriptorDacl(v1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      KeySecurity = GetLastError();
    if ( bDaclPresent && pDacl )
    {
      if ( !KeySecurity )
      {
        if ( GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
        {
          v5 = 0;
          v6 = 0;
          for ( i = 0; i < (unsigned int)pAclInformation; ++i )
          {
            pAce = 0;
            if ( !GetAce(pDacl, i, &pAce) )
            {
              KeySecurity = GetLastError();
              if ( KeySecurity )
                goto LABEL_39;
              break;
            }
            v8 = pAce;
            if ( !*(_BYTE *)pAce && (*((_DWORD *)pAce + 1) & 0x20019) != 0 )
            {
              if ( !v5 )
                v5 = EqualSid((char *)pAce + 8, g_pAppContainerSid);
              if ( (v8[1] & 0x20019) != 0 && !v6 )
                v6 = EqualSid(v8 + 2, g_pLPACCapabilitySid);
            }
          }
          if ( !v5 || !v6 )
          {
            pAce = 0;
            v9 = 0;
            if ( !v5 )
              v9 = g_pAppContainerSid;
            v20[1] = 0;
            v10 = !v5;
            v20[0] = v9;
            if ( !v6 )
            {
              ++v10;
              v20[!v5] = g_pLPACCapabilitySid;
            }
            KeySecurity = DuplicateDaclWithSpecialPermission(pDacl, v20, v10, 0, (struct _ACL **)&pAce);
            if ( !KeySecurity )
            {
              memset(v21, 0, sizeof(v21));
              v22 = 0;
              if ( InitializeSecurityDescriptor(v21, 1u) && SetSecurityDescriptorDacl(v21, 1, (PACL)pAce, 0) )
                LastError = ApplySecDescRecursively(a1, v21);
              else
                LastError = GetLastError();
              KeySecurity = LastError;
            }
            operator delete(pAce, v11);
          }
        }
        else
        {
          KeySecurity = GetLastError();
        }
      }
    }
    else
    {
      KeySecurity = 1;
    }
  }
LABEL_39:
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&pSecurityDescriptor);
  return KeySecurity;
}

```

## disassembly

```asm
0x14006a3dc  push    rbp
0x14006a3de  push    rbx
0x14006a3df  push    rsi
0x14006a3e0  push    rdi
0x14006a3e1  push    r12
0x14006a3e3  push    r13
0x14006a3e5  push    r14
0x14006a3e7  push    r15
0x14006a3e9  lea     rbp, [rsp-1Fh]
0x14006a3ee  sub     rsp, 0B8h
0x14006a3f5  mov     rax, cs:__security_cookie
0x14006a3fc  xor     rax, rsp
0x14006a3ff  mov     [rbp+57h+var_48], rax
0x14006a403  xor     edi, edi
0x14006a405  mov     [rbp+57h+cbSecurityDescriptor], 0
0x14006a40c  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14006a410  mov     [rbp+57h+pSecurityDescriptor], rdi
0x14006a414  xor     r8d, r8d; pSecurityDescriptor
0x14006a417  mov     r13, rcx
0x14006a41a  lea     esi, [rdi+4]
0x14006a41d  mov     edx, esi; SecurityInformation
0x14006a41f  call    cs:__imp_RegGetKeySecurity
0x14006a425  mov     ebx, eax
0x14006a427  cmp     eax, 7Ah ; 'z'
0x14006a42a  jnz     short loc_14006A461
0x14006a42c  mov     ecx, [rbp+57h+cbSecurityDescriptor]; unsigned __int64
0x14006a42f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006a434  mov     rdx, rax
0x14006a437  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14006a43b  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x14006a440  mov     rdi, [rbp+57h+pSecurityDescriptor]
0x14006a444  test    rdi, rdi
0x14006a447  jz      loc_14006A565
0x14006a44d  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14006a451  mov     r8, rdi; pSecurityDescriptor
0x14006a454  mov     edx, esi; SecurityInformation
0x14006a456  mov     rcx, r13; hKey
0x14006a459  call    cs:__imp_RegGetKeySecurity
0x14006a45f  mov     ebx, eax
0x14006a461  test    ebx, ebx
0x14006a463  jnz     loc_14006A655
0x14006a469  xor     eax, eax
0x14006a46b  mov     [rbp+57h+bDaclPresent], ebx
0x14006a46e  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x14006a472  mov     [rbp+57h+pAclInformation], rax
0x14006a476  lea     r8, [rbp+57h+pDacl]; pDacl
0x14006a47a  mov     [rbp+57h+var_50], eax
0x14006a47d  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x14006a481  mov     [rbp+57h+pDacl], 0
0x14006a489  mov     rcx, rdi; pSecurityDescriptor
0x14006a48c  mov     [rbp+57h+bDaclDefaulted], ebx
0x14006a48f  call    cs:__imp_GetSecurityDescriptorDacl
0x14006a495  test    eax, eax
0x14006a497  jnz     short loc_14006A4A1
0x14006a499  call    cs:__imp_GetLastError
0x14006a49f  mov     ebx, eax
0x14006a4a1  cmp     [rbp+57h+bDaclPresent], 0
0x14006a4a5  jz      loc_14006A650
0x14006a4ab  mov     rcx, [rbp+57h+pDacl]; pAcl
0x14006a4af  test    rcx, rcx
0x14006a4b2  jz      loc_14006A650
0x14006a4b8  test    ebx, ebx
0x14006a4ba  jnz     loc_14006A655
0x14006a4c0  lea     r9d, [rbx+2]; dwAclInformationClass
0x14006a4c4  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x14006a4c8  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x14006a4cc  call    cs:__imp_GetAclInformation
0x14006a4d2  test    eax, eax
0x14006a4d4  jz      loc_14006A646
0x14006a4da  xor     esi, esi
0x14006a4dc  lea     edi, [rbx+1]
0x14006a4df  xor     r14d, r14d
0x14006a4e2  xor     r12d, r12d
0x14006a4e5  cmp     r12d, dword ptr [rbp+57h+pAclInformation]
0x14006a4e9  jnb     loc_14006A57F
0x14006a4ef  mov     rcx, [rbp+57h+pDacl]; pAcl
0x14006a4f3  lea     r8, [rbp+57h+pAce]; pAce
0x14006a4f7  mov     edx, r12d; dwAceIndex
0x14006a4fa  mov     [rbp+57h+pAce], 0
0x14006a502  call    cs:__imp_GetAce
0x14006a508  test    eax, eax
0x14006a50a  jz      short loc_14006A56F
0x14006a50c  mov     r15, [rbp+57h+pAce]
0x14006a510  cmp     byte ptr [r15], 0
0x14006a514  jnz     short loc_14006A560
0x14006a516  test    dword ptr [r15+4], 20019h
0x14006a51e  jz      short loc_14006A560
0x14006a520  test    esi, esi
0x14006a522  jnz     short loc_14006A53A
0x14006a524  mov     rdx, cs:?g_pAppContainerSid@@3PEAXEA; pSid2
0x14006a52b  lea     rcx, [r15+8]; pSid1
0x14006a52f  call    cs:__imp_EqualSid
0x14006a535  test    eax, eax
0x14006a537  cmovnz  esi, edi
0x14006a53a  test    dword ptr [r15+4], 20019h
0x14006a542  jz      short loc_14006A560
0x14006a544  test    r14d, r14d
0x14006a547  jnz     short loc_14006A560
0x14006a549  mov     rdx, cs:?g_pLPACCapabilitySid@@3PEAXEA; pSid2
0x14006a550  lea     rcx, [r15+8]; pSid1
0x14006a554  call    cs:__imp_EqualSid
0x14006a55a  test    eax, eax
0x14006a55c  cmovnz  r14d, edi
0x14006a560  add     r12d, edi
0x14006a563  jmp     short loc_14006A4E5
0x14006a565  mov     ebx, 8
0x14006a56a  jmp     loc_14006A655
0x14006a56f  call    cs:__imp_GetLastError
0x14006a575  mov     ebx, eax
0x14006a577  test    eax, eax
0x14006a579  jnz     loc_14006A655
0x14006a57f  test    esi, esi
0x14006a581  jz      short loc_14006A58C
0x14006a583  test    r14d, r14d
0x14006a586  jnz     loc_14006A655
0x14006a58c  test    esi, esi
0x14006a58e  mov     [rbp+57h+pAce], 0
0x14006a596  xorps   xmm0, xmm0
0x14006a599  movq    rax, xmm0
0x14006a59e  cmovz   rax, cs:?g_pAppContainerSid@@3PEAXEA; void * g_pAppContainerSid
0x14006a5a6  xor     r8d, r8d
0x14006a5a9  test    esi, esi
0x14006a5ab  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14006a5af  setz    r8b
0x14006a5b3  mov     [rbp+57h+var_90], rax
0x14006a5b7  test    r14d, r14d
0x14006a5ba  jnz     short loc_14006A5CE
0x14006a5bc  mov     rax, cs:?g_pLPACCapabilitySid@@3PEAXEA; void * g_pLPACCapabilitySid
0x14006a5c3  mov     ecx, r8d
0x14006a5c6  inc     r8d; unsigned int
0x14006a5c9  mov     [rbp+rcx*8+57h+var_90], rax
0x14006a5ce  mov     rcx, [rbp+57h+pDacl]; pAcl
0x14006a5d2  lea     rax, [rbp+57h+pAce]
0x14006a5d6  xor     r9d, r9d; bool
0x14006a5d9  mov     [rsp+0F0h+var_D0], rax; struct _ACL **
0x14006a5de  lea     rdx, [rbp+57h+var_90]; void **
0x14006a5e2  call    ?DuplicateDaclWithSpecialPermission@@YAKPEAU_ACL@@PEAPEAXK_NPEAPEAU1@@Z; DuplicateDaclWithSpecialPermission(_ACL *,void * *,ulong,bool,_ACL * *)
0x14006a5e7  mov     ebx, eax
0x14006a5e9  test    eax, eax
0x14006a5eb  jnz     short loc_14006A63B
0x14006a5ed  xorps   xmm0, xmm0
0x14006a5f0  lea     rcx, [rbp+57h+var_80]; pSecurityDescriptor
0x14006a5f4  xor     eax, eax
0x14006a5f6  mov     edx, edi; dwRevision
0x14006a5f8  movups  [rbp+57h+var_80], xmm0
0x14006a5fc  mov     [rbp+57h+var_60], rax
0x14006a600  movups  [rbp+57h+var_70], xmm0
0x14006a604  call    cs:__imp_InitializeSecurityDescriptor
0x14006a60a  test    eax, eax
0x14006a60c  jz      short loc_14006A633
0x14006a60e  mov     r8, [rbp+57h+pAce]; pDacl
0x14006a612  lea     rcx, [rbp+57h+var_80]; pSecurityDescriptor
0x14006a616  xor     r9d, r9d; bDaclDefaulted
0x14006a619  mov     edx, edi; bDaclPresent
0x14006a61b  call    cs:__imp_SetSecurityDescriptorDacl
0x14006a621  test    eax, eax
0x14006a623  jz      short loc_14006A633
0x14006a625  lea     rdx, [rbp+57h+var_80]; void *
0x14006a629  mov     rcx, r13; HKEY
0x14006a62c  call    ?ApplySecDescRecursively@@YAKPEAUHKEY__@@PEAX@Z; ApplySecDescRecursively(HKEY__ *,void *)
0x14006a631  jmp     short loc_14006A639
0x14006a633  call    cs:__imp_GetLastError
0x14006a639  mov     ebx, eax
0x14006a63b  mov     rcx, [rbp+57h+pAce]; void *
0x14006a63f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006a644  jmp     short loc_14006A655
0x14006a646  call    cs:__imp_GetLastError
0x14006a64c  mov     ebx, eax
0x14006a64e  jmp     short loc_14006A655
0x14006a650  mov     ebx, 1
0x14006a655  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14006a659  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x14006a65e  mov     eax, ebx
0x14006a660  mov     rcx, [rbp+57h+var_48]
0x14006a664  xor     rcx, rsp; StackCookie
0x14006a667  call    __security_check_cookie
0x14006a66c  add     rsp, 0B8h
0x14006a673  pop     r15
0x14006a675  pop     r14
0x14006a677  pop     r13
0x14006a679  pop     r12
0x14006a67b  pop     rdi
0x14006a67c  pop     rsi
0x14006a67d  pop     rbx
0x14006a67e  pop     rbp
0x14006a67f  retn
```
