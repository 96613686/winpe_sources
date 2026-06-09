# StripOutInheritedAcesForDACL(CNtSecurityDescriptor &)

- ea: `0x1800bf548`
- end: `0x1800bf781`
- name: `?StripOutInheritedAcesForDACL@@YAJAEAVCNtSecurityDescriptor@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct CNtSecurityDescriptor *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024428`
- `0x18007ebf4`

## callees

- `0x18000b140`
- `0x180060ba4`
- `0x18009a79c`
- `0x1800bf548`

## import_xrefs

- `wbemcomn!?DeleteAce@CNtAcl@@QEAAHH@Z` at `0x1800bf62d`
- `wbemcomn!?DeleteAce@CNtAcl@@QEAAHH@Z` at `0x1800bf62d`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x1800bf56c`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x1800bf56c`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800bf610`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800bf610`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800bf61d`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800bf61d`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800bf5de`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800bf5de`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800bf5f7`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800bf5f7`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bf6fa`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bf6fa`
- `wbemcomn!GetMemLogObject` at `0x1800bf578`
- `wbemcomn!GetMemLogObject` at `0x1800bf649`
- `wbemcomn!GetMemLogObject` at `0x1800bf6b5`
- `wbemcomn!GetMemLogObject` at `0x1800bf704`
- `wbemcomn!GetMemLogObject` at `0x1800bf578`
- `wbemcomn!GetMemLogObject` at `0x1800bf649`
- `wbemcomn!GetMemLogObject` at `0x1800bf6b5`
- `wbemcomn!GetMemLogObject` at `0x1800bf704`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf583`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf657`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf6c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf712`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf583`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf657`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf6c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf712`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StripOutInheritedAcesForDACL(struct CNtSecurityDescriptor *a1)
{
  int Dacl; // ebx
  CMemoryLog *v3; // rax
  int v5; // esi
  int i; // ebx
  CNtAce *Ace; // rax
  CNtAce *v8; // rdi
  CMemoryLog *v9; // rax
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v11; // rax
  __int64 v12; // rdx
  CMemoryLog *v13; // rax
  struct CNtAcl *v14; // [rsp+20h] [rbp-10h] BYREF
  CNtAcl *v15; // [rsp+28h] [rbp-8h] BYREF
  CNtAce *v16; // [rsp+58h] [rbp+28h] BYREF

  v14 = 0;
  Dacl = CNtSecurityDescriptor::GetDacl(a1, &v14);
  if ( Dacl >= 0 )
  {
    if ( v14 )
    {
      v15 = v14;
      v5 = 0;
      for ( i = CNtAcl::GetNumAces(v14) - 1; i >= 0; --i )
      {
        Ace = CNtAcl::GetAce(v14, i);
        v8 = Ace;
        if ( !Ace )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2147217407);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 22;
            goto LABEL_32;
          }
          goto LABEL_21;
        }
        v16 = Ace;
        if ( !CNtAce::GetStatus(Ace) && (CNtAce::GetFlags(v8) & 0x10) != 0 )
        {
          if ( !CNtAcl::DeleteAce(v14, i) )
          {
            v9 = GetMemLogObject();
            CMemoryLog::Write(v9, -2147217407);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                23,
                WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
                2147749889LL);
            }
            CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v16);
            goto LABEL_21;
          }
          v5 = 1;
        }
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v16);
      }
      if ( v5 && !CNtSecurityDescriptor::SetDacl(a1, v14) )
      {
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, -2147217407);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 24;
LABEL_32:
          WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749889LL);
        }
LABEL_21:
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v15);
        return 2147749889LL;
      }
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v15);
    }
    return 0;
  }
  else
  {
    v3 = GetMemLogObject();
    CMemoryLog::Write(v3, Dacl);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)Dacl);
    }
    return (unsigned int)Dacl;
  }
}

