# Windows::Internal::Events::ParallelInvokeTraits<8>::Invoke<_lambda_7145197bcd7171bc1979b8af5902dfce_,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::UserCreatedEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>>>(_lambda_7145197bcd7171bc1979b8af5902dfce_ &,Windows::Internal::Events::HeapEventStore::HeapEventStoreTargets &,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::UserCreatedEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>> &,Windows::Internal::Events::WatchdogEventCallMonitor &,unsigned __int64)

- ea: `0x180053e4c`
- end: `0x180053f63`
- name: `??$Invoke@V_lambda_7145197bcd7171bc1979b8af5902dfce_@@V?$HardenedEventSource@U?$IEventHandler@PEAVUserCreatedEventArgs@Internal@System@Windows@@@Foundation@Windows@@$0JME@VHeapEventStore@Events@Internal@3@VWatchdogEventCallMonitor@563@U?$GitDelegateTraits@VGitPtr@Internal@Windows@@@563@V?$ParallelInvokeTraits@$07@563@@Internal@Windows@@@?$ParallelInvokeTraits@$07@Events@Internal@Windows@@SAXAEAV_lambda_7145197bcd7171bc1979b8af5902dfce_@@AEAVHeapEventStoreTargets@HeapEventStore@123@AEAV?$HardenedEventSource@U?$IEventHandler@PEAVUserCreatedEventArgs@Internal@System@Windows@@@Foundation@Windows@@$0JME@VHeapEventStore@Events@Internal@3@VWatchdogEventCallMonitor@563@U?$GitDelegateTraits@VGitPtr@Internal@Windows@@@563@V?$ParallelInvokeTraits@$07@563@@23@AEAVWatchdogEventCallMonitor@123@_K@Z`
- size: `279`
- prototype: `void __fastcall(__int64, Windows::Internal::Events::HeapEventStore *, __int64, __int64, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18008ed20`
- `0x18008f080`
- `0x18008fca0`
- `0x18008fec0`
- `0x1800901a0`

## callees

- `0x1800397c4`
- `0x180053e4c`
- `0x18006c380`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180053f4c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180053f4c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180053f02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180053f02`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180053f14`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180053f14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180053f3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180053f3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180053f30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180053f30`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall Windows::Internal::Events::ParallelInvokeTraits<8>::Invoke<_lambda_7145197bcd7171bc1979b8af5902dfce_,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::UserCreatedEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>>>(
        __int64 a1,
        Windows::Internal::Events::HeapEventStore *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  unsigned __int64 Size; // rax
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  _QWORD *v13; // rdi
  __int64 v14; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v16; // rbx
  struct _TP_WORK *v17; // rcx
  _QWORD pv[17]; // [rsp+20h] [rbp-88h] BYREF

  Size = Windows::Internal::Events::HeapEventStore::GetSize(a2);
  v10 = Size;
  if ( Size )
  {
    v11 = Size;
    if ( Size > 8 )
      v11 = 8;
    v12 = 8 * v11;
    if ( !is_mul_ok(v11, 8u) )
      v12 = -1;
    v13 = operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
    if ( v13 )
    {
      pv[5] = v10;
      v14 = 0;
      a5 = -1;
      pv[0] = a3;
      pv[1] = a4;
      pv[2] = a1;
      pv[3] = a2;
      pv[4] = &a5;
      pv[6] = 2500;
      do
      {
        ThreadpoolWork = CreateThreadpoolWork(_lambda_dba9ddd2cff4bea778a9446f00c90c85_::_lambda_invoker_cdecl_, pv, 0);
        v13[v14] = ThreadpoolWork;
        if ( ThreadpoolWork )
          SubmitThreadpoolWork(ThreadpoolWork);
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < v11 );
      v16 = 0;
      do
      {
        v17 = (struct _TP_WORK *)v13[v16];
        if ( v17 )
        {
          WaitForThreadpoolWorkCallbacks(v17, 0);
          CloseThreadpoolWork((PTP_WORK)v13[v16]);
        }
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < v11 );
      operator delete[](v13);
    }
  }
}

```

