# CRegAccount::SetACLOnDir(void *,ushort const *,ulong,int)

- ea: `0x1800263bc`
- end: `0x18002656c`
- name: `?SetACLOnDir@CRegAccount@@SAJPEAXPEBGKH@Z`
- size: `432`
- prototype: `__int64 __fastcall(PSID pSid1, LPWSTR pObjectName, unsigned int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800214a4`
- `0x180021624`
- `0x180023044`

## callees

- `0x180021730`
- `0x180025f24`
- `0x1800263bc`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x180026441`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180026441`
- `ADVAPI32!GetFileSecurityW` at `0x18002645e`
- `ADVAPI32!GetFileSecurityW` at `0x18002645e`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002648a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002648a`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180026523`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180026523`

## pseudocode

```c
__int64 __fastcall CRegAccount::SetACLOnDir(PSID pSid1, LPWSTR pObjectName, unsigned int a3, int a4)
{
  void *v4; // rdi
  int v5; // r12d
  PACL v6; // r15
  unsigned int LastWin32Error; // ebx
  DWORD v8; // eax
  DWORD v11; // esi
  void *v12; // rax
  unsigned int v13; // eax
  struct _ACL *v14; // rax
  signed int v15; // eax
  int v17; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-24h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-18h] BYREF
  PACL v21; // [rsp+58h] [rbp-10h] BYREF
  void *v22; // [rsp+B0h] [rbp+48h] BYREF
  DWORD nLengthNeeded; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v24; // [rsp+C0h] [rbp+58h]
  int v25; // [rsp+C8h] [rbp+60h]

  v25 = a4;
  v24 = a3;
  v22 = pSid1;
  v4 = 0;
  v5 = 0;
  pDacl = 0;
  v6 = 0;
  LastWin32Error = 0;
  v17 = 0;
  v21 = 0;
  v8 = 1024;
  nLengthNeeded = 1024;
  if ( pObjectName && pSid1 )
  {
    while ( 1 )
    {
      if ( v4 )
      {
        MemFree(v4);
        v8 = nLengthNeeded;
      }
      v11 = v8;
      v12 = MemAllocClear(v8);
      v4 = v12;
      if ( !v12 )
      {
        LastWin32Error = -2147024882;
        goto LABEL_23;
      }
      InitializeSecurityDescriptor(v12, 1u);
      if ( GetFileSecurityW(pObjectName, 4u, v4, v11, &nLengthNeeded) )
        break;
      v8 = nLengthNeeded;
      if ( nLengthNeeded <= v11 )
        goto LABEL_8;
    }
    if ( !GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
LABEL_8:
      LastWin32Error = GetLastWin32Error();
      goto LABEL_23;
    }
    if ( bDaclPresent && pDacl )
    {
      if ( v25 )
      {
        v13 = CRegAccount::AddAccess(&pDacl, &v22, 1, v24, &v17, 3, &v21);
        v6 = v21;
        LastWin32Error = v13;
        v5 = v17;
        v14 = v21;
        pDacl = v21;
      }
      else
      {
        LastWin32Error = CRegAccount::RemoveACL(pDacl, pSid1);
        v14 = pDacl;
      }
      if ( !LastWin32Error && !v5 )
      {
        v15 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, v14, 0);
        if ( v15 )
        {
          LastWin32Error = (unsigned __int16)v15 | 0x80070000;
          if ( v15 <= 0 )
            LastWin32Error = v15;
        }
      }
    }
  }
  else
  {
    LastWin32Error = -2147024809;
  }
LABEL_23:
  MemFree(v6);
  MemFree(v4);
  return LastWin32Error;
}

