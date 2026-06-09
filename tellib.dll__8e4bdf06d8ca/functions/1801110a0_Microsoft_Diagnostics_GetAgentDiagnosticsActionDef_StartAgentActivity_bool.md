# Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::StartAgentActivity(bool)

- ea: `0x1801110a0`
- end: `0x180111313`
- name: `?StartAgentActivity@GetAgentDiagnosticsActionDef@Diagnostics@Microsoft@@QEAAX_N@Z`
- size: `627`
- prototype: `void __fastcall(Microsoft::Diagnostics::GetAgentDiagnosticsActionDef *__hidden this, bool)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180104f0c`
- `0x1801cbb28`
- `0x1801e240c`

## callees

- `0x180020fbc`
- `0x180054ca4`
- `0x18005af1c`
- `0x18009c71c`
- `0x18009d380`
- `0x1800b83bc`
- `0x1800bc2e0`
- `0x1801110a0`
- `0x180111a68`
- `0x18012de40`
- `0x1801c9284`
- `0x180202414`

## import_xrefs

- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x18011123f`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x18011123f`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180111275`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180111275`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x1801111b3`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x1801111b3`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x18011117d`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x18011117d`

## string_xrefs

- `0x18011112a`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x180111194`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x1801111ca`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x180111256`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x18011128c`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x1801112b9`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x1801112db`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::StartAgentActivity(
        Microsoft::Diagnostics::GetAgentDiagnosticsActionDef *this,
        unsigned __int8 a2)
{
  int v2; // r12d
  int v4; // eax
  _QWORD *v5; // rdi
  wilp *v6; // rsi
  void *v7; // rdx
  int v8; // eax
  int v9; // eax
  _QWORD *v10; // rsi
  wilp *v11; // r14
  void *v12; // rdx
  int Activity; // eax
  int started; // eax
  const char *v15; // r9
  int v16; // [rsp+20h] [rbp-50h]
  int v17; // [rsp+20h] [rbp-50h]
  __int128 v18; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[16]; // [rsp+40h] [rbp-30h] BYREF
  GUID v20; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v2 = a2;
  v18 = *(_OWORD *)&off_180360990;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v18) )
  {
    v20 = GUID_NULL;
    v18 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 160, v19);
    v4 = Microsoft::Diagnostics::Utils::String::GUIDFromString(&v18, &v20, 0);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)v4,
        v16);
    v5 = (_QWORD *)((char *)this + 200);
    v6 = (wilp *)*((_QWORD *)this + 25);
    if ( v6 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v18);
      wilp::CloseCmsContainer(v6, v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v18);
    }
    *v5 = 0;
    v8 = CmsOpenContainer(&v20, 8, 33, v5);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)v8,
        v16);
    v9 = CmsRegisterForContainerNotifications(
           *v5,
           Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerNotificationCallback,
           this);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)v9,
        v16);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (_DWORD)this + 192,
      0,
      0,
      0,
      0);
    v10 = (_QWORD *)((char *)this + 208);
    v11 = (wilp *)*((_QWORD *)this + 26);
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v18);
      wilp::CloseCmsActivity(v11, v12);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v18);
    }
    *v10 = 0;
    Activity = CmsCreateActivity(*v5, (v2 ^ 1u) + 8001, (char *)this + 208);
    if ( Activity < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)Activity,
        v17);
    started = CmsStartActivityAsync(
                *v10,
                Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerActivityNotificationCallback,
                this);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)started,
        v17);
    if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(*((void **)this + 24), 0x2710u) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)0x800705B4LL,
        v17);
    v15 = (const char *)*((unsigned int *)this + 54);
    if ( (int)v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        v15,
        v17);
  }
}

