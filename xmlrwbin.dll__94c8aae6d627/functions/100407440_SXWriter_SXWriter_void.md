# SXWriter::~SXWriter(void)

- ea: `0x100407440`
- end: `0x100407659`
- name: `??1SXWriter@@MEAA@XZ`
- size: `537`
- prototype: `void __fastcall(SXWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100407670`

## callees

- `0x100407330`
- `0x100407440`
- `0x100407710`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1004075de`
- `KERNEL32!EnterCriticalSection` at `0x1004075de`
- `KERNEL32!LeaveCriticalSection` at `0x100407618`
- `KERNEL32!LeaveCriticalSection` at `0x100407618`
- `KERNEL32!HeapFree` at `0x100407512`
- `KERNEL32!HeapFree` at `0x100407554`
- `KERNEL32!HeapFree` at `0x100407512`
- `KERNEL32!HeapFree` at `0x100407554`

## pseudocode

```c
void __fastcall SXWriter::~SXWriter(SXWriter *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void *v3; // r8
  struct IMalloc *v4; // rcx
  void *v5; // r8
  struct IMalloc *v6; // rcx
  __int64 v7; // rcx
  WriterHandleEntry *v8; // rbx
  unsigned int v9; // eax
  WriterHandleEntry *v10; // rsi
  __int64 v11; // rcx

  *(_QWORD *)this = &SXWriter::`vftable'{for `Base'};
  *((_QWORD *)this + 2) = &SXWriter::`vftable'{for `ISXFormatWriter'};
  *((_QWORD *)this + 3) = &SXWriter::`vftable'{for `ISXFormatContentHandler'};
  *((_QWORD *)this + 4) = &SXWriter::`vftable'{for `ISAXLexicalHandler'};
  *((_QWORD *)this + 5) = &SXWriter::`vftable'{for `ISAXDeclHandler'};
  *((_QWORD *)this + 6) = &SXWriter::`vftable'{for `ISAXDTDHandler'};
  *((_QWORD *)this + 7) = &SXWriter::`vftable'{for `ISAXErrorHandler'};
  *((_QWORD *)this + 8) = &SXWriter::`vftable'{for `IMXSXAttributeWriter'};
  *((_QWORD *)this + 9) = &SXWriter::`vftable'{for `ISXNametable'};
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 33);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (void *)*((_QWORD *)this + 43);
  if ( v3 )
  {
    v4 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v4 || (v4 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v4->lpVtbl->Free)(v4, *((_QWORD *)this + 43));
    else
      HeapFree(g_hHeap, 0, v3);
  }
  v5 = (void *)*((_QWORD *)this + 36);
  if ( v5 )
  {
    v6 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v6 || (v6 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v6->lpVtbl->Free)(v6, *((_QWORD *)this + 36));
    else
      HeapFree(g_hHeap, 0, v5);
  }
  v7 = *((_QWORD *)this + 10);
  if ( v7 )
  {
    do
    {
      *((_QWORD *)this + 10) = *(_QWORD *)(v7 + 168);
      (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
      v7 = *((_QWORD *)this + 10);
    }
    while ( v7 );
  }
  else
  {
    *((_QWORD *)this + 10) = 0;
  }
  v8 = (WriterHandleEntry *)*((_QWORD *)this + 14);
  v9 = *((_DWORD *)this + 27);
  v10 = (WriterHandleEntry *)((char *)v8 + 32 * v9);
  if ( v8 != v10 )
  {
    do
    {
      WriterHandleEntry::~WriterHandleEntry(v8);
      v8 = (WriterHandleEntry *)((char *)v8 + 32);
    }
    while ( v8 != v10 );
    v9 = *((_DWORD *)this + 27);
    v8 = (WriterHandleEntry *)*((_QWORD *)this + 14);
  }
  memset(v8, 0, 32LL * v9);
  *((_DWORD *)this + 27) = 0;
  EnterCriticalSection(&s_cs);
  if ( !--s_cComponents && s_pMultiLanguage2 )
  {
    ((void (__fastcall *)(struct IMultiLanguage2 *))s_pMultiLanguage2->lpVtbl->Release)(s_pMultiLanguage2);
    s_pMultiLanguage2 = 0;
  }
  LeaveCriticalSection(&s_cs);
  v11 = *((_QWORD *)this + 15);
  if ( v11 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::~_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>((char *)this + 88);
}

```

## disassembly

```asm
0x100407440  mov     [rsp+arg_0], rbx
0x100407445  mov     [rsp+arg_8], rbp
0x10040744a  mov     [rsp+arg_10], rsi
0x10040744f  push    rdi
0x100407450  sub     rsp, 20h
0x100407454  lea     rax, ??_7SXWriter@@6BBase@@@; const SXWriter::`vftable'{for `Base'}
0x10040745b  mov     rdi, rcx
0x10040745e  mov     [rcx], rax
0x100407461  lea     rax, ??_7SXWriter@@6BISXFormatWriter@@@; const SXWriter::`vftable'{for `ISXFormatWriter'}
0x100407468  mov     [rcx+10h], rax
0x10040746c  lea     rax, ??_7SXWriter@@6BISXFormatContentHandler@@@; const SXWriter::`vftable'{for `ISXFormatContentHandler'}
0x100407473  mov     [rcx+18h], rax
0x100407477  lea     rax, ??_7SXWriter@@6BISAXLexicalHandler@@@; const SXWriter::`vftable'{for `ISAXLexicalHandler'}
0x10040747e  mov     [rcx+20h], rax
0x100407482  lea     rax, ??_7SXWriter@@6BISAXDeclHandler@@@; const SXWriter::`vftable'{for `ISAXDeclHandler'}
0x100407489  mov     [rcx+28h], rax
0x10040748d  lea     rax, ??_7SXWriter@@6BISAXDTDHandler@@@; const SXWriter::`vftable'{for `ISAXDTDHandler'}
0x100407494  mov     [rcx+30h], rax
0x100407498  lea     rax, ??_7SXWriter@@6BISAXErrorHandler@@@; const SXWriter::`vftable'{for `ISAXErrorHandler'}
0x10040749f  mov     [rcx+38h], rax
0x1004074a3  lea     rax, ??_7SXWriter@@6BIMXSXAttributeWriter@@@; const SXWriter::`vftable'{for `IMXSXAttributeWriter'}
0x1004074aa  mov     [rcx+40h], rax
0x1004074ae  lea     rax, ??_7SXWriter@@6BISXNametable@@@; const SXWriter::`vftable'{for `ISXNametable'}
0x1004074b5  mov     [rcx+48h], rax
0x1004074b9  mov     rcx, [rcx+108h]
0x1004074c0  test    rcx, rcx
0x1004074c3  jz      short loc_1004074D6
0x1004074c5  mov     rax, [rcx]
0x1004074c8  mov     edx, 1
0x1004074cd  mov     rax, [rax]
0x1004074d0  call    cs:__guard_dispatch_icall_fptr
0x1004074d6  mov     r8, [rdi+158h]; lpMem
0x1004074dd  test    r8, r8
0x1004074e0  jz      short loc_100407518
0x1004074e2  mov     rcx, [rdi+8]
0x1004074e6  test    rcx, rcx
0x1004074e9  jnz     short loc_1004074F7
0x1004074eb  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004074f2  test    rcx, rcx
0x1004074f5  jz      short loc_100407509
0x1004074f7  mov     rax, [rcx]
0x1004074fa  mov     rdx, r8
0x1004074fd  mov     rax, [rax+28h]
0x100407501  call    cs:__guard_dispatch_icall_fptr
0x100407507  jmp     short loc_100407518
0x100407509  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407510  xor     edx, edx; dwFlags
0x100407512  call    cs:__imp_HeapFree
0x100407518  mov     r8, [rdi+120h]; lpMem
0x10040751f  test    r8, r8
0x100407522  jz      short loc_10040755A
0x100407524  mov     rcx, [rdi+8]
0x100407528  test    rcx, rcx
0x10040752b  jnz     short loc_100407539
0x10040752d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100407534  test    rcx, rcx
0x100407537  jz      short loc_10040754B
0x100407539  mov     rax, [rcx]
0x10040753c  mov     rdx, r8
0x10040753f  mov     rax, [rax+28h]
0x100407543  call    cs:__guard_dispatch_icall_fptr
0x100407549  jmp     short loc_10040755A
0x10040754b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407552  xor     edx, edx; dwFlags
0x100407554  call    cs:__imp_HeapFree
0x10040755a  mov     rcx, [rdi+50h]
0x10040755e  test    rcx, rcx
0x100407561  jz      short loc_10040758A
0x100407563  mov     rax, [rcx+0A8h]
0x10040756a  mov     edx, 1
0x10040756f  mov     [rdi+50h], rax
0x100407573  mov     rax, [rcx]
0x100407576  mov     rax, [rax]
0x100407579  call    cs:__guard_dispatch_icall_fptr
0x10040757f  mov     rcx, [rdi+50h]
0x100407583  test    rcx, rcx
0x100407586  jnz     short loc_100407563
0x100407588  jmp     short loc_100407592
0x10040758a  mov     qword ptr [rdi+50h], 0
0x100407592  mov     rbx, [rdi+70h]
0x100407596  mov     eax, [rdi+6Ch]
0x100407599  mov     esi, eax
0x10040759b  shl     rsi, 5
0x10040759f  add     rsi, rbx
0x1004075a2  cmp     rbx, rsi
0x1004075a5  jz      short loc_1004075BF
0x1004075a7  mov     rcx, rbx; this
0x1004075aa  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x1004075af  add     rbx, 20h ; ' '
0x1004075b3  cmp     rbx, rsi
0x1004075b6  jnz     short loc_1004075A7
0x1004075b8  mov     eax, [rdi+6Ch]
0x1004075bb  mov     rbx, [rdi+70h]
0x1004075bf  mov     r8d, eax
0x1004075c2  xor     edx, edx; Val
0x1004075c4  shl     r8, 5; Size
0x1004075c8  mov     rcx, rbx; void *
0x1004075cb  call    memset
0x1004075d0  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1004075d7  mov     dword ptr [rdi+6Ch], 0
0x1004075de  call    cs:__imp_EnterCriticalSection
0x1004075e4  sub     cs:?s_cComponents@@3JA, 1; long s_cComponents
0x1004075eb  jnz     short loc_100407611
0x1004075ed  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x1004075f4  test    rcx, rcx
0x1004075f7  jz      short loc_100407611
0x1004075f9  mov     rax, [rcx]
0x1004075fc  mov     rax, [rax+10h]
0x100407600  call    cs:__guard_dispatch_icall_fptr
0x100407606  mov     cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, 0; IMultiLanguage2 * s_pMultiLanguage2
0x100407611  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100407618  call    cs:__imp_LeaveCriticalSection
0x10040761e  mov     rcx, [rdi+78h]
0x100407622  test    rcx, rcx
0x100407625  jz      short loc_10040763C
0x100407627  mov     qword ptr [rdi+78h], 0
0x10040762f  mov     rax, [rcx]
0x100407632  mov     rax, [rax+10h]
0x100407636  call    cs:__guard_dispatch_icall_fptr
0x10040763c  lea     rcx, [rdi+58h]
0x100407640  mov     rbx, [rsp+28h+arg_0]
0x100407645  mov     rbp, [rsp+28h+arg_8]
0x10040764a  mov     rsi, [rsp+28h+arg_10]
0x10040764f  add     rsp, 20h
0x100407653  pop     rdi
0x100407654  jmp     ??1?$_xarray@UWriterHandleEntry@@V?$_xarray_item@UWriterHandleEntry@@@@@@UEAA@XZ; _xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>::~_xarray<WriterHandleEntry,_xarray_item<WriterHandleEntry>>(void)
```
