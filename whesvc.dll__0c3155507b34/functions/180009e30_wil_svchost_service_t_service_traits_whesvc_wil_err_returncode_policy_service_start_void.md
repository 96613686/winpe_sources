# wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_start(void)

- ea: `0x180009e30`
- end: `0x18000a146`
- name: `?service_start@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAJXZ`
- size: `790`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009160`

## callees

- `0x18000370c`
- `0x180008478`
- `0x180009044`
- `0x180009068`
- `0x180009d5c`
- `0x180009d78`
- `0x180009e30`
- `0x18000a370`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ea5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ea5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009e65`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009e65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009fb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009fb3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a0b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a0b1`
- `combase!__imp_CoGetSharedServiceId` at `0x180009f3d`
- `combase!__imp_CoGetSharedServiceId` at `0x180009f3d`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180009eb8`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180009eb8`

## string_xrefs

- `0x180009edb`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x180009fca`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x18000a04d`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x18000a076`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x18000a0fe`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_start(_QWORD *a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rsi
  void *v4; // rbx
  DWORD LastError; // ebp
  unsigned int v6; // r8d
  const char *v7; // r9
  int LastErrorFailHr; // ebx
  __int64 v9; // rdx
  Microsoft::WRL::Details *v11; // rax
  Microsoft::WRL::Details *v12; // rbx
  int SharedServiceId; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  __int64 v17; // rbp
  _QWORD *v18; // rsi
  HRESULT Instance; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 (__fastcall *v22)(_QWORD *, const wchar_t *, __int64, __int64 (__fastcall *)()); // r15
  __int64 v23; // r14
  void *v24; // rbp
  DWORD v25; // ebx
  unsigned int v26; // eax
  int ppv; // [rsp+20h] [rbp-78h]
  int ppva; // [rsp+20h] [rbp-78h]
  int ppvb; // [rsp+20h] [rbp-78h]
  _QWORD v30[2]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v31[9]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(a1, 2, 0, 1025);
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v4 = (void *)a1[2];
    if ( v4 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v4) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
      SetLastError(LastError);
    }
    a1[2] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    if ( LastErrorFailHr < 0 )
    {
      v9 = 285;
      goto LABEL_10;
    }
  }
  LastErrorFailHr = CoRegisterServerShutdownDelay(a1[2], 5000);
  if ( LastErrorFailHr < 0 )
  {
    v9 = 289;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
      (const char *)(unsigned int)LastErrorFailHr,
      ppv);
    return LastErrorFailHr;
  }
  v11 = (Microsoft::WRL::Details *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    Microsoft::WRL::Details::ModuleBase::module_ = v11;
    *((_QWORD *)v11 + 1) = 0;
    *(_QWORD *)v11 = &wil::SvchostModule::`vftable';
    *((_QWORD *)v11 + 2) = 0;
    *((_DWORD *)v11 + 6) = 0;
    SharedServiceId = CoGetSharedServiceId();
    if ( SharedServiceId < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v14, v15, (const char *)(unsigned int)SharedServiceId, ppv);
  }
  else
  {
    v12 = 0;
  }
  v16 = (void (__fastcall ***)(_QWORD, __int64))a1[3];
  a1[3] = v12;
  if ( v16 )
    (**v16)(v16, 1);
  v17 = a1[3];
  if ( !v17 )
  {
    LastErrorFailHr = -2147024882;
    v9 = 293;
    goto LABEL_10;
  }
  v18 = (_QWORD *)(v17 + 16);
  if ( !*(_QWORD *)(v17 + 16) )
  {
    *v18 = 0;
    Instance = CoCreateInstance(
                 &CLSID_ContextSwitcher,
                 0,
                 1u,
                 &GUID_000001da_0000_0000_c000_000000000046,
                 (LPVOID *)(v17 + 16));
    LastErrorFailHr = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
        (const char *)(unsigned int)Instance,
        ppva);
      v20 = 70;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
        (const char *)(unsigned int)LastErrorFailHr,
        ppvb);
      v9 = 294;
      goto LABEL_10;
    }
  }
  v30[0] = v17;
  v30[1] = &WideCharStr;
  v31[0] = 0;
  v31[1] = v30;
  ppvb = 5;
  v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD (*)(struct tagComCallData *), _QWORD *, GUID *))(*(_QWORD *)*v18 + 24LL))(
          *v18,
          _lambda_e087c5742fecdb49d630a755e1ac6f19_::_lambda_invoker_cdecl_,
          v31,
          &IID_IContextCallback);
  LastErrorFailHr = v21;
  if ( v21 >= 0 )
    LastErrorFailHr = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
      (const char *)(unsigned int)v21,
      5);
  if ( LastErrorFailHr < 0 )
  {
    v20 = 82;
    goto LABEL_27;
  }
  v22 = *(__int64 (__fastcall **)(_QWORD *, const wchar_t *, __int64, __int64 (__fastcall *)()))(*a1 + 192LL);
  v23 = a1[2];
  v24 = (void *)a1[1];
  if ( v24 )
  {
    v25 = GetLastError();
    UnregisterWait(v24);
    SetLastError(v25);
  }
  a1[1] = 0;
  v26 = v22(
          a1 + 1,
          L"whesvc",
          v23,
          wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_stop_callback_proc);
  if ( v26 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x129,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
             (const char *)v26,
             (unsigned int)a1);
  wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(a1, 4, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180009e30  push    rbx
0x180009e32  push    rbp
0x180009e33  push    rsi
0x180009e34  push    rdi
0x180009e35  push    r14
0x180009e37  push    r15
0x180009e39  sub     rsp, 68h
0x180009e3d  mov     rdi, rcx
0x180009e40  mov     r9d, 401h
0x180009e46  xor     r8d, r8d
0x180009e49  lea     edx, [r8+2]
0x180009e4d  call    ?update_service_status@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXKKK@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(ulong,ulong,ulong)
0x180009e52  mov     r9d, 1F0003h; dwDesiredAccess
0x180009e58  mov     r14d, 1
0x180009e5e  mov     r8d, r14d; dwFlags
0x180009e61  xor     edx, edx; lpName
0x180009e63  xor     ecx, ecx; lpEventAttributes
0x180009e65  call    cs:__imp_CreateEventExW
0x180009e6b  mov     rsi, rax
0x180009e6e  test    rax, rax
0x180009e71  jz      short loc_180009ECB
0x180009e73  call    cs:__imp_GetLastError
0x180009e79  mov     rbx, [rdi+10h]
0x180009e7d  test    rbx, rbx
0x180009e80  jz      short loc_180009EAB
0x180009e82  call    cs:__imp_GetLastError
0x180009e88  mov     ebp, eax
0x180009e8a  mov     rcx, rbx; hObject
0x180009e8d  call    cs:__imp_CloseHandle
0x180009e93  mov     rcx, [rsp+98h]; this
0x180009e9b  test    eax, eax
0x180009e9d  jz      loc_18000A132
0x180009ea3  mov     ecx, ebp; dwErrCode
0x180009ea5  call    cs:__imp_SetLastError
0x180009eab  mov     [rdi+10h], rsi
0x180009eaf  mov     edx, 1388h
0x180009eb4  mov     rcx, [rdi+10h]
0x180009eb8  call    cs:__imp_CoRegisterServerShutdownDelay
0x180009ebe  mov     ebx, eax
0x180009ec0  test    eax, eax
0x180009ec2  jns     short loc_180009EF9
0x180009ec4  mov     edx, 121h
0x180009ec9  jmp     short loc_180009EDB
0x180009ecb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009ed0  mov     ebx, eax
0x180009ed2  test    eax, eax
0x180009ed4  jns     short loc_180009EAF
0x180009ed6  mov     edx, 11Dh; void *
0x180009edb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180009ee2  mov     r9d, ebx; char *
0x180009ee5  mov     rcx, [rsp+98h]; this
0x180009eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ef2  mov     eax, ebx
0x180009ef4  jmp     loc_18000A125
0x180009ef9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009f00  mov     ecx, 20h ; ' '; unsigned __int64
0x180009f05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009f0a  mov     rbx, rax
0x180009f0d  test    rax, rax
0x180009f10  jz      short loc_180009F55
0x180009f12  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, rax; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009f19  mov     qword ptr [rax+8], 0
0x180009f21  lea     rax, ??_7SvchostModule@wil@@6B@; const wil::SvchostModule::`vftable'
0x180009f28  mov     [rbx], rax
0x180009f2b  mov     qword ptr [rbx+10h], 0
0x180009f33  lea     rcx, [rbx+18h]
0x180009f37  mov     dword ptr [rcx], 0
0x180009f3d  call    cs:__imp_CoGetSharedServiceId
0x180009f43  mov     rcx, [rsp+98h]; this
0x180009f4b  test    eax, eax
0x180009f4d  js      loc_18000A13D
0x180009f53  jmp     short loc_180009F57
0x180009f55  xor     ebx, ebx
0x180009f57  mov     rcx, [rdi+18h]
0x180009f5b  mov     [rdi+18h], rbx
0x180009f5f  test    rcx, rcx
0x180009f62  jz      short loc_180009F72
0x180009f64  mov     rax, [rcx]
0x180009f67  mov     edx, r14d
0x180009f6a  mov     rax, [rax]
0x180009f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f72  mov     rbp, [rdi+18h]
0x180009f76  test    rbp, rbp
0x180009f79  jnz     short loc_180009F8A
0x180009f7b  mov     ebx, 8007000Eh
0x180009f80  mov     edx, 125h
0x180009f85  jmp     loc_180009EDB
0x180009f8a  lea     rsi, [rbp+10h]
0x180009f8e  cmp     qword ptr [rsi], 0
0x180009f92  jnz     short loc_180009FE5
0x180009f94  mov     qword ptr [rsi], 0
0x180009f9b  mov     [rsp+98h+ppv], rsi; int
0x180009fa0  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180009fa7  mov     r8d, r14d; dwClsContext
0x180009faa  xor     edx, edx; pUnkOuter
0x180009fac  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180009fb3  call    cs:__imp_CoCreateInstance
0x180009fb9  mov     ebx, eax
0x180009fbb  test    eax, eax
0x180009fbd  jns     short loc_180009FE5
0x180009fbf  mov     rcx, [rsp+98h]; this
0x180009fc7  mov     r9d, eax; char *
0x180009fca  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180009fd1  mov     edx, 77h ; 'w'; void *
0x180009fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fdb  mov     edx, 46h ; 'F'
0x180009fe0  jmp     loc_18000A06B
0x180009fe5  mov     [rsp+98h+var_58], rbp
0x180009fea  lea     rax, WideCharStr
0x180009ff1  mov     [rsp+98h+var_50], rax
0x180009ff6  mov     [rsp+98h+var_48], 0
0x180009fff  lea     rax, [rsp+98h+var_58]
0x18000a004  mov     [rsp+98h+var_40], rax
0x18000a009  mov     rcx, [rsi]
0x18000a00c  mov     rax, [rcx]
0x18000a00f  mov     [rsp+98h+var_70], 0
0x18000a018  mov     dword ptr [rsp+98h+ppv], 5; int
0x18000a020  lea     r9, IID_IContextCallback
0x18000a027  lea     r8, [rsp+98h+var_48]
0x18000a02c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_e087c5742fecdb49d630a755e1ac6f19_@@CA@PEAUtagComCallData@@@Z; _lambda_e087c5742fecdb49d630a755e1ac6f19_::_lambda_invoker_cdecl_(tagComCallData *)
0x18000a033  mov     rax, [rax+18h]
0x18000a037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a03c  mov     ebx, eax
0x18000a03e  test    eax, eax
0x18000a040  jns     short loc_18000A060
0x18000a042  mov     rcx, [rsp+98h]; this
0x18000a04a  mov     r9d, eax; char *
0x18000a04d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a054  mov     edx, 96h; void *
0x18000a059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a05e  jmp     short loc_18000A062
0x18000a060  xor     ebx, ebx
0x18000a062  test    ebx, ebx
0x18000a064  jns     short loc_18000A08C
0x18000a066  mov     edx, 52h ; 'R'; void *
0x18000a06b  mov     r9d, ebx; char *
0x18000a06e  mov     rcx, [rsp+98h]; this
0x18000a076  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a07d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a082  mov     edx, 126h
0x18000a087  jmp     loc_180009EDB
0x18000a08c  mov     rax, [rdi]
0x18000a08f  mov     r15, [rax+0C0h]
0x18000a096  mov     r14, [rdi+10h]
0x18000a09a  lea     rsi, [rdi+8]
0x18000a09e  mov     rbp, [rsi]
0x18000a0a1  test    rbp, rbp
0x18000a0a4  jz      short loc_18000A0BF
0x18000a0a6  call    cs:__imp_GetLastError
0x18000a0ac  mov     ebx, eax
0x18000a0ae  mov     rcx, rbp; WaitHandle
0x18000a0b1  call    cs:__imp_UnregisterWait
0x18000a0b7  mov     ecx, ebx; dwErrCode
0x18000a0b9  call    cs:__imp_SetLastError
0x18000a0bf  mov     qword ptr [rsi], 0
0x18000a0c6  mov     dword ptr [rsp+98h+var_70], 8
0x18000a0ce  mov     [rsp+98h+ppv], rdi; unsigned int
0x18000a0d3  lea     r9, ?service_stop_callback_proc@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@CAXPEAXE@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_stop_callback_proc(void *,uchar)
0x18000a0da  mov     r8, r14
0x18000a0dd  lea     rdx, aWhesvc_0; "whesvc"
0x18000a0e4  mov     rcx, rsi
0x18000a0e7  mov     rax, r15
0x18000a0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0ef  test    eax, eax
0x18000a0f1  jz      short loc_18000A111
0x18000a0f3  mov     rcx, [rsp+98h]; this
0x18000a0fb  mov     r9d, eax; char *
0x18000a0fe  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x18000a105  mov     edx, 129h; void *
0x18000a10a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a10f  jmp     short loc_18000A125
0x18000a111  xor     r9d, r9d
0x18000a114  xor     r8d, r8d
0x18000a117  lea     edx, [r9+4]
0x18000a11b  mov     rcx, rdi
0x18000a11e  call    ?update_service_status@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXKKK@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(ulong,ulong,ulong)
0x18000a123  xor     eax, eax
0x18000a125  add     rsp, 68h
0x18000a129  pop     r15
0x18000a12b  pop     r14
0x18000a12d  pop     rdi
0x18000a12e  pop     rsi
0x18000a12f  pop     rbp
0x18000a130  pop     rbx
0x18000a131  retn
0x18000a132  mov     edx, 0A0Bh; void *
0x18000a137  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a13d  mov     r9d, eax; char *
0x18000a140  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
