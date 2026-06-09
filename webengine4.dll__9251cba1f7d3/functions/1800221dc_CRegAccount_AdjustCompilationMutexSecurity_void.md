# CRegAccount::AdjustCompilationMutexSecurity(void *)

- ea: `0x1800221dc`
- end: `0x18002245b`
- name: `?AdjustCompilationMutexSecurity@CRegAccount@@SAJPEAX@Z`
- size: `639`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044bd8`

## callees

- `0x18000d56c`
- `0x180021730`
- `0x1800221dc`
- `0x18004d030`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180022406`
- `ADVAPI32!RegCloseKey` at `0x180022415`
- `ADVAPI32!RegCloseKey` at `0x180022406`
- `ADVAPI32!RegCloseKey` at `0x180022415`
- `ADVAPI32!RegOpenKeyExW` at `0x180022263`
- `ADVAPI32!RegOpenKeyExW` at `0x180022263`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800223bf`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800223bf`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800223d6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800223d6`
- `ADVAPI32!SetKernelObjectSecurity` at `0x1800223ec`
- `ADVAPI32!SetKernelObjectSecurity` at `0x1800223ec`
- `ADVAPI32!GetAce` at `0x18002235c`
- `ADVAPI32!GetAce` at `0x18002235c`
- `ADVAPI32!GetAclInformation` at `0x180022338`
- `ADVAPI32!GetAclInformation` at `0x180022338`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002230f`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002230f`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800222ef`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800222ef`
- `ADVAPI32!RegGetKeySecurity` at `0x1800222af`
- `ADVAPI32!RegGetKeySecurity` at `0x1800222e2`
- `ADVAPI32!RegGetKeySecurity` at `0x1800222af`
- `ADVAPI32!RegGetKeySecurity` at `0x1800222e2`

## string_xrefs

- `0x18002225c`: `CompilationMutexName`

## pseudocode

```c
__int64 __fastcall CRegAccount::AdjustCompilationMutexSecurity(HANDLE Handle)
{
  struct _ACL *v1; // r14
  void *v3; // rdi
  unsigned int LastWin32Error; // ebx
  LSTATUS KeySecurity; // eax
  void *v6; // rax
  void *v7; // rax
  DWORD v8; // esi
  DWORD cbSecurityDescriptor; // [rsp+40h] [rbp-49h] BYREF
  struct _ACL *v11; // [rsp+48h] [rbp-41h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-39h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-29h] BYREF
  LPVOID pAce; // [rsp+68h] [rbp-21h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+70h] [rbp-19h] BYREF
  WINBOOL bDaclPresent; // [rsp+74h] [rbp-15h] BYREF
  void *v18; // [rsp+78h] [rbp-11h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+80h] [rbp-9h] BYREF
  _DWORD pAclInformation[4]; // [rsp+A8h] [rbp+1Fh] BYREF

  hKey = 0;
  v1 = 0;
  phkResult = 0;
  pDacl = 0;
  v11 = 0;
  v3 = 0;
  cbSecurityDescriptor = 0;
  LastWin32Error = CRegInfo::OpenCurrentVersionKey((DWORD)&hKey, 0x20019u, 1, 1);
  if ( LastWin32Error )
    goto LABEL_27;
  KeySecurity = RegOpenKeyExW(hKey, L"CompilationMutexName", 0, 0x20019u, &phkResult);
  if ( KeySecurity )
    goto LABEL_3;
  cbSecurityDescriptor = 1000;
  v6 = MemAllocClear(0x3E8u);
  v3 = v6;
  if ( !v6 )
  {
LABEL_7:
    LastWin32Error = -2147024882;
    goto LABEL_27;
  }
  KeySecurity = RegGetKeySecurity(phkResult, 4u, v6, &cbSecurityDescriptor);
  if ( KeySecurity == 122 )
  {
    MemFree(v3);
    v7 = MemAllocClear(cbSecurityDescriptor);
    v3 = v7;
    if ( !v7 )
      goto LABEL_7;
    KeySecurity = RegGetKeySecurity(phkResult, 4u, v7, &cbSecurityDescriptor);
  }
  if ( KeySecurity )
  {
LABEL_3:
    LastWin32Error = (unsigned __int16)KeySecurity | 0x80070000;
    if ( KeySecurity <= 0 )
      LastWin32Error = KeySecurity;
    goto LABEL_27;
  }
  cbSecurityDescriptor = GetSecurityDescriptorLength(v3);
  if ( !cbSecurityDescriptor || !GetSecurityDescriptorDacl(v3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
LABEL_26:
    LastWin32Error = GetLastWin32Error();
    goto LABEL_27;
  }
  if ( !pDacl )
    goto LABEL_23;
  if ( !GetAclInformation(pDacl, pAclInformation, 0xCu, AclSizeInformation) )
    goto LABEL_26;
  v8 = pAclInformation[0] - 1;
  if ( pAclInformation[0] - 1 < 0 )
  {
LABEL_23:
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v1, 0)
      && SetKernelObjectSecurity(Handle, 4u, pSecurityDescriptor) )
    {
      goto LABEL_27;
    }
    goto LABEL_26;
  }
  while ( 1 )
  {
    pAce = 0;
    if ( GetAce(pDacl, v8, &pAce) )
    {
      if ( pAce )
      {
        if ( !*(_BYTE *)pAce )
        {
          v18 = (char *)pAce + 8;
          LastWin32Error = CRegAccount::AddAccess(&v11, &v18, 1, 0x1F0001u, 0, 3, &v11);
          if ( LastWin32Error )
            break;
        }
      }
    }
    if ( (--v8 & 0x80000000) != 0 )
    {
      v1 = v11;
      goto LABEL_23;
    }
  }
  v1 = v11;
