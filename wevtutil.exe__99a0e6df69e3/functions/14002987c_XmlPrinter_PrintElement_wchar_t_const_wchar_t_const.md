# XmlPrinter::PrintElement(wchar_t const *,wchar_t const *)

- ea: `0x14002987c`
- end: `0x140029b1a`
- name: `?PrintElement@XmlPrinter@@QEAAXPEB_W0@Z`
- size: `670`
- prototype: `void __fastcall(XmlPrinter *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1400217b8`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140007b10`
- `0x140008100`
- `0x140008130`
- `0x14000cabc`
- `0x14000cc04`
- `0x14000d144`
- `0x14000d2ec`
- `0x14000d6e8`
- `0x14000d868`
- `0x14000d88c`
- `0x14001a9b8`
- `0x140021b00`
- `0x140022cec`
- `0x14002987c`
- `0x14002f4a8`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall XmlPrinter::PrintElement(XmlPrinter *this, const wchar_t *a2, const wchar_t *a3)
{
  __int64 v6; // r8
  unsigned __int64 v7; // rbx
  const char *v8; // r8
  int v9; // r8d
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // r8
  void *v13; // rax
  void *v14; // rax
  void *v15; // rax
  __int64 v16; // [rsp+20h] [rbp-60h] BYREF
  _WORD *v17; // [rsp+28h] [rbp-58h]
  __int128 v18; // [rsp+40h] [rbp-40h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+50h] [rbp-30h] BYREF

  if ( *((_BYTE *)this + 32) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v16);
    v7 = 2 * ((v6 - *((_QWORD *)this + 1)) >> 5);
    if ( v7 > utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(&v16)
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(&v16, v7) )
    {
      goto LABEL_15;
    }
    utl::_CharTraitsBase<wchar_t,unsigned short,unsigned short>::assign(v16, v7, 32);
    v17 = (_WORD *)(v16 + 2 * v7);
    *v17 = 0;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &v16,
                             (unsigned int)(v9 + 28)) )
      goto LABEL_15;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             &v16,
                             a2) )
      goto LABEL_15;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &v16,
                             62) )
      goto LABEL_15;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    *(_QWORD *)&v18 = a3;
    *((_QWORD *)&v18 + 1) = v10;
    if ( !(unsigned __int8)AppendEscapedXml(&v16, &v18, 0)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             &v16,
                             L"</",
                             2)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             &v16,
                             a2)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             &v16,
                             L">\r\n",
                             3) )
    {
LABEL_15:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1c2e816ccb3d35486907a84ddef57de8_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v8, 147);
      throw (EvtException *)pExceptionObject;
    }
    *(_QWORD *)&v18 = v16;
    *((_QWORD *)&v18 + 1) = ((__int64)v17 - v16) >> 1;
    FilePuts(*(HANDLE *)this, &v18);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v16);
  }
  else
  {
    std::wstring::wstring(pExceptionObject, 2 * ((__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 5) - 2);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = (void *)std::wstring::_Append<wchar_t>(pExceptionObject);
    v14 = (void *)std::wstring::_Append<wchar_t>(v13);
    do
      ++v11;
    while ( a3[v11] );
    v15 = (void *)std::wstring::_Append<wchar_t>(v14);
    std::wstring::_Append<wchar_t>(v15);
    v18 = *(_OWORD *)std::wstring::operator std::wstring_view(pExceptionObject, &v16);
    FilePuts(*(HANDLE *)this, &v18);
    std::wstring::_Tidy_deallocate(pExceptionObject);
  }
}

```

## disassembly

