# ATL::CComObject<CUpdateCollection>::CreateInstance(ATL::CComObject<CUpdateCollection> * *)

- ea: `0x1800037d8`
- end: `0x180003997`
- name: `?CreateInstance@?$CComObject@VCUpdateCollection@@@ATL@@SAJPEAPEAV12@@Z`
- size: `447`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002ec0`
- `0x18000cfc0`
- `0x1800132c4`
- `0x18001757c`
- `0x180024260`
- `0x1800297cc`
- `0x180060a80`

## callees

- `0x1800037d8`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000390d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000390d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003959`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003917`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000381c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000381c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003808`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CUpdateCollection>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // r14
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  char *v6; // rdi
  __int64 v7; // rcx
  char *v8; // r15
  __int64 v9; // rdx
  void *v10; // r8
  signed int LastError; // eax
  int FreeThreadedMarshaler; // ecx
  IUnknown *v13; // rax
  char *v15; // [rsp+60h] [rbp+18h]
  char *v16; // [rsp+68h] [rbp+20h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 0, 0x80u);
  try
  {
    v6 = v5;
    if ( v5 )
    {
      memset_0(v5, 0, 0x80u);
      *(_QWORD *)v6 = &CSusBaseAllocTag<1752326505>::`vftable';
      *((_DWORD *)v6 + 8) = 0;
      *(_OWORD *)(v6 + 40) = 0;
      *(_OWORD *)(v6 + 56) = 0;
      *((_QWORD *)v6 + 9) = 0;
      v6[80] = 0;
      *((_WORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_QWORD *)v6 + 12) = 0;
      *((_QWORD *)v6 + 14) = 0;
      *((_QWORD *)v6 + 15) = 0;
      *((_QWORD *)v6 + 13) = &CSusArrayList<IUpdate *,CSusArrayListItemOpNoop<IUpdate *>>::`vftable';
      v7 = *((_QWORD *)v6 + 12);
      if ( v7 )
      {
        *((_QWORD *)v6 + 12) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      *(_QWORD *)v6 = &ATL::CComObject<CUpdateCollection>::`vftable'{for `CSusBaseAllocTag<1668637027>'};
      *((_QWORD *)v6 + 1) = &CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
      *((_QWORD *)v6 + 3) = &ATL::CComObject<CUpdateCollection>::`vftable'{for `ATL::IDispatchImpl<IUpdateCollection,&_GUID const IID_IUpdateCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v6 = 0;
    }
    v15 = v6;
    v8 = v6;
    v16 = v6;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v8 = v16;
    v6 = v15;
  }
  if ( v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v6 + 8);
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)v6 + 1, 0, 0) )
      goto LABEL_15;
    LastError = GetLastError();
    FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      FreeThreadedMarshaler = LastError;
    if ( FreeThreadedMarshaler >= 0 )
    {
LABEL_15:
      v6[80] = 1;
      FreeThreadedMarshaler = SecurityCheck(-2147483647, v9, v10);
      if ( FreeThreadedMarshaler >= 0 )
      {
        v13 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
        FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v13, (LPUNKNOWN *)v6 + 12);
      }
    }
    v3 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v3 = FreeThreadedMarshaler;
    _InterlockedDecrement((volatile signed __int32 *)v6 + 8);
    if ( v3 )
    {
      (**(void (__fastcall ***)(void *, __int64))v6)(v6, 1);
      v8 = 0;
    }
  }
  *v1 = v8;
  return v3;
}

