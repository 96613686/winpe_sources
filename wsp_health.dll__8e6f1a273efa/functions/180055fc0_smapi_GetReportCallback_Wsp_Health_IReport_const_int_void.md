# smapi::GetReportCallback(Wsp::Health::IReport const &,int,void *)

- ea: `0x180055fc0`
- end: `0x1800564ea`
- name: `?GetReportCallback@smapi@@YAXAEBVIReport@Health@Wsp@@HPEAX@Z`
- size: `1322`
- prototype: `void(smapi *__hidden this, const struct Wsp::Health::IReport *, int, void *)`
- caller_count: `0`
- callee_count: `22`
- tags: ``

## callees

- `0x180002b50`
- `0x18000bc64`
- `0x18000c85c`
- `0x18000cd9c`
- `0x18000ce04`
- `0x18000daf8`
- `0x180017fcc`
- `0x18001aef0`
- `0x18001b484`
- `0x18001f2b0`
- `0x180035104`
- `0x180035168`
- `0x180037760`
- `0x1800551a8`
- `0x180055388`
- `0x180055fc0`
- `0x1800728a8`
- `0x180072974`
- `0x180072acc`
- `0x180075904`
- `0x180075980`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180056079`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800560f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180056079`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800560f4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005609a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180056115`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005609a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180056115`

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
  __int64 v32; // [rsp+68h] [rbp-D0h] BYREF
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
                  &v32,
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
                &v32,
                &v25);
              std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(&v25);
            }
            v18 = v28;
          }
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 56LL))(v14, &v32);
          (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v14 + 16LL))(v14, v8 + 50);
          if ( ++v8[58] >= v8[59] )
            cxl::ManualResetEvent::Set((cxl::ManualResetEvent *)(v8 + 12));
          if ( v32 )
          {
            std::_Destroy_range<std::allocator<std::unique_ptr<smapi::IHealthRecordSchema>>>(v32, v33);
            std::_Deallocate<16>(v32, (*((_QWORD *)&v33 + 1) - v32) & 0xFFFFFFFFFFFFFFF8uLL);
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
0x180055fc0  mov     [rsp+arg_8], rbx
0x180055fc5  mov     [rsp+arg_18], rsi
0x180055fca  push    rdi
0x180055fcb  push    r12
0x180055fcd  push    r13
0x180055fcf  push    r14
0x180055fd1  push    r15
0x180055fd3  sub     rsp, 110h
0x180055fda  mov     rax, cs:__security_cookie
0x180055fe1  xor     rax, rsp
0x180055fe4  mov     [rsp+138h+var_38], rax
0x180055fec  mov     rbx, r8
0x180055fef  mov     esi, edx
0x180055ff1  mov     r13, rcx
0x180055ff4  xor     r14d, r14d
0x180055ff7  mov     [rsp+138h+var_100], r14d
0x180055ffc  test    rbx, rbx
0x180055fff  jz      loc_1800564BC
0x180056005  lea     rcx, [rsp+138h+var_A8]
0x18005600d  call    ?GetInstance@ReportSubscriptionManager@Facade@Wsp@@SA?AV?$shared_ptr@VReportSubscriptionManager@Facade@Wsp@@@std@@XZ; Wsp::Facade::ReportSubscriptionManager::GetInstance(void)
0x180056012  mov     r8d, ebx
0x180056015  lea     rdx, [rsp+138h+var_E0]
0x18005601a  mov     rcx, [rax]; struct cxl::NonReentrantRWLock *
0x18005601d  call    ?GetElement@ReportSubscriptionManager@Facade@Wsp@@QEAA?AV?$shared_ptr@VGetReportContext@Facade@Wsp@@@std@@I@Z; Wsp::Facade::ReportSubscriptionManager::GetElement(uint)
0x180056022  nop
0x180056023  mov     rcx, [rsp+138h+var_A0]; this
0x18005602b  test    rcx, rcx
0x18005602e  jz      short loc_180056035
0x180056030  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056035  mov     rdi, [rsp+138h+var_E0]
0x18005603a  test    rdi, rdi
0x18005603d  jz      loc_1800564A7
0x180056043  lea     rdx, [rdi+20h]; struct cxl::NonReentrantRWLock *
0x180056047  lea     rcx, [rsp+138h+var_A8]; this
0x18005604f  call    ??0AcquireWriteLock@cxl@@QEAA@AEAVNonReentrantRWLock@1@@Z; cxl::AcquireWriteLock::AcquireWriteLock(cxl::NonReentrantRWLock &)
0x180056054  nop
0x180056055  test    esi, esi
0x180056057  jz      short loc_1800560C9
0x180056059  mov     dword ptr [rdi+0F4h], 800705B4h
0x180056063  lea     rcx, [rdi+30h]; this
0x180056067  call    ?Set@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Set(void)
0x18005606c  xor     r8d, r8d; pcbe
0x18005606f  mov     rdx, rbx; pv
0x180056072  lea     rcx, ?CleanupReportSubscriptionCallback@smapi@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180056079  call    cs:__imp_CreateThreadpoolWork
0x180056080  nop     dword ptr [rax+rax+00h]
0x180056085  mov     rbx, rax
0x180056088  test    rax, rax
0x18005608b  jz      short loc_1800560A7
0x18005608d  lea     rcx, [rsp+138h+var_E0]
0x180056092  call    ?reset@?$shared_ptr@VGetReportContext@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::GetReportContext>::reset(void)
0x180056097  mov     rcx, rbx; pwk
0x18005609a  call    cs:__imp_SubmitThreadpoolWork
0x1800560a1  nop     dword ptr [rax+rax+00h]
0x1800560a6  nop
0x1800560a7  lea     rcx, [rsp+138h+var_A8]
0x1800560af  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x1800560b4  nop
0x1800560b5  mov     rcx, [rsp+138h+var_D8]; this
0x1800560ba  test    rcx, rcx
0x1800560bd  jz      short loc_1800560C4
0x1800560bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800560c4  jmp     loc_1800564BC
0x1800560c9  mov     eax, [rdi+0E8h]
0x1800560cf  cmp     eax, [rdi+0ECh]
0x1800560d5  jb      short loc_180056144
0x1800560d7  inc     eax
0x1800560d9  mov     [rdi+0E8h], eax
0x1800560df  cmp     eax, [rdi+0F0h]
0x1800560e5  jnz     short loc_180056122
0x1800560e7  xor     r8d, r8d; pcbe
0x1800560ea  mov     rdx, rbx; pv
0x1800560ed  lea     rcx, ?CleanupReportSubscriptionCallback@smapi@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800560f4  call    cs:__imp_CreateThreadpoolWork
0x1800560fb  nop     dword ptr [rax+rax+00h]
0x180056100  mov     rbx, rax
0x180056103  test    rax, rax
0x180056106  jz      short loc_180056122
0x180056108  lea     rcx, [rsp+138h+var_E0]
0x18005610d  call    ?reset@?$shared_ptr@VGetReportContext@Facade@Wsp@@@std@@QEAAXXZ; std::shared_ptr<Wsp::Facade::GetReportContext>::reset(void)
0x180056112  mov     rcx, rbx; pwk
0x180056115  call    cs:__imp_SubmitThreadpoolWork
0x18005611c  nop     dword ptr [rax+rax+00h]
0x180056121  nop
0x180056122  lea     rcx, [rsp+138h+var_A8]
0x18005612a  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x18005612f  nop
0x180056130  mov     rcx, [rsp+138h+var_D8]; this
0x180056135  test    rcx, rcx
0x180056138  jz      short loc_18005613F
0x18005613a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005613f  jmp     loc_1800564BC
0x180056144  mov     r12, [rdi+18h]
0x180056148  mov     [rsp+138h+var_F8], r14
0x18005614d  mov     [rsp+138h+var_78], r12
0x180056155  mov     [rsp+138h+var_70], r14
0x18005615d  lea     rdx, [rsp+138h+var_F8]
0x180056162  lea     rcx, [rsp+138h+var_78]
0x18005616a  call    ?Create@SchemaFactory@smapi@@SAXVMiContext@mi@@AEAV?$unique_ptr@UIStorageHealthReportSchema@smapi@@U?$default_delete@UIStorageHealthReportSchema@smapi@@@std@@@std@@@Z; smapi::SchemaFactory::Create(mi::MiContext,std::unique_ptr<smapi::IStorageHealthReportSchema> &)
0x18005616f  mov     rbx, [rsp+138h+var_F8]
0x180056174  mov     [rsp+138h+var_F8], r14
0x180056179  mov     [rsp+138h+var_108], r14
0x18005617e  mov     [rsp+138h+var_E8], rbx
0x180056183  lea     rcx, [rsp+138h+var_108]
0x180056188  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x18005618d  nop
0x18005618e  mov     rax, [rbx]
0x180056191  lea     rdx, [rdi+0A8h]
0x180056198  mov     rcx, rbx
0x18005619b  mov     rax, [rax+28h]
0x18005619f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561a4  mov     rax, [rbx]
0x1800561a7  mov     rsi, [rax+30h]
0x1800561ab  lea     rcx, [rsp+138h+var_B8]
0x1800561b3  call    ?GetInstance@MiSpaceAdapter@Wsp@@SA?AV?$shared_ptr@VMiSpaceAdapter@Wsp@@@std@@XZ; Wsp::MiSpaceAdapter::GetInstance(void)
0x1800561b8  nop
0x1800561b9  lea     r8, [rdi+88h]
0x1800561c0  mov     [rsp+138h+var_118], 2
0x1800561c8  mov     r9d, 1
0x1800561ce  lea     rdx, [rsp+138h+var_58]
0x1800561d6  mov     rcx, [rax]
0x1800561d9  call    ?PackObjectId@MiSpaceAdapter@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@@Z; Wsp::MiSpaceAdapter::PackObjectId(std::wstring const &,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE)
0x1800561de  nop
0x1800561df  mov     rdx, rax
0x1800561e2  mov     rcx, rbx
0x1800561e5  mov     rax, rsi
0x1800561e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561ed  nop
0x1800561ee  lea     rcx, [rsp+138h+var_58]
0x1800561f6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800561fb  nop
0x1800561fc  mov     rcx, [rsp+138h+var_B0]; this
0x180056204  test    rcx, rcx
0x180056207  jz      short loc_18005620E
0x180056209  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005620e  lea     rcx, [rsp+138h+var_D0]
0x180056213  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180056218  nop
0x180056219  mov     rax, [r13+0]
0x18005621d  mov     rcx, r13
0x180056220  mov     rax, [rax+10h]
0x180056224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056229  mov     [rsp+138h+var_F0], eax
0x18005622d  mov     r15d, r14d
0x180056230  cmp     r15d, eax
0x180056233  jnb     loc_1800563F1
0x180056239  mov     rax, [r13+0]
0x18005623d  mov     r8d, r15d
0x180056240  lea     rdx, [rsp+138h+var_58]
0x180056248  mov     rcx, r13
0x18005624b  mov     rax, [rax+20h]
0x18005624f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056254  mov     rax, [r13+0]
0x180056258  mov     edx, r15d
0x18005625b  mov     rcx, r13
0x18005625e  mov     rax, [rax+18h]
0x180056262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056267  test    eax, eax
0x180056269  jz      loc_18005632F
0x18005626f  cmp     eax, 1
0x180056272  jnz     loc_1800563E5
0x180056278  mov     [rsp+138h+var_108], r14
0x18005627d  mov     [rsp+138h+var_98], r12
0x180056285  mov     [rsp+138h+var_90], r14
0x18005628d  lea     rdx, [rsp+138h+var_108]
0x180056292  lea     rcx, [rsp+138h+var_98]
0x18005629a  call    ?Create@SchemaFactory@smapi@@SAXVMiContext@mi@@AEAV?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@std@@@Z; smapi::SchemaFactory::Create(mi::MiContext,std::unique_ptr<smapi::IHealthRecordUInt64Schema> &)
0x18005629f  mov     rsi, [rsp+138h+var_108]
0x1800562a4  mov     rax, [rsi]
0x1800562a7  mov     r14, [rax+28h]
0x1800562ab  mov     rdx, [rsp+138h+var_48]
0x1800562b3  lea     rcx, [rsp+138h+var_78]
0x1800562bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800562c0  nop
0x1800562c1  lea     rdx, [rsp+138h+var_78]
0x1800562c9  mov     rcx, rsi
0x1800562cc  mov     rax, r14
0x1800562cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562d4  nop
0x1800562d5  lea     rcx, [rsp+138h+var_78]
0x1800562dd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800562e2  mov     rax, [rsi]
0x1800562e5  mov     rdx, [rsp+138h+var_50]
0x1800562ed  mov     rcx, rsi
0x1800562f0  mov     rax, [rax+38h]
0x1800562f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562f9  mov     rax, [rsi]
0x1800562fc  movzx   edx, [rsp+138h+var_40]
0x180056304  mov     rcx, rsi
0x180056307  mov     rax, [rax+30h]
0x18005630b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056310  lea     rdx, [rsp+138h+var_108]
0x180056315  lea     rcx, [rsp+138h+var_D0]
0x18005631a  call    ??$emplace_back@V?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@std@@@?$vector@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@V?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@1@$$QEAV?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@1@@Z; std::vector<std::unique_ptr<smapi::IHealthRecordSchema>>::emplace_back<std::unique_ptr<smapi::IHealthRecordUInt64Schema>>(std::unique_ptr<smapi::IHealthRecordUInt64Schema> &&)
0x18005631f  nop
0x180056320  lea     rcx, [rsp+138h+var_108]
0x180056325  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x18005632a  jmp     loc_1800563E2
0x18005632f  mov     [rsp+138h+var_108], r14
0x180056334  mov     [rsp+138h+var_B8], r12
0x18005633c  mov     [rsp+138h+var_B0], r14
0x180056344  lea     rdx, [rsp+138h+var_108]
0x180056349  lea     rcx, [rsp+138h+var_B8]
0x180056351  call    ?Create@SchemaFactory@smapi@@SAXVMiContext@mi@@AEAV?$unique_ptr@UIHealthRecordReal64Schema@smapi@@U?$default_delete@UIHealthRecordReal64Schema@smapi@@@std@@@std@@@Z; smapi::SchemaFactory::Create(mi::MiContext,std::unique_ptr<smapi::IHealthRecordReal64Schema> &)
0x180056356  mov     rsi, [rsp+138h+var_108]
0x18005635b  mov     rax, [rsi]
0x18005635e  mov     r14, [rax+28h]
0x180056362  mov     rdx, [rsp+138h+var_48]
0x18005636a  lea     rcx, [rsp+138h+var_78]
0x180056372  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180056377  nop
0x180056378  lea     rdx, [rsp+138h+var_78]
0x180056380  mov     rcx, rsi
0x180056383  mov     rax, r14
0x180056386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005638b  nop
0x18005638c  lea     rcx, [rsp+138h+var_78]
0x180056394  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056399  mov     rax, [rsi]
0x18005639c  movsd   xmm1, [rsp+138h+var_50]
0x1800563a5  mov     rcx, rsi
0x1800563a8  mov     rax, [rax+38h]
0x1800563ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563b1  mov     rax, [rsi]
0x1800563b4  movzx   edx, [rsp+138h+var_40]
0x1800563bc  mov     rcx, rsi
0x1800563bf  mov     rax, [rax+30h]
0x1800563c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563c8  lea     rdx, [rsp+138h+var_108]
0x1800563cd  lea     rcx, [rsp+138h+var_D0]
0x1800563d2  call    ??$emplace_back@V?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@std@@@?$vector@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@V?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@1@$$QEAV?$unique_ptr@UIHealthRecordUInt64Schema@smapi@@U?$default_delete@UIHealthRecordUInt64Schema@smapi@@@std@@@1@@Z; std::vector<std::unique_ptr<smapi::IHealthRecordSchema>>::emplace_back<std::unique_ptr<smapi::IHealthRecordUInt64Schema>>(std::unique_ptr<smapi::IHealthRecordUInt64Schema> &&)
0x1800563d7  nop
0x1800563d8  lea     rcx, [rsp+138h+var_108]
0x1800563dd  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x1800563e2  xor     r14d, r14d
0x1800563e5  inc     r15d
0x1800563e8  mov     eax, [rsp+138h+var_F0]
0x1800563ec  jmp     loc_180056230
0x1800563f1  mov     rax, [rbx]
0x1800563f4  lea     rdx, [rsp+138h+var_D0]
0x1800563f9  mov     rcx, rbx
0x1800563fc  mov     rax, [rax+38h]
0x180056400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056405  mov     rax, [rbx]
0x180056408  lea     rdx, [rdi+0C8h]
0x18005640f  mov     rcx, rbx
0x180056412  mov     rax, [rax+10h]
0x180056416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005641b  inc     dword ptr [rdi+0E8h]
0x180056421  mov     eax, [rdi+0E8h]
0x180056427  cmp     eax, [rdi+0ECh]
0x18005642d  jb      short loc_180056439
0x18005642f  lea     rcx, [rdi+30h]; this
0x180056433  call    ?Set@ManualResetEvent@cxl@@QEAAXXZ; cxl::ManualResetEvent::Set(void)
0x180056438  nop
0x180056439  mov     rcx, [rsp+138h+var_D0]
0x18005643e  test    rcx, rcx
0x180056441  jz      short loc_180056471
0x180056443  mov     rdx, qword ptr [rsp+138h+var_C8]
0x180056448  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UIHealthRecordSchema@smapi@@U?$default_delete@UIHealthRecordSchema@smapi@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<smapi::IHealthRecordSchema>>>(std::unique_ptr<smapi::IHealthRecordSchema> *,std::unique_ptr<smapi::IHealthRecordSchema> * const,std::allocator<std::unique_ptr<smapi::IHealthRecordSchema>> &)
0x18005644d  mov     rcx, [rsp+138h+var_D0]
0x180056452  mov     rdx, qword ptr [rsp+138h+var_C8+8]
0x180056457  sub     rdx, rcx
0x18005645a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005645e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180056463  mov     [rsp+138h+var_D0], r14
0x180056468  xorps   xmm0, xmm0
0x18005646b  movdqu  [rsp+138h+var_C8], xmm0
0x180056471  lea     rcx, [rsp+138h+var_E8]
0x180056476  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x18005647b  nop
0x18005647c  lea     rcx, [rsp+138h+var_F8]
0x180056481  call    ??1?$unique_ptr@UIStorageHealthSchema@smapi@@U?$default_delete@UIStorageHealthSchema@smapi@@@std@@@std@@QEAA@XZ; std::unique_ptr<smapi::IStorageHealthSchema>::~unique_ptr<smapi::IStorageHealthSchema>(void)
0x180056486  nop
0x180056487  lea     rcx, [rsp+138h+var_A8]
0x18005648f  call    ?Release@?$ScopedResOwner@VNonReentrantRWLock@cxl@@V?$AcquireExclusiveTraits@VNonReentrantRWLock@cxl@@@2@@cxl@@QEBAXXZ; cxl::ScopedResOwner<cxl::NonReentrantRWLock,cxl::AcquireExclusiveTraits<cxl::NonReentrantRWLock>>::Release(void)
0x180056494  nop
0x180056495  mov     rcx, [rsp+138h+var_D8]; this
0x18005649a  test    rcx, rcx
0x18005649d  jz      short loc_1800564A5
0x18005649f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800564a4  nop
0x1800564a5  jmp     short loc_1800564BC
0x1800564a7  mov     rcx, [rsp+138h+var_D8]; this
0x1800564ac  test    rcx, rcx
0x1800564af  jz      short loc_1800564B6
0x1800564b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800564b6  jmp     short loc_1800564BC
0x1800564b8  jmp     short loc_1800564BC
0x1800564ba  jmp     short $+2
0x1800564bc  mov     rcx, [rsp+138h+var_38]
0x1800564c4  xor     rcx, rsp; StackCookie
0x1800564c7  call    __security_check_cookie
0x1800564cc  lea     r11, [rsp+138h+var_28]
0x1800564d4  mov     rbx, [r11+38h]
0x1800564d8  mov     rsi, [r11+48h]
0x1800564dc  mov     rsp, r11
0x1800564df  pop     r15
0x1800564e1  pop     r14
0x1800564e3  pop     r13
  ... truncated ...
```
