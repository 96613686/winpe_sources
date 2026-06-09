# smapi::GetReportCallback(Wsp::Health::IReport const &,int,void *)

- ea: `0x1800545b0`
- end: `0x180054ac2`
- name: `?GetReportCallback@smapi@@YAXAEBVIReport@Health@Wsp@@HPEAX@Z`
- size: `1298`
- prototype: `void(smapi *__hidden this, const struct Wsp::Health::IReport *, int, void *)`
- caller_count: `0`
- callee_count: `22`
- tags: ``

## callees

- `0x180002ae0`
- `0x18000b8e4`
- `0x18000c4c4`
- `0x18000c9f0`
- `0x18000ca58`
- `0x18000d6dc`
- `0x180017688`
- `0x18001a470`
- `0x18001a9b4`
- `0x18001e6c8`
- `0x180033fd4`
- `0x180034038`
- `0x180036644`
- `0x1800537a8`
- `0x18005397c`
- `0x1800545b0`
- `0x180070eb0`
- `0x180070f78`
- `0x180071040`
- `0x180073ae4`
- `0x180073b60`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180054669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800546d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180054669`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800546d8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180054684`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800546f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180054684`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800546f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
void __fastcall smapi::GetReportCallback(smapi *this, const struct Wsp::Health::IReport *a2, void *a3, void *a4)
{
  int v5; // esi
  struct cxl::NonReentrantRWLock **Instance; // rax
  _DWORD *v8; // rdi
  struct _TP_WORK *ThreadpoolWork; // rbx
  unsigned int v10; // eax
  unsigned int v11; // eax
  struct _TP_WORK *v12; // rbx
  __int64 v13; // r12
  __int64 v14; // rbx
  void (__fastcall *v15)(__int64, __int64); // rsi
  _QWORD *v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  unsigned int i; // r15d
  int v20; // eax
  __int64 v21; // rsi
  void (__fastcall *v22)(__int64, _QWORD *); // r14
  __int64 v23; // rsi
  void (__fastcall *v24)(__int64, _QWORD *); // r14
  __int64 v25; // [rsp+30h] [rbp-108h] BYREF
  int v26; // [rsp+38h] [rbp-100h]
  __int64 v27; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-F0h]
  __int64 v29; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-E0h] BYREF
  std::_Ref_count_base *v31; // [rsp+60h] [rbp-D8h]
  void *v32; // [rsp+68h] [rbp-D0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-C8h]
  __int64 v34; // [rsp+80h] [rbp-B8h] BYREF
  std::_Ref_count_base *v35; // [rsp+88h] [rbp-B0h]
  _BYTE v36[8]; // [rsp+90h] [rbp-A8h] BYREF
  std::_Ref_count_base *v37; // [rsp+98h] [rbp-A0h]
  _QWORD v38[4]; // [rsp+A0h] [rbp-98h] BYREF
  _QWORD v39[4]; // [rsp+C0h] [rbp-78h] BYREF
  _BYTE v40[8]; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-50h]
  __int64 v42; // [rsp+F0h] [rbp-48h]
  unsigned __int16 v43; // [rsp+F8h] [rbp-40h]

  v5 = (int)a2;
  v26 = 0;
  if ( a3 )
  {
    Instance = (struct cxl::NonReentrantRWLock **)Wsp::Facade::ReportSubscriptionManager::GetInstance(v36);
    Wsp::Facade::ReportSubscriptionManager::GetElement(*Instance);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    v8 = (_DWORD *)v30;
    if ( v30 )
    {
      cxl::AcquireWriteLock::AcquireWriteLock(
        (cxl::AcquireWriteLock *)v36,
        (struct cxl::NonReentrantRWLock *)(v30 + 32));
      if ( v5 )
      {
        *(_DWORD *)(v30 + 244) = -2147023436;
        cxl::ManualResetEvent::Set((cxl::ManualResetEvent *)(v8 + 12));
        ThreadpoolWork = CreateThreadpoolWork(smapi::CleanupReportSubscriptionCallback, a3, 0);
        if ( ThreadpoolWork )
        {
          std::shared_ptr<Wsp::Facade::GetReportContext>::reset(&v30);
          SubmitThreadpoolWork(ThreadpoolWork);
        }
        cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v36);
        if ( v31 )
          std::_Ref_count_base::_Decref(v31);
      }
      else
      {
        v10 = *(_DWORD *)(v30 + 232);
        if ( v10 < *(_DWORD *)(v30 + 236) )
        {
          v13 = *(_QWORD *)(v30 + 24);
          v27 = 0;
          v39[0] = v13;
          v39[1] = 0;
          smapi::SchemaFactory::Create(v39, &v27);
          v14 = v27;
          v27 = 0;
          v25 = 0;
          v29 = v14;
          std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(&v25);
          (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v14 + 40LL))(v14, v8 + 42);
          v15 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 48LL);
          v16 = (_QWORD *)Wsp::MiSpaceAdapter::GetInstance(&v34);
          v17 = Wsp::MiSpaceAdapter::PackObjectId(*v16, (unsigned int)v40, (int)v8 + 136, 1, 2);
          v15(v14, v17);
          std::wstring::_Tidy_deallocate(v40);
          if ( v35 )
            std::_Ref_count_base::_Decref(v35);
          std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(&v32);
          v18 = (*(__int64 (__fastcall **)(smapi *))(*(_QWORD *)this + 16LL))(this);
          v28 = v18;
          for ( i = 0; i < v18; ++i )
          {
            (*(void (__fastcall **)(smapi *, _BYTE *, _QWORD))(*(_QWORD *)this + 32LL))(this, v40, i);
            v20 = (*(__int64 (__fastcall **)(smapi *, _QWORD))(*(_QWORD *)this + 24LL))(this, i);
            if ( v20 )
            {
              if ( v20 == 1 )
              {
                v25 = 0;
                v38[0] = v13;
                v38[1] = 0;
                smapi::SchemaFactory::Create(v38, &v25);
                v21 = v25;
                v22 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v25 + 40LL);
                std::wstring::wstring(v39, v42);
                v22(v21, v39);
                std::wstring::_Tidy_deallocate(v39);
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 56LL))(v21, v41);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 48LL))(v21, v43);
                std::vector<std::unique_ptr<smapi::IHealthRecordSchema>>::emplace_back<std::unique_ptr<smapi::IHealthRecordUInt64Schema>>(
                  (__int64 *)&v32,
                  &v25);
                std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(&v25);
              }
            }
            else
            {
              v25 = 0;
              v34 = v13;
              v35 = 0;
              smapi::SchemaFactory::Create(&v34, &v25);
              v23 = v25;
              v24 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v25 + 40LL);
              std::wstring::wstring(v39, v42);
              v24(v23, v39);
              std::wstring::_Tidy_deallocate(v39);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 56LL))(v23);
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 48LL))(v23, v43);
              std::vector<std::unique_ptr<smapi::IHealthRecordSchema>>::emplace_back<std::unique_ptr<smapi::IHealthRecordUInt64Schema>>(
                (__int64 *)&v32,
                &v25);
              std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(&v25);
            }
            v18 = v28;
          }
          (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v14 + 56LL))(v14, &v32);
          (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v14 + 16LL))(v14, v8 + 50);
          if ( ++v8[58] >= v8[59] )
            cxl::ManualResetEvent::Set((cxl::ManualResetEvent *)(v8 + 12));
          if ( v32 )
          {
            std::_Destroy_range<std::allocator<std::unique_ptr<smapi::IHealthRecordSchema>>>((__int64)v32, v33);
            std::_Deallocate<16>(v32, (*((_QWORD *)&v33 + 1) - (_QWORD)v32) & 0xFFFFFFFFFFFFFFF8uLL);
            v32 = 0;
            v33 = 0;
          }
          std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(&v29);
          std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(&v27);
          cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v36);
          if ( v31 )
            std::_Ref_count_base::_Decref(v31);
        }
        else
        {
          v11 = v10 + 1;
          *(_DWORD *)(v30 + 232) = v11;
          if ( v11 == v8[60] )
          {
            v12 = CreateThreadpoolWork(smapi::CleanupReportSubscriptionCallback, a3, 0);
            if ( v12 )
            {
              std::shared_ptr<Wsp::Facade::GetReportContext>::reset(&v30);
              SubmitThreadpoolWork(v12);
            }
          }
          cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(v36);
          if ( v31 )
            std::_Ref_count_base::_Decref(v31);
        }
      }
    }
    else if ( v31 )
    {
      std::_Ref_count_base::_Decref(v31);
    }
  }
}

```