```

## disassembly

```asm
0x1800037d8  mov     [rsp+arg_0], rcx
0x1800037dd  push    rbx
0x1800037de  push    rsi
0x1800037df  push    rdi
0x1800037e0  push    r14
0x1800037e2  push    r15
0x1800037e4  sub     rsp, 20h
0x1800037e8  mov     r14, rcx
0x1800037eb  xor     esi, esi
0x1800037ed  test    rcx, rcx
0x1800037f0  jnz     short loc_1800037FC
0x1800037f2  mov     eax, 80004003h
0x1800037f7  jmp     loc_18000398B
0x1800037fc  mov     [rcx], rsi
0x1800037ff  mov     ebx, 8007000Eh
0x180003804  mov     [rsp+48h+arg_8], ebx
0x180003808  call    cs:__imp_GetProcessHeap
0x18000380e  mov     r15d, 80h
0x180003814  mov     r8d, r15d; dwBytes
0x180003817  xor     edx, edx; dwFlags
0x180003819  mov     rcx, rax; hHeap
0x18000381c  call    cs:__imp_HeapAlloc
0x180003822  mov     rdi, rax
0x180003825  mov     [rsp+48h+arg_10], rax
0x18000382a  test    rax, rax
0x18000382d  jz      loc_1800038D0
0x180003833  mov     r8d, r15d; Size
0x180003836  xor     edx, edx; Val
0x180003838  mov     rcx, rax; void *
0x18000383b  call    memset_0
0x180003840  lea     rax, ??_7?$CSusBaseAllocTag@$0GIHCGBGJ@@@6B@; const CSusBaseAllocTag<1752326505>::`vftable'
0x180003847  mov     [rdi], rax
0x18000384a  mov     [rdi+20h], esi
0x18000384d  xorps   xmm0, xmm0
0x180003850  xor     eax, eax
0x180003852  movups  xmmword ptr [rdi+28h], xmm0
0x180003856  movups  xmmword ptr [rdi+38h], xmm0
0x18000385a  mov     [rdi+48h], rax
0x18000385e  mov     [rdi+50h], sil
0x180003862  mov     [rdi+10h], si
0x180003866  mov     [rdi+58h], rsi
0x18000386a  mov     [rdi+60h], rsi
0x18000386e  mov     [rdi+70h], rsi
0x180003872  mov     [rdi+78h], rsi
0x180003876  lea     rax, ??_7?$CSusArrayList@PEAUIUpdate@@V?$CSusArrayListItemOpNoop@PEAUIUpdate@@@@@@6B@; const CSusArrayList<IUpdate *,CSusArrayListItemOpNoop<IUpdate *>>::`vftable'
0x18000387d  mov     [rdi+68h], rax
0x180003881  mov     rcx, [rdi+60h]
0x180003885  test    rcx, rcx
0x180003888  jz      short loc_18000389B
0x18000388a  mov     [rdi+60h], rsi
0x18000388e  mov     rax, [rcx]
0x180003891  mov     rax, [rax+10h]
0x180003895  call    _guard_dispatch_icall
0x18000389a  nop
0x18000389b  lea     rax, ??_7?$CComObject@VCUpdateCollection@@@ATL@@6B?$CSusBaseAllocTag@$0GDHFGBGD@@@@; const ATL::CComObject<CUpdateCollection>::`vftable'{for `CSusBaseAllocTag<1668637027>'}
0x1800038a2  mov     [rdi], rax
0x1800038a5  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x1800038ac  mov     [rdi+8], rax
0x1800038b0  lea     rax, ??_7?$CComObject@VCUpdateCollection@@@ATL@@6B?$IDispatchImpl@UIUpdateCollection@@$1?IID_IUpdateCollection@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CUpdateCollection>::`vftable'{for `ATL::IDispatchImpl<IUpdateCollection,&_GUID const IID_IUpdateCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x1800038b7  mov     [rdi+18h], rax
0x1800038bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800038c2  mov     rax, [rcx]
0x1800038c5  mov     rax, [rax+8]
0x1800038c9  call    _guard_dispatch_icall
0x1800038ce  jmp     short loc_1800038D3
0x1800038d0  mov     rdi, rsi
0x1800038d3  mov     [rsp+48h+arg_10], rdi
0x1800038d8  mov     r15, rdi
0x1800038db  mov     [rsp+48h+arg_18], rdi
0x1800038e0  jmp     short loc_1800038F7
0x1800038e2  xor     esi, esi
0x1800038e4  mov     r14, [rsp+48h+arg_0]
0x1800038e9  mov     ebx, [rsp+48h+arg_8]
0x1800038ed  mov     r15, [rsp+48h+arg_18]
0x1800038f2  mov     rdi, [rsp+48h+arg_10]
0x1800038f7  test    rdi, rdi
0x1800038fa  jz      loc_180003986
0x180003900  lock inc dword ptr [rdi+20h]
0x180003904  xor     r8d, r8d; Flags
0x180003907  xor     edx, edx; dwSpinCount
0x180003909  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000390d  call    cs:__imp_InitializeCriticalSectionEx
0x180003913  test    eax, eax
0x180003915  jnz     short loc_18000392F
0x180003917  call    cs:__imp_GetLastError
0x18000391d  movzx   ecx, ax
0x180003920  or      ecx, 80070000h
0x180003926  test    eax, eax
0x180003928  cmovle  ecx, eax
0x18000392b  test    ecx, ecx
0x18000392d  js      short loc_180003961
0x18000392f  mov     byte ptr [rdi+50h], 1
0x180003933  mov     ecx, 80000001h; unsigned int
0x180003938  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18000393d  mov     ecx, eax
0x18000393f  test    eax, eax
0x180003941  js      short loc_180003961
0x180003943  mov     rax, [rdi]
0x180003946  mov     rcx, rdi
0x180003949  mov     rax, [rax+8]
0x18000394d  call    _guard_dispatch_icall
0x180003952  mov     rcx, rax; punkOuter
0x180003955  lea     rdx, [rdi+60h]; ppunkMarshal
0x180003959  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000395f  mov     ecx, eax
0x180003961  mov     ebx, esi
0x180003963  test    ecx, ecx
0x180003965  cmovs   ebx, ecx
0x180003968  lock dec dword ptr [rdi+20h]
0x18000396c  test    ebx, ebx
0x18000396e  jz      short loc_180003986
0x180003970  mov     r8, [rdi]
0x180003973  mov     edx, 1
0x180003978  mov     rcx, rdi
0x18000397b  mov     rax, [r8]
0x18000397e  call    _guard_dispatch_icall
0x180003983  mov     r15, rsi
0x180003986  mov     [r14], r15
0x180003989  mov     eax, ebx
0x18000398b  add     rsp, 20h
0x18000398f  pop     r15
0x180003991  pop     r14
0x180003993  pop     rdi
0x180003994  pop     rsi
0x180003995  pop     rbx
0x180003996  retn
```
