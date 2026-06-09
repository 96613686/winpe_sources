# mi::MiSession::WriteErrorCallback(_MI_Operation *,void *,_MI_Instance *,_MI_Result (*)(_MI_Operation *,_MI_OperationCallback_ResponseType))

- ea: `0x1800256e0`
- end: `0x180025873`
- name: `?WriteErrorCallback@MiSession@mi@@CAXPEAU_MI_Operation@@PEAXPEAU_MI_Instance@@P6A?AW4_MI_Result@@0W4_MI_OperationCallback_ResponseType@@@Z@Z`
- size: `403`
- prototype: `static void(struct _MI_Operation *, void *, struct _MI_Instance *, enum _MI_Result (*)(struct _MI_Operation *, enum _MI_OperationCallback_ResponseType))`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800014e0`
- `0x180006630`
- `0x1800242d8`
- `0x180024358`
- `0x1800256e0`
- `0x180026aec`
- `0x180026c30`
- `0x180027154`
- `0x180028630`
- `0x180028658`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800257f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800257f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025827`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025827`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall mi::MiSession::WriteErrorCallback(
        struct _MI_Operation *a1,
        RTL_SRWLOCK *a2,
        struct _MI_Instance *a3,
        enum _MI_Result (*a4)(struct _MI_Operation *, enum _MI_OperationCallback_ResponseType))
{
  _QWORD *v6; // rdx
  __int64 application; // rax
  __int64 v8; // r10
  PVOID Ptr; // rcx
  bool v10; // dl
  MI_CancellationReason v11; // edx
  RTL_SRWLOCK *v14; // [rsp+30h] [rbp-118h] BYREF
  std::_Ref_count_base *v15; // [rsp+38h] [rbp-110h]
  _BYTE v16[8]; // [rsp+40h] [rbp-108h] BYREF
  std::_Ref_count_base *v17; // [rsp+48h] [rbp-100h]
  _QWORD v18[2]; // [rsp+60h] [rbp-E8h] BYREF
  int v19; // [rsp+70h] [rbp-D8h]
  int v20; // [rsp+74h] [rbp-D4h]
  struct _MI_Operation *v21; // [rsp+78h] [rbp-D0h]
  _QWORD *v22; // [rsp+98h] [rbp-B0h]
  _BYTE v23[64]; // [rsp+A0h] [rbp-A8h] BYREF
  _BYTE v24[80]; // [rsp+E0h] [rbp-68h] BYREF

  if ( a2 )
  {
    v18[0] = &std::_Func_impl_no_alloc<_lambda_64db709adc652e24d02859799101a95a_,void,>::`vftable';
    v18[1] = a4;
    v19 = 0;
    v20 = HIDWORD(v17);
    v21 = a1;
    v22 = v18;
    mi::ScopeGuardT<std::function<void (void)>>::ScopeGuardT<std::function<void (void)>>(v24, v18);
    if ( v22 )
    {
      v6 = v18;
      LOBYTE(v6) = v22 != v18;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v22 + 32LL))(v22, v6);
    }
    mi::MiAsyncOperation::MiOperationArgs::get_session(a2, v16);
    application = mi::MiAsyncOperation::MiOperationArgs::get_application(a2, &v14);
    mi::MiInstance::MiInstance(v23, application, v8, 0);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    try
    {
      if ( a3 )
        mi::MiInstance::Attach((mi::MiInstance *)v23, a3);
      v14 = a2 + 57;
      AcquireSRWLockShared(a2 + 57);
      Ptr = a2[49].Ptr;
      if ( Ptr )
        (*(void (__fastcall **)(PVOID, _BYTE *))(*(_QWORD *)Ptr + 16LL))(Ptr, v23);
      ReleaseSRWLockShared(a2 + 57);
      mi::MiInstance::~MiInstance((mi::MiInstance *)v23);
    }
    catch ( ... )
    {
      mi::MiAsyncOperation::MiOperationArgs::store_exception((mi::MiAsyncOperation::MiOperationArgs *)a2);
      mi::MiAsyncOperation::MiOperationArgs::set_resultsCanceled((mi::MiAsyncOperation::MiOperationArgs *)a2, v10);
      MI_Operation_Cancel(a1, v11);
    }
    mi::ScopeGuardT<std::function<void (void)>>::~ScopeGuardT<std::function<void (void)>>(v24);
  }
}

