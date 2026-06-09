# CopyInheritedDACLAces(CNtSecurityDescriptor &,CNtSecurityDescriptor &)

- ea: `0x1800bdac0`
- end: `0x1800bde90`
- name: `?CopyInheritedDACLAces@@YAJAEAVCNtSecurityDescriptor@@0@Z`
- size: `976`
- prototype: `__int64 __fastcall(struct CNtSecurityDescriptor *, struct CNtSecurityDescriptor *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024428`
- `0x1800be2d0`

## callees

- `0x18000b140`
- `0x180060ba4`
- `0x18009a79c`
- `0x1800bdac0`

## import_xrefs

- `wbemcomn!?SetFlags@CNtAce@@UEAAXJ@Z` at `0x1800bdc19`
- `wbemcomn!?SetFlags@CNtAce@@UEAAXJ@Z` at `0x1800bdc19`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800bdbd8`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800bdbd8`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800bdbe9`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800bdbe9`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x1800bdb1f`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x1800bdb1f`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800bdba4`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800bdba4`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800bdbbf`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800bdbbf`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x1800bdc2a`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x1800bdc82`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x1800bdc2a`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x1800bdc82`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x1800bdadd`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x1800bdaf6`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x1800bdadd`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x1800bdaf6`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bdda3`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bddf0`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bdda3`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bddf0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800bdb08`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800bdb08`
- `wbemcomn!GetMemLogObject` at `0x1800bdb31`
- `wbemcomn!GetMemLogObject` at `0x1800bdc34`
- `wbemcomn!GetMemLogObject` at `0x1800bdca3`
- `wbemcomn!GetMemLogObject` at `0x1800bdcdf`
- `wbemcomn!GetMemLogObject` at `0x1800bdd3e`
- `wbemcomn!GetMemLogObject` at `0x1800bddb1`
- `wbemcomn!GetMemLogObject` at `0x1800bddfa`
- `wbemcomn!GetMemLogObject` at `0x1800bdb31`
- `wbemcomn!GetMemLogObject` at `0x1800bdc34`
- `wbemcomn!GetMemLogObject` at `0x1800bdca3`
- `wbemcomn!GetMemLogObject` at `0x1800bdcdf`
- `wbemcomn!GetMemLogObject` at `0x1800bdd3e`
- `wbemcomn!GetMemLogObject` at `0x1800bddb1`
- `wbemcomn!GetMemLogObject` at `0x1800bddfa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdb41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdc44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdcb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdcef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdd4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bddc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bde0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdb41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdc44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdcb3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdcef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bdd4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bddc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bde0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CopyInheritedDACLAces(struct CNtSecurityDescriptor *a1, struct CNtSecurityDescriptor *a2)
{
  CNtAcl *Dacl; // rax
  CNtAcl *v4; // r14
  CNtAcl *v5; // rsi
  CNtAcl *v6; // rax
  CNtAcl *v7; // rdi
  CMemoryLog *v8; // rax
  unsigned int v9; // ebx
  char v11; // r13
  int NumAces; // eax
  int i; // r15d
  CNtAce *Ace; // rax
  CNtAce *v15; // rbx
  int Flags; // eax
  int v17; // r8d
  int v18; // edx
  CMemoryLog *v19; // rax
  CClientCnt *v20; // rcx
  __int64 v21; // rdx
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CNtAcl *v30; // [rsp+20h] [rbp-20h] BYREF
  CNtAce *v31; // [rsp+28h] [rbp-18h] BYREF
  CNtAcl *v32[2]; // [rsp+30h] [rbp-10h] BYREF
  int v33; // [rsp+90h] [rbp+50h]
  CNtAcl *v34; // [rsp+98h] [rbp+58h] BYREF

  Dacl = CNtSecurityDescriptor::GetDacl(a2);
  v4 = Dacl;
  if ( !Dacl )
    return 0;
  v34 = Dacl;
  v5 = CNtSecurityDescriptor::GetDacl(a1);
  v30 = v5;
  v6 = (CNtAcl *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  if ( v6 )
    v7 = CNtAcl::CNtAcl(v6, 0x80u);
  else
    v7 = 0;
  if ( v7 )
  {
    v32[0] = v7;
    v11 = 0;
    NumAces = CNtAcl::GetNumAces(v4);
    v33 = NumAces;
    for ( i = 0; i < NumAces; ++i )
    {
      Ace = CNtAcl::GetAce(v4, i);
      v15 = Ace;
      if ( !Ace )
      {
        MemLogObject = GetMemLogObject();
        v9 = -2147217402;
        CMemoryLog::Write(MemLogObject, -2147217402);
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v26 = 63;
        v27 = 2147749894LL;
        goto LABEL_56;
      }
      v31 = Ace;
      if ( CNtAce::GetStatus(Ace) )
      {
        v23 = GetMemLogObject();
        v9 = -2147217407;
        CMemoryLog::Write(v23, -2147217407);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 64;
LABEL_37:
          WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749889LL);
        }
LABEL_38:
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v31);
LABEL_57:
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(v32);
        goto LABEL_10;
      }
      Flags = CNtAce::GetFlags(v15);
      if ( (Flags & 2) != 0 )
      {
        v17 = Flags ^ 2;
        if ( (Flags & 4) == 0 )
          v17 = Flags;
        v18 = (v17 | 0x10) ^ 8;
        if ( (v17 & 8) == 0 )
          v18 = v17 | 0x10;
        CNtAce::SetFlags(v15, v18);
        if ( v5 )
        {
          if ( !CNtAcl::AddAce(v5, v15) )
          {
            v19 = GetMemLogObject();
            v9 = -2147217407;
            CMemoryLog::Write(v19, -2147217407);
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v21 = 65;
              goto LABEL_37;
            }
            goto LABEL_38;
          }
        }
        else if ( !CNtAcl::AddAce(v7, v15) )
        {
          v22 = GetMemLogObject();
          v9 = -2147217407;
          CMemoryLog::Write(v22, -2147217407);
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = 66;
            goto LABEL_37;
          }
          goto LABEL_38;
        }
        v11 = 1;
      }
      CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v31);
      NumAces = v33;
    }
    if ( v11 )
    {
      if ( v5 )
      {
        if ( !CNtSecurityDescriptor::SetDacl(a1, v5) )
        {
          v28 = GetMemLogObject();
          v9 = -2147217407;
          CMemoryLog::Write(v28, -2147217407);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_57;
          }
          v26 = 67;
          goto LABEL_55;
        }
      }
      else if ( !CNtSecurityDescriptor::SetDacl(a1, v7) )
      {
        v29 = GetMemLogObject();
        v9 = -2147217407;
        CMemoryLog::Write(v29, -2147217407);
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v26 = 68;
LABEL_55:
        v27 = 2147749889LL;
LABEL_56:
        WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v27);
        goto LABEL_57;
      }
    }
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(v32);
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v30);
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v34);
    return 0;
  }
  v8 = GetMemLogObject();
  v9 = -2147217402;
  CMemoryLog::Write(v8, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749894LL);
  }