LABEL_27:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  MemFree(v1);
  MemFree(v3);
  return LastWin32Error;
}

```

## disassembly

```asm
0x1800221dc  mov     [rsp-8+arg_8], rbx
0x1800221e1  mov     [rsp-8+arg_10], rsi
0x1800221e6  push    rbp
0x1800221e7  push    rdi
0x1800221e8  push    r13
0x1800221ea  push    r14
0x1800221ec  push    r15
0x1800221ee  lea     rbp, [rsp-37h]
0x1800221f3  sub     rsp, 0C0h
0x1800221fa  mov     rax, cs:__security_cookie
0x180022201  xor     rax, rsp
0x180022204  mov     [rbp+57h+var_28], rax
0x180022208  and     [rbp+57h+hKey], 0
0x18002220d  xor     r14d, r14d
0x180022210  and     [rbp+57h+var_90], 0
0x180022215  mov     r15, rcx
0x180022218  and     [rbp+57h+pDacl], r14
0x18002221c  lea     rcx, [rbp+57h+hKey]; dwOptions
0x180022220  mov     esi, 20019h
0x180022225  mov     [rbp+57h+var_98], r14
0x180022229  lea     r13d, [r14+1]
0x18002222d  xor     edi, edi
0x18002222f  and     [rbp+57h+cbSecurityDescriptor], edi
0x180022232  mov     r9d, r13d; int
0x180022235  mov     r8d, r13d; int
0x180022238  mov     edx, esi; samDesired
0x18002223a  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x18002223f  mov     ebx, eax
0x180022241  test    eax, eax
0x180022243  jnz     loc_1800223FD
0x180022249  mov     rcx, [rbp+57h+hKey]; hKey
0x18002224d  lea     rax, [rbp+57h+var_90]
0x180022251  mov     r9d, esi; samDesired
0x180022254  mov     [rsp+0E0h+phkResult], rax; int *
0x180022259  xor     r8d, r8d; ulOptions
0x18002225c  lea     rdx, aCompilationmut; "CompilationMutexName"
0x180022263  call    cs:__imp_RegOpenKeyExW
0x180022269  test    eax, eax
0x18002226b  jz      short loc_180022280
0x18002226d  movzx   ebx, ax
0x180022270  or      ebx, 80070000h
0x180022276  test    eax, eax
0x180022278  cmovle  ebx, eax
0x18002227b  jmp     loc_1800223FD
0x180022280  mov     ecx, 3E8h; unsigned __int64
0x180022285  mov     [rbp+57h+cbSecurityDescriptor], ecx
0x180022288  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18002228d  mov     rdi, rax
0x180022290  test    rax, rax
0x180022293  jnz     short loc_18002229F
0x180022295  mov     ebx, 8007000Eh
0x18002229a  jmp     loc_1800223FD
0x18002229f  mov     rcx, [rbp+57h+var_90]; hKey
0x1800222a3  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800222a7  mov     r8, rdi; pSecurityDescriptor
0x1800222aa  mov     edx, 4; SecurityInformation
0x1800222af  call    cs:__imp_RegGetKeySecurity
0x1800222b5  cmp     eax, 7Ah ; 'z'
0x1800222b8  jnz     short loc_1800222E8
0x1800222ba  mov     rcx, rdi; lpMem
0x1800222bd  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800222c2  mov     ecx, [rbp+57h+cbSecurityDescriptor]; unsigned __int64
0x1800222c5  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800222ca  mov     rdi, rax
0x1800222cd  test    rax, rax
0x1800222d0  jz      short loc_180022295
0x1800222d2  mov     rcx, [rbp+57h+var_90]; hKey
0x1800222d6  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800222da  mov     r8, rax; pSecurityDescriptor
0x1800222dd  mov     edx, 4; SecurityInformation
0x1800222e2  call    cs:__imp_RegGetKeySecurity
0x1800222e8  test    eax, eax
0x1800222ea  jnz     short loc_18002226D
0x1800222ec  mov     rcx, rdi; pSecurityDescriptor
0x1800222ef  call    cs:__imp_GetSecurityDescriptorLength
0x1800222f5  mov     [rbp+57h+cbSecurityDescriptor], eax
0x1800222f8  test    eax, eax
0x1800222fa  jz      loc_1800223F6
0x180022300  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180022304  mov     rcx, rdi; pSecurityDescriptor
0x180022307  lea     r8, [rbp+57h+pDacl]; pDacl
0x18002230b  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18002230f  call    cs:__imp_GetSecurityDescriptorDacl
0x180022315  test    eax, eax
0x180022317  jz      loc_1800223F6
0x18002231d  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180022321  test    rcx, rcx
0x180022324  jz      loc_1800223B8
0x18002232a  mov     r9d, 2; dwAclInformationClass
0x180022330  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180022334  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180022338  call    cs:__imp_GetAclInformation
0x18002233e  test    eax, eax
0x180022340  jz      loc_1800223F6
0x180022346  mov     esi, [rbp+57h+pAclInformation]
0x180022349  sub     esi, r13d
0x18002234c  js      short loc_1800223B8
0x18002234e  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180022352  lea     r8, [rbp+57h+pAce]; pAce
0x180022356  and     [rbp+57h+pAce], r14
0x18002235a  mov     edx, esi; dwAceIndex
0x18002235c  call    cs:__imp_GetAce
0x180022362  test    eax, eax
0x180022364  jz      short loc_1800223AF
0x180022366  mov     rax, [rbp+57h+pAce]
0x18002236a  test    rax, rax
0x18002236d  jz      short loc_1800223AF
0x18002236f  cmp     [rax], r14b
0x180022372  jnz     short loc_1800223AF
0x180022374  add     rax, 8
0x180022378  lea     rdx, [rbp+57h+var_68]; void **
0x18002237c  mov     [rbp+57h+var_68], rax
0x180022380  lea     rcx, [rbp+57h+var_98]; struct _ACL **
0x180022384  lea     rax, [rbp+57h+var_98]
0x180022388  mov     r9d, 1F0001h; unsigned int
0x18002238e  mov     [rsp+0E0h+var_B0], rax; struct _ACL **
0x180022393  mov     r8d, r13d; int
0x180022396  mov     [rsp+0E0h+var_B8], 3; char
0x18002239b  and     [rsp+0E0h+phkResult], r14
0x1800223a0  call    ?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z; CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,uchar,_ACL * *)
0x1800223a5  mov     ebx, eax
0x1800223a7  test    eax, eax
0x1800223a9  jnz     loc_180022455
0x1800223af  sub     esi, r13d
0x1800223b2  jns     short loc_18002234E
0x1800223b4  mov     r14, [rbp+57h+var_98]
0x1800223b8  mov     edx, r13d; dwRevision
0x1800223bb  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800223bf  call    cs:__imp_InitializeSecurityDescriptor
0x1800223c5  test    eax, eax
0x1800223c7  jz      short loc_1800223F6
0x1800223c9  xor     r9d, r9d; bDaclDefaulted
0x1800223cc  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800223d0  mov     r8, r14; pDacl
0x1800223d3  mov     edx, r13d; bDaclPresent
0x1800223d6  call    cs:__imp_SetSecurityDescriptorDacl
0x1800223dc  test    eax, eax
0x1800223de  jz      short loc_1800223F6
0x1800223e0  lea     r8, [rbp+57h+pSecurityDescriptor]; SecurityDescriptor
0x1800223e4  mov     edx, 4; SecurityInformation
0x1800223e9  mov     rcx, r15; Handle
0x1800223ec  call    cs:__imp_SetKernelObjectSecurity
0x1800223f2  test    eax, eax
0x1800223f4  jnz     short loc_1800223FD
0x1800223f6  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800223fb  mov     ebx, eax
0x1800223fd  mov     rcx, [rbp+57h+hKey]; hKey
0x180022401  test    rcx, rcx
0x180022404  jz      short loc_18002240C
0x180022406  call    cs:__imp_RegCloseKey
0x18002240c  mov     rcx, [rbp+57h+var_90]; hKey
0x180022410  test    rcx, rcx
0x180022413  jz      short loc_18002241B
0x180022415  call    cs:__imp_RegCloseKey
0x18002241b  mov     rcx, r14; lpMem
0x18002241e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180022423  mov     rcx, rdi; lpMem
0x180022426  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18002242b  mov     eax, ebx
0x18002242d  mov     rcx, [rbp+57h+var_28]
0x180022431  xor     rcx, rsp; StackCookie
0x180022434  call    __security_check_cookie
0x180022439  lea     r11, [rsp+0E0h+var_20]
0x180022441  mov     rbx, [r11+38h]
0x180022445  mov     rsi, [r11+40h]
0x180022449  mov     rsp, r11
0x18002244c  pop     r15
0x18002244e  pop     r14
0x180022450  pop     r13
0x180022452  pop     rdi
0x180022453  pop     rbp
0x180022454  retn
0x180022455  mov     r14, [rbp+57h+var_98]
0x180022459  jmp     short loc_1800223FD
```
