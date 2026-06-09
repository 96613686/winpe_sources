# mi::MiSession::WriteErrorCallback(_MI_Operation *,void *,_MI_Instance *,_MI_Result (*)(_MI_Operation *,_MI_OperationCallback_ResponseType))

- ea: `0x1800253e0`
- end: `0x180025566`
- name: `?WriteErrorCallback@MiSession@mi@@CAXPEAU_MI_Operation@@PEAXPEAU_MI_Instance@@P6A?AW4_MI_Result@@0W4_MI_OperationCallback_ResponseType@@@Z@Z`
- size: `390`
- prototype: `void __fastcall(struct _MI_Operation *, RTL_SRWLOCK *, struct _MI_Instance *, enum _MI_Result (*)(struct _MI_Operation *, enum _MI_OperationCallback_ResponseType))`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800014e0`
- `0x1800065ec`
- `0x180024004`
- `0x180024080`
- `0x1800253e0`
- `0x1800267a8`
- `0x1800268e4`
- `0x180026dfc`
- `0x180028238`
- `0x18002825c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800254f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800254f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025521`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025521`

## pseudocode

```c
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
  std::_Ref_count_base *v23[8]; // [rsp+A0h] [rbp-A8h] BYREF
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
        (*(void (__fastcall **)(PVOID, std::_Ref_count_base **))(*(_QWORD *)Ptr + 16LL))(Ptr, v23);
      ReleaseSRWLockShared(a2 + 57);
      mi::MiInstance::~MiInstance(v23);
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
0x1800253e0  test    rdx, rdx
0x1800253e3  jz      locret_180025565
0x1800253e9  mov     r11, rsp
0x1800253ec  mov     [r11+20h], rbx
0x1800253f0  push    rdi
0x1800253f1  sub     rsp, 140h
0x1800253f8  mov     rax, cs:__security_cookie
0x1800253ff  xor     rax, rsp
0x180025402  mov     [rsp+148h+var_18], rax
0x18002540a  mov     rbx, r8
0x18002540d  mov     rdi, rdx
0x180025410  mov     [rsp+148h+var_120], rcx
0x180025415  mov     [rsp+148h+var_128], rdx
0x18002541a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_64db709adc652e24d02859799101a95a_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_64db709adc652e24d02859799101a95a_,void,>::`vftable'
0x180025421  mov     [rsp+148h+var_E8], rax
0x180025426  mov     [rsp+148h+var_E0], r9
0x18002542b  mov     [rsp+148h+var_D8], 0
0x180025433  mov     eax, [rsp+148h+var_FC]
0x180025437  mov     [rsp+148h+var_D4], eax
0x18002543b  mov     [rsp+148h+var_D0], rcx
0x180025440  lea     rax, [rsp+148h+var_E8]
0x180025445  mov     [r11-0B0h], rax
0x18002544c  lea     rdx, [rsp+148h+var_E8]
0x180025451  lea     rcx, [r11-68h]
0x180025455  call    ??0?$ScopeGuardT@V?$function@$$A6AXXZ@std@@@mi@@QEAA@AEBV?$function@$$A6AXXZ@std@@@Z; mi::ScopeGuardT<std::function<void (void)>>::ScopeGuardT<std::function<void (void)>>(std::function<void (void)> const &)
0x18002545a  nop
0x18002545b  mov     rcx, [rsp+148h+var_B0]
0x180025463  test    rcx, rcx
0x180025466  jz      short loc_180025480
0x180025468  mov     rax, [rcx]
0x18002546b  lea     rdx, [rsp+148h+var_E8]
0x180025470  cmp     rcx, rdx
0x180025473  setnz   dl
0x180025476  mov     rax, [rax+20h]
0x18002547a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002547f  nop
0x180025480  lea     rdx, [rsp+148h+var_108]
0x180025485  mov     rcx, rdi
0x180025488  call    ?get_session@MiOperationArgs@MiAsyncOperation@mi@@QEBA?BV?$shared_ptr@$$CBVMiSession@mi@@@std@@XZ; mi::MiAsyncOperation::MiOperationArgs::get_session(void)
0x18002548d  mov     r10, rax
0x180025490  lea     rdx, [rsp+148h+var_118]
0x180025495  mov     rcx, rdi
0x180025498  call    ?get_application@MiOperationArgs@MiAsyncOperation@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiAsyncOperation::MiOperationArgs::get_application(void)
0x18002549d  xor     r9d, r9d
0x1800254a0  mov     r8, r10
0x1800254a3  mov     rdx, rax
0x1800254a6  lea     rcx, [rsp+148h+var_A8]
0x1800254ae  call    ??0MiInstance@mi@@AEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@3@_N@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,bool)
0x1800254b3  nop
0x1800254b4  mov     rcx, [rsp+148h+var_110]; this
0x1800254b9  test    rcx, rcx
0x1800254bc  jz      short loc_1800254C3
0x1800254be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800254c3  mov     rcx, [rsp+48h]; this
0x1800254c8  test    rcx, rcx
0x1800254cb  jz      short loc_1800254D2
0x1800254cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800254d2  test    rbx, rbx
0x1800254d5  jz      short loc_1800254E7
0x1800254d7  mov     rdx, rbx; struct _MI_Instance *
0x1800254da  lea     rcx, [rsp+148h+var_A8]; this
0x1800254e2  call    ?Attach@MiInstance@mi@@QEAAXPEBU_MI_Instance@@@Z; mi::MiInstance::Attach(_MI_Instance const *)
0x1800254e7  lea     rbx, [rdi+1C8h]
0x1800254ee  mov     [rsp+148h+var_118], rbx
0x1800254f3  mov     rcx, rbx; SRWLock
0x1800254f6  call    cs:__imp_AcquireSRWLockShared
0x1800254fc  nop
0x1800254fd  mov     rcx, [rdi+188h]
0x180025504  test    rcx, rcx
0x180025507  jz      short loc_18002551E
0x180025509  mov     rax, [rcx]
0x18002550c  lea     rdx, [rsp+148h+var_A8]
0x180025514  mov     rax, [rax+10h]
0x180025518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002551d  nop
0x18002551e  mov     rcx, rbx; SRWLock
0x180025521  call    cs:__imp_ReleaseSRWLockShared
0x180025527  nop
0x180025528  lea     rcx, [rsp+148h+var_A8]; this
0x180025530  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x180025535  nop
0x180025536  jmp     short $+2
0x180025538  lea     rcx, [rsp+148h+var_68]
0x180025540  call    ??1?$ScopeGuardT@V?$function@$$A6AXXZ@std@@@mi@@QEAA@XZ; mi::ScopeGuardT<std::function<void (void)>>::~ScopeGuardT<std::function<void (void)>>(void)
0x180025545  mov     rcx, [rsp+148h+var_18]
0x18002554d  xor     rcx, rsp; StackCookie
0x180025550  call    __security_check_cookie
0x180025555  mov     rbx, [rsp+148h+arg_18]
0x18002555d  add     rsp, 140h
0x180025564  pop     rdi
0x180025565  retn
```
