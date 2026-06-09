# StripOutInheritedAcesForSACL(CNtSecurityDescriptor &)

- ea: `0x1800bf788`
- end: `0x1800bf9bb`
- name: `?StripOutInheritedAcesForSACL@@YAJAEAVCNtSecurityDescriptor@@@Z`
- size: `563`
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
- `0x1800bf788`

## import_xrefs

- `wbemcomn!?DeleteAce@CNtAcl@@QEAAHH@Z` at `0x1800bf87d`
- `wbemcomn!?DeleteAce@CNtAcl@@QEAAHH@Z` at `0x1800bf87d`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x1800bf7ac`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x1800bf7ac`
- `wbemcomn!?SetSacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bf93f`
- `wbemcomn!?SetSacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800bf93f`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800bf860`
- `wbemcomn!?GetStatus@CNtAce@@UEAAKXZ` at `0x1800bf860`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800bf86d`
- `wbemcomn!?GetFlags@CNtAce@@UEAAHXZ` at `0x1800bf86d`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800bf82e`
- `wbemcomn!?GetNumAces@CNtAcl@@QEAAHXZ` at `0x1800bf82e`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800bf847`
- `wbemcomn!?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z` at `0x1800bf847`
- `wbemcomn!GetMemLogObject` at `0x1800bf7b8`
- `wbemcomn!GetMemLogObject` at `0x1800bf899`
- `wbemcomn!GetMemLogObject` at `0x1800bf8f8`
- `wbemcomn!GetMemLogObject` at `0x1800bf949`
- `wbemcomn!GetMemLogObject` at `0x1800bf7b8`
- `wbemcomn!GetMemLogObject` at `0x1800bf899`
- `wbemcomn!GetMemLogObject` at `0x1800bf8f8`
- `wbemcomn!GetMemLogObject` at `0x1800bf949`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf7c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf8a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf908`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf959`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf7c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf8a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf908`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800bf959`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StripOutInheritedAcesForSACL(struct CNtSecurityDescriptor *a1)
{
  int Sacl; // ebx
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
  Sacl = CNtSecurityDescriptor::GetSacl(a1, &v14);
  if ( Sacl >= 0 )
  {
    if ( !v14 )
      return 1;
    v15 = v14;
    v5 = 0;
    for ( i = CNtAcl::GetNumAces(v14) - 1; i >= 0; --i )
    {
      Ace = CNtAcl::GetAce(v14, i);
      v8 = Ace;
      if ( !Ace )
      {
        MemLogObject = GetMemLogObject();
        Sacl = -2147217407;
        CMemoryLog::Write(MemLogObject, -2147217407);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_33;
        }
        v12 = 26;
LABEL_31:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, 2147749889LL);
        goto LABEL_33;
      }
      v16 = Ace;
      if ( !CNtAce::GetStatus(Ace) && (CNtAce::GetFlags(v8) & 0x10) != 0 )
      {
        if ( !CNtAcl::DeleteAce(v14, i) )
        {
          v9 = GetMemLogObject();
          Sacl = -2147217407;
          CMemoryLog::Write(v9, -2147217407);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
              2147749889LL);
          }
          CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v16);
          goto LABEL_33;
        }
        v5 = 1;
      }
      CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v16);
    }
    if ( !v5 || CNtSecurityDescriptor::SetSacl(a1, v14) )
    {
      Sacl = 0;
      goto LABEL_33;
    }
    v13 = GetMemLogObject();
    Sacl = -2147217407;
    CMemoryLog::Write(v13, -2147217407);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 28;
      goto LABEL_31;
    }
LABEL_33:
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v15);
  }
  else
  {
    v3 = GetMemLogObject();
    CMemoryLog::Write(v3, Sacl);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)Sacl);
    }
  }
  return (unsigned int)Sacl;
}

