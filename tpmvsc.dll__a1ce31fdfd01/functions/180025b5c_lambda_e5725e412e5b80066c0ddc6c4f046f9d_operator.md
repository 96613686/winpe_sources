# _lambda_e5725e412e5b80066c0ddc6c4f046f9d_::operator()

- ea: `0x180025b5c`
- end: `0x180025f0a`
- name: `_lambda_e5725e412e5b80066c0ddc6c4f046f9d_::operator()`
- size: `942`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180025758`

## callees

- `0x180006128`
- `0x180006204`
- `0x18000653c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c198`
- `0x180014be4`
- `0x180015544`
- `0x180016954`
- `0x180025b5c`
- `0x1800261b4`

## string_xrefs

- `0x180025c64`: `Failed to check access`
- `0x180025ddd`: `Unable to create card`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_e5725e412e5b80066c0ddc6c4f046f9d_::operator()(__int64 a1)
{
  __int64 v1; // rdi
  bool v2; // zf
  __int64 v3; // rcx
  unsigned int Card; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  char *v7; // r15
  size_t v8; // rsi
  char *v9; // rbx
  char *v10; // rcx
  __int64 v11; // rcx
  signed __int64 v12; // r14
  void *v14; // [rsp+50h] [rbp-59h] BYREF
  char *v15; // [rsp+58h] [rbp-51h]
  __int64 v16; // [rsp+60h] [rbp-49h]
  __int64 v17[3]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v18[3]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v19[3]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v20[80]; // [rsp+B0h] [rbp+7h] BYREF

  v1 = a1;
  if ( !**(_QWORD **)(a1 + 8)
    || !**(_QWORD **)(a1 + 32)
    || !**(_DWORD **)(a1 + 40)
    || ((a1 = **(unsigned int **)(a1 + 56), !**(_QWORD **)(v1 + 48)) ? (v2 = (_DWORD)a1 == 0) : (v2 = (_DWORD)a1 == 3),
        !v2
     || **(_QWORD **)(v1 + 64) && !**(_DWORD **)(v1 + 72)
     || !**(_QWORD **)(v1 + 80)
     || **(_QWORD **)(v1 + 96) && !**(_DWORD **)(v1 + 104)
     || (LOBYTE(a1) = **(_BYTE **)(v1 + 16) + 0x80, (unsigned __int8)a1 > 0x20u)
     || (LOBYTE(a1) = (**(_BYTE **)(v1 + 24) & 0xF) - 2, (unsigned __int8)a1 > 3u)) )
  {
    WppTraceIndent(a1, 2);
    Card = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
        (_DWORD)WPP_pszIndent,
        87,
        (__int64)"Invalid parameter");
    }
    return Card;
  }
  Card = TpmVCardManagerImpl::CheckAccess((TpmVCardManagerImpl *)a1);
  if ( Card )
  {
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
        (_DWORD)WPP_pszIndent,
        Card,
        (__int64)"Failed to check access");
    }
    return Card;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v20);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v19);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v18);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v17);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v14);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
    v20,
    **(_QWORD **)(v1 + 32),
    **(unsigned int **)(v1 + 40));
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
    v17,
    **(_QWORD **)(v1 + 80),
    **(unsigned int **)(v1 + 88));
  v5 = **(_QWORD **)(v1 + 48);
  if ( v5 )
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
      v19,
      v5,
      **(unsigned int **)(v1 + 56));
  v6 = **(_QWORD **)(v1 + 64);
  if ( v6 )
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
      v18,
      v6,
      **(unsigned int **)(v1 + 72));
  v7 = **(char ***)(v1 + 96);
  if ( v7 )
  {
    v8 = **(unsigned int **)(v1 + 104);
    v9 = (char *)v14;
    if ( v8 <= v16 - (__int64)v14 )
    {
      v12 = v15 - (_BYTE *)v14;
      if ( v8 > v15 - (_BYTE *)v14 )
      {
        std::_Copy_memmove_n<unsigned char const *,unsigned char *>(v7, v15 - (_BYTE *)v14, v14);
        v9 = v15;
        v8 -= v12;
        v10 = &v7[v12];
        goto LABEL_28;
      }
    }
    else
    {
      std::vector<unsigned char>::_Clear_and_reserve_geometric(&v14, (unsigned int)v8);
      v9 = (char *)v14;
    }
    v10 = v7;
LABEL_28:
    std::_Copy_memmove_n<unsigned char const *,unsigned char *>(v10, v8, v9);
    v15 = &v9[v8];
  }
  Card = I_CreateCard(
           **(unsigned __int16 ***)(v1 + 8),
           **(_BYTE **)(v1 + 16),
           **(_BYTE **)(v1 + 24),
           (__int64)v20,
           v19,
           v18,
           (__int64)v17,
           (__int64)&v14,
           **(_DWORD **)(v1 + 112));
  if ( !Card )
  {
    std::vector<unsigned char>::_Tidy(&v14);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v17);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v18);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v19);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v20);
    return 0;
  }
  WppTraceIndent(v11, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_f3132f67e798390788997da23861f0b6_Traceguids,
      (_DWORD)WPP_pszIndent,
      Card,
      (__int64)"Unable to create card");
  }
  std::vector<unsigned char>::_Tidy(&v14);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v17);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v18);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v19);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v20);
  return Card;
}

```

