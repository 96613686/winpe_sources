# ApplySettings::ProcessRegistryKeys(std::basic_ifstream<ushort,std::char_traits<ushort>> &)

- ea: `0x1800463e4`
- end: `0x180046675`
- name: `?ProcessRegistryKeys@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@@Z`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x18002d08c`
- `0x18002efa0`
- `0x18002f240`
- `0x1800341e8`
- `0x1800388a0`
- `0x180038ad0`
- `0x1800405a0`
- `0x180041148`
- `0x1800420f0`
- `0x180042a80`
- `0x1800463e4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180046493`
- `OLEAUT32!__imp_SysAllocString` at `0x180046493`
- `OLEAUT32!__imp_VariantInit` at `0x180046469`
- `OLEAUT32!__imp_VariantInit` at `0x180046469`

## string_xrefs

- `0x1800465e3`: `SetRegistryValue(%S\%S %S) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ApplySettings::ProcessRegistryKeys(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  _QWORD *v6; // rsi
  const OLECHAR *v7; // r14
  BSTR v8; // rax
  const unsigned __int16 *v9; // rdx
  _bstr_t *v10; // rax
  wchar_t *v11; // r12
  const unsigned __int16 *v12; // rdx
  _bstr_t *v13; // rax
  const WCHAR *v14; // r14
  const unsigned __int16 *v15; // rdx
  _bstr_t *v16; // rax
  const WCHAR *v17; // rdx
  int v18; // r12d
  unsigned int v19; // r14d
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  char v22; // [rsp+A0h] [rbp+40h] BYREF
  char v23; // [rsp+B0h] [rbp+50h] BYREF
  char v24; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a1 + 2;
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 2);
  while ( 1 )
  {
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, v4);
    if ( (unsigned __int8)std::operator==<unsigned short>(v4, L"=================================================") )
      return 0;
    v5 = a1 + 6;
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 6);
    v6 = a1 + 10;
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 10);
    v7 = (const OLECHAR *)(a1 + 14);
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, a1 + 14);
    VariantInit(&pvarg);
    if ( a1[17] >= 8u )
      v7 = *(const OLECHAR **)v7;
    _variant_t::Clear((_variant_t *)&pvarg);
    if ( v7 )
    {
      v8 = SysAllocString(v7);
      if ( !v8 )
        _com_issue_error(-2147024882);
      pvarg.llVal = (LONGLONG)v8;
    }
    else
    {
      pvarg.llVal = 0;
    }
    pvarg.vt = 8;
    v9 = a1[13] < 8u ? (const unsigned __int16 *)(a1 + 10) : (const unsigned __int16 *)*v6;
    v10 = _bstr_t::_bstr_t((_bstr_t *)&v24, v9);
    v11 = *(_QWORD *)v10 ? **(wchar_t ***)v10 : 0LL;
    v12 = a1[9] < 8u ? (const unsigned __int16 *)(a1 + 6) : (const unsigned __int16 *)*v5;
    v13 = _bstr_t::_bstr_t((_bstr_t *)&v23, v12);
    v14 = *(_QWORD *)v13 ? **(const WCHAR ***)v13 : 0LL;
    v15 = a1[5] < 8u ? (const unsigned __int16 *)v4 : (const unsigned __int16 *)*v4;
    v16 = _bstr_t::_bstr_t((_bstr_t *)&v22, v15);
    v17 = *(_QWORD *)v16 ? **(const WCHAR ***)v16 : 0LL;
    v18 = SetRegistryValue(HKEY_LOCAL_MACHINE, v17, v14, v11, (__int64)&pvarg);
    _bstr_t::_Free((_bstr_t *)&v22);
    _bstr_t::_Free((_bstr_t *)&v23);
    _bstr_t::_Free((_bstr_t *)&v24);
    if ( v18 )
      break;
    _variant_t::~_variant_t((_variant_t *)&pvarg);
  }
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  else
    v19 = v18;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("SetRegistryValue(%S\\%S %S) failed with 0x%x");
    if ( a1[13] >= 8u )
      v6 = (_QWORD *)*v6;
    if ( a1[9] >= 8u )
      v5 = (_QWORD *)*v5;
    if ( v4[3] >= 8u )
      v4 = (_QWORD *)*v4;
    WPP_SF_sSSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v4, (__int64)v5, (__int64)v6, v18);
  }
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return v19;
}

