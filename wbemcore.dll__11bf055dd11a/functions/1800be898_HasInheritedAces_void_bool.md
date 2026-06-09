# HasInheritedAces(void *,bool *)

- ea: `0x1800be898`
- end: `0x1800bec7b`
- name: `?HasInheritedAces@@YAJPEAXPEA_N@Z`
- size: `995`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800827d0`

## callees

- `0x18000b140`
- `0x18009a79c`
- `0x1800be898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beabf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beabf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800be8d5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800be8d5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800beab5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800beab5`
- `wbemcomn!??0CNtAcl@@QEAA@PEAU_ACL@@@Z` at `0x1800be958`
- `wbemcomn!??0CNtAcl@@QEAA@PEAU_ACL@@@Z` at `0x1800beb2f`
- `wbemcomn!??0CNtAcl@@QEAA@PEAU_ACL@@@Z` at `0x1800be958`
- `wbemcomn!??0CNtAcl@@QEAA@PEAU_ACL@@@Z` at `0x1800beb2f`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800be993`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800beb6a`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800be993`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800beb6a`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800be9a0`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800beb77`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800be9a0`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800beb77`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800bea7b`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800bea8a`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800bec5b`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800bea7b`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800bea8a`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800bec5b`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800be963`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800beb3a`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800be963`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800beb3a`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800be97a`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800beb51`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800be97a`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800beb51`
- `wbemcomn!GetMemLogObject` at `0x1800be8f8`
- `wbemcomn!GetMemLogObject` at `0x1800be9ca`
- `wbemcomn!GetMemLogObject` at `0x1800bea26`
- `wbemcomn!GetMemLogObject` at `0x1800bead8`
- `wbemcomn!GetMemLogObject` at `0x1800beba1`
- `wbemcomn!GetMemLogObject` at `0x1800bebfd`
- `wbemcomn!GetMemLogObject` at `0x1800be8f8`
- `wbemcomn!GetMemLogObject` at `0x1800be9ca`
- `wbemcomn!GetMemLogObject` at `0x1800bea26`
- `wbemcomn!GetMemLogObject` at `0x1800bead8`
- `wbemcomn!GetMemLogObject` at `0x1800beba1`
- `wbemcomn!GetMemLogObject` at `0x1800bebfd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be903`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be9da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bea36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800beae3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bebb1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bec0d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be903`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be9da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bea36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800beae3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bebb1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bec0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HasInheritedAces(PSECURITY_DESCRIPTOR pSecurityDescriptor, bool *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v7; // rcx
  __int64 v8; // rdx
  int i; // ebx
  CNtAce *Ace; // rax
  CNtAce *v12; // rdi
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CNtAcl *v15; // rcx
  signed int v16; // eax
  CMemoryLog *v17; // rax
  int j; // ebx
  CNtAce *v19; // rax
  CNtAce *v20; // rdi
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  WINBOOL bDaclDefaulted; // [rsp+20h] [rbp-40h] BYREF
  WINBOOL bDaclPresent; // [rsp+24h] [rbp-3Ch] BYREF
  WINBOOL bSaclPresent; // [rsp+28h] [rbp-38h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-30h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v28[16]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v29[16]; // [rsp+50h] [rbp-10h] BYREF
  CNtAce *v30; // [rsp+90h] [rbp+30h] BYREF

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v5);
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v8 = 15;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v5);
    return v5;
  }
  if ( pDacl )
  {
    CNtAcl::CNtAcl((CNtAcl *)v28, pDacl);
    for ( i = CNtAcl::GetNumAces((CNtAcl *)v28) - 1; ; --i )
    {
      if ( i < 0 )
      {
        CNtAcl::~CNtAcl((CNtAcl *)v28);
        goto LABEL_32;
      }
      Ace = CNtAcl::GetAce((CNtAcl *)v28, i);
      v12 = Ace;
      if ( !Ace )
        break;
      v30 = Ace;
      if ( CNtAce::GetStatus(Ace) )
      {
        v13 = GetMemLogObject();
        v5 = -2147217407;
        CMemoryLog::Write(v13, -2147217407);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            2147749889LL);
        }
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
        goto LABEL_29;
      }
      if ( (CNtAce::GetFlags(v12) & 0x10) != 0 )
      {
        *a2 = 1;
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
        v5 = 0;
        goto LABEL_29;
      }
      CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
    }
    v14 = GetMemLogObject();
    v5 = -2147217407;
    CMemoryLog::Write(v14, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749889LL);
    }
LABEL_29:
    v15 = (CNtAcl *)v28;
LABEL_30:
    CNtAcl::~CNtAcl(v15);
    return v5;
  }
