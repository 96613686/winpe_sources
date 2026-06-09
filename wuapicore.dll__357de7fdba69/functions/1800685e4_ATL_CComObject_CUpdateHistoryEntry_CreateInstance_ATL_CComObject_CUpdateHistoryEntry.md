# ATL::CComObject<CUpdateHistoryEntry>::CreateInstance(ATL::CComObject<CUpdateHistoryEntry> * *)

- ea: `0x1800685e4`
- end: `0x18006879d`
- name: `?CreateInstance@?$CComObject@VCUpdateHistoryEntry@@@ATL@@SAJPEAPEAV12@@Z`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180068340`

## callees

- `0x180006ac4`
- `0x1800685e4`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800686e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800686e6`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18006874d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18006874d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800686f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800686f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006862c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006862c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068619`

## string_xrefs

- `0x180068721`: `C:\__w\1\s\src\Client\comapi\UpdateHistoryEntry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CUpdateHistoryEntry>::CreateInstance(_QWORD *a1)
{
  unsigned int v3; // r14d
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  char *v6; // rdi
  char *v7; // r12
  __int64 v8; // rdx
  void *v9; // r8
  signed int LastError; // eax
  signed int v11; // ebx
  int FreeThreadedMarshaler; // eax
  __int64 v13; // rdx
  IUnknown *v14; // rax
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 0, 0x70u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x70u);
    *((_DWORD *)v6 + 6) = 0;
    *((_OWORD *)v6 + 2) = 0;
    *((_OWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 8) = 0;
    v6[72] = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 12) = 0;
    *((_DWORD *)v6 + 26) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CUpdateHistoryEntry>::`vftable'{for `CSusBaseAllocTag<6644067>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CUpdateHistoryEntry>::`vftable'{for `IDispatchImpl2<IUpdateHistoryEntry2,IUpdateHistoryEntry2,&_GUID const IID_IUpdateHistoryEntry2,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 2) = &ATL::CComObject<CUpdateHistoryEntry>::`vftable'{for `IUpdateHistoryEntry3'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v6 = 0;
  }
  v7 = v6;
  if ( v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v6 + 6);
    if ( !InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v6 + 32), 0, 0) )
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      if ( v11 < 0 )
        goto LABEL_17;
    }
    v6[72] = 1;
    FreeThreadedMarshaler = SecurityCheck(-2147483647, v8, v9);
    v11 = FreeThreadedMarshaler;
    if ( FreeThreadedMarshaler >= 0 )
    {
      v14 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v14, (LPUNKNOWN *)v6 + 10);
      v11 = FreeThreadedMarshaler;
      if ( FreeThreadedMarshaler >= 0 )
      {
        v11 = 0;
        goto LABEL_17;
      }
      v13 = 618;
    }
    else
    {
      v13 = 617;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateHistoryEntry.cpp",
      (const char *)(unsigned int)FreeThreadedMarshaler,
      v15);
