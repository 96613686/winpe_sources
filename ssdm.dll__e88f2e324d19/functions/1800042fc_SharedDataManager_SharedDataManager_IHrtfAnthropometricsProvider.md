# SharedDataManager::SharedDataManager(IHrtfAnthropometricsProvider *)

- ea: `0x1800042fc`
- end: `0x18000450d`
- name: `??0SharedDataManager@@QEAA@PEAUIHrtfAnthropometricsProvider@@@Z`
- size: `529`
- prototype: `SharedDataManager *__fastcall(SharedDataManager *__hidden this, struct IHrtfAnthropometricsProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800062cc`

## callees

- `0x1800042fc`
- `0x180005144`
- `0x180007484`
- `0x180007594`
- `0x180008834`
- `0x18000a3d0`
- `0x18000c610`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004455`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000447e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004455`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000447e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004442`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000445d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000445d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800043da`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800043da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000432b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000432b`

## string_xrefs

- `0x1800044cd`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800044fb`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
SharedDataManager *__fastcall SharedDataManager::SharedDataManager(
        SharedDataManager *this,
        struct IHrtfAnthropometricsProvider *a2)
{
  int v3; // eax
  wil::details::event_watcher_state **v4; // r14
  void *v5; // rbx
  wil::details *v6; // rcx
  HANDLE Event; // rdi
  int LastErrorFailHr; // eax
  int take_hevent_ownership; // eax
  wil::details::event_watcher_state *v10; // r15
  wil::details::event_watcher_state *v11; // rdi
  DWORD LastError; // ebx
  wil::details::event_watcher_state *v13; // rbx
  int v15; // [rsp+20h] [rbp-79h]
  wil::details::event_watcher_state *v16[3]; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v18[13]; // [rsp+48h] [rbp-51h] BYREF
  _QWORD *v19; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v16[1] = this;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this, 0, 0);
  *((_QWORD *)this + 5) = 0;
  v3 = Microsoft::WRL::Details::MakeAndInitialize<DefaultHumanProvider,IHrtfAnthropometricsProvider,>();
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsoundpersonalizer.cpp",
      (const char *)(unsigned int)v3,
      (_DWORD)this + 40);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  v16[2] = (SharedDataManager *)((char *)this + 64);
  *((_QWORD *)this + 8) = &ProcessMonitor::`vftable';
  *((_QWORD *)this + 9) = this;
  v4 = (wil::details::event_watcher_state **)((char *)this + 80);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = std::_List_alloc<0,std::_List_base_types<unsigned long const>>::_Buynode0(retaddr, 0, 0);
  *((_QWORD *)this + 13) = 0;
  v18[0] = &wistd::__function::__func<_lambda_a8db8c53c4d8f1132d3b58544171a766_,void (void)>::`vftable';
  v18[1] = (char *)this + 64;
  v19 = v18;
  v16[0] = 0;
  v5 = 0;
  v15 = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v5 = Event;
    v15 = (int)Event;
    LastErrorFailHr = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
  }
  if ( LastErrorFailHr < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastErrorFailHr,
      v15);
  take_hevent_ownership = wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
                            v16,
                            v5,
                            0,
                            (__int64)v17);
  if ( take_hevent_ownership < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)take_hevent_ownership,
      0);
  if ( v4 == v16 )
  {
    v13 = v16[0];
  }
  else
  {
    v10 = v16[0];
    v11 = *v4;
    if ( *v4 )
    {
      LastError = GetLastError();
      wil::details::event_watcher_state::~event_watcher_state(v11);
      operator delete(v11);
      SetLastError(LastError);
    }
    *v4 = v10;
    v13 = 0;
  }
  if ( v13 )
  {
    wil::details::event_watcher_state::~event_watcher_state(v13);
    operator delete(v13);
  }
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *))(*v19 + 24LL))(v19);
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  return this;
}

