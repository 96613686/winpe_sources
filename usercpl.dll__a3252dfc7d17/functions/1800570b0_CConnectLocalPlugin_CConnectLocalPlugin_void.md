# CConnectLocalPlugin::~CConnectLocalPlugin(void)

- ea: `0x1800570b0`
- end: `0x180057193`
- name: `??1CConnectLocalPlugin@@EEAA@XZ`
- size: `227`
- prototype: `void __fastcall(CConnectLocalPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800571f0`

## callees

- `0x1800570b0`
- `0x180057430`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005711f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005712c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057146`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005711f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005712c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057146`

## pseudocode

```c
void __fastcall CConnectLocalPlugin::~CConnectLocalPlugin(CConnectLocalPlugin *this)
{
  CConnectLocalPlugin *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CConnectLocalPlugin::`vftable'{for `ITaskFlowPlugin'};
  *((_QWORD *)this + 1) = &CConnectLocalPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConfirmPasswordPagePlugin,IEmailPagePlugin,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'};
  v2 = (CConnectLocalPlugin *)((char *)this + 16);
  *(_QWORD *)v2 = &CConnectLocalPlugin::`vftable'{for `IEmailPagePlugin'};
  *((_QWORD *)this + 3) = &CConnectLocalPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'};
  *((_QWORD *)this + 4) = &CConnectLocalPlugin::`vftable'{for `IWebErrorPagePlugin'};
  *((_QWORD *)this + 5) = &CConnectLocalPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFinishPagePlugin>'};
  *((_QWORD *)this + 7) = &CConnectLocalPlugin::`vftable'{for `CBasePlugin'};
  *((_QWORD *)this + 11) = &CConnectLocalPlugin::`vftable'{for `CThreadRefTaker'};
  CConnectLocalPlugin::ClearCredentials(v2);
  CoTaskMemFree(*((LPVOID *)this + 20));
  CoTaskMemFree(*((LPVOID *)this + 21));
  CoTaskMemFree(*((LPVOID *)this + 23));
  CoTaskMemFree(*((LPVOID *)this + 24));
  v3 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 11) = &CThreadRefTaker::`vftable';
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 7) = &CBasePlugin::`vftable';
  _InterlockedDecrement(&g_cLocks);
  *((_DWORD *)this + 13) = -1073741823;
}

```

## disassembly

```asm
0x1800570b0  push    rbx
0x1800570b2  sub     rsp, 20h
0x1800570b6  mov     rbx, rcx
0x1800570b9  lea     rax, ??_7CConnectLocalPlugin@@6BITaskFlowPlugin@@@; const CConnectLocalPlugin::`vftable'{for `ITaskFlowPlugin'}
0x1800570c0  mov     [rcx], rax
0x1800570c3  lea     rax, ??_7CConnectLocalPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIConfirmPasswordPagePlugin@@UIEmailPagePlugin@@UIWebWizardPagePlugin@@UIWebErrorPagePlugin@@UIFinishPagePlugin@@@Details@WRL@Microsoft@@@; const CConnectLocalPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IConfirmPasswordPagePlugin,IEmailPagePlugin,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'}
0x1800570ca  mov     [rcx+8], rax
0x1800570ce  add     rcx, 10h; this
0x1800570d2  lea     rax, ??_7CConnectLocalPlugin@@6BIEmailPagePlugin@@@; const CConnectLocalPlugin::`vftable'{for `IEmailPagePlugin'}
0x1800570d9  mov     [rcx], rax
0x1800570dc  lea     rax, ??_7CConnectLocalPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebWizardPagePlugin@@UIWebErrorPagePlugin@@UIFinishPagePlugin@@@Details@WRL@Microsoft@@@; const CConnectLocalPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'}
0x1800570e3  mov     [rbx+18h], rax
0x1800570e7  lea     rax, ??_7CConnectLocalPlugin@@6BIWebErrorPagePlugin@@@; const CConnectLocalPlugin::`vftable'{for `IWebErrorPagePlugin'}
0x1800570ee  mov     [rbx+20h], rax
0x1800570f2  lea     rax, ??_7CConnectLocalPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFinishPagePlugin@@@Details@WRL@Microsoft@@@; const CConnectLocalPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFinishPagePlugin>'}
0x1800570f9  mov     [rbx+28h], rax
0x1800570fd  lea     rax, ??_7CConnectLocalPlugin@@6BCBasePlugin@@@; const CConnectLocalPlugin::`vftable'{for `CBasePlugin'}
0x180057104  mov     [rbx+38h], rax
0x180057108  lea     rax, ??_7CConnectLocalPlugin@@6BCThreadRefTaker@@@; const CConnectLocalPlugin::`vftable'{for `CThreadRefTaker'}
0x18005710f  mov     [rbx+58h], rax
0x180057113  call    ?ClearCredentials@CConnectLocalPlugin@@UEAAXXZ; CConnectLocalPlugin::ClearCredentials(void)
0x180057118  mov     rcx, [rbx+0A0h]; pv
0x18005711f  call    cs:__imp_CoTaskMemFree
0x180057125  mov     rcx, [rbx+0A8h]; pv
0x18005712c  call    cs:__imp_CoTaskMemFree
0x180057132  mov     rcx, [rbx+0B8h]; pv
0x180057139  call    cs:__imp_CoTaskMemFree
0x18005713f  mov     rcx, [rbx+0C0h]; pv
0x180057146  call    cs:__imp_CoTaskMemFree
0x18005714c  mov     rcx, [rbx+60h]
0x180057150  lea     rax, ??_7CThreadRefTaker@@6B@; const CThreadRefTaker::`vftable'
0x180057157  mov     [rbx+58h], rax
0x18005715b  test    rcx, rcx
0x18005715e  jz      short loc_180057174
0x180057160  mov     rax, [rcx]
0x180057163  mov     rax, [rax+10h]
0x180057167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005716c  mov     qword ptr [rbx+60h], 0
0x180057174  lea     rax, ??_7CBasePlugin@@6B@; const CBasePlugin::`vftable'
0x18005717b  mov     [rbx+38h], rax
0x18005717f  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180057186  mov     dword ptr [rbx+34h], 0C0000001h
0x18005718d  add     rsp, 20h
0x180057191  pop     rbx
0x180057192  retn
```
