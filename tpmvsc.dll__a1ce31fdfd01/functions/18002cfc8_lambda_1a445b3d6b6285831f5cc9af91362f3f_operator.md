# _lambda_1a445b3d6b6285831f5cc9af91362f3f_::operator()

- ea: `0x18002cfc8`
- end: `0x18002d17e`
- name: `_lambda_1a445b3d6b6285831f5cc9af91362f3f_::operator()`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002c290`

## callees

- `0x180006128`
- `0x18000653c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c198`
- `0x18000cae0`
- `0x180015544`
- `0x180016954`
- `0x18002cfc8`

## string_xrefs

- `0x18002d10f`: `Unable to create card`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_1a445b3d6b6285831f5cc9af91362f3f_::operator()(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int Card; // ebx
  __int64 v8[3]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v9[3]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v10[3]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v11[3]; // [rsp+98h] [rbp+1Fh] BYREF
  _QWORD v12[4]; // [rsp+B0h] [rbp+37h] BYREF

  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v12);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v11);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v10);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v9);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v8);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
    v12,
    ***(char ****)(a1 + 24),
    *(unsigned int *)(**(_QWORD **)(a1 + 24) + 12LL));
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
    v9,
    ***(char ****)(a1 + 48),
    *(unsigned int *)(**(_QWORD **)(a1 + 48) + 12LL));
  v2 = **(_QWORD **)(a1 + 32);
  if ( v2 )
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
      v11,
      *(char **)v2,
      *(unsigned int *)(v2 + 12));
  v3 = **(_QWORD **)(a1 + 40);
  if ( v3 )
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
      v10,
      *(char **)v3,
      *(unsigned int *)(v3 + 12));
  v4 = **(_QWORD **)(a1 + 56);
  if ( v4 )
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(v8, *(_QWORD *)v4, *(unsigned int *)(v4 + 12));
  Card = I_CreateCard(
           **(unsigned __int16 ***)a1,
           **(_BYTE **)(a1 + 8),
           **(_BYTE **)(a1 + 16),
           (__int64)v12,
           v11,
           v10,
           (__int64)v9,
           (__int64)v8,
           **(_DWORD **)(a1 + 64));
  if ( Card )
  {
    WppTraceIndent(v5, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
        (_DWORD)WPP_pszIndent,
        Card,
        (__int64)"Unable to create card");
    }
  }
  else
  {
    Card = 0;
  }
  std::vector<unsigned char>::_Tidy(v8);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v9);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v10);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v11);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v12);
  return Card;
}

```

## disassembly

