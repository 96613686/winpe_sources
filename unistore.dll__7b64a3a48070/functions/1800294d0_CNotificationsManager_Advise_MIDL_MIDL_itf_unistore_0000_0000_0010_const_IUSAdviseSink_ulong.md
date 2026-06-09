# CNotificationsManager::Advise(__MIDL___MIDL_itf_unistore_0000_0000_0010 const *,IUSAdviseSink *,ulong *)

- ea: `0x1800294d0`
- end: `0x1800298d2`
- name: `?Advise@CNotificationsManager@@UEAAJPEBU__MIDL___MIDL_itf_unistore_0000_0000_0010@@PEAUIUSAdviseSink@@PEAK@Z`
- size: `1026`
- prototype: `__int64 __fastcall(CNotificationsManager *__hidden this, const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *, struct IUSAdviseSink *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18001abf4`
- `0x1800230ac`
- `0x180027db0`
- `0x180027e58`
- `0x1800289f4`
- `0x180029494`
- `0x1800294d0`
- `0x180046dfc`
- `0x180054120`
- `0x1800662b8`
- `0x18006bed4`
- `0x18006c4e4`
- `0x180078a40`
- `0x1800c50aa`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029514`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029514`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029666`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002974b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029666`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002974b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029536`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029536`

## string_xrefs

- `0x180029796`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`
- `0x1800296e8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`
- `0x180029718`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`
- `0x1800297b2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`

## pseudocode