LABEL_17:
    v3 = 0;
    if ( v11 < 0 )
      v3 = v11;
    _InterlockedDecrement((volatile signed __int32 *)v6 + 6);
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
0x1800685e4  mov     [rsp+arg_0], rcx
0x1800685e9  push    rbx
0x1800685ea  push    rdi
0x1800685eb  push    r12
0x1800685ed  push    r14
0x1800685ef  push    r15
0x1800685f1  sub     rsp, 20h
0x1800685f5  mov     r15, rcx
0x1800685f8  test    rcx, rcx
0x1800685fb  jnz     short loc_180068607
0x1800685fd  mov     eax, 80004003h
0x180068602  jmp     loc_180068790
0x180068607  mov     qword ptr [rcx], 0
0x18006860e  mov     r14d, 8007000Eh
0x180068614  mov     [rsp+48h+arg_8], r14d
0x180068619  call    cs:__imp_GetProcessHeap
0x18006861f  mov     ebx, 70h ; 'p'
0x180068624  mov     r8d, ebx; dwBytes
0x180068627  xor     edx, edx; dwFlags
0x180068629  mov     rcx, rax; hHeap
0x18006862c  call    cs:__imp_HeapAlloc
0x180068632  mov     rdi, rax
0x180068635  mov     [rsp+48h+arg_10], rax
0x18006863a  test    rax, rax
0x18006863d  jz      short loc_1800686AB
0x18006863f  mov     r8d, ebx; Size
0x180068642  xor     edx, edx; Val
0x180068644  mov     rcx, rax; void *
0x180068647  call    memset_0
0x18006864c  mov     dword ptr [rdi+18h], 0
0x180068653  xorps   xmm0, xmm0
0x180068656  xor     eax, eax
0x180068658  movups  xmmword ptr [rdi+20h], xmm0
0x18006865c  movups  xmmword ptr [rdi+30h], xmm0
0x180068660  mov     [rdi+40h], rax
0x180068664  mov     [rdi+48h], al
0x180068667  mov     [rdi+50h], rax
0x18006866b  mov     [rdi+58h], rax
0x18006866f  mov     [rdi+60h], rax
0x180068673  mov     [rdi+68h], eax
0x180068676  lea     rax, ??_7?$CComObject@VCUpdateHistoryEntry@@@ATL@@6B?$CSusBaseAllocTag@$0GFGBGD@@@@; const ATL::CComObject<CUpdateHistoryEntry>::`vftable'{for `CSusBaseAllocTag<6644067>'}
0x18006867d  mov     [rdi], rax
0x180068680  lea     rax, ??_7?$CComObject@VCUpdateHistoryEntry@@@ATL@@6B?$IDispatchImpl2@UIUpdateHistoryEntry2@@U1@$1?IID_IUpdateHistoryEntry2@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@@@; const ATL::CComObject<CUpdateHistoryEntry>::`vftable'{for `IDispatchImpl2<IUpdateHistoryEntry2,IUpdateHistoryEntry2,&_GUID const IID_IUpdateHistoryEntry2,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x180068687  mov     [rdi+8], rax
0x18006868b  lea     rax, ??_7?$CComObject@VCUpdateHistoryEntry@@@ATL@@6BIUpdateHistoryEntry3@@@; const ATL::CComObject<CUpdateHistoryEntry>::`vftable'{for `IUpdateHistoryEntry3'}
0x180068692  mov     [rdi+10h], rax
0x180068696  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18006869d  mov     rax, [rcx]
0x1800686a0  mov     rax, [rax+8]
0x1800686a4  call    _guard_dispatch_icall
0x1800686a9  jmp     short loc_1800686AD
0x1800686ab  xor     edi, edi
0x1800686ad  mov     [rsp+48h+arg_10], rdi
0x1800686b2  mov     r12, rdi
0x1800686b5  mov     [rsp+48h+arg_18], rdi
0x1800686ba  jmp     short loc_1800686D0
0x1800686bc  mov     r15, [rsp+48h+arg_0]
0x1800686c1  mov     r14d, [rsp+48h+arg_8]
0x1800686c6  mov     r12, [rsp+48h+arg_18]
0x1800686cb  mov     rdi, [rsp+48h+arg_10]
0x1800686d0  test    rdi, rdi
0x1800686d3  jz      loc_18006878A
0x1800686d9  lock inc dword ptr [rdi+18h]
0x1800686dd  xor     r8d, r8d; Flags
0x1800686e0  xor     edx, edx; dwSpinCount
0x1800686e2  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800686e6  call    cs:__imp_InitializeCriticalSectionEx
0x1800686ec  test    eax, eax
0x1800686ee  jnz     short loc_180068708
0x1800686f0  call    cs:__imp_GetLastError
0x1800686f6  movzx   ebx, ax
0x1800686f9  or      ebx, 80070000h
0x1800686ff  test    eax, eax
0x180068701  cmovle  ebx, eax
0x180068704  test    ebx, ebx
0x180068706  js      short loc_180068762
0x180068708  mov     byte ptr [rdi+48h], 1
0x18006870c  mov     ecx, 80000001h; unsigned int
0x180068711  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x180068716  mov     ebx, eax
0x180068718  test    eax, eax
0x18006871a  jns     short loc_180068737
0x18006871c  mov     edx, 269h; void *
0x180068721  lea     r8, aCW1SSrcClientC_6; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180068728  mov     r9d, eax; char *
0x18006872b  mov     rcx, [rsp+48h]; this
0x180068730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068735  jmp     short loc_180068762
0x180068737  mov     rax, [rdi]
0x18006873a  mov     rcx, rdi
0x18006873d  mov     rax, [rax+8]
0x180068741  call    _guard_dispatch_icall
0x180068746  mov     rcx, rax; punkOuter
0x180068749  lea     rdx, [rdi+50h]; ppunkMarshal
0x18006874d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180068753  mov     ebx, eax
0x180068755  test    eax, eax
0x180068757  jns     short loc_180068760
0x180068759  mov     edx, 26Ah
0x18006875e  jmp     short loc_180068721
0x180068760  xor     ebx, ebx
0x180068762  xor     r14d, r14d
0x180068765  test    ebx, ebx
0x180068767  cmovs   r14d, ebx
0x18006876b  lock dec dword ptr [rdi+18h]
0x18006876f  test    r14d, r14d
0x180068772  jz      short loc_18006878A
0x180068774  mov     r8, [rdi]
0x180068777  mov     edx, 1
0x18006877c  mov     rcx, rdi
0x18006877f  mov     rax, [r8]
0x180068782  call    _guard_dispatch_icall
0x180068787  xor     r12d, r12d
0x18006878a  mov     [r15], r12
0x18006878d  mov     eax, r14d
0x180068790  add     rsp, 20h
0x180068794  pop     r15
0x180068796  pop     r14
0x180068798  pop     r12
0x18006879a  pop     rdi
0x18006879b  pop     rbx
0x18006879c  retn
```
