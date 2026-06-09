# CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,uchar,_ACL * *)

- ea: `0x180021730`
- end: `0x180021a46`
- name: `?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z`
- size: `790`
- prototype: `__int64 __fastcall(struct _ACL **, void **, int, DWORD, int *, char, struct _ACL **)`
- caller_count: `7`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180021a48`
- `0x1800221dc`
- `0x1800229d4`
- `0x180024d70`
- `0x1800251a8`
- `0x1800263bc`
- `0x180026634`

## callees

- `0x180021730`
- `0x180023a58`
- `0x18004d030`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x1800653ba`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800219fe`
- `KERNEL32!LocalFree` at `0x180021a0e`
- `KERNEL32!LocalFree` at `0x1800219fe`
- `KERNEL32!LocalFree` at `0x180021a0e`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800218cf`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800218cf`
- `ADVAPI32!GetLengthSid` at `0x180021831`
- `ADVAPI32!GetLengthSid` at `0x180021831`
- `ADVAPI32!InitializeAcl` at `0x18002187c`
- `ADVAPI32!InitializeAcl` at `0x18002187c`
- `ADVAPI32!GetAce` at `0x180021900`
- `ADVAPI32!GetAce` at `0x180021900`
- `ADVAPI32!GetAclInformation` at `0x18002198b`
- `ADVAPI32!GetAclInformation` at `0x18002198b`
- `ADVAPI32!SetEntriesInAclW` at `0x180021967`
- `ADVAPI32!SetEntriesInAclW` at `0x180021967`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x180021939`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x180021939`

## pseudocode

```c
__int64 __fastcall CRegAccount::AddAccess(
        struct _ACL **a1,
        void **a2,
        int a3,
        DWORD a4,
        int *a5,
        char a6,
        struct _ACL **a7)
{
  unsigned int DoesAccessExist; // ebx
  struct _ACL *v9; // rdi
  int v10; // r15d
  struct _ACL *v11; // r13
  __int64 v12; // r14
  int *v13; // r12
  int v14; // r8d
  void **v15; // rsi
  void *v16; // rcx
  struct _ACL *v17; // rax
  void **v18; // rax
  __int64 i; // rsi
  void *v20; // r9
  signed int v21; // esi
  signed int ExplicitEntriesFromAclW; // eax
  struct _ACL *v23; // rax
  struct _ACL **v24; // rsi
  DWORD nAclLength; // [rsp+30h] [rbp-C1h] BYREF
  int *v27; // [rsp+38h] [rbp-B9h]
  DWORD AccessMask; // [rsp+40h] [rbp-B1h]
  void **v29; // [rsp+48h] [rbp-A9h]
  PACL NewAcl; // [rsp+50h] [rbp-A1h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+58h] [rbp-99h] BYREF
  LPVOID pAce; // [rsp+60h] [rbp-91h] BYREF
  int *v33; // [rsp+68h] [rbp-89h]
  struct _ACL **v34; // [rsp+70h] [rbp-81h]
  struct _ACL **v35; // [rsp+78h] [rbp-79h]
  _BYTE pAclInformation[4]; // [rsp+80h] [rbp-71h] BYREF
  int v37; // [rsp+84h] [rbp-6Dh]
  int v38; // [rsp+88h] [rbp-69h]
  int v39[20]; // [rsp+90h] [rbp-61h] BYREF