```asm
0x14002987c  mov     [rsp-28h+arg_18], rbx
0x140029881  push    rbp
0x140029882  push    rdi
0x140029883  push    r12
0x140029885  push    r14
0x140029887  push    r15
0x140029889  mov     rbp, rsp
0x14002988c  sub     rsp, 80h
0x140029893  mov     rax, cs:__security_cookie
0x14002989a  xor     rax, rsp
0x14002989d  mov     [rbp+var_8], rax
0x1400298a1  mov     r14, r8
0x1400298a4  mov     rdi, rdx
0x1400298a7  mov     r15, rcx
0x1400298aa  mov     r8, [rcx+10h]
0x1400298ae  xor     r12d, r12d
0x1400298b1  cmp     [rcx+20h], r12b
0x1400298b5  jz      loc_140029A52
0x1400298bb  lea     rcx, [rbp+var_60]
0x1400298bf  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400298c4  nop
0x1400298c5  sub     r8, [r15+8]
0x1400298c9  sar     r8, 5
0x1400298cd  lea     rbx, [r8+r8]
0x1400298d1  lea     rcx, [rbp+var_60]
0x1400298d5  call    ?capacity@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(void)
0x1400298da  cmp     rbx, rax
0x1400298dd  jbe     short loc_1400298F3
0x1400298df  mov     rdx, rbx
0x1400298e2  lea     rcx, [rbp+var_60]
0x1400298e6  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(unsigned __int64)
0x1400298eb  test    al, al
0x1400298ed  jz      loc_1400299F3
0x1400298f3  mov     r8d, 20h ; ' '
0x1400298f9  mov     rdx, rbx
0x1400298fc  mov     rcx, [rbp+var_60]
0x140029900  call    ?assign@?$_CharTraitsBase@_WGG@utl@@SAPEA_WPEA_W_K_W@Z; utl::_CharTraitsBase<wchar_t,ushort,ushort>::assign(wchar_t *,unsigned __int64,wchar_t)
0x140029905  mov     rdx, [rbp+var_60]
0x140029909  lea     rcx, [rdx+rbx*2]
0x14002990d  mov     [rbp+var_58], rcx
0x140029911  mov     [rcx], r12w
0x140029915  lea     edx, [r8+1Ch]
0x140029919  lea     rcx, [rbp+var_60]
0x14002991d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140029922  test    al, al
0x140029924  jz      loc_1400299F3
0x14002992a  mov     rdx, rdi
0x14002992d  lea     rcx, [rbp+var_60]
0x140029931  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x140029936  test    al, al
0x140029938  jz      loc_1400299F3
0x14002993e  mov     edx, 3Eh ; '>'
0x140029943  lea     rcx, [rbp+var_60]
0x140029947  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002994c  test    al, al
0x14002994e  jz      loc_1400299F3
0x140029954  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140029958  inc     rbx
0x14002995b  cmp     [r14+rbx*2], r12w
0x140029960  jnz     short loc_140029958
0x140029962  mov     qword ptr [rbp+var_40], r14
0x140029966  mov     qword ptr [rbp+var_40+8], rbx
0x14002996a  xor     r8d, r8d
0x14002996d  lea     rdx, [rbp+var_40]
0x140029971  lea     rcx, [rbp+var_60]
0x140029975  call    AppendEscapedXml
0x14002997a  test    al, al
0x14002997c  jz      short loc_1400299F3
0x14002997e  mov     r8d, 2
0x140029984  lea     rdx, asc_140037994; "</"
0x14002998b  lea     rcx, [rbp+var_60]
0x14002998f  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140029994  test    al, al
0x140029996  jz      short loc_1400299F3
0x140029998  mov     rdx, rdi
0x14002999b  lea     rcx, [rbp+var_60]
0x14002999f  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1400299a4  test    al, al
0x1400299a6  jz      short loc_1400299F3
0x1400299a8  mov     r8d, 3
0x1400299ae  lea     rdx, asc_140037988; ">\r\n"
0x1400299b5  lea     rcx, [rbp+var_60]
0x1400299b9  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400299be  test    al, al
0x1400299c0  jz      short loc_1400299F3
0x1400299c2  mov     rax, [rbp+var_60]
0x1400299c6  mov     qword ptr [rbp+var_40], rax
0x1400299ca  mov     rcx, [rbp+var_58]
0x1400299ce  sub     rcx, rax
0x1400299d1  sar     rcx, 1
0x1400299d4  mov     qword ptr [rbp+var_40+8], rcx
0x1400299d8  lea     rdx, [rbp+var_40]
0x1400299dc  mov     rcx, [r15]; hFile
0x1400299df  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x1400299e4  nop
0x1400299e5  lea     rcx, [rbp+var_60]
0x1400299e9  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400299ee  jmp     loc_140029AF6
0x1400299f3  lea     rax, WPP_GLOBAL_Control
0x1400299fa  mov     ebx, 0Eh
0x1400299ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a06  cmp     rcx, rax
0x140029a09  jz      short loc_140029A30
0x140029a0b  test    dword ptr [rcx+1Ch], 400000h
0x140029a12  jz      short loc_140029A30
0x140029a14  cmp     byte ptr [rcx+19h], 2
0x140029a18  jb      short loc_140029A30
0x140029a1a  lea     edx, [rbx-3]
0x140029a1d  mov     r9d, ebx
0x140029a20  lea     r8, WPP_1c2e816ccb3d35486907a84ddef57de8_Traceguids
0x140029a27  mov     rcx, [rcx+10h]
0x140029a2b  call    WPP_SF_d
0x140029a30  mov     r9d, 93h; int
0x140029a36  mov     edx, ebx; unsigned int
0x140029a38  lea     rcx, [rbp+pExceptionObject]; this
0x140029a3c  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140029a41  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140029a48  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140029a4c  call    _CxxThrowException_0
0x140029a52  sub     r8, [rcx+8]
0x140029a56  sar     r8, 5
0x140029a5a  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[r8*2]
0x140029a62  lea     rcx, [rbp+pExceptionObject]
0x140029a66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x140029a6b  nop
0x140029a6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140029a70  mov     r8, rbx
0x140029a73  inc     r8
0x140029a76  cmp     [rdi+r8*2], r12w
0x140029a7b  jnz     short loc_140029A73
0x140029a7d  mov     rdx, rdi
0x140029a80  lea     rcx, [rbp+pExceptionObject]; Src
0x140029a84  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140029a89  mov     r8d, 2
0x140029a8f  lea     rdx, asc_140039618; ": "
0x140029a96  mov     rcx, rax; Src
0x140029a99  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140029a9e  inc     rbx
0x140029aa1  cmp     [r14+rbx*2], r12w
0x140029aa6  jnz     short loc_140029A9E
0x140029aa8  mov     r8, rbx
0x140029aab  mov     rdx, r14
0x140029aae  mov     rcx, rax; Src
0x140029ab1  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140029ab6  mov     r8d, 2
0x140029abc  lea     rdx, asc_140038FDC; "\r\n"
0x140029ac3  mov     rcx, rax; Src
0x140029ac6  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140029acb  lea     rdx, [rbp+var_60]
0x140029acf  lea     rcx, [rbp+pExceptionObject]
0x140029ad3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x140029ad8  movups  xmm0, xmmword ptr [rax]
0x140029adb  movdqu  [rbp+var_40], xmm0
0x140029ae0  lea     rdx, [rbp+var_40]
0x140029ae4  mov     rcx, [r15]; hFile
0x140029ae7  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x140029aec  nop
0x140029aed  lea     rcx, [rbp+pExceptionObject]
0x140029af1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140029af6  mov     rcx, [rbp+var_8]
0x140029afa  xor     rcx, rsp; StackCookie
0x140029afd  call    __security_check_cookie
0x140029b02  mov     rbx, [rsp+80h+arg_18]
0x140029b0a  add     rsp, 80h
0x140029b11  pop     r15
0x140029b13  pop     r14
0x140029b15  pop     r12
0x140029b17  pop     rdi
0x140029b18  pop     rbp
0x140029b19  retn
```
