# CoCreateLocalServerIE

- ea: `0x18011c33c`
- end: `0x18011c5f6`
- name: `CoCreateLocalServerIE`
- size: `698`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18011c5fc`

## callees

- `0x180089154`
- `0x1800a25dc`
- `0x180113ac4`
- `0x180113b00`
- `0x18011c1e0`
- `0x18011c33c`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011c419`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18011c419`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x18011c395`
- `iertutil!__imp_?LCIEUnifiedFrame@@YA_NXZ` at `0x18011c395`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c366`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c3bb`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c366`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011c3bb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011c3a5`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011c3a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011c57d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011c57d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011c45a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18011c45a`

## pseudocode

```c
__int64 __fastcall CoCreateLocalServerIE(void *a1, __int64 a2, unsigned __int8 a3, __int64 a4, DWORD dwProcessId)
{
  int v5; // r15d
  const char *v8; // r9
  const char *v9; // r9
  unsigned int CurrentProcessManager; // ebx
  int ProcessForNav; // esi
  HRESULT v12; // ebx
  DWORD v13; // ecx
  void (__fastcall *v14)(__int64, _OWORD *); // rbx
  LPVOID v15; // rcx
  __int64 v17; // [rsp+60h] [rbp-1h] BYREF
  struct IEUserBroker *v18; // [rsp+68h] [rbp+7h] BYREF
  _OWORD v19[4]; // [rsp+70h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]
  LPVOID ppv; // [rsp+C0h] [rbp+5Fh] BYREF

  ppv = a1;
  v5 = a3;
  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
      v8);
  ppv = 0;
  if ( !LCIEUnifiedFrame() && !IsDualEngineProcess() )
    goto LABEL_16;
  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\inetcore\\lib\\nav\\iehelper.cpp",
      v9);
  CurrentProcessManager = IsoGetCurrentProcessManager();
  if ( !CurrentProcessManager || CurrentProcessManager == IsoGetAuthorityManager() )
  {
LABEL_16:
    v12 = CoCreateInstance(&CLSID_InternetExplorer, 0, 4u, &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e, &ppv);
LABEL_17:
    if ( v12 >= 0 )
      v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
              ppv,
              &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
              a2);
    goto LABEL_19;
  }
  v17 = 0;
  ProcessForNav = GetProcessForNav();
  v18 = 0;
  v12 = CoCreateUserBroker(&v18);
  if ( v12 >= 0 )
  {
    dwProcessId = 0;
    (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v18 + 24LL))(
      v18,
      0,
      0,
      &dwProcessId);
    v13 = -1;
    if ( dwProcessId )
      v13 = dwProcessId;
    AllowSetForegroundWindow(v13);
    *(_QWORD *)&v19[0] = 0;
    v12 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, _OWORD *))(*(_QWORD *)v18 + 48LL))(
            v18,
            &CLSID_CShdocvwBroker,
            &IID_IUnknown,
            v19);
    if ( v12 >= 0 )
    {
      v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v19[0])(
              *(_QWORD *)&v19[0],
              &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
              &v17);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v19[0] + 16LL))(*(_QWORD *)&v19[0]);
    }
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v12 >= 0 )
    {
      v14 = *(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v17 + 1256LL);
      v19[0] = *(_OWORD *)GlobalThreadState();
      v14(v17, v19);
      v12 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, LPVOID *, int, int, __int64, _DWORD, int, int))(*(_QWORD *)v17 + 768LL))(
              v17,
              1,
              &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
              &ppv,
              v5,
              ProcessForNav,
              a4,
              0,
              -1,
              -1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_17;
    }
  }
