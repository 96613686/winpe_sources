# CAceList::_InitFromAcl(_ACL *)

- ea: `0x18000731c`
- end: `0x18000758c`
- name: `?_InitFromAcl@CAceList@@AEAAJPEAU_ACL@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct _DPA **this, struct _ACL *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006180`

## callees

- `0x180002230`
- `0x180002600`
- `0x18000260c`
- `0x1800071a8`
- `0x18000731c`
- `0x18000765c`
- `0x180007980`
- `0x180007c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000753e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000753e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800073da`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800073da`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007449`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007449`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800073b0`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800073b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000751a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000751a`

## pseudocode

```c
__int64 __fastcall CAceList::_InitFromAcl(struct _DPA **this, struct _ACL *a2)
{
  HDPA v4; // rax
  HDPA v5; // rax
  HDPA v6; // rax
  int v7; // ebx
  DWORD v8; // ebp
  char *v9; // r14
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  unsigned __int8 v12; // cl
  DWORD LengthSid; // eax
  char *v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 Ace; // rax
  struct _DPA *v20; // rcx
  signed int LastError; // eax
  LPVOID pAce; // [rsp+40h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+48h] [rbp-40h] BYREF
  int v25; // [rsp+50h] [rbp-38h]

  v4 = g_pfn_DPA_Create(5);
  *this = v4;
  if ( v4 && (v5 = g_pfn_DPA_Create(5), (this[1] = v5) != 0) && (v6 = g_pfn_DPA_Create(5), (this[2] = v6) != 0) )
  {
    v7 = 0;
    if ( a2 )
    {
      pAclInformation = 0;
      v25 = 0;
      GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation);
      v8 = 0;
      do
      {
        if ( v8 >= (unsigned int)pAclInformation )
          return (unsigned int)v7;
        pAce = 0;
        if ( !GetAce(a2, v8, &pAce) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 >= 0 )
            return (unsigned int)-2147467259;
          return (unsigned int)v7;
        }
        v9 = (char *)pAce;
        v7 = -2147024882;
        v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        v11 = v10;
        if ( !v10 )
          goto LABEL_30;
        *v10 = 0x80000;
        v10[1] = 0;
        v10[2] = 0;
        v10[3] = 0;
        if ( !v9 )
        {
          v7 = -2147024809;
LABEL_29:
          LocalFree((HLOCAL)v11[1]);
          LocalFree((HLOCAL)v11[2]);
          *((_DWORD *)v11 + 7) &= ~0x80000000;
          operator delete(v11);
          goto LABEL_30;
        }
        v12 = *v9;
        if ( *v9 == 9 )
        {
          LengthSid = GetLengthSid(v9 + 8);
          v12 = *v9;
          v14 = &v9[LengthSid + 8];
        }
        else
        {
          v14 = 0;
        }
        v7 = CAce::_Init((CAce *)v11, v9 + 8, *((_DWORD *)v9 + 1), v9[1], v12, *((_WORD *)v9 + 1), v14);
        if ( v7 < 0 )
          goto LABEL_29;
        v16 = *((_DWORD *)v11 + 7);
        v17 = v16 & 0x20;
        if ( (v16 & 0x20) != 0 )
        {
          v18 = v16 & 1;
        }
        else
        {
          v18 = v16 & 1;
          if ( !v18 )
          {
            LOBYTE(v15) = -1;
            Ace = CAceList::s_FindAce(v17, this, 0, v15, v11);
            if ( Ace )
              goto LABEL_18;
            v20 = *this;
            goto LABEL_26;
          }
        }
        if ( (_DWORD)v17 || !v18 )
        {
          v20 = this[2];
        }
        else
        {
          LOBYTE(v15) = -1;
          Ace = CAceList::s_FindAce(v17, this + 1, 0, v15, v11);
          if ( Ace )
          {
LABEL_18:
            v7 = 1;
            *(_DWORD *)(Ace + 4) |= *((_DWORD *)v11 + 1);
            goto LABEL_28;
          }
          v20 = this[1];
        }
LABEL_26:
        v7 = 0;
        if ( DPA_InsertPtr(v20, 0x7FFFFFFF, v11) == -1 )
          v7 = -2147024882;
LABEL_28:
        if ( v7 )
          goto LABEL_29;
LABEL_30:
        ++v8;
      }
      while ( v7 >= 0 );
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000731c  mov     [rsp+arg_10], rbx
0x180007321  mov     [rsp+arg_18], rbp
0x180007326  push    rsi
0x180007327  push    rdi
0x180007328  push    r12
0x18000732a  push    r14
0x18000732c  push    r15
0x18000732e  sub     rsp, 60h
0x180007332  mov     rax, cs:__security_cookie
0x180007339  xor     rax, rsp
0x18000733c  mov     [rsp+88h+var_30], rax
0x180007341  mov     r15, rcx
0x180007344  mov     ebx, 5
0x180007349  mov     ecx, ebx; cItemGrow
0x18000734b  mov     r12, rdx
0x18000734e  call    cs:g_pfn_DPA_Create
0x180007354  mov     [r15], rax
0x180007357  test    rax, rax
0x18000735a  jz      loc_18000755F
0x180007360  mov     ecx, ebx; cItemGrow
0x180007362  call    cs:g_pfn_DPA_Create
0x180007368  mov     [r15+8], rax
0x18000736c  test    rax, rax
0x18000736f  jz      loc_18000755F
0x180007375  mov     ecx, ebx; cItemGrow
0x180007377  call    cs:g_pfn_DPA_Create
0x18000737d  mov     [r15+10h], rax
0x180007381  test    rax, rax
0x180007384  jz      loc_18000755F
0x18000738a  xor     ebx, ebx
0x18000738c  test    r12, r12
0x18000738f  jz      loc_180007564
0x180007395  xor     eax, eax
0x180007397  lea     r9d, [rbx+2]; dwAclInformationClass
0x18000739b  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x18000739f  mov     [rsp+88h+pAclInformation], rax
0x1800073a4  lea     rdx, [rsp+88h+pAclInformation]; pAclInformation
0x1800073a9  mov     [rsp+88h+var_38], eax
0x1800073ad  mov     rcx, r12; pAcl
0x1800073b0  call    cs:__imp_GetAclInformation
0x1800073b6  xor     ebp, ebp
0x1800073b8  mov     esi, 8007000Eh
0x1800073bd  cmp     ebp, dword ptr [rsp+88h+pAclInformation]
0x1800073c1  jnb     loc_180007564
0x1800073c7  lea     r8, [rsp+88h+pAce]; pAce
0x1800073cc  mov     [rsp+88h+pAce], 0
0x1800073d5  mov     edx, ebp; dwAceIndex
0x1800073d7  mov     rcx, r12; pAcl
0x1800073da  call    cs:__imp_GetAce
0x1800073e0  test    eax, eax
0x1800073e2  jz      loc_18000753E
0x1800073e8  mov     r14, [rsp+88h+pAce]
0x1800073ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800073f4  mov     ecx, 20h ; ' '; unsigned __int64
0x1800073f9  mov     ebx, esi
0x1800073fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007400  mov     rdi, rax
0x180007403  test    rax, rax
0x180007406  jz      loc_180007532
0x18000740c  mov     qword ptr [rax], 80000h
0x180007413  mov     qword ptr [rax+8], 0
0x18000741b  mov     qword ptr [rax+10h], 0
0x180007423  mov     qword ptr [rax+18h], 0
0x18000742b  test    r14, r14
0x18000742e  jnz     short loc_18000743A
0x180007430  mov     ebx, 80070057h
0x180007435  jmp     loc_18000750C
0x18000743a  mov     cl, [r14]
0x18000743d  lea     rbx, [r14+8]
0x180007441  cmp     cl, 9
0x180007444  jnz     short loc_180007459
0x180007446  mov     rcx, rbx; pSid
0x180007449  call    cs:__imp_GetLengthSid
0x18000744f  mov     cl, [r14]
0x180007452  mov     edx, eax
0x180007454  add     rdx, rbx
0x180007457  jmp     short loc_18000745B
0x180007459  xor     edx, edx
0x18000745b  movzx   eax, word ptr [r14+2]
0x180007460  mov     r9b, [r14+1]; unsigned __int8
0x180007464  mov     r8d, [r14+4]; unsigned int
0x180007468  mov     [rsp+88h+var_58], rdx; void *
0x18000746d  mov     rdx, rbx; void *
0x180007470  mov     [rsp+88h+var_60], ax; unsigned __int16
0x180007475  mov     [rsp+88h+var_68], cl; unsigned __int8
0x180007479  mov     rcx, rdi; this
0x18000747c  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x180007481  mov     ebx, eax
0x180007483  test    eax, eax
0x180007485  js      loc_18000750C
0x18000748b  mov     eax, [rdi+1Ch]
0x18000748e  mov     ecx, eax
0x180007490  and     ecx, 20h
0x180007493  jnz     short loc_1800074C4
0x180007495  and     eax, 1
0x180007498  jnz     short loc_1800074C7
0x18000749a  mov     r9b, 0FFh
0x18000749d  mov     qword ptr [rsp+88h+var_68], rdi
0x1800074a2  xor     r8d, r8d
0x1800074a5  mov     rdx, r15
0x1800074a8  call    ?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z; CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)
0x1800074ad  test    rax, rax
0x1800074b0  jz      short loc_1800074BF
0x1800074b2  mov     ecx, [rdi+4]
0x1800074b5  mov     ebx, 1
0x1800074ba  or      [rax+4], ecx
0x1800074bd  jmp     short loc_180007508
0x1800074bf  mov     rcx, [r15]
0x1800074c2  jmp     short loc_1800074F2
0x1800074c4  and     eax, 1
0x1800074c7  test    ecx, ecx
0x1800074c9  jnz     short loc_1800074EE
0x1800074cb  test    eax, eax
0x1800074cd  jz      short loc_1800074EE
0x1800074cf  mov     r9b, 0FFh
0x1800074d2  mov     qword ptr [rsp+88h+var_68], rdi
0x1800074d7  xor     r8d, r8d
0x1800074da  lea     rdx, [r15+8]
0x1800074de  call    ?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z; CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)
0x1800074e3  test    rax, rax
0x1800074e6  jnz     short loc_1800074B2
0x1800074e8  mov     rcx, [r15+8]
0x1800074ec  jmp     short loc_1800074F2
0x1800074ee  mov     rcx, [r15+10h]; hdpa
0x1800074f2  mov     r8, rdi; p
0x1800074f5  mov     edx, 7FFFFFFFh; i
0x1800074fa  call    cs:__imp_DPA_InsertPtr
0x180007500  xor     ebx, ebx
0x180007502  cmp     eax, 0FFFFFFFFh
0x180007505  cmovz   ebx, esi
0x180007508  test    ebx, ebx
0x18000750a  jz      short loc_180007532
0x18000750c  mov     rcx, [rdi+8]; hMem
0x180007510  call    cs:__imp_LocalFree
0x180007516  mov     rcx, [rdi+10h]; hMem
0x18000751a  call    cs:__imp_LocalFree
0x180007520  btr     dword ptr [rdi+1Ch], 1Fh
0x180007525  mov     edx, 20h ; ' '
0x18000752a  mov     rcx, rdi; Block
0x18000752d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007532  inc     ebp
0x180007534  test    ebx, ebx
0x180007536  jns     loc_1800073BD
0x18000753c  jmp     short loc_180007564
0x18000753e  call    cs:__imp_GetLastError
0x180007544  mov     ebx, eax
0x180007546  test    eax, eax
0x180007548  jle     short loc_180007553
0x18000754a  movzx   ebx, ax
0x18000754d  or      ebx, 80070000h
0x180007553  test    ebx, ebx
0x180007555  mov     eax, 80004005h
0x18000755a  cmovns  ebx, eax
0x18000755d  jmp     short loc_180007564
0x18000755f  mov     ebx, 8007000Eh
0x180007564  mov     eax, ebx
0x180007566  mov     rcx, [rsp+88h+var_30]
0x18000756b  xor     rcx, rsp; StackCookie
0x18000756e  call    __security_check_cookie
0x180007573  lea     r11, [rsp+88h+var_28]
0x180007578  mov     rbx, [r11+40h]
0x18000757c  mov     rbp, [r11+48h]
0x180007580  mov     rsp, r11
0x180007583  pop     r15
0x180007585  pop     r14
0x180007587  pop     r12
0x180007589  pop     rdi
0x18000758a  pop     rsi
0x18000758b  retn
```
