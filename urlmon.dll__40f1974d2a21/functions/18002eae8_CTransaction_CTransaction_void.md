# CTransaction::~CTransaction(void)

- ea: `0x18002eae8`
- end: `0x18002f057`
- name: `??1CTransaction@@UEAA@XZ`
- size: `1391`
- prototype: `void __fastcall(CTransaction *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e97c`
- `0x18007f4fc`
- `0x1800e8690`

## callees

- `0x18002eae8`
- `0x18002f060`
- `0x18002f214`
- `0x18002f3c4`
- `0x180030880`
- `0x1800502f0`
- `0x180079ae8`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_DPA_DestroyCallback` at `0x18002ef4e`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18002ef4e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edc7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edd4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ede1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edfb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ef64`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edc7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edd4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ede1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002edfb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ef64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ecb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ec8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ecb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002efa9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f033`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f045`
- `OLEAUT32!__imp_SysFreeString` at `0x18002efa9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f033`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f045`

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
    DPA_DestroyCallback(v7, (PFNDAENUMCALLBACK)DPA_ReleaseCB<IUri>, 0);
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
0x18002eae8  push    rbx
0x18002eaea  push    rsi
0x18002eaeb  push    rdi
0x18002eaec  push    r14
0x18002eaee  sub     rsp, 28h
0x18002eaf2  lea     rax, ??_7CTransaction@@6BIInternetProtocolSink@@@; const CTransaction::`vftable'{for `IInternetProtocolSink'}
0x18002eaf9  xor     esi, esi
0x18002eafb  mov     rbx, rcx
0x18002eafe  mov     [rcx], rax
0x18002eb01  lea     rax, ??_7LegacyTransaction@@6BITransProtocolSink@@@; const LegacyTransaction::`vftable'{for `ITransProtocolSink'}
0x18002eb08  mov     [rcx+8], rax
0x18002eb0c  lea     rax, ??_7CTransaction@@6BIInternetBindInfoEx@@@; const CTransaction::`vftable'{for `IInternetBindInfoEx'}
0x18002eb13  mov     [rcx+10h], rax
0x18002eb17  lea     rax, ??_7CTransaction@@6BIDevToolbarDownloadInitiatorInfo@@@; const CTransaction::`vftable'{for `IDevToolbarDownloadInitiatorInfo'}
0x18002eb1e  mov     [rcx+18h], rax
0x18002eb22  lea     rax, ??_7CTransaction@@6BIServiceProvider@@@; const CTransaction::`vftable'{for `IServiceProvider'}
0x18002eb29  mov     [rcx+20h], rax
0x18002eb2d  lea     rax, ??_7CTransaction@@6BIAuthenticate@@@; const CTransaction::`vftable'{for `IAuthenticate'}
0x18002eb34  mov     [rcx+28h], rax
0x18002eb38  lea     rax, ??_7CTransaction@@6BIInternetProtocolEx@@@; const CTransaction::`vftable'{for `IInternetProtocolEx'}
0x18002eb3f  mov     [rcx+30h], rax
0x18002eb43  lea     rax, ??_7LegacyTransaction@@6BIInternetPriority@@@; const LegacyTransaction::`vftable'{for `IInternetPriority'}
0x18002eb4a  mov     [rcx+38h], rax
0x18002eb4e  lea     rax, ??_7CTransaction@@6BIInternetPriorityInternal@@@; const CTransaction::`vftable'{for `IInternetPriorityInternal'}
0x18002eb55  mov     [rcx+40h], rax
0x18002eb59  lea     rax, ??_7EdgeTransaction@@6BIWrappedProtocol@@@; const EdgeTransaction::`vftable'{for `IWrappedProtocol'}
0x18002eb60  mov     [rcx+48h], rax
0x18002eb64  lea     rax, ??_7EdgeTransaction@@6BIUriContainer@@@; const EdgeTransaction::`vftable'{for `IUriContainer'}
0x18002eb6b  mov     [rcx+50h], rax
0x18002eb6f  lea     rax, ??_7EdgeTransaction@@6BIPreBindingSupport@@@; const EdgeTransaction::`vftable'{for `IPreBindingSupport'}
0x18002eb76  mov     [rcx+58h], rax
0x18002eb7a  lea     rax, ??_7CTransaction@@6BITransactionInternal@@@; const CTransaction::`vftable'{for `ITransactionInternal'}
0x18002eb81  mov     [rcx+60h], rax
0x18002eb85  lea     rax, ??_7CTransaction@@6BIProtocolHandlerValidator@@@; const CTransaction::`vftable'{for `IProtocolHandlerValidator'}
0x18002eb8c  mov     [rcx+68h], rax
0x18002eb90  lea     rax, ??_7CTransaction@@6BIWinInetHttpTimeouts@@@; const CTransaction::`vftable'{for `IWinInetHttpTimeouts'}
0x18002eb97  mov     [rcx+70h], rax
0x18002eb9b  lea     rax, ??_7LegacyTransaction@@6BIInternetBindInfoInternal@@@; const LegacyTransaction::`vftable'{for `IInternetBindInfoInternal'}
0x18002eba2  mov     [rcx+78h], rax
0x18002eba6  lea     rax, ??_7CTransaction@@6BIDownloadModeHandleCallback@@@; const CTransaction::`vftable'{for `IDownloadModeHandleCallback'}
0x18002ebad  mov     [rcx+80h], rax
0x18002ebb4  lea     rax, ??_7LegacyTransaction@@6BIInternetPriorityInfoInternal@@@; const LegacyTransaction::`vftable'{for `IInternetPriorityInfoInternal'}
0x18002ebbb  mov     [rcx+88h], rax
0x18002ebc2  cmp     [rcx+1B9h], sil
0x18002ebc9  jl      loc_18002EF88
0x18002ebcf  mov     rcx, [rbx+0D8h]
0x18002ebd6  test    rcx, rcx
0x18002ebd9  jz      short loc_18002EC45
0x18002ebdb  mov     rax, [rcx]
0x18002ebde  mov     rax, [rax+10h]
0x18002ebe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebe7  mov     [rbx+0D8h], rsi
0x18002ebee  mov     rdi, [rbx+0E8h]
0x18002ebf5  test    rdi, rdi
0x18002ebf8  jz      loc_18002EF77
0x18002ebfe  mov     rcx, [rbx+0F8h]; bstrString
0x18002ec05  test    rcx, rcx
0x18002ec08  jnz     loc_18002EFA9
0x18002ec0e  mov     [rbx+100h], rsi
0x18002ec15  mov     [rbx+108h], esi
0x18002ec1b  test    rdi, rdi
0x18002ec1e  jz      short loc_18002EC3F
0x18002ec20  mov     rcx, [rbx+0E8h]
0x18002ec27  test    rcx, rcx
0x18002ec2a  jz      short loc_18002EC3F
0x18002ec2c  mov     rax, [rcx]
0x18002ec2f  mov     rax, [rax+10h]
0x18002ec33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec38  mov     [rbx+0E8h], rsi
0x18002ec3f  mov     [rbx+0F0h], esi
0x18002ec45  xor     edx, edx; struct IUri *
0x18002ec47  mov     rcx, rbx; this
0x18002ec4a  call    ?SetRedirectIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetRedirectIUri(IUri *)
0x18002ec4f  mov     rcx, [rbx+118h]; hdpa
0x18002ec56  test    rcx, rcx
0x18002ec59  jnz     loc_18002EF44
0x18002ec5f  mov     rcx, [rbx+1E0h]; pv
0x18002ec66  test    rcx, rcx
0x18002ec69  jz      short loc_18002EC71
0x18002ec6b  call    cs:__imp_CoTaskMemFree
0x18002ec71  mov     rcx, [rbx+1E8h]; pv
0x18002ec78  test    rcx, rcx
0x18002ec7b  jz      short loc_18002EC83
0x18002ec7d  call    cs:__imp_CoTaskMemFree
0x18002ec83  mov     rcx, [rbx+1F8h]; pv
0x18002ec8a  test    rcx, rcx
0x18002ec8d  jz      short loc_18002EC95
0x18002ec8f  call    cs:__imp_CoTaskMemFree
0x18002ec95  mov     rcx, [rbx+1F0h]; pv
0x18002ec9c  test    rcx, rcx
0x18002ec9f  jz      short loc_18002ECA7
0x18002eca1  call    cs:__imp_CoTaskMemFree
0x18002eca7  mov     rcx, [rbx+1D8h]; pv
0x18002ecae  test    rcx, rcx
0x18002ecb1  jz      short loc_18002ECB9
0x18002ecb3  call    cs:__imp_CoTaskMemFree
0x18002ecb9  mov     rcx, [rbx+180h]; this
0x18002ecc0  test    rcx, rcx
0x18002ecc3  jnz     loc_18002EFBB
0x18002ecc9  mov     rcx, [rbx+128h]
0x18002ecd0  test    rcx, rcx
0x18002ecd3  jnz     loc_18002EFD0
0x18002ecd9  mov     rcx, [rbx+120h]
0x18002ece0  test    rcx, rcx
0x18002ece3  jz      short loc_18002ECF8
0x18002ece5  mov     rax, [rcx]
0x18002ece8  mov     rax, [rax+10h]
0x18002ecec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecf1  mov     [rbx+120h], rsi
0x18002ecf8  mov     rcx, [rbx+138h]
0x18002ecff  test    rcx, rcx
0x18002ed02  jz      short loc_18002ED19
0x18002ed04  cmp     [rbx+90h], rsi
0x18002ed0b  jnz     short loc_18002ED19
0x18002ed0d  mov     rax, [rcx]
0x18002ed10  mov     rax, [rax+10h]
0x18002ed14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed19  mov     rcx, [rbx+148h]
0x18002ed20  mov     [rbx+138h], rsi
0x18002ed27  test    rcx, rcx
0x18002ed2a  jnz     loc_18002EFE1
0x18002ed30  mov     rcx, [rbx+140h]
0x18002ed37  mov     [rbx+148h], rsi
0x18002ed3e  test    rcx, rcx
0x18002ed41  jnz     loc_18002EFFF
0x18002ed47  mov     rcx, [rbx+90h]
0x18002ed4e  mov     [rbx+140h], rsi
0x18002ed55  test    rcx, rcx
0x18002ed58  jz      short loc_18002ED6D
0x18002ed5a  mov     rax, [rcx]
0x18002ed5d  mov     rax, [rax+10h]
0x18002ed61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed66  mov     [rbx+90h], rsi
0x18002ed6d  mov     rcx, [rbx+2E8h]; pbindinfo
0x18002ed74  test    rcx, rcx
0x18002ed77  jnz     loc_18002F01D
0x18002ed7d  mov     rcx, rbx; this
0x18002ed80  call    ?CloseNotificationWindow@CTransaction@@IEAAXXZ; CTransaction::CloseNotificationWindow(void)
0x18002ed85  mov     rdi, [rbx+600h]
0x18002ed8c  test    rdi, rdi
0x18002ed8f  jz      short loc_18002EDA8
0x18002ed91  mov     [rbx+600h], rsi
0x18002ed98  or      eax, 0FFFFFFFFh
0x18002ed9b  lock xadd [rdi], eax
0x18002ed9f  cmp     eax, 1
0x18002eda2  jz      loc_18002EF60
0x18002eda8  lea     rcx, [rbx+478h]; this
0x18002edaf  call    ??1COInetProt@@QEAA@XZ; COInetProt::~COInetProt(void)
0x18002edb4  lea     rcx, [rbx+310h]; this
0x18002edbb  call    ??1COInetProt@@QEAA@XZ; COInetProt::~COInetProt(void)
0x18002edc0  lea     rcx, [rbx+2C0h]; lpCriticalSection
0x18002edc7  call    cs:__imp_DeleteCriticalSection
0x18002edcd  lea     rcx, [rbx+298h]; lpCriticalSection
0x18002edd4  call    cs:__imp_DeleteCriticalSection
0x18002edda  lea     rcx, [rbx+270h]; lpCriticalSection
0x18002ede1  call    cs:__imp_DeleteCriticalSection
0x18002ede7  lea     rcx, [rbx+248h]; lpCriticalSection
0x18002edee  call    cs:__imp_DeleteCriticalSection
0x18002edf4  lea     rcx, [rbx+220h]; lpCriticalSection
0x18002edfb  call    cs:__imp_DeleteCriticalSection
0x18002ee01  mov     rcx, [rbx+218h]; hMem
0x18002ee08  test    rcx, rcx
0x18002ee0b  jnz     loc_18002EF0E
0x18002ee11  mov     [rbx+218h], rsi
0x18002ee18  mov     [rbx+210h], rsi
0x18002ee1f  mov     rcx, [rbx+208h]; hMem
0x18002ee26  test    rcx, rcx
0x18002ee29  jnz     loc_18002EF19
0x18002ee2f  mov     [rbx+208h], rsi
0x18002ee36  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x18002ee3d  mov     [rbx+200h], rsi
0x18002ee44  mov     rdi, [rbx+0E8h]
0x18002ee4b  mov     [rbx+0E0h], r14
0x18002ee52  test    rdi, rdi
0x18002ee55  jz      loc_18002EF24
0x18002ee5b  mov     rcx, [rbx+0F8h]; bstrString
0x18002ee62  test    rcx, rcx
0x18002ee65  jnz     loc_18002F033
0x18002ee6b  mov     [rbx+100h], rsi
0x18002ee72  mov     [rbx+108h], esi
0x18002ee78  test    rdi, rdi
0x18002ee7b  jz      short loc_18002EE9C
0x18002ee7d  mov     rcx, [rbx+0E8h]
0x18002ee84  test    rcx, rcx
0x18002ee87  jz      short loc_18002EE9C
0x18002ee89  mov     rax, [rcx]
0x18002ee8c  mov     rax, [rax+10h]
0x18002ee90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee95  mov     [rbx+0E8h], rsi
0x18002ee9c  mov     dword ptr [rbx+0F0h], 0Bh
0x18002eea6  mov     rdi, [rbx+0B0h]
0x18002eead  mov     [rbx+0A8h], r14
0x18002eeb4  test    rdi, rdi
0x18002eeb7  jz      short loc_18002EF36
0x18002eeb9  mov     rcx, [rbx+0C0h]; bstrString
0x18002eec0  test    rcx, rcx
0x18002eec3  jnz     loc_18002F045
0x18002eec9  mov     [rbx+0C8h], rsi
0x18002eed0  mov     [rbx+0D0h], esi
0x18002eed6  test    rdi, rdi
0x18002eed9  jz      short loc_18002EEFA
0x18002eedb  mov     rcx, [rbx+0B0h]
0x18002eee2  test    rcx, rcx
0x18002eee5  jz      short loc_18002EEFA
0x18002eee7  mov     rax, [rcx]
0x18002eeea  mov     rax, [rax+10h]
0x18002eeee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eef3  mov     [rbx+0B0h], rsi
0x18002eefa  mov     dword ptr [rbx+0B8h], 0Bh
0x18002ef04  add     rsp, 28h
0x18002ef08  pop     r14
0x18002ef0a  pop     rdi
0x18002ef0b  pop     rsi
0x18002ef0c  pop     rbx
0x18002ef0d  retn
0x18002ef0e  call    cs:__imp_LocalFree
0x18002ef14  jmp     loc_18002EE11
0x18002ef19  call    cs:__imp_LocalFree
0x18002ef1f  jmp     loc_18002EE2F
0x18002ef24  cmp     dword ptr [rbx+0F0h], 0Bh
0x18002ef2b  jz      loc_18002EE9C
0x18002ef31  jmp     loc_18002EE5B
0x18002ef36  cmp     dword ptr [rbx+0B8h], 0Bh
0x18002ef3d  jz      short loc_18002EEFA
0x18002ef3f  jmp     loc_18002EEB9
0x18002ef44  xor     r8d, r8d; pData
0x18002ef47  lea     rdx, ??$DPA_ReleaseCB@UIUri@@@@YAHPEAUIUri@@PEAX@Z; pfnCB
0x18002ef4e  call    cs:__imp_DPA_DestroyCallback
0x18002ef54  mov     [rbx+118h], rsi
0x18002ef5b  jmp     loc_18002EC5F
0x18002ef60  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002ef64  call    cs:__imp_DeleteCriticalSection
0x18002ef6a  mov     rcx, rdi; void *
0x18002ef6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ef72  jmp     loc_18002EDA8
0x18002ef77  cmp     [rbx+0F0h], esi
0x18002ef7d  jz      loc_18002EC3F
0x18002ef83  jmp     loc_18002EBFE
0x18002ef88  mov     rcx, [rcx+138h]
0x18002ef8f  test    rcx, rcx
0x18002ef92  jz      loc_18002EBCF
0x18002ef98  mov     rax, [rcx]
0x18002ef9b  mov     rax, [rax+60h]
0x18002ef9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efa4  jmp     loc_18002EBCF
0x18002efa9  call    cs:__imp_SysFreeString
0x18002efaf  mov     [rbx+0F8h], rsi
0x18002efb6  jmp     loc_18002EC0E
0x18002efbb  mov     rax, [rcx+38h]
0x18002efbf  mov     [rbx+180h], rax
0x18002efc6  call    ??_GCTransPacket@@QEAAPEAXI@Z; CTransPacket::`scalar deleting destructor'(uint)
0x18002efcb  jmp     loc_18002ECB9
0x18002efd0  mov     rax, [rcx]
0x18002efd3  mov     rax, [rax+10h]
0x18002efd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efdc  jmp     loc_18002ECD9
0x18002efe1  cmp     [rbx+90h], rsi
0x18002efe8  jnz     loc_18002ED30
0x18002efee  mov     rax, [rcx]
0x18002eff1  mov     rax, [rax+10h]
0x18002eff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002effa  jmp     loc_18002ED30
0x18002efff  cmp     [rbx+90h], rsi
0x18002f006  jnz     loc_18002ED47
0x18002f00c  mov     rax, [rcx]
0x18002f00f  mov     rax, [rax+10h]
0x18002f013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f018  jmp     loc_18002ED47
0x18002f01d  call    ReleaseBindInfo
0x18002f022  mov     rcx, [rbx+2E8h]; void *
0x18002f029  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f02e  jmp     loc_18002ED7D
0x18002f033  call    cs:__imp_SysFreeString
0x18002f039  mov     [rbx+0F8h], rsi
0x18002f040  jmp     loc_18002EE6B
0x18002f045  call    cs:__imp_SysFreeString
0x18002f04b  mov     [rbx+0C0h], rsi
0x18002f052  jmp     loc_18002EEC9
```
