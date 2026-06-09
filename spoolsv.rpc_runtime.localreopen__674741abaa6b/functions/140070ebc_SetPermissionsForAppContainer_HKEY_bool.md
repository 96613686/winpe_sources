# SetPermissionsForAppContainer(HKEY__ *,bool)

- ea: `0x140070ebc`
- end: `0x1400711b2`
- name: `?SetPermissionsForAppContainer@@YAKPEAUHKEY__@@_N@Z`
- size: `758`
- prototype: `unsigned int __fastcall(HKEY, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140071470`

## callees

- `0x14000b20c`
- `0x140018204`
- `0x14002cd50`
- `0x14002d0a0`
- `0x14002e0dc`
- `0x14006fe7c`
- `0x1400705dc`
- `0x140070ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071171`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070eff`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070f3f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070eff`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070f3f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140070f7b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140070f7b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140070fc4`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140070fc4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140071000`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140071000`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14007111d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14007111d`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14007113a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14007113a`
- `ADVAPI32!EqualSid` at `0x140071033`
- `ADVAPI32!EqualSid` at `0x14007105e`
- `ADVAPI32!EqualSid` at `0x140071033`
- `ADVAPI32!EqualSid` at `0x14007105e`

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
0x140070ebc  push    rbp
0x140070ebe  push    rbx
0x140070ebf  push    rsi
0x140070ec0  push    rdi
0x140070ec1  push    r12
0x140070ec3  push    r13
0x140070ec5  push    r14
0x140070ec7  push    r15
0x140070ec9  lea     rbp, [rsp-1Fh]
0x140070ece  sub     rsp, 0B8h
0x140070ed5  mov     rax, cs:__security_cookie
0x140070edc  xor     rax, rsp
0x140070edf  mov     [rbp+57h+var_48], rax
0x140070ee3  xor     edi, edi
0x140070ee5  mov     [rbp+57h+cbSecurityDescriptor], 0
0x140070eec  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140070ef0  mov     [rbp+57h+pSecurityDescriptor], rdi
0x140070ef4  xor     r8d, r8d; pSecurityDescriptor
0x140070ef7  mov     r13, rcx
0x140070efa  lea     esi, [rdi+4]
0x140070efd  mov     edx, esi; SecurityInformation
0x140070eff  call    cs:__imp_RegGetKeySecurity
0x140070f06  nop     dword ptr [rax+rax+00h]
0x140070f0b  mov     ebx, eax
0x140070f0d  cmp     eax, 7Ah ; 'z'
0x140070f10  jnz     short loc_140070F4D
0x140070f12  mov     ecx, [rbp+57h+cbSecurityDescriptor]; unsigned __int64
0x140070f15  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140070f1a  mov     rdx, rax
0x140070f1d  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x140070f21  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x140070f26  mov     rdi, [rbp+57h+pSecurityDescriptor]
0x140070f2a  test    rdi, rdi
0x140070f2d  jz      loc_140071078
0x140070f33  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140070f37  mov     r8, rdi; pSecurityDescriptor
0x140070f3a  mov     edx, esi; SecurityInformation
0x140070f3c  mov     rcx, r13; hKey
0x140070f3f  call    cs:__imp_RegGetKeySecurity
0x140070f46  nop     dword ptr [rax+rax+00h]
0x140070f4b  mov     ebx, eax
0x140070f4d  test    ebx, ebx
0x140070f4f  jnz     loc_140071186
0x140070f55  xor     eax, eax
0x140070f57  mov     [rbp+57h+bDaclPresent], ebx
0x140070f5a  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x140070f5e  mov     [rbp+57h+pAclInformation], rax
0x140070f62  lea     r8, [rbp+57h+pDacl]; pDacl
0x140070f66  mov     [rbp+57h+var_50], eax
0x140070f69  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x140070f6d  mov     [rbp+57h+pDacl], 0
0x140070f75  mov     rcx, rdi; pSecurityDescriptor
0x140070f78  mov     [rbp+57h+bDaclDefaulted], ebx
0x140070f7b  call    cs:__imp_GetSecurityDescriptorDacl
0x140070f82  nop     dword ptr [rax+rax+00h]
0x140070f87  test    eax, eax
0x140070f89  jnz     short loc_140070F99
0x140070f8b  call    cs:__imp_GetLastError
0x140070f92  nop     dword ptr [rax+rax+00h]
0x140070f97  mov     ebx, eax
0x140070f99  cmp     [rbp+57h+bDaclPresent], 0
0x140070f9d  jz      loc_140071181
0x140070fa3  mov     rcx, [rbp+57h+pDacl]; pAcl
0x140070fa7  test    rcx, rcx
0x140070faa  jz      loc_140071181
0x140070fb0  test    ebx, ebx
0x140070fb2  jnz     loc_140071186
0x140070fb8  lea     r9d, [rbx+2]; dwAclInformationClass
0x140070fbc  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x140070fc0  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x140070fc4  call    cs:__imp_GetAclInformation
0x140070fcb  nop     dword ptr [rax+rax+00h]
0x140070fd0  test    eax, eax
0x140070fd2  jz      loc_140071171
0x140070fd8  xor     esi, esi
0x140070fda  lea     edi, [rbx+1]
0x140070fdd  xor     r14d, r14d
0x140070fe0  xor     r12d, r12d
0x140070fe3  cmp     r12d, dword ptr [rbp+57h+pAclInformation]
0x140070fe7  jnb     loc_140071098
0x140070fed  mov     rcx, [rbp+57h+pDacl]; pAcl
0x140070ff1  lea     r8, [rbp+57h+pAce]; pAce
0x140070ff5  mov     edx, r12d; dwAceIndex
0x140070ff8  mov     [rbp+57h+pAce], 0
0x140071000  call    cs:__imp_GetAce
0x140071007  nop     dword ptr [rax+rax+00h]
0x14007100c  test    eax, eax
0x14007100e  jz      short loc_140071082
0x140071010  mov     r15, [rbp+57h+pAce]
0x140071014  cmp     byte ptr [r15], 0
0x140071018  jnz     short loc_140071070
0x14007101a  test    dword ptr [r15+4], 20019h
0x140071022  jz      short loc_140071070
0x140071024  test    esi, esi
0x140071026  jnz     short loc_140071044
0x140071028  mov     rdx, cs:?g_pAppContainerSid@@3PEAXEA; pSid2
0x14007102f  lea     rcx, [r15+8]; pSid1
0x140071033  call    cs:__imp_EqualSid
0x14007103a  nop     dword ptr [rax+rax+00h]
0x14007103f  test    eax, eax
0x140071041  cmovnz  esi, edi
0x140071044  test    dword ptr [r15+4], 20019h
0x14007104c  jz      short loc_140071070
0x14007104e  test    r14d, r14d
0x140071051  jnz     short loc_140071070
0x140071053  mov     rdx, cs:?g_pLPACCapabilitySid@@3PEAXEA; pSid2
0x14007105a  lea     rcx, [r15+8]; pSid1
0x14007105e  call    cs:__imp_EqualSid
0x140071065  nop     dword ptr [rax+rax+00h]
0x14007106a  test    eax, eax
0x14007106c  cmovnz  r14d, edi
0x140071070  add     r12d, edi
0x140071073  jmp     loc_140070FE3
0x140071078  mov     ebx, 8
0x14007107d  jmp     loc_140071186
0x140071082  call    cs:__imp_GetLastError
0x140071089  nop     dword ptr [rax+rax+00h]
0x14007108e  mov     ebx, eax
0x140071090  test    eax, eax
0x140071092  jnz     loc_140071186
0x140071098  test    esi, esi
0x14007109a  jz      short loc_1400710A5
0x14007109c  test    r14d, r14d
0x14007109f  jnz     loc_140071186
0x1400710a5  test    esi, esi
0x1400710a7  mov     [rbp+57h+pAce], 0
0x1400710af  xorps   xmm0, xmm0
0x1400710b2  movq    rax, xmm0
0x1400710b7  cmovz   rax, cs:?g_pAppContainerSid@@3PEAXEA; void * g_pAppContainerSid
0x1400710bf  xor     r8d, r8d
0x1400710c2  test    esi, esi
0x1400710c4  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1400710c8  setz    r8b
0x1400710cc  mov     [rbp+57h+var_90], rax
0x1400710d0  test    r14d, r14d
0x1400710d3  jnz     short loc_1400710E7
0x1400710d5  mov     rax, cs:?g_pLPACCapabilitySid@@3PEAXEA; void * g_pLPACCapabilitySid
0x1400710dc  mov     ecx, r8d
0x1400710df  inc     r8d; unsigned int
0x1400710e2  mov     [rbp+rcx*8+57h+var_90], rax
0x1400710e7  mov     rcx, [rbp+57h+pDacl]; pAcl
0x1400710eb  lea     rax, [rbp+57h+pAce]
0x1400710ef  xor     r9d, r9d; bool
0x1400710f2  mov     [rsp+0F0h+var_D0], rax; struct _ACL **
0x1400710f7  lea     rdx, [rbp+57h+var_90]; void **
0x1400710fb  call    ?DuplicateDaclWithSpecialPermission@@YAKPEAU_ACL@@PEAPEAXK_NPEAPEAU1@@Z; DuplicateDaclWithSpecialPermission(_ACL *,void * *,ulong,bool,_ACL * *)
0x140071100  mov     ebx, eax
0x140071102  test    eax, eax
0x140071104  jnz     short loc_140071166
0x140071106  xorps   xmm0, xmm0
0x140071109  lea     rcx, [rbp+57h+var_80]; pSecurityDescriptor
0x14007110d  xor     eax, eax
0x14007110f  mov     edx, edi; dwRevision
0x140071111  movups  [rbp+57h+var_80], xmm0
0x140071115  mov     [rbp+57h+var_60], rax
0x140071119  movups  [rbp+57h+var_70], xmm0
0x14007111d  call    cs:__imp_InitializeSecurityDescriptor
0x140071124  nop     dword ptr [rax+rax+00h]
0x140071129  test    eax, eax
0x14007112b  jz      short loc_140071158
0x14007112d  mov     r8, [rbp+57h+pAce]; pDacl
0x140071131  lea     rcx, [rbp+57h+var_80]; pSecurityDescriptor
0x140071135  xor     r9d, r9d; bDaclDefaulted
0x140071138  mov     edx, edi; bDaclPresent
0x14007113a  call    cs:__imp_SetSecurityDescriptorDacl
0x140071141  nop     dword ptr [rax+rax+00h]
0x140071146  test    eax, eax
0x140071148  jz      short loc_140071158
0x14007114a  lea     rdx, [rbp+57h+var_80]; void *
0x14007114e  mov     rcx, r13; HKEY
0x140071151  call    ?ApplySecDescRecursively@@YAKPEAUHKEY__@@PEAX@Z; ApplySecDescRecursively(HKEY__ *,void *)
0x140071156  jmp     short loc_140071164
0x140071158  call    cs:__imp_GetLastError
0x14007115f  nop     dword ptr [rax+rax+00h]
0x140071164  mov     ebx, eax
0x140071166  mov     rcx, [rbp+57h+pAce]; void *
0x14007116a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14007116f  jmp     short loc_140071186
0x140071171  call    cs:__imp_GetLastError
0x140071178  nop     dword ptr [rax+rax+00h]
0x14007117d  mov     ebx, eax
0x14007117f  jmp     short loc_140071186
0x140071181  mov     ebx, 1
0x140071186  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14007118a  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x14007118f  mov     eax, ebx
0x140071191  mov     rcx, [rbp+57h+var_48]
0x140071195  xor     rcx, rsp; StackCookie
0x140071198  call    __security_check_cookie
0x14007119d  add     rsp, 0B8h
0x1400711a4  pop     r15
0x1400711a6  pop     r14
0x1400711a8  pop     r13
0x1400711aa  pop     r12
0x1400711ac  pop     rdi
0x1400711ad  pop     rsi
0x1400711ae  pop     rbx
0x1400711af  pop     rbp
0x1400711b0  retn
```
