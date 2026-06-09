# TriggerCollectionImpl::Create(_TASK_TRIGGER_TYPE2,ITrigger * *)

- ea: `0x180026e20`
- end: `0x1800271b0`
- name: `?Create@TriggerCollectionImpl@@UEAAJW4_TASK_TRIGGER_TYPE2@@PEAPEAUITrigger@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(TriggerCollectionImpl *__hidden this, enum _TASK_TRIGGER_TYPE2, struct ITrigger **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180026e20`
- `0x1800271b8`
- `0x180027284`
- `0x180027340`
- `0x1800273c8`
- `0x180027494`
- `0x1800275cc`
- `0x180027750`
- `0x1800277ec`
- `0x180027980`
- `0x180027c74`
- `0x180027d98`
- `0x1800280b8`
- `0x180033ca8`
- `0x180038a80`
- `0x180044f58`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TriggerCollectionImpl::Create(
        TaskSettingsImpl **this,
        enum _TASK_TRIGGER_TYPE2 a2,
        struct ITrigger **a3)
{
  _QWORD *v6; // rcx
  char *v7; // rbx
  int v8; // eax
  int v9; // edi
  int v10; // eax
  __int64 *v12; // r14
  __int64 v13; // rsi
  unsigned __int64 v14; // rax
  struct ITrigger *v15; // rax
  __int64 v16; // rsi
  __int64 v17[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  int v19; // [rsp+78h] [rbp+10h]
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+20h] BYREF

  v19 = 0;
  v6 = 0;
  v18 = 0;
  v7 = (char *)(this + 4);
  if ( !this )
    v7 = 0;
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
    v6 = (_QWORD *)v18;
  }
  v17[1] = (__int64)v7;
  switch ( a2 )
  {
    case TASK_TRIGGER_BOOT:
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      v20 = 0;
      v8 = ATL::CComObject<BootTriggerImpl<IBootTrigger,8>>::CreateInstance(&v20);
      break;
    case TASK_TRIGGER_LOGON:
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      v20 = 0;
      v8 = ATL::CComObject<LogonTriggerImpl<ILogonTrigger,9>>::CreateInstance(&v20);
      break;
    case TASK_TRIGGER_TIME:
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      v20 = 0;
      v8 = ATL::CComObject<TimeTriggerImpl<ITimeTrigger,1>>::CreateInstance(&v20);
      break;
    default:
      if ( a2 )
      {
        switch ( a2 )
        {
          case TASK_TRIGGER_DAILY:
            v10 = CreateComInstance<DailyTriggerImpl<IDailyTrigger,2>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_WEEKLY:
            v10 = CreateComInstance<WeeklyTriggerImpl<IWeeklyTrigger,3>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_MONTHLY:
            v10 = CreateComInstance<MonthlyTriggerImpl<IMonthlyTrigger,4>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_MONTHLYDOW:
            v10 = CreateComInstance<MonthlyDOWTriggerImpl<IMonthlyDOWTrigger,5>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_IDLE:
            v10 = CreateComInstance<IdleTriggerImpl<IIdleTrigger,6>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_REGISTRATION:
            v10 = CreateComInstance<RegistrationTriggerImpl<IRegistrationTrigger,7>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_SESSION_STATE_CHANGE:
            v10 = CreateComInstance<SessionStateChangeTriggerImpl<ISessionStateChangeTrigger,11>,ATL::CComPtr<ITrigger>>(&v18);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          case TASK_TRIGGER_CUSTOM_TRIGGER_01:
            v9 = CreateComInstance<WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>,ATL::CComPtr<ITrigger>>(&v18);
            v19 = v9;
            if ( v9 < 0 )
              goto LABEL_17;
            v10 = TaskSettingsImpl::LevelUpCompatibility(this[11], TASK_COMPATIBILITY_V2_2);
            v9 = v10;
            v19 = v10;
            goto LABEL_16;
          default:
            v9 = -2147024809;
            v19 = -2147024809;
            goto LABEL_18;
        }
      }
      if ( v6 )
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      v20 = 0;
      v8 = ATL::CComObject<EventTriggerImpl<IEventTrigger,0>>::CreateInstance(&v20);
      break;
  }
  v9 = v8;
  if ( v8 >= 0 )
    v9 = (**v20)(v20, &GUID_09941815_ea89_4b5b_89e0_2a773801fac3, &v18);
  v10 = v9;
  v19 = v9;
