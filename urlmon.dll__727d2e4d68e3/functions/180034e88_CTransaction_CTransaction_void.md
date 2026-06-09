# CTransaction::~CTransaction(void)

- ea: `0x180034e88`
- end: `0x180035462`
- name: `??1CTransaction@@UEAA@XZ`
- size: `1498`
- prototype: `void __fastcall(CTransaction *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034d14`
- `0x180084904`
- `0x1800f24e0`

## callees

- `0x18002f2c0`
- `0x18002fee0`
- `0x180034e88`
- `0x180035468`
- `0x18003564c`
- `0x18003580c`
- `0x18004ba18`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_DPA_DestroyCallback` at `0x18003533b`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18003533b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035185`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035198`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800351ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800351be`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800351d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035357`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035185`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035198`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800351ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800351be`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800351d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800352ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035300`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800352ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003500b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003503b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003506b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003500b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003503b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003506b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800353a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180035432`
- `OLEAUT32!__imp_SysFreeString` at `0x18003544a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800353a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180035432`
- `OLEAUT32!__imp_SysFreeString` at `0x18003544a`

## pseudocode

```c
void __fastcall CTransaction::~CTransaction(CTransaction *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  OLECHAR *v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // edx
  struct _DPA *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  CTransPacket *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  BINDINFO *v20; // rcx
  __int64 v21; // rdi
  void *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rdi
  OLECHAR *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdi
  OLECHAR *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx

  *(_QWORD *)this = &CTransaction::`vftable'{for `IInternetProtocolSink'};
  *((_QWORD *)this + 1) = &LegacyTransaction::`vftable'{for `ITransProtocolSink'};
  *((_QWORD *)this + 2) = &CTransaction::`vftable'{for `IInternetBindInfoEx'};
  *((_QWORD *)this + 3) = &CTransaction::`vftable'{for `IDevToolbarDownloadInitiatorInfo'};
  *((_QWORD *)this + 4) = &CTransaction::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 5) = &CTransaction::`vftable'{for `IAuthenticate'};
  *((_QWORD *)this + 6) = &CTransaction::`vftable'{for `IInternetProtocolEx'};
  *((_QWORD *)this + 7) = &LegacyTransaction::`vftable'{for `IInternetPriority'};
  *((_QWORD *)this + 8) = &CTransaction::`vftable'{for `IInternetPriorityInternal'};
  *((_QWORD *)this + 9) = &EdgeTransaction::`vftable'{for `IWrappedProtocol'};
  *((_QWORD *)this + 10) = &EdgeTransaction::`vftable'{for `IUriContainer'};
  *((_QWORD *)this + 11) = &EdgeTransaction::`vftable'{for `IPreBindingSupport'};
  *((_QWORD *)this + 12) = &CTransaction::`vftable'{for `ITransactionInternal'};
  *((_QWORD *)this + 13) = &CTransaction::`vftable'{for `IProtocolHandlerValidator'};
  *((_QWORD *)this + 14) = &CTransaction::`vftable'{for `IWinInetHttpTimeouts'};
  *((_QWORD *)this + 15) = &LegacyTransaction::`vftable'{for `IInternetBindInfoInternal'};
  *((_QWORD *)this + 16) = &CTransaction::`vftable'{for `IDownloadModeHandleCallback'};
  *((_QWORD *)this + 17) = &LegacyTransaction::`vftable'{for `IInternetPriorityInfoInternal'};
  if ( *((char *)this + 441) < 0 )
  {
    v30 = *((_QWORD *)this + 39);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
  }
  v2 = *((_QWORD *)this + 27);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 27) = 0;
    v3 = *((_QWORD *)this + 29);
    if ( v3 || *((_DWORD *)this + 60) )
    {
      v4 = (OLECHAR *)*((_QWORD *)this + 31);
      if ( v4 )
      {
        SysFreeString(v4);
        *((_QWORD *)this + 31) = 0;
      }
      *((_QWORD *)this + 32) = 0;
      *((_DWORD *)this + 66) = 0;
      if ( v3 )
      {
        v5 = *((_QWORD *)this + 29);
        if ( v5 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          *((_QWORD *)this + 29) = 0;
        }
      }
    }
    *((_DWORD *)this + 60) = 0;
  }
  CTransaction::SetRedirectIUri(this, 0);
  v7 = (struct _DPA *)*((_QWORD *)this + 35);
  if ( v7 )
  {
    DPA_DestroyCallback(v7, DPA_ReleaseCB<IUri>, 0);
    *((_QWORD *)this + 35) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 60);
  if ( v8 )
    CoTaskMemFree(v8);
  v9 = (void *)*((_QWORD *)this + 61);
  if ( v9 )
    CoTaskMemFree(v9);
  v10 = (void *)*((_QWORD *)this + 63);
  if ( v10 )
    CoTaskMemFree(v10);
  v11 = (void *)*((_QWORD *)this + 62);
  if ( v11 )
    CoTaskMemFree(v11);
  v12 = (void *)*((_QWORD *)this + 59);
  if ( v12 )
    CoTaskMemFree(v12);
  while ( 1 )
  {
    v13 = (CTransPacket *)*((_QWORD *)this + 48);
    if ( !v13 )
      break;
    *((_QWORD *)this + 48) = *((_QWORD *)v13 + 7);
    CTransPacket::`scalar deleting destructor'(v13, v6);
  }
  v14 = *((_QWORD *)this + 37);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v15 = *((_QWORD *)this + 36);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)this + 36) = 0;
  }
  v16 = *((_QWORD *)this + 39);
  if ( v16 && !*((_QWORD *)this + 18) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 39) = 0;
  if ( v17 && !*((_QWORD *)this + 18) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = *((_QWORD *)this + 40);
  *((_QWORD *)this + 41) = 0;
  if ( v18 && !*((_QWORD *)this + 18) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = *((_QWORD *)this + 18);
  *((_QWORD *)this + 40) = 0;
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)this + 18) = 0;
  }
  v20 = (BINDINFO *)*((_QWORD *)this + 93);
  if ( v20 )
  {
    ReleaseBindInfo(v20);
    operator delete(*((void **)this + 93));
  }
  CTransaction::CloseNotificationWindow(this);
  v21 = *((_QWORD *)this + 192);
  if ( v21 )
  {
    *((_QWORD *)this + 192) = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21, 0xFFFFFFFF) == 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v21 + 24));
      operator delete((void *)v21);
    }
  }
  COInetProt::~COInetProt((CTransaction *)((char *)this + 1144));
  COInetProt::~COInetProt((CTransaction *)((char *)this + 784));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
  v22 = (void *)*((_QWORD *)this + 67);
  if ( v22 )
    LocalFree(v22);
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 66) = 0;
  v23 = (void *)*((_QWORD *)this + 65);
  if ( v23 )
    LocalFree(v23);
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 64) = 0;
  v24 = *((_QWORD *)this + 29);
  *((_QWORD *)this + 28) = &CUString::`vftable';
  if ( v24 || *((_DWORD *)this + 60) != 11 )
  {
    v25 = (OLECHAR *)*((_QWORD *)this + 31);
    if ( v25 )
    {
      SysFreeString(v25);
      *((_QWORD *)this + 31) = 0;
    }
    *((_QWORD *)this + 32) = 0;
    *((_DWORD *)this + 66) = 0;
    if ( v24 )
    {
      v26 = *((_QWORD *)this + 29);
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        *((_QWORD *)this + 29) = 0;
      }
    }
  }
  *((_DWORD *)this + 60) = 11;
  v27 = *((_QWORD *)this + 22);
  *((_QWORD *)this + 21) = &CUString::`vftable';
  if ( v27 || *((_DWORD *)this + 46) != 11 )
  {
    v28 = (OLECHAR *)*((_QWORD *)this + 24);
    if ( v28 )
    {
      SysFreeString(v28);
      *((_QWORD *)this + 24) = 0;
    }
    *((_QWORD *)this + 25) = 0;
    *((_DWORD *)this + 52) = 0;
    if ( v27 )
    {
      v29 = *((_QWORD *)this + 22);
      if ( v29 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        *((_QWORD *)this + 22) = 0;
      }
    }
  }
  *((_DWORD *)this + 46) = 11;
}

```