```

## disassembly

```asm
0x1800463e4  mov     [rsp-38h+arg_8], rbx
0x1800463e9  push    rbp
0x1800463ea  push    rsi
0x1800463eb  push    rdi
0x1800463ec  push    r12
0x1800463ee  push    r13
0x1800463f0  push    r14
0x1800463f2  push    r15
0x1800463f4  mov     rbp, rsp
0x1800463f7  sub     rsp, 60h
0x1800463fb  mov     r13, rdx
0x1800463fe  mov     r15, rcx
0x180046401  lea     rbx, [rcx+10h]
0x180046405  mov     rdx, rbx
0x180046408  mov     rcx, r13
0x18004640b  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046410  mov     r12d, 8
0x180046416  mov     rdx, rbx
0x180046419  mov     rcx, r13
0x18004641c  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046421  lea     rdx, asc_180066850; "======================================="...
0x180046428  mov     rcx, rbx
0x18004642b  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180046430  test    al, al
0x180046432  jnz     loc_18004665B
0x180046438  lea     rdi, [r15+30h]
0x18004643c  mov     rdx, rdi
0x18004643f  mov     rcx, r13
0x180046442  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046447  lea     rsi, [r15+50h]
0x18004644b  mov     rdx, rsi
0x18004644e  mov     rcx, r13
0x180046451  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046456  lea     r14, [r15+70h]
0x18004645a  mov     rdx, r14
0x18004645d  mov     rcx, r13
0x180046460  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180046465  lea     rcx, [rbp+pvarg]; pvarg
0x180046469  call    cs:__imp_VariantInit
0x18004646f  nop
0x180046470  cmp     [r15+88h], r12
0x180046477  jb      short loc_18004647C
0x180046479  mov     r14, [r14]
0x18004647c  lea     rcx, [rbp+pvarg]; this
0x180046480  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x180046485  test    r14, r14
0x180046488  jnz     short loc_180046490
0x18004648a  mov     qword ptr [rbp+pvarg+8], r14
0x18004648e  jmp     short loc_1800464A6
0x180046490  mov     rcx, r14; psz
0x180046493  call    cs:__imp_SysAllocString
0x180046499  test    rax, rax
0x18004649c  jz      loc_180046650
0x1800464a2  mov     qword ptr [rbp+pvarg+8], rax
0x1800464a6  mov     word ptr [rbp+pvarg], r12w
0x1800464ab  cmp     [r15+68h], r12
0x1800464af  jb      short loc_1800464B6
0x1800464b1  mov     rdx, [rsi]
0x1800464b4  jmp     short loc_1800464B9
0x1800464b6  mov     rdx, rsi; unsigned __int16 *
0x1800464b9  lea     rcx, [rbp+arg_18]; this
0x1800464bd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800464c2  nop
0x1800464c3  mov     rcx, [rax]
0x1800464c6  test    rcx, rcx
0x1800464c9  jz      short loc_1800464D0
0x1800464cb  mov     r12, [rcx]
0x1800464ce  jmp     short loc_1800464D3
0x1800464d0  xor     r12d, r12d
0x1800464d3  cmp     qword ptr [r15+48h], 8
0x1800464d8  jb      short loc_1800464DF
0x1800464da  mov     rdx, [rdi]
0x1800464dd  jmp     short loc_1800464E2
0x1800464df  mov     rdx, rdi; unsigned __int16 *
0x1800464e2  lea     rcx, [rbp+arg_10]; this
0x1800464e6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800464eb  nop
0x1800464ec  mov     rcx, [rax]
0x1800464ef  test    rcx, rcx
0x1800464f2  jz      short loc_1800464F9
0x1800464f4  mov     r14, [rcx]
0x1800464f7  jmp     short loc_1800464FC
0x1800464f9  xor     r14d, r14d
0x1800464fc  cmp     qword ptr [r15+28h], 8
0x180046501  jb      short loc_180046508
0x180046503  mov     rdx, [rbx]
0x180046506  jmp     short loc_18004650B
0x180046508  mov     rdx, rbx; unsigned __int16 *
0x18004650b  lea     rcx, [rbp+arg_0]; this
0x18004650f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180046514  mov     rcx, [rax]
0x180046517  test    rcx, rcx
0x18004651a  jz      short loc_180046521
0x18004651c  mov     rdx, [rcx]
0x18004651f  jmp     short loc_180046523
0x180046521  xor     edx, edx
0x180046523  lea     rax, [rbp+pvarg]
0x180046527  mov     [rsp+60h+var_40], rax
0x18004652c  mov     r9, r12
0x18004652f  mov     r8, r14
0x180046532  mov     rcx, 0FFFFFFFF80000002h
0x180046539  call    SetRegistryValue
0x18004653e  mov     r12d, eax
0x180046541  lea     rcx, [rbp+arg_0]; this
0x180046545  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004654a  nop
0x18004654b  lea     rcx, [rbp+arg_10]; this
0x18004654f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180046554  nop
0x180046555  lea     rcx, [rbp+arg_18]; this
0x180046559  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004655e  test    r12d, r12d
0x180046561  jnz     short loc_180046571
0x180046563  lea     rcx, [rbp+pvarg]; this
0x180046567  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004656c  jmp     loc_180046410
0x180046571  jg      short loc_180046578
0x180046573  mov     r14d, r12d
0x180046576  jmp     short loc_180046583
0x180046578  movzx   r14d, r12w
0x18004657c  or      r14d, 80070000h
0x180046583  lea     rcx, WPP_GLOBAL_Control
0x18004658a  mov     rax, cs:WPP_GLOBAL_Control
0x180046591  cmp     rax, rcx
0x180046594  jz      loc_180046642
0x18004659a  cmp     byte ptr [rax+19h], 2
0x18004659e  jb      loc_180046642
0x1800465a4  test    byte ptr [rax+1Ch], 10h
0x1800465a8  jz      loc_180046642
0x1800465ae  mov     r15d, 8
0x1800465b4  cmp     [rsi+18h], r15
0x1800465b8  jb      short loc_1800465BF
0x1800465ba  mov     r9, [rsi]
0x1800465bd  jmp     short loc_1800465C2
0x1800465bf  mov     r9, rsi
0x1800465c2  cmp     [rdi+18h], r15
0x1800465c6  jb      short loc_1800465CD
0x1800465c8  mov     r8, [rdi]
0x1800465cb  jmp     short loc_1800465D0
0x1800465cd  mov     r8, rdi
0x1800465d0  cmp     [rbx+18h], r15
0x1800465d4  jb      short loc_1800465DB
0x1800465d6  mov     rdx, [rbx]
0x1800465d9  jmp     short loc_1800465DE
0x1800465db  mov     rdx, rbx
0x1800465de  mov     dword ptr [rsp+60h+var_40], r12d
0x1800465e3  lea     rcx, aSetregistryval; "SetRegistryValue(%S\\%S %S) failed with"...
0x1800465ea  call    WppDbgPrint
0x1800465ef  cmp     [rsi+18h], r15
0x1800465f3  jb      short loc_1800465F8
0x1800465f5  mov     rsi, [rsi]
0x1800465f8  cmp     [rdi+18h], r15
0x1800465fc  jb      short loc_180046601
0x1800465fe  mov     rdi, [rdi]
0x180046601  cmp     [rbx+18h], r15
0x180046605  jb      short loc_18004660A
0x180046607  mov     rbx, [rbx]
0x18004660a  mov     edx, 40h ; '@'
0x18004660f  mov     dword ptr [rsp+60h+var_28], r12d; char
0x180046614  mov     [rsp+60h+var_30], rsi; __int64
0x180046619  mov     [rsp+60h+var_38], rdi; __int64
0x18004661e  mov     [rsp+60h+var_40], rbx; __int64
0x180046623  lea     r9, aNpsds; "NPSDS"
0x18004662a  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180046631  mov     rcx, cs:WPP_GLOBAL_Control
0x180046638  mov     rcx, [rcx+10h]; LoggerHandle
0x18004663c  call    WPP_SF_sSSSD
0x180046641  nop
0x180046642  lea     rcx, [rbp+pvarg]; this
0x180046646  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004664b  mov     eax, r14d
0x18004664e  jmp     short loc_18004665D
0x180046650  mov     ecx, 8007000Eh; int
0x180046655  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004665b  xor     eax, eax
0x18004665d  mov     rbx, [rsp+60h+arg_8]
0x180046665  add     rsp, 60h
0x180046669  pop     r15
0x18004666b  pop     r14
0x18004666d  pop     r13
0x18004666f  pop     r12
0x180046671  pop     rdi
0x180046672  pop     rsi
0x180046673  pop     rbp
0x180046674  retn
```
