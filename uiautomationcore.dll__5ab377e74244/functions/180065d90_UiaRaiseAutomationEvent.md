# UiaRaiseAutomationEvent

- ea: `0x180065d90`
- end: `0x180066408`
- name: `UiaRaiseAutomationEvent`
- size: `1656`
- prototype: `HRESULT __stdcall(IRawElementProviderSimple *pProvider, EVENTID id)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ca7c0`

## callees

- `0x18000b790`
- `0x18002f580`
- `0x180061aec`
- `0x180063580`
- `0x1800637c0`
- `0x18006410c`
- `0x180064788`
- `0x180065aac`
- `0x180065d90`
- `0x1800b8448`
- `0x18011c6d4`
- `0x180126010`
- `0x1801260ac`
- `0x18013a96c`
- `0x180186cd0`
- `0x1801b62e0`
- `0x1801e8320`
- `0x1802c349d`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180066146`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180066146`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180065e90`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180065e90`
- `OLEAUT32!__imp_VariantInit` at `0x1800662ce`
- `OLEAUT32!__imp_VariantInit` at `0x1800662ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800663d9`
- `OLEAUT32!__imp_VariantClear` at `0x1800663d9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800661d8`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180066219`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800661d8`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180066219`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180065fde`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180065fde`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x18006603d`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x18006603d`

## string_xrefs

- `0x1800660a5`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall UiaRaiseAutomationEvent(IRawElementProviderSimple *pProvider, EVENTID id)
{
  int v2; // r8d
  PVOID *v5; // rcx
  int v6; // ecx
  HRESULT v7; // ebx
  const char *v8; // r9
  HWND v9; // rdi
  __int64 v10; // rax
  __int64 i; // rbx
  unsigned __int128 v12; // kr00_16
  struct IRawElementProviderSimple *v13; // rbx
  int v14; // r8d
  PVOID v15; // rcx
  DWORD *v17; // r15
  DWORD *v18; // r13
  DWORD v19; // r12d
  LONG v20; // r8d
  int v21; // r8d
  PVOID v22; // rcx
  int v23; // eax
  DWORD v24; // edx
  HRESULT (__stdcall *QueryInterface)(IRawElementProviderSimple *, const IID *const, void **); // rdi
  HRESULT (__stdcall *v26)(IRawElementProviderSimple *, const IID *const, void **); // rdi
  int *v27; // [rsp+20h] [rbp-59h]
  WINBOOL fPending[2]; // [rsp+30h] [rbp-49h] BYREF
  HWND hwnd; // [rsp+38h] [rbp-41h] BYREF
  struct IRawElementProviderFragment *v30; // [rsp+40h] [rbp-39h] BYREF
  struct IRawElementProviderFragment *v31; // [rsp+48h] [rbp-31h] BYREF
  struct IRawElementProviderSimple *v32; // [rsp+50h] [rbp-29h] BYREF
  __int64 v33; // [rsp+58h] [rbp-21h] BYREF
  struct UiaEventArgs v34; // [rsp+60h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v36[2]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    v27 = (int *)v36;
    McGenEventWrite_EventWriteTransfer(pProvider, UIAutomationCoreAPI_UiaRaiseEvent_Start);
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      v2,
      (unsigned int)"UiaRaiseAutomationEvent",
      (char)pProvider,
      id);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( pProvider )
  {
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( !BasicUiaUtils::s_isDesktop )
    {
LABEL_26:
      v34.Type = EventArgsType_Simple;
      v34.EventId = id;
      v13 = pProvider;
      v36[0] = pProvider;
      ((void (__fastcall *)(IRawElementProviderSimple *))pProvider->lpVtbl->AddRef)(pProvider);
      if ( !BasicUiaUtils::s_isDesktopDetermined )
      {
        BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
        BasicUiaUtils::s_isDesktopDetermined = 1;
      }
      if ( !BasicUiaUtils::s_isDesktop )
      {
        v33 = 0;
        QueryInterface = pProvider->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
        if ( ((int (__fastcall *)(IRawElementProviderSimple *, GUID *, __int64 *))QueryInterface)(
               pProvider,
               &GUID_ff41cccb_7dd5_44fc_aa63_e27925eaee99,
               &v33) >= 0 )
        {
          hwnd = 0;
          v31 = 0;
          v32 = 0;
          VariantInit(&pvarg);
          pvarg.llVal = 0;
          v30 = 0;
          *(_QWORD *)fPending = 0;
          v26 = pProvider->lpVtbl->QueryInterface;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hwnd);
          if ( ((int (__fastcall *)(IRawElementProviderSimple *, GUID *, HWND *))v26)(
                 pProvider,
                 &GUID_f7063da8_8359_439c_9297_bbc5299a7d87,
                 &hwnd) >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            if ( (int)ProviderCallouts::Navigate(
                        (struct IRawElementProviderFragment *)hwnd,
                        NavigateDirection_Parent,
                        &v31) >= 0 )
            {
              if ( v31 )
              {
                if ( (int)Microsoft::WRL::ComPtr<IRawElementProviderFragmentRoot>::As<IRawElementProviderSimple>(
                            &v31,
                            &v32) >= 0
                  && (int)ProviderCallouts::RawGetPropertyValue(v32, 30024, &pvarg) >= 0 )
                {
                  if ( pvarg.llVal )
                  {
                    if ( !wcsncmp_0(pvarg.bstrVal, L"UIX", 3u) )
                    {
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                      if ( (int)ProviderCallouts::Navigate(v31, NavigateDirection_FirstChild, &v30) >= 0
                        && v30
                        && (int)Microsoft::WRL::ComPtr<IRawElementProviderFragmentRoot>::As<IRawElementProviderSimple>(
                                  &v30,
                                  fPending) >= 0 )
                      {
                        Microsoft::WRL::ComPtr<IUnknown>::operator=(v36, fPending);
                        v13 = (struct IRawElementProviderSimple *)v36[0];
                      }
                    }
                  }
                }
              }
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(fPending);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          VariantClear(&pvarg);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hwnd);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      }
      EventManager::RaiseEvent(v13, &v34, 0);
      if ( v13 )
        ((void (__fastcall *)(struct IRawElementProviderSimple *))v13->lpVtbl->Release)(v13);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_sqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          v14,
          (unsigned int)"UiaRaiseAutomationEvent",
          (char)pProvider,
          id);
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(v15, "x");
      return 0;
    }
    LODWORD(v30) = 0;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        (_DWORD)v5,
        (unsigned int)UiaProviderCallout_Start,
        (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
        0,
        0);
    v7 = ((__int64 (__fastcall *)(IRawElementProviderSimple *, struct IRawElementProviderFragment **))pProvider->lpVtbl->get_ProviderOptions)(
           pProvider,
           &v30);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        v6,
        (unsigned int)UiaProviderCallout_Stop,
        (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
        0,
        0);
    if ( v7 >= 0 )
    {
      if ( (char)v30 >= 0 )
      {
        fPending[0] = 0;
        if ( __std_init_once_begin_initialize(&BasicUtils::s_initOnceIsInCrossMachineRemoteSession, 0, fPending, 0) )
        {
          if ( fPending[0] )
          {
            v23 = lambda_312a8970364be71481f3490781272cd3_::operator()();
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x37F,
                (unsigned int)"wil",
                (const char *)(unsigned int)v23,
                (int)v27);
              v24 = 4;
            }
            else
            {
              v24 = 0;
            }
            InitOnceComplete(&BasicUtils::s_initOnceIsInCrossMachineRemoteSession, v24, 0);
          }
        }
        else
        {
          wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v8);
        }
        if ( !BasicUtils::s_inCrossMachineRemoteSession )
        {
          fPending[0] = 0;
          if ( id )
          {
            v9 = 0;
            hwnd = 0;
            v10 = *((_QWORD *)&MsaaEventMap + 1);
            v12 = MsaaEventMap;
            v36[0] = v12 >> 64;
            for ( i = v12; i != v10; i += 48 )
            {
              if ( *(_DWORD *)(i + 4) == id )
              {
                v17 = *(DWORD **)(i + 16);
                v18 = *(DWORD **)(i + 24);
                while ( v17 != v18 )
                {
                  v19 = *v17;
                  if ( IsWinEventHookInstalled(*v17) )
                  {
                    if ( !v9 || (v20 = fPending[0]) == 0 )
                    {
                      if ( (int)GetProviderEventInfo(pProvider, &hwnd, fPending) < 0 )
                        goto LABEL_26;
                      v20 = fPending[0];
                      v9 = hwnd;
                      if ( !fPending[0] )
                      {
                        if ( (int)EventMap::AddEntry((char *)g_TheEventMap, hwnd, pProvider, fPending) < 0 )
                          goto LABEL_26;
                        v20 = fPending[0];
                      }
                    }
                    NotifyWinEvent(v19, v9, v20, 0);
                  }
                  ++v17;
                }
                v10 = v36[0];
              }
            }
            if ( (unsigned int)(id - 49152) <= 0x3FFF )
            {
              LODWORD(v31) = 0;
              FireWinEventIfHookInstalled(pProvider, id, 1, &hwnd, fPending, (int *)&v31);
            }
          }
        }
      }
      goto LABEL_26;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
      (const char *)(unsigned int)v7,
      (int)v27);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v21,
        (unsigned int)"UiaRaiseAutomationEvent",
        (char)pProvider,
        id);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v22, "x");
    return v7;
  }
  else
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
      WPP_SF_sqd((unsigned int)v5[2], 13, v2, (unsigned int)"UiaRaiseAutomationEvent", 0, id);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v5, "x");
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180065d90  mov     [rsp-8+arg_10], rbx
0x180065d95  push    rbp
0x180065d96  push    rsi
0x180065d97  push    rdi
0x180065d98  push    r12
0x180065d9a  push    r13
0x180065d9c  push    r14
0x180065d9e  push    r15
0x180065da0  lea     rbp, [rsp-27h]
0x180065da5  sub     rsp, 0A0h
0x180065dac  mov     rax, cs:__security_cookie
0x180065db3  xor     rax, rsp
0x180065db6  mov     [rbp+57h+var_38], rax
0x180065dba  mov     r14d, edx
0x180065dbd  mov     rsi, rcx
0x180065dc0  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180065dc7  jnz     loc_180066235
0x180065dcd  lea     r12, WPP_GLOBAL_Control
0x180065dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180065ddb  cmp     rcx, r12
0x180065dde  jz      short loc_180065E0C
0x180065de0  test    byte ptr [rcx+1Ch], 10h
0x180065de4  jz      short loc_180065E0C
0x180065de6  mov     edx, 0Ch
0x180065deb  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x180065df0  mov     [rsp+0D0h+var_B0], rsi; int
0x180065df5  lea     r9, aUiaraiseautoma_2; "UiaRaiseAutomationEvent"
0x180065dfc  mov     rcx, [rcx+10h]
0x180065e00  call    WPP_SF_sqd
0x180065e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e0c  xor     r15d, r15d
0x180065e0f  test    rsi, rsi
0x180065e12  jz      loc_18006605D
0x180065e18  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180065e1e  nop
0x180065e1f  test    al, al
0x180065e21  jz      loc_1800661D3
0x180065e27  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r15b; bool BasicUiaUtils::s_isDesktop
0x180065e2e  jz      loc_180065F04
0x180065e34  mov     dword ptr [rbp+57h+var_90], r15d
0x180065e38  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180065e3f  jnz     loc_180066171
0x180065e45  mov     rax, [rsi]
0x180065e48  lea     rdx, [rbp+57h+var_90]
0x180065e4c  mov     rcx, rsi
0x180065e4f  mov     rax, [rax+18h]
0x180065e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e58  mov     ebx, eax
0x180065e5a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180065e61  jnz     loc_180066191
0x180065e67  test    ebx, ebx
0x180065e69  js      loc_18006609E
0x180065e6f  test    byte ptr [rbp+57h+var_90], 80h
0x180065e73  jnz     loc_180065F04
0x180065e79  mov     [rbp+57h+fPending], r15d
0x180065e7d  xor     r9d, r9d; lpContext
0x180065e80  lea     r8, [rbp+57h+fPending]; fPending
0x180065e84  xor     edx, edx; dwFlags
0x180065e86  lea     rbx, ?s_initOnceIsInCrossMachineRemoteSession@BasicUtils@@0T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE BasicUtils::s_initOnceIsInCrossMachineRemoteSession
0x180065e8d  mov     rcx, rbx; lpInitOnce
0x180065e90  call    cs:__imp___std_init_once_begin_initialize
0x180065e96  test    eax, eax
0x180065e98  jz      loc_1800660FB
0x180065e9e  cmp     [rbp+57h+fPending], r15d
0x180065ea2  jnz     loc_180066135
0x180065ea8  cmp     cs:?s_inCrossMachineRemoteSession@BasicUtils@@0_NA, r15b; bool BasicUtils::s_inCrossMachineRemoteSession
0x180065eaf  jnz     short loc_180065F04
0x180065eb1  mov     [rbp+57h+fPending], r15d
0x180065eb5  test    r14d, r14d
0x180065eb8  jz      short loc_180065F04
0x180065eba  mov     rdi, r15
0x180065ebd  mov     [rbp+57h+hwnd], r15
0x180065ec1  mov     rbx, qword ptr cs:?MsaaEventMap@@3V?$vector@UEventMapEntry@@V?$allocator@UEventMapEntry@@@std@@@std@@B; std::vector<EventMapEntry> const MsaaEventMap
0x180065ec8  mov     rax, qword ptr cs:?MsaaEventMap@@3V?$vector@UEventMapEntry@@V?$allocator@UEventMapEntry@@@std@@@std@@B+8; std::vector<EventMapEntry> const MsaaEventMap
0x180065ecf  mov     [rbp+57h+var_48], rax
0x180065ed3  cmp     rbx, rax
0x180065ed6  jz      short loc_180065EE8
0x180065ed8  cmp     [rbx+4], r14d
0x180065edc  jz      loc_180065FCB
0x180065ee2  add     rbx, 30h ; '0'
0x180065ee6  jmp     short loc_180065ED3
0x180065ee8  lea     eax, [r14-0C000h]
0x180065eef  xor     r15d, r15d
0x180065ef2  cmp     eax, 3FFFh
0x180065ef7  jbe     loc_180066255
0x180065efd  lea     r12, WPP_GLOBAL_Control
0x180065f04  mov     [rbp+57h+var_70.Type], r15d
0x180065f08  mov     [rbp+57h+var_70.EventId], r14d
0x180065f0c  mov     rbx, rsi
0x180065f0f  mov     [rbp+57h+var_48], rbx
0x180065f13  mov     rax, [rsi]
0x180065f16  mov     rcx, rsi
0x180065f19  mov     rax, [rax+8]
0x180065f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f22  nop
0x180065f23  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180065f29  nop
0x180065f2a  test    al, al
0x180065f2c  jz      loc_180066214
0x180065f32  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r15b; bool BasicUiaUtils::s_isDesktop
0x180065f39  jz      loc_18006628D
0x180065f3f  xor     r8d, r8d; bool
0x180065f42  lea     rdx, [rbp+57h+var_70]; struct UiaEventArgs *
0x180065f46  mov     rcx, rbx; struct IRawElementProviderSimple *
0x180065f49  call    ?RaiseEvent@EventManager@@SAXPEAUIRawElementProviderSimple@@PEAUUiaEventArgs@@_N@Z; EventManager::RaiseEvent(IRawElementProviderSimple *,UiaEventArgs *,bool)
0x180065f4e  nop
0x180065f4f  test    rbx, rbx
0x180065f52  jz      short loc_180065F64
0x180065f54  mov     rax, [rbx]
0x180065f57  mov     rcx, rbx
0x180065f5a  mov     rax, [rax+10h]
0x180065f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f63  nop
0x180065f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f6b  cmp     rcx, r12
0x180065f6e  jz      short loc_180065F95
0x180065f70  test    byte ptr [rcx+1Ch], 10h
0x180065f74  jz      short loc_180065F95
0x180065f76  mov     edx, 0Dh
0x180065f7b  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x180065f80  mov     [rsp+0D0h+var_B0], rsi
0x180065f85  lea     r9, aUiaraiseautoma_2; "UiaRaiseAutomationEvent"
0x180065f8c  mov     rcx, [rcx+10h]
0x180065f90  call    WPP_SF_sqd
0x180065f95  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180065f9c  jnz     loc_180066115
0x180065fa2  xor     eax, eax
0x180065fa4  mov     rcx, [rbp+57h+var_38]
0x180065fa8  xor     rcx, rsp; StackCookie
0x180065fab  call    __security_check_cookie
0x180065fb0  mov     rbx, [rsp+0D0h+arg_10]
0x180065fb8  add     rsp, 0A0h
0x180065fbf  pop     r15
0x180065fc1  pop     r14
0x180065fc3  pop     r13
0x180065fc5  pop     r12
0x180065fc7  pop     rdi
0x180065fc8  pop     rsi
0x180065fc9  pop     rbp
0x180065fca  retn
0x180065fcb  mov     r15, [rbx+10h]
0x180065fcf  mov     r13, [rbx+18h]
0x180065fd3  cmp     r15, r13
0x180065fd6  jz      short loc_180066049
0x180065fd8  mov     r12d, [r15]
0x180065fdb  mov     ecx, r12d; event
0x180065fde  call    cs:__imp_IsWinEventHookInstalled
0x180065fe4  test    eax, eax
0x180065fe6  jz      short loc_180066043
0x180065fe8  test    rdi, rdi
0x180065feb  jnz     short loc_180066052
0x180065fed  lea     r8, [rbp+57h+fPending]; int *
0x180065ff1  lea     rdx, [rbp+57h+hwnd]; HWND *
0x180065ff5  mov     rcx, rsi; struct IRawElementProviderSimple *
0x180065ff8  call    ?GetProviderEventInfo@@YAJPEAUIRawElementProviderSimple@@PEAPEAUHWND__@@PEAJ@Z; GetProviderEventInfo(IRawElementProviderSimple *,HWND__ * *,long *)
0x180065ffd  test    eax, eax
0x180065fff  js      loc_180066285
0x180066005  mov     r8d, [rbp+57h+fPending]
0x180066009  mov     rdi, [rbp+57h+hwnd]
0x18006600d  test    r8d, r8d
0x180066010  jnz     short loc_180066034
0x180066012  lea     r9, [rbp+57h+fPending]; int *
0x180066016  mov     r8, rsi; struct IRawElementProviderSimple *
0x180066019  mov     rdx, rdi; HWND
0x18006601c  lea     rcx, ?g_TheEventMap@@3V?$object_without_destructor_on_shutdown@VEventMap@@@wil@@A; Parameter
0x180066023  call    ?AddEntry@EventMap@@QEAAJPEAUHWND__@@PEAUIRawElementProviderSimple@@PEAJ@Z; EventMap::AddEntry(HWND__ *,IRawElementProviderSimple *,long *)
0x180066028  test    eax, eax
0x18006602a  js      loc_180066285
0x180066030  mov     r8d, [rbp+57h+fPending]; idObject
0x180066034  xor     r9d, r9d; idChild
0x180066037  mov     rdx, rdi; hwnd
0x18006603a  mov     ecx, r12d; event
0x18006603d  call    cs:__imp_NotifyWinEvent
0x180066043  add     r15, 4
0x180066047  jmp     short loc_180065FD3
0x180066049  mov     rax, [rbp+57h+var_48]
0x18006604d  jmp     loc_180065EE2
0x180066052  mov     r8d, [rbp+57h+fPending]
0x180066056  test    r8d, r8d
0x180066059  jnz     short loc_180066034
0x18006605b  jmp     short loc_180065FED
0x18006605d  cmp     rcx, r12
0x180066060  jz      short loc_180066087
0x180066062  test    byte ptr [rcx+1Ch], 10h
0x180066066  jz      short loc_180066087
0x180066068  mov     edx, 0Dh
0x18006606d  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x180066072  mov     [rsp+0D0h+var_B0], rsi
0x180066077  lea     r9, aUiaraiseautoma_2; "UiaRaiseAutomationEvent"
0x18006607e  mov     rcx, [rcx+10h]
0x180066082  call    WPP_SF_sqd
0x180066087  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18006608e  jnz     loc_180066151
0x180066094  mov     eax, 80070057h
0x180066099  jmp     loc_180065FA4
0x18006609e  mov     rcx, [rbp+5Fh]; this
0x1800660a2  mov     r9d, ebx; char *
0x1800660a5  lea     r8, aOnecoreWindows_45; "onecore\\windows\\accessibletech\\uiaut"...
0x1800660ac  mov     edx, 1B8h; void *
0x1800660b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800660b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660bd  cmp     rcx, r12
0x1800660c0  jz      short loc_1800660E7
0x1800660c2  test    byte ptr [rcx+1Ch], 10h
0x1800660c6  jz      short loc_1800660E7
0x1800660c8  mov     edx, 0Dh
0x1800660cd  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x1800660d2  mov     [rsp+0D0h+var_B0], rsi
0x1800660d7  lea     r9, aUiaraiseautoma_2; "UiaRaiseAutomationEvent"
0x1800660de  mov     rcx, [rcx+10h]
0x1800660e2  call    WPP_SF_sqd
0x1800660e7  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800660ee  jnz     loc_1800661F4
0x1800660f4  mov     eax, ebx
0x1800660f6  jmp     loc_180065FA4
0x1800660fb  mov     rcx, [rbp+5Fh]; this
0x1800660ff  lea     r8, aWil; "wil"
0x180066106  mov     edx, 37Ah; void *
0x18006610b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180066110  jmp     loc_180065EA8
0x180066115  lea     rax, [rbp+57h+var_48]
0x180066119  mov     [rsp+0D0h+var_B0], rax
0x18006611e  mov     r9d, 1
0x180066124  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x18006612b  call    McGenEventWrite_EventWriteTransfer
0x180066130  jmp     loc_180065FA2
0x180066135  call    _lambda_312a8970364be71481f3490781272cd3___operator__
0x18006613a  test    eax, eax
0x18006613c  js      short loc_1800661B1
0x18006613e  xor     edx, edx; dwFlags
0x180066140  xor     r8d, r8d; lpContext
0x180066143  mov     rcx, rbx; lpInitOnce
0x180066146  call    cs:__imp_InitOnceComplete
0x18006614c  jmp     loc_180065EA8
0x180066151  lea     rax, [rbp+57h+var_48]
0x180066155  mov     [rsp+0D0h+var_B0], rax
0x18006615a  mov     r9d, 1
0x180066160  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x180066167  call    McGenEventWrite_EventWriteTransfer
0x18006616c  jmp     loc_180066094
0x180066171  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x180066176  xor     r9d, r9d
0x180066179  lea     r8, aIrawelementpro_9; "IRawElementProviderSimple::get_Provider"...
0x180066180  lea     rdx, UiaProviderCallout_Start
0x180066187  call    McTemplateU0zqq_EventWriteTransfer
0x18006618c  jmp     loc_180065E45
0x180066191  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x180066196  xor     r9d, r9d
0x180066199  lea     r8, aIrawelementpro_9; "IRawElementProviderSimple::get_Provider"...
0x1800661a0  lea     rdx, UiaProviderCallout_Stop
0x1800661a7  call    McTemplateU0zqq_EventWriteTransfer
0x1800661ac  jmp     loc_180065E67
0x1800661b1  mov     rcx, [rbp+5Fh]; this
0x1800661b5  mov     r9d, eax; char *
0x1800661b8  lea     r8, aWil; "wil"
0x1800661bf  mov     edx, 37Fh; void *
0x1800661c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800661c9  mov     edx, 4
0x1800661ce  jmp     loc_180066140
0x1800661d3  mov     ecx, 1800h; nIndex
0x1800661d8  call    cs:__imp_GetSystemMetrics
0x1800661de  test    eax, eax
0x1800661e0  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x1800661e7  nop
0x1800661e8  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800661ef  jmp     loc_180065E27
0x1800661f4  lea     rax, [rbp+57h+var_48]
0x1800661f8  mov     [rsp+0D0h+var_B0], rax
0x1800661fd  mov     r9d, 1
0x180066203  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x18006620a  call    McGenEventWrite_EventWriteTransfer
0x18006620f  jmp     loc_1800660F4
0x180066214  mov     ecx, 1800h; nIndex
0x180066219  call    cs:__imp_GetSystemMetrics
0x18006621f  test    eax, eax
0x180066221  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x180066228  nop
0x180066229  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180066230  jmp     loc_180065F32
0x180066235  lea     rax, [rbp+57h+var_48]
0x180066239  mov     [rsp+0D0h+var_B0], rax
0x18006623e  mov     r9d, 1
0x180066244  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Start
0x18006624b  call    McGenEventWrite_EventWriteTransfer
0x180066250  jmp     loc_180065DCD
0x180066255  mov     dword ptr [rbp+57h+var_88], r15d
0x180066259  lea     rax, [rbp+57h+var_88]
0x18006625d  mov     [rsp+0D0h+var_A8], rax; int *
0x180066262  lea     rax, [rbp+57h+fPending]
0x180066266  mov     [rsp+0D0h+var_B0], rax; int *
0x18006626b  lea     r9, [rbp+57h+hwnd]; HWND *
0x18006626f  mov     r8d, 1; int
0x180066275  mov     edx, r14d; event
0x180066278  mov     rcx, rsi; struct IRawElementProviderSimple *
0x18006627b  call    ?FireWinEventIfHookInstalled@@YAXPEAUIRawElementProviderSimple@@HHPEAPEAUHWND__@@PEAJPEAH@Z; FireWinEventIfHookInstalled(IRawElementProviderSimple *,int,int,HWND__ * *,long *,int *)
0x180066280  jmp     loc_180065EFD
0x180066285  xor     r15d, r15d
0x180066288  jmp     loc_180065EFD
0x18006628d  mov     [rbp+57h+var_78], r15
0x180066291  mov     rax, [rsi]
  ... truncated ...
```
