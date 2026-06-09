# CWLIDFDProv::Query(IFunctionDiscoveryProviderQuery *,IFunctionInstanceCollection * *)

- ea: `0x180007b00`
- end: `0x18000815a`
- name: `?Query@CWLIDFDProv@@UEAAJPEAUIFunctionDiscoveryProviderQuery@@PEAPEAUIFunctionInstanceCollection@@@Z`
- size: `1626`
- prototype: `__int64 __fastcall(struct IFunctionDiscoveryProvider *this, struct IFunctionDiscoveryProviderQuery *, struct IFunctionInstanceCollection **, unsigned int)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002c64`
- `0x180003700`
- `0x180003728`
- `0x18000505c`
- `0x180005088`
- `0x1800054dc`
- `0x180005d3c`
- `0x180007b00`
- `0x180008430`
- `0x180008534`
- `0x180008edc`
- `0x180009cfc`
- `0x18000ab84`
- `0x18000aec0`
- `0x18000de3c`
- `0x18000e1c0`
- `0x18000e500`
- `0x18000eff8`
- `0x18000f0e4`
- `0x18000f11c`
- `0x18000f230`
- `0x18000f4cc`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080f7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180007c66`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180007c66`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008106`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180008106`

## string_xrefs

- `0x180007e54`: `WLIDCCreateContextEx returned PPCRL_NO_SUCH_HANDLE -- not a connected account?`

## pseudocode