```c
__int64 __fastcall CNotificationsManager::Advise(
        CNotificationsManager *this,
        const struct __MIDL___MIDL_itf_unistore_0000_0000_0010 *a2,
        struct IUSAdviseSink *a3,
        unsigned int *a4)
{
  char *v6; // r14
  unsigned int CallerClientId; // eax
  RundownProtectionList *v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD CurrentProcessId; // r12d
  int *v13; // rdx
  int *v14; // r8
  char *v15; // rcx
  char *v16; // rbx
  char *v17; // rax
  char *v18; // rcx
  char *i; // rdi
  int v20; // edx
  int v21; // eax
  char *v23; // rdi
  __int64 v24; // r9
  unsigned int v25; // ebx
  int v26; // ecx
  _DWORD *v27; // rax
  unsigned __int64 v28; // rdi
  unsigned __int64 v29; // rbx
  _DWORD *v30; // r9
  unsigned __int64 v31; // rdi
  unsigned __int64 v32; // rbx
  _DWORD *v33; // rdx
  __int64 v34; // [rsp+30h] [rbp-50h] BYREF
  char *v35; // [rsp+38h] [rbp-48h] BYREF
  char v36[8]; // [rsp+40h] [rbp-40h] BYREF
  void *v37; // [rsp+48h] [rbp-38h] BYREF
  void *v38; // [rsp+50h] [rbp-30h]
  void *Block; // [rsp+60h] [rbp-20h] BYREF
  void *v40; // [rsp+68h] [rbp-18h]

  if ( this )
  {
    v6 = (char *)this + 8;
    if ( this != (CNotificationsManager *)-8LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  else
  {
    v6 = 0;
  }
  v35 = v6;
  CallerClientId = GetCallerClientId();
  LODWORD(v34) = 0;
  v9 = CallerClientId;
  if ( CallerClientId <= 0xFFFFFFFD )
  {
    if ( !(unsigned int)RundownProtectionList::GetProcessIdFromRundownProtectionId(
                          v8,
                          CallerClientId,
                          (unsigned int *)&v34) )
    {
      v25 = -2147483622;
      Log_UnistoreHREvent_0(
        2147483674LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
        1181);
      Log_UnistoreHREvent_0(
        2147483674LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\notificationsmanager.cpp",
        219);
      goto LABEL_35;
    }
    CurrentProcessId = v34;
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
  }
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &v37,
    v10,
    v11);
  if ( !*((_DWORD *)a2 + 5) )
    goto LABEL_7;
  v27 = v37;
  v28 = *((unsigned int *)a2 + 5);
  v29 = ((_BYTE *)v38 - (_BYTE *)v37) >> 2;
  if ( v28 > v29 )
  {
    if ( (unsigned __int8)utl::vector<enum __MIDL___MIDL_itf_unistore_0000_0002_0001,utl::allocator<enum __MIDL___MIDL_itf_unistore_0000_0002_0001>>::reserve(
                            &v37,
                            (unsigned int)v28) )
    {
      memset_0(v38, 0, 4 * ((unsigned int)v28 - v29));
      v27 = v37;
      goto LABEL_47;
    }
    v25 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\notificationsmanager.cpp",
      226);
    if ( v37 != (void *)-1LL )
      operator delete(v37);
LABEL_35:
    if ( v6 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
    return v25;
  }
LABEL_47:
  v13 = (int *)*((_QWORD *)a2 + 3);
  v38 = &v27[v28];
  v14 = &v13[*((unsigned int *)a2 + 5)];
  while ( v13 != v14 )
  {
    v26 = *v13++;
    *v27++ = v26;
  }
LABEL_7:
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &Block,
    v13,
    v14);
  if ( !*((_DWORD *)a2 + 8) )
    goto LABEL_8;
  v30 = Block;
  v31 = *((unsigned int *)a2 + 8);
  v32 = ((_BYTE *)v40 - (_BYTE *)Block) >> 2;
  if ( v31 > v32 )
  {
    if ( (unsigned __int8)utl::vector<enum __MIDL___MIDL_itf_unistore_0000_0002_0001,utl::allocator<enum __MIDL___MIDL_itf_unistore_0000_0002_0001>>::reserve(
                            &Block,
                            (unsigned int)v31) )
    {
      memset_0(v40, 0, 4 * ((unsigned int)v31 - v32));
      v30 = Block;
      goto LABEL_51;
    }
    v24 = 235;
LABEL_32:
    v25 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\notificationsmanager.cpp",
      v24);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&Block);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v37);
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v35);
    return v25;
  }
LABEL_51:
  v33 = (_DWORD *)*((_QWORD *)a2 + 5);
  v40 = &v30[v31];
  utl::copy<unsigned long *,utl::_ArrayIt<unsigned long>>(&v34, v33, &v33[*((unsigned int *)a2 + 8)], v30);
LABEL_8:
  v15 = (char *)this + 72;
  v16 = (char *)*((_QWORD *)this + 9);
  v17 = (char *)this + 72;
  while ( v16 != v15 )
  {
    if ( *((_DWORD *)v16 + 4) == v9 )
      goto LABEL_11;
    if ( !*((_DWORD *)v16 + 4) )
      v17 = v16;
    v16 = *(char **)v16;
  }
  if ( v17 == v15 )
  {
    v16 = *(char **)utl::list<CNotificationsManager::AdviseProcess,utl::allocator<CNotificationsManager::AdviseProcess>>::emplace<,0>(
                      v15,
                      &v34,
                      (char *)this + 72);
    if ( !v16 )
    {
      v24 = 264;
      goto LABEL_32;
    }
  }
  else
  {
    v23 = v17 + 32;
    *((_DWORD *)v17 + 7) = 0;
    v16 = v17;
    utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::_EraseTail(
      v17 + 32,
      *((_QWORD *)v17 + 4));
    *((_DWORD *)v23 + 6) = 0;
  }
LABEL_11:
  v18 = v16 + 64;
  for ( i = (char *)*((_QWORD *)v16 + 8); i != v18; i = *(char **)i )
  {
    if ( !*((_QWORD *)i + 12) )
      goto LABEL_16;
  }
  i = *(char **)utl::list<CNotificationsManager::AdviseInfo,utl::allocator<CNotificationsManager::AdviseInfo>>::emplace<,0>(
                  v18,
                  v36,
                  v16 + 64);
  if ( !i )
  {
    v24 = 289;
    goto LABEL_32;
  }
LABEL_16:
  v20 = *((_DWORD *)a2 + 1);
  *((_DWORD *)i + 4) = ++*((_DWORD *)this + 16);
  *((_DWORD *)i + 8) = CurrentProcessId;
  *((_DWORD *)i + 9) = *(_DWORD *)a2;
  v21 = v20 | 6;
  if ( (v20 & 6) != 0 )
    v21 = v20;
  *((_DWORD *)i + 10) = v21;
  *((_QWORD *)i + 3) = *((_QWORD *)a2 + 1);
  utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(i + 48, &v37);
  utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(i + 72, &Block);
  ATL::CComPtr<IDBFilter>::operator=(i + 96, a3);
  *((_DWORD *)v16 + 4) = v9;
  *((_DWORD *)v16 + 5) = CurrentProcessId;
  *a4 = *((_DWORD *)i + 4);
  if ( g_perfStatEnabled )
  {
    _InterlockedAdd(&dword_18010DA20, 1u);
    _InterlockedIncrement(&dword_18010DA18);
    while ( !dword_18010DA1C && _InterlockedCompareExchange(&dword_18010DA1C, 1, 0) )
      ;
  }
  if ( Block != (void *)-1LL )
    operator delete(Block);
  if ( v37 != (void *)-1LL )
    operator delete(v37);
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800294d0  mov     rax, rsp
0x1800294d3  mov     [rax+10h], rbx
0x1800294d7  mov     [rax+20h], r9
0x1800294db  mov     [rax+18h], r8
0x1800294df  mov     [rax+8], rcx
0x1800294e3  push    rbp
0x1800294e4  push    rsi
0x1800294e5  push    rdi
0x1800294e6  push    r12
0x1800294e8  push    r13
0x1800294ea  push    r14
0x1800294ec  push    r15
0x1800294ee  mov     rbp, rsp
0x1800294f1  sub     rsp, 80h
0x1800294f8  mov     r13, rdx
0x1800294fb  mov     r15, rcx
0x1800294fe  test    rcx, rcx
0x180029501  jz      loc_180029689
0x180029507  lea     r14, [rcx+8]
0x18002950b  test    r14, r14
0x18002950e  jz      short loc_18002951A
0x180029510  lea     rcx, [r14+8]; lpCriticalSection
0x180029514  call    cs:__imp_EnterCriticalSection
0x18002951a  mov     [rbp+var_48], r14
0x18002951e  call    ?GetCallerClientId@@YA?AUCallerId@@XZ; GetCallerClientId(void)
0x180029523  mov     dword ptr [rbp+var_50], 0
0x18002952a  mov     rsi, rax
0x18002952d  cmp     eax, 0FFFFFFFDh
0x180029530  jbe     loc_1800296BF
0x180029536  call    cs:__imp_GetCurrentProcessId
0x18002953c  mov     r12d, eax
0x18002953f  lea     rcx, [rbp+var_38]
0x180029543  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x180029548  cmp     dword ptr [r13+14h], 0
0x18002954d  ja      loc_1800297CA
0x180029553  lea     rcx, [rbp+Block]
0x180029557  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18002955c  cmp     dword ptr [r13+20h], 0
0x180029561  ja      loc_180029827
0x180029567  lea     rcx, [r15+48h]
0x18002956b  mov     rbx, [rcx]
0x18002956e  mov     rax, rcx
0x180029571  cmp     rbx, rcx
0x180029574  jz      loc_180029691
0x18002957a  cmp     [rbx+10h], esi
0x18002957d  jnz     loc_180029894
0x180029583  lea     rcx, [rbx+40h]
0x180029587  mov     rdi, [rcx]
0x18002958a  cmp     rdi, rcx
0x18002958d  jz      short loc_18002959B
0x18002958f  cmp     qword ptr [rdi+60h], 0
0x180029594  jz      short loc_1800295B3
0x180029596  mov     rdi, [rdi]
0x180029599  jmp     short loc_18002958A
0x18002959b  mov     r8, rcx
0x18002959e  lea     rdx, [rbp+var_40]
0x1800295a2  call    ??$emplace@$$V$0A@@?$list@VAdviseInfo@CNotificationsManager@@V?$allocator@VAdviseInfo@CNotificationsManager@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@VAdviseInfo@CNotificationsManager@@@utl@@VAdviseInfo@CNotificationsManager@@@1@V?$_DlistConstIt@U?$_DlistNode@VAdviseInfo@CNotificationsManager@@@utl@@VAdviseInfo@CNotificationsManager@@@1@@Z; utl::list<CNotificationsManager::AdviseInfo,utl::allocator<CNotificationsManager::AdviseInfo>>::emplace<,0>(utl::_DlistConstIt<utl::_DlistNode<CNotificationsManager::AdviseInfo>,CNotificationsManager::AdviseInfo>)
0x1800295a7  mov     rdi, [rax]
0x1800295aa  test    rdi, rdi
0x1800295ad  jz      loc_1800296DB
0x1800295b3  mov     edx, [r13+4]
0x1800295b7  lea     rcx, [rdi+30h]
0x1800295bb  mov     rax, [rbp+arg_0]
0x1800295bf  mov     r15d, 1
0x1800295c5  add     [rax+40h], r15d
0x1800295c9  mov     eax, [rax+40h]
0x1800295cc  mov     [rdi+10h], eax
0x1800295cf  mov     [rdi+20h], r12d
0x1800295d3  mov     eax, [r13+0]
0x1800295d7  mov     [rdi+24h], eax
0x1800295da  mov     eax, edx
0x1800295dc  or      eax, 6
0x1800295df  test    dl, 6
0x1800295e2  cmovnz  eax, edx
0x1800295e5  lea     rdx, [rbp+var_38]
0x1800295e9  mov     [rdi+28h], eax
0x1800295ec  mov     rax, [r13+8]
0x1800295f0  mov     [rdi+18h], rax
0x1800295f4  call    ?swap@?$vector@V?$CComPtr@VCNotificationEvent@@@ATL@@V?$allocator@V?$CComPtr@VCNotificationEvent@@@ATL@@@utl@@@utl@@QEAAXAEAV12@@Z; utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>> &)
0x1800295f9  lea     rdx, [rbp+Block]
0x1800295fd  lea     rcx, [rdi+48h]
0x180029601  call    ?swap@?$vector@V?$CComPtr@VCNotificationEvent@@@ATL@@V?$allocator@V?$CComPtr@VCNotificationEvent@@@ATL@@@utl@@@utl@@QEAAXAEAV12@@Z; utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>> &)
0x180029606  mov     rdx, [rbp+arg_10]
0x18002960a  lea     rcx, [rdi+60h]
0x18002960e  call    ??4?$CComPtr@UIDBFilter@@@ATL@@QEAAPEAUIDBFilter@@PEAU2@@Z; ATL::CComPtr<IDBFilter>::operator=(IDBFilter *)
0x180029613  mov     rcx, [rbp+arg_18]
0x180029617  mov     [rbx+10h], esi
0x18002961a  mov     [rbx+14h], r12d
0x18002961e  mov     eax, [rdi+10h]
0x180029621  mov     [rcx], eax
0x180029623  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180029629  test    eax, eax
0x18002962b  jnz     loc_1800298A4
0x180029631  mov     rcx, [rbp+Block]; Block
0x180029635  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029639  jz      short loc_180029647
0x18002963b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029642  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029647  mov     rcx, [rbp+var_38]; Block
0x18002964b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002964f  jz      short loc_18002965D
0x180029651  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180029658  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002965d  test    r14, r14
0x180029660  jz      short loc_18002966C
0x180029662  lea     rcx, [r14+8]; lpCriticalSection
0x180029666  call    cs:__imp_LeaveCriticalSection
0x18002966c  xor     eax, eax
0x18002966e  mov     rbx, [rsp+80h+arg_8]
0x180029676  add     rsp, 80h
0x18002967d  pop     r15
0x18002967f  pop     r14
0x180029681  pop     r13
0x180029683  pop     r12
0x180029685  pop     rdi
0x180029686  pop     rsi
0x180029687  pop     rbp
0x180029688  retn
0x180029689  xor     r14d, r14d
0x18002968c  jmp     loc_18002951A
0x180029691  cmp     rax, rcx
0x180029694  jz      loc_18002976E
0x18002969a  lea     rdi, [rax+20h]
0x18002969e  mov     dword ptr [rax+1Ch], 0
0x1800296a5  mov     rdx, [rdi]
0x1800296a8  mov     rcx, rdi
0x1800296ab  mov     rbx, rax
0x1800296ae  call    ?_EraseTail@?$vector@V?$CComPtr@VCNotificationEvent@@@ATL@@V?$allocator@V?$CComPtr@VCNotificationEvent@@@ATL@@@utl@@@utl@@AEAAXPEAV?$CComPtr@VCNotificationEvent@@@ATL@@@Z; utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::_EraseTail(ATL::CComPtr<CNotificationEvent> *)
0x1800296b3  mov     dword ptr [rdi+18h], 0
0x1800296ba  jmp     loc_180029583
0x1800296bf  lea     r8, [rbp+var_50]; unsigned int *
0x1800296c3  mov     edx, esi; unsigned int
0x1800296c5  call    ?GetProcessIdFromRundownProtectionId@RundownProtectionList@@QEAAHKPEAK@Z; RundownProtectionList::GetProcessIdFromRundownProtectionId(ulong,ulong *)
0x1800296ca  test    eax, eax
0x1800296cc  jz      loc_180029791
0x1800296d2  mov     r12d, dword ptr [rbp+var_50]
0x1800296d6  jmp     loc_18002953F
0x1800296db  mov     r9d, 121h
0x1800296e1  xor     edx, edx
0x1800296e3  mov     ebx, 8007000Eh
0x1800296e8  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800296ef  mov     ecx, ebx
0x1800296f1  call    Log_UnistoreHREvent_0
0x1800296f6  lea     rcx, [rbp+Block]
0x1800296fa  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x1800296ff  lea     rcx, [rbp+var_38]
0x180029703  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180029708  lea     rcx, [rbp+var_48]
0x18002970c  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180029711  jmp     short loc_180029751
0x180029713  mov     ebx, 8007000Eh
0x180029718  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002971f  mov     ecx, ebx
0x180029721  mov     r9d, 0E2h
0x180029727  call    Log_UnistoreHREvent_0
0x18002972c  mov     rcx, [rbp+var_38]; Block
0x180029730  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029734  jz      short loc_180029742
0x180029736  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002973d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029742  test    r14, r14
0x180029745  jz      short loc_180029751
0x180029747  lea     rcx, [r14+8]; lpCriticalSection
0x18002974b  call    cs:__imp_LeaveCriticalSection
0x180029751  mov     eax, ebx
0x180029753  jmp     loc_18002966E
0x180029758  mov     ecx, [rdx]
0x18002975a  add     rdx, 4
0x18002975e  mov     [rax], ecx
0x180029760  lea     rax, [rax+4]
0x180029764  cmp     rdx, r8
0x180029767  jnz     short loc_180029758
0x180029769  jmp     loc_180029553
0x18002976e  mov     r8, rcx
0x180029771  lea     rdx, [rbp+var_50]
0x180029775  call    ??$emplace@$$V$0A@@?$list@VAdviseProcess@CNotificationsManager@@V?$allocator@VAdviseProcess@CNotificationsManager@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@VAdviseProcess@CNotificationsManager@@@utl@@VAdviseProcess@CNotificationsManager@@@1@V?$_DlistConstIt@U?$_DlistNode@VAdviseProcess@CNotificationsManager@@@utl@@VAdviseProcess@CNotificationsManager@@@1@@Z; utl::list<CNotificationsManager::AdviseProcess,utl::allocator<CNotificationsManager::AdviseProcess>>::emplace<,0>(utl::_DlistConstIt<utl::_DlistNode<CNotificationsManager::AdviseProcess>,CNotificationsManager::AdviseProcess>)
0x18002977a  mov     rbx, [rax]
0x18002977d  test    rbx, rbx
0x180029780  jnz     loc_180029583
0x180029786  mov     r9d, 108h
0x18002978c  jmp     loc_1800296E1
0x180029791  mov     ebx, 8000001Ah
0x180029796  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002979d  mov     ecx, ebx
0x18002979f  mov     r9d, 49Dh
0x1800297a5  xor     edx, edx
0x1800297a7  call    Log_UnistoreHREvent_0
0x1800297ac  mov     r9d, 0DBh
0x1800297b2  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800297b9  mov     edx, 1
0x1800297be  mov     ecx, ebx
0x1800297c0  call    Log_UnistoreHREvent_0
0x1800297c5  jmp     loc_180029742
0x1800297ca  mov     rbx, [rbp+var_30]
0x1800297ce  mov     rax, [rbp+var_38]
0x1800297d2  mov     edi, [r13+14h]
0x1800297d6  sub     rbx, rax
0x1800297d9  sar     rbx, 2
0x1800297dd  cmp     rdi, rbx
0x1800297e0  jbe     short loc_18002980E
0x1800297e2  mov     edx, edi
0x1800297e4  lea     rcx, [rbp+var_38]
0x1800297e8  call    ?reserve@?$vector@W4__MIDL___MIDL_itf_unistore_0000_0002_0001@@V?$allocator@W4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<__MIDL___MIDL_itf_unistore_0000_0002_0001,utl::allocator<__MIDL___MIDL_itf_unistore_0000_0002_0001>>::reserve(unsigned __int64)
0x1800297ed  xor     edx, edx; Val
0x1800297ef  test    al, al
0x1800297f1  jz      loc_180029713
0x1800297f7  mov     rcx, [rbp+var_30]; void *
0x1800297fb  mov     r8d, edi
0x1800297fe  sub     r8, rbx
0x180029801  shl     r8, 2; Size
0x180029805  call    memset_0
0x18002980a  mov     rax, [rbp+var_38]
0x18002980e  mov     rdx, [r13+18h]
0x180029812  lea     rcx, [rax+rdi*4]
0x180029816  mov     [rbp+var_30], rcx
0x18002981a  mov     ecx, [r13+14h]
0x18002981e  lea     r8, [rdx+rcx*4]
0x180029822  jmp     loc_180029764
0x180029827  mov     rbx, [rbp+var_18]
0x18002982b  mov     r9, [rbp+Block]
0x18002982f  mov     edi, [r13+20h]
0x180029833  sub     rbx, r9
0x180029836  sar     rbx, 2
0x18002983a  cmp     rdi, rbx
0x18002983d  jbe     short loc_180029867
0x18002983f  mov     edx, edi
0x180029841  lea     rcx, [rbp+Block]
0x180029845  call    ?reserve@?$vector@W4__MIDL___MIDL_itf_unistore_0000_0002_0001@@V?$allocator@W4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<__MIDL___MIDL_itf_unistore_0000_0002_0001,utl::allocator<__MIDL___MIDL_itf_unistore_0000_0002_0001>>::reserve(unsigned __int64)
0x18002984a  xor     edx, edx; Val
0x18002984c  test    al, al
0x18002984e  jz      short loc_180029889
0x180029850  mov     rcx, [rbp+var_18]; void *
0x180029854  mov     r8d, edi
0x180029857  sub     r8, rbx
0x18002985a  shl     r8, 2; Size
0x18002985e  call    memset_0
0x180029863  mov     r9, [rbp+Block]
0x180029867  mov     rdx, [r13+28h]
0x18002986b  lea     rax, [r9+rdi*4]
0x18002986f  mov     [rbp+var_18], rax
0x180029873  lea     rcx, [rbp+var_50]
0x180029877  mov     eax, [r13+20h]
0x18002987b  lea     r8, [rdx+rax*4]
0x18002987f  call    ??$copy@PEAKV?$_ArrayIt@K@utl@@@utl@@YA?AV?$_ArrayIt@K@0@PEAK0V10@@Z; utl::copy<ulong *,utl::_ArrayIt<ulong>>(ulong *,ulong *,utl::_ArrayIt<ulong>)
0x180029884  jmp     loc_180029567
0x180029889  mov     r9d, 0EBh
0x18002988f  jmp     loc_1800296E3
0x180029894  cmp     dword ptr [rbx+10h], 0
0x180029898  cmovz   rax, rbx
0x18002989c  mov     rbx, [rbx]
0x18002989f  jmp     loc_180029571
0x1800298a4  lock add cs:dword_18010DA20, r15d
0x1800298ac  lock inc cs:dword_18010DA18
0x1800298b3  mov     eax, cs:dword_18010DA1C
0x1800298b9  cmp     eax, r15d
0x1800298bc  jnb     loc_180029631
0x1800298c2  lock cmpxchg cs:dword_18010DA1C, r15d
0x1800298cb  jnz     short loc_1800298B3
0x1800298cd  jmp     loc_180029631
```
