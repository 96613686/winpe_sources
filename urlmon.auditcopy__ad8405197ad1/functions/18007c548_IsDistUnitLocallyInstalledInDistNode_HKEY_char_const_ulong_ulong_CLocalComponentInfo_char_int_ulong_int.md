# IsDistUnitLocallyInstalledInDistNode(HKEY__ *,char const *,ulong,ulong,CLocalComponentInfo *,char *,int *,ulong,int *)

- ea: `0x18007c548`
- end: `0x18007c8f7`
- name: `?IsDistUnitLocallyInstalledInDistNode@@YAJPEAUHKEY__@@PEBDKKPEAVCLocalComponentInfo@@PEADPEAHK4@Z`
- size: `943`
- prototype: `__int64 __fastcall(HKEY, const char *, unsigned int, DWORD, struct CLocalComponentInfo *, char *, int *, unsigned int, struct HKEY__ *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007baf4`

## callees

- `0x18002fee0`
- `0x18007b978`
- `0x18007c108`
- `0x18007c548`
- `0x180096c28`
- `0x1800a5678`
- `0x1800cffe0`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c5c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c63b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c67a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c7d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c5c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c63b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c67a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c7d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c87c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c892`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c8a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c8be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c87c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c892`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c8a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c8be`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x18007c6b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x18007c82b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x18007c6b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x18007c82b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18007c84a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18007c84a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007c718`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007c718`

## pseudocode

```c
__int64 __fastcall IsDistUnitLocallyInstalledInDistNode(
        HKEY a1,
        const char *a2,
        unsigned int a3,
        DWORD a4,
        struct CLocalComponentInfo *a5,
        char *a6,
        int *a7,
        unsigned int a8,
        struct HKEY__ *a9)
{
  LSTATUS v11; // eax
  int v12; // ebx
  DWORD v13; // r14d
  OLECHAR *v14; // rdi
  DWORD v15; // edi
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v18; // [rsp+54h] [rbp-ACh] BYREF
  LPCOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v22; // [rsp+70h] [rbp-90h] BYREF
  HKEY v23; // [rsp+78h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  CHAR v25[320]; // [rsp+90h] [rbp-70h] BYREF
  CHAR ValueName[272]; // [rsp+1D0h] [rbp+D0h] BYREF

  v22 = 0;
  *(_DWORD *)a9 = 0;
  hKey = 0;
  phkResult = 0;
  v23 = 0;
  cchValueName = 260;
  v11 = RegOpenKeyExA(a1, a2, 0, 0x20019u, &hKey);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_35;
  }
  v12 = CheckInstalledVersionHint(hKey, a5, a3, a4);
  if ( v12 == 1 )
  {
    *(_DWORD *)a9 = 1;
LABEL_6:
    if ( a3 != -1 || a4 != -1 )
      goto LABEL_8;
    goto LABEL_9;
  }
  if ( v12 )
  {
    if ( v12 < 0 )
    {
LABEL_8:
      v12 = 1;
      goto LABEL_35;
    }
    goto LABEL_6;
  }
LABEL_9:
  if ( !RegOpenKeyExA(hKey, "Contains", 0, 0x20019u, &phkResult) )
  {
    if ( a7 )
      *a7 = 1;
    if ( !RegOpenKeyExA(phkResult, "Distribution Units", 0, 0x20019u, &v22) )
    {
      v13 = 0;
      while ( !RegEnumValueA(v22, v13, ValueName, &cchValueName, 0, 0, 0, 0) )
      {
        CLocalComponentInfo::CLocalComponentInfo((CLocalComponentInfo *)v25);
        lpsz = 0;
        pclsid = 0;
        if ( (int)Ansi2Unicode(ValueName, (WCHAR **)&lpsz) < 0 )
        {
          if ( lpsz )
            operator delete((void *)lpsz);
          CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v25);
          break;
        }
        v14 = (OLECHAR *)lpsz;
        pclsid = GUID_NULL;
        if ( lpsz )
          CLSIDFromString(lpsz, &pclsid);
        if ( (unsigned int)IsControlLocallyInstalled(0, &pclsid, v14, 0, 0, (struct CLocalComponentInfo *)v25, 0, 0, a9) )
        {
          if ( v14 )
            operator delete(v14);
          *((_QWORD *)a5 + 35) = 0;
          v12 = 1;
          CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v25);
          goto LABEL_35;
        }
        ++v13;
        if ( v14 )
          operator delete(v14);
        cchValueName = 260;
        CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v25);
      }
    }
    if ( !RegOpenKeyExA(phkResult, "Files", 0, 0x20019u, &v23) )
    {
      LODWORD(lpsz) = 1;
      v18 = 260;
      v15 = 0;
      while ( !RegEnumValueA(v23, v15, ValueName, &v18, 0, (LPDWORD)&lpsz, 0, 0) )
      {
        v18 = 260;
        ++v15;
        if ( GetFileAttributesA(ValueName) == -1 )
        {
          *((_QWORD *)a5 + 35) = 0;
          v12 = 1;
          break;
        }
      }
    }
  }
