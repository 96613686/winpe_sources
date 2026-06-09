# DataStoreReader::GetAllWinSATAssessmentFileNames(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> &,DataStoreID,AssessmentTimeTaken)

- ea: `0x1800043a0`
- end: `0x180004636`
- name: `?GetAllWinSATAssessmentFileNames@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@W4DataStoreID@@W4AssessmentTimeTaken@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180001a70`
- `0x18001f070`

## callees

- `0x1800043a0`
- `0x180004b10`
- `0x180005394`
- `0x180005570`
- `0x1800071d0`
- `0x18000c5e4`
- `0x180013220`
- `0x180013290`
- `0x180013370`
- `0x180013fa3`
- `0x18002aa74`
- `0x18002dec0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800044c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000456f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004592`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800044c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000456f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004592`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800045c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800045cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800045c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800045cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000459c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000459c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000449c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000449c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044cc`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800044af`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800044af`

## string_xrefs

- `0x180004428`: `.WinSAT.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DataStoreReader::GetAllWinSATAssessmentFileNames(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  const wchar_t *i; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rsi
  WCHAR *v9; // rdx
  WCHAR *v10; // rdi
  WCHAR *v11; // rax
  DWORD LastError; // esi
  signed int v13; // eax
  unsigned int v14; // edi
  bool v15; // zf
  void *v16; // rcx
  char pExceptionObject; // [rsp+30h] [rbp-2B8h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-2B0h] BYREF
  void **v20; // [rsp+50h] [rbp-298h] BYREF
  __int16 v21; // [rsp+58h] [rbp-290h]
  __int64 v22; // [rsp+260h] [rbp-88h]
  __int64 v23; // [rsp+268h] [rbp-80h]
  __int64 v24; // [rsp+270h] [rbp-78h]
  __int64 v25; // [rsp+278h] [rbp-70h]
  __int64 v26; // [rsp+280h] [rbp-68h]
  void **v27; // [rsp+288h] [rbp-60h]
  __int128 v28; // [rsp+290h] [rbp-58h]
  __int128 v29; // [rsp+2A0h] [rbp-48h]
  _QWORD *v30; // [rsp+2B0h] [rbp-38h]

  v19[1] = -2;
  v4 = operator new(0x28u);
  if ( !v4 )
    std::_Xbad_alloc();
  v19[0] = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v4,
             260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    v19,
    L"*%s.Assessment (%s)",
    L"Formal",
    L"*");
  v5 = 0x10000;
  for ( i = L".WinSAT.xml"; ; ++i )
  {
    if ( !v5 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v5;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
    v19,
    0,
    *(_QWORD *)v19[0]);
  v7 = (_QWORD *)v19[0];
  v8 = *(_QWORD *)(v19[0] + 24LL);
  v9 = *(WCHAR **)(*(_QWORD *)a1 + 24LL);
  if ( !v9 || (v10 = 0, !*v9) )
  {
    v11 = (WCHAR *)operator new[](0x208u);
    v10 = v11;
    if ( !v11 )
    {
      SetLastError(8u);
      goto LABEL_18;
    }
    if ( !GetCurrentDirectoryW(0x104u, v11) )
    {
      LastError = GetLastError();
      operator delete[](v10);
      SetLastError(LastError);
      goto LABEL_17;
    }
    v9 = v10;
  }
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = 0;
  v27 = &mlib::FSpecList<unsigned short>::`vftable';
  v28 = 0;
  v29 = 0;
  v21 = 0;
  v20 = &mlib::FileFinder<unsigned short>::`vftable';
  v30 = a2;
  LastError = mlib::TraverseDirT<unsigned short>::traverse_dir(&v20, v9, v8);
  if ( v10 )
    operator delete[](v10);
  v20 = &mlib::TraverseDirT<unsigned short>::`vftable';
  v27 = &mlib::FSpecList<unsigned short>::`vftable';
  operator delete[](*((void **)&v29 + 1));
LABEL_17:
  if ( !LastError )
  {
    std::_Sort<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> *,__int64,bool (*)(mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &,mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &)>(
      *a2,
      a2[1],
      (__int64)(a2[1] - *a2) >> 3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v19);
    return 0;
  }
LABEL_18:
  v13 = GetLastError();
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  v15 = v7[2]-- == 1;
  if ( v15 && v7 )
  {
    v16 = (void *)v7[3];
    if ( v16 )
      operator delete(v16);
    operator delete(v7);
  }
  return v14;
}

```

