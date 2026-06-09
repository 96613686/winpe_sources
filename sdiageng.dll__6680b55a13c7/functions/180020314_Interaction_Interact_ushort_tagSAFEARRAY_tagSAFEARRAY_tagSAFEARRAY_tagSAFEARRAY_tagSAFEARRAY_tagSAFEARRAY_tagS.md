# Interaction::Interact(ushort *,tagSAFEARRAY *,tagSAFEARRAY *,tagSAFEARRAY *,tagSAFEARRAY *,tagSAFEARRAY *,tagSAFEARRAY *,tagSAFEARRAY * *)

- ea: `0x180020314`
- end: `0x18002063f`
- name: `?Interact@Interaction@@QEAAJPEAGPEAUtagSAFEARRAY@@11111PEAPEAU2@@Z`
- size: `811`
- prototype: `Interact *__fastcall(Interact *this, unsigned __int16 *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180016518`

## callees

- `0x180005ad0`
- `0x18001f844`
- `0x180020314`
- `0x180026fa0`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002036c`
- `msvcrt!_wcsicmp` at `0x18002036c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020613`
- `OLEAUT32!__imp_SysFreeString` at `0x180020613`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002062a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002062a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800203e6`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800203e6`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002056b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002056b`

## pseudocode

```c
Interact *__fastcall Interaction::Interact(
        Interact *this,
        unsigned __int16 *a2,
        struct tagSAFEARRAY *a3,
        struct tagSAFEARRAY *a4,
        struct tagSAFEARRAY *a5,
        struct tagSAFEARRAY *a6,
        struct tagSAFEARRAY *a7,
        struct tagSAFEARRAY *a8,
        struct tagSAFEARRAY **a9)
{
  struct IXMLDOMDocument2 *v9; // r14
  unsigned int v13; // ebx
  int v14; // r8d
  int v15; // r9d
  const wchar_t *v16; // rcx
  int v17; // eax
  SAFEARRAY *v18; // rcx
  __int64 v19; // rsi
  HRESULT v20; // eax
  int updated; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rcx
  SAFEARRAY *v29; // rdx
  SAFEARRAY *v30; // rax
  BSTR bstrString; // [rsp+40h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v33; // [rsp+48h] [rbp-10h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+98h] [rbp+40h] BYREF

  v9 = 0;
  bstrString = 0;
  v33 = 0;
  ppsaOut = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    v14 = 421;
    v15 = -2147024809;
LABEL_44:
    SdpDebugTrace(1u, L"Interaction::Interact", v14, v15);
    goto LABEL_45;
  }
  v16 = (const wchar_t *)*((_QWORD *)this + 2);
  if ( !v16 )
  {
    v14 = 422;
LABEL_43:
    v15 = -2147467261;
    v13 = -2147467261;
    goto LABEL_44;
  }
  if ( _wcsicmp(v16, a2) )
  {
    v13 = 1;
    goto LABEL_45;
  }
  (*(void (__fastcall **)(Interact *))(*(_QWORD *)this + 16LL))(this);
  v17 = (*(__int64 (__fastcall **)(Interact *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, struct tagSAFEARRAY *))(*(_QWORD *)this + 40LL))(
          this,
          a3,
          a4,
          a5,
          a6,
          a7,
          a8);
  v13 = v17;
  if ( v17 < 0 )
  {
    v15 = v17;
    v14 = 460;
    goto LABEL_44;
  }
  v18 = (SAFEARRAY *)*((_QWORD *)this + 10);
  if ( v18 )
  {
    v19 = 0;
    v20 = SafeArrayCopy(v18, &ppsaOut);
    v13 = v20;
    if ( v20 < 0 )
    {
      v15 = v20;
      v14 = 469;
      goto LABEL_44;
    }
LABEL_29:
    v29 = ppsaOut;
LABEL_30:
    if ( !v29 )
    {
      v27 = -2147467261;
      v26 = 537;
      v13 = -2147467261;
      goto LABEL_22;
    }
    v25 = (*(__int64 (__fastcall **)(Interact *))(*(_QWORD *)this + 48LL))(this);
    v13 = v25;
    if ( v25 >= 0 )
    {
      v30 = ppsaOut;
      ppsaOut = 0;
      *a9 = v30;
      goto LABEL_38;
    }
    v26 = 539;
    goto LABEL_21;
  }
  updated = SdpUpdateParamSet(a3, a4, (Interact *)((char *)this + 40));
  v13 = updated;
  if ( updated < 0 )
  {
    v15 = updated;
    v14 = 480;
    goto LABEL_44;
  }
  v22 = SdpUpdateParamSet(a3, a4, (Interact *)((char *)this + 64));
  v13 = v22;
  if ( v22 < 0 )
  {
    v15 = v22;
    v14 = 485;
    goto LABEL_44;
  }
  v23 = *((_QWORD *)this + 1);
  v19 = *(_QWORD *)(v23 + 80);
  if ( !v19 )
  {
    if ( *((_DWORD *)this + 22) )
    {
      v14 = 498;
      goto LABEL_43;
    }
    ppsaOut = SafeArrayCreateVector(8u, 0, 0);
    v29 = ppsaOut;
    if ( !ppsaOut )
    {
      v13 = -2147024882;
      v14 = 496;
      v15 = -2147024882;
      goto LABEL_44;
    }
    goto LABEL_30;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(*(_QWORD *)(v23 + 80));
  v24 = Interaction::BuildInteractionDocument(this, &v33, 0);
  v13 = v24;
  if ( v24 >= 0 )
  {
    v9 = v33;
    v25 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR *))v33->lpVtbl->get_xml)(v33, &bstrString);
    v13 = v25;
    if ( v25 >= 0 )
    {
      v28 = *((_QWORD *)this + 1);
      if ( !v28 )
      {
        v27 = -2147467261;
        v26 = 514;
        v13 = -2147467261;
        goto LABEL_22;
      }
      if ( _InterlockedExchange((volatile __int32 *)(v28 + 60), *(_DWORD *)(v28 + 60)) )
      {
        v13 = -2143551232;
        v26 = 521;
        v27 = -2143551232;
        goto LABEL_22;
      }
      v25 = (*(__int64 (__fastcall **)(__int64, BSTR, SAFEARRAY **))(*(_QWORD *)v19 + 24LL))(v19, bstrString, &ppsaOut);
      v13 = v25;
      if ( v25 >= 0 )
        goto LABEL_29;
      v26 = 529;
    }
    else
    {
      v26 = 508;
    }
LABEL_21:
    v27 = v25;
LABEL_22:
    SdpDebugTrace(1u, L"Interaction::Interact", v26, v27);
    goto LABEL_38;
  }
  SdpDebugTrace(1u, L"Interaction::Interact", 505, v24);
  v9 = v33;
LABEL_38:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9->lpVtbl->Release)(v9);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_45:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( ppsaOut )
    SafeArrayDestroy(ppsaOut);
  return (Interact *)v13;
}

```

