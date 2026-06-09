# ActionCollectionImpl::Create(_TASK_ACTION_TYPE,IAction * *)

- ea: `0x180028870`
- end: `0x180028b1a`
- name: `?Create@ActionCollectionImpl@@UEAAJW4_TASK_ACTION_TYPE@@PEAPEAUIAction@@@Z`
- size: `682`
- prototype: `__int64 __fastcall(ActionCollectionImpl *__hidden this, enum _TASK_ACTION_TYPE, struct IAction **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180028870`
- `0x180028b20`
- `0x180028cd0`
- `0x180028f1c`
- `0x180033ca8`
- `0x180043020`
- `0x18004307c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800288e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800288e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028940`

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
0x180028870  mov     [rsp+arg_0], rbx
0x180028875  mov     [rsp+arg_8], rsi
0x18002887a  mov     [rsp+arg_10], r8
0x18002887f  push    rdi
0x180028880  push    r12
0x180028882  push    r13
0x180028884  push    r14
0x180028886  push    r15
0x180028888  sub     rsp, 50h
0x18002888c  mov     r12, r8
0x18002888f  mov     ebx, edx
0x180028891  mov     r15, rcx
0x180028894  test    r8, r8
0x180028897  jnz     short loc_1800288B9
0x180028899  mov     eax, 80004003h
0x18002889e  lea     r11, [rsp+78h+var_28]
0x1800288a3  mov     rbx, [r11+30h]
0x1800288a7  mov     rsi, [r11+38h]
0x1800288ab  mov     rsp, r11
0x1800288ae  pop     r15
0x1800288b0  pop     r14
0x1800288b2  pop     r13
0x1800288b4  pop     r12
0x1800288b6  pop     rdi
0x1800288b7  retn
0x1800288b9  mov     [rsp+78h+arg_18], 0
0x1800288c4  xor     ecx, ecx
0x1800288c6  mov     [rsp+78h+var_48], rcx
0x1800288cb  mov     rax, r15
0x1800288ce  lea     rdx, [r15+20h]
0x1800288d2  neg     rax
0x1800288d5  sbb     r14, r14
0x1800288d8  and     r14, rdx
0x1800288db  jz      short loc_1800288F2
0x1800288dd  lea     rcx, [r14+8]; lpCriticalSection
0x1800288e1  call    cs:__imp_EnterCriticalSection
0x1800288e8  nop     dword ptr [rax+rax+00h]
0x1800288ed  mov     rcx, [rsp+78h+var_48]
0x1800288f2  mov     [rsp+78h+var_38], r14
0x1800288f7  test    ebx, ebx
0x1800288f9  jnz     loc_18002898B
0x1800288ff  lea     rcx, [rsp+78h+var_48]
0x180028904  call    ??$CreateComInstance@V?$ExecActionImpl@UIExecAction2@@$0A@@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<ExecActionImpl<IExecAction2,0>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x180028909  mov     ebx, eax
0x18002890b  mov     [rsp+78h+arg_18], eax
0x180028912  test    eax, eax
0x180028914  js      loc_180028B04
0x18002891a  mov     rdi, [rsp+78h+var_48]
0x18002891f  mov     r13, [r15+68h]
0x180028923  mov     rax, rdi
0x180028926  lea     rcx, [rdi+8]
0x18002892a  neg     rax
0x18002892d  sbb     rsi, rsi
0x180028930  and     rsi, rcx
0x180028933  jz      loc_180028AB6
0x180028939  lea     r12, [rsi+8]
0x18002893d  mov     rcx, r12; lpCriticalSection
0x180028940  call    cs:__imp_EnterCriticalSection
0x180028947  nop     dword ptr [rax+rax+00h]
0x18002894c  mov     rcx, [rdi+70h]
0x180028950  test    rcx, rcx
0x180028953  jnz     loc_180028AC1
0x180028959  mov     [rdi+70h], r13
0x18002895d  mov     rax, [r13+0]
0x180028961  mov     rcx, r13
0x180028964  mov     rax, [rax+8]
0x180028968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002896d  test    rsi, rsi
0x180028970  jz      short loc_180028981
0x180028972  mov     rcx, r12; lpCriticalSection
0x180028975  call    cs:__imp_LeaveCriticalSection
0x18002897c  nop     dword ptr [rax+rax+00h]
0x180028981  mov     r12, [rsp+78h+arg_10]
0x180028989  jmp     short loc_1800289AF
0x18002898b  sub     ebx, 5
0x18002898e  jnz     loc_180028A80
0x180028994  lea     rcx, [rsp+78h+var_48]
0x180028999  call    ??$CreateComInstance@V?$ComHandlerActionImpl@UIComHandlerAction@@$04@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<ComHandlerActionImpl<IComHandlerAction,5>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x18002899e  mov     ebx, eax
0x1800289a0  mov     [rsp+78h+arg_18], eax
0x1800289a7  test    eax, eax
0x1800289a9  js      loc_180028B04
0x1800289af  lea     rdi, [r15+8]
0x1800289b3  mov     rsi, [rsp+78h+var_48]
0x1800289b8  mov     [rsp+78h+var_40], rsi
0x1800289bd  test    rsi, rsi
0x1800289c0  jz      short loc_1800289D2
0x1800289c2  mov     rax, [rsi]
0x1800289c5  mov     rcx, rsi
0x1800289c8  mov     rax, [rax+8]
0x1800289cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289d1  nop
0x1800289d2  lea     rax, [rsp+78h+var_40]
0x1800289d7  cmp     rax, [rdi+8]
0x1800289db  jb      loc_180028A6B
0x1800289e1  xor     al, al
0x1800289e3  mov     rcx, [rdi+10h]
0x1800289e7  test    al, al
0x1800289e9  jnz     loc_180028AD2
0x1800289ef  cmp     [rdi+8], rcx
0x1800289f3  jnz     short loc_1800289FD
0x1800289f5  mov     rcx, rdi
0x1800289f8  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<IAction>>>::_Reserve(unsigned __int64)
0x1800289fd  mov     rax, [rdi+8]
0x180028a01  mov     [rax], rsi
0x180028a04  test    rsi, rsi
0x180028a07  jz      short loc_180028A19
0x180028a09  mov     rax, [rsi]
0x180028a0c  mov     rcx, rsi
0x180028a0f  mov     rax, [rax+8]
0x180028a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a18  nop
0x180028a19  add     qword ptr [rdi+8], 8
0x180028a1e  lea     rcx, [rsp+78h+var_40]
0x180028a23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028a28  mov     rax, [rsp+78h+var_48]
0x180028a2d  xor     ecx, ecx
0x180028a2f  mov     [rsp+78h+var_48], rcx
0x180028a34  mov     [r12], rax
0x180028a38  test    r14, r14
0x180028a3b  jz      short loc_180028A52
0x180028a3d  lea     rcx, [r14+8]; lpCriticalSection
0x180028a41  call    cs:__imp_LeaveCriticalSection
0x180028a48  nop     dword ptr [rax+rax+00h]
0x180028a4d  mov     rcx, [rsp+78h+var_48]
0x180028a52  test    rcx, rcx
0x180028a55  jz      short loc_180028A64
0x180028a57  mov     rax, [rcx]
0x180028a5a  mov     rax, [rax+10h]
0x180028a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a63  nop
0x180028a64  mov     eax, ebx
0x180028a66  jmp     loc_18002889E
0x180028a6b  lea     rax, [rsp+78h+var_40]
0x180028a70  cmp     [rdi], rax
0x180028a73  ja      loc_1800289E1
0x180028a79  mov     al, 1
0x180028a7b  jmp     loc_1800289E3
0x180028a80  sub     ebx, 1
0x180028a83  jz      short loc_180028AA7
0x180028a85  cmp     ebx, 1
0x180028a88  jz      short loc_180028A98
0x180028a8a  mov     ebx, 80070057h
0x180028a8f  mov     [rsp+78h+arg_18], ebx
0x180028a96  jmp     short loc_180028A38
0x180028a98  lea     rcx, [rsp+78h+var_48]
0x180028a9d  call    ??$CreateComInstance@V?$ShowMessageActionImpl@UIShowMessageAction@@$06@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<ShowMessageActionImpl<IShowMessageAction,7>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x180028aa2  jmp     loc_18002899E
0x180028aa7  lea     rcx, [rsp+78h+var_48]
0x180028aac  call    ??$CreateComInstance@V?$EmailActionImpl@UIEmailAction@@$05@@V?$CComPtr@UIAction@@@ATL@@@@YAJAEAV?$CComPtr@UIAction@@@ATL@@@Z; CreateComInstance<EmailActionImpl<IEmailAction,6>,ATL::CComPtr<IAction>>(ATL::CComPtr<IAction> &)
0x180028ab1  jmp     loc_18002899E
0x180028ab6  mov     r12d, 8
0x180028abc  jmp     loc_18002894C
0x180028ac1  mov     rax, [rcx]
0x180028ac4  mov     rax, [rax+10h]
0x180028ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028acd  jmp     loc_180028959
0x180028ad2  mov     rsi, [rdi]
0x180028ad5  cmp     [rdi+8], rcx
0x180028ad9  jnz     short loc_180028AE3
0x180028adb  mov     rcx, rdi
0x180028ade  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<IAction>>>::_Reserve(unsigned __int64)
0x180028ae3  lea     rcx, [rsp+78h+var_40]
0x180028ae8  sub     rcx, rsi
0x180028aeb  sar     rcx, 3
0x180028aef  mov     rax, [rdi]
0x180028af2  lea     r8, [rax+rcx*8]
0x180028af6  mov     rdx, [rdi+8]
0x180028afa  call    ??$construct@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V12@@?$_Wrap_alloc@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAV?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@$$QEAV23@@Z; std::_Wrap_alloc<std::allocator<ATL::CAdapt<ATL::CComPtr<IAction>>>>::construct<ATL::CAdapt<ATL::CComPtr<IAction>>,ATL::CAdapt<ATL::CComPtr<IAction>>>(ATL::CAdapt<ATL::CComPtr<IAction>> *,ATL::CAdapt<ATL::CComPtr<IAction>> &&)
0x180028aff  jmp     loc_180028A19
0x180028b04  mov     rcx, [rsp+78h+var_48]
0x180028b09  jmp     loc_180028A38
0x180028b0e  mov     ebx, [rsp+78h+arg_18]
0x180028b15  jmp     loc_180028A64
```
