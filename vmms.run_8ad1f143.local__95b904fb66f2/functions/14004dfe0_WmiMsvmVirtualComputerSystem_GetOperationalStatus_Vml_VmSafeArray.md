# WmiMsvmVirtualComputerSystem::GetOperationalStatus(Vml::VmSafeArray &)

- ea: `0x14004dfe0`
- end: `0x14004e650`
- name: `?GetOperationalStatus@WmiMsvmVirtualComputerSystem@@UEBAXAEAVVmSafeArray@Vml@@@Z`
- size: `1648`
- prototype: `void __fastcall(WmiMsvmVirtualComputerSystem *__hidden this, struct Vml::VmSafeArray *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x140020a04`
- `0x14002d384`
- `0x14004dfe0`
- `0x14004f058`
- `0x14004f0a4`
- `0x14004f4d8`
- `0x140188e18`
- `0x1404828e0`
- `0x140482b74`
- `0x1404835a0`
- `0x140486541`
- `0x140498a40`
- `0x1408aa010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14004e0c4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14004e0ee`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14004e0c4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14004e0ee`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x14004e2ea`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x14004e2ea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14004e178`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14004e1a1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14004e178`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14004e1a1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14004e1c7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14004e216`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14004e1c7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14004e216`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14004e27c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14004e27c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14004e327`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14004e327`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14004e38f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14004e38f`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x14004e23b`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x14004e23b`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14004e02c`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14004e02c`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14004e345`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14004e345`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14004e2bc`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14004e2db`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14004e2bc`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x14004e2db`

## string_xrefs

- `0x14004e252`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e293`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e3a6`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e568`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e59d`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e5b2`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e5ce`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e5e3`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e5f8`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e60d`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e622`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14004e637`: `onecore\vm\common\vml\VmAutomation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WmiMsvmVirtualComputerSystem::GetOperationalStatus(WmiMsvmVirtualComputerSystem *this, SAFEARRAY **a2)
{
  SAFEARRAY *Vector; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int i; // r14d
  char *v8; // rcx
  SAFEARRAY *v9; // rax
  HRESULT v10; // eax
  HRESULT v11; // eax
  const struct std::nothrow_t *v12; // rdx
  char *v13; // rax
  HRESULT UBound; // eax
  HRESULT v15; // eax
  HRESULT LBound; // eax
  LONG v17; // esi
  int v18; // edi
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  UINT Elemsize; // edi
  HRESULT Vartype; // eax
  HRESULT v24; // eax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  int v27; // esi
  int v28; // r14d
  __int64 v29; // rdx
  int v30; // edi
  _QWORD *v31; // rax
  _QWORD *v32; // rdx
  __int64 v33; // r8
  _QWORD **v34; // rcx
  _QWORD *v35; // rcx
  _QWORD *v36; // rdi
  __int64 v37; // rax
  _QWORD *v38; // rcx
  int v39; // [rsp+20h] [rbp-99h]
  void *pv; // [rsp+30h] [rbp-89h] BYREF
  __int64 v41; // [rsp+38h] [rbp-81h]
  void **p_pv; // [rsp+40h] [rbp-79h] BYREF
  __int64 v43; // [rsp+48h] [rbp-71h]
  __int128 v44; // [rsp+50h] [rbp-69h]
  SAFEARRAY *v45; // [rsp+60h] [rbp-59h]
  void *v46; // [rsp+68h] [rbp-51h] BYREF
  LONG plUbound; // [rsp+70h] [rbp-49h] BYREF
  LONG v48; // [rsp+78h] [rbp-41h] BYREF
  void *v49; // [rsp+80h] [rbp-39h] BYREF
  LONG plLbound[2]; // [rsp+88h] [rbp-31h] BYREF
  LONG rgIndices; // [rsp+90h] [rbp-29h] BYREF
  void *Src[2]; // [rsp+98h] [rbp-21h] BYREF
  void *v53[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-1h]
  SAFEARRAY *psa; // [rsp+C0h] [rbp+7h]
  void *ppvData; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *(_OWORD *)v53 = 0;
  v54 = 0;
  Vector = SafeArrayCreateVectorEx(0x12u, 0, 0, 0);
  v45 = Vector;
  if ( !Vector )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      v39);
  v5 = *((_QWORD *)this + 4) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL) + 12LL);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5) )
  {
    v6 = *((_QWORD *)this + 4) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL) + 16LL);
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 304LL))(v6, v53);
  }
  else
  {
    Src[1] = 0;
    v25 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
    *v25 = v25;
    v25[1] = v25;
    Src[0] = v25;
    v26 = *((_QWORD *)this + 4) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL) + 16LL);
    (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v26 + 344LL))(v26, Src);
    v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 160LL))(*((_QWORD *)this + 4));
    v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
    v29 = *((_QWORD *)this + 4);
    if ( v29 )
      v30 = v29 + *(_DWORD *)(*(_QWORD *)(v29 + 8) + 16LL) + 8;
    else
      v30 = 0;
    pv = 0;
    v41 = 0;
    p_pv = &pv;
    v43 = 0;
    v44 = 0;
    std::_List_node_insert_op2<std::allocator<std::_List_node<enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,void *>>>::_Append_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,std::_Iterator_base0>>(
      &p_pv,
      *(_QWORD *)Src[0],
      Src[0]);
    psa = (SAFEARRAY *)p_pv;
    ppvData = 0;
    v31 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
    v32 = v31;
    v33 = v43;
    v43 = 0;
    if ( v33 )
    {
      v37 = *((_QWORD *)&v44 + 1);
      v38 = (_QWORD *)v44;
      *v32 = *((_QWORD *)&v44 + 1);
      v32[1] = v38;
      *(_QWORD *)(v37 + 8) = v32;
      *v38 = v32;
    }
    else
    {
      *v31 = v31;
      v31[1] = v31;
    }
    v41 = v33;
    pv = v32;
    std::_List_node_insert_op2<std::allocator<std::_List_node<enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,void *>>>::~_List_node_insert_op2<std::allocator<std::_List_node<enum __MIDL___MIDL_itf_vmtskitf_0000_0000_0001,void *>>>(&p_pv);
    TranslateVmTaskTypesToOperationalStatus((unsigned int)&pv, v30, v28, v27, (__int64)v53);
    v34 = (_QWORD **)Src[0];
    **((_QWORD **)Src[0] + 1) = 0;
    v35 = *v34;
    if ( v35 )
    {
      do
      {
        v36 = (_QWORD *)*v35;
        std::_Deallocate<16>(v35, 24);
        v35 = v36;
      }
      while ( v36 );
    }
    operator delete(Src[0], (const struct std::nothrow_t *)0x18);
  }
  for ( i = 0; ; ++i )
  {
    v8 = (char *)v53[0];
    if ( i >= (unsigned __int64)(((char *)v53[1] - (char *)v53[0]) >> 2) )
      break;
    LOWORD(v49) = *((_WORD *)v53[0] + 2 * i);
    plUbound = 0;
    UBound = SafeArrayGetUBound(Vector, 1u, &plUbound);
    if ( UBound < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3AE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)UBound,
        v39);
    ++plUbound;
    v48 = 0;
    v15 = SafeArrayGetUBound(Vector, 1u, &v48);
    if ( v15 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3AE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v15,
        v39);
    plLbound[0] = 0;
    LBound = SafeArrayGetLBound(Vector, 1u, plLbound);
    if ( LBound < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)LBound,
        v39);
    if ( plUbound < plLbound[0] || (v17 = v48, v18 = v48 + 1, plUbound > v48 + 1) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB5D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)0x8002000BLL,
        v39);
    plLbound[1] = 0;
    plLbound[0] = v48 - plLbound[0] + 2;
    v48 = 0;
    v19 = SafeArrayGetLBound(Vector, 1u, &v48);
    if ( v19 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v19,
        v39);
    plLbound[1] = v48;
    v20 = SafeArrayRedim(Vector, (SAFEARRAYBOUND *)plLbound);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x435,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v20,
        v39);
    if ( plUbound != v18 )
    {
      psa = Vector;
      ppvData = 0;
      v21 = SafeArrayAccessData(Vector, &ppvData);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7B2,
          (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
          (const char *)(unsigned int)v21,
          v39);
      Src[0] = 0;
      rgIndices = 0;
      v46 = 0;
      SafeArrayPtrOfIndex(Vector, &plUbound, Src);
      rgIndices = plUbound + 1;
      SafeArrayPtrOfIndex(Vector, &rgIndices, &v46);
      Elemsize = SafeArrayGetElemsize(Vector);
      memmove_0(v46, Src[0], Elemsize * (v17 - plUbound + 1));
      memset_0(Src[0], 0, Elemsize);
      if ( psa )
        SafeArrayUnaccessData(psa);
    }
    v48 = plUbound;
    LOWORD(plLbound[0]) = 0;
    Vartype = SafeArrayGetVartype(Vector, (VARTYPE *)plLbound);
    if ( Vartype < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x38D,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)Vartype,
        v39);
    if ( LOWORD(plLbound[0]) == 8 || LOWORD(plLbound[0]) == 9 || LOWORD(plLbound[0]) == 13 )
      pv = v49;
    else
      pv = &v49;
    v24 = SafeArrayPutElement(Vector, &v48, pv);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3A,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v24,
        v39);
  }
  v9 = *a2;
  if ( *a2 )
  {
    v10 = SafeArrayDestroy(*a2);
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v10,
        v39);
    v9 = 0;
    v8 = (char *)v53[0];
  }
  *a2 = Vector;
  if ( v9 )
  {
    v11 = SafeArrayDestroy(v9);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v11,
        v39);
    v8 = (char *)v53[0];
  }
  if ( v8 )
  {
    v12 = (const struct std::nothrow_t *)(4 * ((v54 - (__int64)v8) >> 2));
    if ( (unsigned __int64)v12 >= 0x1000 )
    {
      v13 = (char *)*((_QWORD *)v8 - 1);
      if ( (unsigned __int64)(v8 - v13 - 8) > 0x1F )
        __fastfail(5u);
      v12 = (const struct std::nothrow_t *)((char *)v12 + 39);
    }
    else
    {
      v13 = v8;
    }
    operator delete(v13, v12);
  }
}

```

