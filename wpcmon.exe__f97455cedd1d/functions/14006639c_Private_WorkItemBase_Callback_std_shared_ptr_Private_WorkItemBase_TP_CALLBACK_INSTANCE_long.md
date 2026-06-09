# Private::WorkItemBase::Callback(std::shared_ptr<Private::WorkItemBase> &&,_TP_CALLBACK_INSTANCE *,long)

- ea: `0x14006639c`
- end: `0x14006668b`
- name: `?Callback@WorkItemBase@Private@@CAX$$QEAV?$shared_ptr@VWorkItemBase@Private@@@std@@PEAU_TP_CALLBACK_INSTANCE@@J@Z`
- size: `751`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140066fb0`
- `0x1400670f0`

## callees

- `0x140005530`
- `0x140006338`
- `0x140061310`
- `0x140062c94`
- `0x140062ddc`
- `0x140063170`
- `0x140063930`
- `0x140063c38`
- `0x14006639c`
- `0x140067058`
- `0x140067360`
- `0x1400673a0`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CallbackMayRunLong` at `0x1400663ea`
- `KERNEL32!CallbackMayRunLong` at `0x1400663ea`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x140066493`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x140066493`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1400664ae`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1400664ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400664c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400664c7`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400664bf`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400664bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Private::WorkItemBase::Callback(struct Private::WorkItemBase **a1, struct _TP_CALLBACK_INSTANCE *a2)
{
  struct Private::WorkItemBase **v3; // r14
  __int64 v4; // rdx
  __int64 v5; // r8
  _QWORD *ThreadId; // rax
  __int64 v7; // rdx
  struct Private::WorkItemBase *v8; // rdi
  void (__fastcall *v9)(struct Private::WorkItemBase *, Private::ThreadpoolImpl **); // rbx
  int v10; // r8d
  struct Private::WorkItemBase *v11; // rdi
  __int64 v12; // rdx
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  Private::ThreadpoolImpl *v15; // rcx
  volatile signed __int32 *v16; // rdi
  struct Private::WorkItemBase *v17; // rax
  volatile signed __int32 *v18; // rcx
  volatile signed __int32 *v19; // rdi
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, Private::ThreadpoolImpl **); // rbx
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, __int128 *); // rbx
  Private::ThreadpoolImpl *v24[2]; // [rsp+30h] [rbp-128h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-118h] BYREF
  __int128 v26; // [rsp+48h] [rbp-110h] BYREF
  DWORD v27; // [rsp+58h] [rbp-100h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v29; // [rsp+80h] [rbp-D8h]
  _BYTE v30[160]; // [rsp+90h] [rbp-C8h] BYREF

  v3 = a1;
  *(_QWORD *)&v26 = a1;
  (*(void (__fastcall **)(struct Private::WorkItemBase *, unsigned int *))(*(_QWORD *)*a1 + 32LL))(*a1, &v25);
  if ( *((_BYTE *)*v3 + 24) )
    CallbackMayRunLong(a2);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
    WPP_SF_DD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v4, v5, v25);
  try
  {
    Threading::ThreadEntered::ThreadEntered((Threading::ThreadEntered *)v30, *((unsigned __int8 *)*v3 + 24));
    Threading::SetPerformanceId(v24, v25);
    ThreadId = (_QWORD *)Threading::GetThreadId(v24);
    try
    {
      *((_QWORD *)*v3 + 8) = *ThreadId;
      if ( *((_BYTE *)*v3 + 72) )
      {
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        v29 = 0;
        ThreadCancelledException::ThreadCancelledException((ThreadCancelledException *)pExceptionObject);
        throw (ThreadCancelledException *)pExceptionObject;
      }
      ComInitialize::ComInitialize(&v27, *((_DWORD *)*v3 + 7));
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(struct Private::WorkItemBase *, __int64))(*(_QWORD *)*v3 + 16LL))(*v3, v7);
      v8 = *v3;
      v9 = *(void (__fastcall **)(struct Private::WorkItemBase *, Private::ThreadpoolImpl **))(*(_QWORD *)*v3 + 24LL);
      *(_OWORD *)v24 = 0;
      __ExceptionPtrCreate(v24);
      v9(v8, v24);
      __ExceptionPtrDestroy(v24);
      if ( (v27 & 0xFFFFFFFD) != 0 )
        RoUninitialize();
      else
        CoUninitialize();
    }
    catch ( std::exception )
    {
      v20 = *(_QWORD *)v26;
      v21 = *(void (__fastcall **)(__int64, Private::ThreadpoolImpl **))(**(_QWORD **)v26 + 24LL);
      *(_OWORD *)v24 = 0;
      __ExceptionPtrCreate(v24);
      __ExceptionPtrCurrentException(v24);
      v21(v20, v24);
      __ExceptionPtrDestroy(v24);
      v3 = (struct Private::WorkItemBase **)v26;
    }
    v11 = *v3;
    *(_OWORD *)v24 = 0;
    v12 = *((_QWORD *)v11 + 5);
    if ( v12 )
    {
      v13 = *(_DWORD *)(v12 + 8);
      while ( v13 )
      {
        v14 = v13;
        v13 = _InterlockedCompareExchange((volatile signed __int32 *)(v12 + 8), v13 + 1, v13);
        if ( v14 == v13 )
        {
          v15 = (Private::ThreadpoolImpl *)*((_QWORD *)v11 + 4);
          v24[0] = v15;
          v16 = (volatile signed __int32 *)*((_QWORD *)v11 + 5);
          v24[1] = (Private::ThreadpoolImpl *)v16;
          goto LABEL_15;
        }
      }
    }
    v15 = v24[0];
    v16 = (volatile signed __int32 *)v24[1];
LABEL_15:
    if ( v15 )
    {
      Private::ThreadpoolImpl::Unregister(v15, *v3);
      v17 = *v3;
      *((_QWORD *)v17 + 4) = 0;
      v18 = (volatile signed __int32 *)*((_QWORD *)v17 + 5);
      *((_QWORD *)v17 + 5) = 0;
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    *v3 = 0;
    v19 = (volatile signed __int32 *)v3[1];
    v3[1] = 0;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    Threading::ThreadEntered::~ThreadEntered((Threading::ThreadEntered *)v30, v12, v10);
  }
  catch ( std::exception )
  {
    v22 = *(_QWORD *)v26;
    v23 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)v26 + 24LL);
    v26 = 0;
    __ExceptionPtrCreate(&v26);
    __ExceptionPtrCurrentException(&v26);
    v23(v22, &v26);
    __ExceptionPtrDestroy(&v26);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v25);
}

```

