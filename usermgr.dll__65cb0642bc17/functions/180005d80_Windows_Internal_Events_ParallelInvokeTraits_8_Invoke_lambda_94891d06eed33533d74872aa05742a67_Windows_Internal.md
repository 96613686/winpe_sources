# Windows::Internal::Events::ParallelInvokeTraits<8>::Invoke<_lambda_94891d06eed33533d74872aa05742a67_,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>>>(_lambda_94891d06eed33533d74872aa05742a67_ &,Windows::Internal::Events::HeapEventStore::HeapEventStoreTargets &,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>> &,Windows::Internal::Events::WatchdogEventCallMonitor &,unsigned __int64)

- ea: `0x180005d80`
- end: `0x180005e97`
- name: `??$Invoke@V_lambda_94891d06eed33533d74872aa05742a67_@@V?$HardenedEventSource@U?$IEventHandler@PEAVSignOutCompleteEventArgs@Internal@System@Windows@@@Foundation@Windows@@$0JME@VHeapEventStore@Events@Internal@3@VWatchdogEventCallMonitor@563@U?$GitDelegateTraits@VGitPtr@Internal@Windows@@@563@V?$ParallelInvokeTraits@$07@563@@Internal@Windows@@@?$ParallelInvokeTraits@$07@Events@Internal@Windows@@SAXAEAV_lambda_94891d06eed33533d74872aa05742a67_@@AEAVHeapEventStoreTargets@HeapEventStore@123@AEAV?$HardenedEventSource@U?$IEventHandler@PEAVSignOutCompleteEventArgs@Internal@System@Windows@@@Foundation@Windows@@$0JME@VHeapEventStore@Events@Internal@3@VWatchdogEventCallMonitor@563@U?$GitDelegateTraits@VGitPtr@Internal@Windows@@@563@V?$ParallelInvokeTraits@$07@563@@23@AEAVWatchdogEventCallMonitor@123@_K@Z`
- size: `279`
- prototype: `void __fastcall(__int64, Windows::Internal::Events::HeapEventStore *, __int64, __int64, int)`
- caller_count: `11`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005958`
- `0x180006300`
- `0x18000dca8`
- `0x1800903c0`
- `0x1800914b8`
- `0x1800915d4`
- `0x1800a39d0`
- `0x1800a3bf8`
- `0x1800bb7c0`
- `0x1800bb950`
- `0x1800bbbd0`

## callees

- `0x180005d80`
- `0x1800397c4`
- `0x18006c380`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180005e80`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005e80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180005e36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180005e36`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005e48`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005e48`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005e6e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005e6e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180005e64`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180005e64`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Internal::Events::ParallelInvokeTraits<8>::Invoke<_lambda_94891d06eed33533d74872aa05742a67_,Windows::Internal::HardenedEventSource<Windows::Foundation::IEventHandler<Windows::System::Internal::SignOutCompleteEventArgs *>,2500,Windows::Internal::Events::HeapEventStore,Windows::Internal::Events::WatchdogEventCallMonitor,Windows::Internal::Events::GitDelegateTraits<Windows::Internal::GitPtr>,Windows::Internal::Events::ParallelInvokeTraits<8>>>(
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
        ThreadpoolWork = CreateThreadpoolWork(_lambda_d169b7d68a1c7430a7019dd2a380950d_::_lambda_invoker_cdecl_, pv, 0);
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
0x180005d80  push    rbx
0x180005d82  push    rbp
0x180005d83  push    rsi
0x180005d84  push    rdi
0x180005d85  push    r12
0x180005d87  push    r13
0x180005d89  push    r14
0x180005d8b  push    r15
0x180005d8d  sub     rsp, 68h
0x180005d91  mov     r12, rcx
0x180005d94  mov     r14, r9
0x180005d97  mov     rcx, rdx; this
0x180005d9a  mov     r15, r8
0x180005d9d  mov     rbp, rdx
0x180005da0  call    ?GetSize@HeapEventStore@Events@Internal@Windows@@QEBA_KXZ; Windows::Internal::Events::HeapEventStore::GetSize(void)
0x180005da5  mov     rbx, rax
0x180005da8  test    rax, rax
0x180005dab  jz      loc_180005E86
0x180005db1  mov     rsi, rax
0x180005db4  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180005dbb  mov     eax, 8
0x180005dc0  cmp     rbx, rax
0x180005dc3  cmova   rsi, rax
0x180005dc7  mul     rsi
0x180005dca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005dd1  cmovb   rax, r13
0x180005dd5  mov     rcx, rax; unsigned __int64
0x180005dd8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005ddd  mov     rdi, rax
0x180005de0  test    rax, rax
0x180005de3  jz      loc_180005E86
0x180005de9  mov     [rsp+0A8h+var_60], rbx
0x180005dee  lea     rax, [rsp+0A8h+arg_20]
0x180005df6  xor     ebx, ebx
0x180005df8  mov     [rsp+0A8h+arg_20], r13d
0x180005e00  mov     [rsp+0A8h+pv], r15
0x180005e05  mov     [rsp+0A8h+var_80], r14
0x180005e0a  mov     [rsp+0A8h+var_78], r12
0x180005e0f  mov     [rsp+0A8h+var_70], rbp
0x180005e14  mov     [rsp+0A8h+var_68], rax
0x180005e19  mov     [rsp+0A8h+var_58], 9C4h
0x180005e22  test    rsi, rsi
0x180005e25  jz      short loc_180005E7D
0x180005e27  xor     r8d, r8d; pcbe
0x180005e2a  lea     rdx, [rsp+0A8h+pv]; pv
0x180005e2f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d169b7d68a1c7430a7019dd2a380950d_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180005e36  call    cs:__imp_CreateThreadpoolWork
0x180005e3c  mov     [rdi+rbx*8], rax
0x180005e40  test    rax, rax
0x180005e43  jz      short loc_180005E4E
0x180005e45  mov     rcx, rax; pwk
0x180005e48  call    cs:__imp_SubmitThreadpoolWork
0x180005e4e  inc     ebx
0x180005e50  mov     eax, ebx
0x180005e52  cmp     rax, rsi
0x180005e55  jb      short loc_180005E27
0x180005e57  xor     ebx, ebx
0x180005e59  mov     rcx, [rdi+rbx*8]; pwk
0x180005e5d  test    rcx, rcx
0x180005e60  jz      short loc_180005E74
0x180005e62  xor     edx, edx; fCancelPendingCallbacks
0x180005e64  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180005e6a  mov     rcx, [rdi+rbx*8]; pwk
0x180005e6e  call    cs:__imp_CloseThreadpoolWork
0x180005e74  inc     ebx
0x180005e76  mov     eax, ebx
0x180005e78  cmp     rax, rsi
0x180005e7b  jb      short loc_180005E59
0x180005e7d  mov     rcx, rdi
0x180005e80  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005e86  add     rsp, 68h
0x180005e8a  pop     r15
0x180005e8c  pop     r14
0x180005e8e  pop     r13
0x180005e90  pop     r12
0x180005e92  pop     rdi
0x180005e93  pop     rsi
0x180005e94  pop     rbp
0x180005e95  pop     rbx
0x180005e96  retn
```
