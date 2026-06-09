# AddRemoveDeleteAceOnFolder(ushort const *,void *,int)

- ea: `0x180006180`
- end: `0x180006452`
- name: `?AddRemoveDeleteAceOnFolder@@YAJPEBGPEAXH@Z`
- size: `722`
- prototype: `__int64 __fastcall(const WCHAR *pObjectName, void *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180006890`
- `0x180006b00`

## callees

- `0x180002600`
- `0x18000260c`
- `0x1800060a8`
- `0x180006180`
- `0x1800064d4`
- `0x180006c70`
- `0x18000731c`
- `0x1800079f0`
- `0x180007b90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063eb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800063a7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800063a7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180006391`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180006391`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000629d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800062f3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000629d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800062f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000631d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000640d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006436`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000631d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000640d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006436`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800063d4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800063d4`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800061e0`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800061e0`

## pseudocode

```c
__int64 __fastcall AddRemoveDeleteAceOnFolder(const WCHAR *pObjectName, void *a2, int a3)
{
  PSID *v3; // r15
  void *v4; // r14
  WCHAR *v5; // r12
  signed int NamedSecurityInfoW; // eax
  signed int AclForExplicitEntries; // ebx
  struct _ACL *v8; // rbx
  HDPA *v9; // rax
  HDPA *v10; // rsi
  CAceList *v11; // rdi
  void *v12; // rdx
  unsigned int v13; // r8d
  unsigned __int8 v14; // r9
  CAceList *v15; // rcx
  HDPA *v16; // r13
  int *v17; // rax
  int v18; // r12d
  int v19; // r14d
  PSID *Ptr; // rax
  PSID *v21; // rsi
  int i; // ebx
  struct _DPA *v23; // rcx
  int v24; // eax
  HLOCAL *v25; // rsi
  struct _ACL *v26; // rsi
  signed int v27; // eax
  signed int LastError; // eax
  PACL pDacl; // [rsp+48h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+50h] [rbp-21h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v33; // [rsp+78h] [rbp+7h]
  PACL ppDacl; // [rsp+F0h] [rbp+7Fh] BYREF

  v3 = 0;
  v4 = a2;
  ppSecurityDescriptor = 0;
  ppDacl = 0;
  v5 = (WCHAR *)pObjectName;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
  AclForExplicitEntries = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    AclForExplicitEntries = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( AclForExplicitEntries >= 0 )
  {
    v8 = ppDacl;
    v9 = (HDPA *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      AclForExplicitEntries = -2147024882;
      goto LABEL_41;
    }
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    v9[3] = (HDPA)1;
    v11 = (CAceList *)v9;
    AclForExplicitEntries = CAceList::_InitFromAcl((CAceList *)v9, v8);
    if ( AclForExplicitEntries < 0 )
    {
      CAceList::~CAceList((CAceList *)v10);
      v15 = (CAceList *)v10;
LABEL_7:
      operator delete(v15);
LABEL_41:
      LocalFree(ppSecurityDescriptor);
      return (unsigned int)AclForExplicitEntries;
    }
    v16 = v10 + 1;
    v17 = (int *)v10[1];
    if ( v17 )
    {
      v18 = *v17;
      v19 = 0;
      if ( *v17 > 0 )
      {
        while ( 1 )
        {
          Ptr = (PSID *)g_pfn_DPA_GetPtr(*v16, v19);
          v21 = Ptr;
          if ( !*((_DWORD *)Ptr + 6) && *((_BYTE *)Ptr + 1) == 11 && EqualSid(Ptr[1], a2) )
            break;
          if ( ++v19 >= v18 )
            goto LABEL_16;
        }
        v3 = v21;
      }
LABEL_16:
      v4 = a2;
      v5 = (WCHAR *)pObjectName;
    }
    if ( a3 )
    {
      if ( v3 )
      {
        for ( i = 0; ; ++i )
        {
          v23 = *v16;
          v24 = *v16 ? *(_DWORD *)v23 : 0;
          if ( i >= v24 )
            break;
          v25 = (HLOCAL *)g_pfn_DPA_GetPtr(v23, i);
          if ( EqualSid(v4, v25[1]) && *((_BYTE *)v25 + 1) == 11 )
          {
            g_pfn_DPA_DeletePtr(*v16, i);
            LocalFree(v25[1]);
            LocalFree(v25[2]);
            *((_DWORD *)v25 + 7) &= ~0x80000000;
            operator delete(v25);
            --i;
          }
        }
LABEL_30:
        pDacl = 0;
        AclForExplicitEntries = CAceList::GetAclForExplicitEntries(v11, v12, &pDacl);
        if ( AclForExplicitEntries >= 0 )
        {
          v33 = 0;
          memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
          InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
          v26 = pDacl;
          if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
          {
            v27 = SetNamedSecurityInfoW(v5, SE_FILE_OBJECT, 4u, 0, 0, v26, 0);
            AclForExplicitEntries = v27;
            if ( v27 > 0 )
              AclForExplicitEntries = (unsigned __int16)v27 | 0x80070000;
          }
          else
          {
            LastError = GetLastError();
            AclForExplicitEntries = LastError;
            if ( LastError > 0 )
              AclForExplicitEntries = (unsigned __int16)LastError | 0x80070000;
            if ( AclForExplicitEntries >= 0 )
              AclForExplicitEntries = -2147467259;
          }
          LocalFree(v26);
        }
      }
    }
    else if ( !v3 )
    {
      AclForExplicitEntries = CAceList::SetExplicitAllowAce(v11, v4, v13, v14);
      if ( AclForExplicitEntries >= 0 )
        goto LABEL_30;
    }
    CAceList::~CAceList(v11);
    v15 = v11;
    goto LABEL_7;
  }
  return (unsigned int)AclForExplicitEntries;
}

```