## disassembly

```asm
0x14004dfe0  mov     [rsp-8+arg_10], rbx
0x14004dfe5  push    rbp
0x14004dfe6  push    rsi
0x14004dfe7  push    rdi
0x14004dfe8  push    r12
0x14004dfea  push    r13
0x14004dfec  push    r14
0x14004dfee  push    r15
0x14004dff0  lea     rbp, [rsp-27h]
0x14004dff5  sub     rsp, 0E0h
0x14004dffc  mov     rax, cs:__security_cookie
0x14004e003  xor     rax, rsp
0x14004e006  mov     [rbp+57h+var_40], rax
0x14004e00a  mov     r15, rdx
0x14004e00d  mov     rdi, rcx
0x14004e010  xorps   xmm1, xmm1
0x14004e013  movdqu  xmmword ptr [rbp+57h+var_68], xmm1
0x14004e018  xor     r12d, r12d
0x14004e01b  mov     [rbp+57h+var_58], r12
0x14004e01f  lea     ecx, [r12+12h]; vt
0x14004e024  xor     r9d, r9d; pvExtra
0x14004e027  xor     r8d, r8d; cElements
0x14004e02a  xor     edx, edx; lLbound
0x14004e02c  call    cs:__imp_SafeArrayCreateVectorEx
0x14004e033  nop     dword ptr [rax+rax+00h]
0x14004e038  mov     rbx, rax
0x14004e03b  mov     [rbp+57h+var_B0], rax
0x14004e03f  test    rax, rax
0x14004e042  jz      loc_14004E55E
0x14004e048  mov     rdx, [rdi+20h]
0x14004e04c  mov     rax, [rdx+8]
0x14004e050  movsxd  rcx, dword ptr [rax+0Ch]
0x14004e054  add     rdx, 8
0x14004e058  add     rcx, rdx
0x14004e05b  mov     rax, [rcx]
0x14004e05e  mov     rax, [rax+60h]
0x14004e062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e067  test    eax, eax
0x14004e069  jz      loc_14004E3C0
0x14004e06f  mov     rdx, [rdi+20h]
0x14004e073  mov     rax, [rdx+8]
0x14004e077  movsxd  rcx, dword ptr [rax+10h]
0x14004e07b  add     rdx, 8
0x14004e07f  add     rcx, rdx
0x14004e082  mov     rax, [rcx]
0x14004e085  lea     rdx, [rbp+57h+var_68]
0x14004e089  mov     rax, [rax+130h]
0x14004e090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e095  mov     r14d, r12d
0x14004e098  mov     r13d, 1
0x14004e09e  movsxd  rdx, r14d
0x14004e0a1  mov     rax, [rbp+57h+var_68+8]
0x14004e0a5  mov     rcx, [rbp+57h+var_68]
0x14004e0a9  sub     rax, rcx
0x14004e0ac  sar     rax, 2
0x14004e0b0  cmp     rdx, rax
0x14004e0b3  jb      loc_14004E162
0x14004e0b9  mov     rax, [r15]
0x14004e0bc  test    rax, rax
0x14004e0bf  jz      short loc_14004E0E3
0x14004e0c1  mov     rcx, rax; psa
0x14004e0c4  call    cs:__imp_SafeArrayDestroy
0x14004e0cb  nop     dword ptr [rax+rax+00h]
0x14004e0d0  mov     rcx, [rbp+5Fh]; this
0x14004e0d4  test    eax, eax
0x14004e0d6  js      loc_14004E61F
0x14004e0dc  mov     rax, r12
0x14004e0df  mov     rcx, [rbp+57h+var_68]
0x14004e0e3  mov     [r15], rbx
0x14004e0e6  test    rax, rax
0x14004e0e9  jz      short loc_14004E10A
0x14004e0eb  mov     rcx, rax; psa
0x14004e0ee  call    cs:__imp_SafeArrayDestroy
0x14004e0f5  nop     dword ptr [rax+rax+00h]
0x14004e0fa  mov     rcx, [rbp+5Fh]; this
0x14004e0fe  test    eax, eax
0x14004e100  js      loc_14004E634
0x14004e106  mov     rcx, [rbp+57h+var_68]
0x14004e10a  test    rcx, rcx
0x14004e10d  jz      short loc_14004E13A
0x14004e10f  mov     rax, [rbp+57h+var_58]
0x14004e113  sub     rax, rcx
0x14004e116  sar     rax, 2
0x14004e11a  lea     rdx, ds:0[rax*4]; struct std::nothrow_t *
0x14004e122  cmp     rdx, 1000h
0x14004e129  jnb     loc_14004E51D
0x14004e12f  mov     rax, rcx
0x14004e132  mov     rcx, rax; void *
0x14004e135  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004e13a  mov     rcx, [rbp+57h+var_40]
0x14004e13e  xor     rcx, rsp; StackCookie
0x14004e141  call    __security_check_cookie
0x14004e146  mov     rbx, [rsp+110h+arg_10]
0x14004e14e  add     rsp, 0E0h
0x14004e155  pop     r15
0x14004e157  pop     r14
0x14004e159  pop     r13
0x14004e15b  pop     r12
0x14004e15d  pop     rdi
0x14004e15e  pop     rsi
0x14004e15f  pop     rbp
0x14004e160  retn
0x14004e162  movzx   eax, word ptr [rcx+rdx*4]
0x14004e166  mov     [rbp+57h+var_90], ax
0x14004e16a  mov     [rbp+57h+plUbound], r12d
0x14004e16e  lea     r8, [rbp+57h+plUbound]; plUbound
0x14004e172  mov     edx, r13d; nDim
0x14004e175  mov     rcx, rbx; psa
0x14004e178  call    cs:__imp_SafeArrayGetUBound
0x14004e17f  nop     dword ptr [rax+rax+00h]
0x14004e184  mov     rcx, [rbp+5Fh]; this
0x14004e188  test    eax, eax
0x14004e18a  js      loc_14004E60A
0x14004e190  inc     [rbp+57h+plUbound]
0x14004e193  mov     [rbp+57h+var_98], r12d
0x14004e197  lea     r8, [rbp+57h+var_98]; plUbound
0x14004e19b  mov     edx, r13d; nDim
0x14004e19e  mov     rcx, rbx; psa
0x14004e1a1  call    cs:__imp_SafeArrayGetUBound
0x14004e1a8  nop     dword ptr [rax+rax+00h]
0x14004e1ad  mov     rcx, [rbp+5Fh]; this
0x14004e1b1  test    eax, eax
0x14004e1b3  js      loc_14004E5F5
0x14004e1b9  mov     [rbp+57h+plLbound], r12d
0x14004e1bd  lea     r8, [rbp+57h+plLbound]; plLbound
0x14004e1c1  mov     edx, r13d; nDim
0x14004e1c4  mov     rcx, rbx; psa
0x14004e1c7  call    cs:__imp_SafeArrayGetLBound
0x14004e1ce  nop     dword ptr [rax+rax+00h]
0x14004e1d3  mov     rcx, [rbp+5Fh]; this
0x14004e1d7  test    eax, eax
0x14004e1d9  js      loc_14004E5E0
0x14004e1df  mov     ecx, [rbp+57h+plLbound]
0x14004e1e2  cmp     [rbp+57h+plUbound], ecx
0x14004e1e5  jl      loc_14004E5C4
0x14004e1eb  mov     esi, [rbp+57h+var_98]
0x14004e1ee  lea     edi, [rsi+1]
0x14004e1f1  cmp     [rbp+57h+plUbound], edi
0x14004e1f4  jg      loc_14004E5C4
0x14004e1fa  mov     qword ptr [rbp+57h+plLbound], r12
0x14004e1fe  mov     eax, esi
0x14004e200  sub     eax, ecx
0x14004e202  add     eax, 2
0x14004e205  mov     [rbp+57h+plLbound], eax
0x14004e208  mov     [rbp+57h+var_98], r12d
0x14004e20c  lea     r8, [rbp+57h+var_98]; plLbound
0x14004e210  mov     edx, r13d; nDim
0x14004e213  mov     rcx, rbx; psa
0x14004e216  call    cs:__imp_SafeArrayGetLBound
0x14004e21d  nop     dword ptr [rax+rax+00h]
0x14004e222  mov     rcx, [rbp+5Fh]; this
0x14004e226  test    eax, eax
0x14004e228  js      loc_14004E5AF
0x14004e22e  mov     eax, [rbp+57h+var_98]
0x14004e231  mov     [rbp+57h+plLbound+4], eax
0x14004e234  lea     rdx, [rbp+57h+plLbound]; psaboundNew
0x14004e238  mov     rcx, rbx; psa
0x14004e23b  call    cs:__imp_SafeArrayRedim
0x14004e242  nop     dword ptr [rax+rax+00h]
0x14004e247  mov     rcx, [rbp+5Fh]; this
0x14004e24b  test    eax, eax
0x14004e24d  jns     short loc_14004E264
0x14004e24f  mov     r9d, eax; char *
0x14004e252  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14004e259  mov     edx, 435h; void *
0x14004e25e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004e264  cmp     [rbp+57h+plUbound], edi
0x14004e267  jz      loc_14004E333
0x14004e26d  mov     [rbp+57h+psa], rbx
0x14004e271  mov     [rbp+57h+ppvData], r12
0x14004e275  lea     rdx, [rbp+57h+ppvData]; ppvData
0x14004e279  mov     rcx, rbx; psa
0x14004e27c  call    cs:__imp_SafeArrayAccessData
0x14004e283  nop     dword ptr [rax+rax+00h]
0x14004e288  mov     rcx, [rbp+5Fh]; this
0x14004e28c  test    eax, eax
0x14004e28e  jns     short loc_14004E2A5
0x14004e290  mov     r9d, eax; char *
0x14004e293  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14004e29a  mov     edx, 7B2h; void *
0x14004e29f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004e2a5  mov     [rbp+57h+Src], r12
0x14004e2a9  mov     [rbp+57h+rgIndices], r12d
0x14004e2ad  mov     [rbp+57h+var_A8], r12
0x14004e2b1  lea     r8, [rbp+57h+Src]; ppvData
0x14004e2b5  lea     rdx, [rbp+57h+plUbound]; rgIndices
0x14004e2b9  mov     rcx, rbx; psa
0x14004e2bc  call    cs:__imp_SafeArrayPtrOfIndex
0x14004e2c3  nop     dword ptr [rax+rax+00h]
0x14004e2c8  mov     eax, [rbp+57h+plUbound]
0x14004e2cb  inc     eax
0x14004e2cd  mov     [rbp+57h+rgIndices], eax
0x14004e2d0  lea     r8, [rbp+57h+var_A8]; ppvData
0x14004e2d4  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x14004e2d8  mov     rcx, rbx; psa
0x14004e2db  call    cs:__imp_SafeArrayPtrOfIndex
0x14004e2e2  nop     dword ptr [rax+rax+00h]
0x14004e2e7  mov     rcx, rbx; psa
0x14004e2ea  call    cs:__imp_SafeArrayGetElemsize
0x14004e2f1  nop     dword ptr [rax+rax+00h]
0x14004e2f6  mov     edi, eax
0x14004e2f8  sub     esi, [rbp+57h+plUbound]
0x14004e2fb  lea     r8d, [rsi+r13]
0x14004e2ff  imul    r8d, eax; Size
0x14004e303  mov     rdx, [rbp+57h+Src]; Src
0x14004e307  mov     rcx, [rbp+57h+var_A8]; void *
0x14004e30b  call    memmove_0
0x14004e310  mov     r8d, edi; Size
0x14004e313  xor     edx, edx; Val
0x14004e315  mov     rcx, [rbp+57h+Src]; void *
0x14004e319  call    memset_0
0x14004e31e  mov     rcx, [rbp+57h+psa]; psa
0x14004e322  test    rcx, rcx
0x14004e325  jz      short loc_14004E333
0x14004e327  call    cs:__imp_SafeArrayUnaccessData
0x14004e32e  nop     dword ptr [rax+rax+00h]
0x14004e333  mov     eax, [rbp+57h+plUbound]
0x14004e336  mov     [rbp+57h+var_98], eax
0x14004e339  mov     word ptr [rbp+57h+plLbound], r12w
0x14004e33e  lea     rdx, [rbp+57h+plLbound]; pvt
0x14004e342  mov     rcx, rbx; psa
0x14004e345  call    cs:__imp_SafeArrayGetVartype
0x14004e34c  nop     dword ptr [rax+rax+00h]
0x14004e351  mov     rcx, [rbp+5Fh]; this
0x14004e355  test    eax, eax
0x14004e357  js      loc_14004E59A
0x14004e35d  movzx   ecx, word ptr [rbp+57h+plLbound]
0x14004e361  sub     ecx, 8
0x14004e364  jnz     loc_14004E57A
0x14004e36a  movzx   eax, [rbp+57h+var_90]
0x14004e36e  mov     word ptr [rsp+110h+pv], ax
0x14004e373  mov     eax, [rbp+57h+var_8E]
0x14004e376  mov     dword ptr [rsp+110h+pv+2], eax
0x14004e37a  movzx   eax, [rbp+57h+var_8A]
0x14004e37e  mov     word ptr [rsp+110h+pv+6], ax
0x14004e383  mov     r8, [rsp+110h+pv]; pv
0x14004e388  lea     rdx, [rbp+57h+var_98]; rgIndices
0x14004e38c  mov     rcx, rbx; psa
0x14004e38f  call    cs:__imp_SafeArrayPutElement
0x14004e396  nop     dword ptr [rax+rax+00h]
0x14004e39b  mov     rcx, [rbp+5Fh]; this
0x14004e39f  test    eax, eax
0x14004e3a1  jns     short loc_14004E3B8
0x14004e3a3  mov     r9d, eax; char *
0x14004e3a6  lea     r8, aOnecoreVmCommo_58; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14004e3ad  mov     edx, 0B3Ah; void *
0x14004e3b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004e3b8  add     r14d, r13d
0x14004e3bb  jmp     loc_14004E09E
0x14004e3c0  xorps   xmm0, xmm0
0x14004e3c3  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14004e3c7  mov     [rbp+57h+Src], r12
0x14004e3cb  mov     [rbp+57h+Src+8], r12
0x14004e3cf  mov     r13d, 18h
0x14004e3d5  mov     ecx, r13d
0x14004e3d8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14004e3dd  mov     [rax], rax
0x14004e3e0  mov     [rax+8], rax
0x14004e3e4  mov     [rbp+57h+Src], rax
0x14004e3e8  mov     rdx, [rdi+20h]
0x14004e3ec  mov     rax, [rdx+8]
0x14004e3f0  movsxd  rcx, dword ptr [rax+10h]
0x14004e3f4  add     rdx, 8
0x14004e3f8  add     rcx, rdx
0x14004e3fb  mov     rax, [rcx]
0x14004e3fe  lea     rdx, [rbp+57h+Src]
0x14004e402  mov     rax, [rax+158h]
0x14004e409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e40e  mov     rcx, [rdi+20h]
0x14004e412  mov     rax, [rcx]
0x14004e415  mov     rax, [rax+0A0h]
0x14004e41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e421  mov     esi, eax
0x14004e423  mov     rcx, [rdi+20h]
0x14004e427  mov     rdx, [rcx]
0x14004e42a  mov     rax, [rdx+90h]
0x14004e431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e436  mov     r14d, eax
0x14004e439  mov     rdx, [rdi+20h]
0x14004e43d  test    rdx, rdx
0x14004e440  jz      loc_14004E53B
0x14004e446  mov     rax, [rdx+8]
0x14004e44a  movsxd  rdi, dword ptr [rax+10h]
0x14004e44e  add     rdi, 8
0x14004e452  add     rdi, rdx
0x14004e455  mov     [rsp+110h+pv], r12
0x14004e45a  mov     [rsp+110h+var_D8], r12
0x14004e45f  mov     rdx, [rbp+57h+Src]
0x14004e463  lea     rax, [rsp+110h+pv]
0x14004e468  mov     [rbp+57h+var_D0], rax
0x14004e46c  mov     [rbp+57h+var_C8], r12
0x14004e470  xorps   xmm0, xmm0
0x14004e473  movdqu  [rbp+57h+var_C0], xmm0
0x14004e478  mov     r8, rdx
0x14004e47b  mov     rdx, [rdx]
0x14004e47e  lea     rcx, [rbp+57h+var_D0]
0x14004e482  call    ??$_Append_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@W4__MIDL___MIDL_itf_vmtskitf_0000_0000_0001@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$_List_node_insert_op2@V?$allocator@U?$_List_node@W4__MIDL___MIDL_itf_vmtskitf_0000_0000_0001@@PEAX@std@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@W4__MIDL___MIDL_itf_vmtskitf_0000_0000_0001@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::_List_node_insert_op2<std::allocator<std::_List_node<__MIDL___MIDL_itf_vmtskitf_0000_0000_0001,void *>>>::_Append_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<__MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<__MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<__MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<__MIDL___MIDL_itf_vmtskitf_0000_0000_0001>>,std::_Iterator_base0>)
0x14004e487  mov     rax, [rbp+57h+var_D0]
0x14004e48b  mov     [rbp+57h+psa], rax
0x14004e48f  mov     [rbp+57h+ppvData], r12
  ... truncated ...
```
