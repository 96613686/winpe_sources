# ATL::CComObject<CWindowsDriverUpdateEntry>::CreateInstance(ATL::CComObject<CWindowsDriverUpdateEntry> * *)

- ea: `0x18005d778`
- end: `0x18005d908`
- name: `?CreateInstance@?$CComObject@VCWindowsDriverUpdateEntry@@@ATL@@SAJPEAPEAV12@@Z`
- size: `400`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180052d44`
- `0x1800591f0`
- `0x180059b28`

## callees

- `0x18005d778`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18005d87f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18005d87f`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18005d8cb`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18005d8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d889`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d7bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d7bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d7a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d7a9`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWindowsDriverUpdateEntry>::CreateInstance(_QWORD *a1)
{
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  char *v6; // rdi
  char *v7; // r15
  __int64 v8; // rdx
  void *v9; // r8
  signed int LastError; // eax
  int FreeThreadedMarshaler; // ecx
  IUnknown *v12; // rax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 0, 0x88u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x88u);
    *((_DWORD *)v6 + 4) = 0;
    *(_OWORD *)(v6 + 24) = 0;
    *(_OWORD *)(v6 + 40) = 0;
    *((_QWORD *)v6 + 7) = 0;
    v6[64] = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 12) = 0;
    *((_QWORD *)v6 + 13) = 0;
    *((_QWORD *)v6 + 14) = 0;
    *((_QWORD *)v6 + 15) = 0;
    *((_QWORD *)v6 + 16) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CWindowsDriverUpdateEntry>::`vftable'{for `CSusBaseAllocTag<7823715>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CWindowsDriverUpdateEntry>::`vftable'{for `ATL::IDispatchImpl<IWindowsDriverUpdateEntry,&_GUID const IID_IWindowsDriverUpdateEntry,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v6 = 0;
  }
  v7 = v6;
  if ( v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v6 + 4);
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v6 + 24), 0, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      FreeThreadedMarshaler = LastError;
    if ( FreeThreadedMarshaler >= 0 )
    {
LABEL_11:
      v6[64] = 1;
      FreeThreadedMarshaler = SecurityCheck(-2147483647, v8, v9);
      if ( FreeThreadedMarshaler >= 0 )
      {
        v12 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
        FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v12, (LPUNKNOWN *)v6 + 9);
      }
    }
    v3 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v3 = FreeThreadedMarshaler;
    _InterlockedDecrement((volatile signed __int32 *)v6 + 4);
    if ( v3 )
    {
      (**(void (__fastcall ***)(void *, __int64))v6)(v6, 1);
      v7 = 0;
    }
  }
  *a1 = v7;
  return v3;
}

```

## disassembly

```asm
0x18005d778  mov     [rsp+arg_0], rcx
0x18005d77d  push    rbx
0x18005d77e  push    rdi
0x18005d77f  push    r14
0x18005d781  push    r15
0x18005d783  sub     rsp, 28h
0x18005d787  mov     r14, rcx
0x18005d78a  test    rcx, rcx
0x18005d78d  jnz     short loc_18005D799
0x18005d78f  mov     eax, 80004003h
0x18005d794  jmp     loc_18005D8FD
0x18005d799  mov     qword ptr [rcx], 0
0x18005d7a0  mov     ebx, 8007000Eh
0x18005d7a5  mov     [rsp+48h+arg_8], ebx
0x18005d7a9  call    cs:__imp_GetProcessHeap
0x18005d7af  mov     r15d, 88h
0x18005d7b5  mov     r8d, r15d; dwBytes
0x18005d7b8  xor     edx, edx; dwFlags
0x18005d7ba  mov     rcx, rax; hHeap
0x18005d7bd  call    cs:__imp_HeapAlloc
0x18005d7c3  mov     rdi, rax
0x18005d7c6  mov     [rsp+48h+arg_10], rax
0x18005d7cb  test    rax, rax
0x18005d7ce  jz      short loc_18005D845
0x18005d7d0  mov     r8d, r15d; Size
0x18005d7d3  xor     edx, edx; Val
0x18005d7d5  mov     rcx, rax; void *
0x18005d7d8  call    memset_0
0x18005d7dd  mov     dword ptr [rdi+10h], 0
0x18005d7e4  xorps   xmm0, xmm0
0x18005d7e7  xor     eax, eax
0x18005d7e9  movups  xmmword ptr [rdi+18h], xmm0
0x18005d7ed  movups  xmmword ptr [rdi+28h], xmm0
0x18005d7f1  mov     [rdi+38h], rax
0x18005d7f5  mov     [rdi+40h], al
0x18005d7f8  mov     [rdi+48h], rax
0x18005d7fc  mov     [rdi+50h], rax
0x18005d800  mov     [rdi+58h], rax
0x18005d804  mov     [rdi+60h], rax
0x18005d808  mov     [rdi+68h], rax
0x18005d80c  mov     [rdi+70h], rax
0x18005d810  mov     [rdi+78h], rax
0x18005d814  mov     [rdi+80h], rax
0x18005d81b  lea     rax, ??_7?$CComObject@VCWindowsDriverUpdateEntry@@@ATL@@6B?$CSusBaseAllocTag@$0HHGBGD@@@@; const ATL::CComObject<CWindowsDriverUpdateEntry>::`vftable'{for `CSusBaseAllocTag<7823715>'}
0x18005d822  mov     [rdi], rax
0x18005d825  lea     rax, ??_7?$CComObject@VCWindowsDriverUpdateEntry@@@ATL@@6B?$IDispatchImpl@UIWindowsDriverUpdateEntry@@$1?IID_IWindowsDriverUpdateEntry@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWindowsDriverUpdateEntry>::`vftable'{for `ATL::IDispatchImpl<IWindowsDriverUpdateEntry,&_GUID const IID_IWindowsDriverUpdateEntry,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x18005d82c  mov     [rdi+8], rax
0x18005d830  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18005d837  mov     rax, [rcx]
0x18005d83a  mov     rax, [rax+8]
0x18005d83e  call    _guard_dispatch_icall
0x18005d843  jmp     short loc_18005D847
0x18005d845  xor     edi, edi
0x18005d847  mov     [rsp+48h+arg_10], rdi
0x18005d84c  mov     r15, rdi
0x18005d84f  mov     [rsp+48h+arg_18], rdi
0x18005d854  jmp     short loc_18005D869
0x18005d856  mov     r14, [rsp+48h+arg_0]
0x18005d85b  mov     ebx, [rsp+48h+arg_8]
0x18005d85f  mov     r15, [rsp+48h+arg_18]
0x18005d864  mov     rdi, [rsp+48h+arg_10]
0x18005d869  test    rdi, rdi
0x18005d86c  jz      loc_18005D8F8
0x18005d872  lock inc dword ptr [rdi+10h]
0x18005d876  xor     r8d, r8d; Flags
0x18005d879  xor     edx, edx; dwSpinCount
0x18005d87b  lea     rcx, [rdi+18h]; lpCriticalSection
0x18005d87f  call    cs:__imp_InitializeCriticalSectionEx
0x18005d885  test    eax, eax
0x18005d887  jnz     short loc_18005D8A1
0x18005d889  call    cs:__imp_GetLastError
0x18005d88f  movzx   ecx, ax
0x18005d892  or      ecx, 80070000h
0x18005d898  test    eax, eax
0x18005d89a  cmovle  ecx, eax
0x18005d89d  test    ecx, ecx
0x18005d89f  js      short loc_18005D8D3
0x18005d8a1  mov     byte ptr [rdi+40h], 1
0x18005d8a5  mov     ecx, 80000001h; unsigned int
0x18005d8aa  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18005d8af  mov     ecx, eax
0x18005d8b1  test    eax, eax
0x18005d8b3  js      short loc_18005D8D3
0x18005d8b5  mov     rax, [rdi]
0x18005d8b8  mov     rcx, rdi
0x18005d8bb  mov     rax, [rax+8]
0x18005d8bf  call    _guard_dispatch_icall
0x18005d8c4  mov     rcx, rax; punkOuter
0x18005d8c7  lea     rdx, [rdi+48h]; ppunkMarshal
0x18005d8cb  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18005d8d1  mov     ecx, eax
0x18005d8d3  xor     ebx, ebx
0x18005d8d5  test    ecx, ecx
0x18005d8d7  cmovs   ebx, ecx
0x18005d8da  lock dec dword ptr [rdi+10h]
0x18005d8de  test    ebx, ebx
0x18005d8e0  jz      short loc_18005D8F8
0x18005d8e2  mov     r8, [rdi]
0x18005d8e5  mov     edx, 1
0x18005d8ea  mov     rcx, rdi
0x18005d8ed  mov     rax, [r8]
0x18005d8f0  call    _guard_dispatch_icall
0x18005d8f5  xor     r15d, r15d
0x18005d8f8  mov     [r14], r15
0x18005d8fb  mov     eax, ebx
0x18005d8fd  add     rsp, 28h
0x18005d901  pop     r15
0x18005d903  pop     r14
0x18005d905  pop     rdi
0x18005d906  pop     rbx
0x18005d907  retn
```
