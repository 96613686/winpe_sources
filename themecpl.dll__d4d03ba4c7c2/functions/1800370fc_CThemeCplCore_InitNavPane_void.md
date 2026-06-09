# CThemeCplCore::_InitNavPane(void)

- ea: `0x1800370fc`
- end: `0x1800372f3`
- name: `?_InitNavPane@CThemeCplCore@@AEAAJXZ`
- size: `503`
- prototype: `__int64 __fastcall(CThemeCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035ba4`

## callees

- `0x18000268c`
- `0x1800370fc`
- `0x1800548a4`
- `0x180054968`
- `0x180057010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800372ab`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800372ab`
- `SHELL32!__imp_SHRestricted` at `0x180037157`
- `SHELL32!__imp_SHRestricted` at `0x180037157`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18003728a`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18003728a`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18003719e`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18003719e`

## string_xrefs

- `0x180037178`: `%windir%\system32\rundll32.exe`
- `0x180037169`: `shell32.dll,Control_RunDLL desk.cpl,Web,0`
- `0x18003721c`: `Microsoft.Taskbar`
- `0x1800372a1`: `ControlPanelNavLinks`
- `0x18003724c`: `ms-settings:easeofaccess-narrator`

## pseudocode

```c
__int64 __fastcall CThemeCplCore::_InitNavPane(CThemeCplCore *this)
{
  IUnknown *v2; // rax
  IUnknown *v3; // rbx
  const CHAR *v4; // rdx
  __int64 v5; // r8
  HRESULT v6; // edi
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  IUnknown *v10; // rcx
  void *ppvOut; // [rsp+58h] [rbp+10h] BYREF

  v2 = (IUnknown *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  ppvOut = v2;
  v3 = v2;
  if ( v2 )
  {
    v2[1].lpVtbl = 0;
    v2->lpVtbl = (struct IUnknownVtbl *)&CControlPanelNavLinks::`vftable';
    LODWORD(v2[2].lpVtbl) = 1;
    if ( SHRestricted(REST_NODISPBACKGROUND)
      || (v6 = CControlPanelNavLinks::AddLinkShellEx(
                 v3,
                 0,
                 v5,
                 79,
                 L"%windir%\\system32\\rundll32.exe",
                 L"shell32.dll,Control_RunDLL desk.cpl,Web,0"),
          v6 >= 0) )
    {
      if ( SHWindowsPolicy(POLID_NoChangingMousePointers, v4)
        || (v6 = CControlPanelNavLinks::AddLinkControlPanel(v3, 0, v7, 80, L"Microsoft.Mouse", L"1"), v6 >= 0) )
      {
        v6 = CControlPanelNavLinks::AddLinkShellEx(v3, 1, v7, 81, L"ms-settings:display", 0);
        if ( v6 >= 0 )
        {
          v6 = CControlPanelNavLinks::AddLinkControlPanel(v3, 1, v8, 82, L"Microsoft.Taskbar", 0);
          if ( v6 >= 0 )
          {
            v6 = CControlPanelNavLinks::AddLinkShellEx(v3, 1, v9, 83, L"ms-settings:easeofaccess-narrator", 0);
            if ( v6 >= 0 )
            {
              v10 = (IUnknown *)*((_QWORD *)this + 5);
              ppvOut = 0;
              v6 = IUnknown_QueryService(
                     v10,
                     (const GUID *const)&SID_PerLayoutPropertyBag,
                     &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                     &ppvOut);
              if ( v6 >= 0 )
              {
                v6 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppvOut, L"ControlPanelNavLinks", v3);
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
              }
            }
          }
        }
      }
    }
    ((void (__fastcall *)(IUnknown *))v3->lpVtbl->Release)(v3);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800370fc  mov     [rsp+arg_0], rbx
0x180037101  mov     [rsp+arg_10], rsi
0x180037106  push    rdi
0x180037107  sub     rsp, 40h
0x18003710b  mov     rsi, rcx
0x18003710e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037115  mov     ecx, 18h; unsigned __int64
0x18003711a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003711f  mov     [rsp+48h+ppvOut], rax
0x180037124  mov     rbx, rax
0x180037127  test    rax, rax
0x18003712a  jz      loc_1800372DB
0x180037130  mov     qword ptr [rbx+8], 0
0x180037138  lea     rax, ??_7CControlPanelNavLinks@@6B@; const CControlPanelNavLinks::`vftable'
0x18003713f  mov     [rbx], rax
0x180037142  mov     dword ptr [rbx+10h], 1
0x180037149  test    rbx, rbx
0x18003714c  jz      loc_1800372DB
0x180037152  mov     ecx, 40000077h; rest
0x180037157  call    cs:__imp_SHRestricted
0x18003715e  nop     dword ptr [rax+rax+00h]
0x180037163  test    eax, eax
0x180037165  jnz     short loc_180037197
0x180037167  xor     edx, edx
0x180037169  lea     rax, aShell32DllCont; "shell32.dll,Control_RunDLL desk.cpl,Web"...
0x180037170  mov     [rsp+48h+var_20], rax
0x180037175  mov     rcx, rbx
0x180037178  lea     rax, aWindirSystem32; "%windir%\\system32\\rundll32.exe"
0x18003717f  mov     [rsp+48h+var_28], rax
0x180037184  lea     r9d, [rdx+4Fh]
0x180037188  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x18003718d  mov     edi, eax
0x18003718f  test    eax, eax
0x180037191  js      loc_1800372CA
0x180037197  lea     rcx, POLID_NoChangingMousePointers; "="
0x18003719e  call    cs:__imp_SHWindowsPolicy
0x1800371a5  nop     dword ptr [rax+rax+00h]
0x1800371aa  test    eax, eax
0x1800371ac  jnz     short loc_1800371DE
0x1800371ae  xor     edx, edx
0x1800371b0  lea     rax, a1; "1"
0x1800371b7  mov     [rsp+48h+var_20], rax
0x1800371bc  mov     rcx, rbx
0x1800371bf  lea     rax, aMicrosoftMouse; "Microsoft.Mouse"
0x1800371c6  mov     [rsp+48h+var_28], rax
0x1800371cb  lea     r9d, [rdx+50h]
0x1800371cf  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x1800371d4  mov     edi, eax
0x1800371d6  test    eax, eax
0x1800371d8  js      loc_1800372CA
0x1800371de  mov     edx, 1
0x1800371e3  mov     [rsp+48h+var_20], 0
0x1800371ec  lea     rax, aMsSettingsDisp; "ms-settings:display"
0x1800371f3  mov     rcx, rbx
0x1800371f6  mov     [rsp+48h+var_28], rax
0x1800371fb  lea     r9d, [rdx+50h]
0x1800371ff  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180037204  mov     edi, eax
0x180037206  test    eax, eax
0x180037208  js      loc_1800372CA
0x18003720e  mov     edx, 1
0x180037213  mov     [rsp+48h+var_20], 0
0x18003721c  lea     rax, aMicrosoftTaskb; "Microsoft.Taskbar"
0x180037223  mov     rcx, rbx
0x180037226  mov     [rsp+48h+var_28], rax
0x18003722b  lea     r9d, [rdx+51h]
0x18003722f  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180037234  mov     edi, eax
0x180037236  test    eax, eax
0x180037238  js      loc_1800372CA
0x18003723e  mov     edx, 1
0x180037243  mov     [rsp+48h+var_20], 0
0x18003724c  lea     rax, aMsSettingsEase; "ms-settings:easeofaccess-narrator"
0x180037253  mov     rcx, rbx
0x180037256  mov     [rsp+48h+var_28], rax
0x18003725b  lea     r9d, [rdx+52h]
0x18003725f  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180037264  mov     edi, eax
0x180037266  test    eax, eax
0x180037268  js      short loc_1800372CA
0x18003726a  mov     rcx, [rsi+28h]; punk
0x18003726e  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x180037273  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18003727a  mov     [rsp+48h+ppvOut], 0
0x180037283  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x18003728a  call    cs:__imp_IUnknown_QueryService
0x180037291  nop     dword ptr [rax+rax+00h]
0x180037296  mov     edi, eax
0x180037298  test    eax, eax
0x18003729a  js      short loc_1800372CA
0x18003729c  mov     rcx, [rsp+48h+ppvOut]; propBag
0x1800372a1  lea     rdx, propName; "ControlPanelNavLinks"
0x1800372a8  mov     r8, rbx; punk
0x1800372ab  call    cs:__imp_PSPropertyBag_WriteUnknown
0x1800372b2  nop     dword ptr [rax+rax+00h]
0x1800372b7  mov     rcx, [rsp+48h+ppvOut]
0x1800372bc  mov     edi, eax
0x1800372be  mov     rax, [rcx]
0x1800372c1  mov     rax, [rax+10h]
0x1800372c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372ca  mov     rax, [rbx]
0x1800372cd  mov     rcx, rbx
0x1800372d0  mov     rax, [rax+10h]
0x1800372d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372d9  jmp     short loc_1800372E0
0x1800372db  mov     edi, 8007000Eh
0x1800372e0  mov     rbx, [rsp+48h+arg_0]
0x1800372e5  mov     eax, edi
0x1800372e7  mov     rsi, [rsp+48h+arg_10]
0x1800372ec  add     rsp, 40h
0x1800372f0  pop     rdi
0x1800372f1  retn
```
