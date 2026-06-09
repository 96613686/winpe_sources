# UniversalOrchestrator::ResumeSignal(void)

- ea: `0x180072280`
- end: `0x18007288e`
- name: `?ResumeSignal@UniversalOrchestrator@@UEAAJXZ`
- size: `1550`
- prototype: `__int64 __fastcall(UniversalOrchestrator *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180010890`
- `0x180011680`
- `0x18001b064`
- `0x18001c6b4`
- `0x18002b918`
- `0x1800420e0`
- `0x18006ea28`
- `0x18006ee60`
- `0x180072280`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800727fb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800727fb`

## string_xrefs

- `0x180072861`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18007287b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800723a1`: `\Microsoft\Windows\UpdateOrchestrator\Universal Orchestrator Idle Start`
- `0x1800726b4`: `Checking if DC wakes should be tracked: didUOIdleTaskWakeDevice: {}, didUSOWakeTaskWakeDevice: {}, isOnAC: {}, isCs: {}`
- `0x18007249b`: `\Microsoft\Windows\UpdateOrchestrator\Schedule Wake To Work`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UniversalOrchestrator::ResumeSignal(UniversalOrchestrator *this)
{
  UniversalOrchestrator *v1; // rsi
  UniversalOrchestrator *v2; // r15
  __int64 *System; // rax
  _QWORD *v4; // rax
  const char *v5; // r9
  volatile signed __int32 *v6; // rdi
  volatile signed __int32 *v7; // rdi
  __int64 *v8; // rax
  __int64 (__fastcall *v9)(__int64, __int128 *); // rdi
  wchar_t *traits_2_unsigned_short; // rax
  const char *v11; // r9
  __int64 v12; // r11
  __int64 v13; // rax
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi
  __int64 *v16; // rax
  __int64 (__fastcall *v17)(__int64, __int128 *); // rdi
  const bool *v18; // rax
  const char *v19; // r9
  __int64 v20; // r11
  __int64 v21; // rax
  char v22; // r13
  volatile signed __int32 *v23; // rdi
  volatile signed __int32 *v24; // rdi
  __int64 *v25; // rax
  _QWORD *v26; // rax
  char v27; // r12
  volatile signed __int32 *v28; // rdi
  volatile signed __int32 *v29; // rdi
  __int64 *v30; // rax
  _QWORD *v31; // rax
  char v32; // r14
  volatile signed __int32 *v33; // rdi
  volatile signed __int32 *v34; // rdi
  std::_Format_arg_index *v35; // rbx
  __int64 v36; // rdi
  _QWORD *v37; // rax
  __int64 v38; // rcx
  const char *v39; // r9
  unsigned __int64 v40; // rdx
  __int64 result; // rax
  char v42; // [rsp+20h] [rbp-B8h]
  __int128 v43; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v44; // [rsp+40h] [rbp-98h] BYREF
  _QWORD v45[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 Src; // [rsp+60h] [rbp-78h] BYREF
  volatile signed __int32 *v47; // [rsp+68h] [rbp-70h]
  _QWORD v48[4]; // [rsp+80h] [rbp-58h] BYREF
  char v49; // [rsp+A0h] [rbp-38h]
  char v50; // [rsp+A1h] [rbp-37h]
  char v51; // [rsp+A2h] [rbp-36h]
  char v52; // [rsp+A3h] [rbp-35h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    try
    {
      v1 = this;
      v2 = this;
      v45[0] = this;
      System = SystemInterface::Service::GetSystem((__int64 *)&v44);
      v4 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*System + 24LL))(*System, &Src);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 72LL))(*v4);
      v6 = v47;
      if ( v47 )
      {
        if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      v7 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
      if ( *((_QWORD *)&v44 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
        v5);
      v2 = (UniversalOrchestrator *)v45[0];
      v1 = (UniversalOrchestrator *)v45[0];
    }
    *((_BYTE *)v1 + 104) = 0;
    v8 = SystemInterface::Service::GetSystem(&Src);
    v9 = *(__int64 (__fastcall **)(__int64, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v8 + 72LL))(
                                                                        *v8,
                                                                        &v44)
                                                       + 144LL);
    traits_2_unsigned_short = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"\\Microsoft\\Windows\\UpdateOrchestrator\\Universal Orchestrator Idle Start",
                                           L"threshold: {}, minutesSinceWake: {}",
                                           0);
    if ( traits_2_unsigned_short == L"threshold: {}, minutesSinceWake: {}"
      || (v13 = traits_2_unsigned_short - L"\\Microsoft\\Windows\\UpdateOrchestrator\\Universal Orchestrator Idle Start",
          v13 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v11);
    }
    *(_QWORD *)&v43 = L"\\Microsoft\\Windows\\UpdateOrchestrator\\Universal Orchestrator Idle Start";
    *((_QWORD *)&v43 + 1) = v13;
    v42 = v9(v12, &v43);
    v14 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
    if ( *((_QWORD *)&v44 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v15 = v47;
    if ( v47 )
    {
      if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = SystemInterface::Service::GetSystem(&Src);
    v17 = *(__int64 (__fastcall **)(__int64, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v16 + 72LL))(
                                                                         *v16,
                                                                         &v44)
                                                        + 144LL);
    v18 = (const bool *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                          L"\\Microsoft\\Windows\\UpdateOrchestrator\\Schedule Wake To Work",
                          "Caller: %ws Cmdline: %ws",
                          0);
    if ( v18 == "Caller: %ws Cmdline: %ws"
      || (v21 = (v18 - (const bool *)L"\\Microsoft\\Windows\\UpdateOrchestrator\\Schedule Wake To Work") >> 1, v21 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v19);
    }
    *(_QWORD *)&v43 = L"\\Microsoft\\Windows\\UpdateOrchestrator\\Schedule Wake To Work";
    *((_QWORD *)&v43 + 1) = v21;
    v22 = v17(v20, &v43);
    v23 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
    if ( *((_QWORD *)&v44 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v24 = v47;
    if ( v47 )
    {
      if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v25 = SystemInterface::Service::GetSystem(&Src);
    v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v25 + 56LL))(*v25, &v44);
    v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 40LL))(*v26);
    v28 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
    if ( *((_QWORD *)&v44 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
    v29 = v47;
    if ( v47 )
    {
      if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    v30 = SystemInterface::Service::GetSystem(&Src);
    v31 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v30 + 56LL))(*v30, &v44);
    v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 80LL))(*v31);
    v33 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
    if ( *((_QWORD *)&v44 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    v34 = v47;
    if ( v47 )
    {
      if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
        if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
    *(_QWORD *)&v43 = L"Checking if DC wakes should be tracked: didUOIdleTaskWakeDevice: {}, didUSOWakeTaskWakeDevice: {},"
                       " isOnAC: {}, isCs: {}";
    *((_QWORD *)&v43 + 1) = 119;
    v35 = (std::_Format_arg_index *)v48;
    v36 = 4;
    do
    {
      std::_Format_arg_index::_Format_arg_index(v35);
      v35 = (std::_Format_arg_index *)((char *)v35 + 8);
      --v36;
    }
    while ( v36 );
    v49 = v42;
    v48[0] = 0x5000000000000000LL;
    v50 = v22;
    v48[1] = 0x5000000000000001LL;
    v51 = v27;
    v48[2] = 0x5000000000000002LL;
    v52 = v32;
    v48[3] = 0x5000000000000003LL;
    v45[0] = 4;
    v45[1] = v48;
    v44 = v43;
    v37 = (_QWORD *)std::vformat<0>(&Src);
    v38 = v37[2];
    if ( v37[3] > 7u )
      v37 = (_QWORD *)*v37;
    *(_QWORD *)&v43 = v37;
    *((_QWORD *)&v43 + 1) = v38;
    SystemInterface::LogMessage(&v43, 1);
    std::wstring::~wstring(&Src);
    if ( !v42 && !v22 || v27 || v32 )
    {
      *((_BYTE *)v1 + 104) = 0;
      result = 0;
    }
    else
    {
      *(_QWORD *)&v43 = L"Tracking wakes on DC";
      *((_QWORD *)&v43 + 1) = 20;
      SystemInterface::Log<>(&v43);
      v45[0] = 0;
      GetSystemTimePreciseAsFileTime(v45);
      v40 = LODWORD(v45[0]) + ((unsigned __int64)HIDWORD(v45[0]) << 32) - 116444736000000000LL;
      if ( !*((_BYTE *)v2 + 104) )
        *((_BYTE *)v2 + 104) = 1;
      *((_QWORD *)v1 + 12) = v40;
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x216,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
                           v39);
  }
  return result;
}

```

## disassembly

```asm
0x180072280  mov     [rsp+arg_8], rbx
0x180072285  mov     [rsp+arg_10], rsi
0x18007228a  push    rdi
0x18007228b  push    r12
0x18007228d  push    r13
0x18007228f  push    r14
0x180072291  push    r15
0x180072293  sub     rsp, 0B0h
0x18007229a  mov     rsi, rcx
0x18007229d  mov     r15, rcx
0x1800722a0  mov     [rsp+0D8h+var_88], rcx
0x1800722a5  lea     rcx, [rsp+0D8h+var_98]
0x1800722aa  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800722af  nop
0x1800722b0  mov     rcx, [rax]
0x1800722b3  mov     rax, [rcx]
0x1800722b6  lea     rdx, [rsp+0D8h+Src]
0x1800722bb  mov     rax, [rax+18h]
0x1800722bf  call    _guard_dispatch_icall
0x1800722c4  nop
0x1800722c5  mov     rcx, [rax]
0x1800722c8  mov     rax, [rcx]
0x1800722cb  mov     rax, [rax+48h]
0x1800722cf  call    _guard_dispatch_icall
0x1800722d4  nop
0x1800722d5  mov     rdi, [rsp+0D8h+var_70]
0x1800722da  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800722de  test    rdi, rdi
0x1800722e1  jz      short loc_180072317
0x1800722e3  mov     eax, ebx
0x1800722e5  lock xadd [rdi+8], eax
0x1800722ea  add     eax, ebx
0x1800722ec  jnz     short loc_180072317
0x1800722ee  mov     rax, [rdi]
0x1800722f1  mov     rcx, rdi
0x1800722f4  mov     rax, [rax]
0x1800722f7  call    _guard_dispatch_icall
0x1800722fc  mov     eax, ebx
0x1800722fe  lock xadd [rdi+0Ch], eax
0x180072303  add     eax, ebx
0x180072305  jnz     short loc_180072317
0x180072307  mov     rax, [rdi]
0x18007230a  mov     rcx, rdi
0x18007230d  mov     rax, [rax+8]
0x180072311  call    _guard_dispatch_icall
0x180072316  nop
0x180072317  mov     rdi, qword ptr [rsp+0D8h+var_98+8]
0x18007231c  test    rdi, rdi
0x18007231f  jz      short loc_180072355
0x180072321  mov     eax, ebx
0x180072323  lock xadd [rdi+8], eax
0x180072328  add     eax, ebx
0x18007232a  jnz     short loc_180072355
0x18007232c  mov     rax, [rdi]
0x18007232f  mov     rcx, rdi
0x180072332  mov     rax, [rax]
0x180072335  call    _guard_dispatch_icall
0x18007233a  mov     eax, ebx
0x18007233c  lock xadd [rdi+0Ch], eax
0x180072341  add     eax, ebx
0x180072343  jnz     short loc_180072355
0x180072345  mov     rax, [rdi]
0x180072348  mov     rcx, rdi
0x18007234b  mov     rax, [rax+8]
0x18007234f  call    _guard_dispatch_icall
0x180072354  nop
0x180072355  jmp     short loc_180072363
0x180072357  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007235b  mov     r15, [rsp+0D8h+var_88]
0x180072360  mov     rsi, r15
0x180072363  mov     byte ptr [rsi+68h], 0
0x180072367  lea     rcx, [rsp+0D8h+Src]
0x18007236c  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180072371  nop
0x180072372  mov     rcx, [rax]
0x180072375  mov     rax, [rcx]
0x180072378  lea     rdx, [rsp+0D8h+var_98]
0x18007237d  mov     rax, [rax+48h]
0x180072381  call    _guard_dispatch_icall
0x180072386  nop
0x180072387  mov     r11, [rax]
0x18007238a  mov     rax, [r11]
0x18007238d  mov     rdi, [rax+90h]
0x180072394  xor     r8d, r8d
0x180072397  lea     r14, aThresholdMinut; "threshold: {}, minutesSinceWake: {}"
0x18007239e  mov     rdx, r14
0x1800723a1  lea     r12, aMicrosoftWindo_2; "\\Microsoft\\Windows\\UpdateOrchestrato"...
0x1800723a8  mov     rcx, r12
0x1800723ab  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800723b0  cmp     rax, r14
0x1800723b3  jz      loc_180072873
0x1800723b9  sub     rax, r12
0x1800723bc  sar     rax, 1
0x1800723bf  cmp     rax, rbx
0x1800723c2  jz      loc_180072873
0x1800723c8  mov     qword ptr [rsp+0D8h+var_A8], r12
0x1800723cd  mov     qword ptr [rsp+0D8h+var_A8+8], rax
0x1800723d2  lea     rdx, [rsp+0D8h+var_A8]
0x1800723d7  mov     rcx, r11
0x1800723da  mov     rax, rdi
0x1800723dd  call    _guard_dispatch_icall
0x1800723e2  mov     [rsp+0D8h+var_B8], al
0x1800723e6  mov     rdi, qword ptr [rsp+0D8h+var_98+8]
0x1800723eb  test    rdi, rdi
0x1800723ee  jz      short loc_180072424
0x1800723f0  mov     ecx, ebx
0x1800723f2  lock xadd [rdi+8], ecx
0x1800723f7  add     ecx, ebx
0x1800723f9  jnz     short loc_180072424
0x1800723fb  mov     rax, [rdi]
0x1800723fe  mov     rcx, rdi
0x180072401  mov     rax, [rax]
0x180072404  call    _guard_dispatch_icall
0x180072409  mov     eax, ebx
0x18007240b  lock xadd [rdi+0Ch], eax
0x180072410  add     eax, ebx
0x180072412  jnz     short loc_180072424
0x180072414  mov     rax, [rdi]
0x180072417  mov     rcx, rdi
0x18007241a  mov     rax, [rax+8]
0x18007241e  call    _guard_dispatch_icall
0x180072423  nop
0x180072424  mov     rdi, [rsp+0D8h+var_70]
0x180072429  test    rdi, rdi
0x18007242c  jz      short loc_180072461
0x18007242e  mov     eax, ebx
0x180072430  lock xadd [rdi+8], eax
0x180072435  add     eax, ebx
0x180072437  jnz     short loc_180072461
0x180072439  mov     rax, [rdi]
0x18007243c  mov     rcx, rdi
0x18007243f  mov     rax, [rax]
0x180072442  call    _guard_dispatch_icall
0x180072447  mov     eax, ebx
0x180072449  lock xadd [rdi+0Ch], eax
0x18007244e  add     eax, ebx
0x180072450  jnz     short loc_180072461
0x180072452  mov     rax, [rdi]
0x180072455  mov     rcx, rdi
0x180072458  mov     rax, [rax+8]
0x18007245c  call    _guard_dispatch_icall
0x180072461  lea     rcx, [rsp+0D8h+Src]
0x180072466  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18007246b  nop
0x18007246c  mov     rcx, [rax]
0x18007246f  mov     rax, [rcx]
0x180072472  lea     rdx, [rsp+0D8h+var_98]
0x180072477  mov     rax, [rax+48h]
0x18007247b  call    _guard_dispatch_icall
0x180072480  nop
0x180072481  mov     r11, [rax]
0x180072484  mov     rax, [r11]
0x180072487  mov     rdi, [rax+90h]
0x18007248e  xor     r8d, r8d
0x180072491  lea     r14, aCallerWsCmdlin; "Caller: %ws Cmdline: %ws"
0x180072498  mov     rdx, r14
0x18007249b  lea     r12, aMicrosoftWindo_3; "\\Microsoft\\Windows\\UpdateOrchestrato"...
0x1800724a2  mov     rcx, r12
0x1800724a5  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800724aa  cmp     rax, r14
0x1800724ad  jz      loc_180072859
0x1800724b3  sub     rax, r12
0x1800724b6  sar     rax, 1
0x1800724b9  cmp     rax, rbx
0x1800724bc  jz      loc_180072859
0x1800724c2  mov     qword ptr [rsp+0D8h+var_A8], r12
0x1800724c7  mov     qword ptr [rsp+0D8h+var_A8+8], rax
0x1800724cc  lea     rdx, [rsp+0D8h+var_A8]
0x1800724d1  mov     rcx, r11
0x1800724d4  mov     rax, rdi
0x1800724d7  call    _guard_dispatch_icall
0x1800724dc  mov     r13b, al
0x1800724df  mov     rdi, qword ptr [rsp+0D8h+var_98+8]
0x1800724e4  test    rdi, rdi
0x1800724e7  jz      short loc_18007251D
0x1800724e9  mov     ecx, ebx
0x1800724eb  lock xadd [rdi+8], ecx
0x1800724f0  add     ecx, ebx
0x1800724f2  jnz     short loc_18007251D
0x1800724f4  mov     rax, [rdi]
0x1800724f7  mov     rcx, rdi
0x1800724fa  mov     rax, [rax]
0x1800724fd  call    _guard_dispatch_icall
0x180072502  mov     eax, ebx
0x180072504  lock xadd [rdi+0Ch], eax
0x180072509  add     eax, ebx
0x18007250b  jnz     short loc_18007251D
0x18007250d  mov     rax, [rdi]
0x180072510  mov     rcx, rdi
0x180072513  mov     rax, [rax+8]
0x180072517  call    _guard_dispatch_icall
0x18007251c  nop
0x18007251d  mov     rdi, [rsp+0D8h+var_70]
0x180072522  test    rdi, rdi
0x180072525  jz      short loc_18007255A
0x180072527  mov     eax, ebx
0x180072529  lock xadd [rdi+8], eax
0x18007252e  add     eax, ebx
0x180072530  jnz     short loc_18007255A
0x180072532  mov     rax, [rdi]
0x180072535  mov     rcx, rdi
0x180072538  mov     rax, [rax]
0x18007253b  call    _guard_dispatch_icall
0x180072540  mov     eax, ebx
0x180072542  lock xadd [rdi+0Ch], eax
0x180072547  add     eax, ebx
0x180072549  jnz     short loc_18007255A
0x18007254b  mov     rax, [rdi]
0x18007254e  mov     rcx, rdi
0x180072551  mov     rax, [rax+8]
0x180072555  call    _guard_dispatch_icall
0x18007255a  lea     rcx, [rsp+0D8h+Src]
0x18007255f  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180072564  nop
0x180072565  mov     rcx, [rax]
0x180072568  mov     rax, [rcx]
0x18007256b  lea     rdx, [rsp+0D8h+var_98]
0x180072570  mov     rax, [rax+38h]
0x180072574  call    _guard_dispatch_icall
0x180072579  nop
0x18007257a  mov     rcx, [rax]
0x18007257d  mov     rax, [rcx]
0x180072580  mov     rax, [rax+28h]
0x180072584  call    _guard_dispatch_icall
0x180072589  mov     r12b, al
0x18007258c  mov     rdi, qword ptr [rsp+0D8h+var_98+8]
0x180072591  test    rdi, rdi
0x180072594  jz      short loc_1800725CA
0x180072596  mov     ecx, ebx
0x180072598  lock xadd [rdi+8], ecx
0x18007259d  add     ecx, ebx
0x18007259f  jnz     short loc_1800725CA
0x1800725a1  mov     rax, [rdi]
0x1800725a4  mov     rcx, rdi
0x1800725a7  mov     rax, [rax]
0x1800725aa  call    _guard_dispatch_icall
0x1800725af  mov     eax, ebx
0x1800725b1  lock xadd [rdi+0Ch], eax
0x1800725b6  add     eax, ebx
0x1800725b8  jnz     short loc_1800725CA
0x1800725ba  mov     rax, [rdi]
0x1800725bd  mov     rcx, rdi
0x1800725c0  mov     rax, [rax+8]
0x1800725c4  call    _guard_dispatch_icall
0x1800725c9  nop
0x1800725ca  mov     rdi, [rsp+0D8h+var_70]
0x1800725cf  test    rdi, rdi
0x1800725d2  jz      short loc_180072607
0x1800725d4  mov     eax, ebx
0x1800725d6  lock xadd [rdi+8], eax
0x1800725db  add     eax, ebx
0x1800725dd  jnz     short loc_180072607
0x1800725df  mov     rax, [rdi]
0x1800725e2  mov     rcx, rdi
0x1800725e5  mov     rax, [rax]
0x1800725e8  call    _guard_dispatch_icall
0x1800725ed  mov     eax, ebx
0x1800725ef  lock xadd [rdi+0Ch], eax
0x1800725f4  add     eax, ebx
0x1800725f6  jnz     short loc_180072607
0x1800725f8  mov     rax, [rdi]
0x1800725fb  mov     rcx, rdi
0x1800725fe  mov     rax, [rax+8]
0x180072602  call    _guard_dispatch_icall
0x180072607  lea     rcx, [rsp+0D8h+Src]
0x18007260c  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180072611  nop
0x180072612  mov     rcx, [rax]
0x180072615  mov     rax, [rcx]
0x180072618  lea     rdx, [rsp+0D8h+var_98]
0x18007261d  mov     rax, [rax+38h]
0x180072621  call    _guard_dispatch_icall
0x180072626  nop
0x180072627  mov     rcx, [rax]
0x18007262a  mov     rax, [rcx]
0x18007262d  mov     rax, [rax+50h]
0x180072631  call    _guard_dispatch_icall
0x180072636  mov     r14b, al
0x180072639  mov     rdi, qword ptr [rsp+0D8h+var_98+8]
0x18007263e  test    rdi, rdi
0x180072641  jz      short loc_180072677
0x180072643  mov     ecx, ebx
0x180072645  lock xadd [rdi+8], ecx
0x18007264a  add     ecx, ebx
0x18007264c  jnz     short loc_180072677
0x18007264e  mov     rax, [rdi]
0x180072651  mov     rcx, rdi
0x180072654  mov     rax, [rax]
0x180072657  call    _guard_dispatch_icall
0x18007265c  mov     eax, ebx
0x18007265e  lock xadd [rdi+0Ch], eax
0x180072663  add     eax, ebx
0x180072665  jnz     short loc_180072677
0x180072667  mov     rax, [rdi]
0x18007266a  mov     rcx, rdi
0x18007266d  mov     rax, [rax+8]
0x180072671  call    _guard_dispatch_icall
0x180072676  nop
0x180072677  mov     rdi, [rsp+0D8h+var_70]
0x18007267c  test    rdi, rdi
  ... truncated ...
```
