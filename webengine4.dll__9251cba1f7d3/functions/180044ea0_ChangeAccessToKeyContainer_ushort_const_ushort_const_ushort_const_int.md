# ChangeAccessToKeyContainer(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180044ea0`
- end: `0x1800450e5`
- name: `?ChangeAccessToKeyContainer@@YAHPEBG00H@Z`
- size: `581`
- prototype: `__int64 __fastcall(LPCWSTR szContainer, const unsigned __int16 *, LPCWSTR szProvider, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021a48`
- `0x180025f24`
- `0x180044ea0`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x18004eaa8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044f6e`
- `KERNEL32!GetLastError` at `0x180044f6e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180045057`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180045057`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18004506f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18004506f`
- `ADVAPI32!CryptAcquireContextW` at `0x180044f34`
- `ADVAPI32!CryptAcquireContextW` at `0x180044f34`
- `ADVAPI32!CryptReleaseContext` at `0x1800450a3`
- `ADVAPI32!CryptReleaseContext` at `0x1800450a3`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180044fcb`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180044fcb`
- `ADVAPI32!CryptSetProvParam` at `0x180045087`
- `ADVAPI32!CryptSetProvParam` at `0x180045087`
- `ADVAPI32!CryptGetProvParam` at `0x180044f60`
- `ADVAPI32!CryptGetProvParam` at `0x180044fae`
- `ADVAPI32!CryptGetProvParam` at `0x180044f60`
- `ADVAPI32!CryptGetProvParam` at `0x180044fae`

## pseudocode

```c
__int64 __fastcall ChangeAccessToKeyContainer(LPCWSTR szContainer, char *a2, LPCWSTR szProvider, char a4)
{
  int v5; // r12d
  int v6; // r14d
  const WCHAR *v8; // rdi
  BYTE *v9; // rsi
  unsigned int PrincipalSID; // ebx
  BYTE *v11; // rax
  DWORD pdwDataLen; // [rsp+30h] [rbp-39h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-31h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-29h] BYREF
  PSID pSid1; // [rsp+48h] [rbp-21h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+50h] [rbp-19h] BYREF
  void *lpMem; // [rsp+58h] [rbp-11h] BYREF
  BYTE pSecurityDescriptor[96]; // [rsp+60h] [rbp-9h] BYREF
  WINBOOL bDaclPresent; // [rsp+E0h] [rbp+77h] BYREF
  BYTE pbData; // [rsp+E8h] [rbp+7Fh] BYREF

  v5 = a4 & 1;
  v6 = a4 & 2;
  phProv = 0;
  pdwDataLen = 0;
  v8 = szProvider;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  v9 = 0;
  pDacl = 0;
  lpMem = 0;
  pSid1 = 0;
  if ( !szProvider || !*szProvider )
    v8 = 0;
  PrincipalSID = GetPrincipalSID(a2, &pSid1);
  if ( !PrincipalSID )
  {
    if ( !CryptAcquireContextW(&phProv, szContainer, v8, 1u, v6 != 0 ? 0x20 : 0) )
      goto LABEL_22;
    pdwDataLen = 1;
    if ( CryptGetProvParam(phProv, 8u, &pbData, &pdwDataLen, 4u) )
      goto LABEL_23;
    if ( GetLastError() != 234 )
      goto LABEL_22;
    v11 = (BYTE *)MemAllocClear(pdwDataLen);
    v9 = v11;
    if ( !v11 )
    {
      PrincipalSID = -2147024882;
      goto LABEL_23;
    }
    if ( !CryptGetProvParam(phProv, 8u, v11, &pdwDataLen, 4u)
      || !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted)
      || bDaclPresent
      && pDacl
      && ((bDaclPresent = 0, !v5)
        ? (PACL)(PrincipalSID = CRegAccount::RemoveACL(pDacl, pSid1))
        : (PrincipalSID = CRegAccount::AddAccess(
                            &pDacl,
                            &pSid1,
                            1,
                            (a4 & 4) != 0 ? 0x10000000 : 0x80000000,
                            &bDaclPresent,
                            (struct _ACL **)&lpMem),
           pDacl = (PACL)lpMem),
          !PrincipalSID
       && !bDaclPresent
       && (!InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0)
        || !CryptSetProvParam(phProv, 8u, pSecurityDescriptor, 4u))) )
    {
LABEL_22:
      PrincipalSID = GetLastWin32Error();
    }
  }
