# DataStoreReader::GetHistoryValueFromDocument(IXMLDOMDocument2 *,ulong &)

- ea: `0x18000a3cc`
- end: `0x18000a748`
- name: `?GetHistoryValueFromDocument@DataStoreReader@@KAJPEAUIXMLDOMDocument2@@AEAK@Z`
- size: `892`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180004e00`

## callees

- `0x180009d50`
- `0x18000a380`
- `0x18000a3cc`
- `0x180013220`
- `0x180013290`
- `0x180013fa3`
- `0x180013fb6`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000a690`
- `msvcrt!iswdigit` at `0x18000a6b6`
- `msvcrt!iswdigit` at `0x18000a690`
- `msvcrt!iswdigit` at `0x18000a6b6`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000a4b5`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000a5e7`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000a4b5`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000a5e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a70d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a716`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a70d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a716`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6ed`

## string_xrefs

- `0x18000a430`: `/WinSAT/SystemConfig/HistoryVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DataStoreReader::GetHistoryValueFromDocument(struct IXMLDOMDocument2 *a1, unsigned int *a2)
{
  int v4; // r14d
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rcx
  const wchar_t *i; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  void *v12; // rax
  __int64 v13; // rdx
  int NodeValue; // r12d
  BSTR v15; // rdi
  __int64 *v16; // rax
  __int64 *v17; // rbx
  BSTR j; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  void *v21; // rax
  __int64 v22; // r8
  BSTR v23; // rdx
  __int64 v24; // rdx
  unsigned int v25; // r15d
  __int64 v26; // rsi
  wint_t *v27; // rdi
  bool v28; // zf
  void *v29; // rcx
  __int64 *v30; // rbx
  void *v31; // rcx
  int v33; // [rsp+20h] [rbp-40h]
  _QWORD pExceptionObject[4]; // [rsp+40h] [rbp-20h] BYREF
  const char *v35; // [rsp+A8h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp+50h] BYREF
  __int64 *v37; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  *a2 = 0;
  v5 = (__int64 *)operator new(0x28u);
  v6 = v5;
  if ( !v5 )
    std::_Xbad_alloc();
  bstrString = (BSTR)v5;
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 1;
  v5[3] = 0;
  v7 = 0x10000;
  v8 = 0x10000;
  for ( i = L"/WinSAT/SystemConfig/HistoryVersion"; ; ++i )
  {
    if ( !v8 )
      goto LABEL_64;
    if ( !*i )
      break;
    --v8;
  }
  if ( !i )
LABEL_64:
    throw (mlib::CStringTooBig *)&v35;
  v10 = i - L"/WinSAT/SystemConfig/HistoryVersion";
  *v6 = v10;
  v6[1] = v10;
  v11 = v10 + 1;
  v12 = 0;
  if ( v11 )
  {
    if ( v11 > 0x7FFFFFFFFFFFFFFFLL || (v12 = operator new(2 * v11)) == 0 )
      std::_Xbad_alloc();
  }
  v6[3] = (__int64)v12;
  if ( !v12 )
  {
    v35 = "bad allocation";
    exception::exception((exception *)pExceptionObject, &v35, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( *v6 )
    memcpy_0(v12, L"/WinSAT/SystemConfig/HistoryVersion", 2 * *v6);
  v13 = v6[3];
  if ( v13 )
    *(_WORD *)(v13 + 2 * *v6) = 0;
  v37 = v6;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue((__int64)a1, (__int64)&v37, 1, (__int64)&bstrString, v33);
  if ( NodeValue < 0 )
    goto LABEL_57;
  v15 = bstrString;
  if ( bstrString )
  {
    v16 = (__int64 *)operator new(0x28u);
    v17 = v16;
    if ( !v16 )
      std::_Xbad_alloc();
    *v16 = 0;
    v16[1] = 0;
    v16[2] = 1;
    v16[3] = 0;
    if ( v15 && *v15 )
    {
      for ( j = v15; ; ++j )
      {
        if ( !v7 )
          goto LABEL_36;
        if ( !*j )
          break;
        --v7;
      }
      if ( !j )
LABEL_36:
        throw (mlib::CStringTooBig *)&v35;
      v19 = j - v15;
      *v17 = v19;
      v17[1] = v19;
      v20 = v19 + 1;
      v21 = 0;
      if ( !v20 || v20 <= 0x7FFFFFFFFFFFFFFFLL && (v21 = operator new(2 * v20)) != 0 )
      {
        v17[3] = (__int64)v21;
        if ( !v21 )
        {
          v35 = "bad allocation";
          exception::exception((exception *)pExceptionObject, &v35, 1);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v22 = *v17;
        if ( !*v17 )
          goto LABEL_42;
        v23 = v15;
        goto LABEL_41;
      }
    }
    else
    {
      v21 = operator new(2u);
      if ( v21 )
      {
        v17[3] = (__int64)v21;
        v22 = *v17;
        if ( !*v17 )
        {
LABEL_42:
          v24 = v17[3];
          if ( v24 )
            *(_WORD *)(v24 + 2 * *v17) = 0;
          v25 = 0;
          v26 = *v17;
          if ( *v17 )
          {
            v27 = (wint_t *)v17[3];
            while ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v27) )
            {
              ++v27;
              if ( !--v26 )
                goto LABEL_53;
            }
            if ( iswdigit(*v27) )
            {
              do
              {
                v4 = *v27 + 2 * (5 * v4 - 24);
                if ( !--v26 )
                  break;
                ++v27;
              }
              while ( iswdigit(*v27) );
              v25 = v4;
            }
          }
LABEL_53:
          *a2 = v25;
          v28 = v17[2]-- == 1;
          if ( v28 )
          {
            v29 = (void *)v17[3];
            if ( v29 )
              operator delete(v29);
            operator delete(v17);
          }
LABEL_57:
          v15 = bstrString;
          goto LABEL_58;
        }
        v23 = 0;
LABEL_41:
        memcpy_0(v21, v23, 2 * v22);
        goto LABEL_42;
      }
    }
    std::_Xbad_alloc();
  }
LABEL_58:
  SysFreeString(v15);
  v30 = v37;
  v28 = v37[2]-- == 1;
  if ( v28 && v30 )
  {
    v31 = (void *)v30[3];
    if ( v31 )
      operator delete(v31);
    operator delete(v30);
  }
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18000a3cc  mov     rax, rsp
0x18000a3cf  push    rbp
0x18000a3d0  push    rsi
0x18000a3d1  push    rdi
0x18000a3d2  push    r12
0x18000a3d4  push    r13
0x18000a3d6  push    r14
0x18000a3d8  push    r15
0x18000a3da  mov     rbp, rsp
0x18000a3dd  sub     rsp, 60h
0x18000a3e1  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000a3e9  mov     [rax+8], rbx
0x18000a3ed  mov     r13, rdx
0x18000a3f0  mov     rdi, rcx
0x18000a3f3  xor     r14d, r14d
0x18000a3f6  mov     [rdx], r14d
0x18000a3f9  lea     ecx, [r14+28h]; Size
0x18000a3fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a402  mov     rbx, rax
0x18000a405  test    rax, rax
0x18000a408  jnz     short loc_18000A410
0x18000a40a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a410  mov     [rbp+bstrString], rbx
0x18000a414  mov     [rax], r14
0x18000a417  mov     [rax+8], r14
0x18000a41b  mov     r15d, 1
0x18000a421  mov     [rax+10h], r15
0x18000a425  mov     [rax+18h], r14
0x18000a429  mov     esi, 10000h
0x18000a42e  mov     ecx, esi
0x18000a430  lea     r12, aWinsatSystemco; "/WinSAT/SystemConfig/HistoryVersion"
0x18000a437  mov     rax, r12
0x18000a43a  test    rcx, rcx
0x18000a43d  jz      loc_18000A737
0x18000a443  cmp     [rax], r14w
0x18000a447  jz      short loc_18000A452
0x18000a449  add     rax, 2
0x18000a44d  sub     rcx, r15
0x18000a450  jmp     short loc_18000A43A
0x18000a452  test    rax, rax
0x18000a455  jz      loc_18000A737
0x18000a45b  sub     rax, r12
0x18000a45e  sar     rax, 1
0x18000a461  mov     [rbx], rax
0x18000a464  mov     [rbx+8], rax
0x18000a468  lea     rcx, [rax+1]
0x18000a46c  mov     rax, r14
0x18000a46f  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18000a479  test    rcx, rcx
0x18000a47c  jz      short loc_18000A496
0x18000a47e  cmp     rcx, rdx
0x18000a481  ja      short loc_18000A490
0x18000a483  add     rcx, rcx; Size
0x18000a486  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a48b  test    rax, rax
0x18000a48e  jnz     short loc_18000A496
0x18000a490  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a496  mov     [rbx+18h], rax
0x18000a49a  test    rax, rax
0x18000a49d  jnz     short loc_18000A4D7
0x18000a49f  lea     rax, aBadAllocation; "bad allocation"
0x18000a4a6  mov     [rbp+arg_8], rax
0x18000a4aa  mov     r8d, r15d
0x18000a4ad  lea     rdx, [rbp+arg_8]
0x18000a4b1  lea     rcx, [rbp+pExceptionObject]
0x18000a4b5  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000a4bb  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000a4c2  mov     [rbp+pExceptionObject], rax
0x18000a4c6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000a4cd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a4d1  call    _CxxThrowException_0
0x18000a4d7  mov     r8, [rbx]
0x18000a4da  test    r8, r8
0x18000a4dd  jz      short loc_18000A4ED
0x18000a4df  add     r8, r8; Size
0x18000a4e2  mov     rdx, r12; Src
0x18000a4e5  mov     rcx, rax; void *
0x18000a4e8  call    memcpy_0
0x18000a4ed  mov     rdx, [rbx+18h]
0x18000a4f1  test    rdx, rdx
0x18000a4f4  jz      short loc_18000A4FE
0x18000a4f6  mov     rcx, [rbx]
0x18000a4f9  mov     [rdx+rcx*2], r14w
0x18000a4fe  mov     [rbp+arg_18], rbx
0x18000a502  mov     [rbp+bstrString], r14
0x18000a506  lea     r9, [rbp+bstrString]
0x18000a50a  mov     r8b, r15b
0x18000a50d  lea     rdx, [rbp+arg_18]
0x18000a511  mov     rcx, rdi
0x18000a514  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000a519  mov     r12d, eax
0x18000a51c  test    eax, eax
0x18000a51e  js      loc_18000A6E6
0x18000a524  mov     rdi, [rbp+bstrString]
0x18000a528  test    rdi, rdi
0x18000a52b  jz      loc_18000A6EA
0x18000a531  mov     ecx, 28h ; '('; Size
0x18000a536  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a53b  mov     rbx, rax
0x18000a53e  test    rax, rax
0x18000a541  jnz     short loc_18000A549
0x18000a543  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a549  mov     [rbp+var_28], rbx
0x18000a54d  mov     [rax], r14
0x18000a550  mov     [rax+8], r14
0x18000a554  mov     [rax+10h], r15
0x18000a558  mov     [rax+18h], r14
0x18000a55c  test    rdi, rdi
0x18000a55f  jz      loc_18000A627
0x18000a565  cmp     [rdi], r14w
0x18000a569  jz      loc_18000A627
0x18000a56f  mov     rax, rdi
0x18000a572  test    rsi, rsi
0x18000a575  jz      loc_18000A616
0x18000a57b  cmp     [rax], r14w
0x18000a57f  jz      short loc_18000A58A
0x18000a581  add     rax, 2
0x18000a585  sub     rsi, r15
0x18000a588  jmp     short loc_18000A572
0x18000a58a  test    rax, rax
0x18000a58d  jz      loc_18000A616
0x18000a593  sub     rax, rdi
0x18000a596  sar     rax, 1
0x18000a599  mov     [rbx], rax
0x18000a59c  mov     [rbx+8], rax
0x18000a5a0  lea     rcx, [rax+1]
0x18000a5a4  mov     rax, r14
0x18000a5a7  test    rcx, rcx
0x18000a5aa  jz      short loc_18000A5C8
0x18000a5ac  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a5b6  cmp     rcx, rax
0x18000a5b9  ja      short loc_18000A636
0x18000a5bb  add     rcx, rcx; Size
0x18000a5be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5c3  test    rax, rax
0x18000a5c6  jz      short loc_18000A636
0x18000a5c8  mov     [rbx+18h], rax
0x18000a5cc  test    rax, rax
0x18000a5cf  jnz     short loc_18000A609
0x18000a5d1  lea     rax, aBadAllocation; "bad allocation"
0x18000a5d8  mov     [rbp+arg_8], rax
0x18000a5dc  mov     r8d, r15d
0x18000a5df  lea     rdx, [rbp+arg_8]
0x18000a5e3  lea     rcx, [rbp+pExceptionObject]
0x18000a5e7  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000a5ed  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000a5f4  mov     [rbp+pExceptionObject], rax
0x18000a5f8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000a5ff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a603  call    _CxxThrowException_0
0x18000a609  mov     r8, [rbx]
0x18000a60c  test    r8, r8
0x18000a60f  jz      short loc_18000A655
0x18000a611  mov     rdx, rdi
0x18000a614  jmp     short loc_18000A64A
0x18000a616  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x18000a61d  lea     rcx, [rbp+arg_8]; pExceptionObject
0x18000a621  call    _CxxThrowException_0
0x18000a627  mov     ecx, 2; Size
0x18000a62c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a631  test    rax, rax
0x18000a634  jnz     short loc_18000A63C
0x18000a636  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a63c  mov     [rbx+18h], rax
0x18000a640  mov     r8, [rbx]
0x18000a643  test    r8, r8
0x18000a646  jz      short loc_18000A655
0x18000a648  xor     edx, edx; Src
0x18000a64a  add     r8, r8; Size
0x18000a64d  mov     rcx, rax; void *
0x18000a650  call    memcpy_0
0x18000a655  mov     rdx, [rbx+18h]
0x18000a659  test    rdx, rdx
0x18000a65c  jz      short loc_18000A666
0x18000a65e  mov     rcx, [rbx]
0x18000a661  mov     [rdx+rcx*2], r14w
0x18000a666  mov     r15d, r14d
0x18000a669  mov     rsi, [rbx]
0x18000a66c  test    rsi, rsi
0x18000a66f  jz      short loc_18000A6C3
0x18000a671  mov     rdi, [rbx+18h]
0x18000a675  movzx   ecx, word ptr [rdi]
0x18000a678  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18000a67d  test    al, al
0x18000a67f  jz      short loc_18000A68D
0x18000a681  add     rdi, 2
0x18000a685  sub     rsi, 1
0x18000a689  jnz     short loc_18000A675
0x18000a68b  jmp     short loc_18000A6C3
0x18000a68d  movzx   ecx, word ptr [rdi]; C
0x18000a690  call    cs:__imp_iswdigit
0x18000a696  test    eax, eax
0x18000a698  jz      short loc_18000A6C3
0x18000a69a  lea     r14d, [r14+r14*4]
0x18000a69e  movzx   eax, word ptr [rdi]
0x18000a6a1  lea     r14d, [r14-18h]
0x18000a6a5  lea     r14d, [rax+r14*2]
0x18000a6a9  sub     rsi, 1
0x18000a6ad  jz      short loc_18000A6C0
0x18000a6af  add     rdi, 2
0x18000a6b3  movzx   ecx, word ptr [rdi]; C
0x18000a6b6  call    cs:__imp_iswdigit
0x18000a6bc  test    eax, eax
0x18000a6be  jnz     short loc_18000A69A
0x18000a6c0  mov     r15d, r14d
0x18000a6c3  mov     [r13+0], r15d
0x18000a6c7  sub     qword ptr [rbx+10h], 1
0x18000a6cc  jnz     short loc_18000A6E6
0x18000a6ce  mov     rcx, [rbx+18h]
0x18000a6d2  test    rcx, rcx
0x18000a6d5  jz      short loc_18000A6DD
0x18000a6d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a6dd  mov     rcx, rbx
0x18000a6e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a6e6  mov     rdi, [rbp+bstrString]
0x18000a6ea  mov     rcx, rdi; bstrString
0x18000a6ed  call    cs:__imp_SysFreeString
0x18000a6f3  nop
0x18000a6f4  mov     rbx, [rbp+arg_18]
0x18000a6f8  sub     qword ptr [rbx+10h], 1
0x18000a6fd  jnz     short loc_18000A71C
0x18000a6ff  test    rbx, rbx
0x18000a702  jz      short loc_18000A71C
0x18000a704  mov     rcx, [rbx+18h]
0x18000a708  test    rcx, rcx
0x18000a70b  jz      short loc_18000A713
0x18000a70d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a713  mov     rcx, rbx
0x18000a716  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a71c  mov     eax, r12d
0x18000a71f  mov     rbx, [rsp+60h+arg_0]
0x18000a727  add     rsp, 60h
0x18000a72b  pop     r15
0x18000a72d  pop     r14
0x18000a72f  pop     r13
0x18000a731  pop     r12
0x18000a733  pop     rdi
0x18000a734  pop     rsi
0x18000a735  pop     rbp
0x18000a736  retn
0x18000a737  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x18000a73e  lea     rcx, [rbp+arg_8]; pExceptionObject
0x18000a742  call    _CxxThrowException_0
```
