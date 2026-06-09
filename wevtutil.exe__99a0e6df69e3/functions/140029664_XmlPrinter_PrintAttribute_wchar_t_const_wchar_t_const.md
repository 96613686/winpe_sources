# XmlPrinter::PrintAttribute(wchar_t const *,wchar_t const *)

- ea: `0x140029664`
- end: `0x140029875`
- name: `?PrintAttribute@XmlPrinter@@QEAAXPEB_W0@Z`
- size: `529`
- prototype: `void __fastcall(XmlPrinter *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1400217b8`

## callees

- `0x140004ae0`
- `0x140005600`
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
- `0x140029664`
- `0x14002f4a8`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall XmlPrinter::PrintAttribute(HANDLE *this, const wchar_t *a2, const wchar_t *a3)
{
  const char *v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // r8
  void *v10; // rax
  void *v11; // rax
  void *v12; // rax
  __int128 v13; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v14[4]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+50h] [rbp-30h] BYREF

  if ( *((_BYTE *)this + 32) )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v14);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v14,
                             32) )
      goto LABEL_11;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v14, a2) )
      goto LABEL_11;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v14,
                             L"=\"",
                             2) )
      goto LABEL_11;
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    *(_QWORD *)&v13 = a3;
    *((_QWORD *)&v13 + 1) = v7;
    LOBYTE(v6) = 1;
    if ( !(unsigned __int8)AppendEscapedXml(v14, &v13, v6)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v14,
                             34) )
    {
LABEL_11:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1c2e816ccb3d35486907a84ddef57de8_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v6, 78);
      throw (EvtException *)pExceptionObject;
    }
    *(_QWORD *)&v13 = v14[0];
    *((_QWORD *)&v13 + 1) = (__int64)(v14[1] - v14[0]) >> 1;
    FilePuts(*this, &v13);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v14);
  }
  else
  {
    std::wstring::wstring(pExceptionObject, 2 * (((_BYTE *)this[2] - (_BYTE *)this[1]) >> 5) - 2);
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = (void *)std::wstring::_Append<wchar_t>(pExceptionObject);
    v11 = (void *)std::wstring::_Append<wchar_t>(v10);
    do
      ++v8;
    while ( a3[v8] );
    v12 = (void *)std::wstring::_Append<wchar_t>(v11);
    std::wstring::_Append<wchar_t>(v12);
    v13 = *(_OWORD *)std::wstring::operator std::wstring_view(pExceptionObject, v14);
    FilePuts(*this, &v13);
    std::wstring::_Tidy_deallocate(pExceptionObject);
  }
}