LABEL_19:
  v15 = ppv;
  if ( ppv )
  {
    if ( v12 < 0 )
    {
      (*(void (**)(void))(*(_QWORD *)ppv + 256LL))();
      v15 = ppv;
    }
    if ( v15 )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18011c33c  mov     [rsp-8+arg_0], rcx
0x18011c341  push    rbp
0x18011c342  push    rbx
0x18011c343  push    rsi
0x18011c344  push    rdi
0x18011c345  push    r14
0x18011c347  push    r15
0x18011c349  lea     rbp, [rsp-27h]
0x18011c34e  sub     rsp, 88h
0x18011c355  mov     ebx, 1000002Dh
0x18011c35a  movzx   r15d, r8b
0x18011c35e  mov     ecx, ebx
0x18011c360  mov     r14, r9
0x18011c363  mov     rdi, rdx
0x18011c366  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18011c36d  nop     dword ptr [rax+rax+00h]
0x18011c372  cmp     eax, 2
0x18011c375  jnz     short loc_18011C38D
0x18011c377  mov     rcx, [rbp+57h]; this
0x18011c37b  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x18011c382  mov     edx, 0D9h; void *
0x18011c387  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18011c38d  mov     [rbp+4Fh+arg_0], 0
0x18011c395  call    cs:__imp_?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18011c39c  nop     dword ptr [rax+rax+00h]
0x18011c3a1  test    al, al
0x18011c3a3  jnz     short loc_18011C3B9
0x18011c3a5  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18011c3ac  nop     dword ptr [rax+rax+00h]
0x18011c3b1  test    al, al
0x18011c3b3  jz      loc_18011C560
0x18011c3b9  mov     ecx, ebx
0x18011c3bb  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18011c3c2  nop     dword ptr [rax+rax+00h]
0x18011c3c7  cmp     eax, 2
0x18011c3ca  jnz     short loc_18011C3E2
0x18011c3cc  mov     rcx, [rbp+57h]; this
0x18011c3d0  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\lib\\nav\\iehelpe"...
0x18011c3d7  mov     edx, 0CAh; void *
0x18011c3dc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18011c3e2  call    ?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x18011c3e7  mov     ebx, eax
0x18011c3e9  test    eax, eax
0x18011c3eb  jz      loc_18011C560
0x18011c3f1  call    ?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x18011c3f6  cmp     ebx, eax
0x18011c3f8  jz      loc_18011C560
0x18011c3fe  call    ?GetProcessForNav@@YAKXZ; GetProcessForNav(void)
0x18011c403  lea     rcx, [rbp+4Fh+var_48]
0x18011c407  mov     [rbp+4Fh+var_50], 0
0x18011c40f  mov     esi, eax
0x18011c411  mov     [rbp+4Fh+var_48], 0
0x18011c419  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18011c420  nop     dword ptr [rax+rax+00h]
0x18011c425  mov     ebx, eax
0x18011c427  test    eax, eax
0x18011c429  js      loc_18011C5AA
0x18011c42f  mov     rcx, [rbp+4Fh+var_48]
0x18011c433  lea     r9, [rbp+4Fh+dwProcessId]
0x18011c437  mov     [rbp+4Fh+dwProcessId], 0
0x18011c43e  xor     r8d, r8d
0x18011c441  mov     rdx, [rcx]
0x18011c444  mov     rax, [rdx+18h]
0x18011c448  xor     edx, edx
0x18011c44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c44f  mov     eax, [rbp+4Fh+dwProcessId]
0x18011c452  or      ecx, 0FFFFFFFFh
0x18011c455  test    eax, eax
0x18011c457  cmovnz  ecx, eax; dwProcessId
0x18011c45a  call    cs:__imp_AllowSetForegroundWindow
0x18011c461  nop     dword ptr [rax+rax+00h]
0x18011c466  mov     rcx, [rbp+4Fh+var_48]
0x18011c46a  lea     r9, [rbp+4Fh+var_40]
0x18011c46e  mov     qword ptr [rbp+4Fh+var_40], 0
0x18011c476  lea     r8, IID_IUnknown
0x18011c47d  lea     rdx, CLSID_CShdocvwBroker
0x18011c484  mov     rax, [rcx]
0x18011c487  mov     rax, [rax+30h]
0x18011c48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c490  mov     ebx, eax
0x18011c492  test    eax, eax
0x18011c494  js      short loc_18011C4C2
0x18011c496  mov     rcx, qword ptr [rbp+4Fh+var_40]
0x18011c49a  lea     r8, [rbp+4Fh+var_50]
0x18011c49e  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18011c4a5  mov     rax, [rcx]
0x18011c4a8  mov     rax, [rax]
0x18011c4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c4b0  mov     rcx, qword ptr [rbp+4Fh+var_40]
0x18011c4b4  mov     ebx, eax
0x18011c4b6  mov     rax, [rcx]
0x18011c4b9  mov     rax, [rax+10h]
0x18011c4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c4c2  mov     rcx, [rbp+4Fh+var_48]
0x18011c4c6  mov     rax, [rcx]
0x18011c4c9  mov     rax, [rax+10h]
0x18011c4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c4d2  test    ebx, ebx
0x18011c4d4  js      loc_18011C5AA
0x18011c4da  mov     rax, [rbp+4Fh+var_50]
0x18011c4de  mov     rcx, [rax]
0x18011c4e1  mov     rbx, [rcx+4E8h]
0x18011c4e8  call    ?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18011c4ed  mov     rcx, [rbp+4Fh+var_50]
0x18011c4f1  lea     rdx, [rbp+4Fh+var_40]
0x18011c4f5  movups  xmm0, xmmword ptr [rax]
0x18011c4f8  mov     rax, rbx
0x18011c4fb  movdqu  [rbp+4Fh+var_40], xmm0
0x18011c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c505  mov     rcx, [rbp+4Fh+var_50]
0x18011c509  lea     r9, [rbp+4Fh+arg_0]
0x18011c50d  or      r8d, 0FFFFFFFFh
0x18011c511  mov     edx, 1
0x18011c516  mov     [rsp+0B0h+var_68], r8d
0x18011c51b  mov     [rsp+0B0h+var_70], r8d
0x18011c520  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x18011c527  mov     rax, [rcx]
0x18011c52a  mov     [rsp+0B0h+var_78], 0
0x18011c532  mov     [rsp+0B0h+var_80], r14
0x18011c537  mov     [rsp+0B0h+var_88], esi
0x18011c53b  mov     rax, [rax+300h]
0x18011c542  mov     dword ptr [rsp+0B0h+ppv], r15d
0x18011c547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c54c  mov     rcx, [rbp+4Fh+var_50]
0x18011c550  mov     ebx, eax
0x18011c552  mov     rax, [rcx]
0x18011c555  mov     rax, [rax+10h]
0x18011c559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c55e  jmp     short loc_18011C58B
0x18011c560  xor     edx, edx; pUnkOuter
0x18011c562  lea     rax, [rbp+4Fh+arg_0]
0x18011c566  lea     r9, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e; riid
0x18011c56d  mov     [rsp+0B0h+ppv], rax; ppv
0x18011c572  lea     rcx, CLSID_InternetExplorer; rclsid
0x18011c579  lea     r8d, [rdx+4]; dwClsContext
0x18011c57d  call    cs:__imp_CoCreateInstance
0x18011c584  nop     dword ptr [rax+rax+00h]
0x18011c589  mov     ebx, eax
0x18011c58b  test    ebx, ebx
0x18011c58d  js      short loc_18011C5AA
0x18011c58f  mov     rcx, [rbp+4Fh+arg_0]
0x18011c593  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x18011c59a  mov     r8, rdi
0x18011c59d  mov     rax, [rcx]
0x18011c5a0  mov     rax, [rax]
0x18011c5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c5a8  mov     ebx, eax
0x18011c5aa  mov     rcx, [rbp+4Fh+arg_0]
0x18011c5ae  test    rcx, rcx
0x18011c5b1  jz      short loc_18011C5E3
0x18011c5b3  test    ebx, ebx
0x18011c5b5  jns     short loc_18011C5CA
0x18011c5b7  mov     rax, [rcx]
0x18011c5ba  mov     rax, [rax+100h]
0x18011c5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c5c6  mov     rcx, [rbp+4Fh+arg_0]
0x18011c5ca  test    rcx, rcx
0x18011c5cd  jz      short loc_18011C5E3
0x18011c5cf  mov     [rbp+4Fh+arg_0], 0
0x18011c5d7  mov     rax, [rcx]
0x18011c5da  mov     rax, [rax+10h]
0x18011c5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c5e3  mov     eax, ebx
0x18011c5e5  add     rsp, 88h
0x18011c5ec  pop     r15
0x18011c5ee  pop     r14
0x18011c5f0  pop     rdi
0x18011c5f1  pop     rsi
0x18011c5f2  pop     rbx
0x18011c5f3  pop     rbp
0x18011c5f4  retn
```
