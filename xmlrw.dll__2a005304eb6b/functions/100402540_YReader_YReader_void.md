# YReader::~YReader(void)

- ea: `0x100402540`
- end: `0x100402a93`
- name: `??1YReader@@UEAA@XZ`
- size: `1363`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1004024a0`

## callees

- `0x100402540`
- `0x10040d780`
- `0x10040db80`
- `0x1004156b0`
- `0x100416ac0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10040270a`
- `KERNEL32!EnterCriticalSection` at `0x10040270a`
- `KERNEL32!LeaveCriticalSection` at `0x100402742`
- `KERNEL32!LeaveCriticalSection` at `0x100402742`
- `KERNEL32!HeapFree` at `0x1004025c2`
- `KERNEL32!HeapFree` at `0x100402612`
- `KERNEL32!HeapFree` at `0x100402662`
- `KERNEL32!HeapFree` at `0x1004026b2`
- `KERNEL32!HeapFree` at `0x1004027c1`
- `KERNEL32!HeapFree` at `0x100402820`
- `KERNEL32!HeapFree` at `0x10040287f`
- `KERNEL32!HeapFree` at `0x1004028d7`
- `KERNEL32!HeapFree` at `0x100402936`
- `KERNEL32!HeapFree` at `0x100402a01`
- `KERNEL32!HeapFree` at `0x100402a6e`
- `KERNEL32!HeapFree` at `0x1004025c2`
- `KERNEL32!HeapFree` at `0x100402612`
- `KERNEL32!HeapFree` at `0x100402662`
- `KERNEL32!HeapFree` at `0x1004026b2`
- `KERNEL32!HeapFree` at `0x1004027c1`
- `KERNEL32!HeapFree` at `0x100402820`
- `KERNEL32!HeapFree` at `0x10040287f`
- `KERNEL32!HeapFree` at `0x1004028d7`
- `KERNEL32!HeapFree` at `0x100402936`
- `KERNEL32!HeapFree` at `0x100402a01`
- `KERNEL32!HeapFree` at `0x100402a6e`

## pseudocode

```c
void __fastcall YReader::~YReader(YReader *this)
{
  void *v2; // r8
  struct IMalloc *v3; // rcx
  void *v4; // r8
  struct IMalloc *v5; // rcx
  void *v6; // r8
  struct IMalloc *v7; // rcx
  void *v8; // r8
  struct IMalloc *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  __int64 v13; // rcx
  char *v14; // r8
  struct IMalloc *v15; // rcx
  char *v16; // r8
  struct IMalloc *v17; // rcx
  char *v18; // r8
  struct IMalloc *v19; // rcx
  char *v20; // r8
  struct IMalloc *v21; // rcx
  char *v22; // r8
  struct IMalloc *v23; // rcx
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  char *v25; // r8
  struct IMalloc *v26; // rcx
  _QWORD *v27; // rdx
  __int64 v28; // rcx

  *(_QWORD *)this = &YReader::`vftable'{for `Base'};
  *((_QWORD *)this + 2) = &YReader::`vftable'{for `IInfoSetEntityLocator'};
  *((_QWORD *)this + 3) = &YReader::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 4) = &YReader::`vftable'{for `IInfoSetReader'};
  if ( *((_DWORD *)this + 430) != dword_100450B38 )
  {
    v2 = (void *)*((_QWORD *)this + 214);
    if ( v2 )
    {
      v3 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v3 || (v3 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, void *))v3->lpVtbl->Free)(v3, v2);
      else
        HeapFree(g_hHeap, 0, v2);
    }
  }
  if ( *((_DWORD *)this + 434) != dword_100450B38 )
  {
    v4 = (void *)*((_QWORD *)this + 216);
    if ( v4 )
    {
      v5 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v5 || (v5 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, _QWORD))v5->lpVtbl->Free)(v5, *((_QWORD *)this + 216));
      else
        HeapFree(g_hHeap, 0, v4);
    }
  }
  if ( *((_DWORD *)this + 438) != dword_100450B38 )
  {
    v6 = (void *)*((_QWORD *)this + 218);
    if ( v6 )
    {
      v7 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v7 || (v7 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, _QWORD))v7->lpVtbl->Free)(v7, *((_QWORD *)this + 218));
      else
        HeapFree(g_hHeap, 0, v6);
    }
  }
  if ( *((_DWORD *)this + 442) != dword_100450B38 )
  {
    v8 = (void *)*((_QWORD *)this + 220);
    if ( v8 )
    {
      v9 = (struct IMalloc *)*((_QWORD *)this + 1);
      if ( v9 || (v9 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, _QWORD))v9->lpVtbl->Free)(v9, *((_QWORD *)this + 220));
      else
        HeapFree(g_hHeap, 0, v8);
    }
  }
  LODWORD(v10) = *((_DWORD *)this + 118);
  while ( (_DWORD)v10 )
  {
    v11 = *((_QWORD *)this + 58);
    v10 = (unsigned int)(v10 - 1);
    *((_DWORD *)this + 118) = v10;
    v12 = *(void (__fastcall ****)(_QWORD, __int64))(v11 + 8 * v10);
    if ( v12 )
    {
      (**v12)(v12, 1);
      LODWORD(v10) = *((_DWORD *)this + 118);
    }
  }
  EnterCriticalSection(&s_cs);
  if ( !--s_cComponents && s_pMultiLanguage2 )
  {
    ((void (__fastcall *)(struct IMultiLanguage2 *))s_pMultiLanguage2->lpVtbl->Release)(s_pMultiLanguage2);
    s_pMultiLanguage2 = 0;
  }
  LeaveCriticalSection(&s_cs);
  v13 = *((_QWORD *)this + 1032);
  if ( v13 )
  {
    *((_QWORD *)this + 1032) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = (char *)*((_QWORD *)this + 1022);
  *((_QWORD *)this + 1020) = &_stack<unsigned int,16>::`vftable';
  if ( v14 && v14 != (char *)this + 0x2000 )
  {
    v15 = (struct IMalloc *)*((_QWORD *)this + 1021);
    if ( v15 || (v15 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v15->lpVtbl->Free)(v15, v14);
    else
      HeapFree(g_hHeap, 0, v14);
  }
  v16 = (char *)*((_QWORD *)this + 970);
  *((_QWORD *)this + 968) = &_stack<AttValueToken,16>::`vftable';
  if ( v16 && v16 != (char *)this + 7776 )
  {
    v17 = (struct IMalloc *)*((_QWORD *)this + 969);
    if ( v17 || (v17 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v17->lpVtbl->Free)(v17, v16);
    else
      HeapFree(g_hHeap, 0, v16);
  }
  v18 = (char *)*((_QWORD *)this + 662);
  *((_QWORD *)this + 660) = &_stack<Attribute,16>::`vftable';
  if ( v18 && v18 != (char *)this + 5312 )
  {
    v19 = (struct IMalloc *)*((_QWORD *)this + 661);
    if ( v19 || (v19 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v19->lpVtbl->Free)(v19, v18);
    else
      HeapFree(g_hHeap, 0, v18);
  }
  v20 = (char *)*((_QWORD *)this + 354);
  *((_QWORD *)this + 352) = &_stack<Attribute,16>::`vftable';
  if ( v20 && v20 != (char *)this + 2848 )
  {
    v21 = (struct IMalloc *)*((_QWORD *)this + 353);
    if ( v21 || (v21 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v21->lpVtbl->Free)(v21, v20);
    else
      HeapFree(g_hHeap, 0, v20);
  }
  v22 = (char *)*((_QWORD *)this + 235);
  *((_QWORD *)this + 233) = &_stack<YReader::Element,16>::`vftable';
  if ( v22 && v22 != (char *)this + 1896 )
  {
    v23 = (struct IMalloc *)*((_QWORD *)this + 234);
    if ( v23 || (v23 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v23->lpVtbl->Free)(v23, v22);
    else
      HeapFree(g_hHeap, 0, v22);
  }
  v24 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 187);
  *((_QWORD *)this + 157) = &DeclDoctype::`vftable';
  if ( v24 )
    (**v24)(v24, 1);
  _htable<DeclEntity>::~_htable<DeclEntity>((char *)this + 1456);
  _htable<DeclEntity>::~_htable<DeclEntity>((char *)this + 1416);
  _htable<DeclEntity>::~_htable<DeclEntity>((char *)this + 1376);
  _htable<DeclEntity>::~_htable<DeclEntity>((char *)this + 1336);
  DeclExternalId::~DeclExternalId((YReader *)((char *)this + 1256));
  NamespaceSupport::~NamespaceSupport((YReader *)((char *)this + 512));
  v25 = (char *)*((_QWORD *)this + 58);
  *((_QWORD *)this + 56) = &_stack<DeclAttDef *,4>::`vftable';
  if ( v25 && v25 != (char *)this + 480 )
  {
    v26 = (struct IMalloc *)*((_QWORD *)this + 57);
    if ( v26 || (v26 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, char *))v26->lpVtbl->Free)(v26, v25);
    else
      HeapFree(g_hHeap, 0, v25);
  }
  v27 = (_QWORD *)*((_QWORD *)this + 54);
  for ( *((_QWORD *)this + 52) = &BlockAlloc::`vftable'; v27; v27 = (_QWORD *)*((_QWORD *)this + 54) )
  {
    v28 = *((_QWORD *)this + 53);
    *((_QWORD *)this + 54) = v27[1];
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 40LL))(v28);
    }
    else if ( g_pMalloc )
    {
      ((void (__fastcall *)(struct IMalloc *))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    }
    else
    {
      HeapFree(g_hHeap, 0, v27);
    }
  }
  Scanner::~Scanner((YReader *)((char *)this + 40));
}

