# Windows::Reboot::WaitForStorageReserveInitialization(void)

- ea: `0x180054330`
- end: `0x18005459c`
- name: `?WaitForStorageReserveInitialization@Reboot@Windows@@UEAAXXZ`
- size: `620`
- prototype: `void __fastcall(Windows::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update`

## callees

- `0x180006a58`
- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x18002765c`
- `0x180028330`
- `0x18003b360`
- `0x180045bd4`
- `0x180053f90`
- `0x180054330`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180054358`
- `msvcp_win!_Xtime_get_ticks` at `0x18005436f`
- `msvcp_win!_Xtime_get_ticks` at `0x180054358`
- `msvcp_win!_Xtime_get_ticks` at `0x18005436f`

## string_xrefs

- `0x18005456d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\reboot.cpp`
- `0x1800543c1`: `TiAttemptedInitialization`
- `0x18005455b`: `Timed out waiting for Trusted Installer Signal - TiAttemptedInitialization`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Reboot::WaitForStorageReserveInitialization(Windows::Reboot *this)
{
  __int64 v1; // rsi
  _QWORD *System; // rax
  __int64 **v3; // rax
  __int64 *v4; // rbx
  __int64 v5; // rdi
  char v6; // di
  const char *v7; // r9
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rdx
  _QWORD *v11; // rbx
  DWORD v12; // eax
  int v13; // [rsp+20h] [rbp-E8h]
  const char *v14; // [rsp+28h] [rbp-E0h]
  __int64 v15; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v19[8]; // [rsp+50h] [rbp-B8h] BYREF
  volatile signed __int32 *v20; // [rsp+58h] [rbp-B0h]
  _BYTE v21[8]; // [rsp+60h] [rbp-A8h] BYREF
  volatile signed __int32 *v22; // [rsp+68h] [rbp-A0h]
  _OWORD v23[2]; // [rsp+70h] [rbp-98h] BYREF
  _OWORD v24[2]; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v25[2]; // [rsp+B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v16 = 5;
  v1 = _Xtime_get_ticks() + 9000000000LL;
  try
  {
    while ( _Xtime_get_ticks() < v1 )
    {
      System = (_QWORD *)SystemInterface::Service::GetSystem(v21);
      v3 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 32LL))(*System, v19);
      v4 = *v3;
      v5 = **v3;
      memset(v25, 0, sizeof(v25));
      std::wstring::_Construct<1,unsigned short const *>(v25, L"TiAttemptedInitialization", 25);
      memset(v24, 0, sizeof(v24));
      std::wstring::_Construct<1,unsigned short const *>(v24, &psz, 0);
      memset(v23, 0, sizeof(v23));
      std::wstring::_Construct<1,unsigned short const *>(v23, L"ReserveManager", 14);
      LOBYTE(v13) = 0;
      v6 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, _OWORD *, _OWORD *, int))(v5 + 48))(v4, v23, v24, v25, v13);
      std::wstring::_Tidy_deallocate(v23);
      std::wstring::_Tidy_deallocate(v24);
      std::wstring::_Tidy_deallocate(v25);
      v8 = v20;
      if ( v20 )
      {
        if ( !_InterlockedDecrement(v20 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( !_InterlockedDecrement(v8 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
      v9 = v22;
      if ( v22 )
      {
        if ( !_InterlockedDecrement(v22 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( !_InterlockedDecrement(v9 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
      if ( v6 )
        return;
      v11 = (_QWORD *)std::_To_absolute_time<__int64,std::ratio<1,1>>(v18, &v16);
      while ( 1 )
      {
        std::chrono::steady_clock::now(&v15, v10);
        if ( v15 >= *v11 )
          break;
        v17 = *v11 - v15;
        v12 = std::_Clamped_rel_time_ms_count<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(&v17);
        Thrd_sleep_for(v12);
      }
    }
    wil::details::in1diag3::Log_Win32Msg(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\reboot.cpp",
      (const char *)0x5B4,
      (unsigned int)"Timed out waiting for Trusted Installer Signal - TiAttemptedInitialization",
      v14);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\reboot.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x180054330  push    rbx
0x180054332  push    rsi
0x180054333  push    rdi
0x180054334  push    r14
0x180054336  sub     rsp, 0E8h
0x18005433d  mov     rax, cs:__security_cookie
0x180054344  xor     rax, rsp
0x180054347  mov     [rsp+108h+var_38], rax
0x18005434f  mov     [rsp+108h+var_D0], 5
0x180054358  call    cs:__imp__Xtime_get_ticks
0x18005435e  mov     rsi, 218711A00h
0x180054368  add     rsi, rax
0x18005436b  or      r14d, 0FFFFFFFFh
0x18005436f  call    cs:__imp__Xtime_get_ticks
0x180054375  cmp     rax, rsi
0x180054378  jge     loc_180054553
0x18005437e  lea     rcx, [rsp+108h+var_A8]
0x180054383  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180054388  nop
0x180054389  mov     rcx, [rax]
0x18005438c  mov     rax, [rcx]
0x18005438f  lea     rdx, [rsp+108h+var_B8]
0x180054394  mov     rax, [rax+20h]
0x180054398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005439d  nop
0x18005439e  mov     rbx, [rax]
0x1800543a1  mov     rdi, [rbx]
0x1800543a4  xorps   xmm0, xmm0
0x1800543a7  movups  [rsp+108h+var_58], xmm0
0x1800543af  xorps   xmm1, xmm1
0x1800543b2  movdqu  [rsp+108h+var_48], xmm1
0x1800543bb  mov     r8d, 19h
0x1800543c1  lea     rdx, aTiattemptedini; "TiAttemptedInitialization"
0x1800543c8  lea     rcx, [rsp+108h+var_58]
0x1800543d0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800543d5  nop
0x1800543d6  xorps   xmm0, xmm0
0x1800543d9  movups  [rsp+108h+var_78], xmm0
0x1800543e1  xorps   xmm1, xmm1
0x1800543e4  movdqu  [rsp+108h+var_68], xmm1
0x1800543ed  xor     r8d, r8d
0x1800543f0  lea     rdx, psz
0x1800543f7  lea     rcx, [rsp+108h+var_78]
0x1800543ff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180054404  nop
0x180054405  xorps   xmm0, xmm0
0x180054408  movups  [rsp+108h+var_98], xmm0
0x18005440d  xorps   xmm1, xmm1
0x180054410  movdqu  [rsp+108h+var_88], xmm1
0x180054419  mov     r8d, 0Eh
0x18005441f  lea     rdx, aReservemanager; "ReserveManager"
0x180054426  lea     rcx, [rsp+108h+var_98]
0x18005442b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180054430  nop
0x180054431  mov     byte ptr [rsp+108h+var_E8], 0
0x180054436  lea     r9, [rsp+108h+var_58]
0x18005443e  lea     r8, [rsp+108h+var_78]
0x180054446  lea     rdx, [rsp+108h+var_98]
0x18005444b  mov     rcx, rbx
0x18005444e  mov     rax, [rdi+30h]
0x180054452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054457  mov     dil, al
0x18005445a  lea     rcx, [rsp+108h+var_98]
0x18005445f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054464  nop
0x180054465  lea     rcx, [rsp+108h+var_78]
0x18005446d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054472  nop
0x180054473  lea     rcx, [rsp+108h+var_58]
0x18005447b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054480  nop
0x180054481  mov     rbx, [rsp+108h+var_B0]
0x180054486  test    rbx, rbx
0x180054489  jz      short loc_1800544C3
0x18005448b  mov     eax, r14d
0x18005448e  lock xadd [rbx+8], eax
0x180054493  add     eax, r14d
0x180054496  jnz     short loc_1800544C3
0x180054498  mov     rax, [rbx]
0x18005449b  mov     rcx, rbx
0x18005449e  mov     rax, [rax]
0x1800544a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544a6  mov     eax, r14d
0x1800544a9  lock xadd [rbx+0Ch], eax
0x1800544ae  add     eax, r14d
0x1800544b1  jnz     short loc_1800544C3
0x1800544b3  mov     rax, [rbx]
0x1800544b6  mov     rcx, rbx
0x1800544b9  mov     rax, [rax+8]
0x1800544bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544c2  nop
0x1800544c3  mov     rbx, [rsp+108h+var_A0]
0x1800544c8  test    rbx, rbx
0x1800544cb  jz      short loc_180054504
0x1800544cd  mov     eax, r14d
0x1800544d0  lock xadd [rbx+8], eax
0x1800544d5  add     eax, r14d
0x1800544d8  jnz     short loc_180054504
0x1800544da  mov     rax, [rbx]
0x1800544dd  mov     rcx, rbx
0x1800544e0  mov     rax, [rax]
0x1800544e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544e8  mov     eax, r14d
0x1800544eb  lock xadd [rbx+0Ch], eax
0x1800544f0  add     eax, r14d
0x1800544f3  jnz     short loc_180054504
0x1800544f5  mov     rax, [rbx]
0x1800544f8  mov     rcx, rbx
0x1800544fb  mov     rax, [rax+8]
0x1800544ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054504  test    dil, dil
0x180054507  jz      short loc_18005450B
0x180054509  jmp     short loc_18005457F
0x18005450b  lea     rdx, [rsp+108h+var_D0]
0x180054510  lea     rcx, [rsp+108h+var_C0]
0x180054515  call    ??$_To_absolute_time@_JU?$ratio@$00$00@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@0@@Z
0x18005451a  mov     rbx, rax
0x18005451d  lea     rcx, [rsp+108h+var_D8]
0x180054522  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180054527  mov     rcx, [rbx]
0x18005452a  cmp     [rsp+108h+var_D8], rcx
0x18005452f  jge     loc_18005436F
0x180054535  sub     rcx, [rsp+108h+var_D8]
0x18005453a  mov     [rsp+108h+var_C8], rcx
0x18005453f  lea     rcx, [rsp+108h+var_C8]
0x180054544  call    ??$_Clamped_rel_time_ms_count@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@std@@YA?AU_Clamped_rel_time_ms_count_result@0@AEBV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@0@@Z; std::_Clamped_rel_time_ms_count<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>> const &)
0x180054549  mov     rcx, rax; dwMilliseconds
0x18005454c  call    _Thrd_sleep_for
0x180054551  jmp     short loc_18005451D
0x180054553  mov     rcx, [rsp+108h]; this
0x18005455b  lea     rax, aTimedOutWaitin; "Timed out waiting for Trusted Installer"...
0x180054562  mov     qword ptr [rsp+108h+var_E8], rax; unsigned int
0x180054567  mov     r9d, 5B4h; char *
0x18005456d  lea     r8, aOnecoreEnduser_27; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180054574  mov     edx, 9Bh; void *
0x180054579  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18005457e  nop
0x18005457f  mov     rcx, [rsp+108h+var_38]
0x180054587  xor     rcx, rsp; StackCookie
0x18005458a  call    __security_check_cookie
0x18005458f  add     rsp, 0E8h
0x180054596  pop     r14
0x180054598  pop     rdi
0x180054599  pop     rsi
0x18005459a  pop     rbx
0x18005459b  retn
```