## disassembly

```asm
0x1800043a0  mov     rax, rsp
0x1800043a3  push    rsi
0x1800043a4  push    rdi
0x1800043a5  push    r14
0x1800043a7  sub     rsp, 2D0h
0x1800043ae  mov     [rsp+2E8h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x1800043b7  mov     [rax+10h], rbx
0x1800043bb  mov     [rax+18h], rbp
0x1800043bf  mov     rax, cs:__security_cookie
0x1800043c6  xor     rax, rsp
0x1800043c9  mov     [rsp+2E8h+var_28], rax
0x1800043d1  mov     r14, rdx
0x1800043d4  mov     rdi, rcx
0x1800043d7  mov     ecx, 28h ; '('; Size
0x1800043dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800043e1  test    rax, rax
0x1800043e4  jnz     short loc_1800043EC
0x1800043e6  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800043ec  mov     [rsp+2E8h+var_2B0], rax
0x1800043f1  mov     edx, 104h
0x1800043f6  mov     rcx, rax
0x1800043f9  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x1800043fe  nop
0x1800043ff  mov     [rsp+2E8h+var_2B0], rax
0x180004404  lea     r9, asc_180035914; "*"
0x18000440b  lea     r8, aFormal; "Formal"
0x180004412  lea     rdx, aSAssessmentS; "*%s.Assessment (%s)"
0x180004419  lea     rcx, [rsp+2E8h+var_2B0]
0x18000441e  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180004423  mov     ecx, 10000h
0x180004428  lea     r9, aWinsatXml; ".WinSAT.xml"
0x18000442f  mov     rax, r9
0x180004432  test    rcx, rcx
0x180004435  jz      loc_180004624
0x18000443b  cmp     word ptr [rax], 0
0x18000443f  jz      short loc_18000444A
0x180004441  add     rax, 2
0x180004445  dec     rcx
0x180004448  jmp     short loc_180004432
0x18000444a  sub     rax, r9
0x18000444d  sar     rax, 1
0x180004450  mov     [rsp+2E8h+var_2C8], rax
0x180004455  mov     r8, [rsp+2E8h+var_2B0]
0x18000445a  mov     r8, [r8]
0x18000445d  xor     edx, edx
0x18000445f  lea     rcx, [rsp+2E8h+var_2B0]
0x180004464  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180004469  mov     rbx, [rsp+2E8h+var_2B0]
0x18000446e  mov     rsi, [rbx+18h]
0x180004472  mov     rax, [rdi]
0x180004475  mov     rdx, [rax+18h]
0x180004479  test    rdx, rdx
0x18000447c  jz      short loc_180004485
0x18000447e  xor     edi, edi
0x180004480  cmp     [rdx], di
0x180004483  jnz     short loc_1800044DA
0x180004485  mov     ecx, 208h; unsigned __int64
0x18000448a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000448f  mov     rdi, rax
0x180004492  test    rax, rax
0x180004495  jnz     short loc_1800044A7
0x180004497  mov     ecx, 8; dwErrCode
0x18000449c  call    cs:__imp_SetLastError
0x1800044a2  jmp     loc_18000459C
0x1800044a7  mov     rdx, rdi; lpBuffer
0x1800044aa  mov     ecx, 104h; nBufferLength
0x1800044af  call    cs:__imp_GetCurrentDirectoryW
0x1800044b5  test    eax, eax
0x1800044b7  jnz     short loc_1800044D7
0x1800044b9  call    cs:__imp_GetLastError
0x1800044bf  mov     esi, eax
0x1800044c1  mov     rcx, rdi
0x1800044c4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800044ca  mov     ecx, esi; dwErrCode
0x1800044cc  call    cs:__imp_SetLastError
0x1800044d2  jmp     loc_180004598
0x1800044d7  mov     rdx, rdi
0x1800044da  mov     [rsp+2E8h+var_88], 0
0x1800044e6  mov     [rsp+2E8h+var_80], 0
0x1800044f2  mov     [rsp+2E8h+var_78], 0
0x1800044fe  mov     [rsp+2E8h+var_70], 0FFFFFFFFFFFFFFFFh
0x18000450a  mov     [rsp+2E8h+var_68], 0
0x180004516  lea     rbp, ??_7?$FSpecList@G@mlib@@6B@; const mlib::FSpecList<ushort>::`vftable'
0x18000451d  mov     [rsp+2E8h+var_60], rbp
0x180004525  xorps   xmm0, xmm0
0x180004528  movdqa  [rsp+2E8h+var_58], xmm0
0x180004531  xorps   xmm1, xmm1
0x180004534  movdqa  [rsp+2E8h+var_48], xmm1
0x18000453d  xor     eax, eax
0x18000453f  mov     [rsp+2E8h+var_290], ax
0x180004544  lea     rax, ??_7?$FileFinder@G@mlib@@6B@; const mlib::FileFinder<ushort>::`vftable'
0x18000454b  mov     [rsp+2E8h+var_298], rax
0x180004550  mov     [rsp+2E8h+var_38], r14
0x180004558  mov     r8, rsi
0x18000455b  lea     rcx, [rsp+2E8h+var_298]
0x180004560  call    ?traverse_dir@?$TraverseDirT@G@mlib@@QEAAKPEBG0_K_N@Z; mlib::TraverseDirT<ushort>::traverse_dir(ushort const *,ushort const *,unsigned __int64,bool)
0x180004565  mov     esi, eax
0x180004567  test    rdi, rdi
0x18000456a  jz      short loc_180004576
0x18000456c  mov     rcx, rdi
0x18000456f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004575  nop
0x180004576  lea     rax, ??_7?$TraverseDirT@G@mlib@@6B@; const mlib::TraverseDirT<ushort>::`vftable'
0x18000457d  mov     [rsp+2E8h+var_298], rax
0x180004582  mov     [rsp+2E8h+var_60], rbp
0x18000458a  mov     rcx, qword ptr [rsp+2E8h+var_48+8]
0x180004592  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004598  test    esi, esi
0x18000459a  jz      short loc_1800045FF
0x18000459c  call    cs:__imp_GetLastError
0x1800045a2  mov     edi, eax
0x1800045a4  test    eax, eax
0x1800045a6  jle     short loc_1800045B1
0x1800045a8  movzx   edi, ax
0x1800045ab  or      edi, 80070000h
0x1800045b1  sub     qword ptr [rbx+10h], 1
0x1800045b6  jnz     short loc_1800045D5
0x1800045b8  test    rbx, rbx
0x1800045bb  jz      short loc_1800045D5
0x1800045bd  mov     rcx, [rbx+18h]
0x1800045c1  test    rcx, rcx
0x1800045c4  jz      short loc_1800045CC
0x1800045c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800045cc  mov     rcx, rbx
0x1800045cf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800045d5  mov     eax, edi
0x1800045d7  mov     rcx, [rsp+2E8h+var_28]
0x1800045df  xor     rcx, rsp; StackCookie
0x1800045e2  call    __security_check_cookie
0x1800045e7  lea     r11, [rsp+2E8h+var_18]
0x1800045ef  mov     rbx, [r11+28h]
0x1800045f3  mov     rbp, [r11+30h]
0x1800045f7  mov     rsp, r11
0x1800045fa  pop     r14
0x1800045fc  pop     rdi
0x1800045fd  pop     rsi
0x1800045fe  retn
0x1800045ff  mov     rdx, [r14+8]
0x180004603  mov     rcx, [r14]
0x180004606  mov     r8, rdx
0x180004609  sub     r8, rcx
0x18000460c  sar     r8, 3
0x180004610  call    ??$_Sort@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_JP6A_NAEBV12@0@Z@std@@YAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0_JP6A_NAEBV12@2@Z@Z; std::_Sort<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &))
0x180004615  nop
0x180004616  lea     rcx, [rsp+2E8h+var_2B0]
0x18000461b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180004620  xor     eax, eax
0x180004622  jmp     short loc_1800045D7
0x180004624  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x18000462b  lea     rcx, [rsp+2E8h+pExceptionObject]; pExceptionObject
0x180004630  call    _CxxThrowException_0
```
