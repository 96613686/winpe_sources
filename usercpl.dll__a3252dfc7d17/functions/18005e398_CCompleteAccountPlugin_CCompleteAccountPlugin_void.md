# CCompleteAccountPlugin::~CCompleteAccountPlugin(void)

- ea: `0x18005e398`
- end: `0x18005e493`
- name: `??1CCompleteAccountPlugin@@EEAA@XZ`
- size: `251`
- prototype: `void __fastcall(CCompleteAccountPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e4c0`

## callees

- `0x18005e398`
- `0x18005e680`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e3fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e409`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e3fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e409`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e423`

## pseudocode

```c
void __fastcall CCompleteAccountPlugin::~CCompleteAccountPlugin(CCompleteAccountPlugin *this)
{
  CCompleteAccountPlugin *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CCompleteAccountPlugin::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskFlowPlugin,IConfirmPasswordPagePlugin,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'};
  *((_QWORD *)this + 1) = &CCompleteAccountPlugin::`vftable'{for `IConfirmPasswordPagePlugin'};
  v2 = (CCompleteAccountPlugin *)((char *)this + 16);
  *(_QWORD *)v2 = &CCompleteAccountPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'};
  *((_QWORD *)this + 3) = &CCompleteAccountPlugin::`vftable'{for `IWebErrorPagePlugin'};
  *((_QWORD *)this + 4) = &CCompleteAccountPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFinishPagePlugin>'};
  *((_QWORD *)this + 6) = &CCompleteAccountPlugin::`vftable'{for `CBasePlugin'};
  *((_QWORD *)this + 10) = &CCompleteAccountPlugin::`vftable'{for `CThreadRefTaker'};
  CCompleteAccountPlugin::ClearCredentials(v2);
  CoTaskMemFree(*((LPVOID *)this + 19));
  CoTaskMemFree(*((LPVOID *)this + 20));
  CoTaskMemFree(*((LPVOID *)this + 22));
  CoTaskMemFree(*((LPVOID *)this + 23));
  v3 = *((_QWORD *)this + 24);
  if ( v3 )
  {
    *((_QWORD *)this + 24) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 10) = &CThreadRefTaker::`vftable';
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 11) = 0;
  }
  *((_QWORD *)this + 6) = &CBasePlugin::`vftable';
  _InterlockedDecrement(&g_cLocks);
  *((_DWORD *)this + 11) = -1073741823;
}

```

## disassembly

```asm
0x18005e398  push    rbx
0x18005e39a  sub     rsp, 20h
0x18005e39e  mov     rbx, rcx
0x18005e3a1  lea     rax, ??_7CCompleteAccountPlugin@@6B?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITaskFlowPlugin@@UIConfirmPasswordPagePlugin@@UIWebWizardPagePlugin@@UIWebErrorPagePlugin@@UIFinishPagePlugin@@@WRL@Microsoft@@@; const CCompleteAccountPlugin::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskFlowPlugin,IConfirmPasswordPagePlugin,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'}
0x18005e3a8  mov     [rcx], rax
0x18005e3ab  lea     rax, ??_7CCompleteAccountPlugin@@6BIConfirmPasswordPagePlugin@@@; const CCompleteAccountPlugin::`vftable'{for `IConfirmPasswordPagePlugin'}
0x18005e3b2  mov     [rcx+8], rax
0x18005e3b6  add     rcx, 10h; this
0x18005e3ba  lea     rax, ??_7CCompleteAccountPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebWizardPagePlugin@@UIWebErrorPagePlugin@@UIFinishPagePlugin@@@Details@WRL@Microsoft@@@; const CCompleteAccountPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebWizardPagePlugin,IWebErrorPagePlugin,IFinishPagePlugin>'}
0x18005e3c1  mov     [rcx], rax
0x18005e3c4  lea     rax, ??_7CCompleteAccountPlugin@@6BIWebErrorPagePlugin@@@; const CCompleteAccountPlugin::`vftable'{for `IWebErrorPagePlugin'}
0x18005e3cb  mov     [rbx+18h], rax
0x18005e3cf  lea     rax, ??_7CCompleteAccountPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIFinishPagePlugin@@@Details@WRL@Microsoft@@@; const CCompleteAccountPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IFinishPagePlugin>'}
0x18005e3d6  mov     [rbx+20h], rax
0x18005e3da  lea     rax, ??_7CCompleteAccountPlugin@@6BCBasePlugin@@@; const CCompleteAccountPlugin::`vftable'{for `CBasePlugin'}
0x18005e3e1  mov     [rbx+30h], rax
0x18005e3e5  lea     rax, ??_7CCompleteAccountPlugin@@6BCThreadRefTaker@@@; const CCompleteAccountPlugin::`vftable'{for `CThreadRefTaker'}
0x18005e3ec  mov     [rbx+50h], rax
0x18005e3f0  call    ?ClearCredentials@CCompleteAccountPlugin@@UEAAXXZ; CCompleteAccountPlugin::ClearCredentials(void)
0x18005e3f5  mov     rcx, [rbx+98h]; pv
0x18005e3fc  call    cs:__imp_CoTaskMemFree
0x18005e402  mov     rcx, [rbx+0A0h]; pv
0x18005e409  call    cs:__imp_CoTaskMemFree
0x18005e40f  mov     rcx, [rbx+0B0h]; pv
0x18005e416  call    cs:__imp_CoTaskMemFree
0x18005e41c  mov     rcx, [rbx+0B8h]; pv
0x18005e423  call    cs:__imp_CoTaskMemFree
0x18005e429  mov     rcx, [rbx+0C0h]
0x18005e430  test    rcx, rcx
0x18005e433  jz      short loc_18005E44C
0x18005e435  mov     qword ptr [rbx+0C0h], 0
0x18005e440  mov     rax, [rcx]
0x18005e443  mov     rax, [rax+10h]
0x18005e447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e44c  mov     rcx, [rbx+58h]
0x18005e450  lea     rax, ??_7CThreadRefTaker@@6B@; const CThreadRefTaker::`vftable'
0x18005e457  mov     [rbx+50h], rax
0x18005e45b  test    rcx, rcx
0x18005e45e  jz      short loc_18005E474
0x18005e460  mov     rax, [rcx]
0x18005e463  mov     rax, [rax+10h]
0x18005e467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e46c  mov     qword ptr [rbx+58h], 0
0x18005e474  lea     rax, ??_7CBasePlugin@@6B@; const CBasePlugin::`vftable'
0x18005e47b  mov     [rbx+30h], rax
0x18005e47f  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18005e486  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18005e48d  add     rsp, 20h
0x18005e491  pop     rbx
0x18005e492  retn
```