## disassembly

```asm
0x180006180  mov     rax, rsp
0x180006183  mov     [rax+18h], r8d
0x180006187  mov     [rax+10h], rdx
0x18000618b  mov     [rax+8], rcx
0x18000618f  push    rbp
0x180006190  push    rbx
0x180006191  push    rsi
0x180006192  push    rdi
0x180006193  push    r12
0x180006195  push    r13
0x180006197  push    r14
0x180006199  push    r15
0x18000619b  lea     rbp, [rax-5Fh]
0x18000619f  sub     rsp, 88h
0x1800061a6  xor     r15d, r15d
0x1800061a9  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x1800061ad  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800061b2  mov     r14, rdx
0x1800061b5  lea     rax, [rbp+57h+arg_18]
0x1800061b9  mov     [rsp+0C0h+ppSacl], r15; ppSacl
0x1800061be  mov     [rsp+0C0h+ppDacl], rax; ppDacl
0x1800061c3  xor     r9d, r9d; ppsidOwner
0x1800061c6  lea     edi, [r15+1]
0x1800061ca  mov     [rbp+57h+ppSecurityDescriptor], r15
0x1800061ce  mov     edx, edi; ObjectType
0x1800061d0  mov     [rbp+57h+arg_18], r15
0x1800061d4  lea     r8d, [r15+4]; SecurityInfo
0x1800061d8  mov     [rsp+0C0h+ppsidGroup], r15; ppsidGroup
0x1800061dd  mov     r12, rcx
0x1800061e0  call    cs:__imp_GetNamedSecurityInfoW
0x1800061e6  mov     ebx, eax
0x1800061e8  test    eax, eax
0x1800061ea  jle     short loc_1800061F5
0x1800061ec  movzx   ebx, ax
0x1800061ef  or      ebx, 80070000h
0x1800061f5  test    ebx, ebx
0x1800061f7  js      loc_18000643C
0x1800061fd  mov     rbx, [rbp+57h+arg_18]
0x180006201  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006208  mov     r13d, 20h ; ' '
0x18000620e  mov     ecx, r13d; unsigned __int64
0x180006211  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006216  mov     rsi, rax
0x180006219  test    rax, rax
0x18000621c  jz      loc_18000642D
0x180006222  mov     rdx, rbx; struct _ACL *
0x180006225  mov     [rax], r15
0x180006228  mov     rcx, rax; this
0x18000622b  mov     [rax+8], r15
0x18000622f  mov     [rax+10h], r15
0x180006233  mov     [rax+18h], rdi
0x180006237  call    ?_InitFromAcl@CAceList@@AEAAJPEAU_ACL@@@Z; CAceList::_InitFromAcl(_ACL *)
0x18000623c  test    eax, eax
0x18000623e  mov     rdi, rsi
0x180006241  mov     ebx, eax
0x180006243  cmovs   rdi, r15
0x180006247  jns     short loc_180006261
0x180006249  mov     rcx, rsi; this
0x18000624c  call    ??1CAceList@@QEAA@XZ; CAceList::~CAceList(void)
0x180006251  mov     edx, r13d
0x180006254  mov     rcx, rsi; Block
0x180006257  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000625c  jmp     loc_180006432
0x180006261  lea     r13, [rdi+8]
0x180006265  mov     rax, [r13+0]
0x180006269  test    rax, rax
0x18000626c  jz      short loc_1800062BC
0x18000626e  mov     r12d, [rax]
0x180006271  xor     r14d, r14d
0x180006274  test    r12d, r12d
0x180006277  jle     short loc_1800062B4
0x180006279  mov     rcx, [r13+0]; hdpa
0x18000627d  movsxd  rdx, r14d; i
0x180006280  call    cs:g_pfn_DPA_GetPtr
0x180006286  mov     rsi, rax
0x180006289  cmp     [rax+18h], r15d
0x18000628d  jnz     short loc_1800062A7
0x18000628f  cmp     byte ptr [rax+1], 0Bh
0x180006293  jnz     short loc_1800062A7
0x180006295  mov     rdx, [rbp+57h+pSid2]; pSid2
0x180006299  mov     rcx, [rax+8]; pSid1
0x18000629d  call    cs:__imp_EqualSid
0x1800062a3  test    eax, eax
0x1800062a5  jnz     short loc_1800062B1
0x1800062a7  inc     r14d
0x1800062aa  cmp     r14d, r12d
0x1800062ad  jl      short loc_180006279
0x1800062af  jmp     short loc_1800062B4
0x1800062b1  mov     r15, rsi
0x1800062b4  mov     r14, [rbp+57h+pSid2]
0x1800062b8  mov     r12, [rbp+57h+arg_0]
0x1800062bc  cmp     [rbp+57h+arg_10], 0
0x1800062c0  jz      short loc_18000633B
0x1800062c2  test    r15, r15
0x1800062c5  jz      loc_180006413
0x1800062cb  xor     ebx, ebx
0x1800062cd  mov     rcx, [r13+0]; hdpa
0x1800062d1  test    rcx, rcx
0x1800062d4  jz      short loc_1800062DA
0x1800062d6  mov     eax, [rcx]
0x1800062d8  jmp     short loc_1800062DC
0x1800062da  xor     eax, eax
0x1800062dc  cmp     ebx, eax
0x1800062de  jge     short loc_180006359
0x1800062e0  movsxd  rdx, ebx; i
0x1800062e3  call    cs:g_pfn_DPA_GetPtr
0x1800062e9  mov     rcx, r14; pSid1
0x1800062ec  mov     rsi, rax
0x1800062ef  mov     rdx, [rax+8]; pSid2
0x1800062f3  call    cs:__imp_EqualSid
0x1800062f9  test    eax, eax
0x1800062fb  jz      short loc_180006337
0x1800062fd  cmp     byte ptr [rsi+1], 0Bh
0x180006301  jnz     short loc_180006337
0x180006303  mov     rcx, [r13+0]; hdpa
0x180006307  mov     edx, ebx; i
0x180006309  call    cs:g_pfn_DPA_DeletePtr
0x18000630f  mov     rcx, [rsi+8]; hMem
0x180006313  call    cs:__imp_LocalFree
0x180006319  mov     rcx, [rsi+10h]; hMem
0x18000631d  call    cs:__imp_LocalFree
0x180006323  btr     dword ptr [rsi+1Ch], 1Fh
0x180006328  mov     edx, 20h ; ' '
0x18000632d  mov     rcx, rsi; Block
0x180006330  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006335  dec     ebx
0x180006337  inc     ebx
0x180006339  jmp     short loc_1800062CD
0x18000633b  test    r15, r15
0x18000633e  jnz     loc_180006413
0x180006344  mov     rdx, r14; void *
0x180006347  mov     rcx, rdi; this
0x18000634a  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x18000634f  mov     ebx, eax
0x180006351  test    eax, eax
0x180006353  js      loc_180006413
0x180006359  lea     r8, [rbp+57h+pDacl]; struct _ACL **
0x18000635d  mov     [rbp+57h+pDacl], 0
0x180006365  mov     rcx, rdi; this
0x180006368  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x18000636d  mov     ebx, eax
0x18000636f  test    eax, eax
0x180006371  js      loc_180006413
0x180006377  xor     eax, eax
0x180006379  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000637d  xorps   xmm0, xmm0
0x180006380  mov     [rbp+57h+var_50], rax
0x180006384  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180006388  lea     ebx, [rax+1]
0x18000638b  mov     edx, ebx; dwRevision
0x18000638d  movups  [rbp+57h+var_60], xmm0
0x180006391  call    cs:__imp_InitializeSecurityDescriptor
0x180006397  mov     rsi, [rbp+57h+pDacl]
0x18000639b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000639f  mov     r8, rsi; pDacl
0x1800063a2  xor     r9d, r9d; bDaclDefaulted
0x1800063a5  mov     edx, ebx; bDaclPresent
0x1800063a7  call    cs:__imp_SetSecurityDescriptorDacl
0x1800063ad  test    eax, eax
0x1800063af  jz      short loc_1800063EB
0x1800063b1  mov     [rsp+0C0h+ppSacl], 0; pSacl
0x1800063ba  lea     r8d, [rbx+3]; SecurityInfo
0x1800063be  mov     [rsp+0C0h+ppDacl], rsi; pDacl
0x1800063c3  xor     r9d, r9d; psidOwner
0x1800063c6  mov     edx, ebx; ObjectType
0x1800063c8  mov     [rsp+0C0h+ppsidGroup], 0; psidGroup
0x1800063d1  mov     rcx, r12; pObjectName
0x1800063d4  call    cs:__imp_SetNamedSecurityInfoW
0x1800063da  mov     ebx, eax
0x1800063dc  test    eax, eax
0x1800063de  jle     short loc_18000640A
0x1800063e0  movzx   ebx, ax
0x1800063e3  or      ebx, 80070000h
0x1800063e9  jmp     short loc_18000640A
0x1800063eb  call    cs:__imp_GetLastError
0x1800063f1  mov     ebx, eax
0x1800063f3  test    eax, eax
0x1800063f5  jle     short loc_180006400
0x1800063f7  movzx   ebx, ax
0x1800063fa  or      ebx, 80070000h
0x180006400  test    ebx, ebx
0x180006402  mov     eax, 80004005h
0x180006407  cmovns  ebx, eax
0x18000640a  mov     rcx, rsi; hMem
0x18000640d  call    cs:__imp_LocalFree
0x180006413  test    rdi, rdi
0x180006416  jz      short loc_180006432
0x180006418  mov     rcx, rdi; this
0x18000641b  call    ??1CAceList@@QEAA@XZ; CAceList::~CAceList(void)
0x180006420  mov     edx, 20h ; ' '
0x180006425  mov     rcx, rdi
0x180006428  jmp     loc_180006257
0x18000642d  mov     ebx, 8007000Eh
0x180006432  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x180006436  call    cs:__imp_LocalFree
0x18000643c  mov     eax, ebx
0x18000643e  add     rsp, 88h
0x180006445  pop     r15
0x180006447  pop     r14
0x180006449  pop     r13
0x18000644b  pop     r12
0x18000644d  pop     rdi
0x18000644e  pop     rsi
0x18000644f  pop     rbx
0x180006450  pop     rbp
0x180006451  retn
```