## disassembly

```asm
0x14006639c  mov     [rsp+arg_10], rbx
0x1400663a1  push    rdi
0x1400663a2  push    r14
0x1400663a4  push    r15
0x1400663a6  sub     rsp, 140h
0x1400663ad  mov     rax, cs:__security_cookie
0x1400663b4  xor     rax, rsp
0x1400663b7  mov     [rsp+158h+var_28], rax
0x1400663bf  mov     rbx, rdx
0x1400663c2  mov     r14, rcx
0x1400663c5  mov     qword ptr [rsp+158h+var_110], rcx
0x1400663ca  mov     rcx, [rcx]
0x1400663cd  mov     rax, [rcx]
0x1400663d0  lea     rdx, [rsp+158h+var_118]
0x1400663d5  mov     rax, [rax+20h]
0x1400663d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400663de  mov     rax, [r14]
0x1400663e1  cmp     byte ptr [rax+18h], 0
0x1400663e5  jz      short loc_1400663F0
0x1400663e7  mov     rcx, rbx; pci
0x1400663ea  call    cs:__imp_CallbackMayRunLong
0x1400663f0  lea     r15, WPP_GLOBAL_Control
0x1400663f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400663fe  cmp     rcx, r15
0x140066401  jz      short loc_140066418
0x140066403  test    byte ptr [rcx+1Ch], 10h
0x140066407  jz      short loc_140066418
0x140066409  mov     r9d, [rsp+158h+var_118]
0x14006640e  mov     rcx, [rcx+10h]
0x140066412  call    WPP_SF_DD
0x140066417  nop
0x140066418  mov     rax, [r14]
0x14006641b  movzx   edx, byte ptr [rax+18h]; int
0x14006641f  lea     rcx, [rsp+158h+var_C8]; this
0x140066427  call    ??0ThreadEntered@Threading@@QEAA@H@Z; Threading::ThreadEntered::ThreadEntered(int)
0x14006642c  nop
0x14006642d  mov     edx, [rsp+158h+var_118]
0x140066431  lea     rcx, [rsp+158h+var_128]
0x140066436  call    ?SetPerformanceId@Threading@@YA?AUPerformanceId@Private@@U23@@Z; Threading::SetPerformanceId(Private::PerformanceId)
0x14006643b  lea     rcx, [rsp+158h+var_128]
0x140066440  call    ?GetThreadId@Threading@@YA?ATThreadId@Private@@XZ; Threading::GetThreadId(void)
0x140066445  mov     rcx, [r14]
0x140066448  mov     rax, [rax]
0x14006644b  mov     [rcx+40h], rax
0x14006644f  mov     rdx, [r14]
0x140066452  cmp     byte ptr [rdx+48h], 0
0x140066456  jnz     loc_140066657
0x14006645c  mov     edx, [rdx+1Ch]
0x14006645f  lea     rcx, [rsp+158h+var_100]
0x140066464  call    ??0ComInitialize@@QEAA@W4ComApartment@ComApartments@@_N@Z; ComInitialize::ComInitialize(ComApartments::ComApartment,bool)
0x140066469  nop
0x14006646a  mov     rcx, [r14]
0x14006646d  mov     rax, [rcx]
0x140066470  mov     dl, 1
0x140066472  mov     rax, [rax+10h]
0x140066476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006647b  mov     rdi, [r14]
0x14006647e  mov     rax, [rdi]
0x140066481  mov     rbx, [rax+18h]
0x140066485  xorps   xmm0, xmm0
0x140066488  movdqu  xmmword ptr [rsp+158h+var_128], xmm0
0x14006648e  lea     rcx, [rsp+158h+var_128]
0x140066493  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x140066499  lea     rdx, [rsp+158h+var_128]
0x14006649e  mov     rcx, rdi
0x1400664a1  mov     rax, rbx
0x1400664a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400664a9  lea     rcx, [rsp+158h+var_128]
0x1400664ae  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1400664b4  nop
0x1400664b5  test    [rsp+158h+var_100], 0FFFFFFFDh
0x1400664bd  jz      short loc_1400664C7
0x1400664bf  call    cs:__imp_RoUninitialize
0x1400664c5  jmp     short loc_1400664CE
0x1400664c7  call    cs:__imp_CoUninitialize
0x1400664cd  nop
0x1400664ce  jmp     short loc_1400664DC
0x1400664d0  lea     r15, WPP_GLOBAL_Control
0x1400664d7  mov     r14, qword ptr [rsp+158h+var_110]
0x1400664dc  mov     rdi, [r14]
0x1400664df  xorps   xmm0, xmm0
0x1400664e2  movdqu  xmmword ptr [rsp+158h+var_128], xmm0
0x1400664e8  mov     rdx, [rdi+28h]
0x1400664ec  test    rdx, rdx
0x1400664ef  jz      short loc_140066504
0x1400664f1  mov     eax, [rdx+8]
0x1400664f4  jmp     short loc_140066500
0x1400664f6  lea     ecx, [rax+1]
0x1400664f9  lock cmpxchg [rdx+8], ecx
0x1400664fe  jz      short loc_140066553
0x140066500  test    eax, eax
0x140066502  jnz     short loc_1400664F6
0x140066504  mov     rcx, [rsp+158h+var_128]; this
0x140066509  mov     rdi, [rsp+158h+var_128+8]
0x14006650e  test    rcx, rcx
0x140066511  jz      short loc_140066567
0x140066513  mov     rdx, [r14]; struct Private::WorkItemBase *
0x140066516  call    ?Unregister@ThreadpoolImpl@Private@@QEAAXAEAVWorkItemBase@2@@Z; Private::ThreadpoolImpl::Unregister(Private::WorkItemBase &)
0x14006651b  mov     rax, [r14]
0x14006651e  mov     qword ptr [rax+20h], 0
0x140066526  mov     rcx, [rax+28h]
0x14006652a  mov     qword ptr [rax+28h], 0
0x140066532  test    rcx, rcx
0x140066535  jz      short loc_140066567
0x140066537  or      ebx, 0FFFFFFFFh
0x14006653a  mov     eax, ebx
0x14006653c  lock xadd [rcx+0Ch], eax
0x140066541  add     eax, ebx
0x140066543  jnz     short loc_14006656A
0x140066545  mov     rax, [rcx]
0x140066548  mov     rax, [rax+8]
0x14006654c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066551  jmp     short loc_14006656A
0x140066553  mov     rcx, [rdi+20h]
0x140066557  mov     [rsp+158h+var_128], rcx
0x14006655c  mov     rdi, [rdi+28h]
0x140066560  mov     [rsp+158h+var_128+8], rdi
0x140066565  jmp     short loc_14006650E
0x140066567  or      ebx, 0FFFFFFFFh
0x14006656a  test    rdi, rdi
0x14006656d  jz      short loc_1400665A2
0x14006656f  mov     eax, ebx
0x140066571  lock xadd [rdi+8], eax
0x140066576  add     eax, ebx
0x140066578  jnz     short loc_1400665A2
0x14006657a  mov     rax, [rdi]
0x14006657d  mov     rcx, rdi
0x140066580  mov     rax, [rax]
0x140066583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066588  mov     eax, ebx
0x14006658a  lock xadd [rdi+0Ch], eax
0x14006658f  add     eax, ebx
0x140066591  jnz     short loc_1400665A2
0x140066593  mov     rax, [rdi]
0x140066596  mov     rcx, rdi
0x140066599  mov     rax, [rax+8]
0x14006659d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400665a2  mov     qword ptr [r14], 0
0x1400665a9  mov     rdi, [r14+8]
0x1400665ad  mov     qword ptr [r14+8], 0
0x1400665b5  test    rdi, rdi
0x1400665b8  jz      short loc_1400665EE
0x1400665ba  mov     eax, ebx
0x1400665bc  lock xadd [rdi+8], eax
0x1400665c1  add     eax, ebx
0x1400665c3  jnz     short loc_1400665EE
0x1400665c5  mov     rax, [rdi]
0x1400665c8  mov     rcx, rdi
0x1400665cb  mov     rax, [rax]
0x1400665ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400665d3  mov     eax, ebx
0x1400665d5  lock xadd [rdi+0Ch], eax
0x1400665da  add     eax, ebx
0x1400665dc  jnz     short loc_1400665EE
0x1400665de  mov     rax, [rdi]
0x1400665e1  mov     rcx, rdi
0x1400665e4  mov     rax, [rax+8]
0x1400665e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400665ed  nop
0x1400665ee  lea     rcx, [rsp+158h+var_C8]; this
0x1400665f6  call    ??1ThreadEntered@Threading@@QEAA@XZ; Threading::ThreadEntered::~ThreadEntered(void)
0x1400665fb  nop
0x1400665fc  jmp     short loc_140066605
0x1400665fe  lea     r15, WPP_GLOBAL_Control
0x140066605  mov     rcx, cs:WPP_GLOBAL_Control
0x14006660c  cmp     rcx, r15
0x14006660f  jz      short loc_140066632
0x140066611  test    byte ptr [rcx+1Ch], 10h
0x140066615  jz      short loc_140066632
0x140066617  mov     edx, 0Fh
0x14006661c  mov     r9d, [rsp+158h+var_118]
0x140066621  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x140066628  mov     rcx, [rcx+10h]
0x14006662c  call    WPP_SF_D
0x140066631  nop
0x140066632  mov     rcx, [rsp+158h+var_28]
0x14006663a  xor     rcx, rsp; StackCookie
0x14006663d  call    __security_check_cookie
0x140066642  mov     rbx, [rsp+158h+arg_10]
0x14006664a  add     rsp, 140h
0x140066651  pop     r15
0x140066653  pop     r14
0x140066655  pop     rdi
0x140066656  retn
0x140066657  xorps   xmm0, xmm0
0x14006665a  xor     eax, eax
0x14006665c  movups  [rsp+158h+pExceptionObject], xmm0
0x140066661  movups  [rsp+158h+var_E8], xmm0
0x140066666  mov     [rsp+158h+var_D8], rax
0x14006666e  lea     rcx, [rsp+158h+pExceptionObject]; this
0x140066673  call    ??0ThreadCancelledException@@QEAA@XZ; ThreadCancelledException::ThreadCancelledException(void)
0x140066678  lea     rdx, _TI4?AVThreadCancelledException@@; pThrowInfo
0x14006667f  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x140066684  call    _CxxThrowException_0
```
