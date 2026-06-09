# UxUpdateManager::PersistRebootStartTimeValues(void)

- ea: `0x18003fc64`
- end: `0x180040125`
- name: `?PersistRebootStartTimeValues@UxUpdateManager@@AEAAXXZ`
- size: `1217`
- prototype: `void __fastcall(UxUpdateManager *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003cc10`
- `0x18003cf2c`
- `0x18003dde0`

## callees

- `0x18000c524`
- `0x180010890`
- `0x180011680`
- `0x18003fc64`
- `0x1800420e0`
- `0x18006ea28`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18003fcb3`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18003fcb3`

## string_xrefs

- `0x1800400e7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800400fd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180040113`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18003fe41`: `FirstLogonAfterUpdateFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall UxUpdateManager::PersistRebootStartTimeValues(UxUpdateManager *this)
{
  __int64 *System; // rax
  __int64 v2; // rbx
  __int64 traits_2_unsigned_short; // rax
  const char *v4; // r9
  __int64 v5; // r11
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  __int64 *v11; // rax
  void (__fastcall *v12)(__int64, __int128 *, __int128 *, __int128 *, _DWORD *); // rbx
  int *v13; // rax
  const char *v14; // r9
  __int64 v15; // r11
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  __int64 *v21; // rax
  void (__fastcall *v22)(__int64, __int128 *, __int128 *, __int128 *); // rbx
  wchar_t *v23; // rax
  const char *v24; // r9
  __int64 v25; // r11
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  volatile signed __int32 *v29; // rbx
  volatile signed __int32 *v30; // rbx
  __int128 v31; // [rsp+38h] [rbp-69h] BYREF
  __int128 v32; // [rsp+48h] [rbp-59h] BYREF
  __int128 v33; // [rsp+58h] [rbp-49h] BYREF
  __int128 v34; // [rsp+68h] [rbp-39h] BYREF
  __int128 v35; // [rsp+78h] [rbp-29h] BYREF
  __int128 v36; // [rsp+88h] [rbp-19h] BYREF
  __int128 v37; // [rsp+98h] [rbp-9h] BYREF
  __int64 v38; // [rsp+A8h] [rbp+7h] BYREF
  volatile signed __int32 *v39; // [rsp+B0h] [rbp+Fh]
  _DWORD v40[8]; // [rsp+B8h] [rbp+17h] BYREF
  char v41; // [rsp+D8h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]
  UxUpdateManager *v43; // [rsp+108h] [rbp+67h] BYREF

  v43 = this;
  System = SystemInterface::Service::GetSystem((__int64 *)&v35);
  v2 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*System + 32LL))(*System, &v34);
  v43 = 0;
  GetSystemTimePreciseAsFileTime(&v43);
  v43 = (UxUpdateManager *)(((unsigned __int64)HIDWORD(v43) << 32) - 116444736000000000LL + (unsigned int)v43);
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"StartTime",
                              &dword_1800FB21C,
                              0);
  if ( traits_2_unsigned_short == v5 || (v6 = (traits_2_unsigned_short - (__int64)L"StartTime") >> 1, v6 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v4);
  *(_QWORD *)&v32 = L"StartTime";
  *((_QWORD *)&v32 + 1) = v6;
  v7 = -1;
  do
    ++v7;
  while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v7] );
  *(_QWORD *)&v33 = SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT;
  *((_QWORD *)&v33 + 1) = v7;
  *(_QWORD *)&v31 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
  v8 = -1;
  do
    ++v8;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v8] );
  *((_QWORD *)&v31 + 1) = v8;
  SystemInterface::Registry::SetSystemTime(
    v2,
    (unsigned int)&v31,
    (unsigned int)&v33,
    (unsigned int)&v32,
    (__int64)&v43);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
  if ( *((_QWORD *)&v35 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = SystemInterface::Service::GetSystem((__int64 *)&v37);
  v12 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _DWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v11 + 32LL))(*v11, &v36)
                                                                                     + 64LL);
  v40[0] = 1;
  v41 = 0;
  v13 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                 L"FirstLogonAfterUpdateFlag",
                 &dword_1800FB254,
                 0);
  if ( v13 == &dword_1800FB254 || (v16 = ((char *)v13 - (char *)L"FirstLogonAfterUpdateFlag") >> 1, v16 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v14);
  *(_QWORD *)&v31 = L"FirstLogonAfterUpdateFlag";
  *((_QWORD *)&v31 + 1) = v16;
  v17 = -1;
  do
    ++v17;
  while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v17] );
  *(_QWORD *)&v33 = SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT;
  *((_QWORD *)&v33 + 1) = v17;
  *(_QWORD *)&v32 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
  v18 = -1;
  do
    ++v18;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v18] );
  *((_QWORD *)&v32 + 1) = v18;
  v35 = v31;
  v34 = v33;
  v31 = v32;
  v12(v15, &v31, &v34, &v35, v40);
  if ( v41 != -1 && v41 && v41 != 1 )
    std::wstring::~wstring(v40);
  v19 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
  if ( *((_QWORD *)&v36 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  v20 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
  if ( *((_QWORD *)&v37 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = SystemInterface::Service::GetSystem(&v38);
  v22 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v21 + 32LL))(
                                                                                            *v21,
                                                                                            &v34)
                                                                           + 80LL);
  v23 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"EndTime",
                     L"RestartRequest:",
                     0);
  if ( v23 == L"RestartRequest:" || (v26 = v23 - L"EndTime", v26 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v24);
  *(_QWORD *)&v31 = L"EndTime";
  *((_QWORD *)&v31 + 1) = v26;
  v27 = -1;
  do
    ++v27;
  while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v27] );
  *(_QWORD *)&v33 = SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT;
  *((_QWORD *)&v33 + 1) = v27;
  *(_QWORD *)&v32 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
  v28 = -1;
  do
    ++v28;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v28] );
  *((_QWORD *)&v32 + 1) = v28;
  v37 = v31;
  v36 = v33;
  v35 = v32;
  v22(v25, &v35, &v36, &v37);
  v29 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
      if ( !_InterlockedDecrement(v29 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  v30 = v39;
  if ( v39 && !_InterlockedDecrement(v39 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
    if ( !_InterlockedDecrement(v30 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
  }
}

```

## disassembly

```asm
0x18003fc64  mov     rax, rsp
0x18003fc67  mov     [rax+10h], rbx
0x18003fc6b  mov     [rax+18h], rsi
0x18003fc6f  mov     [rax+20h], rdi
0x18003fc73  mov     [rax+8], rcx
0x18003fc77  push    rbp
0x18003fc78  push    r14
0x18003fc7a  push    r15
0x18003fc7c  lea     rbp, [rax-5Fh]
0x18003fc80  sub     rsp, 0E0h
0x18003fc87  lea     rcx, [rbp+57h+var_80]
0x18003fc8b  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003fc90  nop
0x18003fc91  mov     rcx, [rax]
0x18003fc94  mov     rax, [rcx]
0x18003fc97  lea     rdx, [rbp+57h+var_90]
0x18003fc9b  mov     rax, [rax+20h]
0x18003fc9f  call    _guard_dispatch_icall
0x18003fca4  nop
0x18003fca5  mov     rbx, [rax]
0x18003fca8  xor     r14d, r14d
0x18003fcab  mov     [rbp+57h+arg_0], r14
0x18003fcaf  lea     rcx, [rbp+57h+arg_0]
0x18003fcb3  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18003fcb9  mov     eax, dword ptr [rbp+57h+arg_0+4]
0x18003fcbc  shl     rax, 20h
0x18003fcc0  mov     ecx, dword ptr [rbp+57h+arg_0]
0x18003fcc3  mov     rdx, 0FE624E212AC18000h
0x18003fccd  add     rax, rdx
0x18003fcd0  add     rcx, rax
0x18003fcd3  mov     [rbp+57h+arg_0], rcx
0x18003fcd7  xor     r8d, r8d
0x18003fcda  lea     r11, dword_1800FB21C
0x18003fce1  mov     rdx, r11
0x18003fce4  lea     rdi, aStarttime; "StartTime"
0x18003fceb  mov     rcx, rdi
0x18003fcee  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003fcf3  cmp     rax, r11
0x18003fcf6  jz      loc_1800400F9
0x18003fcfc  sub     rax, rdi
0x18003fcff  sar     rax, 1
0x18003fd02  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003fd06  cmp     rax, rsi
0x18003fd09  jz      loc_1800400F9
0x18003fd0f  mov     qword ptr [rbp+57h+var_B0], rdi
0x18003fd13  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18003fd17  mov     rcx, cs:?UPDATE_UX_REBOOTDOWNTIME_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT
0x18003fd1e  mov     rax, rsi
0x18003fd21  inc     rax
0x18003fd24  cmp     [rcx+rax*2], r14w
0x18003fd29  jnz     short loc_18003FD21
0x18003fd2b  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003fd2f  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18003fd33  mov     rcx, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x18003fd3a  mov     qword ptr [rbp+57h+var_C0], rcx
0x18003fd3e  mov     rax, rsi
0x18003fd41  inc     rax
0x18003fd44  cmp     [rcx+rax*2], r14w
0x18003fd49  jnz     short loc_18003FD41
0x18003fd4b  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18003fd4f  movups  xmm0, [rbp+57h+var_B0]
0x18003fd53  movdqu  [rbp+57h+var_B0], xmm0
0x18003fd58  movups  xmm1, [rbp+57h+var_A0]
0x18003fd5c  movdqu  [rbp+57h+var_A0], xmm1
0x18003fd61  movaps  xmm0, [rbp+57h+var_C0]
0x18003fd65  movdqa  [rbp+57h+var_C0], xmm0
0x18003fd6a  lea     rax, [rbp+57h+arg_0]
0x18003fd6e  mov     [rsp+0F0h+var_D0], rax
0x18003fd73  lea     r9, [rbp+57h+var_B0]
0x18003fd77  lea     r8, [rbp+57h+var_A0]
0x18003fd7b  lea     rdx, [rbp+57h+var_C0]
0x18003fd7f  mov     rcx, rbx
0x18003fd82  call    ?SetSystemTime@Registry@SystemInterface@@QEAAXV?$basic_zstring_view@_W@wil@@00AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; SystemInterface::Registry::SetSystemTime(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18003fd87  nop
0x18003fd88  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x18003fd8c  test    rbx, rbx
0x18003fd8f  jz      short loc_18003FDC5
0x18003fd91  mov     eax, esi
0x18003fd93  lock xadd [rbx+8], eax
0x18003fd98  add     eax, esi
0x18003fd9a  jnz     short loc_18003FDC5
0x18003fd9c  mov     rax, [rbx]
0x18003fd9f  mov     rcx, rbx
0x18003fda2  mov     rax, [rax]
0x18003fda5  call    _guard_dispatch_icall
0x18003fdaa  mov     eax, esi
0x18003fdac  lock xadd [rbx+0Ch], eax
0x18003fdb1  add     eax, esi
0x18003fdb3  jnz     short loc_18003FDC5
0x18003fdb5  mov     rax, [rbx]
0x18003fdb8  mov     rcx, rbx
0x18003fdbb  mov     rax, [rax+8]
0x18003fdbf  call    _guard_dispatch_icall
0x18003fdc4  nop
0x18003fdc5  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x18003fdc9  test    rbx, rbx
0x18003fdcc  jz      short loc_18003FE01
0x18003fdce  mov     eax, esi
0x18003fdd0  lock xadd [rbx+8], eax
0x18003fdd5  add     eax, esi
0x18003fdd7  jnz     short loc_18003FE01
0x18003fdd9  mov     rax, [rbx]
0x18003fddc  mov     rcx, rbx
0x18003fddf  mov     rax, [rax]
0x18003fde2  call    _guard_dispatch_icall
0x18003fde7  mov     eax, esi
0x18003fde9  lock xadd [rbx+0Ch], eax
0x18003fdee  add     eax, esi
0x18003fdf0  jnz     short loc_18003FE01
0x18003fdf2  mov     rax, [rbx]
0x18003fdf5  mov     rcx, rbx
0x18003fdf8  mov     rax, [rax+8]
0x18003fdfc  call    _guard_dispatch_icall
0x18003fe01  lea     rcx, [rbp+57h+var_60]
0x18003fe05  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003fe0a  nop
0x18003fe0b  mov     rcx, [rax]
0x18003fe0e  mov     rax, [rcx]
0x18003fe11  lea     rdx, [rbp+57h+var_70]
0x18003fe15  mov     rax, [rax+20h]
0x18003fe19  call    _guard_dispatch_icall
0x18003fe1e  nop
0x18003fe1f  mov     r11, [rax]
0x18003fe22  mov     rax, [r11]
0x18003fe25  mov     rbx, [rax+40h]
0x18003fe29  mov     [rbp+57h+var_40], 1
0x18003fe30  mov     [rbp+57h+var_20], r14b
0x18003fe34  xor     r8d, r8d
0x18003fe37  lea     rdi, dword_1800FB254
0x18003fe3e  mov     rdx, rdi
0x18003fe41  lea     r15, aFirstlogonafte; "FirstLogonAfterUpdateFlag"
0x18003fe48  mov     rcx, r15
0x18003fe4b  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003fe50  cmp     rax, rdi
0x18003fe53  jz      loc_1800400E3
0x18003fe59  sub     rax, r15
0x18003fe5c  sar     rax, 1
0x18003fe5f  cmp     rax, rsi
0x18003fe62  jz      loc_1800400E3
0x18003fe68  mov     qword ptr [rbp+57h+var_C0], r15
0x18003fe6c  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18003fe70  mov     rcx, cs:?UPDATE_UX_REBOOTDOWNTIME_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT
0x18003fe77  mov     rax, rsi
0x18003fe7a  inc     rax
0x18003fe7d  cmp     [rcx+rax*2], r14w
0x18003fe82  jnz     short loc_18003FE7A
0x18003fe84  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003fe88  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18003fe8c  mov     rcx, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x18003fe93  mov     qword ptr [rbp+57h+var_B0], rcx
0x18003fe97  mov     rax, rsi
0x18003fe9a  inc     rax
0x18003fe9d  cmp     [rcx+rax*2], r14w
0x18003fea2  jnz     short loc_18003FE9A
0x18003fea4  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18003fea8  movups  xmm0, [rbp+57h+var_C0]
0x18003feac  movdqu  [rbp+57h+var_80], xmm0
0x18003feb1  movups  xmm1, [rbp+57h+var_A0]
0x18003feb5  movdqu  [rbp+57h+var_90], xmm1
0x18003feba  movaps  xmm0, [rbp+57h+var_B0]
0x18003febe  movdqa  [rbp+57h+var_C0], xmm0
0x18003fec3  lea     rax, [rbp+57h+var_40]
0x18003fec7  mov     [rsp+0F0h+var_D0], rax
0x18003fecc  lea     r9, [rbp+57h+var_80]
0x18003fed0  lea     r8, [rbp+57h+var_90]
0x18003fed4  lea     rdx, [rbp+57h+var_C0]
0x18003fed8  mov     rcx, r11
0x18003fedb  mov     rax, rbx
0x18003fede  call    _guard_dispatch_icall
0x18003fee3  nop
0x18003fee4  movsx   rax, [rbp+57h+var_20]
0x18003fee9  add     rax, 1
0x18003feed  jz      short loc_18003FF05
0x18003feef  sub     rax, 1
0x18003fef3  jz      short loc_18003FF05
0x18003fef5  cmp     rax, 1
0x18003fef9  jz      short loc_18003FF05
0x18003fefb  lea     rcx, [rbp+57h+var_40]; void *
0x18003feff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ff04  nop
0x18003ff05  mov     rbx, qword ptr [rbp+57h+var_70+8]
0x18003ff09  test    rbx, rbx
0x18003ff0c  jz      short loc_18003FF42
0x18003ff0e  mov     eax, esi
0x18003ff10  lock xadd [rbx+8], eax
0x18003ff15  add     eax, esi
0x18003ff17  jnz     short loc_18003FF42
0x18003ff19  mov     rax, [rbx]
0x18003ff1c  mov     rcx, rbx
0x18003ff1f  mov     rax, [rax]
0x18003ff22  call    _guard_dispatch_icall
0x18003ff27  mov     eax, esi
0x18003ff29  lock xadd [rbx+0Ch], eax
0x18003ff2e  add     eax, esi
0x18003ff30  jnz     short loc_18003FF42
0x18003ff32  mov     rax, [rbx]
0x18003ff35  mov     rcx, rbx
0x18003ff38  mov     rax, [rax+8]
0x18003ff3c  call    _guard_dispatch_icall
0x18003ff41  nop
0x18003ff42  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x18003ff46  test    rbx, rbx
0x18003ff49  jz      short loc_18003FF7E
0x18003ff4b  mov     eax, esi
0x18003ff4d  lock xadd [rbx+8], eax
0x18003ff52  add     eax, esi
0x18003ff54  jnz     short loc_18003FF7E
0x18003ff56  mov     rax, [rbx]
0x18003ff59  mov     rcx, rbx
0x18003ff5c  mov     rax, [rax]
0x18003ff5f  call    _guard_dispatch_icall
0x18003ff64  mov     eax, esi
0x18003ff66  lock xadd [rbx+0Ch], eax
0x18003ff6b  add     eax, esi
0x18003ff6d  jnz     short loc_18003FF7E
0x18003ff6f  mov     rax, [rbx]
0x18003ff72  mov     rcx, rbx
0x18003ff75  mov     rax, [rax+8]
0x18003ff79  call    _guard_dispatch_icall
0x18003ff7e  lea     rcx, [rbp+57h+var_50]
0x18003ff82  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003ff87  nop
0x18003ff88  mov     rcx, [rax]
0x18003ff8b  mov     rax, [rcx]
0x18003ff8e  lea     rdx, [rbp+57h+var_90]
0x18003ff92  mov     rax, [rax+20h]
0x18003ff96  call    _guard_dispatch_icall
0x18003ff9b  nop
0x18003ff9c  mov     r11, [rax]
0x18003ff9f  mov     rax, [r11]
0x18003ffa2  mov     rbx, [rax+50h]
0x18003ffa6  xor     r8d, r8d
0x18003ffa9  lea     rdi, aRestartrequest; "RestartRequest:"
0x18003ffb0  mov     rdx, rdi
0x18003ffb3  lea     r15, aEndtime; "EndTime"
0x18003ffba  mov     rcx, r15
0x18003ffbd  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003ffc2  cmp     rax, rdi
0x18003ffc5  jz      loc_18004010F
0x18003ffcb  sub     rax, r15
0x18003ffce  sar     rax, 1
0x18003ffd1  cmp     rax, rsi
0x18003ffd4  jz      loc_18004010F
0x18003ffda  mov     qword ptr [rbp+57h+var_C0], r15
0x18003ffde  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18003ffe2  mov     rcx, cs:?UPDATE_UX_REBOOTDOWNTIME_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT
0x18003ffe9  mov     rax, rsi
0x18003ffec  inc     rax
0x18003ffef  cmp     [rcx+rax*2], r14w
0x18003fff4  jnz     short loc_18003FFEC
0x18003fff6  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003fffa  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18003fffe  mov     rax, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x180040005  mov     qword ptr [rbp+57h+var_B0], rax
0x180040009  mov     rdx, rsi
0x18004000c  inc     rdx
0x18004000f  cmp     [rax+rdx*2], r14w
0x180040014  jnz     short loc_18004000C
0x180040016  mov     qword ptr [rbp+57h+var_B0+8], rdx
0x18004001a  movups  xmm0, [rbp+57h+var_C0]
0x18004001e  movdqu  [rbp+57h+var_60], xmm0
0x180040023  movups  xmm1, [rbp+57h+var_A0]
0x180040027  movdqu  [rbp+57h+var_70], xmm1
0x18004002c  movaps  xmm0, [rbp+57h+var_B0]
0x180040030  movdqa  [rbp+57h+var_80], xmm0
0x180040035  lea     r9, [rbp+57h+var_60]
0x180040039  lea     r8, [rbp+57h+var_70]
0x18004003d  lea     rdx, [rbp+57h+var_80]
0x180040041  mov     rcx, r11
0x180040044  mov     rax, rbx
0x180040047  call    _guard_dispatch_icall
0x18004004c  nop
0x18004004d  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x180040051  test    rbx, rbx
0x180040054  jz      short loc_18004008A
0x180040056  mov     eax, esi
0x180040058  lock xadd [rbx+8], eax
0x18004005d  add     eax, esi
0x18004005f  jnz     short loc_18004008A
0x180040061  mov     rax, [rbx]
0x180040064  mov     rcx, rbx
0x180040067  mov     rax, [rax]
0x18004006a  call    _guard_dispatch_icall
0x18004006f  mov     eax, esi
0x180040071  lock xadd [rbx+0Ch], eax
0x180040076  add     eax, esi
0x180040078  jnz     short loc_18004008A
0x18004007a  mov     rax, [rbx]
0x18004007d  mov     rcx, rbx
0x180040080  mov     rax, [rax+8]
0x180040084  call    _guard_dispatch_icall
0x180040089  nop
0x18004008a  mov     rbx, [rbp+57h+var_48]
0x18004008e  test    rbx, rbx
0x180040091  jz      short loc_1800400C6
0x180040093  mov     eax, esi
0x180040095  lock xadd [rbx+8], eax
0x18004009a  add     eax, esi
0x18004009c  jnz     short loc_1800400C6
0x18004009e  mov     rax, [rbx]
  ... truncated ...
```