  v33 = a5;
  v34 = a7;
  AccessMask = a4;
  DoesAccessExist = 0;
  v9 = 0;
  v29 = a2;
  v10 = 0;
  v35 = a1;
  v11 = 0;
  pAce = 0;
  nAclLength = 0;
  pListOfExplicitEntries = 0;
  NewAcl = 0;
  v27 = 0;
  if ( a1 )
    v11 = *a1;
  v12 = a3;
  if ( (unsigned __int64)a3 > 0x14 )
  {
    v27 = (int *)MemAllocClear(4LL * a3);
    v13 = v27;
    if ( !v27 )
    {
      DoesAccessExist = -2147024882;
      goto LABEL_47;
    }
  }
  else
  {
    v13 = v39;
    memset_0(v39, 0, sizeof(v39));
  }
  if ( !v11 )
  {
    v15 = v29;
    goto LABEL_11;
  }
  v14 = a3;
  v15 = v29;
  DoesAccessExist = CRegAccount::DoesAccessExist(v11, v29, v14, AccessMask, v13);
  if ( !DoesAccessExist )
  {
LABEL_11:
    if ( v12 > 0 )
    {
      do
      {
        v16 = v15[(_QWORD)v9];
        if ( v16 && !v13[(_QWORD)v9] )
        {
          ++v10;
          nAclLength += GetLengthSid(v16);
        }
        v9 = (struct _ACL *)((char *)v9 + 1);
      }
      while ( (__int64)v9 < v12 );
    }
    nAclLength += 4 * (v10 + 2 * (v10 + 1));
    v17 = (struct _ACL *)MemAllocClear(nAclLength);
    v9 = v17;
    if ( !v17 )
    {
LABEL_17:
      DoesAccessExist = -2147024882;
      goto LABEL_46;
    }
    if ( InitializeAcl(v17, nAclLength, 2u) )
    {
      if ( v33 )
        *v33 = v10 == 0;
      if ( v12 > 0 )
      {
        v18 = v29;
        for ( i = 0; i < v12; ++i )
        {
          v20 = v18[i];
          if ( v20 && !v13[i] )
          {
            if ( !AddAccessAllowedAce(v9, 2u, AccessMask, v20) )
              goto LABEL_19;
            v18 = v29;
          }
        }
      }
      if ( a6 && (v21 = 0, v10 > 0) )
      {
        while ( GetAce(v9, v21, &pAce) && pAce )
        {
          ++v21;
          *((_BYTE *)pAce + 1) = a6;
          if ( v21 >= v10 )
            goto LABEL_34;
        }
      }
      else
      {
LABEL_34:
        nAclLength = 0;
        ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(v9, &nAclLength, &pListOfExplicitEntries);
        if ( ExplicitEntriesFromAclW
          || (ExplicitEntriesFromAclW = SetEntriesInAclW(nAclLength, pListOfExplicitEntries, v11, &NewAcl)) != 0 )
        {
          DoesAccessExist = (unsigned __int16)ExplicitEntriesFromAclW | 0x80070000;
          if ( ExplicitEntriesFromAclW <= 0 )
            DoesAccessExist = ExplicitEntriesFromAclW;
          goto LABEL_46;
        }
        if ( NewAcl && GetAclInformation(NewAcl, pAclInformation, 0xCu, AclSizeInformation) && v37 )
        {
          MemFree(v9);
          v23 = (struct _ACL *)MemAllocClear((unsigned int)(v38 + v37));
          v9 = v23;
          if ( v23 )
          {
            memcpy_0(v23, NewAcl, (unsigned int)(v38 + v37));
            v24 = v34;
            if ( v35 == v34 )
              MemFree(v11);
            *v24 = v9;
            v9 = 0;
            goto LABEL_46;
          }
          goto LABEL_17;
        }
      }
    }
LABEL_19:
    DoesAccessExist = GetLastWin32Error();
  }
LABEL_46:
  v13 = v27;
LABEL_47:
  if ( pListOfExplicitEntries )
    LocalFree(pListOfExplicitEntries);
  if ( NewAcl )
    LocalFree(NewAcl);
  MemFree(v9);
  MemFree(v13);
  return DoesAccessExist;
}