```

## disassembly

```asm
0x1800bf788  mov     [rsp-18h+arg_0], rbx
0x1800bf78d  mov     [rsp-18h+arg_10], rsi
0x1800bf792  push    rbp
0x1800bf793  push    rdi
0x1800bf794  push    r14
0x1800bf796  mov     rbp, rsp
0x1800bf799  sub     rsp, 30h
0x1800bf79d  mov     r14, rcx
0x1800bf7a0  mov     [rbp+var_10], 0
0x1800bf7a8  lea     rdx, [rbp+var_10]
0x1800bf7ac  call    cs:__imp_?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z; CNtSecurityDescriptor::GetSacl(CNtAcl * *)
0x1800bf7b2  mov     ebx, eax
0x1800bf7b4  test    eax, eax
0x1800bf7b6  jns     short loc_1800BF813
0x1800bf7b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf7be  mov     edx, ebx
0x1800bf7c0  mov     rcx, rax
0x1800bf7c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf7c9  lea     rcx, WPP_GLOBAL_Control
0x1800bf7d0  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf7d7  cmp     r10, rcx
0x1800bf7da  jz      loc_1800BF9A6
0x1800bf7e0  test    byte ptr [r10+1Ch], 1
0x1800bf7e5  jz      loc_1800BF9A6
0x1800bf7eb  cmp     byte ptr [r10+19h], 2
0x1800bf7f0  jb      loc_1800BF9A6
0x1800bf7f6  mov     edx, 19h
0x1800bf7fb  mov     r9d, ebx
0x1800bf7fe  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bf805  mov     rcx, [r10+10h]
0x1800bf809  call    WPP_SF_d
0x1800bf80e  jmp     loc_1800BF9A6
0x1800bf813  mov     rax, [rbp+var_10]
0x1800bf817  test    rax, rax
0x1800bf81a  jnz     short loc_1800BF826
0x1800bf81c  mov     eax, 1
0x1800bf821  jmp     loc_1800BF9A8
0x1800bf826  mov     [rbp+var_8], rax
0x1800bf82a  mov     rcx, [rbp+var_10]
0x1800bf82e  call    cs:__imp_?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x1800bf834  xor     esi, esi
0x1800bf836  lea     ebx, [rax-1]
0x1800bf839  test    ebx, ebx
0x1800bf83b  js      loc_1800BF934
0x1800bf841  mov     edx, ebx
0x1800bf843  mov     rcx, [rbp+var_10]
0x1800bf847  call    cs:__imp_?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x1800bf84d  mov     rdi, rax
0x1800bf850  test    rax, rax
0x1800bf853  jz      loc_1800BF8F8
0x1800bf859  mov     [rbp+arg_8], rax
0x1800bf85d  mov     rcx, rax
0x1800bf860  call    cs:__imp_?GetStatus@CNtAce@@UEAAKXZ; CNtAce::GetStatus(void)
0x1800bf866  test    eax, eax
0x1800bf868  jnz     short loc_1800BF88C
0x1800bf86a  mov     rcx, rdi
0x1800bf86d  call    cs:__imp_?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x1800bf873  test    al, 10h
0x1800bf875  jz      short loc_1800BF88C
0x1800bf877  mov     edx, ebx
0x1800bf879  mov     rcx, [rbp+var_10]
0x1800bf87d  call    cs:__imp_?DeleteAce@CNtAcl@@QEAAHH@Z; CNtAcl::DeleteAce(int)
0x1800bf883  test    eax, eax
0x1800bf885  jz      short loc_1800BF899
0x1800bf887  mov     esi, 1
0x1800bf88c  lea     rcx, [rbp+arg_8]
0x1800bf890  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bf895  dec     ebx
0x1800bf897  jmp     short loc_1800BF839
0x1800bf899  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf89f  mov     ebx, 80041001h
0x1800bf8a4  mov     edx, ebx
0x1800bf8a6  mov     rcx, rax
0x1800bf8a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf8af  lea     rcx, WPP_GLOBAL_Control
0x1800bf8b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800bf8bd  cmp     rax, rcx
0x1800bf8c0  jz      short loc_1800BF8EA
0x1800bf8c2  test    byte ptr [rax+1Ch], 1
0x1800bf8c6  jz      short loc_1800BF8EA
0x1800bf8c8  cmp     byte ptr [rax+19h], 2
0x1800bf8cc  jb      short loc_1800BF8EA
0x1800bf8ce  mov     edx, 1Bh
0x1800bf8d3  mov     r9d, 80041001h
0x1800bf8d9  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bf8e0  mov     rcx, [rax+10h]
0x1800bf8e4  call    WPP_SF_d
0x1800bf8e9  nop
0x1800bf8ea  lea     rcx, [rbp+arg_8]
0x1800bf8ee  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x1800bf8f3  jmp     loc_1800BF99D
0x1800bf8f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf8fe  mov     ebx, 80041001h
0x1800bf903  mov     edx, ebx
0x1800bf905  mov     rcx, rax
0x1800bf908  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf90e  lea     rcx, WPP_GLOBAL_Control
0x1800bf915  mov     rax, cs:WPP_GLOBAL_Control
0x1800bf91c  cmp     rax, rcx
0x1800bf91f  jz      short loc_1800BF99D
0x1800bf921  test    byte ptr [rax+1Ch], 1
0x1800bf925  jz      short loc_1800BF99D
0x1800bf927  cmp     byte ptr [rax+19h], 2
0x1800bf92b  jb      short loc_1800BF99D
0x1800bf92d  mov     edx, 1Ah
0x1800bf932  jmp     short loc_1800BF983
0x1800bf934  test    esi, esi
0x1800bf936  jz      short loc_1800BF99B
0x1800bf938  mov     rdx, [rbp+var_10]
0x1800bf93c  mov     rcx, r14
0x1800bf93f  call    cs:__imp_?SetSacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetSacl(CNtAcl *)
0x1800bf945  test    eax, eax
0x1800bf947  jnz     short loc_1800BF99B
0x1800bf949  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800bf94f  mov     ebx, 80041001h
0x1800bf954  mov     edx, ebx
0x1800bf956  mov     rcx, rax
0x1800bf959  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800bf95f  lea     rcx, WPP_GLOBAL_Control
0x1800bf966  mov     rax, cs:WPP_GLOBAL_Control
0x1800bf96d  cmp     rax, rcx
0x1800bf970  jz      short loc_1800BF99D
0x1800bf972  test    byte ptr [rax+1Ch], 1
0x1800bf976  jz      short loc_1800BF99D
0x1800bf978  cmp     byte ptr [rax+19h], 2
0x1800bf97c  jb      short loc_1800BF99D
0x1800bf97e  mov     edx, 1Ch
0x1800bf983  mov     r9d, 80041001h
0x1800bf989  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800bf990  mov     rcx, [rax+10h]
0x1800bf994  call    WPP_SF_d
0x1800bf999  jmp     short loc_1800BF99D
0x1800bf99b  xor     ebx, ebx
0x1800bf99d  lea     rcx, [rbp+var_8]
0x1800bf9a1  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x1800bf9a6  mov     eax, ebx
0x1800bf9a8  mov     rbx, [rsp+30h+arg_0]
0x1800bf9ad  mov     rsi, [rsp+30h+arg_10]
0x1800bf9b2  add     rsp, 30h
0x1800bf9b6  pop     r14
0x1800bf9b8  pop     rdi
0x1800bf9b9  pop     rbp
0x1800bf9ba  retn
```