```

## disassembly

```asm
0x1800256e0  test    rdx, rdx
0x1800256e3  jz      locret_180025871
0x1800256e9  mov     r11, rsp
0x1800256ec  mov     [r11+20h], rbx
0x1800256f0  push    rdi
0x1800256f1  sub     rsp, 140h
0x1800256f8  mov     rax, cs:__security_cookie
0x1800256ff  xor     rax, rsp
0x180025702  mov     [rsp+148h+var_18], rax
0x18002570a  mov     rbx, r8
0x18002570d  mov     rdi, rdx
0x180025710  mov     [rsp+148h+var_120], rcx
0x180025715  mov     [rsp+148h+var_128], rdx
0x18002571a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_64db709adc652e24d02859799101a95a_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_64db709adc652e24d02859799101a95a_,void,>::`vftable'
0x180025721  mov     [rsp+148h+var_E8], rax
0x180025726  mov     [rsp+148h+var_E0], r9
0x18002572b  mov     [rsp+148h+var_D8], 0
0x180025733  mov     eax, [rsp+148h+var_FC]
0x180025737  mov     [rsp+148h+var_D4], eax
0x18002573b  mov     [rsp+148h+var_D0], rcx
0x180025740  lea     rax, [rsp+148h+var_E8]
0x180025745  mov     [r11-0B0h], rax
0x18002574c  lea     rdx, [rsp+148h+var_E8]
0x180025751  lea     rcx, [r11-68h]
0x180025755  call    ??0?$ScopeGuardT@V?$function@$$A6AXXZ@std@@@mi@@QEAA@AEBV?$function@$$A6AXXZ@std@@@Z; mi::ScopeGuardT<std::function<void (void)>>::ScopeGuardT<std::function<void (void)>>(std::function<void (void)> const &)
0x18002575a  nop
0x18002575b  mov     rcx, [rsp+148h+var_B0]
0x180025763  test    rcx, rcx
0x180025766  jz      short loc_180025780
0x180025768  mov     rax, [rcx]
0x18002576b  lea     rdx, [rsp+148h+var_E8]
0x180025770  cmp     rcx, rdx
0x180025773  setnz   dl
0x180025776  mov     rax, [rax+20h]
0x18002577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002577f  nop
0x180025780  lea     rdx, [rsp+148h+var_108]
0x180025785  mov     rcx, rdi
0x180025788  call    ?get_session@MiOperationArgs@MiAsyncOperation@mi@@QEBA?BV?$shared_ptr@$$CBVMiSession@mi@@@std@@XZ; mi::MiAsyncOperation::MiOperationArgs::get_session(void)
0x18002578d  mov     r10, rax
0x180025790  lea     rdx, [rsp+148h+var_118]
0x180025795  mov     rcx, rdi
0x180025798  call    ?get_application@MiOperationArgs@MiAsyncOperation@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiAsyncOperation::MiOperationArgs::get_application(void)
0x18002579d  xor     r9d, r9d
0x1800257a0  mov     r8, r10
0x1800257a3  mov     rdx, rax
0x1800257a6  lea     rcx, [rsp+148h+var_A8]
0x1800257ae  call    ??0MiInstance@mi@@AEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@3@_N@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,bool)
0x1800257b3  nop
0x1800257b4  mov     rcx, [rsp+148h+var_110]; this
0x1800257b9  test    rcx, rcx
0x1800257bc  jz      short loc_1800257C3
0x1800257be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800257c3  mov     rcx, [rsp+48h]; this
0x1800257c8  test    rcx, rcx
0x1800257cb  jz      short loc_1800257D2
0x1800257cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800257d2  test    rbx, rbx
0x1800257d5  jz      short loc_1800257E7
0x1800257d7  mov     rdx, rbx; struct _MI_Instance *
0x1800257da  lea     rcx, [rsp+148h+var_A8]; this
0x1800257e2  call    ?Attach@MiInstance@mi@@QEAAXPEBU_MI_Instance@@@Z; mi::MiInstance::Attach(_MI_Instance const *)
0x1800257e7  lea     rbx, [rdi+1C8h]
0x1800257ee  mov     [rsp+148h+var_118], rbx
0x1800257f3  mov     rcx, rbx; SRWLock
0x1800257f6  call    cs:__imp_AcquireSRWLockShared
0x1800257fd  nop     dword ptr [rax+rax+00h]
0x180025802  nop
0x180025803  mov     rcx, [rdi+188h]
0x18002580a  test    rcx, rcx
0x18002580d  jz      short loc_180025824
0x18002580f  mov     rax, [rcx]
0x180025812  lea     rdx, [rsp+148h+var_A8]
0x18002581a  mov     rax, [rax+10h]
0x18002581e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025823  nop
0x180025824  mov     rcx, rbx; SRWLock
0x180025827  call    cs:__imp_ReleaseSRWLockShared
0x18002582e  nop     dword ptr [rax+rax+00h]
0x180025833  nop
0x180025834  lea     rcx, [rsp+148h+var_A8]; this
0x18002583c  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x180025841  nop
0x180025842  jmp     short $+2
0x180025844  lea     rcx, [rsp+148h+var_68]
0x18002584c  call    ??1?$ScopeGuardT@V?$function@$$A6AXXZ@std@@@mi@@QEAA@XZ; mi::ScopeGuardT<std::function<void (void)>>::~ScopeGuardT<std::function<void (void)>>(void)
0x180025851  mov     rcx, [rsp+148h+var_18]
0x180025859  xor     rcx, rsp; StackCookie
0x18002585c  call    __security_check_cookie
0x180025861  mov     rbx, [rsp+148h+arg_18]
0x180025869  add     rsp, 140h
0x180025870  pop     rdi
0x180025871  retn
```
