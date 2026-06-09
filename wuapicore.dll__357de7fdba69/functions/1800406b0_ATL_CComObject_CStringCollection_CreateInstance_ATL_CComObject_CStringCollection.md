# ATL::CComObject<CStringCollection>::CreateInstance(ATL::CComObject<CStringCollection> * *)

- ea: `0x1800406b0`
- end: `0x18004086b`
- name: `?CreateInstance@?$CComObject@VCStringCollection@@@ATL@@SAJPEAPEAV12@@Z`
- size: `443`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040080`
- `0x180058d64`
- `0x180067750`
- `0x180068340`
- `0x180071160`
- `0x180075140`

## callees

- `0x1800406b0`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800407e1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800407e1`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18004082d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18004082d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800406f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800406f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800406e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800406e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CStringCollection>::CreateInstance(_QWORD *a1)
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
  v5 = (char *)HeapAlloc(ProcessHeap, 0, 0x78u);
  try
  {
    v6 = v5;
    if ( v5 )
    {
      memset_0(v5, 0, 0x78u);
      *(_QWORD *)v6 = &CSusBaseAllocTag<1752326505>::`vftable';
      *((_DWORD *)v6 + 8) = 0;
      *(_OWORD *)(v6 + 40) = 0;
      *(_OWORD *)(v6 + 56) = 0;
      *((_QWORD *)v6 + 9) = 0;
      v6[80] = 0;
      *((_WORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_QWORD *)v6 + 13) = 0;
      *((_QWORD *)v6 + 14) = 0;
      *((_QWORD *)v6 + 12) = &CSusArray<wchar_t *,CStringCollection::CSusArrayListItemOpsBstr>::`vftable';
      v7 = *((_QWORD *)v6 + 11);
      if ( v7 )
      {
        *((_QWORD *)v6 + 11) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      *(_QWORD *)v6 = &ATL::CComObject<CStringCollection>::`vftable'{for `CSusBaseAllocTag<1668505955>'};
      *((_QWORD *)v6 + 1) = &CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
      *((_QWORD *)v6 + 3) = &ATL::CComObject<CStringCollection>::`vftable'{for `ATL::IDispatchImpl<IStringCollection,&_GUID const IID_IStringCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
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
        FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v13, (LPUNKNOWN *)v6 + 11);
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
0x1800406b0  mov     [rsp+arg_0], rcx
0x1800406b5  push    rbx
0x1800406b6  push    rsi
0x1800406b7  push    rdi
0x1800406b8  push    r14
0x1800406ba  push    r15
0x1800406bc  sub     rsp, 20h
0x1800406c0  mov     r14, rcx
0x1800406c3  xor     esi, esi
0x1800406c5  test    rcx, rcx
0x1800406c8  jnz     short loc_1800406D4
0x1800406ca  mov     eax, 80004003h
0x1800406cf  jmp     loc_18004085F
0x1800406d4  mov     [rcx], rsi
0x1800406d7  mov     ebx, 8007000Eh
0x1800406dc  mov     [rsp+48h+arg_8], ebx
0x1800406e0  call    cs:__imp_GetProcessHeap
0x1800406e6  mov     r15d, 78h ; 'x'
0x1800406ec  mov     r8d, r15d; dwBytes
0x1800406ef  xor     edx, edx; dwFlags
0x1800406f1  mov     rcx, rax; hHeap
0x1800406f4  call    cs:__imp_HeapAlloc
0x1800406fa  mov     rdi, rax
0x1800406fd  mov     [rsp+48h+arg_10], rax
0x180040702  test    rax, rax
0x180040705  jz      loc_1800407A4
0x18004070b  mov     r8d, r15d; Size
0x18004070e  xor     edx, edx; Val
0x180040710  mov     rcx, rax; void *
0x180040713  call    memset_0
0x180040718  lea     rax, ??_7?$CSusBaseAllocTag@$0GIHCGBGJ@@@6B@; const CSusBaseAllocTag<1752326505>::`vftable'
0x18004071f  mov     [rdi], rax
0x180040722  mov     [rdi+20h], esi
0x180040725  xorps   xmm0, xmm0
0x180040728  xor     eax, eax
0x18004072a  movups  xmmword ptr [rdi+28h], xmm0
0x18004072e  movups  xmmword ptr [rdi+38h], xmm0
0x180040732  mov     [rdi+48h], rax
0x180040736  mov     [rdi+50h], sil
0x18004073a  mov     [rdi+10h], si
0x18004073e  mov     [rdi+58h], rsi
0x180040742  mov     [rdi+68h], rsi
0x180040746  mov     [rdi+70h], rsi
0x18004074a  lea     rax, ??_7?$CSusArray@PEA_WVCSusArrayListItemOpsBstr@CStringCollection@@@@6B@; const CSusArray<wchar_t *,CStringCollection::CSusArrayListItemOpsBstr>::`vftable'
0x180040751  mov     [rdi+60h], rax
0x180040755  mov     rcx, [rdi+58h]
0x180040759  test    rcx, rcx
0x18004075c  jz      short loc_18004076F
0x18004075e  mov     [rdi+58h], rsi
0x180040762  mov     rax, [rcx]
0x180040765  mov     rax, [rax+10h]
0x180040769  call    _guard_dispatch_icall
0x18004076e  nop
0x18004076f  lea     rax, ??_7?$CComObject@VCStringCollection@@@ATL@@6B?$CSusBaseAllocTag@$0GDHDGBGD@@@@; const ATL::CComObject<CStringCollection>::`vftable'{for `CSusBaseAllocTag<1668505955>'}
0x180040776  mov     [rdi], rax
0x180040779  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x180040780  mov     [rdi+8], rax
0x180040784  lea     rax, ??_7?$CComObject@VCStringCollection@@@ATL@@6B?$IDispatchImpl@UIStringCollection@@$1?IID_IStringCollection@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CStringCollection>::`vftable'{for `ATL::IDispatchImpl<IStringCollection,&_GUID const IID_IStringCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x18004078b  mov     [rdi+18h], rax
0x18004078f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180040796  mov     rax, [rcx]
0x180040799  mov     rax, [rax+8]
0x18004079d  call    _guard_dispatch_icall
0x1800407a2  jmp     short loc_1800407A7
0x1800407a4  mov     rdi, rsi
0x1800407a7  mov     [rsp+48h+arg_10], rdi
0x1800407ac  mov     r15, rdi
0x1800407af  mov     [rsp+48h+arg_18], rdi
0x1800407b4  jmp     short loc_1800407CB
0x1800407b6  xor     esi, esi
0x1800407b8  mov     r14, [rsp+48h+arg_0]
0x1800407bd  mov     ebx, [rsp+48h+arg_8]
0x1800407c1  mov     r15, [rsp+48h+arg_18]
0x1800407c6  mov     rdi, [rsp+48h+arg_10]
0x1800407cb  test    rdi, rdi
0x1800407ce  jz      loc_18004085A
0x1800407d4  lock inc dword ptr [rdi+20h]
0x1800407d8  xor     r8d, r8d; Flags
0x1800407db  xor     edx, edx; dwSpinCount
0x1800407dd  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800407e1  call    cs:__imp_InitializeCriticalSectionEx
0x1800407e7  test    eax, eax
0x1800407e9  jnz     short loc_180040803
0x1800407eb  call    cs:__imp_GetLastError
0x1800407f1  movzx   ecx, ax
0x1800407f4  or      ecx, 80070000h
0x1800407fa  test    eax, eax
0x1800407fc  cmovle  ecx, eax
0x1800407ff  test    ecx, ecx
0x180040801  js      short loc_180040835
0x180040803  mov     byte ptr [rdi+50h], 1
0x180040807  mov     ecx, 80000001h; unsigned int
0x18004080c  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x180040811  mov     ecx, eax
0x180040813  test    eax, eax
0x180040815  js      short loc_180040835
0x180040817  mov     rax, [rdi]
0x18004081a  mov     rcx, rdi
0x18004081d  mov     rax, [rax+8]
0x180040821  call    _guard_dispatch_icall
0x180040826  mov     rcx, rax; punkOuter
0x180040829  lea     rdx, [rdi+58h]; ppunkMarshal
0x18004082d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180040833  mov     ecx, eax
0x180040835  mov     ebx, esi
0x180040837  test    ecx, ecx
0x180040839  cmovs   ebx, ecx
0x18004083c  lock dec dword ptr [rdi+20h]
0x180040840  test    ebx, ebx
0x180040842  jz      short loc_18004085A
0x180040844  mov     r8, [rdi]
0x180040847  mov     edx, 1
0x18004084c  mov     rcx, rdi
0x18004084f  mov     rax, [r8]
0x180040852  call    _guard_dispatch_icall
0x180040857  mov     r15, rsi
0x18004085a  mov     [r14], r15
0x18004085d  mov     eax, ebx
0x18004085f  add     rsp, 20h
0x180040863  pop     r15
0x180040865  pop     r14
0x180040867  pop     rdi
0x180040868  pop     rsi
0x180040869  pop     rbx
0x18004086a  retn
```
