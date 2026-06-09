# WmiVariantChangeType(tagVARIANT &,tagVARIANT *,long)

- ea: `0x1800265f0`
- end: `0x180026a03`
- name: `?WmiVariantChangeType@@YAJAEAUtagVARIANT@@PEAU1@J@Z`
- size: `1043`
- prototype: `__int64 __fastcall(struct tagVARIANT *, VARIANTARG *pvarSrc, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018ee0`
- `0x180026120`
- `0x18002641c`

## callees

- `0x180002ef4`
- `0x18000c0b0`
- `0x180019114`
- `0x180026120`
- `0x18002641c`
- `0x1800265f0`
- `0x18003403b`
- `0x180034047`
- `0x180036010`

## import_xrefs

- `msvcrt!mbstowcs` at `0x1800268ac`
- `msvcrt!mbstowcs` at `0x1800268ac`
- `msvcrt!_fcvt` at `0x180026831`
- `msvcrt!_fcvt` at `0x180026831`
- `OLEAUT32!__imp_SysAllocString` at `0x1800268bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800268bb`
- `OLEAUT32!__imp_VariantInit` at `0x180026613`
- `OLEAUT32!__imp_VariantInit` at `0x180026613`
- `OLEAUT32!__imp_VariantCopy` at `0x1800266b4`
- `OLEAUT32!__imp_VariantCopy` at `0x180026793`
- `OLEAUT32!__imp_VariantCopy` at `0x1800266b4`
- `OLEAUT32!__imp_VariantCopy` at `0x180026793`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002677d`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800268e6`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002695f`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800269a7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002677d`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800268e6`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002695f`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800269a7`
- `OLEAUT32!__imp_VarUI4FromR8` at `0x180026938`
- `OLEAUT32!__imp_VarUI4FromR8` at `0x180026938`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002687f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002687f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800268cd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800268cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WmiVariantChangeType(struct tagVARIANT *a1, VARIANTARG *pvarSrc, int a3)
{
  unsigned int vt; // ebp
  VARTYPE v7; // ax
  struct tagSAFEARRAY **v8; // r9
  HRESULT v9; // edi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rcx
  LONGLONG llVal; // rcx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  double dblVal; // xmm7_8
  double v23; // xmm0_8
  char *v24; // rax
  const char *v25; // rbp
  size_t v26; // rbx
  OLECHAR *v27; // rax
  OLECHAR *v28; // rdi
  wchar_t *v29; // rcx
  double v30; // xmm6_8
  int v31; // ebx
  int v32; // ecx
  LONGLONG PtSign; // [rsp+78h] [rbp+10h] BYREF
  int PtDec; // [rsp+88h] [rbp+20h] BYREF

  VariantInit(a1);
  if ( !pvarSrc || (vt = pvarSrc->vt, (unsigned __int16)vt < 2u) || (_WORD)vt == 10 && pvarSrc->lVal == -2147352572 )
  {
    *(_OWORD *)&a1->vt = 0;
    a1->pRecInfo = 0;
    a1->vt = 1;
    return 0;
  }
  v7 = CimTypeToVtType(a3);
  if ( v7 == (_WORD)vt )
    return (unsigned int)VariantCopy(a1, pvarSrc);
  v9 = -2147217403;
  if ( (a3 & 0x2000) != 0 )
  {
    if ( (_WORD)vt != 8204 )
    {
      if ( (_WORD)vt != 24588 )
      {
        if ( (((_WORD)vt - 9) & 0xBFFF) == 0 )
        {
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarSrc->llVal;
          if ( (vt & 0x4000) != 0 )
            p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
          llVal = p_llVal->llVal;
          PtSign = llVal;
          if ( llVal )
            (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 8LL))(llVal);
          v9 = WmiConvertDispatchArray(a1, &PtSign, a3 & 0xFFFFDFFF);
          ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&PtSign);
          return (unsigned int)v9;
        }
        if ( (((_WORD)vt - 8201) & 0xBFFF) != 0 )
          return (unsigned int)v9;
        goto LABEL_11;
      }
      v8 = (struct tagSAFEARRAY **)*v8;
    }
    return (unsigned int)WmiConvertSafeArray(a1, *v8, a3 & 0xFFFFDFFF);
  }
  if ( a3 > 101 )
  {
    v31 = a3 - 102;
    if ( v31 )
    {
      if ( v31 != 1 )
        return (unsigned int)v9;
LABEL_63:
      v9 = VariantChangeType(a1, pvarSrc, 0, v7);
      if ( v9 >= 0 )
      {
        if ( (unsigned __int16)vt <= 0x11u )
        {
          v32 = 133124;
          if ( _bittest(&v32, vt) )
            WORD1(a1->decVal.Lo64) = 0;
        }
        return (unsigned int)v9;
      }
      return (unsigned int)VariantCopy(a1, pvarSrc);
    }
LABEL_30:
    v9 = VariantChangeType(a1, pvarSrc, 0, v7);
    if ( v9 >= 0 )
      return (unsigned int)v9;
    return (unsigned int)VariantCopy(a1, pvarSrc);
  }
  if ( a3 == 101 )
    goto LABEL_30;
  if ( a3 > 13 )
  {
    v18 = a3 - 16;
    if ( !v18 )
    {
      v9 = VariantChangeType(a1, pvarSrc, 0, v7);
      if ( v9 >= 0 )
      {
        if ( (_WORD)vt == 17 || (_WORD)vt == 11 )
          a1->lVal = (unsigned __int8)a1->lVal;
        return (unsigned int)v9;
      }
      return (unsigned int)VariantCopy(a1, pvarSrc);
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( !v21 )
        {
          v9 = VariantChangeType(a1, pvarSrc, 0, v7);
          if ( v9 >= 0 )
            return (unsigned int)v9;
          if ( pvarSrc->vt == 5 )
          {
            v30 = floor_0(pvarSrc->dblVal);
            if ( v30 == ceil_0(pvarSrc->dblVal) )
            {
              v9 = VarUI4FromR8(pvarSrc->dblVal, (ULONG *)&a1->cyVal);
              if ( v9 >= 0 )
              {
                a1->vt = 3;
                return (unsigned int)v9;
              }
            }
          }
          return (unsigned int)VariantCopy(a1, pvarSrc);
        }
        if ( (unsigned int)(v21 - 1) > 1 )
          return (unsigned int)v9;
        if ( (_WORD)vt != 5 )
          goto LABEL_30;
        a1->vt = 5;
        dblVal = pvarSrc->dblVal;
        if ( dblVal + 0.5 <= ceil_0(dblVal) )
          dblVal = dblVal - 0.5;
        v23 = ceil_0(dblVal);
        a1->dblVal = v23;
        PtDec = 0;
        LODWORD(PtSign) = 0;
        v24 = _fcvt(v23, 0, &PtDec, (int *)&PtSign);
        v25 = v24;
        if ( !v24 )
          return (unsigned int)VariantCopy(a1, pvarSrc);
        v26 = -1;
        do
          ++v26;
        while ( v24[v26] );
        if ( PtDec != v26 )
          return (unsigned int)VariantCopy(a1, pvarSrc);
        if ( (_DWORD)PtSign )
          ++v26;
        v27 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v26 + 1, 2u));
        v28 = v27;
        if ( !v27 )
          return (unsigned int)VariantCopy(a1, pvarSrc);
        if ( (_DWORD)PtSign )
        {
          *v27 = 45;
          v29 = v27 + 1;
        }
        else
        {
          v29 = v27;
        }
        mbstowcs(v29, v25, v26);
        v28[v26] = 0;
        a1->llVal = (LONGLONG)SysAllocString(v28);
        a1->vt = 8;
        CWin32DefaultArena::WbemMemFree(v28);
        return 0;
      }
      goto LABEL_63;
    }
    goto LABEL_30;
  }
  if ( a3 != 13 )
  {
    v13 = a3 - 2;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 3;
            if ( v17 )
            {
              if ( v17 != 3 )
                return (unsigned int)v9;
            }
          }
        }
      }
    }
    goto LABEL_30;
  }
LABEL_11:
  v9 = VariantCopy(a1, pvarSrc);
  if ( v9 >= 0 )
    return (unsigned int)MapToCIMOMObject(a1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800265f0  mov     [rsp+arg_0], rbx
0x1800265f5  push    rbp
0x1800265f6  push    rsi
0x1800265f7  push    rdi
0x1800265f8  push    r12
0x1800265fa  push    r14
0x1800265fc  sub     rsp, 40h
0x180026600  movaps  [rsp+68h+var_38], xmm6
0x180026605  movaps  [rsp+68h+var_48], xmm7
0x18002660a  mov     ebx, r8d
0x18002660d  mov     r14, rdx
0x180026610  mov     rsi, rcx
0x180026613  call    cs:__imp_VariantInit
0x180026619  test    r14, r14
0x18002661c  jz      loc_1800269D3
0x180026622  movzx   ebp, word ptr [r14]
0x180026626  mov     r12d, 2
0x18002662c  cmp     bp, r12w
0x180026630  jb      loc_1800269D3
0x180026636  lea     eax, [r12+8]
0x18002663b  lea     r9, [r14+8]
0x18002663f  cmp     ax, bp
0x180026642  jnz     short loc_180026651
0x180026644  cmp     dword ptr [r9], 80020004h
0x18002664b  jz      loc_1800269D3
0x180026651  mov     ecx, ebx; int
0x180026653  call    ?CimTypeToVtType@@YAGJ@Z; CimTypeToVtType(long)
0x180026658  movzx   r10d, ax
0x18002665c  cmp     ax, bp
0x18002665f  jz      loc_18002678D
0x180026665  mov     edi, 80041005h
0x18002666a  bt      ebx, 0Dh
0x18002666e  jnb     loc_180026735
0x180026674  mov     eax, 200Ch
0x180026679  cmp     ax, bp
0x18002667c  jz      loc_180026721
0x180026682  mov     eax, 600Ch
0x180026687  cmp     ax, bp
0x18002668a  jz      loc_18002671E
0x180026690  lea     eax, [rbp-9]
0x180026693  mov     ecx, 0BFFFh
0x180026698  test    cx, ax
0x18002669b  jz      short loc_1800266D1
0x18002669d  mov     eax, 2009h
0x1800266a2  sub     bp, ax
0x1800266a5  test    cx, bp
0x1800266a8  jnz     loc_1800269E6
0x1800266ae  mov     rdx, r14; pvargSrc
0x1800266b1  mov     rcx, rsi; pvargDest
0x1800266b4  call    cs:__imp_VariantCopy
0x1800266ba  mov     edi, eax
0x1800266bc  test    eax, eax
0x1800266be  js      loc_1800269E6
0x1800266c4  mov     rcx, rsi; struct tagVARIANT *
0x1800266c7  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x1800266cc  jmp     loc_180026799
0x1800266d1  lea     rcx, [r14+8]
0x1800266d5  bt      bp, 0Eh
0x1800266da  jnb     short loc_1800266DF
0x1800266dc  mov     rcx, [rcx]
0x1800266df  mov     rcx, [rcx]
0x1800266e2  mov     [rsp+68h+PtSign], rcx
0x1800266e7  test    rcx, rcx
0x1800266ea  jz      short loc_1800266F9
0x1800266ec  mov     rax, [rcx]
0x1800266ef  mov     rax, [rax+8]
0x1800266f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266f8  nop
0x1800266f9  btr     ebx, 0Dh
0x1800266fd  mov     r8d, ebx
0x180026700  lea     rdx, [rsp+68h+PtSign]
0x180026705  mov     rcx, rsi
0x180026708  call    ?WmiConvertDispatchArray@@YAJAEAUtagVARIANT@@AEAV?$CComPtr@UIDispatch@@@ATL@@J@Z; WmiConvertDispatchArray(tagVARIANT &,ATL::CComPtr<IDispatch> &,long)
0x18002670d  mov     edi, eax
0x18002670f  lea     rcx, [rsp+68h+PtSign]
0x180026714  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180026719  jmp     loc_1800269E6
0x18002671e  mov     r9, [r9]
0x180026721  btr     ebx, 0Dh
0x180026725  mov     r8d, ebx; int
0x180026728  mov     rdx, [r9]; struct tagSAFEARRAY *
0x18002672b  mov     rcx, rsi; struct tagVARIANT *
0x18002672e  call    ?WmiConvertSafeArray@@YAJAEAUtagVARIANT@@PEAUtagSAFEARRAY@@J@Z; WmiConvertSafeArray(tagVARIANT &,tagSAFEARRAY *,long)
0x180026733  jmp     short loc_180026799
0x180026735  cmp     ebx, 65h ; 'e'
0x180026738  jg      loc_18002698C
0x18002673e  jz      short loc_180026770
0x180026740  cmp     ebx, 0Dh
0x180026743  jg      short loc_1800267A0
0x180026745  jz      loc_1800266AE
0x18002674b  sub     ebx, r12d
0x18002674e  jz      short loc_180026770
0x180026750  sub     ebx, 1
0x180026753  jz      short loc_180026770
0x180026755  sub     ebx, 1
0x180026758  jz      short loc_180026770
0x18002675a  sub     ebx, 1
0x18002675d  jz      short loc_180026770
0x18002675f  mov     eax, 3
0x180026764  sub     ebx, eax
0x180026766  jz      short loc_180026770
0x180026768  cmp     ebx, eax
0x18002676a  jnz     loc_1800269E6
0x180026770  xor     r8d, r8d; wFlags
0x180026773  movzx   r9d, r10w; vt
0x180026777  mov     rdx, r14; pvarSrc
0x18002677a  mov     rcx, rsi; pvargDest
0x18002677d  call    cs:__imp_VariantChangeType
0x180026783  mov     edi, eax
0x180026785  test    eax, eax
0x180026787  jns     loc_1800269E6
0x18002678d  mov     rdx, r14; pvargSrc
0x180026790  mov     rcx, rsi; pvargDest
0x180026793  call    cs:__imp_VariantCopy
0x180026799  mov     edi, eax
0x18002679b  jmp     loc_1800269E6
0x1800267a0  sub     ebx, 10h
0x1800267a3  jz      loc_180026952
0x1800267a9  sub     ebx, 1
0x1800267ac  jz      short loc_180026770
0x1800267ae  sub     ebx, 1
0x1800267b1  jz      loc_18002699A
0x1800267b7  sub     ebx, 1
0x1800267ba  jz      loc_1800268D9
0x1800267c0  sub     ebx, 1
0x1800267c3  jz      short loc_1800267CE
0x1800267c5  cmp     ebx, 1
0x1800267c8  jnz     loc_1800269E6
0x1800267ce  mov     eax, 5
0x1800267d3  cmp     ax, bp
0x1800267d6  jnz     short loc_180026770
0x1800267d8  mov     [rsi], ax
0x1800267db  movsd   xmm7, qword ptr [r14+8]
0x1800267e1  movaps  xmm6, xmm7
0x1800267e4  addsd   xmm6, cs:__real@3fe0000000000000
0x1800267ec  movaps  xmm0, xmm7; X
0x1800267ef  call    ceil_0
0x1800267f4  comisd  xmm6, xmm0
0x1800267f8  ja      short loc_180026802
0x1800267fa  subsd   xmm7, cs:__real@3fe0000000000000
0x180026802  movaps  xmm0, xmm7; X
0x180026805  call    ceil_0
0x18002680a  movsd   qword ptr [rsi+8], xmm0
0x18002680f  mov     [rsp+68h+PtDec], 0
0x18002681a  mov     dword ptr [rsp+68h+PtSign], 0
0x180026822  lea     r9, [rsp+68h+PtSign]; PtSign
0x180026827  lea     r8, [rsp+68h+PtDec]; PtDec
0x18002682f  xor     edx, edx; FractionalDigitCount
0x180026831  call    cs:__imp__fcvt
0x180026837  mov     rbp, rax
0x18002683a  test    rax, rax
0x18002683d  jz      loc_18002678D
0x180026843  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026847  mov     rbx, r8
0x18002684a  inc     rbx
0x18002684d  cmp     byte ptr [rbx+rax], 0
0x180026851  jnz     short loc_18002684A
0x180026853  movsxd  rax, [rsp+68h+PtDec]
0x18002685b  cmp     rax, rbx
0x18002685e  jnz     loc_18002678D
0x180026864  cmp     dword ptr [rsp+68h+PtSign], 0
0x180026869  jz      short loc_18002686E
0x18002686b  inc     rbx
0x18002686e  lea     rcx, [rbx+1]
0x180026872  mov     rax, r12
0x180026875  mul     rcx
0x180026878  cmovb   rax, r8
0x18002687c  mov     rcx, rax
0x18002687f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180026885  mov     rdi, rax
0x180026888  test    rax, rax
0x18002688b  jz      loc_18002678D
0x180026891  mov     r8, rbx; MaxCount
0x180026894  mov     rdx, rbp; Source
0x180026897  cmp     dword ptr [rsp+68h+PtSign], 0
0x18002689c  jz      short loc_1800268A9
0x18002689e  mov     word ptr [rax], 2Dh ; '-'
0x1800268a3  lea     rcx, [rax+2]
0x1800268a7  jmp     short loc_1800268AC
0x1800268a9  mov     rcx, rdi; Dest
0x1800268ac  call    cs:__imp_mbstowcs
0x1800268b2  xor     eax, eax
0x1800268b4  mov     [rdi+rbx*2], ax
0x1800268b8  mov     rcx, rdi; psz
0x1800268bb  call    cs:__imp_SysAllocString
0x1800268c1  mov     [rsi+8], rax
0x1800268c5  mov     word ptr [rsi], 8
0x1800268ca  mov     rcx, rdi
0x1800268cd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800268d3  nop
0x1800268d4  jmp     loc_1800269E4
0x1800268d9  xor     r8d, r8d; wFlags
0x1800268dc  movzx   r9d, r10w; vt
0x1800268e0  mov     rdx, r14; pvarSrc
0x1800268e3  mov     rcx, rsi; pvargDest
0x1800268e6  call    cs:__imp_VariantChangeType
0x1800268ec  mov     edi, eax
0x1800268ee  test    eax, eax
0x1800268f0  jns     loc_1800269E6
0x1800268f6  mov     eax, 5
0x1800268fb  cmp     ax, [r14]
0x1800268ff  jnz     loc_18002678D
0x180026905  movsd   xmm0, qword ptr [r14+8]; X
0x18002690b  call    floor_0
0x180026910  movaps  xmm6, xmm0
0x180026913  movsd   xmm0, qword ptr [r14+8]; X
0x180026919  call    ceil_0
0x18002691e  ucomisd xmm6, xmm0
0x180026922  jp      loc_18002678D
0x180026928  jnz     loc_18002678D
0x18002692e  lea     rdx, [rsi+8]; pulOut
0x180026932  movsd   xmm0, qword ptr [r14+8]; dblIn
0x180026938  call    cs:__imp_VarUI4FromR8
0x18002693e  mov     edi, eax
0x180026940  test    eax, eax
0x180026942  js      loc_18002678D
0x180026948  mov     word ptr [rsi], 3
0x18002694d  jmp     loc_1800269E6
0x180026952  xor     r8d, r8d; wFlags
0x180026955  movzx   r9d, r10w; vt
0x180026959  mov     rdx, r14; pvarSrc
0x18002695c  mov     rcx, rsi; pvargDest
0x18002695f  call    cs:__imp_VariantChangeType
0x180026965  mov     edi, eax
0x180026967  test    eax, eax
0x180026969  js      loc_18002678D
0x18002696f  mov     eax, 11h
0x180026974  cmp     ax, bp
0x180026977  jz      short loc_180026983
0x180026979  mov     eax, 0Bh
0x18002697e  cmp     ax, bp
0x180026981  jnz     short loc_1800269E6
0x180026983  and     dword ptr [rsi+8], 0FFh
0x18002698a  jmp     short loc_1800269E6
0x18002698c  sub     ebx, 66h ; 'f'
0x18002698f  jz      loc_180026770
0x180026995  cmp     ebx, 1
0x180026998  jnz     short loc_1800269E6
0x18002699a  xor     r8d, r8d; wFlags
0x18002699d  movzx   r9d, r10w; vt
0x1800269a1  mov     rdx, r14; pvarSrc
0x1800269a4  mov     rcx, rsi; pvargDest
0x1800269a7  call    cs:__imp_VariantChangeType
0x1800269ad  mov     edi, eax
0x1800269af  test    eax, eax
0x1800269b1  js      loc_18002678D
0x1800269b7  mov     eax, 11h
0x1800269bc  cmp     bp, ax
0x1800269bf  ja      short loc_1800269E6
0x1800269c1  mov     ecx, 20804h
0x1800269c6  bt      ecx, ebp
0x1800269c9  jnb     short loc_1800269E6
0x1800269cb  xor     eax, eax
0x1800269cd  mov     [rsi+0Ah], ax
0x1800269d1  jmp     short loc_1800269E6
0x1800269d3  xorps   xmm0, xmm0
0x1800269d6  xor     eax, eax
0x1800269d8  movups  xmmword ptr [rsi], xmm0
0x1800269db  mov     [rsi+10h], rax
0x1800269df  mov     word ptr [rsi], 1
0x1800269e4  xor     edi, edi
0x1800269e6  mov     eax, edi
0x1800269e8  mov     rbx, [rsp+68h+arg_0]
0x1800269ed  movaps  xmm6, [rsp+68h+var_38]
0x1800269f2  movaps  xmm7, [rsp+68h+var_48]
0x1800269f7  add     rsp, 40h
0x1800269fb  pop     r14
0x1800269fd  pop     r12
0x1800269ff  pop     rdi
0x180026a00  pop     rsi
0x180026a01  pop     rbp
0x180026a02  retn
```