```asm
0x18002cfc8  mov     [rsp-8+arg_0], rbx
0x18002cfcd  push    rbp
0x18002cfce  lea     rbp, [rsp-57h]
0x18002cfd3  sub     rsp, 0D0h
0x18002cfda  mov     rbx, rcx
0x18002cfdd  lea     rcx, [rbp+57h+var_20]
0x18002cfe1  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002cfe6  nop
0x18002cfe7  lea     rcx, [rbp+57h+var_38]
0x18002cfeb  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002cff0  nop
0x18002cff1  lea     rcx, [rbp+57h+var_50]
0x18002cff5  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002cffa  nop
0x18002cffb  lea     rcx, [rbp+57h+var_68]
0x18002cfff  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002d004  nop
0x18002d005  lea     rcx, [rbp+57h+var_80]
0x18002d009  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002d00e  nop
0x18002d00f  mov     rax, [rbx+18h]
0x18002d013  mov     rdx, [rax]
0x18002d016  mov     r8d, [rdx+0Ch]
0x18002d01a  mov     rdx, [rdx]
0x18002d01d  lea     rcx, [rbp+57h+var_20]
0x18002d021  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18002d026  mov     rax, [rbx+30h]
0x18002d02a  mov     rdx, [rax]
0x18002d02d  mov     r8d, [rdx+0Ch]
0x18002d031  mov     rdx, [rdx]
0x18002d034  lea     rcx, [rbp+57h+var_68]
0x18002d038  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18002d03d  mov     rax, [rbx+20h]
0x18002d041  mov     rdx, [rax]
0x18002d044  test    rdx, rdx
0x18002d047  jz      short loc_18002D059
0x18002d049  mov     r8d, [rdx+0Ch]
0x18002d04d  mov     rdx, [rdx]
0x18002d050  lea     rcx, [rbp+57h+var_38]
0x18002d054  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18002d059  mov     rax, [rbx+28h]
0x18002d05d  mov     rdx, [rax]
0x18002d060  test    rdx, rdx
0x18002d063  jz      short loc_18002D075
0x18002d065  mov     r8d, [rdx+0Ch]
0x18002d069  mov     rdx, [rdx]
0x18002d06c  lea     rcx, [rbp+57h+var_50]
0x18002d070  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18002d075  mov     rax, [rbx+38h]
0x18002d079  mov     rdx, [rax]
0x18002d07c  test    rdx, rdx
0x18002d07f  jz      short loc_18002D091
0x18002d081  mov     r8d, [rdx+0Ch]
0x18002d085  mov     rdx, [rdx]
0x18002d088  lea     rcx, [rbp+57h+var_80]
0x18002d08c  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18002d091  mov     rax, [rbx+40h]
0x18002d095  mov     r8, [rbx+10h]
0x18002d099  mov     rdx, [rbx+8]
0x18002d09d  mov     rcx, [rbx]
0x18002d0a0  mov     eax, [rax]
0x18002d0a2  mov     [rsp+0D0h+var_90], eax; int
0x18002d0a6  lea     rax, [rbp+57h+var_80]
0x18002d0aa  mov     [rsp+0D0h+var_98], rax; __int64
0x18002d0af  lea     rax, [rbp+57h+var_68]
0x18002d0b3  mov     [rsp+0D0h+var_A0], rax; __int64
0x18002d0b8  lea     rax, [rbp+57h+var_50]
0x18002d0bc  mov     [rsp+0D0h+var_A8], rax; __int64
0x18002d0c1  lea     rax, [rbp+57h+var_38]
0x18002d0c5  mov     [rsp+0D0h+var_B0], rax; __int64
0x18002d0ca  lea     r9, [rbp+57h+var_20]
0x18002d0ce  mov     r8b, [r8]
0x18002d0d1  mov     dl, [rdx]
0x18002d0d3  mov     rcx, [rcx]; unsigned __int16 *
0x18002d0d6  call    ?I_CreateCard@@YAKPEBGEEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@111AEBV?$vector@EV?$allocator@E@std@@@2@W4TPMVSC_ATTESTATION_TYPE@@@Z; I_CreateCard(ushort const *,uchar,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar> const &,TPMVSC_ATTESTATION_TYPE)
0x18002d0db  mov     ebx, eax
0x18002d0dd  test    eax, eax
0x18002d0df  jz      short loc_18002D138
0x18002d0e1  mov     edx, 2
0x18002d0e6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d0eb  lea     rax, WPP_GLOBAL_Control
0x18002d0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0f9  cmp     rcx, rax
0x18002d0fc  jz      short loc_18002D13A
0x18002d0fe  test    byte ptr [rcx+1Ch], 1
0x18002d102  jz      short loc_18002D13A
0x18002d104  cmp     byte ptr [rcx+19h], 2
0x18002d108  jb      short loc_18002D13A
0x18002d10a  mov     edx, 85h
0x18002d10f  lea     rax, aUnableToCreate_3; "Unable to create card"
0x18002d116  mov     [rsp+0D0h+var_A8], rax
0x18002d11b  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18002d11f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002d126  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18002d12d  mov     rcx, [rcx+10h]
0x18002d131  call    WPP_SF_sDs
0x18002d136  jmp     short loc_18002D13A
0x18002d138  xor     ebx, ebx
0x18002d13a  lea     rcx, [rbp+57h+var_80]
0x18002d13e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002d143  nop
0x18002d144  lea     rcx, [rbp+57h+var_68]
0x18002d148  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002d14d  nop
0x18002d14e  lea     rcx, [rbp+57h+var_50]
0x18002d152  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002d157  nop
0x18002d158  lea     rcx, [rbp+57h+var_38]
0x18002d15c  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002d161  nop
0x18002d162  lea     rcx, [rbp+57h+var_20]
0x18002d166  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002d16b  mov     eax, ebx
0x18002d16d  mov     rbx, [rsp+0D0h+arg_0]
0x18002d175  add     rsp, 0D0h
0x18002d17c  pop     rbp
0x18002d17d  retn
```