```

## disassembly

```asm
0x1800bf548  mov     [rsp-18h+arg_0], rbx
0x1800bf54d  mov     [rsp-18h+arg_10], rsi
0x1800bf552  push    rbp
0x1800bf553  push    rdi
0x1800bf554  push    r14
0x1800bf556  mov     rbp, rsp
0x1800bf559  sub     rsp, 30h
0x1800bf55d  mov     r14, rcx
0x1800bf560  mov     [rbp+var_10], 0
0x1800bf568  lea     rdx, [rbp+var_10]
0x1800bf56c  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z; CNtSecurityDescriptor::GetDacl(CNtAcl * *)
0x1800bf572  mov     ebx, eax
0x1800bf574  test    eax, eax
0x1800bf576  jns     short loc_1800BF5C9
0x1800bf578  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf57e  mov     edx, ebx
0x1800bf580  mov     rcx, rax
0x1800bf583  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf589  lea     rcx, WPP_GLOBAL_Control
0x1800bf590  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf597  cmp     r10, rcx
0x1800bf59a  jz      short loc_1800BF5C2
0x1800bf59c  test    byte ptr [r10+1Ch], 1
0x1800bf5a1  jz      short loc_1800BF5C2
0x1800bf5a3  cmp     byte ptr [r10+19h], 2
0x1800bf5a8  jb      short loc_1800BF5C2
0x1800bf5aa  mov     edx, 15h
0x1800bf5af  mov     r9d, ebx
0x1800bf5b2  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bf5b9  mov     rcx, [r10+10h]
0x1800bf5bd  call    WPP_SF_d
0x1800bf5c2  mov     eax, ebx
0x1800bf5c4  jmp     loc_1800BF76E
0x1800bf5c9  mov     rax, [rbp+var_10]
0x1800bf5cd  test    rax, rax
0x1800bf5d0  jz      loc_1800BF76C
0x1800bf5d6  mov     [rbp+var_8], rax
0x1800bf5da  mov     rcx, [rbp+var_10]
0x1800bf5de  call    cs:__imp_?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x1800bf5e4  xor     esi, esi
0x1800bf5e6  lea     ebx, [rax-1]
0x1800bf5e9  test    ebx, ebx
0x1800bf5eb  js      loc_1800BF6EF
0x1800bf5f1  mov     edx, ebx
0x1800bf5f3  mov     rcx, [rbp+var_10]
0x1800bf5f7  call    cs:__imp_?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x1800bf5fd  mov     rdi, rax
0x1800bf600  test    rax, rax
0x1800bf603  jz      loc_1800BF6B5
0x1800bf609  mov     [rbp+arg_8], rax
0x1800bf60d  mov     rcx, rax
0x1800bf610  call    cs:__imp_?GetStatus@CNtAce@@UEAAKXZ; CNtAce::GetStatus(void)
0x1800bf616  test    eax, eax
0x1800bf618  jnz     short loc_1800BF63C
0x1800bf61a  mov     rcx, rdi
0x1800bf61d  call    cs:__imp_?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x1800bf623  test    al, 10h
0x1800bf625  jz      short loc_1800BF63C
0x1800bf627  mov     edx, ebx
0x1800bf629  mov     rcx, [rbp+var_10]
0x1800bf62d  call    cs:__imp_?DeleteAce@CNtAcl@@QEAAHH@Z; CNtAcl::DeleteAce(int)
0x1800bf633  test    eax, eax
0x1800bf635  jz      short loc_1800BF649
0x1800bf637  mov     esi, 1
0x1800bf63c  lea     rcx, [rbp+arg_8]
0x1800bf640  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bf645  dec     ebx
0x1800bf647  jmp     short loc_1800BF5E9
0x1800bf649  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf64f  mov     edx, 80041001h
0x1800bf654  mov     rcx, rax
0x1800bf657  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf65d  lea     rcx, WPP_GLOBAL_Control
0x1800bf664  mov     rax, cs:WPP_GLOBAL_Control
0x1800bf66b  cmp     rax, rcx
0x1800bf66e  jz      short loc_1800BF698
0x1800bf670  test    byte ptr [rax+1Ch], 1
0x1800bf674  jz      short loc_1800BF698
0x1800bf676  cmp     byte ptr [rax+19h], 2
0x1800bf67a  jb      short loc_1800BF698
0x1800bf67c  mov     edx, 17h
0x1800bf681  mov     r9d, 80041001h
0x1800bf687  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bf68e  mov     rcx, [rax+10h]
0x1800bf692  call    WPP_SF_d
0x1800bf697  nop
0x1800bf698  lea     rcx, [rbp+arg_8]
0x1800bf69c  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bf6a1  nop
0x1800bf6a2  lea     rcx, [rbp+var_8]
0x1800bf6a6  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bf6ab  mov     eax, 80041001h
0x1800bf6b0  jmp     loc_1800BF76E
0x1800bf6b5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf6bb  mov     edx, 80041001h
0x1800bf6c0  mov     rcx, rax
0x1800bf6c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf6c9  lea     rcx, WPP_GLOBAL_Control
0x1800bf6d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800bf6d7  cmp     rax, rcx
0x1800bf6da  jz      short loc_1800BF6A2
0x1800bf6dc  test    byte ptr [rax+1Ch], 1
0x1800bf6e0  jz      short loc_1800BF6A2
0x1800bf6e2  cmp     byte ptr [rax+19h], 2
0x1800bf6e6  jb      short loc_1800BF6A2
0x1800bf6e8  mov     edx, 16h
0x1800bf6ed  jmp     short loc_1800BF748
0x1800bf6ef  test    esi, esi
0x1800bf6f1  jz      short loc_1800BF763
0x1800bf6f3  mov     rdx, [rbp+var_10]
0x1800bf6f7  mov     rcx, r14
0x1800bf6fa  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x1800bf700  test    eax, eax
0x1800bf702  jnz     short loc_1800BF763
0x1800bf704  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf70a  mov     edx, 80041001h
0x1800bf70f  mov     rcx, rax
0x1800bf712  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf718  lea     rcx, WPP_GLOBAL_Control
0x1800bf71f  mov     rax, cs:WPP_GLOBAL_Control
0x1800bf726  cmp     rax, rcx
0x1800bf729  jz      loc_1800BF6A2
0x1800bf72f  test    byte ptr [rax+1Ch], 1
0x1800bf733  jz      loc_1800BF6A2
0x1800bf739  cmp     byte ptr [rax+19h], 2
0x1800bf73d  jb      loc_1800BF6A2
0x1800bf743  mov     edx, 18h
0x1800bf748  mov     r9d, 80041001h
0x1800bf74e  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bf755  mov     rcx, [rax+10h]
0x1800bf759  call    WPP_SF_d
0x1800bf75e  jmp     loc_1800BF6A2
0x1800bf763  lea     rcx, [rbp+var_8]
0x1800bf767  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bf76c  xor     eax, eax
0x1800bf76e  mov     rbx, [rsp+30h+arg_0]
0x1800bf773  mov     rsi, [rsp+30h+arg_10]
0x1800bf778  add     rsp, 30h
0x1800bf77c  pop     r14
0x1800bf77e  pop     rdi
0x1800bf77f  pop     rbp
0x1800bf780  retn
```