```c
__int64 __fastcall CWLIDFDProv::Query(
        struct IFunctionDiscoveryProvider *this,
        struct IFunctionDiscoveryProviderQuery *a2,
        struct IFunctionInstanceCollection **a3,
        unsigned int a4)
{
  unsigned __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  HRESULT v10; // eax
  CWLIDQueue *v11; // rax
  struct IFunctionDiscoveryProviderVtbl *v12; // rax
  struct IFunctionDiscoveryProviderVtbl *lpVtbl; // rsi
  struct IFunctionDiscoveryProviderVtbl *v14; // r14
  struct IFunctionDiscoveryProviderVtbl *v15; // r15
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rcx
  unsigned __int64 v19; // r8
  int v20; // eax
  unsigned int v21; // edx
  unsigned __int8 v22; // dl
  PPTraceStatus *v23; // rcx
  bool v24; // al
  char v25; // cl
  const unsigned __int16 *String; // rax
  unsigned int i; // esi
  int v28; // eax
  struct IFunctionInstanceCollection *v29; // rax
  unsigned int v30; // ebx
  struct IFunctionInstance **v32; // [rsp+20h] [rbp-E8h]
  struct IFunctionInstance **v33; // [rsp+20h] [rbp-E8h]
  struct IFunctionInstance **v34; // [rsp+20h] [rbp-E8h]
  struct IFunctionInstance **v35; // [rsp+20h] [rbp-E8h]
  struct IFunctionInstance **v36; // [rsp+20h] [rbp-E8h]
  unsigned int v37; // [rsp+30h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-D0h] BYREF
  struct IFunctionInstanceCollection *v39; // [rsp+40h] [rbp-C8h] BYREF
  void *v40; // [rsp+48h] [rbp-C0h] BYREF
  struct IFunctionInstance *v41; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v42[4]; // [rsp+58h] [rbp-B0h] BYREF
  void *Block; // [rsp+78h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-88h] BYREF
  CWLIDQueue *v45; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v46[3]; // [rsp+90h] [rbp-78h] BYREF
  char v47; // [rsp+A8h] [rbp-60h]
  int v48; // [rsp+B0h] [rbp-58h] BYREF
  const wil::ResultException *v49; // [rsp+B8h] [rbp-50h] BYREF
  ATL::CAtlException *v50; // [rsp+C0h] [rbp-48h] BYREF
  CPassportException *v51; // [rsp+C8h] [rbp-40h] BYREF
  char v52; // [rsp+110h] [rbp+8h]
  int v53; // [rsp+128h] [rbp+20h] BYREF

  v53 = 0;
  v44 = 0;
  v37 = 0;
  pv = 0;
  v41 = 0;
  v39 = 0;
  v52 = 0;
  v40 = 0;
  Block = 0;
  v42[0] = "CWLIDFDProv::Query";
  v42[1] = &v53;
  v42[2] = 0;
  v42[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"\\fdprov.cpp",
    "CWLIDFDProv::Query",
    (const char *)0x69,
    a4,
    (const unsigned __int16 *)v32);
  if ( !LOBYTE(this[17].lpVtbl) )
  {
    v53 = -2147418113;
    CTraceFuncW<long>::~CTraceFuncW<long>(v42);
    goto LABEL_69;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( a2 && a3 )
    {
      v8 = ((__int64 (__fastcall *)(struct IFunctionDiscoveryProviderQuery *, __int64 *))a2->lpVtbl->GetQueryConstraints)(
             a2,
             &v44);
      v53 = v8;
      if ( v8 < 0 )
      {
        LODWORD(v33) = v8;
        TracePrintW(2u, "\\fdprov.cpp", 0x7Cu, L"Couldn't retrieve query contraints. (0x%x)", v33);
        CTraceFuncW<long>::~CTraceFuncW<long>(v42);
        goto LABEL_69;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v44 + 32LL))(
             v44,
             L"OwnerName",
             &pv);
      v53 = v9;
      if ( v9 < 0 )
      {
        LODWORD(v33) = v9;
        TracePrintW(2u, "\\fdprov.cpp", 0x86u, L"Couldn't retrieve owner name from query contraints. (0x%x)", v33);
        CTraceFuncW<long>::~CTraceFuncW<long>(v42);
        goto LABEL_69;
      }
      v10 = CoImpersonateClient();
      v53 = v10;
      if ( v10 >= 0 )
      {
        v52 = 1;
        goto LABEL_13;
      }
      if ( v10 == -2147417833 )
      {
        v53 = 0;
LABEL_13:
        if ( LOBYTE(this[15].lpVtbl) )
        {
          CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
            v46,
            &this[8]);
          TracePrintW(5u, "\\fdprov.cpp", 0x9Eu, L"Query is Async.");
          if ( !this[16].lpVtbl )
          {
            v11 = (CWLIDQueue *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
            v45 = v11;
            if ( v11 )
              v12 = (struct IFunctionDiscoveryProviderVtbl *)CWLIDQueue::CWLIDQueue(v11);
            else
              v12 = 0;
            this[16].lpVtbl = v12;
            if ( !v12 )
            {
              v53 = -2147024882;
              CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(v46);
              CTraceFuncW<long>::~CTraceFuncW<long>(v42);
              goto LABEL_69;
            }
            v53 = CWLIDTimerQueue::Initialize((CWLIDTimerQueue *)&v12[1]);
            if ( v53 < 0 )
            {
              CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(v46);
              CTraceFuncW<long>::~CTraceFuncW<long>(v42);
              goto LABEL_69;
            }
          }
          lpVtbl = this[16].lpVtbl;
          v14 = this[14].lpVtbl;
          v15 = this[13].lpVtbl;
          v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &v45,
                  pv);
          v53 = CWLIDQueue::QueueItem((_QWORD *)(_DWORD)lpVtbl, v16, (int)this, (unsigned int)v15, (__int64)v14);
          ATL::CStringData::Release((CWLIDQueue *)((char *)v45 - 24));
          if ( v53 < 0 )
          {
            LODWORD(v34) = v53;
            TracePrintW(2u, "\\fdprov.cpp", 0xB8u, L"Failed to queue Item. (0x%x)", v34);
            CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(v46);
            CTraceFuncW<long>::~CTraceFuncW<long>(v42);
            goto LABEL_69;
          }
          *a3 = 0;
          v53 = -2147483638;
          CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(v46);
          goto LABEL_43;
        }
        TracePrintW(5u, "\\fdprov.cpp", 0xC6u, L"Query is Sync.");
        v20 = WLIDCCreateContextEx(v18, v17, v19, &v40);
        v53 = v20;
        if ( v20 == -2147188724 )
        {
          TracePrintW(
            5u,
            "\\fdprov.cpp",
            0xD6u,
            L"WLIDCCreateContextEx returned PPCRL_NO_SUCH_HANDLE -- not a connected account?");
          v53 = 0;
        }
        else if ( v20 < 0
               || (v20 = WLIDCEnumerateUserAssociatedDevices(
                           v40,
                           v21,
                           (unsigned __int16 *)pv,
                           &v37,
                           (struct __MIDL_liveidsvc_0003 **)&Block),
                   v53 = v20,
                   v20 < 0) )
        {
          LODWORD(v33) = v20;
          TracePrintW(2u, "\\fdprov.cpp", 0xE5u, L"Failed to enumerate devices. (0x%x)", v33);
          if ( v53 == -2147186655 || v53 == -2147186459 )
          {
            v53 = -2147024810;
            LODWORD(v36) = -2147024810;
            TracePrintW(2u, "\\fdprov.cpp", 0xEBu, L"Returning invalid password instead. (0x%x)", v36);
          }
LABEL_43:
          CTraceFuncW<long>::~CTraceFuncW<long>(v42);
          goto LABEL_69;
        }
        if ( !PPTraceShouldRedact() || (LOBYTE(v23) = 1, v24 = PPTraceStatus::TraceOnFlag(v23, v22), v25 = 1, !v24) )
          v25 = 0;
        v46[1] = pv;
        v46[2] = 0;
        v47 = v25;
        v46[0] = &PPRedactedStringW::`vftable';
        String = PPRedactedStringW::GetString((PPRedactedStringW *)v46);
        LODWORD(v33) = v37;
        TracePrintW(5u, "\\fdprov.cpp", 0xF1u, L"Enumerated %u devices for owner %ls", v33, String);
        PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v46);
        v53 = (*((__int64 (__fastcall **)(struct IFunctionDiscoveryProviderVtbl *, struct IFunctionInstanceCollection **))this[13].lpVtbl->QueryInterface
               + 5))(
                this[13].lpVtbl,
                &v39);
        if ( v53 >= 0 )
        {
          for ( i = 0; i < v37; ++i )
          {
            v28 = ((__int64 (__usercall *)@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, struct IFunctionDiscoveryProvider *@<r8>, struct IFunctionDiscoveryProviderFactory *@<r9>, struct IFunctionInstance **))CWLIDFDProv::BuildInstance)(
                    *((unsigned __int16 **)Block + 2 * i),
                    *((unsigned __int16 **)Block + 2 * i + 1),
                    this,
                    (struct IFunctionDiscoveryProviderFactory *)this[13].lpVtbl,
                    &v41);
            v53 = v28;
            if ( v28 < 0 )
            {
              LODWORD(v35) = v28;
              TracePrintW(2u, "\\fdprov.cpp", 0x106u, L"Failed to build instance. (0x%x)", v35);
              CTraceFuncW<long>::~CTraceFuncW<long>(v42);
              goto LABEL_69;
            }
            v53 = ((__int64 (__fastcall *)(struct IFunctionInstanceCollection *, struct IFunctionInstance *))v39->lpVtbl->Add)(
                    v39,
                    v41);
            if ( v53 < 0 )
              goto LABEL_43;
            ATL::CComPtrBase<IFunctionInstance>::Release(&v41);
          }
          v29 = v39;
          v39 = 0;
          *a3 = v29;
        }
        goto LABEL_43;
      }
      CTraceFuncW<long>::~CTraceFuncW<long>(v42);
    }
    else
    {
      v53 = -2147024809;
      CTraceFuncW<long>::~CTraceFuncW<long>(v42);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CPassportException `RTTI Type Descriptor', &v51) )
    {
      v7 = *((unsigned int *)v51 + 2);
      v53 = v7;
      if ( (v7 & 0x80000000) == 0LL )
        v53 = -2147418113;
      __eh34_try_continuation(0, &CPassportException `RTTI Type Descriptor', &loc_1800080BF);
      goto LABEL_69;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v50) )
    {
      v7 = *(unsigned int *)v50;
      v53 = v7;
      if ( (v7 & 0x80000000) == 0LL )
        v53 = -2147418113;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800080D9);
      goto LABEL_69;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v53 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800080D7);
      goto LABEL_69;
    }
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v48) )
    {
      v53 = v48;
      if ( v48 >= 0 )
        v53 = -2147418113;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_1800080D5);
      goto LABEL_69;
    }
    if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v49) )
    {
      v7 = *((unsigned int *)v49 + 8);
      v53 = v7;
      if ( (v7 & 0x80000000) == 0LL )
        v53 = -2147418113;
      __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_1800080BF);
    }
  }
