# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002b490`
- end: `0x18002baca`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1594`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, unsigned __int8, OLECHAR *psz, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bad0`

## callees

- `0x180001d66`
- `0x1800085b8`
- `0x18000e390`
- `0x18002b490`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!malloc` at `0x18002b81f`
- `msvcrt!malloc` at `0x18002b91d`
- `msvcrt!malloc` at `0x18002b81f`
- `msvcrt!malloc` at `0x18002b91d`
- `msvcrt!free` at `0x18002b809`
- `msvcrt!free` at `0x18002b906`
- `msvcrt!free` at `0x18002b809`
- `msvcrt!free` at `0x18002b906`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b52b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b52b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b565`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b70b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b79a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b565`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b70b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b79a`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        struct IQueryRecentWinSATAssessment *a2,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 a3,
        char a4,
        OLECHAR *psz,
        union _LARGE_INTEGER a6,
        unsigned int a7,
        __int16 a8)
{
  void *v12; // rdi
  struct IQueryRecentWinSATAssessmentVtbl *lpVtbl; // r13
  OLECHAR *v14; // rbx
  BSTR v15; // rdx
  BSTR v16; // rax
  int v17; // r12d
  __int64 v18; // rcx
  int v19; // ebx
  int v20; // ebx
  __int64 v21; // r8
  volatile signed __int32 *v22; // rbx
  unsigned int v23; // edi
  void *v24; // rax
  unsigned int (__fastcall *v25)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD); // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v26; // rax
  unsigned int v27; // edi
  __int64 v28; // r12
  unsigned int v29; // r12d
  void *v30; // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v31; // rcx
  unsigned int v32; // [rsp+50h] [rbp-E8h] BYREF
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v33; // [rsp+54h] [rbp-E4h]
  __int64 v34; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD *v35; // [rsp+60h] [rbp-D8h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-D0h] BYREF
  void *Src; // [rsp+70h] [rbp-C8h] BYREF
  BSTR v38; // [rsp+78h] [rbp-C0h]
  __int64 v39; // [rsp+80h] [rbp-B8h]
  _WORD v40[2]; // [rsp+90h] [rbp-A8h] BYREF
  char v41; // [rsp+94h] [rbp-A4h]
  char v42; // [rsp+95h] [rbp-A3h]
  __int16 v43; // [rsp+96h] [rbp-A2h]
  union _LARGE_INTEGER v44; // [rsp+A0h] [rbp-98h]
  __int128 v45; // [rsp+A8h] [rbp-90h]
  __int64 v46; // [rsp+D8h] [rbp-60h]
  unsigned int v47; // [rsp+E0h] [rbp-58h]
  unsigned int v48; // [rsp+E4h] [rbp-54h]

  v39 = -2;
  v33 = a3;
  if ( !a2 )
    return 2147500035LL;
  v12 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Src = v12;
  v34 = 0;
  v35 = 0;
  lpVtbl = a2->lpVtbl;
  if ( psz )
  {
    v16 = SysAllocString(psz);
    v14 = v16;
    v38 = v16;
    if ( !v16 )
      ATL::AtlThrowImpl(-2147024882);
    v15 = v16;
  }
  else
  {
    v14 = 0;
    v38 = 0;
    v15 = 0;
  }
  v17 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, BSTR, _QWORD, __int64 *))lpVtbl->get_XML)(
          a2,
          v15,
          0,
          &v34);
  SysFreeString(v14);
  if ( v17 < 0 )
  {
    if ( v35 )
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v17;
  }
  v18 = v34;
  if ( !v34 )
  {
    if ( v35 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
      v18 = v34;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return 1;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v34 + 72LL))(v34, &v35);
  if ( v19 < 0 )
  {
    if ( v35 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v35 + 16LL))(v35, *v35);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v19;
  }
  if ( !v35 )
  {
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return 1;
  }
  bstrString = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v35 + 272LL))(v35, &bstrString);
  if ( v20 < 0 )
  {
    SysFreeString(bstrString);
    if ( v35 )
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v20;
  }
  if ( bstrString )
  {
    v21 = -1;
    do
      ++v21;
    while ( bstrString[v21] );
  }
  else
  {
    LODWORD(v21) = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&Src, bstrString, v21);
  SysFreeString(bstrString);
  if ( v35 )
    (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  v22 = (volatile signed __int32 *)Src;
  v23 = 2 * *((_DWORD *)Src - 4) + 2;
  v32 = 0;
  if ( v23 < 8 || *((_BYTE *)this + 33) )
    goto LABEL_71;
  if ( *((_DWORD *)this + 20) < v23 - 8 )
  {
    free(*((void **)this + 9));
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    v24 = malloc(v23);
    *((_QWORD *)this + 9) = v24;
    if ( !v24 )
    {
LABEL_73:
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 2147942414LL;
    }
    *((_DWORD *)this + 20) = v23;
  }
  v25 = (unsigned int (__fastcall *)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD))*((_QWORD *)this + 5);
  if ( !v25
    || v25(258, v22, v23, *((_QWORD *)this + 9) + 8LL, v23 - 8, 4096, &v32, *((_QWORD *)this + 7))
    || v32 > v23 - 8 )
  {
LABEL_71:
    v29 = v23 + 4;
    if ( *((_DWORD *)this + 24) < v23 + 4 )
    {
      free(*((void **)this + 11));
      *((_QWORD *)this + 11) = 0;
      *((_DWORD *)this + 24) = 0;
      v30 = malloc(v29);
      *((_QWORD *)this + 11) = v30;
      if ( !v30 )
        goto LABEL_73;
      *((_DWORD *)this + 24) = v29;
    }
    v31 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 11);
    *v31 = v33;
    memcpy_0(v31 + 1, (const void *)v22, v23);
    v28 = *((_QWORD *)this + 11);
    v27 = *((_DWORD *)this + 24);
