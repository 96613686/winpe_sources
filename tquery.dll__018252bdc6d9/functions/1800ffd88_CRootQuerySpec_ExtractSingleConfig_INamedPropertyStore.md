# CRootQuerySpec::ExtractSingleConfig(INamedPropertyStore *)

- ea: `0x1800ffd88`
- end: `0x18010010a`
- name: `?ExtractSingleConfig@CRootQuerySpec@@AEAAXPEAUINamedPropertyStore@@@Z`
- size: `898`
- prototype: `void __fastcall(CRootQuerySpec *__hidden this, struct INamedPropertyStore *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ff9cc`
- `0x1800ffc8c`

## callees

- `0x180038f08`
- `0x18006380c`
- `0x18008b084`
- `0x18008facc`
- `0x1800ffd88`
- `0x1801124b0`
- `0x18015e264`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ffe3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ffe95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800fff08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800fff74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800fffca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180100023`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801000d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801000e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ffe3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ffe95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800fff08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800fff74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800fffca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180100023`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801000d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801000e1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18010004b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18010004b`

## string_xrefs

- `0x1800ffdee`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800ffe17`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800ffe68`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800ffec0`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800fff46`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800fff9f`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800ffff5`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x18010007e`: `onecoreuap\base\appmodel\search\tquery\icommand\qryspec.cxx`
- `0x1800fff81`: `DoNotComputeExpensiveProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRootQuerySpec::ExtractSingleConfig(CRootQuerySpec *this, struct INamedPropertyStore *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  char *v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  char v11; // al
  int v12; // eax
  unsigned int i; // edi
  int v14; // [rsp+20h] [rbp-60h]
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+40h] [rbp-40h]
  PROPVARIANT *v17; // [rsp+48h] [rbp-38h]
  _BYTE v18[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *(_OWORD *)pvar = 0;
  v16 = 0;
  v17 = pvar;
  v4 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
         a2,
         L"MachineName",
         pvar);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x763,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v4,
      v14);
  if ( LOWORD(pvar[0]) != 31 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x767,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)0x80070057LL,
      v14);
  CLMString::operator=((char *)this + 224, pvar[1]);
  PropVariantClear(pvar);
  v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
         a2,
         L"Scope",
         pvar);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x774,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v5,
      v14);
  if ( LOWORD(pvar[0]) == 31 )
    CLMString::operator=((char *)this + 664, pvar[1]);
  PropVariantClear(pvar);
  v6 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
         a2,
         L"Catalog",
         pvar);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x77F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v6,
      v14);
  v7 = (char *)this + 320;
  if ( LOWORD(pvar[0]) )
    CLMString::operator=(v7, pvar[1]);
  else
    (*(void (__fastcall **)(char *, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v7 + 32LL))(
      v7,
      L"SystemIndex",
      0,
      0xFFFFFFFFLL);
  PropVariantClear(pvar);
  if ( *((_DWORD *)this + 701) != 1 )
  {
    v8 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
           a2,
           L"SkipInternalReuse",
           pvar);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x793,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)(unsigned int)v8,
        v14);
    if ( LOWORD(pvar[0]) == 11 && LOWORD(pvar[1]) == 0xFFFF )
      *((_DWORD *)this + 701) = 1;
    PropVariantClear(pvar);
  }
  v9 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
         a2,
         L"DoNotComputeExpensiveProperties",
         pvar);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v9,
      v14);
  if ( LOWORD(pvar[0]) == 11 )
    *((_BYTE *)this + 2800) = LOWORD(pvar[1]) == 0xFFFF;
  PropVariantClear(pvar);
  v10 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
          a2,
          L"WinRTDataModel",
          pvar);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7A6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
      (const char *)(unsigned int)v10,
      v14);
  if ( LOWORD(pvar[0]) != 11 || (v11 = 1, !LOWORD(pvar[1])) )
    v11 = 0;
  *((_BYTE *)this + 2801) = v11;
  PropVariantClear(pvar);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
    && !lstrcmpW(*((LPCWSTR *)this + 29), L".") )
  {
    v12 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
            a2,
            L"ExternalResultSetList",
            pvar);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B6,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\qryspec.cxx",
        (const char *)(unsigned int)v12,
        v14);
    if ( LOWORD(pvar[0]) )
    {
      for ( i = 0; i < LODWORD(pvar[1]); ++i )
      {
        std::wstring::wstring(v18);
        std::vector<std::wstring>::push_back((char *)this + 2808, v18);
        std::wstring::_Tidy_deallocate(v18);
      }
    }
    PropVariantClear(pvar);
  }
  PropVariantClear(pvar);
}

```