LABEL_69:
  if ( v40 )
    WLIDCDeleteContextEx(v7, &v40);
  if ( Block )
    free(Block);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v52 )
    CoRevertToSelf();
  v30 = v53;
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(&v39);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(&v41);
  ATL::CComPtrBase<IFunctionInstanceCollection>::~CComPtrBase<IFunctionInstanceCollection>(&v44);
  return v30;
}

```

## disassembly

```asm
0x180007b00  mov     rax, rsp
0x180007b03  mov     [rax+10h], rbx
0x180007b07  mov     [rax+18h], rsi
0x180007b0b  push    rdi
0x180007b0c  push    r12
0x180007b0e  push    r13
0x180007b10  push    r14
0x180007b12  push    r15
0x180007b14  sub     rsp, 0E0h
0x180007b1b  mov     r12, r8
0x180007b1e  mov     rsi, rdx
0x180007b21  mov     rdi, rcx
0x180007b24  xor     ebx, ebx
0x180007b26  mov     [rax+20h], ebx
0x180007b29  mov     [rax-88h], rbx
0x180007b30  mov     [rsp+108h+var_D8], ebx
0x180007b34  mov     [rsp+108h+pv], rbx
0x180007b39  mov     [rsp+108h+var_B8], rbx
0x180007b3e  mov     [rsp+108h+var_C8], rbx
0x180007b43  mov     [rsp+108h+arg_0], bl
0x180007b4a  mov     [rsp+108h+var_C0], rbx
0x180007b4f  mov     [rsp+108h+Block], rbx
0x180007b54  lea     rdx, aCwlidfdprovQue; "CWLIDFDProv::Query"
0x180007b5b  mov     [rsp+108h+var_B0], rdx
0x180007b60  lea     rax, [rax+20h]
0x180007b64  mov     [rsp+108h+var_A8], rax
0x180007b69  mov     [rsp+108h+var_A0], rbx
0x180007b6e  mov     [rsp+108h+var_98], rbx
0x180007b73  lea     r8d, [rbx+69h]; char *
0x180007b77  lea     r13, aFdprovCpp; "\\fdprov.cpp"
0x180007b7e  mov     rcx, r13; this
0x180007b81  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180007b86  nop
0x180007b87  cmp     [rdi+88h], bl
0x180007b8d  jnz     short loc_180007BAA
0x180007b8f  mov     [rsp+108h+arg_18], 8000FFFFh
0x180007b9a  lea     rcx, [rsp+108h+var_B0]
0x180007b9f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007ba4  nop
0x180007ba5  jmp     loc_1800080C1
0x180007baa  test    rsi, rsi
0x180007bad  jz      loc_1800080A7
0x180007bb3  test    r12, r12
0x180007bb6  jz      loc_1800080A7
0x180007bbc  mov     rax, [rsi]
0x180007bbf  lea     rdx, [rsp+108h+var_88]
0x180007bc7  mov     rcx, rsi
0x180007bca  mov     rax, [rax+28h]
0x180007bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd3  mov     [rsp+108h+arg_18], eax
0x180007bda  test    eax, eax
0x180007bdc  jns     short loc_180007C0C
0x180007bde  mov     dword ptr [rsp+108h+var_E8], eax
0x180007be2  lea     r9, aCouldnTRetriev; "Couldn't retrieve query contraints. (0x"...
0x180007be9  mov     r8d, 7Ch ; '|'; unsigned int
0x180007bef  mov     rdx, r13; char *
0x180007bf2  lea     ecx, [r8-7Ah]; unsigned __int8
0x180007bf6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007bfb  nop
0x180007bfc  lea     rcx, [rsp+108h+var_B0]
0x180007c01  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007c06  nop
0x180007c07  jmp     loc_1800080C1
0x180007c0c  mov     rcx, [rsp+108h+var_88]
0x180007c14  mov     rax, [rcx]
0x180007c17  lea     r8, [rsp+108h+pv]
0x180007c1c  lea     rdx, aOwnername; "OwnerName"
0x180007c23  mov     rax, [rax+20h]
0x180007c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c2c  mov     [rsp+108h+arg_18], eax
0x180007c33  test    eax, eax
0x180007c35  jns     short loc_180007C66
0x180007c37  mov     dword ptr [rsp+108h+var_E8], eax
0x180007c3b  lea     r9, aCouldnTRetriev_0; "Couldn't retrieve owner name from query"...
0x180007c42  mov     r8d, 86h; unsigned int
0x180007c48  mov     rdx, r13; char *
0x180007c4b  mov     ecx, 2; unsigned __int8
0x180007c50  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007c55  nop
0x180007c56  lea     rcx, [rsp+108h+var_B0]
0x180007c5b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007c60  nop
0x180007c61  jmp     loc_1800080C1
0x180007c66  call    cs:__imp_CoImpersonateClient
0x180007c6c  mov     [rsp+108h+arg_18], eax
0x180007c73  test    eax, eax
0x180007c75  js      short loc_180007C81
0x180007c77  mov     [rsp+108h+arg_0], 1
0x180007c7f  jmp     short loc_180007C93
0x180007c81  cmp     eax, 80010117h
0x180007c86  jnz     loc_18000809A
0x180007c8c  mov     [rsp+108h+arg_18], ebx
0x180007c93  cmp     [rdi+78h], bl
0x180007c96  jz      loc_180007E20
0x180007c9c  lea     rdx, [rdi+40h]
0x180007ca0  lea     rcx, [rsp+108h+var_78]
0x180007ca8  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x180007cad  nop
0x180007cae  lea     r9, aQueryIsAsync; "Query is Async."
0x180007cb5  mov     r8d, 9Eh; unsigned int
0x180007cbb  mov     rdx, r13; char *
0x180007cbe  mov     ecx, 5; unsigned __int8
0x180007cc3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007cc8  cmp     [rdi+80h], rbx
0x180007ccf  jnz     loc_180007D67
0x180007cd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007cdc  mov     ecx, 0D0h; unsigned __int64
0x180007ce1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007ce6  mov     [rsp+108h+var_80], rax
0x180007cee  test    rax, rax
0x180007cf1  jz      short loc_180007CFD
0x180007cf3  mov     rcx, rax; this
0x180007cf6  call    ??0CWLIDQueue@@QEAA@XZ; CWLIDQueue::CWLIDQueue(void)
0x180007cfb  jmp     short loc_180007D00
0x180007cfd  mov     rax, rbx
0x180007d00  mov     [rdi+80h], rax
0x180007d07  test    rax, rax
0x180007d0a  jnz     short loc_180007D35
0x180007d0c  mov     [rsp+108h+arg_18], 8007000Eh
0x180007d17  lea     rcx, [rsp+108h+var_78]
0x180007d1f  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180007d24  nop
0x180007d25  lea     rcx, [rsp+108h+var_B0]
0x180007d2a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007d2f  nop
0x180007d30  jmp     loc_1800080C1
0x180007d35  lea     rcx, [rax+58h]; this
0x180007d39  call    ?Initialize@CWLIDTimerQueue@@QEAAJXZ; CWLIDTimerQueue::Initialize(void)
0x180007d3e  mov     [rsp+108h+arg_18], eax
0x180007d45  test    eax, eax
0x180007d47  jns     short loc_180007D67
0x180007d49  lea     rcx, [rsp+108h+var_78]
0x180007d51  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180007d56  nop
0x180007d57  lea     rcx, [rsp+108h+var_B0]
0x180007d5c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007d61  nop
0x180007d62  jmp     loc_1800080C1
0x180007d67  mov     rsi, [rdi+80h]
0x180007d6e  mov     r14, [rdi+70h]
0x180007d72  mov     r15, [rdi+68h]
0x180007d76  mov     rdx, [rsp+108h+pv]
0x180007d7b  lea     rcx, [rsp+108h+var_80]
0x180007d83  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007d88  nop
0x180007d89  mov     [rsp+108h+var_E8], r14
0x180007d8e  mov     r9, r15
0x180007d91  mov     r8, rdi
0x180007d94  mov     rdx, rax
0x180007d97  mov     rcx, rsi
0x180007d9a  call    ?QueueItem@CWLIDQueue@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUIFunctionDiscoveryProvider@@PEAUIFunctionDiscoveryProviderFactory@@PEAUIFunctionDiscoveryNotification@@@Z; CWLIDQueue::QueueItem(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,IFunctionDiscoveryProvider *,IFunctionDiscoveryProviderFactory *,IFunctionDiscoveryNotification *)
0x180007d9f  mov     [rsp+108h+arg_18], eax
0x180007da6  mov     rcx, [rsp+108h+var_80]
0x180007dae  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007db2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007db7  mov     eax, [rsp+108h+arg_18]
0x180007dbe  test    eax, eax
0x180007dc0  jns     short loc_180007DFF
0x180007dc2  mov     dword ptr [rsp+108h+var_E8], eax
0x180007dc6  lea     r9, aFailedToQueueI; "Failed to queue Item. (0x%x)"
0x180007dcd  mov     r8d, 0B8h; unsigned int
0x180007dd3  mov     rdx, r13; char *
0x180007dd6  mov     ecx, 2; unsigned __int8
0x180007ddb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007de0  nop
0x180007de1  lea     rcx, [rsp+108h+var_78]
0x180007de9  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180007dee  nop
0x180007def  lea     rcx, [rsp+108h+var_B0]
0x180007df4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007df9  nop
0x180007dfa  jmp     loc_1800080C1
0x180007dff  mov     [r12], rbx
0x180007e03  mov     [rsp+108h+arg_18], 8000000Ah
0x180007e0e  lea     rcx, [rsp+108h+var_78]
0x180007e16  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180007e1b  jmp     loc_18000801A
0x180007e20  lea     r9, aQueryIsSync; "Query is Sync."
0x180007e27  mov     r8d, 0C6h; unsigned int
0x180007e2d  mov     rdx, r13; char *
0x180007e30  mov     esi, 5
0x180007e35  mov     ecx, esi; unsigned __int8
0x180007e37  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007e3c  lea     r9, [rsp+108h+var_C0]; void **
0x180007e41  call    ?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z; WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)
0x180007e46  mov     [rsp+108h+arg_18], eax
0x180007e4d  cmp     eax, 8004800Ch
0x180007e52  jnz     short loc_180007E74
0x180007e54  lea     r9, aWlidccreatecon_0; "WLIDCCreateContextEx returned PPCRL_NO_"...
0x180007e5b  mov     r8d, 0D6h; unsigned int
0x180007e61  mov     rdx, r13; char *
0x180007e64  mov     ecx, esi; unsigned __int8
0x180007e66  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007e6b  mov     [rsp+108h+arg_18], ebx
0x180007e72  jmp     short loc_180007EA9
0x180007e74  test    eax, eax
0x180007e76  js      loc_18000802A
0x180007e7c  lea     rax, [rsp+108h+Block]
0x180007e81  mov     [rsp+108h+var_E8], rax; struct __MIDL_liveidsvc_0003 **
0x180007e86  lea     r9, [rsp+108h+var_D8]; unsigned int *
0x180007e8b  mov     r8, [rsp+108h+pv]; unsigned __int16 *
0x180007e90  mov     rcx, [rsp+108h+var_C0]; void *
0x180007e95  call    ?WLIDCEnumerateUserAssociatedDevices@@YAJQEAXKPEAGPEAKPEAPEAU__MIDL_liveidsvc_0003@@@Z; WLIDCEnumerateUserAssociatedDevices(void * const,ulong,ushort *,ulong *,__MIDL_liveidsvc_0003 * *)
0x180007e9a  mov     [rsp+108h+arg_18], eax
0x180007ea1  test    eax, eax
0x180007ea3  js      loc_18000802A
0x180007ea9  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180007eae  test    al, al
0x180007eb0  jz      short loc_180007EBF
0x180007eb2  mov     cl, 1; this
0x180007eb4  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180007eb9  test    al, al
0x180007ebb  mov     cl, 1
0x180007ebd  jnz     short loc_180007EC1
0x180007ebf  mov     cl, bl
0x180007ec1  mov     rax, [rsp+108h+pv]
0x180007ec6  mov     [rsp+108h+var_70], rax
0x180007ece  mov     [rsp+108h+var_68], rbx
0x180007ed6  mov     [rsp+108h+var_60], cl
0x180007edd  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180007ee4  mov     [rsp+108h+var_78], rax
0x180007eec  lea     rcx, [rsp+108h+var_78]; this
0x180007ef4  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180007ef9  mov     [rsp+108h+var_E0], rax
0x180007efe  mov     eax, [rsp+108h+var_D8]
0x180007f02  mov     dword ptr [rsp+108h+var_E8], eax
0x180007f06  lea     r9, aEnumeratedUDev_0; "Enumerated %u devices for owner %ls"
0x180007f0d  mov     r8d, 0F1h; unsigned int
0x180007f13  mov     rdx, r13; char *
0x180007f16  mov     ecx, esi; unsigned __int8
0x180007f18  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007f1d  nop
0x180007f1e  lea     rcx, [rsp+108h+var_78]; this
0x180007f26  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180007f2b  mov     rcx, [rdi+68h]
0x180007f2f  mov     rax, [rcx]
0x180007f32  lea     rdx, [rsp+108h+var_C8]
0x180007f37  mov     rax, [rax+28h]
0x180007f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f40  mov     [rsp+108h+arg_18], eax
0x180007f47  test    eax, eax
0x180007f49  jns     short loc_180007F5B
0x180007f4b  lea     rcx, [rsp+108h+var_B0]
0x180007f50  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007f55  nop
0x180007f56  jmp     loc_1800080C1
0x180007f5b  mov     esi, ebx
0x180007f5d  cmp     esi, [rsp+108h+var_D8]
0x180007f61  jnb     loc_18000800C
0x180007f67  mov     eax, esi
0x180007f69  add     rax, rax
0x180007f6c  mov     rcx, [rsp+108h+Block]
0x180007f71  lea     rdx, [rsp+108h+var_B8]
0x180007f76  mov     [rsp+108h+var_E8], rdx; struct IFunctionInstance **
0x180007f7b  mov     r9, [rdi+68h]; struct IFunctionDiscoveryProviderFactory *
0x180007f7f  mov     r8, rdi; struct IFunctionDiscoveryProvider *
0x180007f82  mov     rdx, [rcx+rax*8+8]; unsigned __int16 *
0x180007f87  mov     rcx, [rcx+rax*8]; Source
0x180007f8b  call    ?BuildInstance@CWLIDFDProv@@SAJPEAG0PEAUIFunctionDiscoveryProvider@@PEAUIFunctionDiscoveryProviderFactory@@PEAPEAUIFunctionInstance@@@Z; CWLIDFDProv::BuildInstance(ushort *,ushort *,IFunctionDiscoveryProvider *,IFunctionDiscoveryProviderFactory *,IFunctionInstance * *)
0x180007f90  mov     [rsp+108h+arg_18], eax
0x180007f97  test    eax, eax
0x180007f99  jns     short loc_180007FCA
0x180007f9b  mov     dword ptr [rsp+108h+var_E8], eax
0x180007f9f  lea     r9, aFailedToBuildI; "Failed to build instance. (0x%x)"
0x180007fa6  mov     r8d, 106h; unsigned int
0x180007fac  mov     rdx, r13; char *
0x180007faf  mov     ecx, 2; unsigned __int8
0x180007fb4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007fb9  nop
0x180007fba  lea     rcx, [rsp+108h+var_B0]
0x180007fbf  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007fc4  nop
0x180007fc5  jmp     loc_1800080C1
0x180007fca  mov     rcx, [rsp+108h+var_C8]
0x180007fcf  mov     rax, [rcx]
0x180007fd2  mov     rdx, [rsp+108h+var_B8]
0x180007fd7  mov     rax, [rax+30h]
0x180007fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe0  mov     [rsp+108h+arg_18], eax
0x180007fe7  test    eax, eax
0x180007fe9  jns     short loc_180007FFB
0x180007feb  lea     rcx, [rsp+108h+var_B0]
0x180007ff0  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007ff5  nop
0x180007ff6  jmp     loc_1800080C1
0x180007ffb  lea     rcx, [rsp+108h+var_B8]
0x180008000  call    ?Release@?$CComPtrBase@UIFunctionInstance@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IFunctionInstance>::Release(void)
0x180008005  inc     esi
0x180008007  jmp     loc_180007F5D
0x18000800c  mov     rax, [rsp+108h+var_C8]
0x180008011  mov     [rsp+108h+var_C8], rbx
0x180008016  mov     [r12], rax
0x18000801a  lea     rcx, [rsp+108h+var_B0]
0x18000801f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180008024  nop
0x180008025  jmp     loc_1800080C1
0x18000802a  mov     dword ptr [rsp+108h+var_E8], eax
0x18000802e  lea     r9, aFailedToEnumer_0; "Failed to enumerate devices. (0x%x)"
0x180008035  mov     r8d, 0E5h; unsigned int
0x18000803b  mov     rdx, r13; char *
  ... truncated ...
```
