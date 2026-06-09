# ServiceMain(ulong,ushort * *)

- ea: `0x180009160`
- end: `0x18000924f`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `239`
- prototype: `void __fastcall(__int64, unsigned __int16 **, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180006c58`
- `0x180008ba8`
- `0x180009024`
- `0x180009044`
- `0x180009160`
- `0x180009e00`
- `0x180009e30`
- `0x18000a14c`
- `0x18000a370`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800091a4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800091a4`

## string_xrefs

- `0x180009179`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x1800091bb`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x1800091eb`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`
- `0x180009212`: `pcshell\base\whesvc\dll\whesvc.cpp`
- `0x18000916b`: `Clients must implement SvchostPushServiceGlobals() and call set_service_globals() before calling service_main().`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2, __int64 a3, __int64 a4, int a5)
{
  const char *v5; // r9
  int LastError; // ebx
  int v7; // eax
  int v8; // [rsp+20h] [rbp-18h]
  char v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::in1diag3::FailFast_IfNullMsg<_SVCHOST_GLOBAL_DATA *,0>(
    (int)retaddr,
    184,
    (int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
    g_service,
    (void *)"Clients must implement SvchostPushServiceGlobals() and call set_service_globals() before calling service_main().",
    v9);
  qword_180034DC0 = (__int64)RegisterServiceCtrlHandlerExW(
                               L"whesvc",
                               _lambda_08bc7f71881c94ab483e8c6cd713e9ef_::_lambda_invoker_cdecl_,
                               &g_service);
  if ( !qword_180034DC0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC3,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
                  v5);
    if ( LastError >= 0 )
      return;
    goto LABEL_6;
  }
  v7 = wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_start((unsigned int)&g_service);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
      (const char *)(unsigned int)v7,
      v8);
LABEL_6:
    wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_stop(
      &g_service,
      (unsigned int)LastError);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)9,
      (unsigned int)"pcshell\\base\\whesvc\\dll\\whesvc.cpp",
      (const char *)(unsigned int)LastError,
      a5);
    return;
  }
  PostServiceMainCallback();
  wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(
    &g_service,
    4,
    0,
    1025);
}

```

## disassembly

```asm
0x180009160  push    rbx
0x180009162  sub     rsp, 30h
0x180009166  mov     rcx, [rsp+38h]; int
0x18000916b  lea     rax, aClientsMustImp; "Clients must implement SvchostPushServi"...
0x180009172  mov     r9, cs:?g_service@@3V?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@A; int
0x180009179  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180009180  mov     edx, 0B8h; int
0x180009185  mov     [rsp+38h+var_18], rax; int
0x18000918a  call    ??$FailFast_IfNullMsg@PEAU_SVCHOST_GLOBAL_DATA@@$0A@@in1diag3@details@wil@@YAPEAU_SVCHOST_GLOBAL_DATA@@PEAXIPEBDPEAU3@1ZZ; wil::details::in1diag3::FailFast_IfNullMsg<_SVCHOST_GLOBAL_DATA *,0>(void *,uint,char const *,_SVCHOST_GLOBAL_DATA *,char const *,...)
0x18000918f  lea     r8, ?g_service@@3V?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@A; lpContext
0x180009196  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_08bc7f71881c94ab483e8c6cd713e9ef_@@CA@KKPEAX0@Z; lpHandlerProc
0x18000919d  lea     rcx, aWhesvc_0; "whesvc"
0x1800091a4  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800091aa  mov     cs:qword_180034DC0, rax
0x1800091b1  test    rax, rax
0x1800091b4  jnz     short loc_1800091D4
0x1800091b6  mov     rcx, [rsp+38h]; this
0x1800091bb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x1800091c2  mov     edx, 0C3h; void *
0x1800091c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800091cc  mov     ebx, eax
0x1800091ce  test    eax, eax
0x1800091d0  jns     short loc_180009249
0x1800091d2  jmp     short loc_1800091FF
0x1800091d4  lea     rcx, ?g_service@@3V?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@A; unsigned int
0x1800091db  call    ?service_start@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAJXZ; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_start(void)
0x1800091e0  mov     ebx, eax
0x1800091e2  test    eax, eax
0x1800091e4  jns     short loc_18000922B
0x1800091e6  mov     rcx, [rsp+38h]; this
0x1800091eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x1800091f2  mov     r9d, eax; char *
0x1800091f5  mov     edx, 0C5h; void *
0x1800091fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091ff  mov     edx, ebx
0x180009201  lea     rcx, ?g_service@@3V?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@A; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy> g_service
0x180009208  call    ?service_stop@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXK@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::service_stop(ulong)
0x18000920d  mov     rcx, [rsp+38h]; this
0x180009212  lea     r8, aPcshellBaseWhe_4; "pcshell\\base\\whesvc\\dll\\whesvc.cpp"
0x180009219  mov     r9d, ebx; char *
0x18000921c  mov     edx, 9; void *
0x180009221  add     rsp, 30h
0x180009225  pop     rbx
0x180009226  jmp     ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000922b  call    ?PostServiceMainCallback@@YAXXZ; PostServiceMainCallback(void)
0x180009230  xor     r8d, r8d
0x180009233  lea     rcx, ?g_service@@3V?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@A; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy> g_service
0x18000923a  mov     r9d, 401h
0x180009240  lea     edx, [r8+4]
0x180009244  call    ?update_service_status@?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@AEAAXKKK@Z; wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::update_service_status(ulong,ulong,ulong)
0x180009249  add     rsp, 30h
0x18000924d  pop     rbx
0x18000924e  retn
```