## disassembly

```asm
0x180020314  push    rbp
0x180020316  push    rbx
0x180020317  push    rsi
0x180020318  push    rdi
0x180020319  push    r14
0x18002031b  push    r15
0x18002031d  mov     rbp, rsp
0x180020320  sub     rsp, 58h
0x180020324  xor     r14d, r14d
0x180020327  mov     [rbp+bstrString], 0
0x18002032f  mov     [rbp+var_10], r14
0x180020333  mov     rsi, r9
0x180020336  mov     [rbp+ppsaOut], r14
0x18002033a  mov     r15, r8
0x18002033d  mov     rdi, rcx
0x180020340  test    rdx, rdx
0x180020343  jnz     short loc_180020358
0x180020345  mov     ebx, 80070057h
0x18002034a  mov     r8d, 1A5h
0x180020350  mov     r9d, ebx
0x180020353  jmp     loc_1800205F9
0x180020358  mov     rcx, [rcx+10h]; String1
0x18002035c  test    rcx, rcx
0x18002035f  jnz     short loc_18002036C
0x180020361  mov     r8d, 1A6h
0x180020367  jmp     loc_1800205F0
0x18002036c  call    cs:__imp__wcsicmp
0x180020372  test    eax, eax
0x180020374  jz      short loc_180020380
0x180020376  mov     ebx, 1
0x18002037b  jmp     loc_18002060A
0x180020380  mov     rax, [rdi]
0x180020383  mov     rcx, rdi
0x180020386  mov     rax, [rax+10h]
0x18002038a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002038f  mov     rcx, [rbp+arg_38]
0x180020393  mov     r8, rsi
0x180020396  mov     rax, [rdi]
0x180020399  mov     rdx, r15
0x18002039c  mov     r9, [rbp+arg_20]
0x1800203a0  mov     [rsp+58h+var_28], rcx
0x1800203a5  mov     rcx, [rbp+arg_30]
0x1800203a9  mov     rax, [rax+28h]
0x1800203ad  mov     [rsp+58h+var_30], rcx
0x1800203b2  mov     rcx, [rbp+arg_28]
0x1800203b6  mov     [rsp+58h+var_38], rcx
0x1800203bb  mov     rcx, rdi
0x1800203be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203c3  mov     ebx, eax
0x1800203c5  test    eax, eax
0x1800203c7  jns     short loc_1800203D7
0x1800203c9  mov     r9d, eax
0x1800203cc  mov     r8d, 1CCh
0x1800203d2  jmp     loc_1800205F9
0x1800203d7  mov     rcx, [rdi+50h]; psa
0x1800203db  test    rcx, rcx
0x1800203de  jz      short loc_180020404
0x1800203e0  lea     rdx, [rbp+ppsaOut]; ppsaOut
0x1800203e4  xor     esi, esi
0x1800203e6  call    cs:__imp_SafeArrayCopy
0x1800203ec  mov     ebx, eax
0x1800203ee  test    eax, eax
0x1800203f0  jns     loc_18002053A
0x1800203f6  mov     r9d, eax
0x1800203f9  mov     r8d, 1D5h
0x1800203ff  jmp     loc_1800205F9
0x180020404  lea     r8, [rdi+28h]; struct _SDIAG_PARAMSET *
0x180020408  mov     rdx, rsi; SAFEARRAY *
0x18002040b  mov     rcx, r15; psa
0x18002040e  call    ?SdpUpdateParamSet@@YAJPEAUtagSAFEARRAY@@0PEAU_SDIAG_PARAMSET@@@Z; SdpUpdateParamSet(tagSAFEARRAY *,tagSAFEARRAY *,_SDIAG_PARAMSET *)
0x180020413  mov     ebx, eax
0x180020415  test    eax, eax
0x180020417  jns     short loc_180020427
0x180020419  mov     r9d, eax
0x18002041c  mov     r8d, 1E0h
0x180020422  jmp     loc_1800205F9
0x180020427  lea     r8, [rdi+40h]; struct _SDIAG_PARAMSET *
0x18002042b  mov     rdx, rsi; SAFEARRAY *
0x18002042e  mov     rcx, r15; psa
0x180020431  call    ?SdpUpdateParamSet@@YAJPEAUtagSAFEARRAY@@0PEAU_SDIAG_PARAMSET@@@Z; SdpUpdateParamSet(tagSAFEARRAY *,tagSAFEARRAY *,_SDIAG_PARAMSET *)
0x180020436  mov     ebx, eax
0x180020438  test    eax, eax
0x18002043a  jns     short loc_18002044A
0x18002043c  mov     r9d, eax
0x18002043f  mov     r8d, 1E5h
0x180020445  jmp     loc_1800205F9
0x18002044a  mov     rax, [rdi+8]
0x18002044e  mov     rsi, [rax+50h]
0x180020452  test    rsi, rsi
0x180020455  jz      loc_180020557
0x18002045b  mov     rax, [rsi]
0x18002045e  mov     rcx, rsi
0x180020461  mov     rax, [rax+8]
0x180020465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002046a  xor     r8d, r8d; int
0x18002046d  lea     rdx, [rbp+var_10]; struct IXMLDOMDocument2 **
0x180020471  mov     rcx, rdi; this
0x180020474  call    ?BuildInteractionDocument@Interaction@@IEAAJPEAPEAUIXMLDOMDocument2@@H@Z; Interaction::BuildInteractionDocument(IXMLDOMDocument2 * *,int)
0x180020479  mov     ebx, eax
0x18002047b  test    eax, eax
0x18002047d  jns     short loc_1800204A2
0x18002047f  mov     r9d, eax; int
0x180020482  lea     rdx, aInteractionInt; "Interaction::Interact"
0x180020489  mov     r8d, 1F9h; int
0x18002048f  mov     ecx, 1; Level
0x180020494  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020499  mov     r14, [rbp+var_10]
0x18002049d  jmp     loc_1800205C0
0x1800204a2  mov     r14, [rbp+var_10]
0x1800204a6  lea     rdx, [rbp+bstrString]
0x1800204aa  mov     rcx, r14
0x1800204ad  mov     rax, [r14]
0x1800204b0  mov     rax, [rax+110h]
0x1800204b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204bc  mov     ebx, eax
0x1800204be  test    eax, eax
0x1800204c0  jns     short loc_1800204E1
0x1800204c2  mov     r8d, 1FCh; int
0x1800204c8  mov     r9d, eax; int
0x1800204cb  lea     rdx, aInteractionInt; "Interaction::Interact"
0x1800204d2  mov     ecx, 1; Level
0x1800204d7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800204dc  jmp     loc_1800205C0
0x1800204e1  mov     rcx, [rdi+8]
0x1800204e5  test    rcx, rcx
0x1800204e8  jnz     short loc_1800204FB
0x1800204ea  mov     r9d, 80004003h
0x1800204f0  mov     r8d, 202h
0x1800204f6  mov     ebx, r9d
0x1800204f9  jmp     short loc_1800204CB
0x1800204fb  mov     eax, [rcx+3Ch]
0x1800204fe  xchg    eax, [rcx+3Ch]
0x180020501  test    eax, eax
0x180020503  jz      short loc_180020515
0x180020505  mov     ebx, 803C0100h
0x18002050a  mov     r8d, 209h
0x180020510  mov     r9d, ebx
0x180020513  jmp     short loc_1800204CB
0x180020515  mov     rax, [rsi]
0x180020518  lea     r8, [rbp+ppsaOut]
0x18002051c  mov     rdx, [rbp+bstrString]
0x180020520  mov     rcx, rsi
0x180020523  mov     rax, [rax+18h]
0x180020527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002052c  mov     ebx, eax
0x18002052e  test    eax, eax
0x180020530  jns     short loc_18002053A
0x180020532  mov     r8d, 211h
0x180020538  jmp     short loc_1800204C8
0x18002053a  mov     rdx, [rbp+ppsaOut]
0x18002053e  test    rdx, rdx
0x180020541  jnz     short loc_18002058D
0x180020543  mov     r9d, 80004003h
0x180020549  mov     r8d, 219h
0x18002054f  mov     ebx, r9d
0x180020552  jmp     loc_1800204CB
0x180020557  cmp     [rdi+58h], r14d
0x18002055b  jnz     loc_1800205EA
0x180020561  mov     ecx, 8; vt
0x180020566  xor     r8d, r8d; cElements
0x180020569  xor     edx, edx; lLbound
0x18002056b  call    cs:__imp_SafeArrayCreateVector
0x180020571  mov     [rbp+ppsaOut], rax
0x180020575  mov     rdx, rax
0x180020578  test    rax, rax
0x18002057b  jnz     short loc_18002053E
0x18002057d  mov     ebx, 8007000Eh
0x180020582  mov     r8d, 1F0h
0x180020588  mov     r9d, ebx
0x18002058b  jmp     short loc_1800205F9
0x18002058d  mov     rax, [rdi]
0x180020590  mov     rcx, rdi
0x180020593  mov     rax, [rax+30h]
0x180020597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002059c  mov     ebx, eax
0x18002059e  test    eax, eax
0x1800205a0  jns     short loc_1800205AD
0x1800205a2  mov     r8d, 21Bh
0x1800205a8  jmp     loc_1800204C8
0x1800205ad  mov     rax, [rbp+ppsaOut]
0x1800205b1  mov     rdx, [rbp+arg_40]
0x1800205b5  mov     [rbp+ppsaOut], 0
0x1800205bd  mov     [rdx], rax
0x1800205c0  test    r14, r14
0x1800205c3  jz      short loc_1800205D4
0x1800205c5  mov     rax, [r14]
0x1800205c8  mov     rcx, r14
0x1800205cb  mov     rax, [rax+10h]
0x1800205cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205d4  test    rsi, rsi
0x1800205d7  jz      short loc_18002060A
0x1800205d9  mov     rax, [rsi]
0x1800205dc  mov     rcx, rsi
0x1800205df  mov     rax, [rax+10h]
0x1800205e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205e8  jmp     short loc_18002060A
0x1800205ea  mov     r8d, 1F2h; int
0x1800205f0  mov     r9d, 80004003h; int
0x1800205f6  mov     ebx, r9d
0x1800205f9  lea     rdx, aInteractionInt; "Interaction::Interact"
0x180020600  mov     ecx, 1; Level
0x180020605  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002060a  mov     rcx, [rbp+bstrString]; bstrString
0x18002060e  test    rcx, rcx
0x180020611  jz      short loc_180020621
0x180020613  call    cs:__imp_SysFreeString
0x180020619  mov     [rbp+bstrString], 0
0x180020621  mov     rcx, [rbp+ppsaOut]; psa
0x180020625  test    rcx, rcx
0x180020628  jz      short loc_180020630
0x18002062a  call    cs:__imp_SafeArrayDestroy
0x180020630  mov     eax, ebx
0x180020632  add     rsp, 58h
0x180020636  pop     r15
0x180020638  pop     r14
0x18002063a  pop     rdi
0x18002063b  pop     rsi
0x18002063c  pop     rbx
0x18002063d  pop     rbp
0x18002063e  retn
```