```

## disassembly

```asm
0x1801110a0  mov     [rsp-28h+arg_8], rbx
0x1801110a5  mov     [rsp-28h+arg_10], rsi
0x1801110aa  push    rbp
0x1801110ab  push    rdi
0x1801110ac  push    r12
0x1801110ae  push    r14
0x1801110b0  push    r15
0x1801110b2  mov     rbp, rsp
0x1801110b5  sub     rsp, 70h
0x1801110b9  mov     rax, cs:__security_cookie
0x1801110c0  xor     rax, rsp
0x1801110c3  mov     [rbp+var_10], rax
0x1801110c7  movzx   r12d, dl
0x1801110cb  mov     rbx, rcx
0x1801110ce  movups  xmm0, xmmword ptr cs:off_180360990; "AgentSocketTestMode"
0x1801110d5  movdqu  [rbp+var_40], xmm0
0x1801110da  lea     rcx, [rbp+var_40]
0x1801110de  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x1801110e3  test    al, al
0x1801110e5  jnz     loc_1801112ED
0x1801110eb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801110f2  movdqu  [rbp+var_20], xmm0
0x1801110f7  lea     rcx, [rbx+0A0h]
0x1801110fe  lea     rdx, [rbp+var_30]
0x180111102  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180111107  movups  xmm0, xmmword ptr [rax]
0x18011110a  movdqu  [rbp+var_40], xmm0
0x18011110f  xor     r8d, r8d
0x180111112  lea     rdx, [rbp+var_20]
0x180111116  lea     rcx, [rbp+var_40]
0x18011111a  call    ?GUIDFromString@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::GUIDFromString(std::wstring_view,_GUID &,bool)
0x18011111f  mov     rcx, [rbp+28h]; this
0x180111123  test    eax, eax
0x180111125  jns     short loc_18011113C
0x180111127  mov     r9d, eax; char *
0x18011112a  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x180111131  mov     edx, 59h ; 'Y'; void *
0x180111136  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011113c  lea     rdi, [rbx+0C8h]
0x180111143  mov     rsi, [rdi]
0x180111146  test    rsi, rsi
0x180111149  jz      short loc_180111166
0x18011114b  lea     rcx, [rbp+var_40]; this
0x18011114f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180111154  mov     rcx, rsi; this
0x180111157  call    ?CloseCmsContainer@wilp@@YAXPEAX@Z; wilp::CloseCmsContainer(void *)
0x18011115c  lea     rcx, [rbp+var_40]; this
0x180111160  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180111165  nop
0x180111166  mov     qword ptr [rdi], 0
0x18011116d  mov     r9, rdi
0x180111170  mov     edx, 8
0x180111175  lea     r8d, [rdx+19h]
0x180111179  lea     rcx, [rbp+var_20]
0x18011117d  call    cs:__imp_CmsOpenContainer
0x180111184  nop     dword ptr [rax+rax+00h]
0x180111189  mov     rcx, [rbp+28h]; this
0x18011118d  test    eax, eax
0x18011118f  jns     short loc_1801111A6
0x180111191  mov     r9d, eax; char *
0x180111194  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x18011119b  mov     edx, 5Eh ; '^'; void *
0x1801111a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801111a6  mov     r8, rbx
0x1801111a9  lea     rdx, ?ContainerNotificationCallback@GetAgentDiagnosticsActionDef@Diagnostics@Microsoft@@SAXPEAU_CMS_CONTAINER_NOTIFICATION@@PEAX@Z; Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerNotificationCallback(_CMS_CONTAINER_NOTIFICATION *,void *)
0x1801111b0  mov     rcx, [rdi]
0x1801111b3  call    cs:__imp_CmsRegisterForContainerNotifications
0x1801111ba  nop     dword ptr [rax+rax+00h]
0x1801111bf  mov     rcx, [rbp+28h]; this
0x1801111c3  test    eax, eax
0x1801111c5  jns     short loc_1801111DC
0x1801111c7  mov     r9d, eax; char *
0x1801111ca  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1801111d1  mov     edx, 62h ; 'b'; void *
0x1801111d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801111dc  lea     r15, [rbx+0C0h]
0x1801111e3  mov     qword ptr [rsp+70h+var_50], 0; int
0x1801111ec  xor     r9d, r9d
0x1801111ef  xor     r8d, r8d
0x1801111f2  xor     edx, edx
0x1801111f4  mov     rcx, r15
0x1801111f7  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801111fc  lea     rsi, [rbx+0D0h]
0x180111203  mov     r14, [rsi]
0x180111206  test    r14, r14
0x180111209  jz      short loc_180111226
0x18011120b  lea     rcx, [rbp+var_40]; this
0x18011120f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180111214  mov     rcx, r14; this
0x180111217  call    ?CloseCmsActivity@wilp@@YAXPEAX@Z; wilp::CloseCmsActivity(void *)
0x18011121c  lea     rcx, [rbp+var_40]; this
0x180111220  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180111225  nop
0x180111226  mov     qword ptr [rsi], 0
0x18011122d  mov     edx, r12d
0x180111230  xor     edx, 1
0x180111233  add     edx, 1F41h
0x180111239  mov     r8, rsi
0x18011123c  mov     rcx, [rdi]
0x18011123f  call    cs:__imp_CmsCreateActivity
0x180111246  nop     dword ptr [rax+rax+00h]
0x18011124b  test    eax, eax
0x18011124d  jns     short loc_180111268
0x18011124f  mov     rcx, [rbp+28h]; this
0x180111253  mov     r9d, eax; char *
0x180111256  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x18011125d  mov     edx, 67h ; 'g'; void *
0x180111262  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180111268  mov     r8, rbx
0x18011126b  lea     rdx, ?ContainerActivityNotificationCallback@GetAgentDiagnosticsActionDef@Diagnostics@Microsoft@@SAXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z; Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerActivityNotificationCallback(_CMS_ACTIVITY_NOTIFICATION *,void *)
0x180111272  mov     rcx, [rsi]
0x180111275  call    cs:__imp_CmsStartActivityAsync
0x18011127c  nop     dword ptr [rax+rax+00h]
0x180111281  test    eax, eax
0x180111283  jns     short loc_18011129E
0x180111285  mov     rcx, [rbp+28h]; this
0x180111289  mov     r9d, eax; char *
0x18011128c  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x180111293  mov     edx, 6Bh ; 'k'; void *
0x180111298  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011129e  mov     edx, 2710h; unsigned int
0x1801112a3  mov     rcx, [r15]; void *
0x1801112a6  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x1801112ab  test    al, al
0x1801112ad  jnz     short loc_1801112CB
0x1801112af  mov     rcx, [rbp+28h]; this
0x1801112b3  mov     r9d, 800705B4h; char *
0x1801112b9  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1801112c0  mov     edx, 6Eh ; 'n'; void *
0x1801112c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801112cb  mov     r9d, [rbx+0D8h]; char *
0x1801112d2  test    r9d, r9d
0x1801112d5  jns     short loc_1801112ED
0x1801112d7  mov     rcx, [rbp+28h]; this
0x1801112db  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1801112e2  mov     edx, 70h ; 'p'; void *
0x1801112e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801112ed  mov     rcx, [rbp+var_10]
0x1801112f1  xor     rcx, rsp; StackCookie
0x1801112f4  call    __security_check_cookie
0x1801112f9  lea     r11, [rsp+70h+var_s0]
0x1801112fe  mov     rbx, [r11+38h]
0x180111302  mov     rsi, [r11+40h]
0x180111306  mov     rsp, r11
0x180111309  pop     r15
0x18011130b  pop     r14
0x18011130d  pop     r12
0x18011130f  pop     rdi
0x180111310  pop     rbp
0x180111311  retn
```