LABEL_23:
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  MemFree(v9);
  MemFree(lpMem);
  if ( pSid1 )
    MemFree(pSid1);
  return PrincipalSID;
}

```

## disassembly

```asm
0x180044ea0  mov     [rsp-8+arg_0], rbx
0x180044ea5  push    rbp
0x180044ea6  push    rsi
0x180044ea7  push    rdi
0x180044ea8  push    r12
0x180044eaa  push    r13
0x180044eac  push    r14
0x180044eae  push    r15
0x180044eb0  lea     rbp, [rsp-27h]
0x180044eb5  sub     rsp, 90h
0x180044ebc  mov     r12d, r9d
0x180044ebf  mov     r14d, r9d
0x180044ec2  mov     r13, rcx
0x180044ec5  and     r12d, 1
0x180044ec9  xor     ecx, ecx
0x180044ecb  and     r14d, 2
0x180044ecf  mov     [rbp+57h+phProv], rcx
0x180044ed3  mov     r15d, r9d
0x180044ed6  mov     [rbp+57h+pdwDataLen], ecx
0x180044ed9  mov     rdi, r8
0x180044edc  mov     [rbp+57h+bDaclPresent], ecx
0x180044edf  mov     rax, rdx
0x180044ee2  mov     [rbp+57h+bDaclDefaulted], ecx
0x180044ee5  mov     esi, ecx
0x180044ee7  mov     [rbp+57h+pDacl], rcx
0x180044eeb  mov     [rbp+57h+lpMem], rcx
0x180044eef  mov     [rbp+57h+pSid1], rcx
0x180044ef3  test    r8, r8
0x180044ef6  jz      short loc_180044EFE
0x180044ef8  cmp     [r8], cx
0x180044efc  jnz     short loc_180044F01
0x180044efe  mov     rdi, rcx
0x180044f01  lea     rdx, [rbp+57h+pSid1]; void **
0x180044f05  mov     rcx, rax; unsigned __int16 *
0x180044f08  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x180044f0d  mov     ebx, eax
0x180044f0f  test    eax, eax
0x180044f11  jnz     loc_180045098
0x180044f17  neg     r14d
0x180044f1a  lea     rcx, [rbp+57h+phProv]; phProv
0x180044f1e  lea     r14d, [rbx+1]
0x180044f22  mov     r8, rdi; szProvider
0x180044f25  sbb     eax, eax
0x180044f27  mov     r9d, r14d; dwProvType
0x180044f2a  and     eax, 20h
0x180044f2d  mov     rdx, r13; szContainer
0x180044f30  mov     [rsp+0C0h+dwFlags], eax; dwFlags
0x180044f34  call    cs:__imp_CryptAcquireContextW
0x180044f3a  xor     edi, edi
0x180044f3c  test    eax, eax
0x180044f3e  jz      loc_180045091
0x180044f44  mov     rcx, [rbp+57h+phProv]; hProv
0x180044f48  lea     r13d, [rbx+4]
0x180044f4c  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180044f50  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x180044f55  lea     r8, [rbp+57h+pbData]; pbData
0x180044f59  mov     [rbp+57h+pdwDataLen], r14d
0x180044f5d  lea     edx, [rbx+8]; dwParam
0x180044f60  call    cs:__imp_CryptGetProvParam
0x180044f66  test    eax, eax
0x180044f68  jnz     loc_180045098
0x180044f6e  call    cs:__imp_GetLastError
0x180044f74  cmp     eax, 0EAh
0x180044f79  jnz     loc_180045091
0x180044f7f  mov     ecx, [rbp+57h+pdwDataLen]; unsigned __int64
0x180044f82  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180044f87  mov     rsi, rax
0x180044f8a  test    rax, rax
0x180044f8d  jnz     short loc_180044F99
0x180044f8f  mov     ebx, 8007000Eh
0x180044f94  jmp     loc_180045098
0x180044f99  mov     rcx, [rbp+57h+phProv]; hProv
0x180044f9d  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180044fa1  mov     r8, rsi; pbData
0x180044fa4  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x180044fa9  mov     edx, 8; dwParam
0x180044fae  call    cs:__imp_CryptGetProvParam
0x180044fb4  test    eax, eax
0x180044fb6  jz      loc_180045091
0x180044fbc  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180044fc0  mov     rcx, rsi; pSecurityDescriptor
0x180044fc3  lea     r8, [rbp+57h+pDacl]; pDacl
0x180044fc7  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180044fcb  call    cs:__imp_GetSecurityDescriptorDacl
0x180044fd1  test    eax, eax
0x180044fd3  jz      loc_180045091
0x180044fd9  cmp     [rbp+57h+bDaclPresent], edi
0x180044fdc  jz      loc_180045098
0x180044fe2  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180044fe6  test    rcx, rcx
0x180044fe9  jz      loc_180045098
0x180044fef  mov     [rbp+57h+bDaclPresent], edi
0x180044ff2  test    r12d, r12d
0x180044ff5  jz      short loc_18004503C
0x180044ff7  and     r15b, r13b
0x180044ffa  lea     rax, [rbp+57h+lpMem]
0x180044ffe  mov     [rsp+0C0h+var_98], rax; struct _ACL **
0x180045003  lea     rdx, [rbp+57h+pSid1]; void **
0x180045007  neg     r15b
0x18004500a  lea     rax, [rbp+57h+bDaclPresent]
0x18004500e  mov     r8d, r14d; int
0x180045011  mov     qword ptr [rsp+0C0h+dwFlags], rax; int *
0x180045016  sbb     r9d, r9d
0x180045019  lea     rcx, [rbp+57h+pDacl]; struct _ACL **
0x18004501d  and     r9d, 90000000h
0x180045024  add     r9d, 80000000h; unsigned int
0x18004502b  call    ?AddAccess@CRegAccount@@SAJPEAPEAU_ACL@@PEAPEAXHKPEAH0@Z; CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,_ACL * *)
0x180045030  mov     ebx, eax
0x180045032  mov     rax, [rbp+57h+lpMem]
0x180045036  mov     [rbp+57h+pDacl], rax
0x18004503a  jmp     short loc_180045047
0x18004503c  mov     rdx, [rbp+57h+pSid1]; pSid1
0x180045040  call    ?RemoveACL@CRegAccount@@SAJPEAU_ACL@@PEAX@Z; CRegAccount::RemoveACL(_ACL *,void *)
0x180045045  mov     ebx, eax
0x180045047  test    ebx, ebx
0x180045049  jnz     short loc_180045098
0x18004504b  cmp     [rbp+57h+bDaclPresent], edi
0x18004504e  jnz     short loc_180045098
0x180045050  mov     edx, r14d; dwRevision
0x180045053  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180045057  call    cs:__imp_InitializeSecurityDescriptor
0x18004505d  test    eax, eax
0x18004505f  jz      short loc_180045091
0x180045061  mov     r8, [rbp+57h+pDacl]; pDacl
0x180045065  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180045069  xor     r9d, r9d; bDaclDefaulted
0x18004506c  mov     edx, r14d; bDaclPresent
0x18004506f  call    cs:__imp_SetSecurityDescriptorDacl
0x180045075  test    eax, eax
0x180045077  jz      short loc_180045091
0x180045079  mov     rcx, [rbp+57h+phProv]; hProv
0x18004507d  lea     r8, [rbp+57h+pSecurityDescriptor]; pbData
0x180045081  mov     r9d, r13d; dwFlags
0x180045084  lea     edx, [rbx+8]; dwParam
0x180045087  call    cs:__imp_CryptSetProvParam
0x18004508d  test    eax, eax
0x18004508f  jnz     short loc_180045098
0x180045091  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180045096  mov     ebx, eax
0x180045098  mov     rcx, [rbp+57h+phProv]; hProv
0x18004509c  test    rcx, rcx
0x18004509f  jz      short loc_1800450A9
0x1800450a1  xor     edx, edx; dwFlags
0x1800450a3  call    cs:__imp_CryptReleaseContext
0x1800450a9  mov     rcx, rsi; lpMem
0x1800450ac  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800450b1  mov     rcx, [rbp+57h+lpMem]; lpMem
0x1800450b5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800450ba  mov     rcx, [rbp+57h+pSid1]; lpMem
0x1800450be  test    rcx, rcx
0x1800450c1  jz      short loc_1800450C8
0x1800450c3  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800450c8  mov     eax, ebx
0x1800450ca  mov     rbx, [rsp+0C0h+arg_0]
0x1800450d2  add     rsp, 90h
0x1800450d9  pop     r15
0x1800450db  pop     r14
0x1800450dd  pop     r13
0x1800450df  pop     r12
0x1800450e1  pop     rdi
0x1800450e2  pop     rsi
0x1800450e3  pop     rbp
0x1800450e4  retn
```
