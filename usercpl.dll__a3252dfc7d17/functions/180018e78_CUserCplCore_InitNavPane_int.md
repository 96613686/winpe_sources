# CUserCplCore::_InitNavPane(int)

- ea: `0x180018e78`
- end: `0x180019125`
- name: `?_InitNavPane@CUserCplCore@@AEAAJH@Z`
- size: `685`
- prototype: `__int64 __fastcall(CUserCplCore *__hidden this, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014dd8`

## callees

- `0x180002ae4`
- `0x18000dafc`
- `0x180011988`
- `0x180018e78`
- `0x180067e4c`
- `0x180067f48`
- `0x180067fe4`
- `0x1800680bc`
- `0x1800681a4`
- `0x1800682f0`
- `0x18006836c`
- `0x180078010`

## import_xrefs

- `SHELL32!__imp_WPC_InstallState` at `0x180018fde`
- `SHELL32!__imp_WPC_InstallState` at `0x180018fde`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800190de`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800190de`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800190c4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800190c4`

## string_xrefs

- `0x180018eff`: `keymgr.dll,PRShowSaveWizardExW`
- `0x180018ef4`: `%windir%\System32\rundll32.exe`
- `0x180018f36`: `%windir%\System32\rekeywiz.exe`
- `0x1800190d4`: `ControlPanelNavLinks`

## pseudocode

```c
__int64 __fastcall CUserCplCore::_InitNavPane(CUserCplCore *this, int a2)
{
  CControlPanelNavLinks *v4; // rax
  __int64 v5; // r8
  CControlPanelNavLinks *v6; // rdi
  __int64 v7; // rdx
  HRESULT v8; // ebx
  __int64 v9; // r8
  HINSTANCE v10; // rdx
  int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  HINSTANCE v16; // rdx
  int v17; // r8d
  HINSTANCE v18; // rsi
  HINSTANCE v19; // rdx
  CControlPanelNavLink *v20; // rsi
  IUnknown *v21; // rcx
  void *ppvOut; // [rsp+80h] [rbp+40h] BYREF
  CControlPanelNavLink *v24; // [rsp+88h] [rbp+48h]

  v4 = (CControlPanelNavLinks *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &CControlPanelNavLinks::`vftable';
    *((_QWORD *)v4 + 1) = 0;
    *((_DWORD *)v4 + 4) = 1;
    v8 = CControlPanelNavLinks::AddLinkControlPanel(v4, 0, v5, 106, L"Microsoft.CredentialManager");
    if ( v8 >= 0 )
    {
      if ( !a2
        || (v8 = CControlPanelNavLinks::AddLinkShellEx(
                   v6,
                   v7,
                   v9,
                   100,
                   L"%windir%\\System32\\rundll32.exe",
                   L"keymgr.dll,PRShowSaveWizardExW",
                   0),
            v8 >= 0) )
      {
        if ( !*((_BYTE *)this + 105)
          || (v8 = CControlPanelNavLinks::AddLinkShellEx(v6, v7, v9, 102, L"%windir%\\System32\\rekeywiz.exe", 0, 0),
              v8 >= 0) )
        {
          ppvOut = 0;
          v8 = CControlPanelNavLinks::AddLinkShellEx(
                 v6,
                 v7,
                 v9,
                 103,
                 L"%windir%\\System32\\rundll32.exe",
                 L"sysdm.cpl,EditUserProfiles",
                 &ppvOut);
          if ( v8 >= 0 )
          {
            v8 = CControlPanelNavLink::SetIcon((CControlPanelNavLink *)ppvOut, v10, v11);
            if ( v8 >= 0 )
            {
              v8 = CControlPanelNavLinks::AddLinkShellEx(
                     v6,
                     v12,
                     v13,
                     104,
                     L"%windir%\\System32\\rundll32.exe",
                     L"sysdm.cpl,EditEnvironmentVariables",
                     0);
              if ( v8 >= 0 )
              {
                LODWORD(ppvOut) = 0;
                if ( (int)WPC_InstallState(&ppvOut) < 0
                  || (_DWORD)ppvOut
                  || (v24 = 0,
                      v8 = CControlPanelNavLinks::AddLinkControlPanel(v6, 1, v15, 105, L"Microsoft.ParentalControls"),
                      v8 >= 0)
                  && (v8 = CControlPanelNavLink::SetIcon(v24, v16, v17), v8 >= 0) )
                {
                  if ( !EASPoliciesAreBeingEnforced(v14) )
                    goto LABEL_21;
                  v18 = g_hinst;
                  ppvOut = 0;
                  v8 = CControlPanelNavLink::Create(0, &ppvOut);
                  if ( v8 >= 0 )
                  {
                    v19 = v18;
                    v20 = (CControlPanelNavLink *)ppvOut;
                    v8 = CControlPanelNavLink::SetName((CControlPanelNavLink *)ppvOut, v19, 0xE6u);
                    if ( v8 < 0
                      || (*((_DWORD *)v20 + 8) = 0,
                          *((_DWORD *)v20 + 9) = 230,
                          v8 = CControlPanelNavLinks::Add(v6, v20),
                          v8 < 0) )
                    {
                      if ( v20 )
                      {
                        CControlPanelNavLink::~CControlPanelNavLink(v20);
                        operator delete(v20);
                      }
                    }
                  }
                  if ( v8 >= 0 )
                  {
LABEL_21:
                    v21 = (IUnknown *)*((_QWORD *)this + 12);
                    ppvOut = 0;
                    v8 = IUnknown_QueryService(
                           v21,
                           (const GUID *const)&SID_PerLayoutPropertyBag,
                           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                           &ppvOut);
                    if ( v8 >= 0 )
                    {
                      v8 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppvOut, L"ControlPanelNavLinks", (IUnknown *)v6);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(CControlPanelNavLinks *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018e78  mov     [rsp-28h+arg_0], rbx
0x180018e7d  mov     [rsp-28h+arg_8], rsi
0x180018e82  push    rbp
0x180018e83  push    rdi
0x180018e84  push    r12
0x180018e86  push    r14
0x180018e88  push    r15
0x180018e8a  mov     rbp, rsp
0x180018e8d  sub     rsp, 40h
0x180018e91  mov     esi, edx
0x180018e93  mov     r14, rcx
0x180018e96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018e9d  mov     ecx, 18h; unsigned __int64
0x180018ea2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018ea7  xor     r15d, r15d
0x180018eaa  mov     rdi, rax
0x180018ead  test    rax, rax
0x180018eb0  jz      loc_180019107
0x180018eb6  lea     rax, ??_7CControlPanelNavLinks@@6B@; const CControlPanelNavLinks::`vftable'
0x180018ebd  mov     [rsp+40h+var_10], r15
0x180018ec2  mov     [rdi], rax
0x180018ec5  lea     r9d, [r15+6Ah]
0x180018ec9  lea     rax, aMicrosoftCrede; "Microsoft.CredentialManager"
0x180018ed0  mov     [rdi+8], r15
0x180018ed4  xor     edx, edx
0x180018ed6  mov     [rsp+40h+var_20], rax
0x180018edb  mov     rcx, rdi
0x180018ede  mov     dword ptr [rdi+10h], 1
0x180018ee5  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180018eea  mov     ebx, eax
0x180018eec  test    eax, eax
0x180018eee  js      loc_1800190F6
0x180018ef4  lea     r12, aWindirSystem32; "%windir%\\System32\\rundll32.exe"
0x180018efb  test    esi, esi
0x180018efd  jz      short loc_180018F2B
0x180018eff  lea     rax, aKeymgrDllPrsho; "keymgr.dll,PRShowSaveWizardExW"
0x180018f06  mov     [rsp+40h+var_10], r15
0x180018f0b  mov     [rsp+40h+var_18], rax
0x180018f10  lea     r9d, [r15+64h]
0x180018f14  mov     rcx, rdi
0x180018f17  mov     [rsp+40h+var_20], r12
0x180018f1c  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180018f21  mov     ebx, eax
0x180018f23  test    eax, eax
0x180018f25  js      loc_1800190F6
0x180018f2b  cmp     [r14+69h], r15b
0x180018f2f  jz      short loc_180018F5F
0x180018f31  mov     [rsp+40h+var_10], r15
0x180018f36  lea     rax, aWindirSystem32_0; "%windir%\\System32\\rekeywiz.exe"
0x180018f3d  mov     [rsp+40h+var_18], r15
0x180018f42  mov     r9d, 66h ; 'f'
0x180018f48  mov     rcx, rdi
0x180018f4b  mov     [rsp+40h+var_20], rax
0x180018f50  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180018f55  mov     ebx, eax
0x180018f57  test    eax, eax
0x180018f59  js      loc_1800190F6
0x180018f5f  lea     rax, [rbp+ppvOut]
0x180018f63  mov     [rbp+ppvOut], r15
0x180018f67  mov     [rsp+40h+var_10], rax
0x180018f6c  mov     r9d, 67h ; 'g'
0x180018f72  lea     rax, aSysdmCplEditus; "sysdm.cpl,EditUserProfiles"
0x180018f79  mov     rcx, rdi
0x180018f7c  mov     [rsp+40h+var_18], rax
0x180018f81  mov     [rsp+40h+var_20], r12
0x180018f86  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180018f8b  mov     ebx, eax
0x180018f8d  test    eax, eax
0x180018f8f  js      loc_1800190F6
0x180018f95  mov     rcx, [rbp+ppvOut]; this
0x180018f99  call    ?SetIcon@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@H@Z; CControlPanelNavLink::SetIcon(HINSTANCE__ *,int)
0x180018f9e  mov     ebx, eax
0x180018fa0  test    eax, eax
0x180018fa2  js      loc_1800190F6
0x180018fa8  lea     rax, aSysdmCplEditen; "sysdm.cpl,EditEnvironmentVariables"
0x180018faf  mov     [rsp+40h+var_10], r15
0x180018fb4  mov     [rsp+40h+var_18], rax
0x180018fb9  mov     r9d, 68h ; 'h'
0x180018fbf  mov     rcx, rdi
0x180018fc2  mov     [rsp+40h+var_20], r12
0x180018fc7  call    ?AddLinkShellEx@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkShellEx(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180018fcc  mov     ebx, eax
0x180018fce  test    eax, eax
0x180018fd0  js      loc_1800190F6
0x180018fd6  lea     rcx, [rbp+ppvOut]
0x180018fda  mov     dword ptr [rbp+ppvOut], r15d
0x180018fde  call    cs:__imp_WPC_InstallState
0x180018fe4  test    eax, eax
0x180018fe6  js      short loc_180019035
0x180018fe8  cmp     dword ptr [rbp+ppvOut], r15d
0x180018fec  jnz     short loc_180019035
0x180018fee  mov     edx, 1
0x180018ff3  mov     [rbp+arg_18], r15
0x180018ff7  lea     rax, [rbp+arg_18]
0x180018ffb  mov     rcx, rdi
0x180018ffe  mov     [rsp+40h+var_10], rax
0x180019003  lea     rax, aMicrosoftParen; "Microsoft.ParentalControls"
0x18001900a  mov     [rsp+40h+var_20], rax
0x18001900f  lea     r9d, [rdx+68h]
0x180019013  call    ?AddLinkControlPanel@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IPEBG2PEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkControlPanel(CPNAV_LIST,HINSTANCE__ *,uint,ushort const *,ushort const *,CControlPanelNavLink * *)
0x180019018  mov     ebx, eax
0x18001901a  test    eax, eax
0x18001901c  js      loc_1800190F6
0x180019022  mov     rcx, [rbp+arg_18]; this
0x180019026  call    ?SetIcon@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@H@Z; CControlPanelNavLink::SetIcon(HINSTANCE__ *,int)
0x18001902b  mov     ebx, eax
0x18001902d  test    eax, eax
0x18001902f  js      loc_1800190F6
0x180019035  call    ?EASPoliciesAreBeingEnforced@@YA_NXZ; EASPoliciesAreBeingEnforced(void)
0x18001903a  test    al, al
0x18001903c  jz      short loc_1800190AA
0x18001903e  mov     rsi, cs:g_hinst
0x180019045  lea     rdx, [rbp+ppvOut]
0x180019049  xor     ecx, ecx
0x18001904b  mov     [rbp+ppvOut], r15
0x18001904f  call    ?Create@CControlPanelNavLink@@SAJW4CPNAV_LIST@@PEAPEAV1@@Z; CControlPanelNavLink::Create(CPNAV_LIST,CControlPanelNavLink * *)
0x180019054  mov     ebx, eax
0x180019056  test    eax, eax
0x180019058  js      short loc_1800190A6
0x18001905a  mov     rdx, rsi; HINSTANCE
0x18001905d  mov     r12d, 0E6h
0x180019063  mov     rsi, [rbp+ppvOut]
0x180019067  mov     r8d, r12d; unsigned int
0x18001906a  mov     rcx, rsi; this
0x18001906d  call    ?SetName@CControlPanelNavLink@@QEAAJPEAUHINSTANCE__@@I@Z; CControlPanelNavLink::SetName(HINSTANCE__ *,uint)
0x180019072  mov     ebx, eax
0x180019074  test    eax, eax
0x180019076  js      short loc_180019091
0x180019078  mov     rdx, rsi; struct CControlPanelNavLink *
0x18001907b  mov     [rsi+20h], r15d
0x18001907f  mov     rcx, rdi; this
0x180019082  mov     [rsi+24h], r12d
0x180019086  call    ?Add@CControlPanelNavLinks@@QEAAJPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::Add(CControlPanelNavLink *)
0x18001908b  mov     ebx, eax
0x18001908d  test    eax, eax
0x18001908f  jns     short loc_1800190A6
0x180019091  test    rsi, rsi
0x180019094  jz      short loc_1800190A6
0x180019096  mov     rcx, rsi; this
0x180019099  call    ??1CControlPanelNavLink@@QEAA@XZ; CControlPanelNavLink::~CControlPanelNavLink(void)
0x18001909e  mov     rcx, rsi; lpMem
0x1800190a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800190a6  test    ebx, ebx
0x1800190a8  js      short loc_1800190F6
0x1800190aa  mov     rcx, [r14+60h]; punk
0x1800190ae  lea     r9, [rbp+ppvOut]; ppvOut
0x1800190b2  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800190b9  mov     [rbp+ppvOut], r15
0x1800190bd  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x1800190c4  call    cs:__imp_IUnknown_QueryService
0x1800190ca  mov     ebx, eax
0x1800190cc  test    eax, eax
0x1800190ce  js      short loc_1800190F6
0x1800190d0  mov     rcx, [rbp+ppvOut]; propBag
0x1800190d4  lea     rdx, aControlpanelna; "ControlPanelNavLinks"
0x1800190db  mov     r8, rdi; punk
0x1800190de  call    cs:__imp_PSPropertyBag_WriteUnknown
0x1800190e4  mov     rcx, [rbp+ppvOut]
0x1800190e8  mov     ebx, eax
0x1800190ea  mov     rax, [rcx]
0x1800190ed  mov     rax, [rax+10h]
0x1800190f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f6  mov     rax, [rdi]
0x1800190f9  mov     rcx, rdi
0x1800190fc  mov     rax, [rax+10h]
0x180019100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019105  jmp     short loc_18001910C
0x180019107  mov     ebx, 8007000Eh
0x18001910c  mov     rsi, [rsp+40h+arg_8]
0x180019111  mov     eax, ebx
0x180019113  mov     rbx, [rsp+40h+arg_0]
0x180019118  add     rsp, 40h
0x18001911c  pop     r15
0x18001911e  pop     r14
0x180019120  pop     r12
0x180019122  pop     rdi
0x180019123  pop     rbp
0x180019124  retn
```