LABEL_16:
  if ( v10 < 0 )
    goto LABEL_17;
  v12 = (__int64 *)(this + 1);
  v13 = v18;
  v17[0] = v18;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  v14 = v12[1];
  if ( (unsigned __int64)v17 >= v14 || *v12 > (unsigned __int64)v17 )
  {
    if ( v14 == v12[2] )
      std::vector<ATL::CAdapt<ATL::CComPtr<ITrigger>>>::_Reserve(v12);
    *(_QWORD *)v12[1] = v13;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
  else
  {
    v16 = *v12;
    if ( v14 == v12[2] )
      std::vector<ATL::CAdapt<ATL::CComPtr<ITrigger>>>::_Reserve(v12);
    std::_Wrap_alloc<std::allocator<ATL::CAdapt<ATL::CComPtr<IAction>>>>::construct<ATL::CAdapt<ATL::CComPtr<IAction>>,ATL::CAdapt<ATL::CComPtr<IAction>>>(
      ((__int64)v17 - v16) >> 3,
      v12[1],
      *v12 + 8 * (((__int64)v17 - v16) >> 3));
  }
  v12[1] += 8;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v17);
  if ( a3 )
  {
    v15 = (struct ITrigger *)v18;
    v6 = 0;
    v18 = 0;
    *a3 = v15;
  }
  else
  {
LABEL_17:
    v6 = (_QWORD *)v18;
  }