## disassembly

```asm
0x180034e88  push    rbx
0x180034e8a  push    rsi
0x180034e8b  push    rdi
0x180034e8c  push    r14
0x180034e8e  sub     rsp, 28h
0x180034e92  lea     rax, ??_7CTransaction@@6BIInternetProtocolSink@@@; const CTransaction::`vftable'{for `IInternetProtocolSink'}
0x180034e99  xor     esi, esi
0x180034e9b  mov     rbx, rcx
0x180034e9e  mov     [rcx], rax
0x180034ea1  lea     rax, ??_7LegacyTransaction@@6BITransProtocolSink@@@; const LegacyTransaction::`vftable'{for `ITransProtocolSink'}
0x180034ea8  mov     [rcx+8], rax
0x180034eac  lea     rax, ??_7CTransaction@@6BIInternetBindInfoEx@@@; const CTransaction::`vftable'{for `IInternetBindInfoEx'}
0x180034eb3  mov     [rcx+10h], rax
0x180034eb7  lea     rax, ??_7CTransaction@@6BIDevToolbarDownloadInitiatorInfo@@@; const CTransaction::`vftable'{for `IDevToolbarDownloadInitiatorInfo'}
0x180034ebe  mov     [rcx+18h], rax
0x180034ec2  lea     rax, ??_7CTransaction@@6BIServiceProvider@@@; const CTransaction::`vftable'{for `IServiceProvider'}
0x180034ec9  mov     [rcx+20h], rax
0x180034ecd  lea     rax, ??_7CTransaction@@6BIAuthenticate@@@; const CTransaction::`vftable'{for `IAuthenticate'}
0x180034ed4  mov     [rcx+28h], rax
0x180034ed8  lea     rax, ??_7CTransaction@@6BIInternetProtocolEx@@@; const CTransaction::`vftable'{for `IInternetProtocolEx'}
0x180034edf  mov     [rcx+30h], rax
0x180034ee3  lea     rax, ??_7LegacyTransaction@@6BIInternetPriority@@@; const LegacyTransaction::`vftable'{for `IInternetPriority'}
0x180034eea  mov     [rcx+38h], rax
0x180034eee  lea     rax, ??_7CTransaction@@6BIInternetPriorityInternal@@@; const CTransaction::`vftable'{for `IInternetPriorityInternal'}
0x180034ef5  mov     [rcx+40h], rax
0x180034ef9  lea     rax, ??_7EdgeTransaction@@6BIWrappedProtocol@@@; const EdgeTransaction::`vftable'{for `IWrappedProtocol'}
0x180034f00  mov     [rcx+48h], rax
0x180034f04  lea     rax, ??_7EdgeTransaction@@6BIUriContainer@@@; const EdgeTransaction::`vftable'{for `IUriContainer'}
0x180034f0b  mov     [rcx+50h], rax
0x180034f0f  lea     rax, ??_7EdgeTransaction@@6BIPreBindingSupport@@@; const EdgeTransaction::`vftable'{for `IPreBindingSupport'}
0x180034f16  mov     [rcx+58h], rax
0x180034f1a  lea     rax, ??_7CTransaction@@6BITransactionInternal@@@; const CTransaction::`vftable'{for `ITransactionInternal'}
0x180034f21  mov     [rcx+60h], rax
0x180034f25  lea     rax, ??_7CTransaction@@6BIProtocolHandlerValidator@@@; const CTransaction::`vftable'{for `IProtocolHandlerValidator'}
0x180034f2c  mov     [rcx+68h], rax
0x180034f30  lea     rax, ??_7CTransaction@@6BIWinInetHttpTimeouts@@@; const CTransaction::`vftable'{for `IWinInetHttpTimeouts'}
0x180034f37  mov     [rcx+70h], rax
0x180034f3b  lea     rax, ??_7LegacyTransaction@@6BIInternetBindInfoInternal@@@; const LegacyTransaction::`vftable'{for `IInternetBindInfoInternal'}
0x180034f42  mov     [rcx+78h], rax
0x180034f46  lea     rax, ??_7CTransaction@@6BIDownloadModeHandleCallback@@@; const CTransaction::`vftable'{for `IDownloadModeHandleCallback'}
0x180034f4d  mov     [rcx+80h], rax
0x180034f54  lea     rax, ??_7LegacyTransaction@@6BIInternetPriorityInfoInternal@@@; const LegacyTransaction::`vftable'{for `IInternetPriorityInfoInternal'}
0x180034f5b  mov     [rcx+88h], rax
0x180034f62  cmp     [rcx+1B9h], sil
0x180034f69  jl      loc_180035381
0x180034f6f  mov     rcx, [rbx+0D8h]
0x180034f76  test    rcx, rcx
0x180034f79  jz      short loc_180034FE5
0x180034f7b  mov     rax, [rcx]
0x180034f7e  mov     rax, [rax+10h]
0x180034f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f87  mov     [rbx+0D8h], rsi
0x180034f8e  mov     rdi, [rbx+0E8h]
0x180034f95  test    rdi, rdi
0x180034f98  jz      loc_180035370
0x180034f9e  mov     rcx, [rbx+0F8h]; bstrString
0x180034fa5  test    rcx, rcx
0x180034fa8  jnz     loc_1800353A2
0x180034fae  mov     [rbx+100h], rsi
0x180034fb5  mov     [rbx+108h], esi
0x180034fbb  test    rdi, rdi
0x180034fbe  jz      short loc_180034FDF
0x180034fc0  mov     rcx, [rbx+0E8h]
0x180034fc7  test    rcx, rcx
0x180034fca  jz      short loc_180034FDF
0x180034fcc  mov     rax, [rcx]
0x180034fcf  mov     rax, [rax+10h]
0x180034fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fd8  mov     [rbx+0E8h], rsi
0x180034fdf  mov     [rbx+0F0h], esi
0x180034fe5  xor     edx, edx; struct IUri *
0x180034fe7  mov     rcx, rbx; this
0x180034fea  call    ?SetRedirectIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetRedirectIUri(IUri *)
0x180034fef  mov     rcx, [rbx+118h]; hdpa
0x180034ff6  test    rcx, rcx
0x180034ff9  jnz     loc_180035331
0x180034fff  mov     rcx, [rbx+1E0h]; pv
0x180035006  test    rcx, rcx
0x180035009  jz      short loc_180035017
0x18003500b  call    cs:__imp_CoTaskMemFree
0x180035012  nop     dword ptr [rax+rax+00h]
0x180035017  mov     rcx, [rbx+1E8h]; pv
0x18003501e  test    rcx, rcx
0x180035021  jz      short loc_18003502F
0x180035023  call    cs:__imp_CoTaskMemFree
0x18003502a  nop     dword ptr [rax+rax+00h]
0x18003502f  mov     rcx, [rbx+1F8h]; pv
0x180035036  test    rcx, rcx
0x180035039  jz      short loc_180035047
0x18003503b  call    cs:__imp_CoTaskMemFree
0x180035042  nop     dword ptr [rax+rax+00h]
0x180035047  mov     rcx, [rbx+1F0h]; pv
0x18003504e  test    rcx, rcx
0x180035051  jz      short loc_18003505F
0x180035053  call    cs:__imp_CoTaskMemFree
0x18003505a  nop     dword ptr [rax+rax+00h]
0x18003505f  mov     rcx, [rbx+1D8h]; pv
0x180035066  test    rcx, rcx
0x180035069  jz      short loc_180035077
0x18003506b  call    cs:__imp_CoTaskMemFree
0x180035072  nop     dword ptr [rax+rax+00h]
0x180035077  mov     rcx, [rbx+180h]; this
0x18003507e  test    rcx, rcx
0x180035081  jnz     loc_1800353BA
0x180035087  mov     rcx, [rbx+128h]
0x18003508e  test    rcx, rcx
0x180035091  jnz     loc_1800353CF
0x180035097  mov     rcx, [rbx+120h]
0x18003509e  test    rcx, rcx
0x1800350a1  jz      short loc_1800350B6
0x1800350a3  mov     rax, [rcx]
0x1800350a6  mov     rax, [rax+10h]
0x1800350aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350af  mov     [rbx+120h], rsi
0x1800350b6  mov     rcx, [rbx+138h]
0x1800350bd  test    rcx, rcx
0x1800350c0  jz      short loc_1800350D7
0x1800350c2  cmp     [rbx+90h], rsi
0x1800350c9  jnz     short loc_1800350D7
0x1800350cb  mov     rax, [rcx]
0x1800350ce  mov     rax, [rax+10h]
0x1800350d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350d7  mov     rcx, [rbx+148h]
0x1800350de  mov     [rbx+138h], rsi
0x1800350e5  test    rcx, rcx
0x1800350e8  jnz     loc_1800353E0
0x1800350ee  mov     rcx, [rbx+140h]
0x1800350f5  mov     [rbx+148h], rsi
0x1800350fc  test    rcx, rcx
0x1800350ff  jnz     loc_1800353FE
0x180035105  mov     rcx, [rbx+90h]
0x18003510c  mov     [rbx+140h], rsi
0x180035113  test    rcx, rcx
0x180035116  jz      short loc_18003512B
0x180035118  mov     rax, [rcx]
0x18003511b  mov     rax, [rax+10h]
0x18003511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035124  mov     [rbx+90h], rsi
0x18003512b  mov     rcx, [rbx+2E8h]; pbindinfo
0x180035132  test    rcx, rcx
0x180035135  jnz     loc_18003541C
0x18003513b  mov     rcx, rbx; this
0x18003513e  call    ?CloseNotificationWindow@CTransaction@@IEAAXXZ; CTransaction::CloseNotificationWindow(void)
0x180035143  mov     rdi, [rbx+600h]
0x18003514a  test    rdi, rdi
0x18003514d  jz      short loc_180035166
0x18003514f  mov     [rbx+600h], rsi
0x180035156  or      eax, 0FFFFFFFFh
0x180035159  lock xadd [rdi], eax
0x18003515d  cmp     eax, 1
0x180035160  jz      loc_180035353
0x180035166  lea     rcx, [rbx+478h]; this
0x18003516d  call    ??1COInetProt@@QEAA@XZ; COInetProt::~COInetProt(void)
0x180035172  lea     rcx, [rbx+310h]; this
0x180035179  call    ??1COInetProt@@QEAA@XZ; COInetProt::~COInetProt(void)
0x18003517e  lea     rcx, [rbx+2C0h]; lpCriticalSection
0x180035185  call    cs:__imp_DeleteCriticalSection
0x18003518c  nop     dword ptr [rax+rax+00h]
0x180035191  lea     rcx, [rbx+298h]; lpCriticalSection
0x180035198  call    cs:__imp_DeleteCriticalSection
0x18003519f  nop     dword ptr [rax+rax+00h]
0x1800351a4  lea     rcx, [rbx+270h]; lpCriticalSection
0x1800351ab  call    cs:__imp_DeleteCriticalSection
0x1800351b2  nop     dword ptr [rax+rax+00h]
0x1800351b7  lea     rcx, [rbx+248h]; lpCriticalSection
0x1800351be  call    cs:__imp_DeleteCriticalSection
0x1800351c5  nop     dword ptr [rax+rax+00h]
0x1800351ca  lea     rcx, [rbx+220h]; lpCriticalSection
0x1800351d1  call    cs:__imp_DeleteCriticalSection
0x1800351d8  nop     dword ptr [rax+rax+00h]
0x1800351dd  mov     rcx, [rbx+218h]; hMem
0x1800351e4  test    rcx, rcx
0x1800351e7  jnz     loc_1800352EF
0x1800351ed  mov     [rbx+218h], rsi
0x1800351f4  mov     [rbx+210h], rsi
0x1800351fb  mov     rcx, [rbx+208h]; hMem
0x180035202  test    rcx, rcx
0x180035205  jnz     loc_180035300
0x18003520b  mov     [rbx+208h], rsi
0x180035212  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180035219  mov     [rbx+200h], rsi
0x180035220  mov     rdi, [rbx+0E8h]
0x180035227  mov     [rbx+0E0h], r14
0x18003522e  test    rdi, rdi
0x180035231  jz      loc_180035311
0x180035237  mov     rcx, [rbx+0F8h]; bstrString
0x18003523e  test    rcx, rcx
0x180035241  jnz     loc_180035432
0x180035247  mov     [rbx+100h], rsi
0x18003524e  mov     [rbx+108h], esi
0x180035254  test    rdi, rdi
0x180035257  jz      short loc_180035278
0x180035259  mov     rcx, [rbx+0E8h]
0x180035260  test    rcx, rcx
0x180035263  jz      short loc_180035278
0x180035265  mov     rax, [rcx]
0x180035268  mov     rax, [rax+10h]
0x18003526c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035271  mov     [rbx+0E8h], rsi
0x180035278  mov     dword ptr [rbx+0F0h], 0Bh
0x180035282  mov     rdi, [rbx+0B0h]
0x180035289  mov     [rbx+0A8h], r14
0x180035290  test    rdi, rdi
0x180035293  jz      loc_180035323
0x180035299  mov     rcx, [rbx+0C0h]; bstrString
0x1800352a0  test    rcx, rcx
0x1800352a3  jnz     loc_18003544A
0x1800352a9  mov     [rbx+0C8h], rsi
0x1800352b0  mov     [rbx+0D0h], esi
0x1800352b6  test    rdi, rdi
0x1800352b9  jz      short loc_1800352DA
0x1800352bb  mov     rcx, [rbx+0B0h]
0x1800352c2  test    rcx, rcx
0x1800352c5  jz      short loc_1800352DA
0x1800352c7  mov     rax, [rcx]
0x1800352ca  mov     rax, [rax+10h]
0x1800352ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352d3  mov     [rbx+0B0h], rsi
0x1800352da  mov     dword ptr [rbx+0B8h], 0Bh
0x1800352e4  add     rsp, 28h
0x1800352e8  pop     r14
0x1800352ea  pop     rdi
0x1800352eb  pop     rsi
0x1800352ec  pop     rbx
0x1800352ed  retn
0x1800352ef  call    cs:__imp_LocalFree
0x1800352f6  nop     dword ptr [rax+rax+00h]
0x1800352fb  jmp     loc_1800351ED
0x180035300  call    cs:__imp_LocalFree
0x180035307  nop     dword ptr [rax+rax+00h]
0x18003530c  jmp     loc_18003520B
0x180035311  cmp     dword ptr [rbx+0F0h], 0Bh
0x180035318  jz      loc_180035278
0x18003531e  jmp     loc_180035237
0x180035323  cmp     dword ptr [rbx+0B8h], 0Bh
0x18003532a  jz      short loc_1800352DA
0x18003532c  jmp     loc_180035299
0x180035331  xor     r8d, r8d; pData
0x180035334  lea     rdx, ??$DPA_ReleaseCB@UIUri@@@@YAHPEAUIUri@@PEAX@Z; pfnCB
0x18003533b  call    cs:__imp_DPA_DestroyCallback
0x180035342  nop     dword ptr [rax+rax+00h]
0x180035347  mov     [rbx+118h], rsi
0x18003534e  jmp     loc_180034FFF
0x180035353  lea     rcx, [rdi+18h]; lpCriticalSection
0x180035357  call    cs:__imp_DeleteCriticalSection
0x18003535e  nop     dword ptr [rax+rax+00h]
0x180035363  mov     rcx, rdi; void *
0x180035366  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003536b  jmp     loc_180035166
0x180035370  cmp     [rbx+0F0h], esi
0x180035376  jz      loc_180034FDF
0x18003537c  jmp     loc_180034F9E
0x180035381  mov     rcx, [rcx+138h]
0x180035388  test    rcx, rcx
0x18003538b  jz      loc_180034F6F
0x180035391  mov     rax, [rcx]
0x180035394  mov     rax, [rax+60h]
0x180035398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003539d  jmp     loc_180034F6F
0x1800353a2  call    cs:__imp_SysFreeString
0x1800353a9  nop     dword ptr [rax+rax+00h]
0x1800353ae  mov     [rbx+0F8h], rsi
0x1800353b5  jmp     loc_180034FAE
0x1800353ba  mov     rax, [rcx+38h]
0x1800353be  mov     [rbx+180h], rax
0x1800353c5  call    ??_GCTransPacket@@QEAAPEAXI@Z; CTransPacket::`scalar deleting destructor'(uint)
0x1800353ca  jmp     loc_180035077
0x1800353cf  mov     rax, [rcx]
0x1800353d2  mov     rax, [rax+10h]
0x1800353d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353db  jmp     loc_180035097
0x1800353e0  cmp     [rbx+90h], rsi
0x1800353e7  jnz     loc_1800350EE
0x1800353ed  mov     rax, [rcx]
0x1800353f0  mov     rax, [rax+10h]
0x1800353f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353f9  jmp     loc_1800350EE
0x1800353fe  cmp     [rbx+90h], rsi
0x180035405  jnz     loc_180035105
0x18003540b  mov     rax, [rcx]
0x18003540e  mov     rax, [rax+10h]
0x180035412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035417  jmp     loc_180035105
0x18003541c  call    ReleaseBindInfo
0x180035421  mov     rcx, [rbx+2E8h]; void *
0x180035428  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003542d  jmp     loc_18003513B
0x180035432  call    cs:__imp_SysFreeString
0x180035439  nop     dword ptr [rax+rax+00h]
0x18003543e  mov     [rbx+0F8h], rsi
0x180035445  jmp     loc_180035247
0x18003544a  call    cs:__imp_SysFreeString
0x180035451  nop     dword ptr [rax+rax+00h]
0x180035456  mov     [rbx+0C0h], rsi
0x18003545d  jmp     loc_1800352A9
```