## disassembly

```asm
0x180025b5c  push    rbp
0x180025b5e  push    rbx
0x180025b5f  push    rsi
0x180025b60  push    rdi
0x180025b61  push    r14
0x180025b63  push    r15
0x180025b65  lea     rbp, [rsp-2Fh]
0x180025b6a  sub     rsp, 0D8h
0x180025b71  mov     rdi, rcx
0x180025b74  mov     rax, [rcx+8]
0x180025b78  cmp     qword ptr [rax], 0
0x180025b7c  jz      loc_180025E9E
0x180025b82  mov     rax, [rcx+20h]
0x180025b86  cmp     qword ptr [rax], 0
0x180025b8a  jz      loc_180025E9E
0x180025b90  mov     rax, [rcx+28h]
0x180025b94  cmp     dword ptr [rax], 0
0x180025b97  jz      loc_180025E9E
0x180025b9d  mov     rax, [rcx+38h]
0x180025ba1  mov     ecx, [rax]
0x180025ba3  mov     rax, [rdi+30h]
0x180025ba7  cmp     qword ptr [rax], 0
0x180025bab  jz      short loc_180025BB2
0x180025bad  cmp     ecx, 3
0x180025bb0  jmp     short loc_180025BB4
0x180025bb2  test    ecx, ecx
0x180025bb4  jnz     loc_180025E9E
0x180025bba  mov     rax, [rdi+40h]
0x180025bbe  cmp     qword ptr [rax], 0
0x180025bc2  jz      short loc_180025BD1
0x180025bc4  mov     rax, [rdi+48h]
0x180025bc8  cmp     dword ptr [rax], 0
0x180025bcb  jz      loc_180025E9E
0x180025bd1  mov     rax, [rdi+50h]
0x180025bd5  cmp     qword ptr [rax], 0
0x180025bd9  jz      loc_180025E9E
0x180025bdf  mov     rax, [rdi+60h]
0x180025be3  cmp     qword ptr [rax], 0
0x180025be7  jz      short loc_180025BF6
0x180025be9  mov     rax, [rdi+68h]
0x180025bed  cmp     dword ptr [rax], 0
0x180025bf0  jz      loc_180025E9E
0x180025bf6  mov     rax, [rdi+10h]
0x180025bfa  mov     cl, [rax]
0x180025bfc  sub     cl, 80h
0x180025bff  cmp     cl, 20h ; ' '
0x180025c02  ja      loc_180025E9E
0x180025c08  mov     rax, [rdi+18h]
0x180025c0c  mov     cl, [rax]
0x180025c0e  and     cl, 0Fh
0x180025c11  sub     cl, 2; this
0x180025c14  cmp     cl, 3
0x180025c17  ja      loc_180025E9E
0x180025c1d  call    ?CheckAccess@TpmVCardManagerImpl@@AEAAKXZ; TpmVCardManagerImpl::CheckAccess(void)
0x180025c22  mov     ebx, eax
0x180025c24  test    eax, eax
0x180025c26  jz      short loc_180025C75
0x180025c28  mov     edx, 2
0x180025c2d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025c32  lea     rcx, WPP_GLOBAL_Control
0x180025c39  mov     r10, cs:WPP_GLOBAL_Control
0x180025c40  cmp     r10, rcx
0x180025c43  jz      loc_180025EF8
0x180025c49  test    byte ptr [r10+1Ch], 1
0x180025c4e  jz      loc_180025EF8
0x180025c54  cmp     byte ptr [r10+19h], 2
0x180025c59  jb      loc_180025EF8
0x180025c5f  mov     edx, 14h
0x180025c64  lea     rax, aFailedToCheckA; "Failed to check access"
0x180025c6b  mov     [rsp+100h+var_D8], rax
0x180025c70  jmp     loc_180025EDD
0x180025c75  lea     rcx, [rbp+57h+var_50]
0x180025c79  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180025c7e  nop
0x180025c7f  lea     rcx, [rbp+57h+var_68]
0x180025c83  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180025c88  nop
0x180025c89  lea     rcx, [rbp+57h+var_80]
0x180025c8d  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180025c92  nop
0x180025c93  lea     rcx, [rbp+57h+var_98]
0x180025c97  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180025c9c  nop
0x180025c9d  lea     rcx, [rbp+57h+var_B0]
0x180025ca1  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180025ca6  nop
0x180025ca7  mov     rax, [rdi+28h]
0x180025cab  mov     r8d, [rax]
0x180025cae  mov     rdx, [rdi+20h]
0x180025cb2  mov     rdx, [rdx]
0x180025cb5  lea     rcx, [rbp+57h+var_50]
0x180025cb9  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x180025cbe  mov     rax, [rdi+58h]
0x180025cc2  mov     r8d, [rax]
0x180025cc5  mov     rdx, [rdi+50h]
0x180025cc9  mov     rdx, [rdx]
0x180025ccc  lea     rcx, [rbp+57h+var_98]
0x180025cd0  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x180025cd5  mov     rax, [rdi+30h]
0x180025cd9  mov     rdx, [rax]
0x180025cdc  test    rdx, rdx
0x180025cdf  jz      short loc_180025CF1
0x180025ce1  mov     rax, [rdi+38h]
0x180025ce5  mov     r8d, [rax]
0x180025ce8  lea     rcx, [rbp+57h+var_68]
0x180025cec  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x180025cf1  mov     rax, [rdi+40h]
0x180025cf5  mov     rdx, [rax]
0x180025cf8  test    rdx, rdx
0x180025cfb  jz      short loc_180025D0D
0x180025cfd  mov     rax, [rdi+48h]
0x180025d01  mov     r8d, [rax]
0x180025d04  lea     rcx, [rbp+57h+var_80]
0x180025d08  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x180025d0d  mov     rax, [rdi+60h]
0x180025d11  mov     r15, [rax]
0x180025d14  test    r15, r15
0x180025d17  jz      short loc_180025D58
0x180025d19  mov     rax, [rdi+68h]
0x180025d1d  mov     esi, [rax]
0x180025d1f  mov     rbx, [rbp+57h+var_B0]
0x180025d23  mov     rax, [rbp+57h+var_A0]
0x180025d27  sub     rax, rbx
0x180025d2a  cmp     rsi, rax
0x180025d2d  jbe     loc_180025E3B
0x180025d33  mov     edx, esi
0x180025d35  lea     rcx, [rbp+57h+var_B0]
0x180025d39  call    ?_Clear_and_reserve_geometric@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Clear_and_reserve_geometric(unsigned __int64)
0x180025d3e  mov     rbx, [rbp+57h+var_B0]
0x180025d42  mov     rcx, r15; Src
0x180025d45  mov     r8, rbx; void *
0x180025d48  mov     rdx, rsi; Size
0x180025d4b  call    ??$_Copy_memmove_n@PEBEPEAE@std@@YAPEAEPEBE_KPEAE@Z; std::_Copy_memmove_n<uchar const *,uchar *>(uchar const *,unsigned __int64,uchar *)
0x180025d50  lea     rax, [rsi+rbx]
0x180025d54  mov     [rbp+57h+var_A8], rax
0x180025d58  mov     rax, [rdi+70h]
0x180025d5c  mov     r8, [rdi+18h]
0x180025d60  mov     rdx, [rdi+10h]
0x180025d64  mov     rcx, [rdi+8]
0x180025d68  mov     eax, [rax]
0x180025d6a  mov     [rsp+100h+var_C0], eax; int
0x180025d6e  lea     rax, [rbp+57h+var_B0]
0x180025d72  mov     [rsp+100h+var_C8], rax; __int64
0x180025d77  lea     rax, [rbp+57h+var_98]
0x180025d7b  mov     [rsp+100h+var_D0], rax; __int64
0x180025d80  lea     rax, [rbp+57h+var_80]
0x180025d84  mov     [rsp+100h+var_D8], rax; __int64
0x180025d89  lea     rax, [rbp+57h+var_68]
0x180025d8d  mov     [rsp+100h+var_E0], rax; __int64
0x180025d92  lea     r9, [rbp+57h+var_50]
0x180025d96  mov     r8b, [r8]
0x180025d99  mov     dl, [rdx]
0x180025d9b  mov     rcx, [rcx]; unsigned __int16 *
0x180025d9e  call    ?I_CreateCard@@YAKPEBGEEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@111AEBV?$vector@EV?$allocator@E@std@@@2@W4TPMVSC_ATTESTATION_TYPE@@@Z; I_CreateCard(ushort const *,uchar,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar> const &,TPMVSC_ATTESTATION_TYPE)
0x180025da3  mov     ebx, eax
0x180025da5  test    eax, eax
0x180025da7  jz      loc_180025E69
0x180025dad  mov     edx, 2
0x180025db2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025db7  lea     rcx, WPP_GLOBAL_Control
0x180025dbe  mov     r10, cs:WPP_GLOBAL_Control
0x180025dc5  cmp     r10, rcx
0x180025dc8  jz      short loc_180025E05
0x180025dca  test    byte ptr [r10+1Ch], 1
0x180025dcf  jz      short loc_180025E05
0x180025dd1  cmp     byte ptr [r10+19h], 2
0x180025dd6  jb      short loc_180025E05
0x180025dd8  mov     edx, 15h
0x180025ddd  lea     rax, aUnableToCreate_3; "Unable to create card"
0x180025de4  mov     [rsp+100h+var_D8], rax
0x180025de9  mov     dword ptr [rsp+100h+var_E0], ebx
0x180025ded  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025df4  lea     r8, WPP_f3132f67e798390788997da23861f0b6_Traceguids
0x180025dfb  mov     rcx, [r10+10h]
0x180025dff  call    WPP_SF_sDs
0x180025e04  nop
0x180025e05  lea     rcx, [rbp+57h+var_B0]
0x180025e09  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180025e0e  nop
0x180025e0f  lea     rcx, [rbp+57h+var_98]
0x180025e13  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e18  nop
0x180025e19  lea     rcx, [rbp+57h+var_80]
0x180025e1d  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e22  nop
0x180025e23  lea     rcx, [rbp+57h+var_68]
0x180025e27  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e2c  nop
0x180025e2d  lea     rcx, [rbp+57h+var_50]
0x180025e31  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e36  jmp     loc_180025EF8
0x180025e3b  mov     r14, [rbp+57h+var_A8]
0x180025e3f  sub     r14, rbx
0x180025e42  cmp     rsi, r14
0x180025e45  jbe     loc_180025D42
0x180025e4b  mov     r8, rbx; void *
0x180025e4e  mov     rdx, r14; Size
0x180025e51  mov     rcx, r15; Src
0x180025e54  call    ??$_Copy_memmove_n@PEBEPEAE@std@@YAPEAEPEBE_KPEAE@Z; std::_Copy_memmove_n<uchar const *,uchar *>(uchar const *,unsigned __int64,uchar *)
0x180025e59  mov     rbx, [rbp+57h+var_A8]
0x180025e5d  sub     rsi, r14
0x180025e60  lea     rcx, [r14+r15]
0x180025e64  jmp     loc_180025D45
0x180025e69  lea     rcx, [rbp+57h+var_B0]
0x180025e6d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180025e72  nop
0x180025e73  lea     rcx, [rbp+57h+var_98]
0x180025e77  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e7c  nop
0x180025e7d  lea     rcx, [rbp+57h+var_80]
0x180025e81  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e86  nop
0x180025e87  lea     rcx, [rbp+57h+var_68]
0x180025e8b  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e90  nop
0x180025e91  lea     rcx, [rbp+57h+var_50]
0x180025e95  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180025e9a  xor     eax, eax
0x180025e9c  jmp     short loc_180025EFA
0x180025e9e  mov     edx, 2
0x180025ea3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025ea8  lea     rcx, WPP_GLOBAL_Control
0x180025eaf  mov     ebx, 57h ; 'W'
0x180025eb4  mov     r10, cs:WPP_GLOBAL_Control
0x180025ebb  cmp     r10, rcx
0x180025ebe  jz      short loc_180025EF8
0x180025ec0  test    byte ptr [r10+1Ch], 1
0x180025ec5  jz      short loc_180025EF8
0x180025ec7  cmp     byte ptr [r10+19h], 2
0x180025ecc  jb      short loc_180025EF8
0x180025ece  lea     edx, [rbx-44h]
0x180025ed1  lea     rcx, aInvalidParamet; "Invalid parameter"
0x180025ed8  mov     [rsp+100h+var_D8], rcx
0x180025edd  mov     dword ptr [rsp+100h+var_E0], ebx
0x180025ee1  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025ee8  lea     r8, WPP_f3132f67e798390788997da23861f0b6_Traceguids
0x180025eef  mov     rcx, [r10+10h]
0x180025ef3  call    WPP_SF_sDs
0x180025ef8  mov     eax, ebx
0x180025efa  add     rsp, 0D8h
0x180025f01  pop     r15
0x180025f03  pop     r14
0x180025f05  pop     rdi
0x180025f06  pop     rsi
0x180025f07  pop     rbx
0x180025f08  pop     rbp
0x180025f09  retn
```