LABEL_78:
    if ( v27 < 0xFFFF )
    {
      memset_0(v40, 0, 0x58u);
      v40[0] = a8;
      v44 = a6;
      v45 = *(_OWORD *)WinSATAssessmentGuid;
      v41 = a4;
      v43 = 0;
      v42 = 0;
      v46 = v28;
      v47 = v27;
      v48 = a7;
      (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
        *((_QWORD *)this + 2),
        v40,
        0,
        0);
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 0;
    }
    else
    {
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 1;
    }
  }
  v32 += 8;
  switch ( a4 )
  {
    case ' ':
      a4 = 33;
      goto LABEL_70;
    case '"':
      a4 = 35;
      goto LABEL_70;
    case '$':
      a4 = 37;
LABEL_70:
      v26 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 9);
      *v26 = v33;
      *((_DWORD *)v26 + 1) = v23;
      v27 = v32;
      v28 = *((_QWORD *)this + 9);
      goto LABEL_78;
  }
  if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
  return 2147500033LL;
}

```

## disassembly

```asm
0x18002b490  push    rbx
0x18002b492  push    rsi
0x18002b493  push    rdi
0x18002b494  push    r12
0x18002b496  push    r13
0x18002b498  push    r14
0x18002b49a  push    r15
0x18002b49c  sub     rsp, 100h
0x18002b4a3  mov     [rsp+138h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18002b4af  mov     rax, cs:__security_cookie
0x18002b4b6  xor     rax, rsp
0x18002b4b9  mov     [rsp+138h+var_48], rax
0x18002b4c1  mov     r15b, r9b
0x18002b4c4  mov     [rsp+138h+var_E4], r8d
0x18002b4c9  mov     r12, rdx
0x18002b4cc  mov     r14, rcx
0x18002b4cf  mov     rbx, [rsp+138h+psz]
0x18002b4d7  xor     esi, esi
0x18002b4d9  test    rdx, rdx
0x18002b4dc  jnz     short loc_18002B4E8
0x18002b4de  mov     eax, 80004003h
0x18002b4e3  jmp     loc_18002BA9A
0x18002b4e8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002b4ef  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002b4f6  mov     rax, [rax+18h]
0x18002b4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4ff  lea     rdi, [rax+18h]
0x18002b503  mov     [rsp+138h+Src], rdi
0x18002b508  mov     [rsp+138h+var_E0], rsi
0x18002b50d  mov     [rsp+138h+var_D8], rsi
0x18002b512  mov     r13, [r12]
0x18002b516  test    rbx, rbx
0x18002b519  jnz     short loc_18002B528
0x18002b51b  mov     rbx, rsi
0x18002b51e  mov     [rsp+138h+var_C0], rbx
0x18002b523  mov     rdx, rsi
0x18002b526  jmp     short loc_18002B54B
0x18002b528  mov     rcx, rbx; psz
0x18002b52b  call    cs:__imp_SysAllocString
0x18002b532  nop     dword ptr [rax+rax+00h]
0x18002b537  mov     rbx, rax
0x18002b53a  mov     [rsp+138h+var_C0], rax
0x18002b53f  test    rax, rax
0x18002b542  jz      loc_18002BABE
0x18002b548  mov     rdx, rax
0x18002b54b  lea     r9, [rsp+138h+var_E0]
0x18002b550  xor     r8d, r8d
0x18002b553  mov     rcx, r12
0x18002b556  mov     rax, [r13+38h]
0x18002b55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b55f  mov     r12d, eax
0x18002b562  mov     rcx, rbx; bstrString
0x18002b565  call    cs:__imp_SysFreeString
0x18002b56c  nop     dword ptr [rax+rax+00h]
0x18002b571  test    r12d, r12d
0x18002b574  jns     short loc_18002B5CC
0x18002b576  mov     rcx, [rsp+138h+var_D8]
0x18002b57b  test    rcx, rcx
0x18002b57e  jz      short loc_18002B58D
0x18002b580  mov     rax, [rcx]
0x18002b583  mov     rax, [rax+10h]
0x18002b587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b58c  nop
0x18002b58d  mov     rcx, [rsp+138h+var_E0]
0x18002b592  test    rcx, rcx
0x18002b595  jz      short loc_18002B5A4
0x18002b597  mov     rax, [rcx]
0x18002b59a  mov     rax, [rax+10h]
0x18002b59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5a3  nop
0x18002b5a4  lea     rdx, [rdi-18h]
0x18002b5a8  or      eax, 0FFFFFFFFh
0x18002b5ab  lock xadd [rdx+10h], eax
0x18002b5b0  sub     eax, 1
0x18002b5b3  jg      short loc_18002B5C4
0x18002b5b5  mov     rcx, [rdx]
0x18002b5b8  mov     rax, [rcx]
0x18002b5bb  mov     rax, [rax+8]
0x18002b5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5c4  mov     eax, r12d
0x18002b5c7  jmp     loc_18002BA9A
0x18002b5cc  mov     rcx, [rsp+138h+var_E0]
0x18002b5d1  test    rcx, rcx
0x18002b5d4  jnz     short loc_18002B630
0x18002b5d6  mov     rdx, [rsp+138h+var_D8]
0x18002b5db  test    rdx, rdx
0x18002b5de  jz      short loc_18002B5F4
0x18002b5e0  mov     rax, [rdx]
0x18002b5e3  mov     rcx, rdx
0x18002b5e6  mov     rax, [rax+10h]
0x18002b5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5ef  mov     rcx, [rsp+138h+var_E0]
0x18002b5f4  test    rcx, rcx
0x18002b5f7  jz      short loc_18002B606
0x18002b5f9  mov     rax, [rcx]
0x18002b5fc  mov     rax, [rax+10h]
0x18002b600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b605  nop
0x18002b606  lea     rdx, [rdi-18h]
0x18002b60a  or      eax, 0FFFFFFFFh
0x18002b60d  lock xadd [rdx+10h], eax
0x18002b612  sub     eax, 1
0x18002b615  jg      short loc_18002B626
0x18002b617  mov     rcx, [rdx]
0x18002b61a  mov     rax, [rcx]
0x18002b61d  mov     rax, [rax+8]
0x18002b621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b626  mov     eax, 1
0x18002b62b  jmp     loc_18002BA9A
0x18002b630  mov     rax, [rcx]
0x18002b633  lea     rdx, [rsp+138h+var_D8]
0x18002b638  mov     rax, [rax+48h]
0x18002b63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b641  mov     ebx, eax
0x18002b643  test    eax, eax
0x18002b645  jns     short loc_18002B69C
0x18002b647  mov     rcx, [rsp+138h+var_D8]
0x18002b64c  test    rcx, rcx
0x18002b64f  jz      short loc_18002B65E
0x18002b651  mov     rdx, [rcx]
0x18002b654  mov     rax, [rdx+10h]
0x18002b658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b65d  nop
0x18002b65e  mov     rcx, [rsp+138h+var_E0]
0x18002b663  test    rcx, rcx
0x18002b666  jz      short loc_18002B675
0x18002b668  mov     rax, [rcx]
0x18002b66b  mov     rax, [rax+10h]
0x18002b66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b674  nop
0x18002b675  lea     rdx, [rdi-18h]
0x18002b679  or      eax, 0FFFFFFFFh
0x18002b67c  lock xadd [rdx+10h], eax
0x18002b681  sub     eax, 1
0x18002b684  jg      short loc_18002B695
0x18002b686  mov     rcx, [rdx]
0x18002b689  mov     rax, [rcx]
0x18002b68c  mov     rax, [rax+8]
0x18002b690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b695  mov     eax, ebx
0x18002b697  jmp     loc_18002BA9A
0x18002b69c  mov     rcx, [rsp+138h+var_D8]
0x18002b6a1  test    rcx, rcx
0x18002b6a4  jnz     short loc_18002B6E7
0x18002b6a6  mov     rcx, [rsp+138h+var_E0]
0x18002b6ab  test    rcx, rcx
0x18002b6ae  jz      short loc_18002B6BD
0x18002b6b0  mov     rax, [rcx]
0x18002b6b3  mov     rax, [rax+10h]
0x18002b6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6bc  nop
0x18002b6bd  lea     rdx, [rdi-18h]
0x18002b6c1  or      eax, 0FFFFFFFFh
0x18002b6c4  lock xadd [rdx+10h], eax
0x18002b6c9  sub     eax, 1
0x18002b6cc  jg      short loc_18002B6DD
0x18002b6ce  mov     rcx, [rdx]
0x18002b6d1  mov     rax, [rcx]
0x18002b6d4  mov     rax, [rax+8]
0x18002b6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6dd  mov     eax, 1
0x18002b6e2  jmp     loc_18002BA9A
0x18002b6e7  mov     [rsp+138h+bstrString], rsi
0x18002b6ec  mov     rax, [rcx]
0x18002b6ef  lea     rdx, [rsp+138h+bstrString]
0x18002b6f4  mov     rax, [rax+110h]
0x18002b6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b700  mov     ebx, eax
0x18002b702  test    eax, eax
0x18002b704  jns     short loc_18002B76D
0x18002b706  mov     rcx, [rsp+138h+bstrString]; bstrString
0x18002b70b  call    cs:__imp_SysFreeString
0x18002b712  nop     dword ptr [rax+rax+00h]
0x18002b717  nop
0x18002b718  mov     rcx, [rsp+138h+var_D8]
0x18002b71d  test    rcx, rcx
0x18002b720  jz      short loc_18002B72F
0x18002b722  mov     rax, [rcx]
0x18002b725  mov     rax, [rax+10h]
0x18002b729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b72e  nop
0x18002b72f  mov     rcx, [rsp+138h+var_E0]
0x18002b734  test    rcx, rcx
0x18002b737  jz      short loc_18002B746
0x18002b739  mov     rax, [rcx]
0x18002b73c  mov     rax, [rax+10h]
0x18002b740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b745  nop
0x18002b746  lea     rdx, [rdi-18h]
0x18002b74a  or      eax, 0FFFFFFFFh
0x18002b74d  lock xadd [rdx+10h], eax
0x18002b752  sub     eax, 1
0x18002b755  jg      short loc_18002B766
0x18002b757  mov     rcx, [rdx]
0x18002b75a  mov     rax, [rcx]
0x18002b75d  mov     rax, [rax+8]
0x18002b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b766  mov     eax, ebx
0x18002b768  jmp     loc_18002BA9A
0x18002b76d  mov     rdx, [rsp+138h+bstrString]
0x18002b772  test    rdx, rdx
0x18002b775  jnz     short loc_18002B77C
0x18002b777  mov     r8d, esi
0x18002b77a  jmp     short loc_18002B78A
0x18002b77c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b780  inc     r8
0x18002b783  cmp     [rdx+r8*2], si
0x18002b788  jnz     short loc_18002B780
0x18002b78a  lea     rcx, [rsp+138h+Src]
0x18002b78f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002b794  nop
0x18002b795  mov     rcx, [rsp+138h+bstrString]; bstrString
0x18002b79a  call    cs:__imp_SysFreeString
0x18002b7a1  nop     dword ptr [rax+rax+00h]
0x18002b7a6  nop
0x18002b7a7  mov     rcx, [rsp+138h+var_D8]
0x18002b7ac  test    rcx, rcx
0x18002b7af  jz      short loc_18002B7BE
0x18002b7b1  mov     rax, [rcx]
0x18002b7b4  mov     rax, [rax+10h]
0x18002b7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7bd  nop
0x18002b7be  mov     rcx, [rsp+138h+var_E0]
0x18002b7c3  test    rcx, rcx
0x18002b7c6  jz      short loc_18002B7D5
0x18002b7c8  mov     rax, [rcx]
0x18002b7cb  mov     rax, [rax+10h]
0x18002b7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7d4  nop
0x18002b7d5  mov     rbx, [rsp+138h+Src]
0x18002b7da  mov     eax, [rbx-10h]
0x18002b7dd  lea     edi, ds:2[rax*2]
0x18002b7e4  mov     [rsp+138h+var_E8], esi
0x18002b7e8  cmp     edi, 8
0x18002b7eb  jb      loc_18002B8F8
0x18002b7f1  cmp     [r14+21h], sil
0x18002b7f5  jnz     loc_18002B8F8
0x18002b7fb  lea     r12d, [rdi-8]
0x18002b7ff  cmp     [r14+50h], r12d
0x18002b803  jnb     short loc_18002B83C
0x18002b805  mov     rcx, [r14+48h]; Block
0x18002b809  call    cs:__imp_free
0x18002b810  nop     dword ptr [rax+rax+00h]
0x18002b815  mov     [r14+48h], rsi
0x18002b819  mov     [r14+50h], esi
0x18002b81d  mov     ecx, edi; Size
0x18002b81f  call    cs:__imp_malloc
0x18002b826  nop     dword ptr [rax+rax+00h]
0x18002b82b  mov     [r14+48h], rax
0x18002b82f  test    rax, rax
0x18002b832  jz      loc_18002B932
0x18002b838  mov     [r14+50h], edi
0x18002b83c  mov     rax, [r14+28h]
0x18002b840  test    rax, rax
0x18002b843  jz      loc_18002B8F8
0x18002b849  mov     r9, [r14+48h]
0x18002b84d  add     r9, 8
0x18002b851  mov     ecx, 102h
0x18002b856  mov     rdx, [r14+38h]
0x18002b85a  mov     [rsp+138h+var_100], rdx
0x18002b85f  lea     rdx, [rsp+138h+var_E8]
0x18002b864  mov     [rsp+138h+var_108], rdx
0x18002b869  mov     [rsp+138h+var_110], 1000h
0x18002b871  mov     [rsp+138h+var_118], r12d
0x18002b876  mov     r8d, edi
0x18002b879  mov     rdx, rbx
0x18002b87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b881  test    eax, eax
0x18002b883  jnz     short loc_18002B8F8
0x18002b885  mov     eax, [rsp+138h+var_E8]
0x18002b889  cmp     eax, r12d
0x18002b88c  ja      short loc_18002B8F8
0x18002b88e  add     eax, 8
0x18002b891  mov     [rsp+138h+var_E8], eax
0x18002b895  cmp     r15b, 20h ; ' '
0x18002b899  jz      short loc_18002B8DB
0x18002b89b  cmp     r15b, 22h ; '"'
0x18002b89f  jz      short loc_18002B8D6
0x18002b8a1  cmp     r15b, 24h ; '$'
0x18002b8a5  jnz     short loc_18002B8AC
0x18002b8a7  mov     r15b, 25h ; '%'
0x18002b8aa  jmp     short loc_18002B8DE
0x18002b8ac  lea     rdx, [rbx-18h]
0x18002b8b0  or      eax, 0FFFFFFFFh
0x18002b8b3  lock xadd [rdx+10h], eax
0x18002b8b8  sub     eax, 1
0x18002b8bb  jg      short loc_18002B8CC
0x18002b8bd  mov     rcx, [rdx]
0x18002b8c0  mov     rax, [rcx]
0x18002b8c3  mov     rax, [rax+8]
0x18002b8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8cc  mov     eax, 80004001h
0x18002b8d1  jmp     loc_18002BA9A
0x18002b8d6  mov     r15b, 23h ; '#'
0x18002b8d9  jmp     short loc_18002B8DE
0x18002b8db  mov     r15b, 21h ; '!'
0x18002b8de  mov     rax, [r14+48h]
0x18002b8e2  mov     edx, [rsp+138h+var_E4]
0x18002b8e6  mov     [rax], edx
0x18002b8e8  mov     [rax+4], edi
  ... truncated ...
```
