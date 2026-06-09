# wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_stop(ulong)

- ea: `0x18000a14c`
- end: `0x18000a351`
- name: `?service_stop@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXK@Z`
- size: `517`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009160`
- `0x18000a360`

## callees

- `0x180009044`
- `0x180009550`
- `0x180009d5c`
- `0x180009e00`
- `0x18000a14c`
- `0x18000a370`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a18b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a18b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1ad`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a183`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a183`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000a1d7`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000a1d7`

## string_xrefs

- `0x18000a1ec`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x18000a27c`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x18000a2a0`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x18000a2bc`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
__int64 __fastcall wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_stop(
        __int64 a1,
        unsigned int a2)
{
  void *v4; // rsi
  DWORD LastError; // ebx
  void *v6; // rbx
  DWORD v7; // esi
  __int64 v8; // r8
  const char *v9; // r9
  int v10; // eax
  const unsigned __int16 *v11; // r8
  bool v12; // r9
  __int64 v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // esi
  __int64 v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-68h]
  _QWORD v21[2]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v22[7]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(a1, 3, a2, 1025);
  v4 = *(void **)(a1 + 8);
  if ( v4 )
  {
    LastError = GetLastError();
    UnregisterWait(v4);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 8) = 0;
  v6 = *(void **)(a1 + 16);
  if ( v6 )
  {
    v7 = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(v7);
  }
  *(_QWORD *)(a1 + 16) = 0;
  v10 = CoRegisterServerShutdownDelay(0, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
      (const char *)(unsigned int)v10,
      v20);
  v13 = *(_QWORD *)(a1 + 24);
  if ( v13 )
  {
    v14 = *(_QWORD *)(v13 + 16);
    if ( v14 )
    {
      v21[0] = *(_QWORD *)(a1 + 24);
      v21[1] = &WideCharStr;
      v22[0] = 0;
      v22[1] = v21;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *))(*(_QWORD *)v14 + 24LL))(
              v14,
              _lambda_2c2fbf36fecb06923c3b164e3be181e4_::_lambda_invoker_cdecl_,
              v22,
              &IID_IContextCallback);
      v16 = v15;
      if ( v15 >= 0 )
        v16 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x96,
          (int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
          (const char *)(unsigned int)v15);
      if ( v16 >= 0 )
      {
        v17 = *(_QWORD *)(v13 + 16);
        *(_QWORD *)(v13 + 16) = 0;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69,
          (int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
          (const char *)(unsigned int)v16);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
          (const char *)(unsigned int)v16,
          5);
      }
    }
    LOBYTE(v11) = 1;
    Microsoft::WRL::Details::TerminateMap(
      *(Microsoft::WRL::Details **)(a1 + 24),
      (struct Microsoft::WRL::Details::ModuleBase *)&WideCharStr,
      v11,
      v12);
    v18 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 24);
    *(_QWORD *)(a1 + 24) = 0;
    if ( v18 )
      (**v18)(v18, 1);
  }
  result = wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(
             a1,
             1,
             a2,
             1025);
  *(_QWORD *)(a1 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x18000a14c  push    rbx
0x18000a14e  push    rbp
0x18000a14f  push    rsi
0x18000a150  push    rdi
0x18000a151  push    r13
0x18000a153  sub     rsp, 60h
0x18000a157  mov     ebp, edx
0x18000a159  mov     rdi, rcx
0x18000a15c  mov     r9d, 401h
0x18000a162  mov     r8d, edx
0x18000a165  mov     edx, 3
0x18000a16a  call    ?update_service_status@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXKKK@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(ulong,ulong,ulong)
0x18000a16f  mov     rsi, [rdi+8]
0x18000a173  test    rsi, rsi
0x18000a176  jz      short loc_18000A191
0x18000a178  call    cs:__imp_GetLastError
0x18000a17e  mov     ebx, eax
0x18000a180  mov     rcx, rsi; WaitHandle
0x18000a183  call    cs:__imp_UnregisterWait
0x18000a189  mov     ecx, ebx; dwErrCode
0x18000a18b  call    cs:__imp_SetLastError
0x18000a191  mov     qword ptr [rdi+8], 0
0x18000a199  mov     rbx, [rdi+10h]
0x18000a19d  test    rbx, rbx
0x18000a1a0  jz      short loc_18000A1CB
0x18000a1a2  call    cs:__imp_GetLastError
0x18000a1a8  mov     esi, eax
0x18000a1aa  mov     rcx, rbx; hObject
0x18000a1ad  call    cs:__imp_CloseHandle
0x18000a1b3  mov     rcx, [rsp+88h]; this
0x18000a1bb  test    eax, eax
0x18000a1bd  jz      loc_18000A346
0x18000a1c3  mov     ecx, esi; dwErrCode
0x18000a1c5  call    cs:__imp_SetLastError
0x18000a1cb  mov     qword ptr [rdi+10h], 0
0x18000a1d3  xor     edx, edx
0x18000a1d5  xor     ecx, ecx
0x18000a1d7  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000a1dd  mov     rcx, [rsp+88h]; this
0x18000a1e5  test    eax, eax
0x18000a1e7  jns     short loc_18000A1FD
0x18000a1e9  mov     r9d, eax; char *
0x18000a1ec  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a1f3  mov     edx, 13Ah; void *
0x18000a1f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a1fd  mov     rbx, [rdi+18h]
0x18000a201  test    rbx, rbx
0x18000a204  jz      loc_18000A31D
0x18000a20a  mov     rcx, [rbx+10h]
0x18000a20e  lea     r13, WideCharStr
0x18000a215  test    rcx, rcx
0x18000a218  jz      loc_18000A2ED
0x18000a21e  mov     [rsp+88h+var_48], rbx
0x18000a223  mov     [rsp+88h+var_40], r13
0x18000a228  mov     [rsp+88h+var_38], 0
0x18000a231  lea     rax, [rsp+88h+var_48]
0x18000a236  mov     [rsp+88h+var_30], rax
0x18000a23b  mov     rax, [rcx]
0x18000a23e  mov     [rsp+88h+var_60], 0
0x18000a247  mov     [rsp+88h+var_68], 5; int
0x18000a24f  lea     r9, IID_IContextCallback
0x18000a256  lea     r8, [rsp+88h+var_38]
0x18000a25b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_2c2fbf36fecb06923c3b164e3be181e4_@@CA@PEAUtagComCallData@@@Z; _lambda_2c2fbf36fecb06923c3b164e3be181e4_::_lambda_invoker_cdecl_(tagComCallData *)
0x18000a262  mov     rax, [rax+18h]
0x18000a266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a26b  mov     esi, eax
0x18000a26d  test    eax, eax
0x18000a26f  jns     short loc_18000A28F
0x18000a271  mov     rcx, [rsp+88h]; this
0x18000a279  mov     r9d, eax; char *
0x18000a27c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a283  mov     edx, 96h; void *
0x18000a288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a28d  jmp     short loc_18000A291
0x18000a28f  xor     esi, esi
0x18000a291  test    esi, esi
0x18000a293  jns     short loc_18000A2CF
0x18000a295  mov     rcx, [rsp+88h]; this
0x18000a29d  mov     r9d, esi; char *
0x18000a2a0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a2a7  mov     edx, 69h ; 'i'; void *
0x18000a2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2b1  mov     rcx, [rsp+88h]; this
0x18000a2b9  mov     r9d, esi; char *
0x18000a2bc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a2c3  mov     edx, 141h; void *
0x18000a2c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a2cd  jmp     short loc_18000A2ED
0x18000a2cf  mov     rcx, [rbx+10h]
0x18000a2d3  mov     qword ptr [rbx+10h], 0
0x18000a2db  test    rcx, rcx
0x18000a2de  jz      short loc_18000A2ED
0x18000a2e0  mov     rax, [rcx]
0x18000a2e3  mov     rax, [rax+10h]
0x18000a2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ec  nop
0x18000a2ed  mov     r8b, 1; unsigned __int16 *
0x18000a2f0  mov     rdx, r13; struct Microsoft::WRL::Details::ModuleBase *
0x18000a2f3  mov     rcx, [rdi+18h]; this
0x18000a2f7  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000a2fc  mov     rcx, [rdi+18h]
0x18000a300  mov     qword ptr [rdi+18h], 0
0x18000a308  test    rcx, rcx
0x18000a30b  jz      short loc_18000A31D
0x18000a30d  mov     rax, [rcx]
0x18000a310  mov     edx, 1
0x18000a315  mov     rax, [rax]
0x18000a318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31d  mov     r9d, 401h
0x18000a323  mov     r8d, ebp
0x18000a326  mov     edx, 1
0x18000a32b  mov     rcx, rdi
0x18000a32e  call    ?update_service_status@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXKKK@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(ulong,ulong,ulong)
0x18000a333  mov     qword ptr [rdi+20h], 0
0x18000a33b  add     rsp, 60h
0x18000a33f  pop     r13
0x18000a341  pop     rdi
0x18000a342  pop     rsi
0x18000a343  pop     rbp
0x18000a344  pop     rbx
0x18000a345  retn
0x18000a346  mov     edx, 0A0Bh; void *
0x18000a34b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