```

## disassembly

```asm
0x180021730  push    rbp
0x180021732  push    rbx
0x180021733  push    rsi
0x180021734  push    rdi
0x180021735  push    r12
0x180021737  push    r13
0x180021739  push    r14
0x18002173b  push    r15
0x18002173d  lea     rbp, [rsp-7]
0x180021742  sub     rsp, 0F8h
0x180021749  mov     rax, cs:__security_cookie
0x180021750  xor     rax, rsp
0x180021753  mov     [rbp+3Fh+var_50], rax
0x180021757  mov     rax, [rbp+3Fh+arg_20]
0x18002175b  mov     [rsp+130h+var_C8], rax
0x180021760  mov     rax, [rbp+3Fh+arg_30]
0x180021764  mov     [rsp+130h+var_C0], rax
0x180021769  xor     eax, eax
0x18002176b  mov     [rsp+130h+AccessMask], r9d
0x180021770  mov     ebx, eax
0x180021772  movsxd  rsi, r8d
0x180021775  mov     edi, eax
0x180021777  mov     [rsp+130h+var_E8], rdx
0x18002177c  mov     r15d, eax
0x18002177f  mov     [rbp+3Fh+var_B8], rcx
0x180021783  mov     r13d, eax
0x180021786  mov     [rsp+130h+pAce], rax
0x18002178b  mov     [rsp+130h+nAclLength], eax
0x18002178f  mov     [rsp+130h+pListOfExplicitEntries], rax
0x180021794  mov     [rsp+130h+NewAcl], rax
0x180021799  mov     [rsp+130h+var_F8], rax
0x18002179e  test    rcx, rcx
0x1800217a1  jz      short loc_1800217A6
0x1800217a3  mov     r13, [rcx]
0x1800217a6  mov     r14, rsi
0x1800217a9  cmp     rsi, 14h
0x1800217ad  ja      short loc_1800217F0
0x1800217af  xor     edx, edx; Val
0x1800217b1  lea     rcx, [rbp+3Fh+var_A0]; void *
0x1800217b5  lea     r12, [rbp+3Fh+var_A0]
0x1800217b9  lea     r8d, [rdx+50h]; Size
0x1800217bd  call    memset_0
0x1800217c2  test    r13, r13
0x1800217c5  jz      short loc_180021814
0x1800217c7  mov     r9d, [rsp+130h+AccessMask]; unsigned int
0x1800217cc  mov     r8d, esi; int
0x1800217cf  mov     rsi, [rsp+130h+var_E8]
0x1800217d4  mov     rcx, r13; pAcl
0x1800217d7  mov     rdx, rsi; void **
0x1800217da  mov     [rsp+130h+var_110], r12; int *
0x1800217df  call    ?DoesAccessExist@CRegAccount@@CAJPEAU_ACL@@PEAPEAXHKPEAH@Z; CRegAccount::DoesAccessExist(_ACL *,void * *,int,ulong,int *)
0x1800217e4  mov     ebx, eax
0x1800217e6  test    eax, eax
0x1800217e8  jnz     loc_1800219EF
0x1800217ee  jmp     short loc_180021819
0x1800217f0  lea     rcx, ds:0[rsi*4]; unsigned __int64
0x1800217f8  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800217fd  mov     [rsp+130h+var_F8], rax
0x180021802  mov     r12, rax
0x180021805  test    rax, rax
0x180021808  jnz     short loc_1800217C2
0x18002180a  mov     ebx, 8007000Eh
0x18002180f  jmp     loc_1800219F4
0x180021814  mov     rsi, [rsp+130h+var_E8]
0x180021819  test    r14, r14
0x18002181c  jle     short loc_180021843
0x18002181e  mov     rcx, [rsi+rdi*8]; pSid
0x180021822  test    rcx, rcx
0x180021825  jz      short loc_18002183B
0x180021827  cmp     dword ptr [r12+rdi*4], 0
0x18002182c  jnz     short loc_18002183B
0x18002182e  inc     r15d
0x180021831  call    cs:__imp_GetLengthSid
0x180021837  add     [rsp+130h+nAclLength], eax
0x18002183b  inc     rdi
0x18002183e  cmp     rdi, r14
0x180021841  jl      short loc_18002181E
0x180021843  mov     eax, [rsp+130h+nAclLength]
0x180021847  lea     ecx, [r15+1]
0x18002184b  lea     ecx, [r15+rcx*2]
0x18002184f  lea     edx, [rax+rcx*4]
0x180021852  mov     ecx, edx; unsigned __int64
0x180021854  mov     [rsp+130h+nAclLength], edx
0x180021858  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18002185d  mov     rdi, rax
0x180021860  test    rax, rax
0x180021863  jnz     short loc_18002186F
0x180021865  mov     ebx, 8007000Eh
0x18002186a  jmp     loc_1800219EF
0x18002186f  mov     edx, [rsp+130h+nAclLength]; nAclLength
0x180021873  mov     r8d, 2; dwAclRevision
0x180021879  mov     rcx, rdi; pAcl
0x18002187c  call    cs:__imp_InitializeAcl
0x180021882  test    eax, eax
0x180021884  jnz     short loc_180021892
0x180021886  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18002188b  mov     ebx, eax
0x18002188d  jmp     loc_1800219EF
0x180021892  mov     rcx, [rsp+130h+var_C8]
0x180021897  test    rcx, rcx
0x18002189a  jz      short loc_1800218A6
0x18002189c  xor     eax, eax
0x18002189e  test    r15d, r15d
0x1800218a1  setz    al
0x1800218a4  mov     [rcx], eax
0x1800218a6  test    r14, r14
0x1800218a9  jle     short loc_1800218E6
0x1800218ab  mov     rax, [rsp+130h+var_E8]
0x1800218b0  xor     esi, esi
0x1800218b2  mov     r9, [rax+rsi*8]; pSid
0x1800218b6  test    r9, r9
0x1800218b9  jz      short loc_1800218DE
0x1800218bb  cmp     dword ptr [r12+rsi*4], 0
0x1800218c0  jnz     short loc_1800218DE
0x1800218c2  mov     r8d, [rsp+130h+AccessMask]; AccessMask
0x1800218c7  mov     edx, 2; dwAceRevision
0x1800218cc  mov     rcx, rdi; pAcl
0x1800218cf  call    cs:__imp_AddAccessAllowedAce
0x1800218d5  test    eax, eax
0x1800218d7  jz      short loc_180021886
0x1800218d9  mov     rax, [rsp+130h+var_E8]
0x1800218de  inc     rsi
0x1800218e1  cmp     rsi, r14
0x1800218e4  jl      short loc_1800218B2
0x1800218e6  mov     r14b, [rbp+3Fh+arg_28]
0x1800218ea  test    r14b, r14b
0x1800218ed  jz      short loc_180021927
0x1800218ef  xor     esi, esi
0x1800218f1  test    r15d, r15d
0x1800218f4  jle     short loc_180021927
0x1800218f6  lea     r8, [rsp+130h+pAce]; pAce
0x1800218fb  mov     edx, esi; dwAceIndex
0x1800218fd  mov     rcx, rdi; pAcl
0x180021900  call    cs:__imp_GetAce
0x180021906  test    eax, eax
0x180021908  jz      loc_180021886
0x18002190e  mov     rax, [rsp+130h+pAce]
0x180021913  test    rax, rax
0x180021916  jz      loc_180021886
0x18002191c  inc     esi
0x18002191e  mov     [rax+1], r14b
0x180021922  cmp     esi, r15d
0x180021925  jl      short loc_1800218F6
0x180021927  and     [rsp+130h+nAclLength], 0
0x18002192c  lea     r8, [rsp+130h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180021931  lea     rdx, [rsp+130h+nAclLength]; pcCountOfExplicitEntries
0x180021936  mov     rcx, rdi; pacl
0x180021939  call    cs:__imp_GetExplicitEntriesFromAclW
0x18002193f  test    eax, eax
0x180021941  jz      short loc_180021956
0x180021943  movzx   ebx, ax
0x180021946  or      ebx, 80070000h
0x18002194c  test    eax, eax
0x18002194e  cmovle  ebx, eax
0x180021951  jmp     loc_1800219EF
0x180021956  mov     rdx, [rsp+130h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002195b  lea     r9, [rsp+130h+NewAcl]; NewAcl
0x180021960  mov     ecx, [rsp+130h+nAclLength]; cCountOfExplicitEntries
0x180021964  mov     r8, r13; OldAcl
0x180021967  call    cs:__imp_SetEntriesInAclW
0x18002196d  test    eax, eax
0x18002196f  jnz     short loc_180021943
0x180021971  mov     rcx, [rsp+130h+NewAcl]; pAcl
0x180021976  test    rcx, rcx
0x180021979  jz      loc_180021886
0x18002197f  lea     r9d, [rax+2]; dwAclInformationClass
0x180021983  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180021987  lea     rdx, [rbp+3Fh+pAclInformation]; pAclInformation
0x18002198b  call    cs:__imp_GetAclInformation
0x180021991  test    eax, eax
0x180021993  jz      loc_180021886
0x180021999  cmp     [rbp+3Fh+var_AC], 0
0x18002199d  jz      loc_180021886
0x1800219a3  mov     rcx, rdi; lpMem
0x1800219a6  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800219ab  mov     ecx, [rbp+3Fh+var_AC]
0x1800219ae  add     ecx, [rbp+3Fh+var_A8]; unsigned __int64
0x1800219b1  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800219b6  mov     rdi, rax
0x1800219b9  test    rax, rax
0x1800219bc  jz      loc_180021865
0x1800219c2  mov     r8d, [rbp+3Fh+var_AC]
0x1800219c6  mov     rcx, rax; void *
0x1800219c9  add     r8d, [rbp+3Fh+var_A8]; Size
0x1800219cd  mov     rdx, [rsp+130h+NewAcl]; Src
0x1800219d2  call    memcpy_0
0x1800219d7  mov     rsi, [rsp+130h+var_C0]
0x1800219dc  cmp     [rbp+3Fh+var_B8], rsi
0x1800219e0  jnz     short loc_1800219EA
0x1800219e2  mov     rcx, r13; lpMem
0x1800219e5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800219ea  mov     [rsi], rdi
0x1800219ed  xor     edi, edi
0x1800219ef  mov     r12, [rsp+130h+var_F8]
0x1800219f4  mov     rcx, [rsp+130h+pListOfExplicitEntries]; hMem
0x1800219f9  test    rcx, rcx
0x1800219fc  jz      short loc_180021A04
0x1800219fe  call    cs:__imp_LocalFree
0x180021a04  mov     rcx, [rsp+130h+NewAcl]; hMem
0x180021a09  test    rcx, rcx
0x180021a0c  jz      short loc_180021A14
0x180021a0e  call    cs:__imp_LocalFree
0x180021a14  mov     rcx, rdi; lpMem
0x180021a17  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180021a1c  mov     rcx, r12; lpMem
0x180021a1f  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180021a24  mov     eax, ebx
0x180021a26  mov     rcx, [rbp+3Fh+var_50]
0x180021a2a  xor     rcx, rsp; StackCookie
0x180021a2d  call    __security_check_cookie
0x180021a32  add     rsp, 0F8h
0x180021a39  pop     r15
0x180021a3b  pop     r14
0x180021a3d  pop     r13
0x180021a3f  pop     r12
0x180021a41  pop     rdi
0x180021a42  pop     rsi
0x180021a43  pop     rbx
0x180021a44  pop     rbp
0x180021a45  retn
```
