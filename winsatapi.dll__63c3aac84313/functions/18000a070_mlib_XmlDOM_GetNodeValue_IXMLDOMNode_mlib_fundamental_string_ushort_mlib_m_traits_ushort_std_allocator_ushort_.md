# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000a070`
- end: `0x18000a30a`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z`
- size: `666`
- prototype: `__int64 __fastcall(int, int, int, int, __int64 pExceptionObject)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002b2e4`
- `0x18002b3e8`
- `0x18002b714`

## callees

- `0x180009d50`
- `0x18000a070`
- `0x180013220`
- `0x180013290`
- `0x180013fa3`
- `0x180013fb6`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000a11f`
- `msvcrt!iswdigit` at `0x18000a149`
- `msvcrt!iswdigit` at `0x18000a11f`
- `msvcrt!iswdigit` at `0x18000a149`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000a2e0`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000a2e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a169`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a172`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a169`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a172`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a180`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a180`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x18000a282`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x18000a282`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, char a3, int *a4, __int64 pExceptionObject)
{
  int v6; // edi
  int NodeValue; // r15d
  BSTR v8; // rbx
  __int64 *v9; // rax
  __int64 *v10; // r14
  __int64 v11; // rcx
  BSTR i; // rax
  __int64 v13; // rbx
  WCHAR *j; // rsi
  int v15; // ebp
  void *v17; // rcx
  void *v19; // rax
  __int64 v20; // r8
  BSTR v21; // rdx
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  __int64 v24; // rdx
  int lpCharType; // [rsp+20h] [rbp-88h]
  WCHAR SrcStr; // [rsp+30h] [rbp-78h] BYREF
  BSTR bstrString[3]; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v28[11]; // [rsp+50h] [rbp-58h] BYREF

  bstrString[1] = (BSTR)-2LL;
  v6 = 0;
  bstrString[0] = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, a3, (__int64)bstrString, lpCharType);
  if ( NodeValue < 0 )
  {
LABEL_18:
    v8 = bstrString[0];
    goto LABEL_19;
  }
  v8 = bstrString[0];
  if ( bstrString[0] )
  {
    v9 = (__int64 *)operator new(0x28u);
    v10 = v9;
    if ( !v9 )
      std::_Xbad_alloc();
    bstrString[2] = (BSTR)v9;
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 1;
    v9[3] = 0;
    if ( v8 && *v8 )
    {
      v11 = 0x10000;
      for ( i = v8; ; ++i )
      {
        if ( !v11 )
          throw (mlib::CStringTooBig *)&pExceptionObject;
        if ( !*i )
          break;
        --v11;
      }
      v22 = i - v8;
      *v10 = v22;
      v10[1] = v22;
      v23 = v22 + 1;
      v19 = 0;
      if ( !v23 || v23 <= 0x7FFFFFFFFFFFFFFFLL && (v19 = operator new(2 * v23)) != 0 )
      {
        v10[3] = (__int64)v19;
        if ( !v19 )
        {
          pExceptionObject = (__int64)"bad allocation";
          exception::exception((exception *)v28, (const char *const *)&pExceptionObject, 1);
          v28[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)v28;
        }
        v20 = *v10;
        if ( !*v10 )
          goto LABEL_31;
        v21 = v8;
        goto LABEL_30;
      }
    }
    else
    {
      v19 = operator new(2u);
      if ( v19 )
      {
        v10[3] = (__int64)v19;
        v20 = *v10;
        if ( !*v10 )
        {
LABEL_31:
          v24 = v10[3];
          if ( v24 )
            *(_WORD *)(v24 + 2 * *v10) = 0;
          v15 = 0;
          v13 = *v10;
          if ( *v10 )
          {
            for ( j = (WCHAR *)v10[3]; ; ++j )
            {
              SrcStr = *j;
              LOWORD(pExceptionObject) = 0;
              if ( !GetStringTypeExW(0x400u, 1u, &SrcStr, 1, (LPWORD)&pExceptionObject) )
                break;
              if ( (pExceptionObject & 0x48) == 0 )
              {
                if ( !v13 )
                  goto LABEL_14;
                break;
              }
              if ( !--v13 )
                goto LABEL_14;
            }
            if ( iswdigit(*j) )
            {
              do
              {
                v6 = *j + 2 * (5 * v6 - 24);
                if ( !--v13 )
                  break;
                ++j;
              }
              while ( iswdigit(*j) );
              v15 = v6;
            }
          }
LABEL_14:
          *a4 = v15;
          if ( v10[2]-- == 1 )
          {
            v17 = (void *)v10[3];
            if ( v17 )
              operator delete(v17);
            operator delete(v10);
          }
          goto LABEL_18;
        }
        v21 = 0;
LABEL_30:
        memcpy_0(v19, v21, 2 * v20);
        goto LABEL_31;
      }
    }
    std::_Xbad_alloc();
  }
LABEL_19:
  SysFreeString(v8);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18000a070  push    rbx
0x18000a072  push    rbp
0x18000a073  push    rsi
0x18000a074  push    rdi
0x18000a075  push    r12
0x18000a077  push    r14
0x18000a079  push    r15
0x18000a07b  sub     rsp, 70h
0x18000a07f  mov     [rsp+0A8h+var_68], 0FFFFFFFFFFFFFFFEh
0x18000a088  mov     r12, r9
0x18000a08b  xor     edi, edi
0x18000a08d  mov     [rsp+0A8h+bstrString], rdi
0x18000a092  lea     r9, [rsp+0A8h+bstrString]
0x18000a097  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000a09c  mov     r15d, eax
0x18000a09f  test    eax, eax
0x18000a0a1  js      loc_18000A178
0x18000a0a7  mov     rbx, [rsp+0A8h+bstrString]
0x18000a0ac  test    rbx, rbx
0x18000a0af  jz      loc_18000A17D
0x18000a0b5  mov     ecx, 28h ; '('; Size
0x18000a0ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a0bf  mov     r14, rax
0x18000a0c2  test    rax, rax
0x18000a0c5  jz      loc_18000A2B8
0x18000a0cb  mov     [rsp+0A8h+var_60], rax
0x18000a0d0  mov     [rax], rdi
0x18000a0d3  mov     [rax+8], rdi
0x18000a0d7  mov     qword ptr [rax+10h], 1
0x18000a0df  mov     [rax+18h], rdi
0x18000a0e3  test    rbx, rbx
0x18000a0e6  jz      loc_18000A1AD
0x18000a0ec  cmp     [rbx], di
0x18000a0ef  jz      loc_18000A1AD
0x18000a0f5  mov     ecx, 10000h
0x18000a0fa  mov     rax, rbx
0x18000a0fd  nop     dword ptr [rax]
0x18000a100  test    rcx, rcx
0x18000a103  jz      loc_18000A198
0x18000a109  cmp     word ptr [rax], 0
0x18000a10d  jz      loc_18000A1D0
0x18000a113  add     rax, 2
0x18000a117  dec     rcx
0x18000a11a  jmp     short loc_18000A100
0x18000a11c  movzx   ecx, word ptr [rsi]; C
0x18000a11f  call    cs:__imp_iswdigit
0x18000a125  test    eax, eax
0x18000a127  jz      short loc_18000A155
0x18000a129  nop     dword ptr [rax+00000000h]
0x18000a130  lea     edi, [rdi+rdi*4]
0x18000a133  movzx   eax, word ptr [rsi]
0x18000a136  lea     edi, [rdi-18h]
0x18000a139  lea     edi, [rax+rdi*2]
0x18000a13c  sub     rbx, 1
0x18000a140  jz      short loc_18000A153
0x18000a142  add     rsi, 2
0x18000a146  movzx   ecx, word ptr [rsi]; C
0x18000a149  call    cs:__imp_iswdigit
0x18000a14f  test    eax, eax
0x18000a151  jnz     short loc_18000A130
0x18000a153  mov     ebp, edi
0x18000a155  mov     [r12], ebp
0x18000a159  sub     qword ptr [r14+10h], 1
0x18000a15e  jnz     short loc_18000A178
0x18000a160  mov     rcx, [r14+18h]
0x18000a164  test    rcx, rcx
0x18000a167  jz      short loc_18000A16F
0x18000a169  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a16f  mov     rcx, r14
0x18000a172  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a178  mov     rbx, [rsp+0A8h+bstrString]
0x18000a17d  mov     rcx, rbx; bstrString
0x18000a180  call    cs:__imp_SysFreeString
0x18000a186  mov     eax, r15d
0x18000a189  add     rsp, 70h
0x18000a18d  pop     r15
0x18000a18f  pop     r14
0x18000a191  pop     r12
0x18000a193  pop     rdi
0x18000a194  pop     rsi
0x18000a195  pop     rbp
0x18000a196  pop     rbx
0x18000a197  retn
0x18000a198  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x18000a19f  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000a1a7  call    _CxxThrowException_0
0x18000a1ad  mov     ecx, 2; Size
0x18000a1b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a1b7  test    rax, rax
0x18000a1ba  jz      loc_18000A304
0x18000a1c0  mov     [r14+18h], rax
0x18000a1c4  mov     r8, [r14]
0x18000a1c7  test    r8, r8
0x18000a1ca  jz      short loc_18000A230
0x18000a1cc  xor     edx, edx
0x18000a1ce  jmp     short loc_18000A225
0x18000a1d0  sub     rax, rbx
0x18000a1d3  sar     rax, 1
0x18000a1d6  mov     [r14], rax
0x18000a1d9  mov     [r14+8], rax
0x18000a1dd  lea     rcx, [rax+1]
0x18000a1e1  mov     rax, rdi
0x18000a1e4  test    rcx, rcx
0x18000a1e7  jz      short loc_18000A20D
0x18000a1e9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a1f3  cmp     rcx, rax
0x18000a1f6  ja      loc_18000A304
0x18000a1fc  add     rcx, rcx; Size
0x18000a1ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a204  test    rax, rax
0x18000a207  jz      loc_18000A304
0x18000a20d  mov     [r14+18h], rax
0x18000a211  test    rax, rax
0x18000a214  jz      loc_18000A2BE
0x18000a21a  mov     r8, [r14]
0x18000a21d  test    r8, r8
0x18000a220  jz      short loc_18000A230
0x18000a222  mov     rdx, rbx; Src
0x18000a225  add     r8, r8; Size
0x18000a228  mov     rcx, rax; void *
0x18000a22b  call    memcpy_0
0x18000a230  mov     rdx, [r14+18h]
0x18000a234  test    rdx, rdx
0x18000a237  jz      short loc_18000A240
0x18000a239  mov     rcx, [r14]
0x18000a23c  mov     [rdx+rcx*2], di
0x18000a240  mov     ebp, edi
0x18000a242  mov     rbx, [r14]
0x18000a245  test    rbx, rbx
0x18000a248  jz      loc_18000A155
0x18000a24e  mov     rsi, [r14+18h]
0x18000a252  movzx   eax, word ptr [rsi]
0x18000a255  mov     [rsp+0A8h+SrcStr], ax
0x18000a25a  mov     word ptr [rsp+0A8h+pExceptionObject], di
0x18000a262  lea     rax, [rsp+0A8h+pExceptionObject]
0x18000a26a  mov     qword ptr [rsp+0A8h+lpCharType], rax; lpCharType
0x18000a26f  mov     r9d, 1; cchSrc
0x18000a275  lea     r8, [rsp+0A8h+SrcStr]; lpSrcStr
0x18000a27a  mov     edx, r9d; dwInfoType
0x18000a27d  mov     ecx, 400h; Locale
0x18000a282  call    cs:__imp_GetStringTypeExW
0x18000a288  test    eax, eax
0x18000a28a  jz      loc_18000A11C
0x18000a290  test    byte ptr [rsp+0A8h+pExceptionObject], 48h
0x18000a298  jz      short loc_18000A2AA
0x18000a29a  sub     rbx, 1
0x18000a29e  jz      loc_18000A155
0x18000a2a4  add     rsi, 2
0x18000a2a8  jmp     short loc_18000A252
0x18000a2aa  test    rbx, rbx
0x18000a2ad  jz      loc_18000A155
0x18000a2b3  jmp     loc_18000A11C
0x18000a2b8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a2be  lea     rax, aBadAllocation; "bad allocation"
0x18000a2c5  mov     [rsp+0A8h+pExceptionObject], rax
0x18000a2cd  mov     r8d, 1
0x18000a2d3  lea     rdx, [rsp+0A8h+pExceptionObject]
0x18000a2db  lea     rcx, [rsp+0A8h+var_58]
0x18000a2e0  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000a2e6  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000a2ed  mov     [rsp+0A8h+var_58], rax
0x18000a2f2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000a2f9  lea     rcx, [rsp+0A8h+var_58]; pExceptionObject
0x18000a2fe  call    _CxxThrowException_0
0x18000a304  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