LABEL_10:
  CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v30);
  CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v34);
  return v9;
}

```

## disassembly

```asm
0x1800bdac0  mov     [rsp-38h+arg_0], rbx
0x1800bdac5  push    rbp
0x1800bdac6  push    rsi
0x1800bdac7  push    rdi
0x1800bdac8  push    r12
0x1800bdaca  push    r13
0x1800bdacc  push    r14
0x1800bdace  push    r15
0x1800bdad0  mov     rbp, rsp
0x1800bdad3  sub     rsp, 40h
0x1800bdad7  mov     r12, rcx
0x1800bdada  mov     rcx, rdx
0x1800bdadd  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ; CNtSecurityDescriptor::GetDacl(void)
0x1800bdae3  mov     r14, rax
0x1800bdae6  test    rax, rax
0x1800bdae9  jz      loc_1800BDE76
0x1800bdaef  mov     [rbp+arg_18], rax
0x1800bdaf3  mov     rcx, r12
0x1800bdaf6  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ; CNtSecurityDescriptor::GetDacl(void)
0x1800bdafc  mov     rsi, rax
0x1800bdaff  mov     [rbp+var_20], rax
0x1800bdb03  mov     ecx, 10h
0x1800bdb08  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800bdb0e  mov     [rbp+arg_10], rax
0x1800bdb12  test    rax, rax
0x1800bdb15  jz      short loc_1800BDB2A
0x1800bdb17  mov     edx, 80h
0x1800bdb1c  mov     rcx, rax
0x1800bdb1f  call    cs:__imp_??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
0x1800bdb25  mov     rdi, rax
0x1800bdb28  jmp     short loc_1800BDB2C
0x1800bdb2a  xor     edi, edi
0x1800bdb2c  test    rdi, rdi
0x1800bdb2f  jnz     short loc_1800BDB9A
0x1800bdb31  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bdb37  mov     ebx, 80041006h
0x1800bdb3c  mov     edx, ebx
0x1800bdb3e  mov     rcx, rax
0x1800bdb41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bdb47  lea     rax, WPP_GLOBAL_Control
0x1800bdb4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdb55  cmp     rcx, rax
0x1800bdb58  jz      short loc_1800BDB80
0x1800bdb5a  test    byte ptr [rcx+1Ch], 1
0x1800bdb5e  jz      short loc_1800BDB80
0x1800bdb60  cmp     byte ptr [rcx+19h], 2
0x1800bdb64  jb      short loc_1800BDB80
0x1800bdb66  lea     edx, [rdi+3Eh]
0x1800bdb69  mov     r9d, 80041006h
0x1800bdb6f  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bdb76  mov     rcx, [rcx+10h]
0x1800bdb7a  call    WPP_SF_d
0x1800bdb7f  nop
0x1800bdb80  lea     rcx, [rbp+var_20]
0x1800bdb84  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bdb89  nop
0x1800bdb8a  lea     rcx, [rbp+arg_18]
0x1800bdb8e  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bdb93  mov     eax, ebx
0x1800bdb95  jmp     loc_1800BDE78
0x1800bdb9a  mov     [rbp+var_10], rdi
0x1800bdb9e  xor     r13b, r13b
0x1800bdba1  mov     rcx, r14
0x1800bdba4  call    cs:__imp_?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x1800bdbaa  mov     dword ptr [rbp+arg_10], eax
0x1800bdbad  xor     r15d, r15d
0x1800bdbb0  cmp     r15d, eax
0x1800bdbb3  jge     loc_1800BDD8F
0x1800bdbb9  mov     edx, r15d
0x1800bdbbc  mov     rcx, r14
0x1800bdbbf  call    cs:__imp_?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x1800bdbc5  mov     rbx, rax
0x1800bdbc8  test    rax, rax
0x1800bdbcb  jz      loc_1800BDD3E
0x1800bdbd1  mov     [rbp+var_18], rax
0x1800bdbd5  mov     rcx, rax
0x1800bdbd8  call    cs:__imp_?GetStatus@CNtAce@@UEAAKXZ; CNtAce::GetStatus(void)
0x1800bdbde  test    eax, eax
0x1800bdbe0  jnz     loc_1800BDCDF
0x1800bdbe6  mov     rcx, rbx
0x1800bdbe9  call    cs:__imp_?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x1800bdbef  test    al, 2
0x1800bdbf1  jz      loc_1800BDC8F
0x1800bdbf7  mov     r8d, eax
0x1800bdbfa  xor     r8d, 2
0x1800bdbfe  test    al, 4
0x1800bdc00  cmovz   r8d, eax
0x1800bdc04  mov     eax, r8d
0x1800bdc07  or      eax, 10h
0x1800bdc0a  mov     edx, eax
0x1800bdc0c  xor     edx, 8
0x1800bdc0f  test    r8b, 8
0x1800bdc13  cmovz   edx, eax
0x1800bdc16  mov     rcx, rbx
0x1800bdc19  call    cs:__imp_?SetFlags@CNtAce@@UEAAXJ@Z; CNtAce::SetFlags(long)
0x1800bdc1f  mov     rdx, rbx
0x1800bdc22  test    rsi, rsi
0x1800bdc25  jz      short loc_1800BDC7F
0x1800bdc27  mov     rcx, rsi
0x1800bdc2a  call    cs:__imp_?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z; CNtAcl::AddAce(CNtAce *)
0x1800bdc30  test    eax, eax
0x1800bdc32  jnz     short loc_1800BDC8C
0x1800bdc34  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bdc3a  mov     ebx, 80041001h
0x1800bdc3f  mov     edx, ebx
0x1800bdc41  mov     rcx, rax
0x1800bdc44  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bdc4a  lea     rax, WPP_GLOBAL_Control
0x1800bdc51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdc58  cmp     rcx, rax
0x1800bdc5b  jz      loc_1800BDD30
0x1800bdc61  test    byte ptr [rcx+1Ch], 1
0x1800bdc65  jz      loc_1800BDD30
0x1800bdc6b  cmp     byte ptr [rcx+19h], 2
0x1800bdc6f  jb      loc_1800BDD30
0x1800bdc75  mov     edx, 41h ; 'A'
0x1800bdc7a  jmp     loc_1800BDD19
0x1800bdc7f  mov     rcx, rdi
0x1800bdc82  call    cs:__imp_?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z; CNtAcl::AddAce(CNtAce *)
0x1800bdc88  test    eax, eax
0x1800bdc8a  jz      short loc_1800BDCA3
0x1800bdc8c  mov     r13b, 1
0x1800bdc8f  lea     rcx, [rbp+var_18]
0x1800bdc93  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bdc98  inc     r15d
0x1800bdc9b  mov     eax, dword ptr [rbp+arg_10]
0x1800bdc9e  jmp     loc_1800BDBB0
0x1800bdca3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bdca9  mov     ebx, 80041001h
0x1800bdcae  mov     edx, ebx
0x1800bdcb0  mov     rcx, rax
0x1800bdcb3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bdcb9  lea     rax, WPP_GLOBAL_Control
0x1800bdcc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdcc7  cmp     rcx, rax
0x1800bdcca  jz      short loc_1800BDD30
0x1800bdccc  test    byte ptr [rcx+1Ch], 1
0x1800bdcd0  jz      short loc_1800BDD30
0x1800bdcd2  cmp     byte ptr [rcx+19h], 2
0x1800bdcd6  jb      short loc_1800BDD30
0x1800bdcd8  mov     edx, 42h ; 'B'
0x1800bdcdd  jmp     short loc_1800BDD19
0x1800bdcdf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bdce5  mov     ebx, 80041001h
0x1800bdcea  mov     edx, ebx
0x1800bdcec  mov     rcx, rax
0x1800bdcef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bdcf5  lea     rax, WPP_GLOBAL_Control
0x1800bdcfc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd03  cmp     rcx, rax
0x1800bdd06  jz      short loc_1800BDD30
0x1800bdd08  test    byte ptr [rcx+1Ch], 1
0x1800bdd0c  jz      short loc_1800BDD30
0x1800bdd0e  cmp     byte ptr [rcx+19h], 2
0x1800bdd12  jb      short loc_1800BDD30
0x1800bdd14  mov     edx, 40h ; '@'
0x1800bdd19  mov     r9d, 80041001h
0x1800bdd1f  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bdd26  mov     rcx, [rcx+10h]
0x1800bdd2a  call    WPP_SF_d
0x1800bdd2f  nop
0x1800bdd30  lea     rcx, [rbp+var_18]
0x1800bdd34  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bdd39  jmp     loc_1800BDE4B
0x1800bdd3e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bdd44  mov     ebx, 80041006h
0x1800bdd49  mov     edx, ebx
0x1800bdd4b  mov     rcx, rax
0x1800bdd4e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bdd54  lea     rax, WPP_GLOBAL_Control
0x1800bdd5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd62  cmp     rcx, rax
0x1800bdd65  jz      loc_1800BDE4B
0x1800bdd6b  test    byte ptr [rcx+1Ch], 1
0x1800bdd6f  jz      loc_1800BDE4B
0x1800bdd75  cmp     byte ptr [rcx+19h], 2
0x1800bdd79  jb      loc_1800BDE4B
0x1800bdd7f  mov     edx, 3Fh ; '?'
0x1800bdd84  mov     r9d, 80041006h
0x1800bdd8a  jmp     loc_1800BDE3A
0x1800bdd8f  test    r13b, r13b
0x1800bdd92  jz      loc_1800BDE59
0x1800bdd98  mov     rcx, r12
0x1800bdd9b  test    rsi, rsi
0x1800bdd9e  jz      short loc_1800BDDED
0x1800bdda0  mov     rdx, rsi
0x1800bdda3  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x1800bdda9  test    eax, eax
0x1800bddab  jnz     loc_1800BDE59
0x1800bddb1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bddb7  mov     ebx, 80041001h
0x1800bddbc  mov     edx, ebx
0x1800bddbe  mov     rcx, rax
0x1800bddc1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bddc7  lea     rax, WPP_GLOBAL_Control
0x1800bddce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bddd5  cmp     rcx, rax
0x1800bddd8  jz      short loc_1800BDE4B
0x1800bddda  test    byte ptr [rcx+1Ch], 1
0x1800bddde  jz      short loc_1800BDE4B
0x1800bdde0  cmp     byte ptr [rcx+19h], 2
0x1800bdde4  jb      short loc_1800BDE4B
0x1800bdde6  mov     edx, 43h ; 'C'
0x1800bddeb  jmp     short loc_1800BDE34
0x1800bdded  mov     rdx, rdi
0x1800bddf0  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x1800bddf6  test    eax, eax
0x1800bddf8  jnz     short loc_1800BDE59
0x1800bddfa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bde00  mov     ebx, 80041001h
0x1800bde05  mov     edx, ebx
0x1800bde07  mov     rcx, rax
0x1800bde0a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bde10  lea     rax, WPP_GLOBAL_Control
0x1800bde17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bde1e  cmp     rcx, rax
0x1800bde21  jz      short loc_1800BDE4B
0x1800bde23  test    byte ptr [rcx+1Ch], 1
0x1800bde27  jz      short loc_1800BDE4B
0x1800bde29  cmp     byte ptr [rcx+19h], 2
0x1800bde2d  jb      short loc_1800BDE4B
0x1800bde2f  mov     edx, 44h ; 'D'
0x1800bde34  mov     r9d, 80041001h
0x1800bde3a  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bde41  mov     rcx, [rcx+10h]
0x1800bde45  call    WPP_SF_d
0x1800bde4a  nop
0x1800bde4b  lea     rcx, [rbp+var_10]
0x1800bde4f  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bde54  jmp     loc_1800BDB80
0x1800bde59  lea     rcx, [rbp+var_10]
0x1800bde5d  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bde62  nop
0x1800bde63  lea     rcx, [rbp+var_20]
0x1800bde67  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bde6c  nop
0x1800bde6d  lea     rcx, [rbp+arg_18]
0x1800bde71  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bde76  xor     eax, eax
0x1800bde78  mov     rbx, [rsp+40h+arg_0]
0x1800bde80  add     rsp, 40h
0x1800bde84  pop     r15
0x1800bde86  pop     r14
0x1800bde88  pop     r13
0x1800bde8a  pop     r12
0x1800bde8c  pop     rdi
0x1800bde8d  pop     rsi
0x1800bde8e  pop     rbp
0x1800bde8f  retn
```
