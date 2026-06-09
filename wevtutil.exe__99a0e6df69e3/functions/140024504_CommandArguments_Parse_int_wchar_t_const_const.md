# CommandArguments::Parse(int,wchar_t const * * const)

- ea: `0x140024504`
- end: `0x1400247c0`
- name: `?Parse@CommandArguments@@QEAAXHQEAPEB_W@Z`
- size: `700`
- prototype: `void __fastcall(CommandArguments *__hidden this, int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400238ac`

## callees

- `0x14000cabc`
- `0x14000d8c4`
- `0x140010450`
- `0x1400163cc`
- `0x1400165d4`
- `0x14001af4c`
- `0x140021b00`
- `0x140022cec`
- `0x14002421c`
- `0x140024504`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CommandArguments::Parse(CommandArguments *this, int a2, const wchar_t **const a3)
{
  __m128i si128; // xmm6
  int i; // edi
  const wchar_t *v8; // rcx
  _OWORD *v9; // rdx
  char *v10; // rbx
  wchar_t v11; // ax
  const wchar_t *v12; // rdx
  char *v13; // rcx
  const wchar_t *Src; // rax
  char *v15; // [rsp+28h] [rbp-99h]
  char v16; // [rsp+48h] [rbp-79h] BYREF
  char v17[16]; // [rsp+50h] [rbp-71h] BYREF
  char v18[16]; // [rsp+60h] [rbp-61h] BYREF
  __int64 v19; // [rsp+70h] [rbp-51h]
  unsigned __int64 v20; // [rsp+78h] [rbp-49h]
  wchar_t *v21[2]; // [rsp+80h] [rbp-41h] BYREF
  __m128i v22; // [rsp+90h] [rbp-31h]
  __int128 pExceptionObject; // [rsp+A0h] [rbp-21h] BYREF
  __m128i v24; // [rsp+B0h] [rbp-11h]

  *(_OWORD *)v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v22 = si128;
  LOWORD(v21[0]) = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  v20 = 7;
  *(_WORD *)v18 = 0;
  v16 = 0;
  for ( i = 1; i < a2; ++i )
  {
    v8 = a3[i];
    if ( ((*v8 - 45) & 0xFFFD) != 0 )
    {
      std::wstring::wstring(&pExceptionObject, a3[i]);
      v9 = (_OWORD *)*((_QWORD *)this + 3);
      if ( v9 == *((_OWORD **)this + 4) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)this + 16, v9, &pExceptionObject);
      }
      else
      {
        *v9 = pExceptionObject;
        v9[1] = v24;
        v24 = si128;
        LOWORD(pExceptionObject) = 0;
        *((_QWORD *)this + 3) += 32LL;
      }
      std::wstring::_Tidy_deallocate(&pExceptionObject);
    }
    else
    {
      v10 = (char *)(v8 + 1);
      v11 = v8[1];
      if ( v11 == 58 )
        goto LABEL_29;
      v12 = v8 + 1;
      do
      {
        if ( !v11 )
          break;
        v10 += 2;
        v11 = *(_WORD *)v10;
      }
      while ( *(_WORD *)v10 != 58 );
      if ( v10 == (char *)v12 )
      {
LABEL_29:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
        }
        EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, v15, 32, 7u, a3[i]);
        throw (EvtException *)&pExceptionObject;
      }
      std::wstring::_Assign<wchar_t>(v21, v12, (v10 - (char *)v8 - 2) >> 1);
      v13 = v18;
      if ( *(_WORD *)v10 == 58 )
      {
        v16 = 1;
        std::wstring::assign(v18);
      }
      else
      {
        v16 = 0;
        v19 = 0;
        if ( v20 > 7 )
          v13 = *(char **)v18;
        *(_WORD *)v13 = 0;
      }
      std::map<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>>::_Try_emplace<std::wstring const &,bool &,std::wstring>(
        (_DWORD)this,
        (unsigned int)v17,
        (unsigned int)v21,
        (unsigned int)&v16,
        (__int64)v18);
      if ( !v17[8] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
        }
        Src = (const wchar_t *)v21;
        if ( v22.m128i_i64[1] > 7uLL )
          Src = v21[0];
        EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, v15, 52, 8u, Src);
        throw (EvtException *)&pExceptionObject;
      }
    }
  }
  std::wstring::_Tidy_deallocate(v18);
  std::wstring::_Tidy_deallocate(v21);
}