```

## disassembly

```asm
0x1800042fc  push    rbp
0x1800042fe  push    rbx
0x1800042ff  push    rsi
0x180004300  push    rdi
0x180004301  push    r14
0x180004303  push    r15
0x180004305  lea     rbp, [rsp-2Fh]
0x18000430a  sub     rsp, 0C8h
0x180004311  mov     rax, cs:__security_cookie
0x180004318  xor     rax, rsp
0x18000431b  mov     [rbp+57h+var_38], rax
0x18000431f  mov     rsi, rcx
0x180004322  mov     [rbp+57h+var_C0], rcx
0x180004326  xor     r8d, r8d; Flags
0x180004329  xor     edx, edx; dwSpinCount
0x18000432b  call    cs:__imp_InitializeCriticalSectionEx
0x180004331  nop
0x180004332  lea     rcx, [rsi+28h]
0x180004336  mov     [rbp+57h+var_D0], rcx
0x18000433a  mov     qword ptr [rcx], 0
0x180004341  call    ??$MakeAndInitialize@VDefaultHumanProvider@@UIHrtfAnthropometricsProvider@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIHrtfAnthropometricsProvider@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<DefaultHumanProvider,IHrtfAnthropometricsProvider,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHrtfAnthropometricsProvider>>)
0x180004346  mov     rcx, [rbp+5Fh]; this
0x18000434a  test    eax, eax
0x18000434c  js      loc_1800044DF
0x180004352  mov     qword ptr [rsi+30h], 0
0x18000435a  mov     qword ptr [rsi+38h], 0
0x180004362  lea     rdi, [rsi+40h]
0x180004366  mov     [rbp+57h+var_B8], rdi
0x18000436a  lea     rax, ??_7ProcessMonitor@@6B@; const ProcessMonitor::`vftable'
0x180004371  mov     [rdi], rax
0x180004374  mov     [rdi+8], rsi
0x180004378  lea     r14, [rdi+10h]
0x18000437c  mov     qword ptr [r14], 0
0x180004383  mov     qword ptr [rdi+18h], 0
0x18000438b  mov     qword ptr [rdi+20h], 0
0x180004393  xor     r8d, r8d
0x180004396  xor     edx, edx
0x180004398  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@$$CBKV?$allocator@$$CBK@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong const>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x18000439d  mov     [rdi+18h], rax
0x1800043a1  xor     eax, eax
0x1800043a3  mov     [rdi+28h], rax
0x1800043a7  lea     rax, ??_7?$__func@V_lambda_a8db8c53c4d8f1132d3b58544171a766_@@$$A6AXXZ@__function@wistd@@6B@; const wistd::__function::__func<_lambda_a8db8c53c4d8f1132d3b58544171a766_,void (void)>::`vftable'
0x1800043ae  mov     [rbp+57h+var_A8], rax
0x1800043b2  mov     [rbp+57h+var_A0], rdi
0x1800043b6  lea     rax, [rbp+57h+var_A8]
0x1800043ba  mov     [rbp+57h+var_40], rax
0x1800043be  mov     [rbp+57h+var_C8], 0
0x1800043c6  xor     ebx, ebx
0x1800043c8  mov     [rbp+57h+var_D0], rbx
0x1800043cc  xor     edx, edx; lpName
0x1800043ce  xor     ecx, ecx; lpEventAttributes
0x1800043d0  mov     r9d, 1F0003h; dwDesiredAccess
0x1800043d6  lea     r8d, [rbx+1]; dwFlags
0x1800043da  call    cs:__imp_CreateEventExW
0x1800043e0  mov     rdi, rax
0x1800043e3  test    rax, rax
0x1800043e6  jz      short loc_1800043F9
0x1800043e8  call    cs:__imp_GetLastError
0x1800043ee  mov     rbx, rdi
0x1800043f1  mov     [rbp+57h+var_D0], rbx
0x1800043f5  xor     eax, eax
0x1800043f7  jmp     short loc_1800043FE
0x1800043f9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800043fe  test    eax, eax
0x180004400  js      loc_1800044F4
0x180004406  mov     [rbp+57h+var_D0], 0
0x18000440e  lea     r9, [rbp+57h+var_B0]
0x180004412  xor     r8d, r8d
0x180004415  mov     rdx, rbx
0x180004418  lea     rcx, [rbp+57h+var_C8]
0x18000441c  call    ?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)
0x180004421  mov     rcx, [rbp+5Fh]; this
0x180004425  test    eax, eax
0x180004427  js      loc_1800044CA
0x18000442d  lea     rax, [rbp+57h+var_C8]
0x180004431  cmp     r14, rax
0x180004434  jz      short loc_18000446A
0x180004436  mov     r15, [rbp+57h+var_C8]
0x18000443a  mov     rdi, [r14]
0x18000443d  test    rdi, rdi
0x180004440  jz      short loc_180004463
0x180004442  call    cs:__imp_GetLastError
0x180004448  mov     ebx, eax
0x18000444a  mov     rcx, rdi; this
0x18000444d  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x180004452  mov     rcx, rdi
0x180004455  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000445b  mov     ecx, ebx; dwErrCode
0x18000445d  call    cs:__imp_SetLastError
0x180004463  mov     [r14], r15
0x180004466  xor     ebx, ebx
0x180004468  jmp     short loc_18000446E
0x18000446a  mov     rbx, [rbp+57h+var_C8]
0x18000446e  test    rbx, rbx
0x180004471  jz      short loc_180004485
0x180004473  mov     rcx, rbx; this
0x180004476  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x18000447b  mov     rcx, rbx
0x18000447e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004484  nop
0x180004485  mov     rcx, [rbp+57h+var_40]
0x180004489  test    rcx, rcx
0x18000448c  jz      short loc_18000449B
0x18000448e  mov     rax, [rcx]
0x180004491  mov     rax, [rax+18h]
0x180004495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449a  nop
0x18000449b  mov     qword ptr [rsi+70h], 0
0x1800044a3  mov     qword ptr [rsi+78h], 0
0x1800044ab  mov     rax, rsi
0x1800044ae  mov     rcx, [rbp+57h+var_38]
0x1800044b2  xor     rcx, rsp; StackCookie
0x1800044b5  call    __security_check_cookie
0x1800044ba  add     rsp, 0C8h
0x1800044c1  pop     r15
0x1800044c3  pop     r14
0x1800044c5  pop     rdi
0x1800044c6  pop     rsi
0x1800044c7  pop     rbx
0x1800044c8  pop     rbp
0x1800044c9  retn
0x1800044ca  mov     r9d, eax; char *
0x1800044cd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800044d4  mov     edx, 1CBEh; void *
0x1800044d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800044df  mov     r9d, eax; char *
0x1800044e2  lea     r8, aAvcoreXaudioHr_1; "avcore\\xaudio\\hrtf\\ssdm\\lib\\spatia"...
0x1800044e9  mov     edx, 0Eh; void *
0x1800044ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800044f4  mov     rcx, [rbp+5Fh]; this
0x1800044f8  mov     r9d, eax; char *
0x1800044fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004502  mov     edx, 1CBEh; void *
0x180004507  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
