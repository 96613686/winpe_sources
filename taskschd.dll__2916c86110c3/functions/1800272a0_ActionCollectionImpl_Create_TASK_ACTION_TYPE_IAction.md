# ActionCollectionImpl::Create(_TASK_ACTION_TYPE,IAction * *)

- ea: `0x1800272a0`
- end: `0x180027531`
- name: `?Create@ActionCollectionImpl@@UEAAJW4_TASK_ACTION_TYPE@@PEAPEAUIAction@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(ActionCollectionImpl *__hidden this, enum _TASK_ACTION_TYPE, struct IAction **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x1800272a0`
- `0x180027538`
- `0x1800276e0`
- `0x18002790c`
- `0x1800314f4`
- `0x18003fa50`
- `0x18003faac`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002745e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002745e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027310`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027369`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027310`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027369`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ActionCollectionImpl::Create(
        ActionCollectionImpl *this,
        enum _TASK_ACTION_TYPE a2,
        struct IAction **a3)
{
  struct IAction **v3; // r12
  __int64 v7; // rcx
  unsigned __int64 v8; // r14
  int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // r13
  __int64 v12; // rsi
  __int64 v13; // r12
  __int64 v14; // rcx
  int v15; // ebx
  int v16; // eax
  __int64 *v17; // rdi
  __int64 v18; // rsi
  bool v19; // al
  __int64 v20; // rcx
  struct IAction *v21; // rax
  int v22; // ebx
  __int64 v23; // rsi
  __int64 v24; // [rsp+30h] [rbp-48h] BYREF
  __int64 v25[3]; // [rsp+38h] [rbp-40h] BYREF

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  v7 = 0;
  v24 = 0;
  v8 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  if ( v8 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    v7 = v24;
  }
  v25[1] = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  if ( a2 == TASK_ACTION_EXEC )
  {
    v9 = CreateComInstance<ExecActionImpl<IExecAction2,0>,ATL::CComPtr<IAction>>(&v24);
    if ( v9 >= 0 )
    {
      v10 = v24;
      v11 = *((_QWORD *)this + 13);
      v12 = (v24 + 8) & -(__int64)(v24 != 0);
      if ( v12 )
      {
        v13 = v12 + 8;
        EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
      }
      else
      {
        v13 = 8;
      }
      v14 = *(_QWORD *)(v10 + 112);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *(_QWORD *)(v10 + 112) = v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      if ( v12 )
        LeaveCriticalSection((LPCRITICAL_SECTION)v13);
      v3 = a3;
      goto LABEL_17;
    }
LABEL_43:
    v7 = v24;
    goto LABEL_27;
  }
  v15 = a2 - 5;
  if ( !v15 )
  {
    v16 = CreateComInstance<ComHandlerActionImpl<IComHandlerAction,5>,ATL::CComPtr<IAction>>(&v24);
    goto LABEL_16;
  }
  v22 = v15 - 1;
  if ( !v22 )
  {
    v16 = CreateComInstance<EmailActionImpl<IEmailAction,6>,ATL::CComPtr<IAction>>(&v24);
LABEL_16:
    v9 = v16;
    if ( v16 >= 0 )
    {
LABEL_17:
      v17 = (__int64 *)((char *)this + 8);
      v18 = v24;
      v25[0] = v24;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      v19 = (unsigned __int64)v25 < *((_QWORD *)this + 2) && *v17 <= (unsigned __int64)v25;
      v20 = *((_QWORD *)this + 3);
      if ( v19 )
      {
        v23 = *v17;
        if ( *((_QWORD *)this + 2) == v20 )
          std::vector<ATL::CAdapt<ATL::CComPtr<IAction>>>::_Reserve((char *)this + 8);
        std::_Wrap_alloc<std::allocator<ATL::CAdapt<ATL::CComPtr<IAction>>>>::construct<ATL::CAdapt<ATL::CComPtr<IAction>>,ATL::CAdapt<ATL::CComPtr<IAction>>>(
          ((__int64)v25 - v23) >> 3,
          *((_QWORD *)this + 2),
          *v17 + 8 * (((__int64)v25 - v23) >> 3));
      }
      else
      {
        if ( *((_QWORD *)this + 2) == v20 )
          std::vector<ATL::CAdapt<ATL::CComPtr<IAction>>>::_Reserve(v17);
        **((_QWORD **)this + 2) = v18;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      }
      *((_QWORD *)this + 2) += 8LL;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
      v21 = (struct IAction *)v24;
      v7 = 0;
      v24 = 0;
      *v3 = v21;
      goto LABEL_27;
    }
    goto LABEL_43;
  }
  if ( v22 == 1 )
  {
    v16 = CreateComInstance<ShowMessageActionImpl<IShowMessageAction,7>,ATL::CComPtr<IAction>>(&v24);
    goto LABEL_16;
  }
  v9 = -2147024809;
LABEL_27:
  if ( v8 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    v7 = v24;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800272a0  mov     [rsp+arg_0], rbx
0x1800272a5  mov     [rsp+arg_8], rsi
0x1800272aa  mov     [rsp+arg_10], r8
0x1800272af  push    rdi
0x1800272b0  push    r12
0x1800272b2  push    r13
0x1800272b4  push    r14
0x1800272b6  push    r15
0x1800272b8  sub     rsp, 50h
0x1800272bc  mov     r12, r8
0x1800272bf  mov     ebx, edx
0x1800272c1  mov     r15, rcx
0x1800272c4  test    r8, r8
0x1800272c7  jnz     short loc_1800272E8
0x1800272c9  mov     eax, 80004003h
0x1800272ce  lea     r11, [rsp+78h+var_28]
0x1800272d3  mov     rbx, [r11+30h]
0x1800272d7  mov     rsi, [r11+38h]
0x1800272db  mov     rsp, r11
0x1800272de  pop     r15
0x1800272e0  pop     r14
0x1800272e2  pop     r13
0x1800272e4  pop     r12
0x1800272e6  pop     rdi
0x1800272e7  retn
0x1800272e8  mov     [rsp+78h+arg_18], 0
0x1800272f3  xor     ecx, ecx
0x1800272f5  mov     [rsp+78h+var_48], rcx
0x1800272fa  mov     rax, r15
0x1800272fd  lea     rdx, [r15+20h]
0x180027301  neg     rax
0x180027304  sbb     r14, r14
0x180027307  and     r14, rdx
0x18002730a  jz      short loc_18002731B
0x18002730c  lea     rcx, [r14+8]; lpCriticalSection
0x180027310  call    cs:__imp_EnterCriticalSection
0x180027316  mov     rcx, [rsp+78h+var_48]
0x18002731b  mov     [rsp+78h+var_38], r14
0x180027320  test    ebx, ebx
0x180027322  jnz     loc_1800273A8
0x180027328  lea     rcx, [rsp+78h+var_48]
0x18002732d  call    ??$CreateComInstance@V?$ExecActionImpl@UIExecAction2@@$0A@@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<ExecActionImpl<IExecAction2,0>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x180027332  mov     ebx, eax
0x180027334  mov     [rsp+78h+arg_18], eax
0x18002733b  test    eax, eax
0x18002733d  js      loc_18002751B
0x180027343  mov     rdi, [rsp+78h+var_48]
0x180027348  mov     r13, [r15+68h]
0x18002734c  mov     rax, rdi
0x18002734f  lea     rcx, [rdi+8]
0x180027353  neg     rax
0x180027356  sbb     rsi, rsi
0x180027359  and     rsi, rcx
0x18002735c  jz      loc_1800274CD
0x180027362  lea     r12, [rsi+8]
0x180027366  mov     rcx, r12; lpCriticalSection
0x180027369  call    cs:__imp_EnterCriticalSection
0x18002736f  mov     rcx, [rdi+70h]
0x180027373  test    rcx, rcx
0x180027376  jnz     loc_1800274D8
0x18002737c  mov     [rdi+70h], r13
0x180027380  mov     rax, [r13+0]
0x180027384  mov     rcx, r13
0x180027387  mov     rax, [rax+8]
0x18002738b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027390  test    rsi, rsi
0x180027393  jz      short loc_18002739E
0x180027395  mov     rcx, r12; lpCriticalSection
0x180027398  call    cs:__imp_LeaveCriticalSection
0x18002739e  mov     r12, [rsp+78h+arg_10]
0x1800273a6  jmp     short loc_1800273CC
0x1800273a8  sub     ebx, 5
0x1800273ab  jnz     loc_180027497
0x1800273b1  lea     rcx, [rsp+78h+var_48]
0x1800273b6  call    ??$CreateComInstance@V?$ComHandlerActionImpl@UIComHandlerAction@@$04@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<ComHandlerActionImpl<IComHandlerAction,5>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x1800273bb  mov     ebx, eax
0x1800273bd  mov     [rsp+78h+arg_18], eax
0x1800273c4  test    eax, eax
0x1800273c6  js      loc_18002751B
0x1800273cc  lea     rdi, [r15+8]
0x1800273d0  mov     rsi, [rsp+78h+var_48]
0x1800273d5  mov     [rsp+78h+var_40], rsi
0x1800273da  test    rsi, rsi
0x1800273dd  jz      short loc_1800273EF
0x1800273df  mov     rax, [rsi]
0x1800273e2  mov     rcx, rsi
0x1800273e5  mov     rax, [rax+8]
0x1800273e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273ee  nop
0x1800273ef  lea     rax, [rsp+78h+var_40]
0x1800273f4  cmp     rax, [rdi+8]
0x1800273f8  jb      loc_180027482
0x1800273fe  xor     al, al
0x180027400  mov     rcx, [rdi+10h]
0x180027404  test    al, al
0x180027406  jnz     loc_1800274E9
0x18002740c  cmp     [rdi+8], rcx
0x180027410  jnz     short loc_18002741A
0x180027412  mov     rcx, rdi
0x180027415  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<IAction>>>::_Reserve(unsigned __int64)
0x18002741a  mov     rax, [rdi+8]
0x18002741e  mov     [rax], rsi
0x180027421  test    rsi, rsi
0x180027424  jz      short loc_180027436
0x180027426  mov     rax, [rsi]
0x180027429  mov     rcx, rsi
0x18002742c  mov     rax, [rax+8]
0x180027430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027435  nop
0x180027436  add     qword ptr [rdi+8], 8
0x18002743b  lea     rcx, [rsp+78h+var_40]
0x180027440  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027445  mov     rax, [rsp+78h+var_48]
0x18002744a  xor     ecx, ecx
0x18002744c  mov     [rsp+78h+var_48], rcx
0x180027451  mov     [r12], rax
0x180027455  test    r14, r14
0x180027458  jz      short loc_180027469
0x18002745a  lea     rcx, [r14+8]; lpCriticalSection
0x18002745e  call    cs:__imp_LeaveCriticalSection
0x180027464  mov     rcx, [rsp+78h+var_48]
0x180027469  test    rcx, rcx
0x18002746c  jz      short loc_18002747B
0x18002746e  mov     rax, [rcx]
0x180027471  mov     rax, [rax+10h]
0x180027475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002747a  nop
0x18002747b  mov     eax, ebx
0x18002747d  jmp     loc_1800272CE
0x180027482  lea     rax, [rsp+78h+var_40]
0x180027487  cmp     [rdi], rax
0x18002748a  ja      loc_1800273FE
0x180027490  mov     al, 1
0x180027492  jmp     loc_180027400
0x180027497  sub     ebx, 1
0x18002749a  jz      short loc_1800274BE
0x18002749c  cmp     ebx, 1
0x18002749f  jz      short loc_1800274AF
0x1800274a1  mov     ebx, 80070057h
0x1800274a6  mov     [rsp+78h+arg_18], ebx
0x1800274ad  jmp     short loc_180027455
0x1800274af  lea     rcx, [rsp+78h+var_48]
0x1800274b4  call    ??$CreateComInstance@V?$ShowMessageActionImpl@UIShowMessageAction@@$06@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<ShowMessageActionImpl<IShowMessageAction,7>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x1800274b9  jmp     loc_1800273BB
0x1800274be  lea     rcx, [rsp+78h+var_48]
0x1800274c3  call    ??$CreateComInstance@V?$EmailActionImpl@UIEmailAction@@$05@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<EmailActionImpl<IEmailAction,6>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x1800274c8  jmp     loc_1800273BB
0x1800274cd  mov     r12d, 8
0x1800274d3  jmp     loc_18002736F
0x1800274d8  mov     rax, [rcx]
0x1800274db  mov     rax, [rax+10h]
0x1800274df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274e4  jmp     loc_18002737C
0x1800274e9  mov     rsi, [rdi]
0x1800274ec  cmp     [rdi+8], rcx
0x1800274f0  jnz     short loc_1800274FA
0x1800274f2  mov     rcx, rdi
0x1800274f5  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<IAction>>>::_Reserve(unsigned __int64)
0x1800274fa  lea     rcx, [rsp+78h+var_40]
0x1800274ff  sub     rcx, rsi
0x180027502  sar     rcx, 3
0x180027506  mov     rax, [rdi]
0x180027509  lea     r8, [rax+rcx*8]
0x18002750d  mov     rdx, [rdi+8]
0x180027511  call    ??$construct@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V12@@?$_Wrap_alloc@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAV?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@$$QEAV23@@Z; std::_Wrap_alloc<std::allocator<ATL::CAdapt<ATL::CComPtr<IAction>>>>::construct<ATL::CAdapt<ATL::CComPtr<IAction>>,ATL::CAdapt<ATL::CComPtr<IAction>>>(ATL::CAdapt<ATL::CComPtr<IAction>> *,ATL::CAdapt<ATL::CComPtr<IAction>> &&)
0x180027516  jmp     loc_180027436
0x18002751b  mov     rcx, [rsp+78h+var_48]
0x180027520  jmp     loc_180027455
0x180027525  mov     ebx, [rsp+78h+arg_18]
0x18002752c  jmp     loc_18002747B
```
