# CAddUserPlugin::~CAddUserPlugin(void)

- ea: `0x180054804`
- end: `0x1800548ca`
- name: `??1CAddUserPlugin@@EEAA@XZ`
- size: `198`
- prototype: `void __fastcall(CAddUserPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180054910`

## callees

- `0x180054b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005487e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005488b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005487e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005488b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800548a5`

## pseudocode

```c
void __fastcall CAddUserPlugin::~CAddUserPlugin(CAddUserPlugin *this)
{
  CAddUserPlugin *v2; // rcx

  *(_QWORD *)this = &CAddUserPlugin::`vftable'{for `ITaskFlowPlugin'};
  v2 = (CAddUserPlugin *)((char *)this + 8);
  *(_QWORD *)v2 = &CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IEmailPagePlugin,IAddChildPagePlugin,IMoreInfoPagePlugin,IWebWizardPagePlugin,ILocalUserPagePlugin,IFinishPagePlugin,IWebErrorPagePlugin>'};
  *((_QWORD *)this + 2) = &CAddUserPlugin::`vftable'{for `IAddChildPagePlugin'};
  *((_QWORD *)this + 3) = &CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMoreInfoPagePlugin,IWebWizardPagePlugin,ILocalUserPagePlugin,IFinishPagePlugin,IWebErrorPagePlugin>'};
  *((_QWORD *)this + 4) = &CAddUserPlugin::`vftable'{for `IWebWizardPagePlugin'};
  *((_QWORD *)this + 5) = &CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILocalUserPagePlugin,IFinishPagePlugin,IWebErrorPagePlugin>'};
  *((_QWORD *)this + 6) = &CAddUserPlugin::`vftable'{for `IFinishPagePlugin'};
  *((_QWORD *)this + 7) = &CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebErrorPagePlugin>'};
  *((_QWORD *)this + 9) = &CAddUserPlugin::`vftable';
  CAddUserPlugin::ClearCredentials(v2);
  CoTaskMemFree(*((LPVOID *)this + 19));
  CoTaskMemFree(*((LPVOID *)this + 20));
  CoTaskMemFree(*((LPVOID *)this + 22));
  CoTaskMemFree(*((LPVOID *)this + 23));
  *((_QWORD *)this + 9) = &CBasePlugin::`vftable';
  _InterlockedDecrement(&g_cLocks);
  *((_DWORD *)this + 17) = -1073741823;
}

```

## disassembly

```asm
0x180054804  push    rbx
0x180054806  sub     rsp, 20h
0x18005480a  mov     rbx, rcx
0x18005480d  lea     rax, ??_7CAddUserPlugin@@6BITaskFlowPlugin@@@; const CAddUserPlugin::`vftable'{for `ITaskFlowPlugin'}
0x180054814  mov     [rcx], rax
0x180054817  add     rcx, 8; this
0x18005481b  lea     rax, ??_7CAddUserPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIEmailPagePlugin@@UIAddChildPagePlugin@@UIMoreInfoPagePlugin@@UIWebWizardPagePlugin@@UILocalUserPagePlugin@@UIFinishPagePlugin@@UIWebErrorPagePlugin@@@Details@WRL@Microsoft@@@; const CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IEmailPagePlugin,IAddChildPagePlugin,IMoreInfoPagePlugin,IWebWizardPagePlugin,ILocalUserPagePlugin,IFinishPagePlugin,IWebErrorPagePlugin>'}
0x180054822  mov     [rcx], rax
0x180054825  lea     rax, ??_7CAddUserPlugin@@6BIAddChildPagePlugin@@@; const CAddUserPlugin::`vftable'{for `IAddChildPagePlugin'}
0x18005482c  mov     [rbx+10h], rax
0x180054830  lea     rax, ??_7CAddUserPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMoreInfoPagePlugin@@UIWebWizardPagePlugin@@UILocalUserPagePlugin@@UIFinishPagePlugin@@UIWebErrorPagePlugin@@@Details@WRL@Microsoft@@@; const CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMoreInfoPagePlugin,IWebWizardPagePlugin,ILocalUserPagePlugin,IFinishPagePlugin,IWebErrorPagePlugin>'}
0x180054837  mov     [rbx+18h], rax
0x18005483b  lea     rax, ??_7CAddUserPlugin@@6BIWebWizardPagePlugin@@@; const CAddUserPlugin::`vftable'{for `IWebWizardPagePlugin'}
0x180054842  mov     [rbx+20h], rax
0x180054846  lea     rax, ??_7CAddUserPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILocalUserPagePlugin@@UIFinishPagePlugin@@UIWebErrorPagePlugin@@@Details@WRL@Microsoft@@@; const CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILocalUserPagePlugin,IFinishPagePlugin,IWebErrorPagePlugin>'}
0x18005484d  mov     [rbx+28h], rax
0x180054851  lea     rax, ??_7CAddUserPlugin@@6BIFinishPagePlugin@@@; const CAddUserPlugin::`vftable'{for `IFinishPagePlugin'}
0x180054858  mov     [rbx+30h], rax
0x18005485c  lea     rax, ??_7CAddUserPlugin@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebErrorPagePlugin@@@Details@WRL@Microsoft@@@; const CAddUserPlugin::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebErrorPagePlugin>'}
0x180054863  mov     [rbx+38h], rax
0x180054867  lea     rax, ??_7CAddUserPlugin@@6B@; const CAddUserPlugin::`vftable'
0x18005486e  mov     [rbx+48h], rax
0x180054872  call    ?ClearCredentials@CAddUserPlugin@@UEAAXXZ; CAddUserPlugin::ClearCredentials(void)
0x180054877  mov     rcx, [rbx+98h]; pv
0x18005487e  call    cs:__imp_CoTaskMemFree
0x180054884  mov     rcx, [rbx+0A0h]; pv
0x18005488b  call    cs:__imp_CoTaskMemFree
0x180054891  mov     rcx, [rbx+0B0h]; pv
0x180054898  call    cs:__imp_CoTaskMemFree
0x18005489e  mov     rcx, [rbx+0B8h]; pv
0x1800548a5  call    cs:__imp_CoTaskMemFree
0x1800548ab  lea     rax, ??_7CBasePlugin@@6B@; const CBasePlugin::`vftable'
0x1800548b2  mov     [rbx+48h], rax
0x1800548b6  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x1800548bd  mov     dword ptr [rbx+44h], 0C0000001h
0x1800548c4  add     rsp, 20h
0x1800548c8  pop     rbx
0x1800548c9  retn
```