```

## disassembly

```asm
0x1800263bc  mov     [rsp-40h+arg_18], r9d
0x1800263c1  mov     [rsp-40h+arg_10], r8d
0x1800263c6  mov     [rsp-40h+arg_0], rcx
0x1800263cb  push    rbp
0x1800263cc  push    rbx
0x1800263cd  push    rsi
0x1800263ce  push    rdi
0x1800263cf  push    r12
0x1800263d1  push    r13
0x1800263d3  push    r14
0x1800263d5  push    r15
0x1800263d7  mov     rbp, rsp
0x1800263da  sub     rsp, 68h
0x1800263de  xor     edi, edi
0x1800263e0  xor     r12d, r12d
0x1800263e3  and     [rbp+pDacl], rdi
0x1800263e7  xor     r15d, r15d
0x1800263ea  xor     ebx, ebx
0x1800263ec  mov     [rbp+var_28], r12d
0x1800263f0  mov     [rbp+var_10], r15
0x1800263f4  mov     eax, 400h
0x1800263f9  mov     [rbp+nLengthNeeded], eax
0x1800263fc  mov     r13, rdx
0x1800263ff  mov     r14, rcx
0x180026402  test    rdx, rdx
0x180026405  jz      loc_180026544
0x18002640b  test    rcx, rcx
0x18002640e  jz      loc_180026544
0x180026414  test    rdi, rdi
0x180026417  jz      short loc_180026424
0x180026419  mov     rcx, rdi; lpMem
0x18002641c  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180026421  mov     eax, [rbp+nLengthNeeded]
0x180026424  mov     ecx, eax; unsigned __int64
0x180026426  mov     esi, eax
0x180026428  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18002642d  mov     rdi, rax
0x180026430  test    rax, rax
0x180026433  jz      loc_18002653D
0x180026439  mov     edx, 1; dwRevision
0x18002643e  mov     rcx, rax; pSecurityDescriptor
0x180026441  call    cs:__imp_InitializeSecurityDescriptor
0x180026447  lea     rax, [rbp+nLengthNeeded]
0x18002644b  mov     r9d, esi; nLength
0x18002644e  mov     r8, rdi; pSecurityDescriptor
0x180026451  mov     [rsp+68h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180026456  mov     edx, 4; RequestedInformation
0x18002645b  mov     rcx, r13; lpFileName
0x18002645e  call    cs:__imp_GetFileSecurityW
0x180026464  test    eax, eax
0x180026466  jnz     short loc_18002647B
0x180026468  mov     eax, [rbp+nLengthNeeded]
0x18002646b  cmp     eax, esi
0x18002646d  ja      short loc_180026414
0x18002646f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180026474  mov     ebx, eax
0x180026476  jmp     loc_180026549
0x18002647b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18002647f  mov     rcx, rdi; pSecurityDescriptor
0x180026482  lea     r8, [rbp+pDacl]; pDacl
0x180026486  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18002648a  call    cs:__imp_GetSecurityDescriptorDacl
0x180026490  xor     esi, esi
0x180026492  test    eax, eax
0x180026494  jz      short loc_18002646F
0x180026496  cmp     [rbp+bDaclPresent], esi
0x180026499  jz      loc_180026549
0x18002649f  mov     rcx, [rbp+pDacl]; pAcl
0x1800264a3  test    rcx, rcx
0x1800264a6  jz      loc_180026549
0x1800264ac  cmp     [rbp+arg_18], esi
0x1800264af  jz      short loc_1800264F0
0x1800264b1  mov     r9d, [rbp+arg_10]; unsigned int
0x1800264b5  lea     rax, [rbp+var_10]
0x1800264b9  mov     [rsp+68h+pSacl], rax; struct _ACL **
0x1800264be  lea     r8d, [rsi+1]; int
0x1800264c2  lea     rax, [rbp+var_28]
0x1800264c6  mov     byte ptr [rsp+68h+var_40], 3; char
0x1800264cb  lea     rdx, [rbp+arg_0]; void **
0x1800264cf  mov     [rsp+68h+lpnLengthNeeded], rax; int *
0x1800264d4  lea     rcx, [rbp+pDacl]; struct _ACL **
0x1800264d8  call    ?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z; CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,uchar,_ACL * *)
0x1800264dd  mov     r15, [rbp+var_10]
0x1800264e1  mov     ebx, eax
0x1800264e3  mov     r12d, [rbp+var_28]
0x1800264e7  mov     rax, r15
0x1800264ea  mov     [rbp+pDacl], rax
0x1800264ee  jmp     short loc_1800264FE
0x1800264f0  mov     rdx, r14; pSid1
0x1800264f3  call    ?RemoveACL@CRegAccount@@SAJPEAU_ACL@@PEAX@Z; CRegAccount::RemoveACL(_ACL *,void *)
0x1800264f8  mov     ebx, eax
0x1800264fa  mov     rax, [rbp+pDacl]
0x1800264fe  test    ebx, ebx
0x180026500  jnz     short loc_180026549
0x180026502  test    r12d, r12d
0x180026505  jnz     short loc_180026549
0x180026507  mov     [rsp+68h+pSacl], rsi; pSacl
0x18002650c  lea     edx, [rbx+1]; ObjectType
0x18002650f  mov     [rsp+68h+var_40], rax; pDacl
0x180026514  lea     r8d, [rbx+4]; SecurityInfo
0x180026518  xor     r9d, r9d; psidOwner
0x18002651b  mov     [rsp+68h+lpnLengthNeeded], rsi; psidGroup
0x180026520  mov     rcx, r13; pObjectName
0x180026523  call    cs:__imp_SetNamedSecurityInfoW
0x180026529  test    eax, eax
0x18002652b  jz      short loc_180026549
0x18002652d  movzx   ebx, ax
0x180026530  or      ebx, 80070000h
0x180026536  test    eax, eax
0x180026538  cmovle  ebx, eax
0x18002653b  jmp     short loc_180026549
0x18002653d  mov     ebx, 8007000Eh
0x180026542  jmp     short loc_180026549
0x180026544  mov     ebx, 80070057h
0x180026549  mov     rcx, r15; lpMem
0x18002654c  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180026551  mov     rcx, rdi; lpMem
0x180026554  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180026559  mov     eax, ebx
0x18002655b  add     rsp, 68h
0x18002655f  pop     r15
0x180026561  pop     r14
0x180026563  pop     r13
0x180026565  pop     r12
0x180026567  pop     rdi
0x180026568  pop     rsi
0x180026569  pop     rbx
0x18002656a  pop     rbp
0x18002656b  retn
```