```

## disassembly

```asm
0x140029664  push    rbp
0x140029666  push    rbx
0x140029667  push    rsi
0x140029668  push    r14
0x14002966a  push    r15
0x14002966c  mov     rbp, rsp
0x14002966f  sub     rsp, 80h
0x140029676  mov     rax, cs:__security_cookie
0x14002967d  xor     rax, rsp
0x140029680  mov     [rbp+var_8], rax
0x140029684  mov     rsi, r8
0x140029687  mov     r15, rdx
0x14002968a  mov     r14, rcx
0x14002968d  cmp     byte ptr [rcx+20h], 0
0x140029691  jz      loc_1400297B1
0x140029697  lea     rcx, [rbp+var_50]
0x14002969b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400296a0  nop
0x1400296a1  mov     edx, 20h ; ' '
0x1400296a6  lea     rcx, [rbp+var_50]
0x1400296aa  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400296af  test    al, al
0x1400296b1  jz      loc_140029752
0x1400296b7  mov     rdx, r15
0x1400296ba  lea     rcx, [rbp+var_50]
0x1400296be  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1400296c3  test    al, al
0x1400296c5  jz      loc_140029752
0x1400296cb  mov     r8d, 2
0x1400296d1  lea     rdx, asc_140039610; "=\""
0x1400296d8  lea     rcx, [rbp+var_50]
0x1400296dc  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400296e1  test    al, al
0x1400296e3  jz      short loc_140029752
0x1400296e5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400296e9  inc     rbx
0x1400296ec  cmp     word ptr [rsi+rbx*2], 0
0x1400296f1  jnz     short loc_1400296E9
0x1400296f3  mov     qword ptr [rbp+var_60], rsi
0x1400296f7  mov     qword ptr [rbp+var_60+8], rbx
0x1400296fb  mov     r8b, 1
0x1400296fe  lea     rdx, [rbp+var_60]
0x140029702  lea     rcx, [rbp+var_50]
0x140029706  call    AppendEscapedXml
0x14002970b  test    al, al
0x14002970d  jz      short loc_140029752
0x14002970f  mov     edx, 22h ; '"'
0x140029714  lea     rcx, [rbp+var_50]
0x140029718  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14002971d  test    al, al
0x14002971f  jz      short loc_140029752
0x140029721  mov     rax, [rbp+var_50]
0x140029725  mov     qword ptr [rbp+var_60], rax
0x140029729  mov     rcx, [rbp+var_48]
0x14002972d  sub     rcx, rax
0x140029730  sar     rcx, 1
0x140029733  mov     qword ptr [rbp+var_60+8], rcx
0x140029737  lea     rdx, [rbp+var_60]
0x14002973b  mov     rcx, [r14]; hFile
0x14002973e  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x140029743  nop
0x140029744  lea     rcx, [rbp+var_50]
0x140029748  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002974d  jmp     loc_14002985A
0x140029752  lea     rax, WPP_GLOBAL_Control
0x140029759  mov     ebx, 0Eh
0x14002975e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029765  cmp     rcx, rax
0x140029768  jz      short loc_14002978F
0x14002976a  test    dword ptr [rcx+1Ch], 400000h
0x140029771  jz      short loc_14002978F
0x140029773  cmp     byte ptr [rcx+19h], 2
0x140029777  jb      short loc_14002978F
0x140029779  lea     edx, [rbx-4]
0x14002977c  mov     r9d, ebx
0x14002977f  lea     r8, WPP_1c2e816ccb3d35486907a84ddef57de8_Traceguids
0x140029786  mov     rcx, [rcx+10h]
0x14002978a  call    WPP_SF_d
0x14002978f  mov     r9d, 4Eh ; 'N'; int
0x140029795  mov     edx, ebx; unsigned int
0x140029797  lea     rcx, [rbp+pExceptionObject]; this
0x14002979b  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400297a0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400297a7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400297ab  call    _CxxThrowException_0
0x1400297b1  mov     rdx, [rcx+10h]
0x1400297b5  sub     rdx, [rcx+8]
0x1400297b9  sar     rdx, 5
0x1400297bd  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x1400297c5  lea     rcx, [rbp+pExceptionObject]
0x1400297c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1400297ce  nop
0x1400297cf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400297d3  mov     r8, rbx
0x1400297d6  inc     r8
0x1400297d9  cmp     word ptr [r15+r8*2], 0
0x1400297df  jnz     short loc_1400297D6
0x1400297e1  mov     rdx, r15
0x1400297e4  lea     rcx, [rbp+pExceptionObject]; Src
0x1400297e8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400297ed  mov     r8d, 2
0x1400297f3  lea     rdx, asc_140039618; ": "
0x1400297fa  mov     rcx, rax; Src
0x1400297fd  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140029802  inc     rbx
0x140029805  cmp     word ptr [rsi+rbx*2], 0
0x14002980a  jnz     short loc_140029802
0x14002980c  mov     r8, rbx
0x14002980f  mov     rdx, rsi
0x140029812  mov     rcx, rax; Src
0x140029815  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14002981a  mov     r8d, 2
0x140029820  lea     rdx, asc_140038FDC; "\r\n"
0x140029827  mov     rcx, rax; Src
0x14002982a  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14002982f  lea     rdx, [rbp+var_50]
0x140029833  lea     rcx, [rbp+pExceptionObject]
0x140029837  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14002983c  movups  xmm0, xmmword ptr [rax]
0x14002983f  movdqu  [rbp+var_60], xmm0
0x140029844  lea     rdx, [rbp+var_60]
0x140029848  mov     rcx, [r14]; hFile
0x14002984b  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x140029850  nop
0x140029851  lea     rcx, [rbp+pExceptionObject]
0x140029855  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002985a  mov     rcx, [rbp+var_8]
0x14002985e  xor     rcx, rsp; StackCookie
0x140029861  call    __security_check_cookie
0x140029866  add     rsp, 80h
0x14002986d  pop     r15
0x14002986f  pop     r14
0x140029871  pop     rsi
0x140029872  pop     rbx
0x140029873  pop     rbp
0x140029874  retn
```
