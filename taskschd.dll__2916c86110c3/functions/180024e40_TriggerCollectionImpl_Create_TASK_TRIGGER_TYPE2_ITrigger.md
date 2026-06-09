# TriggerCollectionImpl::Create(_TASK_TRIGGER_TYPE2,ITrigger * *)

- ea: `0x180024e40`
- end: `0x1800251bc`
- name: `?Create@TriggerCollectionImpl@@UEAAJW4_TASK_TRIGGER_TYPE2@@PEAPEAUITrigger@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(TriggerCollectionImpl *__hidden this, enum _TASK_TRIGGER_TYPE2, struct ITrigger **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180024e40`
- `0x1800251c4`
- `0x180025290`
- `0x18002534c`
- `0x1800253d4`
- `0x1800254a0`
- `0x1800255d8`
- `0x180025754`
- `0x1800257e4`
- `0x180025978`
- `0x180025c6c`
- `0x180025d8c`
- `0x18002609c`
- `0x1800314f4`
- `0x180035990`
- `0x1800417f4`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024f34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024e7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024e7d`

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
0x180024e40  mov     [rsp+arg_10], rbx
0x180024e45  push    rsi
0x180024e46  push    rdi
0x180024e47  push    r12
0x180024e49  push    r14
0x180024e4b  push    r15
0x180024e4d  sub     rsp, 40h
0x180024e51  mov     r15, r8
0x180024e54  mov     edi, edx
0x180024e56  mov     rsi, rcx
0x180024e59  xor     r12d, r12d
0x180024e5c  mov     [rsp+68h+arg_8], r12d
0x180024e61  mov     ecx, r12d
0x180024e64  mov     [rsp+68h+arg_0], rcx
0x180024e69  lea     rbx, [rsi+20h]
0x180024e6d  test    rsi, rsi
0x180024e70  cmovz   rbx, r12
0x180024e74  test    rbx, rbx
0x180024e77  jz      short loc_180024E88
0x180024e79  lea     rcx, [rbx+8]; lpCriticalSection
0x180024e7d  call    cs:__imp_EnterCriticalSection
0x180024e83  mov     rcx, [rsp+68h+arg_0]
0x180024e88  mov     [rsp+68h+var_30], rbx
0x180024e8d  cmp     edi, 8
0x180024e90  jz      short loc_180024ECF
0x180024e92  cmp     edi, 9
0x180024e95  jz      loc_180024F68
0x180024e9b  cmp     edi, 1
0x180024e9e  jz      loc_18002501F
0x180024ea4  test    edi, edi
0x180024ea6  jz      loc_18002505F
0x180024eac  add     edi, 0FFFFFFFEh; switch 11 cases
0x180024eaf  cmp     edi, 0Ah
0x180024eb2  ja      def_180024ECD; jumptable 0000000180024ECD default case, cases 8-10
0x180024eb8  movsxd  rax, edi
0x180024ebb  lea     r8, __ImageBase
0x180024ec2  mov     edx, ds:(jpt_180024ECD - 180000000h)[r8+rax*4]
0x180024eca  add     rdx, r8
0x180024ecd  jmp     rdx; switch jump
0x180024ecf  test    rcx, rcx
0x180024ed2  jz      short loc_180024EE0
0x180024ed4  mov     rax, [rcx]
0x180024ed7  mov     rax, [rax+10h]
0x180024edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ee0  mov     [rsp+68h+arg_18], r12
0x180024ee8  lea     rcx, [rsp+68h+arg_18]
0x180024ef0  call    ?CreateInstance@?$CComObject@V?$BootTriggerImpl@UIBootTrigger@@$07@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<BootTriggerImpl<IBootTrigger,8>>::CreateInstance(ATL::CComObject<BootTriggerImpl<IBootTrigger,8>> * *)
0x180024ef5  test    eax, eax
0x180024ef7  mov     edi, eax
0x180024ef9  js      short loc_180024F1C
0x180024efb  mov     rcx, [rsp+68h+arg_18]
0x180024f03  mov     rax, [rcx]
0x180024f06  lea     r8, [rsp+68h+arg_0]
0x180024f0b  lea     rdx, _GUID_09941815_ea89_4b5b_89e0_2a773801fac3
0x180024f12  mov     rax, [rax]
0x180024f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f1a  mov     edi, eax
0x180024f1c  mov     eax, edi
0x180024f1e  mov     [rsp+68h+arg_8], edi
0x180024f22  test    eax, eax
0x180024f24  jns     short loc_180024F93
0x180024f26  mov     rcx, [rsp+68h+arg_0]
0x180024f2b  test    rbx, rbx
0x180024f2e  jz      short loc_180024F3F
0x180024f30  lea     rcx, [rbx+8]; lpCriticalSection
0x180024f34  call    cs:__imp_LeaveCriticalSection
0x180024f3a  mov     rcx, [rsp+68h+arg_0]
0x180024f3f  test    rcx, rcx
0x180024f42  jz      short loc_180024F51
0x180024f44  mov     rdx, [rcx]
0x180024f47  mov     rax, [rdx+10h]
0x180024f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f50  nop
0x180024f51  mov     eax, edi
0x180024f53  mov     rbx, [rsp+68h+arg_10]
0x180024f5b  add     rsp, 40h
0x180024f5f  pop     r15
0x180024f61  pop     r14
0x180024f63  pop     r12
0x180024f65  pop     rdi
0x180024f66  pop     rsi
0x180024f67  retn
0x180024f68  test    rcx, rcx
0x180024f6b  jz      short loc_180024F79
0x180024f6d  mov     rax, [rcx]
0x180024f70  mov     rax, [rax+10h]
0x180024f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f79  mov     [rsp+68h+arg_18], r12
0x180024f81  lea     rcx, [rsp+68h+arg_18]
0x180024f89  call    ?CreateInstance@?$CComObject@V?$LogonTriggerImpl@UILogonTrigger@@$08@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<LogonTriggerImpl<ILogonTrigger,9>>::CreateInstance(ATL::CComObject<LogonTriggerImpl<ILogonTrigger,9>> * *)
0x180024f8e  jmp     loc_180024EF5
0x180024f93  lea     r14, [rsi+8]
0x180024f97  mov     rsi, [rsp+68h+arg_0]
0x180024f9c  mov     [rsp+68h+var_38], rsi
0x180024fa1  test    rsi, rsi
0x180024fa4  jz      short loc_180024FB6
0x180024fa6  mov     rax, [rsi]
0x180024fa9  mov     rcx, rsi
0x180024fac  mov     rax, [rax+8]
0x180024fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fb5  nop
0x180024fb6  mov     rax, [r14+8]
0x180024fba  lea     rcx, [rsp+68h+var_38]
0x180024fbf  cmp     rcx, rax
0x180024fc2  jb      loc_18002508A
0x180024fc8  cmp     rax, [r14+10h]
0x180024fcc  jnz     short loc_180024FD6
0x180024fce  mov     rcx, r14
0x180024fd1  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<ITrigger>>>::_Reserve(unsigned __int64)
0x180024fd6  mov     rax, [r14+8]
0x180024fda  mov     [rax], rsi
0x180024fdd  test    rsi, rsi
0x180024fe0  jz      short loc_180024FF2
0x180024fe2  mov     rax, [rsi]
0x180024fe5  mov     rcx, rsi
0x180024fe8  mov     rax, [rax+8]
0x180024fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff1  nop
0x180024ff2  add     qword ptr [r14+8], 8
0x180024ff7  lea     rcx, [rsp+68h+var_38]
0x180024ffc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025001  test    r15, r15
0x180025004  jz      loc_180024F26
0x18002500a  mov     rax, [rsp+68h+arg_0]
0x18002500f  mov     rcx, r12
0x180025012  mov     [rsp+68h+arg_0], rcx
0x180025017  mov     [r15], rax
0x18002501a  jmp     loc_180024F2B
0x18002501f  test    rcx, rcx
0x180025022  jz      short loc_180025030
0x180025024  mov     rax, [rcx]
0x180025027  mov     rax, [rax+10h]
0x18002502b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025030  mov     [rsp+68h+arg_18], r12
0x180025038  lea     rcx, [rsp+68h+arg_18]
0x180025040  call    ?CreateInstance@?$CComObject@V?$TimeTriggerImpl@UITimeTrigger@@$00@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TimeTriggerImpl<ITimeTrigger,1>>::CreateInstance(ATL::CComObject<TimeTriggerImpl<ITimeTrigger,1>> * *)
0x180025045  jmp     loc_180024EF5
0x18002504a  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 6
0x18002504f  call    ??$CreateComInstance@V?$IdleTriggerImpl@UIIdleTrigger@@$05@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<IdleTriggerImpl<IIdleTrigger,6>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x180025054  mov     edi, eax
0x180025056  mov     [rsp+68h+arg_8], eax
0x18002505a  jmp     loc_180024F22
0x18002505f  test    rcx, rcx
0x180025062  jz      short loc_180025070
0x180025064  mov     rax, [rcx]
0x180025067  mov     rax, [rax+10h]
0x18002506b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025070  mov     [rsp+68h+arg_18], r12
0x180025078  lea     rcx, [rsp+68h+arg_18]
0x180025080  call    ?CreateInstance@?$CComObject@V?$EventTriggerImpl@UIEventTrigger@@$0A@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<EventTriggerImpl<IEventTrigger,0>>::CreateInstance(ATL::CComObject<EventTriggerImpl<IEventTrigger,0>> * *)
0x180025085  jmp     loc_180024EF5
0x18002508a  lea     rcx, [rsp+68h+var_38]
0x18002508f  cmp     [r14], rcx
0x180025092  ja      loc_180024FC8
0x180025098  mov     rsi, [r14]
0x18002509b  cmp     rax, [r14+10h]
0x18002509f  jnz     short loc_1800250A9
0x1800250a1  mov     rcx, r14
0x1800250a4  call    ?_Reserve@?$vector@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UITrigger@@@ATL@@@ATL@@@std@@@std@@IEAAX_K@Z; std::vector<ATL::CAdapt<ATL::CComPtr<ITrigger>>>::_Reserve(unsigned __int64)
0x1800250a9  lea     rcx, [rsp+68h+var_38]
0x1800250ae  sub     rcx, rsi
0x1800250b1  sar     rcx, 3
0x1800250b5  mov     rax, [r14]
0x1800250b8  lea     r8, [rax+rcx*8]
0x1800250bc  mov     rdx, [r14+8]
0x1800250c0  call    ??$construct@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@V12@@?$_Wrap_alloc@V?$allocator@V?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@@std@@@std@@QEAAXPEAV?$CAdapt@V?$CComPtr@UIAction@@@ATL@@@ATL@@$$QEAV23@@Z; std::_Wrap_alloc<std::allocator<ATL::CAdapt<ATL::CComPtr<IAction>>>>::construct<ATL::CAdapt<ATL::CComPtr<IAction>>,ATL::CAdapt<ATL::CComPtr<IAction>>>(ATL::CAdapt<ATL::CComPtr<IAction>> *,ATL::CAdapt<ATL::CComPtr<IAction>> &&)
0x1800250c5  jmp     loc_180024FF2
0x1800250ca  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 2
0x1800250cf  call    ??$CreateComInstance@V?$DailyTriggerImpl@UIDailyTrigger@@$01@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<DailyTriggerImpl<IDailyTrigger,2>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x1800250d4  mov     edi, eax
0x1800250d6  mov     [rsp+68h+arg_8], eax
0x1800250da  jmp     loc_180024F22
0x1800250df  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 12
0x1800250e4  call    ??$CreateComInstance@V?$WnfStateChangeTriggerImpl@UIWnfStateChangeTrigger@@$0M@@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<WnfStateChangeTriggerImpl<IWnfStateChangeTrigger,12>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x1800250e9  mov     edi, eax
0x1800250eb  mov     [rsp+68h+arg_8], eax
0x1800250ef  test    eax, eax
0x1800250f1  js      loc_180024F26
0x1800250f7  mov     edx, 4; enum _TASK_COMPATIBILITY
0x1800250fc  mov     rcx, [rsi+58h]; this
0x180025100  call    ?LevelUpCompatibility@TaskSettingsImpl@@QEAAJW4_TASK_COMPATIBILITY@@@Z; TaskSettingsImpl::LevelUpCompatibility(_TASK_COMPATIBILITY)
0x180025105  mov     edi, eax
0x180025107  mov     [rsp+68h+arg_8], eax
0x18002510b  jmp     loc_180024F22
0x180025110  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 3
0x180025115  call    ??$CreateComInstance@V?$WeeklyTriggerImpl@UIWeeklyTrigger@@$02@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<WeeklyTriggerImpl<IWeeklyTrigger,3>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x18002511a  mov     edi, eax
0x18002511c  mov     [rsp+68h+arg_8], eax
0x180025120  jmp     loc_180024F22
0x180025125  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 11
0x18002512a  call    ??$CreateComInstance@V?$SessionStateChangeTriggerImpl@UISessionStateChangeTrigger@@$0L@@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<SessionStateChangeTriggerImpl<ISessionStateChangeTrigger,11>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x18002512f  mov     edi, eax
0x180025131  mov     [rsp+68h+arg_8], eax
0x180025135  jmp     loc_180024F22
0x18002513a  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 7
0x18002513f  call    ??$CreateComInstance@V?$RegistrationTriggerImpl@UIRegistrationTrigger@@$06@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<RegistrationTriggerImpl<IRegistrationTrigger,7>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x180025144  mov     edi, eax
0x180025146  mov     [rsp+68h+arg_8], eax
0x18002514a  jmp     loc_180024F22
0x18002514f  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 4
0x180025154  call    ??$CreateComInstance@V?$MonthlyTriggerImpl@UIMonthlyTrigger@@$03@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<MonthlyTriggerImpl<IMonthlyTrigger,4>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x180025159  mov     edi, eax
0x18002515b  mov     [rsp+68h+arg_8], eax
0x18002515f  jmp     loc_180024F22
0x180025164  lea     rcx, [rsp+68h+arg_0]; jumptable 0000000180024ECD case 5
0x180025169  call    ??$CreateComInstance@V?$MonthlyDOWTriggerImpl@UIMonthlyDOWTrigger@@$04@@V?$CComPtr@UITrigger@@@ATL@@@@YAJAEAV?$CComPtr@UITrigger@@@ATL@@@Z; CreateComInstance<MonthlyDOWTriggerImpl<IMonthlyDOWTrigger,5>,ATL::CComPtr<ITrigger>>(ATL::CComPtr<ITrigger> &)
0x18002516e  mov     edi, eax
0x180025170  mov     [rsp+68h+arg_8], eax
0x180025174  jmp     loc_180024F22
0x180025179  mov     edi, 80070057h; jumptable 0000000180024ECD default case, cases 8-10
0x18002517e  mov     [rsp+68h+arg_8], edi
0x180025182  jmp     loc_180024F2B
0x180025187  mov     eax, [rsp+68h+arg_8]
0x18002518b  jmp     loc_180024F53
```
