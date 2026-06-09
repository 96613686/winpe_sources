# _lambda_0b77cd35b7d31e3a3d84112dc524c3eb_::operator()(SessionState)

- ea: `0x140025428`
- end: `0x1400256b9`
- name: `??R_lambda_0b77cd35b7d31e3a3d84112dc524c3eb_@@QEBA@W4SessionState@@@Z`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140028dc0`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140006338`
- `0x140009858`
- `0x14000ccac`
- `0x140020f3c`
- `0x140025428`
- `0x14002a754`
- `0x140060f58`
- `0x1400673fc`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140025503`
- `KERNEL32!CloseHandle` at `0x140025503`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140025546`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140025546`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400254d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400254d6`

## string_xrefs

- `0x140025471`: `Session state is active, wait for shell to be ready`
- `0x14002564b`: `Session state becomes inactive, cancel timer`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_0b77cd35b7d31e3a3d84112dc524c3eb_::operator()(__int64 *a1, int a2)
{
  char *v3; // rsi
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  HANDLE hObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  char *v13; // [rsp+50h] [rbp-B0h] BYREF
  volatile signed __int32 *v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v17; // [rsp+90h] [rbp-70h] BYREF
  __int64 v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+A8h] [rbp-58h]
  __int128 v20[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v21; // [rsp+F0h] [rbp-10h]

  v18 = 0;
  v19 = 0;
  v17 = 0;
  if ( a2 )
  {
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v17,
      L"Session state becomes inactive, cancel timer",
      0x2Cu);
    wpc::UI::Logging::MonitorUILogger::LogMessage(&v17);
    std::wstring::~wstring((char **)&v17);
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*a1 + 80) + 16LL))(*(_QWORD *)(*a1 + 80), 0);
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v17,
      L"Session state is active, wait for shell to be ready",
      0x33u);
    wpc::UI::Logging::MonitorUILogger::LogMessage(&v17);
    std::wstring::~wstring((char **)&v17);
    v15 = *a1;
    v3 = (char *)operator new(0x20u);
    v13 = v3;
    *(_OWORD *)v3 = 0;
    *((_DWORD *)v3 + 2) = 1;
    *((_DWORD *)v3 + 3) = 1;
    *(_QWORD *)v3 = &std::_Ref_count_obj2<Threading::ManualEvent>::`vftable';
    hObject[0] = CreateEventW(0, 1, 0, c_pszShellLauncherLoginEvent);
    Threading::Event::Event((_QWORD *)v3 + 2, (__int64 *)hObject);
    if ( hObject[0] && (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    *((_QWORD *)v3 + 2) = &Threading::ManualEvent::`vftable';
    v13 = v3 + 16;
    v14 = (volatile signed __int32 *)v3;
    *(_OWORD *)hObject = 0;
    if ( v3 == (char *)-16LL )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v21 = 0;
    _o_wcscpy_s(v20, 32, L"LoginEvent");
    result = Threadpool::QueueWaitCallback<_lambda_18a5cb12fa3370727bcd2eb78841966f_>(
               v4,
               (__int64)&v17,
               v20,
               (__int64)&v13,
               &v15);
    v6 = *a1;
    v7 = *(_QWORD *)result;
    v8 = *(_QWORD *)(result + 8);
    *(_QWORD *)result = 0;
    *(_QWORD *)(result + 8) = 0;
    *(_QWORD *)(v6 + 64) = v7;
    v9 = *(volatile signed __int32 **)(v6 + 72);
    *(_QWORD *)(v6 + 72) = v8;
    if ( v9 )
    {
      result = (unsigned int)_InterlockedDecrement(v9 + 2);
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        result = (unsigned int)_InterlockedDecrement(v9 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
    if ( *((_QWORD *)&v17 + 1) )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        result = (unsigned int)_InterlockedDecrement(v10 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v11 = v14;
    if ( v14 )
    {
      result = (unsigned int)_InterlockedDecrement(v14 + 2);
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        result = (unsigned int)_InterlockedDecrement(v11 + 3);
        if ( !(_DWORD)result )
          return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025428  push    rbp
0x14002542a  push    rbx
0x14002542b  push    rsi
0x14002542c  push    rdi
0x14002542d  lea     rbp, [rsp-18h]
0x140025432  sub     rsp, 118h
0x140025439  mov     rax, cs:__security_cookie
0x140025440  xor     rax, rsp
0x140025443  mov     [rbp+30h+var_30], rax
0x140025447  mov     rdi, rcx
0x14002544a  xorps   xmm0, xmm0
0x14002544d  mov     [rbp+30h+var_90], 0
0x140025455  mov     [rbp+30h+var_88], 0
0x14002545d  lea     rcx, [rbp+30h+var_A0]
0x140025461  movups  [rbp+30h+var_A0], xmm0
0x140025465  test    edx, edx
0x140025467  jnz     loc_140025645
0x14002546d  lea     r8d, [rdx+33h]
0x140025471  lea     rdx, aSessionStateIs; "Session state is active, wait for shell"...
0x140025478  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002547d  nop
0x14002547e  lea     rcx, [rbp+30h+var_A0]
0x140025482  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x140025487  nop
0x140025488  lea     rcx, [rbp+30h+var_A0]
0x14002548c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025491  mov     rax, [rdi]
0x140025494  mov     [rsp+130h+var_D0], rax
0x140025499  mov     ecx, 20h ; ' '; Size
0x14002549e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400254a3  mov     rsi, rax
0x1400254a6  mov     [rsp+130h+var_E0], rax
0x1400254ab  xorps   xmm0, xmm0
0x1400254ae  movups  xmmword ptr [rax], xmm0
0x1400254b1  mov     edx, 1; bManualReset
0x1400254b6  mov     [rax+8], edx
0x1400254b9  mov     [rax+0Ch], edx
0x1400254bc  lea     rax, ??_7?$_Ref_count_obj2@VManualEvent@Threading@@@std@@6B@; const std::_Ref_count_obj2<Threading::ManualEvent>::`vftable'
0x1400254c3  mov     [rsi], rax
0x1400254c6  lea     rbx, [rsi+10h]
0x1400254ca  mov     r9, cs:?c_pszShellLauncherLoginEvent@@3QEBGEB; lpName
0x1400254d1  xor     r8d, r8d; bInitialState
0x1400254d4  xor     ecx, ecx; lpEventAttributes
0x1400254d6  call    cs:__imp_CreateEventW
0x1400254dc  mov     [rsp+130h+hObject], rax
0x1400254e1  lea     rdx, [rsp+130h+hObject]
0x1400254e6  mov     rcx, rbx
0x1400254e9  call    ??0Event@Threading@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Threading::Event::Event(std::unique_ptr<void,Private::HandleClose> &&)
0x1400254ee  nop
0x1400254ef  mov     rcx, [rsp+130h+hObject]; hObject
0x1400254f4  test    rcx, rcx
0x1400254f7  jz      short loc_140025509
0x1400254f9  lea     rax, [rcx-1]
0x1400254fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140025501  ja      short loc_140025509
0x140025503  call    cs:__imp_CloseHandle
0x140025509  lea     rax, ??_7ManualEvent@Threading@@6B@; const Threading::ManualEvent::`vftable'
0x140025510  mov     [rbx], rax
0x140025513  mov     [rsp+130h+var_E0], rbx
0x140025518  mov     [rsp+130h+var_D8], rsi
0x14002551d  xorps   xmm0, xmm0
0x140025520  movdqu  xmmword ptr [rsp+130h+hObject], xmm0
0x140025526  test    rbx, rbx
0x140025529  jz      loc_140025698
0x14002552f  mov     [rbp+30h+var_40], 0
0x140025536  lea     r8, aLoginevent; "LoginEvent"
0x14002553d  mov     edx, 20h ; ' '
0x140025542  lea     rcx, [rbp+30h+var_80]
0x140025546  call    cs:__imp__o_wcscpy_s
0x14002554c  lea     rax, [rsp+130h+var_D0]
0x140025551  mov     [rsp+130h+var_110], rax
0x140025556  lea     r9, [rsp+130h+var_E0]
0x14002555b  lea     r8, [rbp+30h+var_80]
0x14002555f  lea     rdx, [rbp+30h+var_A0]
0x140025563  call    ??$QueueWaitCallback@V_lambda_18a5cb12fa3370727bcd2eb78841966f_@@@Threadpool@@QEAA?AV?$shared_ptr@VWaitCallback@Private@@@std@@AEBUPerformanceInfo@Threading@@AEBV?$shared_ref@$$CBUIWaitable@@@stdext@@$$QEAV_lambda_18a5cb12fa3370727bcd2eb78841966f_@@AEBV?$Optional@VTimeSpan@@@@W4ComApartment@ComApartments@@@Z; Threadpool::QueueWaitCallback<_lambda_18a5cb12fa3370727bcd2eb78841966f_>(Threading::PerformanceInfo const &,stdext::shared_ref<IWaitable const> const &,_lambda_18a5cb12fa3370727bcd2eb78841966f_ &&,Optional<TimeSpan> const &,ComApartments::ComApartment)
0x140025568  mov     r8, [rdi]
0x14002556b  mov     rcx, [rax]
0x14002556e  mov     rdx, [rax+8]
0x140025572  mov     qword ptr [rax], 0
0x140025579  mov     qword ptr [rax+8], 0
0x140025581  mov     [r8+40h], rcx
0x140025585  mov     rbx, [r8+48h]
0x140025589  mov     [r8+48h], rdx
0x14002558d  or      edi, 0FFFFFFFFh
0x140025590  test    rbx, rbx
0x140025593  jz      short loc_1400255C8
0x140025595  mov     eax, edi
0x140025597  lock xadd [rbx+8], eax
0x14002559c  add     eax, edi
0x14002559e  jnz     short loc_1400255C8
0x1400255a0  mov     rax, [rbx]
0x1400255a3  mov     rcx, rbx
0x1400255a6  mov     rax, [rax]
0x1400255a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255ae  mov     eax, edi
0x1400255b0  lock xadd [rbx+0Ch], eax
0x1400255b5  add     eax, edi
0x1400255b7  jnz     short loc_1400255C8
0x1400255b9  mov     rax, [rbx]
0x1400255bc  mov     rcx, rbx
0x1400255bf  mov     rax, [rax+8]
0x1400255c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255c8  mov     rbx, qword ptr [rbp+30h+var_A0+8]
0x1400255cc  test    rbx, rbx
0x1400255cf  jz      short loc_140025605
0x1400255d1  mov     eax, edi
0x1400255d3  lock xadd [rbx+8], eax
0x1400255d8  add     eax, edi
0x1400255da  jnz     short loc_140025605
0x1400255dc  mov     rax, [rbx]
0x1400255df  mov     rcx, rbx
0x1400255e2  mov     rax, [rax]
0x1400255e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255ea  mov     eax, edi
0x1400255ec  lock xadd [rbx+0Ch], eax
0x1400255f1  add     eax, edi
0x1400255f3  jnz     short loc_140025605
0x1400255f5  mov     rax, [rbx]
0x1400255f8  mov     rcx, rbx
0x1400255fb  mov     rax, [rax+8]
0x1400255ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025604  nop
0x140025605  mov     rbx, [rsp+130h+var_D8]
0x14002560a  test    rbx, rbx
0x14002560d  jz      short loc_140025643
0x14002560f  mov     eax, edi
0x140025611  lock xadd [rbx+8], eax
0x140025616  add     eax, edi
0x140025618  jnz     short loc_140025643
0x14002561a  mov     rax, [rbx]
0x14002561d  mov     rcx, rbx
0x140025620  mov     rax, [rax]
0x140025623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025628  mov     eax, edi
0x14002562a  lock xadd [rbx+0Ch], eax
0x14002562f  add     eax, edi
0x140025631  jnz     short loc_140025643
0x140025633  mov     rax, [rbx]
0x140025636  mov     rcx, rbx
0x140025639  mov     rax, [rax+8]
0x14002563d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025642  nop
0x140025643  jmp     short loc_140025680
0x140025645  mov     r8d, 2Ch ; ','
0x14002564b  lea     rdx, aSessionStateBe; "Session state becomes inactive, cancel "...
0x140025652  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140025657  nop
0x140025658  lea     rcx, [rbp+30h+var_A0]
0x14002565c  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x140025661  nop
0x140025662  lea     rcx, [rbp+30h+var_A0]
0x140025666  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002566b  mov     rax, [rdi]
0x14002566e  mov     rcx, [rax+50h]
0x140025672  mov     rax, [rcx]
0x140025675  xor     edx, edx
0x140025677  mov     rax, [rax+10h]
0x14002567b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025680  mov     rcx, [rbp+30h+var_30]
0x140025684  xor     rcx, rsp; StackCookie
0x140025687  call    __security_check_cookie
0x14002568c  add     rsp, 118h
0x140025693  pop     rdi
0x140025694  pop     rsi
0x140025695  pop     rbx
0x140025696  pop     rbp
0x140025697  retn
0x140025698  mov     edx, 8000FFFFh; int
0x14002569d  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1400256a2  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400256a7  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400256ae  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1400256b3  call    _CxxThrowException_0
```
