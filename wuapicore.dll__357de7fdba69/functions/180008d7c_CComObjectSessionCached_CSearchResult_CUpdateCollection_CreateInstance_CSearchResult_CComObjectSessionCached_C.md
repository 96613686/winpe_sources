# CComObjectSessionCached<CSearchResult,CUpdateCollection>::CreateInstance(CSearchResult *,CComObjectSessionCached<CSearchResult,CUpdateCollection> * *)

- ea: `0x180008d7c`
- end: `0x180008eb2`
- name: `?CreateInstance@?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@SAJPEAVCSearchResult@@PEAPEAV1@@Z`
- size: `310`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800085a0`
- `0x1800369f0`
- `0x180058d64`

## callees

- `0x180008d7c`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008e20`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008e20`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008e6c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008dc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008dc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008db1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CComObjectSessionCached<CSearchResult,CUpdateCollection>::CreateInstance(__int64 a1, _QWORD *a2)
{
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  void *v8; // rdi
  __int64 v9; // rdx
  void *v10; // r8
  signed int LastError; // eax
  int FreeThreadedMarshaler; // ecx
  IUnknown *v13; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0x80u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x80u);
    *((_QWORD *)v8 + 13) = &CSusArrayList<IUpdate *,CSusArrayListItemOpNoop<IUpdate *>>::`vftable';
    *(_QWORD *)v8 = &ATL::CComObjectCached<CUpdateCollection>::`vftable'{for `CSusBaseAllocTag<1668637027>'};
    *((_QWORD *)v8 + 1) = &CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
    *((_QWORD *)v8 + 3) = &CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `ATL::IDispatchImpl<IUpdateCollection,&_GUID const IID_IUpdateCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement((volatile signed __int32 *)v8 + 8);
    *((_QWORD *)v8 + 11) = a1;
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)v8 + 1, 0, 0) )
      goto LABEL_8;
    LastError = GetLastError();
    FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      FreeThreadedMarshaler = LastError;
    if ( FreeThreadedMarshaler >= 0 )
    {
LABEL_8:
      *((_BYTE *)v8 + 80) = 1;
      FreeThreadedMarshaler = SecurityCheck(-2147483647, v9, v10);
      if ( FreeThreadedMarshaler >= 0 )
      {
        v13 = (IUnknown *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
        FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v13, (LPUNKNOWN *)v8 + 12);
      }
    }
    v5 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v5 = FreeThreadedMarshaler;
    _InterlockedDecrement((volatile signed __int32 *)v8 + 8);
    if ( !v5 )
      goto LABEL_15;
    (**(void (__fastcall ***)(void *, __int64))v8)(v8, 1);
  }
  v8 = 0;
LABEL_15:
  *a2 = v8;
  return v5;
}

```

## disassembly

```asm
0x180008d7c  mov     [rsp+arg_0], rbx
0x180008d81  mov     [rsp+arg_8], rbp
0x180008d86  mov     [rsp+arg_10], rsi
0x180008d8b  push    rdi
0x180008d8c  sub     rsp, 20h
0x180008d90  mov     rsi, rdx
0x180008d93  mov     rbp, rcx
0x180008d96  test    rdx, rdx
0x180008d99  jnz     short loc_180008DA5
0x180008d9b  mov     eax, 80004003h
0x180008da0  jmp     loc_180008E9D
0x180008da5  mov     qword ptr [rdx], 0
0x180008dac  mov     ebx, 8007000Eh
0x180008db1  call    cs:__imp_GetProcessHeap
0x180008db7  xor     edx, edx; dwFlags
0x180008db9  mov     r8d, 80h; dwBytes
0x180008dbf  mov     rcx, rax; hHeap
0x180008dc2  call    cs:__imp_HeapAlloc
0x180008dc8  mov     rdi, rax
0x180008dcb  test    rax, rax
0x180008dce  jz      loc_180008E96
0x180008dd4  xor     edx, edx; Val
0x180008dd6  mov     r8d, 80h; Size
0x180008ddc  mov     rcx, rax; void *
0x180008ddf  call    memset_0
0x180008de4  lea     rax, ??_7?$CSusArrayList@PEAUIUpdate@@V?$CSusArrayListItemOpNoop@PEAUIUpdate@@@@@@6B@; const CSusArrayList<IUpdate *,CSusArrayListItemOpNoop<IUpdate *>>::`vftable'
0x180008deb  mov     [rdi+68h], rax
0x180008def  lea     rax, ??_7?$CComObjectCached@VCUpdateCollection@@@ATL@@6B?$CSusBaseAllocTag@$0GDHFGBGD@@@@; const ATL::CComObjectCached<CUpdateCollection>::`vftable'{for `CSusBaseAllocTag<1668637027>'}
0x180008df6  mov     [rdi], rax
0x180008df9  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x180008e00  mov     [rdi+8], rax
0x180008e04  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6B?$IDispatchImpl@UIUpdateCollection@@$1?IID_IUpdateCollection@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `ATL::IDispatchImpl<IUpdateCollection,&_GUID const IID_IUpdateCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x180008e0b  mov     [rdi+18h], rax
0x180008e0f  lock inc dword ptr [rdi+20h]
0x180008e13  mov     [rdi+58h], rbp
0x180008e17  xor     r8d, r8d; Flags
0x180008e1a  xor     edx, edx; dwSpinCount
0x180008e1c  lea     rcx, [rdi+28h]; lpCriticalSection
0x180008e20  call    cs:__imp_InitializeCriticalSectionEx
0x180008e26  test    eax, eax
0x180008e28  jnz     short loc_180008E42
0x180008e2a  call    cs:__imp_GetLastError
0x180008e30  movzx   ecx, ax
0x180008e33  or      ecx, 80070000h
0x180008e39  test    eax, eax
0x180008e3b  cmovle  ecx, eax
0x180008e3e  test    ecx, ecx
0x180008e40  js      short loc_180008E74
0x180008e42  mov     byte ptr [rdi+50h], 1
0x180008e46  mov     ecx, 80000001h; unsigned int
0x180008e4b  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x180008e50  mov     ecx, eax
0x180008e52  test    eax, eax
0x180008e54  js      short loc_180008E74
0x180008e56  mov     rax, [rdi]
0x180008e59  mov     rcx, rdi
0x180008e5c  mov     rax, [rax+8]
0x180008e60  call    _guard_dispatch_icall
0x180008e65  mov     rcx, rax; punkOuter
0x180008e68  lea     rdx, [rdi+60h]; ppunkMarshal
0x180008e6c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180008e72  mov     ecx, eax
0x180008e74  xor     ebx, ebx
0x180008e76  test    ecx, ecx
0x180008e78  cmovs   ebx, ecx
0x180008e7b  lock dec dword ptr [rdi+20h]
0x180008e7f  test    ebx, ebx
0x180008e81  jz      short loc_180008E98
0x180008e83  mov     rax, [rdi]
0x180008e86  mov     edx, 1
0x180008e8b  mov     rcx, rdi
0x180008e8e  mov     rax, [rax]
0x180008e91  call    _guard_dispatch_icall
0x180008e96  xor     edi, edi
0x180008e98  mov     [rsi], rdi
0x180008e9b  mov     eax, ebx
0x180008e9d  mov     rbx, [rsp+28h+arg_0]
0x180008ea2  mov     rbp, [rsp+28h+arg_8]
0x180008ea7  mov     rsi, [rsp+28h+arg_10]
0x180008eac  add     rsp, 20h
0x180008eb0  pop     rdi
0x180008eb1  retn
```