```

## disassembly

```asm
0x100402540  mov     [rsp+arg_0], rbx
0x100402545  push    rdi
0x100402546  sub     rsp, 20h
0x10040254a  lea     rax, ??_7YReader@@6BBase@@@; const YReader::`vftable'{for `Base'}
0x100402551  mov     rbx, rcx
0x100402554  mov     [rcx], rax
0x100402557  lea     rax, ??_7YReader@@6BIInfoSetEntityLocator@@@; const YReader::`vftable'{for `IInfoSetEntityLocator'}
0x10040255e  mov     [rcx+10h], rax
0x100402562  lea     rax, ??_7YReader@@6BISupportErrorInfo@@@; const YReader::`vftable'{for `ISupportErrorInfo'}
0x100402569  mov     [rcx+18h], rax
0x10040256d  lea     rax, ??_7YReader@@6BIInfoSetReader@@@; const YReader::`vftable'{for `IInfoSetReader'}
0x100402574  mov     [rcx+20h], rax
0x100402578  mov     eax, cs:dword_100450B38
0x10040257e  cmp     [rcx+6B8h], eax
0x100402584  jz      short loc_1004025C8
0x100402586  mov     r8, [rcx+6B0h]; lpMem
0x10040258d  test    r8, r8
0x100402590  jz      short loc_1004025C8
0x100402592  mov     rcx, [rcx+8]
0x100402596  test    rcx, rcx
0x100402599  jnz     short loc_1004025A7
0x10040259b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004025a2  test    rcx, rcx
0x1004025a5  jz      short loc_1004025B9
0x1004025a7  mov     rax, [rcx]
0x1004025aa  mov     rdx, r8
0x1004025ad  mov     rax, [rax+28h]
0x1004025b1  call    cs:__guard_dispatch_icall_fptr
0x1004025b7  jmp     short loc_1004025C8
0x1004025b9  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004025c0  xor     edx, edx; dwFlags
0x1004025c2  call    cs:__imp_HeapFree
0x1004025c8  mov     eax, cs:dword_100450B38
0x1004025ce  cmp     [rbx+6C8h], eax
0x1004025d4  jz      short loc_100402618
0x1004025d6  mov     r8, [rbx+6C0h]; lpMem
0x1004025dd  test    r8, r8
0x1004025e0  jz      short loc_100402618
0x1004025e2  mov     rcx, [rbx+8]
0x1004025e6  test    rcx, rcx
0x1004025e9  jnz     short loc_1004025F7
0x1004025eb  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004025f2  test    rcx, rcx
0x1004025f5  jz      short loc_100402609
0x1004025f7  mov     rax, [rcx]
0x1004025fa  mov     rdx, r8
0x1004025fd  mov     rax, [rax+28h]
0x100402601  call    cs:__guard_dispatch_icall_fptr
0x100402607  jmp     short loc_100402618
0x100402609  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100402610  xor     edx, edx; dwFlags
0x100402612  call    cs:__imp_HeapFree
0x100402618  mov     eax, cs:dword_100450B38
0x10040261e  cmp     [rbx+6D8h], eax
0x100402624  jz      short loc_100402668
0x100402626  mov     r8, [rbx+6D0h]; lpMem
0x10040262d  test    r8, r8
0x100402630  jz      short loc_100402668
0x100402632  mov     rcx, [rbx+8]
0x100402636  test    rcx, rcx
0x100402639  jnz     short loc_100402647
0x10040263b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100402642  test    rcx, rcx
0x100402645  jz      short loc_100402659
0x100402647  mov     rax, [rcx]
0x10040264a  mov     rdx, r8
0x10040264d  mov     rax, [rax+28h]
0x100402651  call    cs:__guard_dispatch_icall_fptr
0x100402657  jmp     short loc_100402668
0x100402659  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100402660  xor     edx, edx; dwFlags
0x100402662  call    cs:__imp_HeapFree
0x100402668  mov     eax, cs:dword_100450B38
0x10040266e  cmp     [rbx+6E8h], eax
0x100402674  jz      short loc_1004026B8
0x100402676  mov     r8, [rbx+6E0h]; lpMem
0x10040267d  test    r8, r8
0x100402680  jz      short loc_1004026B8
0x100402682  mov     rcx, [rbx+8]
0x100402686  test    rcx, rcx
0x100402689  jnz     short loc_100402697
0x10040268b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100402692  test    rcx, rcx
0x100402695  jz      short loc_1004026A9
0x100402697  mov     rax, [rcx]
0x10040269a  mov     rdx, r8
0x10040269d  mov     rax, [rax+28h]
0x1004026a1  call    cs:__guard_dispatch_icall_fptr
0x1004026a7  jmp     short loc_1004026B8
0x1004026a9  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004026b0  xor     edx, edx; dwFlags
0x1004026b2  call    cs:__imp_HeapFree
0x1004026b8  mov     edx, [rbx+1D8h]
0x1004026be  test    edx, edx
0x1004026c0  jz      short loc_100402703
0x1004026c2  nop     dword ptr [rax+00h]
0x1004026c6  nop     word ptr [rax+rax+00000000h]
0x1004026d0  mov     rax, [rbx+1D0h]
0x1004026d7  dec     edx
0x1004026d9  mov     [rbx+1D8h], edx
0x1004026df  mov     rcx, [rax+rdx*8]
0x1004026e3  test    rcx, rcx
0x1004026e6  jz      short loc_1004026FF
0x1004026e8  mov     rax, [rcx]
0x1004026eb  mov     edx, 1
0x1004026f0  mov     rax, [rax]
0x1004026f3  call    cs:__guard_dispatch_icall_fptr
0x1004026f9  mov     edx, [rbx+1D8h]
0x1004026ff  test    edx, edx
0x100402701  jnz     short loc_1004026D0
0x100402703  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040270a  call    cs:__imp_EnterCriticalSection
0x100402710  xor     edi, edi
0x100402712  sub     cs:?s_cComponents@@3JA, 1; long s_cComponents
0x100402719  jnz     short loc_10040273B
0x10040271b  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100402722  test    rcx, rcx
0x100402725  jz      short loc_10040273B
0x100402727  mov     rax, [rcx]
0x10040272a  mov     rax, [rax+10h]
0x10040272e  call    cs:__guard_dispatch_icall_fptr
0x100402734  mov     cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rdi; IMultiLanguage2 * s_pMultiLanguage2
0x10040273b  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100402742  call    cs:__imp_LeaveCriticalSection
0x100402748  mov     rcx, [rbx+2040h]
0x10040274f  test    rcx, rcx
0x100402752  jz      short loc_100402768
0x100402754  mov     [rbx+2040h], rdi
0x10040275b  mov     rax, [rcx]
0x10040275e  mov     rax, [rax+10h]
0x100402762  call    cs:__guard_dispatch_icall_fptr
0x100402768  mov     r8, [rbx+1FF0h]; lpMem
0x10040276f  lea     rax, ??_7?$_stack@I$0BA@@@6B@; const _stack<uint,16>::`vftable'
0x100402776  mov     [rbx+1FE0h], rax
0x10040277d  test    r8, r8
0x100402780  jz      short loc_1004027C7
0x100402782  lea     rax, [rbx+2000h]
0x100402789  cmp     r8, rax
0x10040278c  jz      short loc_1004027C7
0x10040278e  mov     rcx, [rbx+1FE8h]
0x100402795  test    rcx, rcx
0x100402798  jnz     short loc_1004027A6
0x10040279a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004027a1  test    rcx, rcx
0x1004027a4  jz      short loc_1004027B8
0x1004027a6  mov     rax, [rcx]
0x1004027a9  mov     rdx, r8
0x1004027ac  mov     rax, [rax+28h]
0x1004027b0  call    cs:__guard_dispatch_icall_fptr
0x1004027b6  jmp     short loc_1004027C7
0x1004027b8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004027bf  xor     edx, edx; dwFlags
0x1004027c1  call    cs:__imp_HeapFree
0x1004027c7  mov     r8, [rbx+1E50h]; lpMem
0x1004027ce  lea     rax, ??_7?$_stack@UAttValueToken@@$0BA@@@6B@; const _stack<AttValueToken,16>::`vftable'
0x1004027d5  mov     [rbx+1E40h], rax
0x1004027dc  test    r8, r8
0x1004027df  jz      short loc_100402826
0x1004027e1  lea     rax, [rbx+1E60h]
0x1004027e8  cmp     r8, rax
0x1004027eb  jz      short loc_100402826
0x1004027ed  mov     rcx, [rbx+1E48h]
0x1004027f4  test    rcx, rcx
0x1004027f7  jnz     short loc_100402805
0x1004027f9  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100402800  test    rcx, rcx
0x100402803  jz      short loc_100402817
0x100402805  mov     rax, [rcx]
0x100402808  mov     rdx, r8
0x10040280b  mov     rax, [rax+28h]
0x10040280f  call    cs:__guard_dispatch_icall_fptr
0x100402815  jmp     short loc_100402826
0x100402817  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040281e  xor     edx, edx; dwFlags
0x100402820  call    cs:__imp_HeapFree
0x100402826  mov     r8, [rbx+14B0h]; lpMem
0x10040282d  lea     rdi, ??_7?$_stack@UAttribute@@$0BA@@@6B@; const _stack<Attribute,16>::`vftable'
0x100402834  mov     [rbx+14A0h], rdi
0x10040283b  test    r8, r8
0x10040283e  jz      short loc_100402885
0x100402840  lea     rax, [rbx+14C0h]
0x100402847  cmp     r8, rax
0x10040284a  jz      short loc_100402885
0x10040284c  mov     rcx, [rbx+14A8h]
0x100402853  test    rcx, rcx
0x100402856  jnz     short loc_100402864
0x100402858  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040285f  test    rcx, rcx
0x100402862  jz      short loc_100402876
0x100402864  mov     rax, [rcx]
0x100402867  mov     rdx, r8
0x10040286a  mov     rax, [rax+28h]
0x10040286e  call    cs:__guard_dispatch_icall_fptr
0x100402874  jmp     short loc_100402885
0x100402876  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040287d  xor     edx, edx; dwFlags
0x10040287f  call    cs:__imp_HeapFree
0x100402885  mov     r8, [rbx+0B10h]; lpMem
0x10040288c  mov     [rbx+0B00h], rdi
0x100402893  test    r8, r8
0x100402896  jz      short loc_1004028DD
0x100402898  lea     rax, [rbx+0B20h]
0x10040289f  cmp     r8, rax
0x1004028a2  jz      short loc_1004028DD
0x1004028a4  mov     rcx, [rbx+0B08h]
0x1004028ab  test    rcx, rcx
0x1004028ae  jnz     short loc_1004028BC
0x1004028b0  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004028b7  test    rcx, rcx
0x1004028ba  jz      short loc_1004028CE
0x1004028bc  mov     rax, [rcx]
0x1004028bf  mov     rdx, r8
0x1004028c2  mov     rax, [rax+28h]
0x1004028c6  call    cs:__guard_dispatch_icall_fptr
0x1004028cc  jmp     short loc_1004028DD
0x1004028ce  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004028d5  xor     edx, edx; dwFlags
0x1004028d7  call    cs:__imp_HeapFree
0x1004028dd  mov     r8, [rbx+758h]; lpMem
0x1004028e4  lea     rax, ??_7?$_stack@UElement@YReader@@$0BA@@@6B@; const _stack<YReader::Element,16>::`vftable'
0x1004028eb  mov     [rbx+748h], rax
0x1004028f2  test    r8, r8
0x1004028f5  jz      short loc_10040293C
0x1004028f7  lea     rax, [rbx+768h]
0x1004028fe  cmp     r8, rax
0x100402901  jz      short loc_10040293C
0x100402903  mov     rcx, [rbx+750h]
0x10040290a  test    rcx, rcx
0x10040290d  jnz     short loc_10040291B
0x10040290f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100402916  test    rcx, rcx
0x100402919  jz      short loc_10040292D
0x10040291b  mov     rax, [rcx]
0x10040291e  mov     rdx, r8
0x100402921  mov     rax, [rax+28h]
0x100402925  call    cs:__guard_dispatch_icall_fptr
0x10040292b  jmp     short loc_10040293C
0x10040292d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100402934  xor     edx, edx; dwFlags
0x100402936  call    cs:__imp_HeapFree
0x10040293c  mov     rcx, [rbx+5D8h]
0x100402943  lea     rdi, [rbx+4E8h]
0x10040294a  lea     rax, ??_7DeclDoctype@@6B@; const DeclDoctype::`vftable'
0x100402951  mov     [rdi], rax
0x100402954  test    rcx, rcx
0x100402957  jz      short loc_10040296A
0x100402959  mov     rax, [rcx]
0x10040295c  mov     edx, 1
0x100402961  mov     rax, [rax]
0x100402964  call    cs:__guard_dispatch_icall_fptr
0x10040296a  lea     rcx, [rdi+0C8h]
0x100402971  call    ??1?$_htable@VDeclEntity@@@@UEAA@XZ; _htable<DeclEntity>::~_htable<DeclEntity>(void)
0x100402976  lea     rcx, [rdi+0A0h]
0x10040297d  call    ??1?$_htable@VDeclEntity@@@@UEAA@XZ; _htable<DeclEntity>::~_htable<DeclEntity>(void)
0x100402982  lea     rcx, [rdi+78h]
0x100402986  call    ??1?$_htable@VDeclEntity@@@@UEAA@XZ; _htable<DeclEntity>::~_htable<DeclEntity>(void)
0x10040298b  lea     rcx, [rdi+50h]
0x10040298f  call    ??1?$_htable@VDeclEntity@@@@UEAA@XZ; _htable<DeclEntity>::~_htable<DeclEntity>(void)
0x100402994  mov     rcx, rdi; this
0x100402997  call    ??1DeclExternalId@@UEAA@XZ; DeclExternalId::~DeclExternalId(void)
0x10040299c  lea     rcx, [rbx+200h]; this
0x1004029a3  call    ??1NamespaceSupport@@UEAA@XZ; NamespaceSupport::~NamespaceSupport(void)
0x1004029a8  mov     r8, [rbx+1D0h]; lpMem
0x1004029af  lea     rax, ??_7?$_stack@PEAVDeclAttDef@@$03@@6B@; const _stack<DeclAttDef *,4>::`vftable'
0x1004029b6  mov     [rbx+1C0h], rax
0x1004029bd  test    r8, r8
0x1004029c0  jz      short loc_100402A07
0x1004029c2  lea     rax, [rbx+1E0h]
0x1004029c9  cmp     r8, rax
0x1004029cc  jz      short loc_100402A07
0x1004029ce  mov     rcx, [rbx+1C8h]
0x1004029d5  test    rcx, rcx
0x1004029d8  jnz     short loc_1004029E6
0x1004029da  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004029e1  test    rcx, rcx
0x1004029e4  jz      short loc_1004029F8
0x1004029e6  mov     rax, [rcx]
0x1004029e9  mov     rdx, r8
0x1004029ec  mov     rax, [rax+28h]
0x1004029f0  call    cs:__guard_dispatch_icall_fptr
0x1004029f6  jmp     short loc_100402A07
0x1004029f8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004029ff  xor     edx, edx; dwFlags
0x100402a01  call    cs:__imp_HeapFree
0x100402a07  mov     rdx, [rbx+1B0h]
0x100402a0e  lea     rax, ??_7BlockAlloc@@6B@; const BlockAlloc::`vftable'
0x100402a15  mov     [rbx+1A0h], rax
0x100402a1c  test    rdx, rdx
0x100402a1f  jz      short loc_100402A80
0x100402a21  mov     rcx, [rbx+1A8h]
0x100402a28  mov     rax, [rdx+8]
0x100402a2c  mov     [rbx+1B0h], rax
0x100402a33  test    rcx, rcx
0x100402a36  jz      short loc_100402A47
0x100402a38  mov     rax, [rcx]
0x100402a3b  mov     rax, [rax+28h]
0x100402a3f  call    cs:__guard_dispatch_icall_fptr
0x100402a45  jmp     short loc_100402A74
0x100402a47  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100402a4e  test    rcx, rcx
  ... truncated ...
```