```

## disassembly

```asm
0x140024504  mov     rax, rsp
0x140024507  mov     [rax+10h], rbx
0x14002450b  push    rbp
0x14002450c  push    rsi
0x14002450d  push    rdi
0x14002450e  push    r12
0x140024510  push    r13
0x140024512  push    r14
0x140024514  push    r15
0x140024516  lea     rbp, [rax-5Fh]
0x14002451a  sub     rsp, 0E0h
0x140024521  movaps  xmmword ptr [rax-48h], xmm6
0x140024525  mov     rax, cs:__security_cookie
0x14002452c  xor     rax, rsp
0x14002452f  mov     [rbp+57h+var_50], rax
0x140024533  mov     r15, r8
0x140024536  mov     r12d, edx
0x140024539  mov     r14, rcx
0x14002453c  xorps   xmm0, xmm0
0x14002453f  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x140024543  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14002454b  movdqu  [rbp+57h+var_88], xmm6
0x140024550  xor     r13d, r13d
0x140024553  mov     word ptr [rbp+57h+var_98], r13w
0x140024558  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x14002455c  mov     [rbp+57h+var_A8], r13
0x140024560  mov     [rbp+57h+var_A0], 7
0x140024568  mov     word ptr [rbp+57h+var_B8], r13w
0x14002456d  mov     [rbp+57h+var_D0], r13b
0x140024571  lea     edi, [r13+1]
0x140024575  cmp     edi, r12d
0x140024578  jge     loc_140024781
0x14002457e  movsxd  rsi, edi
0x140024581  mov     rcx, [r15+rsi*8]
0x140024585  movzx   eax, word ptr [rcx]
0x140024588  sub     ax, 2Dh ; '-'
0x14002458c  mov     edx, 0FFFDh
0x140024591  test    dx, ax
0x140024594  jz      short loc_1400245E9
0x140024596  mov     rdx, rcx
0x140024599  lea     rcx, [rbp+57h+pExceptionObject]
0x14002459d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400245a2  nop
0x1400245a3  mov     rdx, [r14+18h]
0x1400245a7  cmp     rdx, [r14+20h]
0x1400245ab  jz      short loc_1400245CD
0x1400245ad  movups  xmm0, [rbp+57h+pExceptionObject]
0x1400245b1  movups  xmmword ptr [rdx], xmm0
0x1400245b4  movups  xmm1, [rbp+57h+var_68]
0x1400245b8  movups  xmmword ptr [rdx+10h], xmm1
0x1400245bc  movdqu  [rbp+57h+var_68], xmm6
0x1400245c1  mov     word ptr [rbp+57h+pExceptionObject], r13w
0x1400245c6  add     qword ptr [r14+18h], 20h ; ' '
0x1400245cb  jmp     short loc_1400245DB
0x1400245cd  lea     r8, [rbp+57h+pExceptionObject]
0x1400245d1  lea     rcx, [r14+10h]
0x1400245d5  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1400245da  nop
0x1400245db  lea     rcx, [rbp+57h+pExceptionObject]
0x1400245df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400245e4  jmp     loc_140024680
0x1400245e9  lea     rbx, [rcx+2]
0x1400245ed  movzx   eax, word ptr [rbx]
0x1400245f0  cmp     ax, 3Ah ; ':'
0x1400245f4  jz      loc_140024709
0x1400245fa  mov     rdx, rbx
0x1400245fd  test    ax, ax
0x140024600  jz      short loc_14002460F
0x140024602  add     rbx, 2
0x140024606  movzx   eax, word ptr [rbx]
0x140024609  cmp     ax, 3Ah ; ':'
0x14002460d  jnz     short loc_1400245FD
0x14002460f  cmp     rbx, rdx
0x140024612  jz      loc_140024709
0x140024618  mov     r8, rbx
0x14002461b  sub     r8, rcx
0x14002461e  sub     r8, 2
0x140024622  sar     r8, 1
0x140024625  lea     rcx, [rbp+57h+var_98]
0x140024629  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x14002462e  lea     rcx, [rbp+57h+var_B8]
0x140024632  cmp     word ptr [rbx], 3Ah ; ':'
0x140024636  jnz     short loc_140024647
0x140024638  mov     [rbp+57h+var_D0], 1
0x14002463c  lea     rdx, [rbx+2]
0x140024640  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x140024645  jmp     short loc_14002465D
0x140024647  mov     [rbp+57h+var_D0], r13b
0x14002464b  mov     [rbp+57h+var_A8], r13
0x14002464f  cmp     [rbp+57h+var_A0], 7
0x140024654  cmova   rcx, qword ptr [rbp+57h+var_B8]
0x140024659  mov     [rcx], r13w
0x14002465d  lea     rax, [rbp+57h+var_B8]
0x140024661  mov     [rsp+110h+var_F0], rax; char *
0x140024666  lea     r9, [rbp+57h+var_D0]
0x14002466a  lea     r8, [rbp+57h+var_98]
0x14002466e  lea     rdx, [rbp+57h+var_C8]
0x140024672  mov     rcx, r14
0x140024675  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NV12@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEA_N$$QEAV31@@Z; std::map<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>>::_Try_emplace<std::wstring const &,bool &,std::wstring>(std::wstring const &,bool &,std::wstring &&)
0x14002467a  cmp     [rbp+57h+var_C0], r13b
0x14002467e  jz      short loc_140024687
0x140024680  inc     edi
0x140024682  jmp     loc_140024575
0x140024687  lea     rax, WPP_GLOBAL_Control
0x14002468e  mov     ebx, 57h ; 'W'
0x140024693  mov     rcx, cs:WPP_GLOBAL_Control
0x14002469a  cmp     rcx, rax
0x14002469d  jz      short loc_1400246C4
0x14002469f  test    dword ptr [rcx+1Ch], 400000h
0x1400246a6  jz      short loc_1400246C4
0x1400246a8  cmp     byte ptr [rcx+19h], 2
0x1400246ac  jb      short loc_1400246C4
0x1400246ae  lea     edx, [rbx-4Ch]
0x1400246b1  mov     r9d, ebx
0x1400246b4  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x1400246bb  mov     rcx, [rcx+10h]
0x1400246bf  call    WPP_SF_d
0x1400246c4  lea     rax, [rbp+57h+var_98]
0x1400246c8  cmp     qword ptr [rbp+57h+var_88+8], 7
0x1400246cd  cmova   rax, [rbp+57h+var_98]
0x1400246d2  mov     [rsp+110h+Src], rax; Src
0x1400246d7  mov     [rsp+110h+var_E0], 8; unsigned int
0x1400246df  mov     [rsp+110h+var_E8], 34h ; '4'; int
0x1400246e7  xor     r9d, r9d; unsigned int
0x1400246ea  xor     r8d, r8d; unsigned int
0x1400246ed  mov     edx, ebx; unsigned int
0x1400246ef  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400246f3  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400246f8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400246ff  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140024703  call    _CxxThrowException_0
0x140024709  lea     rax, WPP_GLOBAL_Control
0x140024710  mov     ebx, 57h ; 'W'
0x140024715  mov     rcx, cs:WPP_GLOBAL_Control
0x14002471c  cmp     rcx, rax
0x14002471f  jz      short loc_140024746
0x140024721  test    dword ptr [rcx+1Ch], 400000h
0x140024728  jz      short loc_140024746
0x14002472a  cmp     byte ptr [rcx+19h], 2
0x14002472e  jb      short loc_140024746
0x140024730  lea     edx, [rbx-4Dh]
0x140024733  mov     r9d, ebx
0x140024736  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14002473d  mov     rcx, [rcx+10h]
0x140024741  call    WPP_SF_d
0x140024746  mov     rax, [r15+rsi*8]
0x14002474a  mov     [rsp+110h+Src], rax; Src
0x14002474f  mov     [rsp+110h+var_E0], 7; unsigned int
0x140024757  mov     [rsp+110h+var_E8], 20h ; ' '; int
0x14002475f  xor     r9d, r9d; unsigned int
0x140024762  xor     r8d, r8d; unsigned int
0x140024765  mov     edx, ebx; unsigned int
0x140024767  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14002476b  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140024770  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140024777  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14002477b  call    _CxxThrowException_0
0x140024781  lea     rcx, [rbp+57h+var_B8]
0x140024785  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002478a  nop
0x14002478b  lea     rcx, [rbp+57h+var_98]
0x14002478f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140024794  mov     rcx, [rbp+57h+var_50]
0x140024798  xor     rcx, rsp; StackCookie
0x14002479b  call    __security_check_cookie
0x1400247a0  lea     r11, [rsp+110h+var_30]
0x1400247a8  mov     rbx, [r11+48h]
0x1400247ac  movaps  xmm6, xmmword ptr [r11-10h]
0x1400247b1  mov     rsp, r11
0x1400247b4  pop     r15
0x1400247b6  pop     r14
0x1400247b8  pop     r13
0x1400247ba  pop     r12
0x1400247bc  pop     rdi
0x1400247bd  pop     rsi
0x1400247be  pop     rbp
0x1400247bf  retn
```