## disassembly

```asm
0x1800545b0  mov     [rsp+arg_8], rbx
0x1800545b5  mov     [rsp+arg_18], rsi
0x1800545ba  push    rdi
0x1800545bb  push    r12
0x1800545bd  push    r13
0x1800545bf  push    r14
0x1800545c1  push    r15
0x1800545c3  sub     rsp, 110h
0x1800545ca  mov     rax, cs:__security_cookie
0x1800545d1  xor     rax, rsp
0x1800545d4  mov     [rsp+138h+var_38], rax
0x1800545dc  mov     rbx, r8
0x1800545df  mov     esi, edx
0x1800545e1  mov     r13, rcx
0x1800545e4  xor     r14d, r14d
0x1800545e7  mov     [rsp+138h+var_100], r14d
0x1800545ec  test    rbx, rbx
0x1800545ef  jz      loc_180054A94
0x1800545f5  lea     rcx, [rsp+138h+var_A8]
0x1800545fd  call    ?GetInstance@ReportSubscriptionManager@Facade@Wsp@@SA?AV?$shared_ptr@VReportSubscriptionManager@Facade@Wsp@@@std@@XZ; Wsp::Facade::ReportSubscriptionManager::GetInstance(void)
0x180054602  mov     r8d, ebx
0x180054605  lea     rdx, [rsp+138h+var_E0]
0x18005460a  mov     rcx, [rax]; struct cxl::NonReentrantRWLock *
0x18005460d  call    ?GetElement@ReportSubscriptionManager@Facade@Wsp@@QEAA?AV?$shared_ptr@VGetReportContext@Facade@Wsp@@@std@@I@Z; Wsp::Facade::ReportSubscriptionManager::GetElement(uint)
0x180054612  nop
0x180054613  mov     rcx, [rsp+138h+var_A0]; this
0x18005461b  test    rcx, rcx
0x18005461e  jz      short loc_180054625
0x180054620  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054625  mov     rdi, [rsp+138h+var_E0]
0x18005462a  test    rdi, rdi
0x18005462d  jz      loc_180054A7F
0x180054633  lea     rdx, [rdi+20h]; struct cxl::NonReentrantRWLock *
0x180054637  lea     rcx, [rsp+138h+var_A8]; this
0x18005463f  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x180054644  nop
0x180054645  test    esi, esi
0x180054647  jz      short loc_1800546AD
0x180054649  mov     dword ptr [rdi+0F4h], 800705B4h
0x180054653  lea     rcx, [rdi+30h]; this
0x180054657  call    ?Set@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Set(void)
0x18005465c  xor     r8d, r8d; pcbe
0x18005465f  mov     rdx, rbx; pv
0x180054662  lea     rcx, ?CleanupReportSubscriptionCallback@smapi@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180054669  call    cs:__imp_CreateThreadpoolWork
0x18005466f  mov     rbx, rax
0x180054672  test    rax, rax
0x180054675  jz      short loc_18005468B
0x180054677  lea     rcx, [rsp+138h+var_E0]
0x18005467c  call    ?reset@?$shared_ptr@VGetReportContext@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::GetReportContext>::reset(void)
0x180054681  mov     rcx, rbx; pwk
0x180054684  call    cs:__imp_SubmitThreadpoolWork
0x18005468a  nop
0x18005468b  lea     rcx, [rsp+138h+var_A8]
0x180054693  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180054698  nop
0x180054699  mov     rcx, [rsp+138h+var_D8]; this
0x18005469e  test    rcx, rcx
0x1800546a1  jz      short loc_1800546A8
0x1800546a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800546a8  jmp     loc_180054A94
0x1800546ad  mov     eax, [rdi+0E8h]
0x1800546b3  cmp     eax, [rdi+0ECh]
0x1800546b9  jb      short loc_18005471C
0x1800546bb  inc     eax
0x1800546bd  mov     [rdi+0E8h], eax
0x1800546c3  cmp     eax, [rdi+0F0h]
0x1800546c9  jnz     short loc_1800546FA
0x1800546cb  xor     r8d, r8d; pcbe
0x1800546ce  mov     rdx, rbx; pv
0x1800546d1  lea     rcx, ?CleanupReportSubscriptionCallback@smapi@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800546d8  call    cs:__imp_CreateThreadpoolWork
0x1800546de  mov     rbx, rax
0x1800546e1  test    rax, rax
0x1800546e4  jz      short loc_1800546FA
0x1800546e6  lea     rcx, [rsp+138h+var_E0]
0x1800546eb  call    ?reset@?$shared_ptr@VGetReportContext@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::GetReportContext>::reset(void)
0x1800546f0  mov     rcx, rbx; pwk
0x1800546f3  call    cs:__imp_SubmitThreadpoolWork
0x1800546f9  nop
0x1800546fa  lea     rcx, [rsp+138h+var_A8]
0x180054702  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180054707  nop
0x180054708  mov     rcx, [rsp+138h+var_D8]; this
0x18005470d  test    rcx, rcx
0x180054710  jz      short loc_180054717
0x180054712  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054717  jmp     loc_180054A94
0x18005471c  mov     r12, [rdi+18h]
0x180054720  mov     [rsp+138h+var_F8], r14
0x180054725  mov     [rsp+138h+var_78], r12
0x18005472d  mov     [rsp+138h+var_70], r14
0x180054735  lea     rdx, [rsp+138h+var_F8]
0x18005473a  lea     rcx, [rsp+138h+var_78]
0x180054742  call    ?Create@SchemaFactory@smapi@@SAXVMiContext@mi@@AEAV?$unique_ptr@UIStorageHealthReportSchema@smapi@@U?$default_delete@UIStorageHealthReportSchema@smapi@@@std@@@std@@@Z; smapi::SchemaFactory::Create(mi::MiContext,std::unique_ptr<smapi::IStorageHealthReportSchema> &)
0x180054747  mov     rbx, [rsp+138h+var_F8]
0x18005474c  mov     [rsp+138h+var_F8], r14
0x180054751  mov     [rsp+138h+var_108], r14
0x180054756  mov     [rsp+138h+var_E8], rbx
0x18005475b  lea     rcx, [rsp+138h+var_108]
0x180054760  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x180054765  nop
0x180054766  mov     rax, [rbx]
0x180054769  lea     rdx, [rdi+0A8h]
0x180054770  mov     rcx, rbx
0x180054773  mov     rax, [rax+28h]
0x180054777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005477c  mov     rax, [rbx]
0x18005477f  mov     rsi, [rax+30h]
0x180054783  lea     rcx, [rsp+138h+var_B8]
0x18005478b  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x180054790  nop
0x180054791  lea     r8, [rdi+88h]
0x180054798  mov     [rsp+138h+var_118], 2
0x1800547a0  mov     r9d, 1
0x1800547a6  lea     rdx, [rsp+138h+var_58]
0x1800547ae  mov     rcx, [rax]
0x1800547b1  call    ?PackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::PackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE)
0x1800547b6  nop
0x1800547b7  mov     rdx, rax
0x1800547ba  mov     rcx, rbx
0x1800547bd  mov     rax, rsi
0x1800547c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547c5  nop
0x1800547c6  lea     rcx, [rsp+138h+var_58]
0x1800547ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800547d3  nop
0x1800547d4  mov     rcx, [rsp+138h+var_B0]; this
0x1800547dc  test    rcx, rcx
0x1800547df  jz      short loc_1800547E6
0x1800547e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800547e6  lea     rcx, [rsp+138h+var_D0]
0x1800547eb  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x1800547f0  nop
0x1800547f1  mov     rax, [r13+0]
0x1800547f5  mov     rcx, r13
0x1800547f8  mov     rax, [rax+10h]
0x1800547fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054801  mov     [rsp+138h+var_F0], eax
0x180054805  mov     r15d, r14d
0x180054808  cmp     r15d, eax
0x18005480b  jnb     loc_1800549C9
0x180054811  mov     rax, [r13+0]
0x180054815  mov     r8d, r15d
0x180054818  lea     rdx, [rsp+138h+var_58]
0x180054820  mov     rcx, r13
0x180054823  mov     rax, [rax+20h]
0x180054827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005482c  mov     rax, [r13+0]
0x180054830  mov     edx, r15d
0x180054833  mov     rcx, r13
0x180054836  mov     rax, [rax+18h]
0x18005483a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005483f  test    eax, eax
0x180054841  jz      loc_180054907
0x180054847  cmp     eax, 1
0x18005484a  jnz     loc_1800549BD
0x180054850  mov     [rsp+138h+var_108], r14
0x180054855  mov     [rsp+138h+var_98], r12
0x18005485d  mov     [rsp+138h+var_90], r14
0x180054865  lea     rdx, [rsp+138h+var_108]
0x18005486a  lea     rcx, [rsp+138h+var_98]
0x180054872  call    ?Create@SchemaFactory@smapi@@SAXVMiContext@mi@@AEAV?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@std@@@Z; smapi::SchemaFactory::Create(mi::MiContext,std::unique_ptr<smapi::IHealthRecordUInt64Schema> &)
0x180054877  mov     rsi, [rsp+138h+var_108]
0x18005487c  mov     rax, [rsi]
0x18005487f  mov     r14, [rax+28h]
0x180054883  mov     rdx, [rsp+138h+var_48]
0x18005488b  lea     rcx, [rsp+138h+var_78]
0x180054893  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054898  nop
0x180054899  lea     rdx, [rsp+138h+var_78]
0x1800548a1  mov     rcx, rsi
0x1800548a4  mov     rax, r14
0x1800548a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548ac  nop
0x1800548ad  lea     rcx, [rsp+138h+var_78]
0x1800548b5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800548ba  mov     rax, [rsi]
0x1800548bd  mov     rdx, [rsp+138h+var_50]
0x1800548c5  mov     rcx, rsi
0x1800548c8  mov     rax, [rax+38h]
0x1800548cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548d1  mov     rax, [rsi]
0x1800548d4  movzx   edx, [rsp+138h+var_40]
0x1800548dc  mov     rcx, rsi
0x1800548df  mov     rax, [rax+30h]
0x1800548e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548e8  lea     rdx, [rsp+138h+var_108]
0x1800548ed  lea     rcx, [rsp+138h+var_D0]
0x1800548f2  call    ??$emplace_back@V?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@std@@@?$vector@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@V?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@1@$$QEAV?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@1@@Z; std::vector<std::unique_ptr<smapi::IHealthRecordSchema>>::emplace_back<std::unique_ptr<smapi::IHealthRecordUInt64Schema>>(std::unique_ptr<smapi::IHealthRecordUInt64Schema> &&)
0x1800548f7  nop
0x1800548f8  lea     rcx, [rsp+138h+var_108]
0x1800548fd  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x180054902  jmp     loc_1800549BA
0x180054907  mov     [rsp+138h+var_108], r14
0x18005490c  mov     [rsp+138h+var_B8], r12
0x180054914  mov     [rsp+138h+var_B0], r14
0x18005491c  lea     rdx, [rsp+138h+var_108]
0x180054921  lea     rcx, [rsp+138h+var_B8]
0x180054929  call    ?Create@SchemaFactory@smapi@@SAXVMiContext@mi@@AEAV?$unique_ptr@UIHealthRecordReal64Schema@smapi@@U?$default_delete@UIHealthRecordReal64Schema@smapi@@@std@@@std@@@Z; smapi::SchemaFactory::Create(mi::MiContext,std::unique_ptr<smapi::IHealthRecordReal64Schema> &)
0x18005492e  mov     rsi, [rsp+138h+var_108]
0x180054933  mov     rax, [rsi]
0x180054936  mov     r14, [rax+28h]
0x18005493a  mov     rdx, [rsp+138h+var_48]
0x180054942  lea     rcx, [rsp+138h+var_78]
0x18005494a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005494f  nop
0x180054950  lea     rdx, [rsp+138h+var_78]
0x180054958  mov     rcx, rsi
0x18005495b  mov     rax, r14
0x18005495e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054963  nop
0x180054964  lea     rcx, [rsp+138h+var_78]
0x18005496c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054971  mov     rax, [rsi]
0x180054974  movsd   xmm1, [rsp+138h+var_50]
0x18005497d  mov     rcx, rsi
0x180054980  mov     rax, [rax+38h]
0x180054984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054989  mov     rax, [rsi]
0x18005498c  movzx   edx, [rsp+138h+var_40]
0x180054994  mov     rcx, rsi
0x180054997  mov     rax, [rax+30h]
0x18005499b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549a0  lea     rdx, [rsp+138h+var_108]
0x1800549a5  lea     rcx, [rsp+138h+var_D0]
0x1800549aa  call    ??$emplace_back@V?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@std@@@?$vector@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@V?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@1@$$QEAV?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@1@@Z; std::vector<std::unique_ptr<smapi::IHealthRecordSchema>>::emplace_back<std::unique_ptr<smapi::IHealthRecordUInt64Schema>>(std::unique_ptr<smapi::IHealthRecordUInt64Schema> &&)
0x1800549af  nop
0x1800549b0  lea     rcx, [rsp+138h+var_108]
0x1800549b5  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x1800549ba  xor     r14d, r14d
0x1800549bd  inc     r15d
0x1800549c0  mov     eax, [rsp+138h+var_F0]
0x1800549c4  jmp     loc_180054808
0x1800549c9  mov     rax, [rbx]
0x1800549cc  lea     rdx, [rsp+138h+var_D0]
0x1800549d1  mov     rcx, rbx
0x1800549d4  mov     rax, [rax+38h]
0x1800549d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549dd  mov     rax, [rbx]
0x1800549e0  lea     rdx, [rdi+0C8h]
0x1800549e7  mov     rcx, rbx
0x1800549ea  mov     rax, [rax+10h]
0x1800549ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549f3  inc     dword ptr [rdi+0E8h]
0x1800549f9  mov     eax, [rdi+0E8h]
0x1800549ff  cmp     eax, [rdi+0ECh]
0x180054a05  jb      short loc_180054A11
0x180054a07  lea     rcx, [rdi+30h]; this
0x180054a0b  call    ?Set@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Set(void)
0x180054a10  nop
0x180054a11  mov     rcx, [rsp+138h+var_D0]
0x180054a16  test    rcx, rcx
0x180054a19  jz      short loc_180054A49
0x180054a1b  mov     rdx, qword ptr [rsp+138h+var_C8]
0x180054a20  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<smapi::IHealthRecordSchema>>>(std::unique_ptr<smapi::IHealthRecordSchema> *,std::unique_ptr<smapi::IHealthRecordSchema> * const,std::allocator<std::unique_ptr<smapi::IHealthRecordSchema>> &)
0x180054a25  mov     rcx, [rsp+138h+var_D0]
0x180054a2a  mov     rdx, qword ptr [rsp+138h+var_C8+8]
0x180054a2f  sub     rdx, rcx
0x180054a32  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180054a36  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180054a3b  mov     [rsp+138h+var_D0], r14
0x180054a40  xorps   xmm0, xmm0
0x180054a43  movdqu  [rsp+138h+var_C8], xmm0
0x180054a49  lea     rcx, [rsp+138h+var_E8]
0x180054a4e  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x180054a53  nop
0x180054a54  lea     rcx, [rsp+138h+var_F8]
0x180054a59  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x180054a5e  nop
0x180054a5f  lea     rcx, [rsp+138h+var_A8]
0x180054a67  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180054a6c  nop
0x180054a6d  mov     rcx, [rsp+138h+var_D8]; this
0x180054a72  test    rcx, rcx
0x180054a75  jz      short loc_180054A7D
0x180054a77  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054a7c  nop
0x180054a7d  jmp     short loc_180054A94
0x180054a7f  mov     rcx, [rsp+138h+var_D8]; this
0x180054a84  test    rcx, rcx
0x180054a87  jz      short loc_180054A8E
0x180054a89  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054a8e  jmp     short loc_180054A94
0x180054a90  jmp     short loc_180054A94
0x180054a92  jmp     short $+2
0x180054a94  mov     rcx, [rsp+138h+var_38]
0x180054a9c  xor     rcx, rsp; StackCookie
0x180054a9f  call    __security_check_cookie
0x180054aa4  lea     r11, [rsp+138h+var_28]
0x180054aac  mov     rbx, [r11+38h]
0x180054ab0  mov     rsi, [r11+48h]
0x180054ab4  mov     rsp, r11
0x180054ab7  pop     r15
0x180054ab9  pop     r14
0x180054abb  pop     r13
0x180054abd  pop     r12
0x180054abf  pop     rdi
0x180054ac0  retn
```