## disassembly

```asm
0x180053e4c  push    rbx
0x180053e4e  push    rbp
0x180053e4f  push    rsi
0x180053e50  push    rdi
0x180053e51  push    r12
0x180053e53  push    r13
0x180053e55  push    r14
0x180053e57  push    r15
0x180053e59  sub     rsp, 68h
0x180053e5d  mov     r12, rcx
0x180053e60  mov     r14, r9
0x180053e63  mov     rcx, rdx; this
0x180053e66  mov     r15, r8
0x180053e69  mov     rbp, rdx
0x180053e6c  call    ?GetSize@HeapEventStore@Events@Internal@Windows@@QEBA_KXZ; Windows::Internal::Events::HeapEventStore::GetSize(void)
0x180053e71  mov     rbx, rax
0x180053e74  test    rax, rax
0x180053e77  jz      loc_180053F52
0x180053e7d  mov     rsi, rax
0x180053e80  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180053e87  mov     eax, 8
0x180053e8c  cmp     rbx, rax
0x180053e8f  cmova   rsi, rax
0x180053e93  mul     rsi
0x180053e96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180053e9d  cmovb   rax, r13
0x180053ea1  mov     rcx, rax; unsigned __int64
0x180053ea4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180053ea9  mov     rdi, rax
0x180053eac  test    rax, rax
0x180053eaf  jz      loc_180053F52
0x180053eb5  mov     [rsp+0A8h+var_60], rbx
0x180053eba  lea     rax, [rsp+0A8h+arg_20]
0x180053ec2  xor     ebx, ebx
0x180053ec4  mov     [rsp+0A8h+arg_20], r13d
0x180053ecc  mov     [rsp+0A8h+pv], r15
0x180053ed1  mov     [rsp+0A8h+var_80], r14
0x180053ed6  mov     [rsp+0A8h+var_78], r12
0x180053edb  mov     [rsp+0A8h+var_70], rbp
0x180053ee0  mov     [rsp+0A8h+var_68], rax
0x180053ee5  mov     [rsp+0A8h+var_58], 9C4h
0x180053eee  test    rsi, rsi
0x180053ef1  jz      short loc_180053F49
0x180053ef3  xor     r8d, r8d; pcbe
0x180053ef6  lea     rdx, [rsp+0A8h+pv]; pv
0x180053efb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_dba9ddd2cff4bea778a9446f00c90c85_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180053f02  call    cs:__imp_CreateThreadpoolWork
0x180053f08  mov     [rdi+rbx*8], rax
0x180053f0c  test    rax, rax
0x180053f0f  jz      short loc_180053F1A
0x180053f11  mov     rcx, rax; pwk
0x180053f14  call    cs:__imp_SubmitThreadpoolWork
0x180053f1a  inc     ebx
0x180053f1c  mov     eax, ebx
0x180053f1e  cmp     rax, rsi
0x180053f21  jb      short loc_180053EF3
0x180053f23  xor     ebx, ebx
0x180053f25  mov     rcx, [rdi+rbx*8]; pwk
0x180053f29  test    rcx, rcx
0x180053f2c  jz      short loc_180053F40
0x180053f2e  xor     edx, edx; fCancelPendingCallbacks
0x180053f30  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180053f36  mov     rcx, [rdi+rbx*8]; pwk
0x180053f3a  call    cs:__imp_CloseThreadpoolWork
0x180053f40  inc     ebx
0x180053f42  mov     eax, ebx
0x180053f44  cmp     rax, rsi
0x180053f47  jb      short loc_180053F25
0x180053f49  mov     rcx, rdi
0x180053f4c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180053f52  add     rsp, 68h
0x180053f56  pop     r15
0x180053f58  pop     r14
0x180053f5a  pop     r13
0x180053f5c  pop     r12
0x180053f5e  pop     rdi
0x180053f5f  pop     rsi
0x180053f60  pop     rbp
0x180053f61  pop     rbx
0x180053f62  retn
```