## disassembly

```asm
0x1800ffd88  mov     [rsp-28h+arg_10], rbx
0x1800ffd8d  push    rbp
0x1800ffd8e  push    rsi
0x1800ffd8f  push    rdi
0x1800ffd90  push    r14
0x1800ffd92  push    r15
0x1800ffd94  mov     rbp, rsp
0x1800ffd97  sub     rsp, 80h
0x1800ffd9e  mov     rax, cs:__security_cookie
0x1800ffda5  xor     rax, rsp
0x1800ffda8  mov     [rbp+var_10], rax
0x1800ffdac  mov     rdi, rdx
0x1800ffdaf  mov     rbx, rcx
0x1800ffdb2  xorps   xmm0, xmm0
0x1800ffdb5  xor     eax, eax
0x1800ffdb7  movups  xmmword ptr [rbp+pvar], xmm0
0x1800ffdbb  mov     [rbp+var_40], rax
0x1800ffdbf  lea     rax, [rbp+pvar]
0x1800ffdc3  mov     [rbp+var_38], rax
0x1800ffdc7  mov     rax, [rdx]
0x1800ffdca  lea     r8, [rbp+pvar]
0x1800ffdce  lea     rdx, aMachinename; "MachineName"
0x1800ffdd5  mov     rcx, rdi
0x1800ffdd8  mov     rax, [rax+18h]
0x1800ffddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffde1  mov     rcx, [rbp+28h]; this
0x1800ffde5  xor     esi, esi
0x1800ffde7  test    eax, eax
0x1800ffde9  jns     short loc_1800FFE00
0x1800ffdeb  mov     r9d, eax; char *
0x1800ffdee  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800ffdf5  mov     edx, 763h; void *
0x1800ffdfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ffe00  mov     r14d, 1Fh
0x1800ffe06  cmp     r14w, word ptr [rbp+pvar]
0x1800ffe0b  jz      short loc_1800FFE29
0x1800ffe0d  mov     rcx, [rbp+28h]; this
0x1800ffe11  mov     r9d, 80070057h; char *
0x1800ffe17  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800ffe1e  mov     edx, 767h; void *
0x1800ffe23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ffe29  lea     rcx, [rbx+0E0h]
0x1800ffe30  mov     rdx, [rbp+pvar+8]
0x1800ffe34  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800ffe39  lea     rcx, [rbp+pvar]; pvar
0x1800ffe3d  call    cs:__imp_PropVariantClear
0x1800ffe43  mov     rax, [rdi]
0x1800ffe46  lea     r8, [rbp+pvar]
0x1800ffe4a  lea     rdx, aScope_0; "Scope"
0x1800ffe51  mov     rcx, rdi
0x1800ffe54  mov     rax, [rax+18h]
0x1800ffe58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffe5d  mov     rcx, [rbp+28h]; this
0x1800ffe61  test    eax, eax
0x1800ffe63  jns     short loc_1800FFE7A
0x1800ffe65  mov     r9d, eax; char *
0x1800ffe68  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800ffe6f  mov     edx, 774h; void *
0x1800ffe74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ffe7a  cmp     word ptr [rbp+pvar], r14w
0x1800ffe7f  jnz     short loc_1800FFE91
0x1800ffe81  lea     rcx, [rbx+298h]
0x1800ffe88  mov     rdx, [rbp+pvar+8]
0x1800ffe8c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800ffe91  lea     rcx, [rbp+pvar]; pvar
0x1800ffe95  call    cs:__imp_PropVariantClear
0x1800ffe9b  mov     rax, [rdi]
0x1800ffe9e  lea     r8, [rbp+pvar]
0x1800ffea2  lea     rdx, aCatalog_0; "Catalog"
0x1800ffea9  mov     rcx, rdi
0x1800ffeac  mov     rax, [rax+18h]
0x1800ffeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffeb5  mov     rcx, [rbp+28h]; this
0x1800ffeb9  test    eax, eax
0x1800ffebb  jns     short loc_1800FFED2
0x1800ffebd  mov     r9d, eax; char *
0x1800ffec0  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800ffec7  mov     edx, 77Fh; void *
0x1800ffecc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ffed2  lea     rcx, [rbx+140h]
0x1800ffed9  cmp     si, word ptr [rbp+pvar]
0x1800ffedd  jnz     short loc_1800FFEFB
0x1800ffedf  mov     rax, [rcx]
0x1800ffee2  or      r9d, 0FFFFFFFFh
0x1800ffee6  xor     r8d, r8d
0x1800ffee9  lea     rdx, aSystemindex; "SystemIndex"
0x1800ffef0  mov     rax, [rax+20h]
0x1800ffef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffef9  jmp     short loc_1800FFF04
0x1800ffefb  mov     rdx, [rbp+pvar+8]
0x1800ffeff  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800fff04  lea     rcx, [rbp+pvar]; pvar
0x1800fff08  call    cs:__imp_PropVariantClear
0x1800fff0e  mov     r14d, 0Bh
0x1800fff14  or      r15d, 0FFFFFFFFh
0x1800fff18  cmp     dword ptr [rbx+0AF4h], 1
0x1800fff1f  jz      short loc_1800FFF7A
0x1800fff21  mov     rax, [rdi]
0x1800fff24  lea     r8, [rbp+pvar]
0x1800fff28  lea     rdx, aSkipinternalre; "SkipInternalReuse"
0x1800fff2f  mov     rcx, rdi
0x1800fff32  mov     rax, [rax+18h]
0x1800fff36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff3b  mov     rcx, [rbp+28h]; this
0x1800fff3f  test    eax, eax
0x1800fff41  jns     short loc_1800FFF58
0x1800fff43  mov     r9d, eax; char *
0x1800fff46  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800fff4d  mov     edx, 793h; void *
0x1800fff52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fff58  cmp     r14w, word ptr [rbp+pvar]
0x1800fff5d  jnz     short loc_1800FFF70
0x1800fff5f  cmp     r15w, word ptr [rbp+pvar+8]
0x1800fff64  jnz     short loc_1800FFF70
0x1800fff66  mov     dword ptr [rbx+0AF4h], 1
0x1800fff70  lea     rcx, [rbp+pvar]; pvar
0x1800fff74  call    cs:__imp_PropVariantClear
0x1800fff7a  mov     rax, [rdi]
0x1800fff7d  lea     r8, [rbp+pvar]
0x1800fff81  lea     rdx, aDonotcomputeex; "DoNotComputeExpensiveProperties"
0x1800fff88  mov     rcx, rdi
0x1800fff8b  mov     rax, [rax+18h]
0x1800fff8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff94  mov     rcx, [rbp+28h]; this
0x1800fff98  test    eax, eax
0x1800fff9a  jns     short loc_1800FFFB1
0x1800fff9c  mov     r9d, eax; char *
0x1800fff9f  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800fffa6  mov     edx, 79Fh; void *
0x1800fffab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fffb1  cmp     r14w, word ptr [rbp+pvar]
0x1800fffb6  jnz     short loc_1800FFFC6
0x1800fffb8  cmp     word ptr [rbp+pvar+8], r15w
0x1800fffbd  setz    al
0x1800fffc0  mov     [rbx+0AF0h], al
0x1800fffc6  lea     rcx, [rbp+pvar]; pvar
0x1800fffca  call    cs:__imp_PropVariantClear
0x1800fffd0  mov     rax, [rdi]
0x1800fffd3  lea     r8, [rbp+pvar]
0x1800fffd7  lea     rdx, aWinrtdatamodel; "WinRTDataModel"
0x1800fffde  mov     rcx, rdi
0x1800fffe1  mov     rax, [rax+18h]
0x1800fffe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fffea  mov     rcx, [rbp+28h]; this
0x1800fffee  test    eax, eax
0x1800ffff0  jns     short loc_180100007
0x1800ffff2  mov     r9d, eax; char *
0x1800ffff5  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800ffffc  mov     edx, 7A6h; void *
0x180100001  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100007  cmp     word ptr [rbp+pvar], r14w
0x18010000c  jnz     short loc_180100016
0x18010000e  cmp     word ptr [rbp+pvar+8], si
0x180100012  mov     al, 1
0x180100014  jnz     short loc_180100019
0x180100016  mov     al, sil
0x180100019  mov     [rbx+0AF1h], al
0x18010001f  lea     rcx, [rbp+pvar]; pvar
0x180100023  call    cs:__imp_PropVariantClear
0x180100029  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x180100030  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x180100035  test    al, al
0x180100037  jz      loc_1801000DD
0x18010003d  lea     rdx, asc_1802EC9B0; "."
0x180100044  mov     rcx, [rbx+0E8h]; lpString1
0x18010004b  call    cs:__imp_lstrcmpW
0x180100051  test    eax, eax
0x180100053  jnz     loc_1801000DD
0x180100059  mov     rax, [rdi]
0x18010005c  lea     r8, [rbp+pvar]
0x180100060  lea     rdx, aExternalresult_0; "ExternalResultSetList"
0x180100067  mov     rcx, rdi
0x18010006a  mov     rax, [rax+18h]
0x18010006e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100073  mov     rcx, [rbp+28h]; this
0x180100077  test    eax, eax
0x180100079  jns     short loc_180100090
0x18010007b  mov     r9d, eax; char *
0x18010007e  lea     r8, aOnecoreuapBase_232; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180100085  mov     edx, 7B6h; void *
0x18010008a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180100090  cmp     si, word ptr [rbp+pvar]
0x180100094  jz      short loc_1801000D2
0x180100096  mov     edi, esi
0x180100098  cmp     dword ptr [rbp+pvar+8], esi
0x18010009b  jbe     short loc_1801000D2
0x18010009d  mov     eax, edi
0x18010009f  mov     rdx, [rbp+var_40]
0x1801000a3  mov     rdx, [rdx+rax*8]
0x1801000a7  lea     rcx, [rbp+var_30]
0x1801000ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801000b0  nop
0x1801000b1  lea     rdx, [rbp+var_30]
0x1801000b5  lea     rcx, [rbx+0AF8h]
0x1801000bc  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1801000c1  nop
0x1801000c2  lea     rcx, [rbp+var_30]
0x1801000c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801000cb  inc     edi
0x1801000cd  cmp     edi, dword ptr [rbp+pvar+8]
0x1801000d0  jb      short loc_18010009D
0x1801000d2  lea     rcx, [rbp+pvar]; pvar
0x1801000d6  call    cs:__imp_PropVariantClear
0x1801000dc  nop
0x1801000dd  lea     rcx, [rbp+pvar]; pvar
0x1801000e1  call    cs:__imp_PropVariantClear
0x1801000e7  mov     rcx, [rbp+var_10]
0x1801000eb  xor     rcx, rsp; StackCookie
0x1801000ee  call    __security_check_cookie
0x1801000f3  mov     rbx, [rsp+80h+arg_10]
0x1801000fb  add     rsp, 80h
0x180100102  pop     r15
0x180100104  pop     r14
0x180100106  pop     rdi
0x180100107  pop     rsi
0x180100108  pop     rbp
0x180100109  retn
```