LABEL_35:
  if ( v22 )
    RegCloseKey(v22);
  if ( v23 )
    RegCloseKey(v23);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18007c548  mov     [rsp-8+arg_10], rbx
0x18007c54d  push    rbp
0x18007c54e  push    rsi
0x18007c54f  push    rdi
0x18007c550  push    r12
0x18007c552  push    r13
0x18007c554  push    r14
0x18007c556  push    r15
0x18007c558  lea     rbp, [rsp-1F0h]
0x18007c560  sub     rsp, 2F0h
0x18007c567  mov     rax, cs:__security_cookie
0x18007c56e  xor     rax, rsp
0x18007c571  mov     [rbp+220h+var_40], rax
0x18007c578  mov     r12, [rbp+220h+arg_40]
0x18007c57f  lea     rax, [rsp+320h+hKey]
0x18007c584  mov     rsi, [rbp+220h+arg_20]
0x18007c58b  xor     r13d, r13d
0x18007c58e  mov     rdi, [rbp+220h+arg_30]
0x18007c595  mov     r15d, r9d
0x18007c598  mov     r14d, r8d
0x18007c59b  mov     [rsp+320h+var_2B0], r13
0x18007c5a0  mov     r9d, 20019h; samDesired
0x18007c5a6  mov     [r12], r13d
0x18007c5aa  xor     r8d, r8d; ulOptions
0x18007c5ad  mov     [rsp+320h+hKey], r13
0x18007c5b2  mov     [rsp+320h+var_2C0], r13
0x18007c5b7  mov     [rsp+320h+var_2A8], r13
0x18007c5bc  mov     [rsp+320h+cchValueName], 104h
0x18007c5c4  mov     [rsp+320h+phkResult], rax; phkResult
0x18007c5c9  call    cs:__imp_RegOpenKeyExA
0x18007c5d0  nop     dword ptr [rax+rax+00h]
0x18007c5d5  mov     ebx, eax
0x18007c5d7  test    eax, eax
0x18007c5d9  jnz     loc_18007C867
0x18007c5df  mov     rcx, [rsp+320h+hKey]; hKey
0x18007c5e4  mov     r9d, r15d; unsigned int
0x18007c5e7  mov     r8d, r14d; unsigned int
0x18007c5ea  mov     rdx, rsi; struct CLocalComponentInfo *
0x18007c5ed  call    ?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z; CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)
0x18007c5f2  mov     ebx, eax
0x18007c5f4  or      ecx, 0FFFFFFFFh
0x18007c5f7  lea     eax, [r13+1]
0x18007c5fb  cmp     ebx, eax
0x18007c5fd  jnz     short loc_18007C605
0x18007c5ff  mov     [r12], eax
0x18007c603  jmp     short loc_18007C60B
0x18007c605  test    ebx, ebx
0x18007c607  jz      short loc_18007C61C
0x18007c609  js      short loc_18007C615
0x18007c60b  cmp     r14d, ecx
0x18007c60e  jnz     short loc_18007C615
0x18007c610  cmp     r15d, ecx
0x18007c613  jz      short loc_18007C61C
0x18007c615  mov     ebx, eax
0x18007c617  jmp     loc_18007C872
0x18007c61c  mov     rcx, [rsp+320h+hKey]; hKey
0x18007c621  lea     rax, [rsp+320h+var_2C0]
0x18007c626  mov     r9d, 20019h; samDesired
0x18007c62c  mov     [rsp+320h+phkResult], rax; phkResult
0x18007c631  xor     r8d, r8d; ulOptions
0x18007c634  lea     rdx, aContains; "Contains"
0x18007c63b  call    cs:__imp_RegOpenKeyExA
0x18007c642  nop     dword ptr [rax+rax+00h]
0x18007c647  test    eax, eax
0x18007c649  jnz     loc_18007C872
0x18007c64f  lea     r15d, [rax+1]
0x18007c653  test    rdi, rdi
0x18007c656  jz      short loc_18007C65B
0x18007c658  mov     [rdi], r15d
0x18007c65b  mov     rcx, [rsp+320h+var_2C0]; hKey
0x18007c660  lea     rax, [rsp+320h+var_2B0]
0x18007c665  mov     r9d, 20019h; samDesired
0x18007c66b  mov     [rsp+320h+phkResult], rax; phkResult
0x18007c670  xor     r8d, r8d; ulOptions
0x18007c673  lea     rdx, aDistributionUn; "Distribution Units"
0x18007c67a  call    cs:__imp_RegOpenKeyExA
0x18007c681  nop     dword ptr [rax+rax+00h]
0x18007c686  test    eax, eax
0x18007c688  jnz     loc_18007C7B9
0x18007c68e  mov     r14d, r13d
0x18007c691  mov     rcx, [rsp+320h+var_2B0]; hKey
0x18007c696  lea     r9, [rsp+320h+cchValueName]; lpcchValueName
0x18007c69b  mov     [rsp+320h+lpcbData], r13; lpcbData
0x18007c6a0  lea     r8, [rbp+220h+ValueName]; lpValueName
0x18007c6a7  mov     [rsp+320h+lpData], r13; lpData
0x18007c6ac  mov     edx, r14d; dwIndex
0x18007c6af  mov     [rsp+320h+lpType], r13; lpType
0x18007c6b4  mov     [rsp+320h+phkResult], r13; lpReserved
0x18007c6b9  call    cs:__imp_RegEnumValueA
0x18007c6c0  nop     dword ptr [rax+rax+00h]
0x18007c6c5  test    eax, eax
0x18007c6c7  jnz     loc_18007C7B9
0x18007c6cd  lea     rcx, [rbp+220h+var_290]; this
0x18007c6d1  call    ??0CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::CLocalComponentInfo(void)
0x18007c6d6  xorps   xmm0, xmm0
0x18007c6d9  mov     [rsp+320h+lpsz], r13
0x18007c6de  lea     rdx, [rsp+320h+lpsz]
0x18007c6e3  lea     rcx, [rbp+220h+ValueName]; lpMultiByteStr
0x18007c6ea  movups  xmmword ptr [rbp+220h+pclsid.Data1], xmm0
0x18007c6ee  call    Ansi2Unicode
0x18007c6f3  test    eax, eax
0x18007c6f5  js      loc_18007C7A1
0x18007c6fb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007c702  mov     rdi, [rsp+320h+lpsz]
0x18007c707  movdqu  xmmword ptr [rbp+220h+pclsid.Data1], xmm0
0x18007c70c  test    rdi, rdi
0x18007c70f  jz      short loc_18007C724
0x18007c711  lea     rdx, [rbp+220h+pclsid]; pclsid
0x18007c715  mov     rcx, rdi; lpsz
0x18007c718  call    cs:__imp_CLSIDFromString
0x18007c71f  nop     dword ptr [rax+rax+00h]
0x18007c724  mov     [rsp+320h+var_2E0], r12; int *
0x18007c729  lea     rax, [rbp+220h+var_290]
0x18007c72d  mov     dword ptr [rsp+320h+lpcbData], r13d; int
0x18007c732  lea     rdx, [rbp+220h+pclsid]; struct _GUID *
0x18007c736  mov     [rsp+320h+lpData], r13; char *
0x18007c73b  xor     r9d, r9d; unsigned int
0x18007c73e  mov     [rsp+320h+lpType], rax; struct CLocalComponentInfo *
0x18007c743  mov     r8, rdi; unsigned __int16 *
0x18007c746  xor     ecx, ecx; char *
0x18007c748  mov     dword ptr [rsp+320h+phkResult], r13d; unsigned int
0x18007c74d  call    ?IsControlLocallyInstalled@@YAJPEADQEAU_GUID@@PEBGKKPEAVCLocalComponentInfo@@0HPEAH@Z; IsControlLocallyInstalled(char *,_GUID * const,ushort const *,ulong,ulong,CLocalComponentInfo *,char *,int,int *)
0x18007c752  test    eax, eax
0x18007c754  jnz     short loc_18007C77C
0x18007c756  add     r14d, r15d
0x18007c759  test    rdi, rdi
0x18007c75c  jz      short loc_18007C766
0x18007c75e  mov     rcx, rdi; void *
0x18007c761  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c766  lea     rcx, [rbp+220h+var_290]; this
0x18007c76a  mov     [rsp+320h+cchValueName], 104h
0x18007c772  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x18007c777  jmp     loc_18007C691
0x18007c77c  test    rdi, rdi
0x18007c77f  jz      short loc_18007C789
0x18007c781  mov     rcx, rdi; void *
0x18007c784  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c789  lea     rcx, [rbp+220h+var_290]; this
0x18007c78d  mov     [rsi+118h], r13
0x18007c794  mov     ebx, r15d
0x18007c797  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x18007c79c  jmp     loc_18007C872
0x18007c7a1  mov     rcx, [rsp+320h+lpsz]; void *
0x18007c7a6  test    rcx, rcx
0x18007c7a9  jz      short loc_18007C7B0
0x18007c7ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c7b0  lea     rcx, [rbp+220h+var_290]; this
0x18007c7b4  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x18007c7b9  mov     rcx, [rsp+320h+var_2C0]; hKey
0x18007c7be  lea     rax, [rsp+320h+var_2A8]
0x18007c7c3  mov     r9d, 20019h; samDesired
0x18007c7c9  mov     [rsp+320h+phkResult], rax; phkResult
0x18007c7ce  xor     r8d, r8d; ulOptions
0x18007c7d1  lea     rdx, aFiles; "Files"
0x18007c7d8  call    cs:__imp_RegOpenKeyExA
0x18007c7df  nop     dword ptr [rax+rax+00h]
0x18007c7e4  test    eax, eax
0x18007c7e6  jnz     loc_18007C872
0x18007c7ec  mov     r14d, 104h
0x18007c7f2  mov     dword ptr [rsp+320h+lpsz], r15d
0x18007c7f7  mov     [rsp+320h+var_2CC], r14d
0x18007c7fc  mov     edi, r13d
0x18007c7ff  mov     rcx, [rsp+320h+var_2A8]; hKey
0x18007c804  lea     rax, [rsp+320h+lpsz]
0x18007c809  mov     [rsp+320h+lpcbData], r13; lpcbData
0x18007c80e  lea     r9, [rsp+320h+var_2CC]; lpcchValueName
0x18007c813  mov     [rsp+320h+lpData], r13; lpData
0x18007c818  lea     r8, [rbp+220h+ValueName]; lpValueName
0x18007c81f  mov     [rsp+320h+lpType], rax; lpType
0x18007c824  mov     edx, edi; dwIndex
0x18007c826  mov     [rsp+320h+phkResult], r13; lpReserved
0x18007c82b  call    cs:__imp_RegEnumValueA
0x18007c832  nop     dword ptr [rax+rax+00h]
0x18007c837  test    eax, eax
0x18007c839  jnz     short loc_18007C872
0x18007c83b  lea     rcx, [rbp+220h+ValueName]; lpFileName
0x18007c842  mov     [rsp+320h+var_2CC], r14d
0x18007c847  add     edi, r15d
0x18007c84a  call    cs:__imp_GetFileAttributesA
0x18007c851  nop     dword ptr [rax+rax+00h]
0x18007c856  cmp     eax, 0FFFFFFFFh
0x18007c859  jnz     short loc_18007C7FF
0x18007c85b  mov     [rsi+118h], r13
0x18007c862  mov     ebx, r15d
0x18007c865  jmp     short loc_18007C872
0x18007c867  jle     short loc_18007C872
0x18007c869  movzx   ebx, ax
0x18007c86c  or      ebx, 80070000h
0x18007c872  mov     rcx, [rsp+320h+var_2B0]; hKey
0x18007c877  test    rcx, rcx
0x18007c87a  jz      short loc_18007C888
0x18007c87c  call    cs:__imp_RegCloseKey
0x18007c883  nop     dword ptr [rax+rax+00h]
0x18007c888  mov     rcx, [rsp+320h+var_2A8]; hKey
0x18007c88d  test    rcx, rcx
0x18007c890  jz      short loc_18007C89E
0x18007c892  call    cs:__imp_RegCloseKey
0x18007c899  nop     dword ptr [rax+rax+00h]
0x18007c89e  mov     rcx, [rsp+320h+var_2C0]; hKey
0x18007c8a3  test    rcx, rcx
0x18007c8a6  jz      short loc_18007C8B4
0x18007c8a8  call    cs:__imp_RegCloseKey
0x18007c8af  nop     dword ptr [rax+rax+00h]
0x18007c8b4  mov     rcx, [rsp+320h+hKey]; hKey
0x18007c8b9  test    rcx, rcx
0x18007c8bc  jz      short loc_18007C8CA
0x18007c8be  call    cs:__imp_RegCloseKey
0x18007c8c5  nop     dword ptr [rax+rax+00h]
0x18007c8ca  mov     eax, ebx
0x18007c8cc  mov     rcx, [rbp+220h+var_40]
0x18007c8d3  xor     rcx, rsp; StackCookie
0x18007c8d6  call    __security_check_cookie
0x18007c8db  mov     rbx, [rsp+320h+arg_10]
0x18007c8e3  add     rsp, 2F0h
0x18007c8ea  pop     r15
0x18007c8ec  pop     r14
0x18007c8ee  pop     r13
0x18007c8f0  pop     r12
0x18007c8f2  pop     rdi
0x18007c8f3  pop     rsi
0x18007c8f4  pop     rbp
0x18007c8f5  retn
```