LABEL_32:
  pSacl = 0;
  bSaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bDaclDefaulted) )
  {
    v16 = GetLastError();
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, v5);
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v8 = 18;
    goto LABEL_10;
  }
  if ( pSacl )
  {
    CNtAcl::CNtAcl((CNtAcl *)v29, pSacl);
    for ( j = CNtAcl::GetNumAces((CNtAcl *)v29) - 1; j >= 0; --j )
    {
      v19 = CNtAcl::GetAce((CNtAcl *)v29, j);
      v20 = v19;
      if ( !v19 )
      {
        v22 = GetMemLogObject();
        v5 = -2147217407;
        CMemoryLog::Write(v22, -2147217407);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            2147749889LL);
        }
        goto LABEL_58;
      }
      v30 = v19;
      if ( CNtAce::GetStatus(v19) )
      {
        v21 = GetMemLogObject();
        v5 = -2147217407;
        CMemoryLog::Write(v21, -2147217407);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            2147749889LL);
        }
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
        goto LABEL_58;
      }
      if ( (CNtAce::GetFlags(v20) & 0x10) != 0 )
      {
        *a2 = 1;
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
        v5 = 0;
LABEL_58:
        v15 = (CNtAcl *)v29;
        goto LABEL_30;
      }
      CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
    }
    CNtAcl::~CNtAcl((CNtAcl *)v29);
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800be898  mov     [rsp-18h+arg_0], rbx
0x1800be89d  mov     [rsp-18h+arg_8], rsi
0x1800be8a2  push    rbp
0x1800be8a3  push    rdi
0x1800be8a4  push    r14
0x1800be8a6  mov     rbp, rsp
0x1800be8a9  sub     rsp, 60h
0x1800be8ad  mov     rsi, rdx
0x1800be8b0  mov     r14, rcx
0x1800be8b3  mov     [rbp+pDacl], 0
0x1800be8bb  mov     [rbp+bDaclPresent], 0
0x1800be8c2  mov     [rbp+bDaclDefaulted], 0
0x1800be8c9  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800be8cd  lea     r8, [rbp+pDacl]; pDacl
0x1800be8d1  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800be8d5  call    cs:__imp_GetSecurityDescriptorDacl
0x1800be8db  test    eax, eax
0x1800be8dd  jnz     short loc_1800BE947
0x1800be8df  call    cs:__imp_GetLastError
0x1800be8e5  mov     ebx, eax
0x1800be8e7  test    eax, eax
0x1800be8e9  jle     short loc_1800BE8F4
0x1800be8eb  movzx   ebx, ax
0x1800be8ee  or      ebx, 80070000h
0x1800be8f4  test    ebx, ebx
0x1800be8f6  jns     short loc_1800BE909
0x1800be8f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be8fe  mov     edx, ebx
0x1800be900  mov     rcx, rax
0x1800be903  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be909  lea     rax, WPP_GLOBAL_Control
0x1800be910  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be917  cmp     rcx, rax
0x1800be91a  jz      short loc_1800BE940
0x1800be91c  test    byte ptr [rcx+1Ch], 1
0x1800be920  jz      short loc_1800BE940
0x1800be922  cmp     byte ptr [rcx+19h], 2
0x1800be926  jb      short loc_1800BE940
0x1800be928  mov     edx, 0Fh
0x1800be92d  mov     r9d, ebx
0x1800be930  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800be937  mov     rcx, [rcx+10h]
0x1800be93b  call    WPP_SF_d
0x1800be940  mov     eax, ebx
0x1800be942  jmp     loc_1800BEC66
0x1800be947  mov     rdx, [rbp+pDacl]
0x1800be94b  test    rdx, rdx
0x1800be94e  jz      loc_1800BEA90
0x1800be954  lea     rcx, [rbp+var_20]
0x1800be958  call    cs:__imp_??0CNtAcl@@QEAA@PEAU_ACL@@@Z; CNtAcl::CNtAcl(_ACL *)
0x1800be95e  nop
0x1800be95f  lea     rcx, [rbp+var_20]
0x1800be963  call    cs:__imp_?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x1800be969  lea     ebx, [rax-1]
0x1800be96c  test    ebx, ebx
0x1800be96e  js      loc_1800BEA86
0x1800be974  mov     edx, ebx
0x1800be976  lea     rcx, [rbp+var_20]
0x1800be97a  call    cs:__imp_?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x1800be980  mov     rdi, rax
0x1800be983  test    rax, rax
0x1800be986  jz      loc_1800BEA26
0x1800be98c  mov     [rbp+arg_10], rax
0x1800be990  mov     rcx, rax
0x1800be993  call    cs:__imp_?GetStatus@CNtAce@@UEAAKXZ; CNtAce::GetStatus(void)
0x1800be999  test    eax, eax
0x1800be99b  jnz     short loc_1800BE9CA
0x1800be99d  mov     rcx, rdi
0x1800be9a0  call    cs:__imp_?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x1800be9a6  test    al, 10h
0x1800be9a8  jnz     short loc_1800BE9B7
0x1800be9aa  lea     rcx, [rbp+arg_10]
0x1800be9ae  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800be9b3  dec     ebx
0x1800be9b5  jmp     short loc_1800BE96C
0x1800be9b7  mov     byte ptr [rsi], 1
0x1800be9ba  lea     rcx, [rbp+arg_10]
0x1800be9be  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800be9c3  xor     ebx, ebx
0x1800be9c5  jmp     loc_1800BEA77
0x1800be9ca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be9d0  mov     ebx, 80041001h
0x1800be9d5  mov     edx, ebx
0x1800be9d7  mov     rcx, rax
0x1800be9da  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be9e0  lea     rax, WPP_GLOBAL_Control
0x1800be9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be9ee  cmp     rcx, rax
0x1800be9f1  jz      short loc_1800BEA1B
0x1800be9f3  test    byte ptr [rcx+1Ch], 1
0x1800be9f7  jz      short loc_1800BEA1B
0x1800be9f9  cmp     byte ptr [rcx+19h], 2
0x1800be9fd  jb      short loc_1800BEA1B
0x1800be9ff  mov     edx, 11h
0x1800bea04  mov     r9d, 80041001h
0x1800bea0a  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bea11  mov     rcx, [rcx+10h]
0x1800bea15  call    WPP_SF_d
0x1800bea1a  nop
0x1800bea1b  lea     rcx, [rbp+arg_10]
0x1800bea1f  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bea24  jmp     short loc_1800BEA77
0x1800bea26  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bea2c  mov     ebx, 80041001h
0x1800bea31  mov     edx, ebx
0x1800bea33  mov     rcx, rax
0x1800bea36  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bea3c  lea     rax, WPP_GLOBAL_Control
0x1800bea43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea4a  cmp     rcx, rax
0x1800bea4d  jz      short loc_1800BEA77
0x1800bea4f  test    byte ptr [rcx+1Ch], 1
0x1800bea53  jz      short loc_1800BEA77
0x1800bea55  cmp     byte ptr [rcx+19h], 2
0x1800bea59  jb      short loc_1800BEA77
0x1800bea5b  mov     edx, 10h
0x1800bea60  mov     r9d, 80041001h
0x1800bea66  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bea6d  mov     rcx, [rcx+10h]
0x1800bea71  call    WPP_SF_d
0x1800bea76  nop
0x1800bea77  lea     rcx, [rbp+var_20]
0x1800bea7b  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x1800bea81  jmp     loc_1800BE940
0x1800bea86  lea     rcx, [rbp+var_20]
0x1800bea8a  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x1800bea90  mov     [rbp+pSacl], 0
0x1800bea98  mov     [rbp+bSaclPresent], 0
0x1800bea9f  mov     [rbp+bDaclDefaulted], 0
0x1800beaa6  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x1800beaaa  lea     r8, [rbp+pSacl]; pSacl
0x1800beaae  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x1800beab2  mov     rcx, r14; pSecurityDescriptor
0x1800beab5  call    cs:__imp_GetSecurityDescriptorSacl
0x1800beabb  test    eax, eax
0x1800beabd  jnz     short loc_1800BEB1E
0x1800beabf  call    cs:__imp_GetLastError
0x1800beac5  mov     ebx, eax
0x1800beac7  test    eax, eax
0x1800beac9  jle     short loc_1800BEAD4
0x1800beacb  movzx   ebx, ax
0x1800beace  or      ebx, 80070000h
0x1800bead4  test    ebx, ebx
0x1800bead6  jns     short loc_1800BEAE9
0x1800bead8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800beade  mov     edx, ebx
0x1800beae0  mov     rcx, rax
0x1800beae3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800beae9  lea     rax, WPP_GLOBAL_Control
0x1800beaf0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beaf7  cmp     rcx, rax
0x1800beafa  jz      loc_1800BE940
0x1800beb00  test    byte ptr [rcx+1Ch], 1
0x1800beb04  jz      loc_1800BE940
0x1800beb0a  cmp     byte ptr [rcx+19h], 2
0x1800beb0e  jb      loc_1800BE940
0x1800beb14  mov     edx, 12h
0x1800beb19  jmp     loc_1800BE92D
0x1800beb1e  mov     rdx, [rbp+pSacl]
0x1800beb22  test    rdx, rdx
0x1800beb25  jz      loc_1800BEC61
0x1800beb2b  lea     rcx, [rbp+var_10]
0x1800beb2f  call    cs:__imp_??0CNtAcl@@QEAA@PEAU_ACL@@@Z; CNtAcl::CNtAcl(_ACL *)
0x1800beb35  nop
0x1800beb36  lea     rcx, [rbp+var_10]
0x1800beb3a  call    cs:__imp_?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x1800beb40  lea     ebx, [rax-1]
0x1800beb43  test    ebx, ebx
0x1800beb45  js      loc_1800BEC57
0x1800beb4b  mov     edx, ebx
0x1800beb4d  lea     rcx, [rbp+var_10]
0x1800beb51  call    cs:__imp_?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x1800beb57  mov     rdi, rax
0x1800beb5a  test    rax, rax
0x1800beb5d  jz      loc_1800BEBFD
0x1800beb63  mov     [rbp+arg_10], rax
0x1800beb67  mov     rcx, rax
0x1800beb6a  call    cs:__imp_?GetStatus@CNtAce@@UEAAKXZ; CNtAce::GetStatus(void)
0x1800beb70  test    eax, eax
0x1800beb72  jnz     short loc_1800BEBA1
0x1800beb74  mov     rcx, rdi
0x1800beb77  call    cs:__imp_?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x1800beb7d  test    al, 10h
0x1800beb7f  jnz     short loc_1800BEB8E
0x1800beb81  lea     rcx, [rbp+arg_10]
0x1800beb85  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800beb8a  dec     ebx
0x1800beb8c  jmp     short loc_1800BEB43
0x1800beb8e  mov     byte ptr [rsi], 1
0x1800beb91  lea     rcx, [rbp+arg_10]
0x1800beb95  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800beb9a  xor     ebx, ebx
0x1800beb9c  jmp     loc_1800BEC4E
0x1800beba1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800beba7  mov     ebx, 80041001h
0x1800bebac  mov     edx, ebx
0x1800bebae  mov     rcx, rax
0x1800bebb1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bebb7  lea     rax, WPP_GLOBAL_Control
0x1800bebbe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bebc5  cmp     rcx, rax
0x1800bebc8  jz      short loc_1800BEBF2
0x1800bebca  test    byte ptr [rcx+1Ch], 1
0x1800bebce  jz      short loc_1800BEBF2
0x1800bebd0  cmp     byte ptr [rcx+19h], 2
0x1800bebd4  jb      short loc_1800BEBF2
0x1800bebd6  mov     edx, 14h
0x1800bebdb  mov     r9d, 80041001h
0x1800bebe1  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bebe8  mov     rcx, [rcx+10h]
0x1800bebec  call    WPP_SF_d
0x1800bebf1  nop
0x1800bebf2  lea     rcx, [rbp+arg_10]
0x1800bebf6  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bebfb  jmp     short loc_1800BEC4E
0x1800bebfd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bec03  mov     ebx, 80041001h
0x1800bec08  mov     edx, ebx
0x1800bec0a  mov     rcx, rax
0x1800bec0d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bec13  lea     rax, WPP_GLOBAL_Control
0x1800bec1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bec21  cmp     rcx, rax
0x1800bec24  jz      short loc_1800BEC4E
0x1800bec26  test    byte ptr [rcx+1Ch], 1
0x1800bec2a  jz      short loc_1800BEC4E
0x1800bec2c  cmp     byte ptr [rcx+19h], 2
0x1800bec30  jb      short loc_1800BEC4E
0x1800bec32  mov     edx, 13h
0x1800bec37  mov     r9d, 80041001h
0x1800bec3d  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bec44  mov     rcx, [rcx+10h]
0x1800bec48  call    WPP_SF_d
0x1800bec4d  nop
0x1800bec4e  lea     rcx, [rbp+var_10]
0x1800bec52  jmp     loc_1800BEA7B
0x1800bec57  lea     rcx, [rbp+var_10]
0x1800bec5b  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x1800bec61  mov     byte ptr [rsi], 0
0x1800bec64  xor     eax, eax
0x1800bec66  lea     r11, [rsp+60h+var_s0]
0x1800bec6b  mov     rbx, [r11+20h]
0x1800bec6f  mov     rsi, [r11+28h]
0x1800bec73  mov     rsp, r11
0x1800bec76  pop     r14
0x1800bec78  pop     rdi
0x1800bec79  pop     rbp
0x1800bec7a  retn
```
