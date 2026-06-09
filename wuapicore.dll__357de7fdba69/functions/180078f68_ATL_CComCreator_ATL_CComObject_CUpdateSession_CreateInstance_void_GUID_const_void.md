# ATL::CComCreator<ATL::CComObject<CUpdateSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180078f68`
- end: `0x1800790fb`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCUpdateSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180077770`

## callees

- `0x18003a110`
- `0x180078f68`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007905e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007905e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800790aa`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800790aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079068`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078fb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078fb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078fa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078fa5`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CUpdateSession>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  char *v9; // rdi
  __int64 v10; // rdx
  void *v11; // r8
  signed int LastError; // eax
  int FreeThreadedMarshaler; // ecx
  IUnknown *v14; // rax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x160u);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0x160u);
    CUpdateSession::CUpdateSession((CUpdateSession *)v9);
    *(_QWORD *)v9 = &ATL::CComObject<CUpdateSession>::`vftable'{for `CSusBaseAllocTag<7561571>'};
    *((_QWORD *)v9 + 1) = &CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
    *((_QWORD *)v9 + 3) = &ATL::CComObject<CUpdateSession>::`vftable'{for `CUpdateLockdown'};
    *((_QWORD *)v9 + 5) = &ATL::CComObject<CUpdateSession>::`vftable'{for `IUpdateInternalConfiguration'};
    *((_QWORD *)v9 + 6) = &ATL::CComObject<CUpdateSession>::`vftable'{for `ATL::IDispatchImpl<IUpdateSession3,&_GUID const IID_IUpdateSession3,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v9 + 14);
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v9 + 64), 0, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      FreeThreadedMarshaler = LastError;
    if ( FreeThreadedMarshaler >= 0 )
    {
LABEL_11:
      v9[104] = 1;
      FreeThreadedMarshaler = SecurityCheck(-2147483646, v10, v11);
      if ( FreeThreadedMarshaler >= 0 )
      {
        v14 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
        FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v14, (LPUNKNOWN *)v9 + 14);
      }
    }
    v6 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v6 = FreeThreadedMarshaler;
    _InterlockedDecrement((volatile signed __int32 *)v9 + 14);
    if ( v6
      || (v6 = (**((__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v9 + 3))((__int64)(v9 + 24), a2, a3)) != 0 )
    {
      (**(void (__fastcall ***)(void *, __int64))v9)(v9, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180078f68  mov     [rsp+arg_10], r8
0x180078f6d  mov     [rsp+arg_8], rdx
0x180078f72  mov     [rsp+arg_0], rcx
0x180078f77  push    rbx
0x180078f78  push    rsi
0x180078f79  push    rdi
0x180078f7a  push    r14
0x180078f7c  sub     rsp, 28h
0x180078f80  mov     rsi, r8
0x180078f83  mov     r14, rdx
0x180078f86  test    r8, r8
0x180078f89  jnz     short loc_180078F95
0x180078f8b  mov     eax, 80004003h
0x180078f90  jmp     loc_1800790F1
0x180078f95  mov     qword ptr [r8], 0
0x180078f9c  mov     ebx, 8007000Eh
0x180078fa1  mov     dword ptr [rsp+48h+arg_0], ebx
0x180078fa5  call    cs:__imp_GetProcessHeap
0x180078fab  xor     edx, edx; dwFlags
0x180078fad  mov     r8d, 160h; dwBytes
0x180078fb3  mov     rcx, rax; hHeap
0x180078fb6  call    cs:__imp_HeapAlloc
0x180078fbc  mov     rdi, rax
0x180078fbf  mov     [rsp+48h+arg_18], rax
0x180078fc4  test    rax, rax
0x180078fc7  jz      short loc_18007902C
0x180078fc9  xor     edx, edx; Val
0x180078fcb  mov     r8d, 160h; Size
0x180078fd1  mov     rcx, rax; void *
0x180078fd4  call    memset_0
0x180078fd9  mov     rcx, rdi; this
0x180078fdc  call    ??0CUpdateSession@@QEAA@XZ; CUpdateSession::CUpdateSession(void)
0x180078fe1  lea     rax, ??_7?$CComObject@VCUpdateSession@@@ATL@@6B?$CSusBaseAllocTag@$0HDGBGD@@@@; const ATL::CComObject<CUpdateSession>::`vftable'{for `CSusBaseAllocTag<7561571>'}
0x180078fe8  mov     [rdi], rax
0x180078feb  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x180078ff2  mov     [rdi+8], rax
0x180078ff6  lea     rax, ??_7?$CComObject@VCUpdateSession@@@ATL@@6BCUpdateLockdown@@@; const ATL::CComObject<CUpdateSession>::`vftable'{for `CUpdateLockdown'}
0x180078ffd  mov     [rdi+18h], rax
0x180079001  lea     rax, ??_7?$CComObject@VCUpdateSession@@@ATL@@6BIUpdateInternalConfiguration@@@; const ATL::CComObject<CUpdateSession>::`vftable'{for `IUpdateInternalConfiguration'}
0x180079008  mov     [rdi+28h], rax
0x18007900c  lea     rax, ??_7?$CComObject@VCUpdateSession@@@ATL@@6B?$IDispatchImpl@UIUpdateSession3@@$1?IID_IUpdateSession3@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CUpdateSession>::`vftable'{for `ATL::IDispatchImpl<IUpdateSession3,&_GUID const IID_IUpdateSession3,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x180079013  mov     [rdi+30h], rax
0x180079017  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18007901e  mov     rax, [rcx]
0x180079021  mov     rax, [rax+8]
0x180079025  call    _guard_dispatch_icall
0x18007902a  jmp     short loc_18007902E
0x18007902c  xor     edi, edi
0x18007902e  mov     [rsp+48h+arg_18], rdi
0x180079033  jmp     short loc_180079048
0x180079035  mov     rsi, [rsp+48h+arg_10]
0x18007903a  mov     r14, [rsp+48h+arg_8]
0x18007903f  mov     ebx, dword ptr [rsp+48h+arg_0]
0x180079043  mov     rdi, [rsp+48h+arg_18]
0x180079048  test    rdi, rdi
0x18007904b  jz      loc_1800790EF
0x180079051  lock inc dword ptr [rdi+38h]
0x180079055  xor     r8d, r8d; Flags
0x180079058  xor     edx, edx; dwSpinCount
0x18007905a  lea     rcx, [rdi+40h]; lpCriticalSection
0x18007905e  call    cs:__imp_InitializeCriticalSectionEx
0x180079064  test    eax, eax
0x180079066  jnz     short loc_180079080
0x180079068  call    cs:__imp_GetLastError
0x18007906e  movzx   ecx, ax
0x180079071  or      ecx, 80070000h
0x180079077  test    eax, eax
0x180079079  cmovle  ecx, eax
0x18007907c  test    ecx, ecx
0x18007907e  js      short loc_1800790B2
0x180079080  mov     byte ptr [rdi+68h], 1
0x180079084  mov     ecx, 80000002h; unsigned int
0x180079089  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18007908e  mov     ecx, eax
0x180079090  test    eax, eax
0x180079092  js      short loc_1800790B2
0x180079094  mov     rax, [rdi]
0x180079097  mov     rcx, rdi
0x18007909a  mov     rax, [rax+8]
0x18007909e  call    _guard_dispatch_icall
0x1800790a3  mov     rcx, rax; punkOuter
0x1800790a6  lea     rdx, [rdi+70h]; ppunkMarshal
0x1800790aa  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800790b0  mov     ecx, eax
0x1800790b2  xor     ebx, ebx
0x1800790b4  test    ecx, ecx
0x1800790b6  cmovs   ebx, ecx
0x1800790b9  lock dec dword ptr [rdi+38h]
0x1800790bd  test    ebx, ebx
0x1800790bf  jnz     short loc_1800790DC
0x1800790c1  lea     rcx, [rdi+18h]
0x1800790c5  mov     rax, [rcx]
0x1800790c8  mov     r8, rsi
0x1800790cb  mov     rdx, r14
0x1800790ce  mov     rax, [rax]
0x1800790d1  call    _guard_dispatch_icall
0x1800790d6  mov     ebx, eax
0x1800790d8  test    eax, eax
0x1800790da  jz      short loc_1800790EF
0x1800790dc  mov     r8, [rdi]
0x1800790df  mov     edx, 1
0x1800790e4  mov     rcx, rdi
0x1800790e7  mov     rax, [r8]
0x1800790ea  call    _guard_dispatch_icall
0x1800790ef  mov     eax, ebx
0x1800790f1  add     rsp, 28h
0x1800790f5  pop     r14
0x1800790f7  pop     rdi
0x1800790f8  pop     rsi
0x1800790f9  pop     rbx
0x1800790fa  retn
```