LABEL_18:
  if ( v7 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
    v6 = (_QWORD *)v18;
  }
  if ( v6 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v6 + 16LL))(v6, *v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026e20  mov     [rsp+arg_10], rbx
0x180026e25  push    rsi
0x180026e26  push    rdi
0x180026e27  push    r12
0x180026e29  push    r14
0x180026e2b  push    r15
0x180026e2d  sub     rsp, 40h
0x180026e31  mov     r15, r8
0x180026e34  mov     edi, edx
0x180026e36  mov     rsi, rcx
0x180026e39  xor     r12d, r12d
0x180026e3c  mov     [rsp+68h+arg_8], r12d
0x180026e41  mov     ecx, r12d
0x180026e44  mov     [rsp+68h+arg_0], rcx
0x180026e49  lea     rbx, [rsi+20h]
0x180026e4d  test    rsi, rsi
0x180026e50  cmovz   rbx, r12
0x180026e54  test    rbx, rbx
0x180026e57  jz      short loc_180026E6E
0x180026e59  lea     rcx, [rbx+8]; lpCriticalSection
0x180026e5d  call    cs:__imp_EnterCriticalSection
0x180026e64  nop     dword ptr [rax+rax+00h]
0x180026e69  mov     rcx, [rsp+68h+arg_0]
0x180026e6e  mov     [rsp+68h+var_30], rbx
0x180026e73  cmp     edi, 8
0x180026e76  jz      short loc_180026EB9
0x180026e78  cmp     edi, 9
0x180026e7b  jz      loc_180026F59
0x180026e81  cmp     edi, 1
0x180026e84  jz      loc_180027010
0x180026e8a  test    edi, edi
0x180026e8c  jz      loc_180027050
0x180026e92  add     edi, 0FFFFFFFEh; switch 11 cases
0x180026e95  cmp     edi, 0Ah
0x180026e98  ja      def_180026EB3; jumptable 0000000180026EB3 default case, cases 8-10
0x180026e9e  movsxd  rax, edi
0x180026ea1  lea     r8, __ImageBase
0x180026ea8  mov     edx, ds:(jpt_180026EB3 - 180000000h)[r8+rax*4]
0x180026eb0  add     rdx, r8
0x180026eb3  jmp     rdx; switch jump
0x180026eb9  test    rcx, rcx
0x180026ebc  jz      short loc_180026ECA
0x180026ebe  mov     rax, [rcx]
0x180026ec1  mov     rax, [rax+10h]
0x180026ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026eca  mov     [rsp+68h+arg_18], r12
0x180026ed2  lea     rcx, [rsp+68h+arg_18]
0x180026eda  call    ?CreateInstance@?$CComObject@V?$BootTriggerImpl@UIBootTrigger@@$07@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<BootTriggerImpl<IBootTrigger,8>>::CreateInstance(ATL::CComObject<BootTriggerImpl<IBootTrigger,8>> * *)
0x180026edf  test    eax, eax
0x180026ee1  mov     edi, eax
0x180026ee3  js      short loc_180026F06
0x180026ee5  mov     rcx, [rsp+68h+arg_18]
0x180026eed  mov     rax, [rcx]
0x180026ef0  lea     r8, [rsp+68h+arg_0]
0x180026ef5  lea     rdx, _GUID_09941815_ea89_4b5b_89e0_2a773801fac3
0x180026efc  mov     rax, [rax]
0x180026eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f04  mov     edi, eax
0x180026f06  mov     eax, edi
0x180026f08  mov     [rsp+68h+arg_8], edi
0x180026f0c  test    eax, eax
0x180026f0e  jns     short loc_180026F84
0x180026f10  mov     rcx, [rsp+68h+arg_0]
0x180026f15  test    rbx, rbx
0x180026f18  jz      short loc_180026F2F
0x180026f1a  lea     rcx, [rbx+8]; lpCriticalSection
0x180026f1e  call    cs:__imp_LeaveCriticalSection
0x180026f25  nop     dword ptr [rax+rax+00h]
0x180026f2a  mov     rcx, [rsp+68h+arg_0]
0x180026f2f  test    rcx, rcx
0x180026f32  jz      short loc_180026F41
0x180026f34  mov     rdx, [rcx]
0x180026f37  mov     rax, [rdx+10h]
0x180026f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f40  nop
0x180026f41  mov     eax, edi
0x180026f43  mov     rbx, [rsp+68h+arg_10]
0x180026f4b  add     rsp, 40h
0x180026f4f  pop     r15
0x180026f51  pop     r14
0x180026f53  pop     r12
0x180026f55  pop     rdi
0x180026f56  pop     rsi
0x180026f57  retn
0x180026f59  test    rcx, rcx
0x180026f5c  jz      short loc_180026F6A
0x180026f5e  mov     rax, [rcx]
0x180026f61  mov     rax, [rax+10h]
0x180026f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f6a  mov     [rsp+68h+arg_18], r12
0x180026f72  lea     rcx, [rsp+68h+arg_18]
0x180026f7a  call    ?CreateInstance@?$CComObject@V?$LogonTriggerImpl@UILogonTrigger@@$08@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<LogonTriggerImpl<ILogonTrigger,9>>::CreateInstance(ATL::CComObject<LogonTriggerImpl<ILogonTrigger,9>> * *)
0x180026f7f  jmp     loc_180026EDF
0x180026f84  lea     r14, [rsi+8]
0x180026f88  mov     rsi, [rsp+68h+arg_0]
0x180026f8d  mov     [rsp+68h+var_38], rsi
0x180026f92  test    rsi, rsi
0x180026f95  jz      short loc_180026FA7
0x180026f97  mov     rax, [rsi]
0x180026f9a  mov     rcx, rsi
0x180026f9d  mov     rax, [rax+8]
0x180026fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa6  nop
0x180026fa7  mov     rax, [r14+8]
0x180026fab  lea     rcx, [rsp+68h+var_38]
0x180026fb0  cmp     rcx, rax
0x180026fb3  jb      loc_18002707B
0x180026fb9  cmp     rax, [r14+10h]
0x180026fbd  jnz     short loc_180026FC7
0x180026fbf  mov     rcx, r14
0x180026fc2  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<ITrigger>>>::_Reserve(unsigned __int64)
0x180026fc7  mov     rax, [r14+8]
0x180026fcb  mov     [rax], rsi
0x180026fce  test    rsi, rsi
0x180026fd1  jz      short loc_180026FE3
0x180026fd3  mov     rax, [rsi]
0x180026fd6  mov     rcx, rsi
0x180026fd9  mov     rax, [rax+8]
0x180026fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fe2  nop
0x180026fe3  add     qword ptr [r14+8], 8
0x180026fe8  lea     rcx, [rsp+68h+var_38]
0x180026fed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180026ff2  test    r15, r15
0x180026ff5  jz      loc_180026F10
0x180026ffb  mov     rax, [rsp+68h+arg_0]
0x180027000  mov     rcx, r12
0x180027003  mov     [rsp+68h+arg_0], rcx
0x180027008  mov     [r15], rax
0x18002700b  jmp     loc_180026F15
0x180027010  test    rcx, rcx
0x180027013  jz      short loc_180027021
0x180027015  mov     rax, [rcx]
0x180027018  mov     rax, [rax+10h]
0x18002701c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027021  mov     [rsp+68h+arg_18], r12
0x180027029  lea     rcx, [rsp+68h+arg_18]
0x180027031  call    ?CreateInstance@?$CComObject@V?$TimeTriggerImpl@UITimeTrigger@@$00@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TimeTriggerImpl<ITimeTrigger,1>>::CreateInstance(ATL::CComObject<TimeTriggerImpl<ITimeTrigger,1>> * *)
0x180027036  jmp     loc_180026EDF
0x18002703b  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 6
0x180027040  call    ??$CreateComInstance@V?$IdleTriggerImpl@UIIdleTrigger@@$05@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<IdleTriggerImpl<IIdleTrigger,6>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x180027045  mov     edi, eax
0x180027047  mov     [rsp+68h+arg_8], eax
0x18002704b  jmp     loc_180026F0C
0x180027050  test    rcx, rcx
0x180027053  jz      short loc_180027061
0x180027055  mov     rax, [rcx]
0x180027058  mov     rax, [rax+10h]
0x18002705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027061  mov     [rsp+68h+arg_18], r12
0x180027069  lea     rcx, [rsp+68h+arg_18]
0x180027071  call    ?CreateInstance@?$CComObject@V?$EventTriggerImpl@UIEventTrigger@@$0A@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<EventTriggerImpl<IEventTrigger,0>>::CreateInstance(ATL::CComObject<EventTriggerImpl<IEventTrigger,0>> * *)
0x180027076  jmp     loc_180026EDF
0x18002707b  lea     rcx, [rsp+68h+var_38]
0x180027080  cmp     [r14], rcx
0x180027083  ja      loc_180026FB9
0x180027089  mov     rsi, [r14]
0x18002708c  cmp     rax, [r14+10h]
0x180027090  jnz     short loc_18002709A
0x180027092  mov     rcx, r14
0x180027095  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<ITrigger>>>::_Reserve(unsigned __int64)
0x18002709a  lea     rcx, [rsp+68h+var_38]
0x18002709f  sub     rcx, rsi
0x1800270a2  sar     rcx, 3
0x1800270a6  mov     rax, [r14]
0x1800270a9  lea     r8, [rax+rcx*8]
0x1800270ad  mov     rdx, [r14+8]
0x1800270b1  call    ??$construct@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V12@@?$_Wrap_alloc@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAV?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@$$QEAV23@@Z; std::_Wrap_alloc<std::allocator<ATL::CAdapt<ATL::CComPtr<IAction>>>>::construct<ATL::CAdapt<ATL::CComPtr<IAction>>,ATL::CAdapt<ATL::CComPtr<IAction>>>(ATL::CAdapt<ATL::CComPtr<IAction>> *,ATL::CAdapt<ATL::CComPtr<IAction>> &&)
0x1800270b6  jmp     loc_180026FE3
0x1800270bb  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 2
0x1800270c0  call    ??$CreateComInstance@V?$DailyTriggerImpl@UIDailyTrigger@@$01@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<DailyTriggerImpl<IDailyTrigger,2>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x1800270c5  mov     edi, eax
0x1800270c7  mov     [rsp+68h+arg_8], eax
0x1800270cb  jmp     loc_180026F0C
0x1800270d0  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 12
0x1800270d5  call    ??$CreateComInstance@V?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x1800270da  mov     edi, eax
0x1800270dc  mov     [rsp+68h+arg_8], eax
0x1800270e0  test    eax, eax
0x1800270e2  js      loc_180026F10
0x1800270e8  mov     edx, 4; enum _TASK_COMPATIBILITY
0x1800270ed  mov     rcx, [rsi+58h]; this
0x1800270f1  call    ?LevelUpCompatibility@TaskSettingsImpl@@QEAAJW4_TASK_COMPATIBILITY@@@Z; TaskSettingsImpl::LevelUpCompatibility(_TASK_COMPATIBILITY)
0x1800270f6  mov     edi, eax
0x1800270f8  mov     [rsp+68h+arg_8], eax
0x1800270fc  jmp     loc_180026F0C
0x180027101  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 3
0x180027106  call    ??$CreateComInstance@V?$WeeklyTriggerImpl@UIWeeklyTrigger@@$02@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<WeeklyTriggerImpl<IWeeklyTrigger,3>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x18002710b  mov     edi, eax
0x18002710d  mov     [rsp+68h+arg_8], eax
0x180027111  jmp     loc_180026F0C
0x180027116  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 11
0x18002711b  call    ??$CreateComInstance@V?$SessionStateChangeTriggerImpl@UISessionStateChangeTrigger@@$0L@@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<SessionStateChangeTriggerImpl<ISessionStateChangeTrigger,11>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x180027120  mov     edi, eax
0x180027122  mov     [rsp+68h+arg_8], eax
0x180027126  jmp     loc_180026F0C
0x18002712b  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 7
0x180027130  call    ??$CreateComInstance@V?$RegistrationTriggerImpl@UIRegistrationTrigger@@$06@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<RegistrationTriggerImpl<IRegistrationTrigger,7>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x180027135  mov     edi, eax
0x180027137  mov     [rsp+68h+arg_8], eax
0x18002713b  jmp     loc_180026F0C
0x180027140  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 4
0x180027145  call    ??$CreateComInstance@V?$MonthlyTriggerImpl@UIMonthlyTrigger@@$03@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<MonthlyTriggerImpl<IMonthlyTrigger,4>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x18002714a  mov     edi, eax
0x18002714c  mov     [rsp+68h+arg_8], eax
0x180027150  jmp     loc_180026F0C
0x180027155  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180026EB3 case 5
0x18002715a  call    ??$CreateComInstance@V?$MonthlyDOWTriggerImpl@UIMonthlyDOWTrigger@@$04@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<MonthlyDOWTriggerImpl<IMonthlyDOWTrigger,5>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x18002715f  mov     edi, eax
0x180027161  mov     [rsp+68h+arg_8], eax
0x180027165  jmp     loc_180026F0C
0x18002716a  mov     edi, 80070057h; jumptable 0000000180026EB3 default case, cases 8-10
0x18002716f  mov     [rsp+68h+arg_8], edi
0x180027173  jmp     loc_180026F15
0x180027178  mov     eax, [rsp+68h+arg_8]
0x18002717c  jmp     loc_180026F43
```
