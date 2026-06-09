# UiaRaiseStructureChangedEvent

- ea: `0x180061b50`
- end: `0x1800621c1`
- name: `UiaRaiseStructureChangedEvent`
- size: `1649`
- prototype: `HRESULT __stdcall(IRawElementProviderSimple *pProvider, StructureChangeType structureChangeType, int *pRuntimeId, int cRuntimeIdLen)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800caef0`

## callees

- `0x180013d90`
- `0x18002f2f0`
- `0x18002f580`
- `0x1800320ec`
- `0x180061aec`
- `0x180061b50`
- `0x180062520`
- `0x180063580`
- `0x1800637c0`
- `0x18006410c`
- `0x180064788`
- `0x1800c20c0`
- `0x1801118f0`
- `0x18011c6d4`
- `0x180186cd0`
- `0x1801b62e0`
- `0x1801e8320`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180062130`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180062130`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180061c71`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180061c71`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061dfa`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180061dfa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061dec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006207d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180062102`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180061dec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006207d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180062102`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800621a5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800621a5`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180061cb6`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180061d1f`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180061cb6`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x180061d1f`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x180061d11`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x180061d84`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x180061d11`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!NotifyWinEvent` at `0x180061d84`

## string_xrefs

- `0x180061fa7`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`
- `0x180062052`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`
- `0x1800620d7`: `onecore\windows\accessibletech\uiautomationcore\uiautomationcoreapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall UiaRaiseStructureChangedEvent(
        IRawElementProviderSimple *pProvider,
        StructureChangeType structureChangeType,
        int *pRuntimeId,
        int cRuntimeIdLen)
{
  PVOID *v8; // rcx
  int v9; // ecx
  HRESULT v10; // ebx
  const char *v11; // r9
  DWORD v12; // edi
  DWORD v13; // r15d
  HWND v14; // rbx
  int ProviderEventInfo; // eax
  WINBOOL v16; // r8d
  struct IRawElementProviderSimple *v17; // r8
  WINBOOL v18; // r8d
  struct IRawElementProviderSimple *v19; // r8
  SAFEARRAY *v20; // rdi
  int v21; // r8d
  PVOID v22; // rcx
  struct IRawElementProviderFragment *v24; // rax
  struct IRawElementProviderFragment *v25; // rbx
  int RuntimeIdFromPartial; // eax
  HRESULT v27; // edi
  int v28; // eax
  HRESULT v29; // r15d
  int v30; // r8d
  PVOID v31; // rcx
  int v32; // r8d
  int v33; // eax
  DWORD v34; // edx
  HWND *v35; // [rsp+20h] [rbp-79h]
  WINBOOL fPending; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v37[4]; // [rsp+34h] [rbp-65h] BYREF
  int v38; // [rsp+38h] [rbp-61h] BYREF
  SAFEARRAY *psa; // [rsp+40h] [rbp-59h] BYREF
  int v40; // [rsp+48h] [rbp-51h]
  int *v41; // [rsp+50h] [rbp-49h]
  struct UiaEventArgs v42; // [rsp+58h] [rbp-41h] BYREF
  StructureChangeType v43; // [rsp+60h] [rbp-39h]
  int v44; // [rsp+64h] [rbp-35h]
  int *v45; // [rsp+68h] [rbp-31h]
  int v46; // [rsp+70h] [rbp-29h]
  int v47; // [rsp+74h] [rbp-25h]
  _QWORD v48[2]; // [rsp+78h] [rbp-21h] BYREF
  StructureChangeType v49; // [rsp+88h] [rbp-11h]
  HWND hwnd[2]; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    v35 = hwnd;
    McGenEventWrite_EventWriteTransfer(pProvider, UIAutomationCoreAPI_UiaRaiseEvent_Start);
  }
  v48[0] = "UiaRaiseStructureChangedEvent";
  v48[1] = pProvider;
  v49 = structureChangeType;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (_DWORD)pRuntimeId,
      (unsigned int)"UiaRaiseStructureChangedEvent",
      (char)pProvider,
      structureChangeType);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( pProvider )
  {
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( !BasicUiaUtils::s_isDesktop )
      goto LABEL_39;
    v38 = 0;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        (_DWORD)v8,
        (unsigned int)UiaProviderCallout_Start,
        (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
        0,
        0);
    v10 = ((__int64 (__fastcall *)(IRawElementProviderSimple *, int *))pProvider->lpVtbl->get_ProviderOptions)(
            pProvider,
            &v38);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        v9,
        (unsigned int)UiaProviderCallout_Stop,
        (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
        0,
        0);
    if ( v10 >= 0 )
    {
      if ( (v38 & 0x80u) != 0 )
        goto LABEL_39;
      fPending = 0;
      if ( __std_init_once_begin_initialize(&BasicUtils::s_initOnceIsInCrossMachineRemoteSession, 0, &fPending, 0) )
      {
        if ( fPending )
        {
          v33 = lambda_312a8970364be71481f3490781272cd3_::operator()();
          if ( v33 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37F,
              (unsigned int)"wil",
              (const char *)(unsigned int)v33,
              (int)v35);
            v34 = 4;
          }
          else
          {
            v34 = 0;
          }
          InitOnceComplete(&BasicUtils::s_initOnceIsInCrossMachineRemoteSession, v34, 0);
        }
      }
      else
      {
        wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v11);
      }
      if ( BasicUtils::s_inCrossMachineRemoteSession )
        goto LABEL_39;
      if ( structureChangeType )
      {
        if ( structureChangeType == StructureChangeType_ChildRemoved )
        {
          v12 = 32771;
          v13 = 32769;
        }
        else
        {
          if ( structureChangeType != StructureChangeType_ChildrenInvalidated
            && structureChangeType != StructureChangeType_ChildrenBulkAdded
            && (unsigned int)(structureChangeType - 4) > 1 )
          {
            goto LABEL_39;
          }
          v13 = 0;
          v12 = 32772;
        }
      }
      else
      {
        v12 = 0x8000;
        v13 = 32770;
      }
      v14 = 0;
      hwnd[0] = 0;
      fPending = 0;
      if ( !IsWinEventHookInstalled(v12) )
        goto LABEL_29;
      ProviderEventInfo = GetProviderEventInfo(pProvider, hwnd, &fPending);
      v14 = hwnd[0];
      if ( ProviderEventInfo < 0 )
        goto LABEL_29;
      v16 = fPending;
      if ( !fPending )
      {
        v17 = pProvider;
        if ( structureChangeType == StructureChangeType_ChildRemoved )
          v17 = 0;
        if ( (int)EventMap::AddEntry((char *)g_TheEventMap, hwnd[0], v17, &fPending) < 0 )
          goto LABEL_29;
        v16 = fPending;
      }
      NotifyWinEvent(v12, v14, v16, 0);
LABEL_29:
      if ( v13 && IsWinEventHookInstalled(v13) )
      {
        if ( v14 )
        {
          v18 = fPending;
          if ( fPending )
            goto LABEL_38;
        }
        if ( (int)GetProviderEventInfo(pProvider, hwnd, &fPending) >= 0 )
        {
          v18 = fPending;
          v14 = hwnd[0];
          if ( fPending )
          {
LABEL_38:
            NotifyWinEvent(v13, v14, v18, 0);
            goto LABEL_39;
          }
          v19 = pProvider;
          if ( structureChangeType == StructureChangeType_ChildRemoved )
            v19 = 0;
          if ( (int)EventMap::AddEntry((char *)g_TheEventMap, hwnd[0], v19, &fPending) >= 0 )
          {
            v18 = fPending;
            goto LABEL_38;
          }
        }
      }
LABEL_39:
      v44 = 0;
      v47 = 0;
      v42.Type = EventArgsType_StructureChanged;
      v42.EventId = 20002;
      v43 = structureChangeType;
      v45 = pRuntimeId;
      v46 = cRuntimeIdLen;
      v20 = 0;
      hwnd[0] = 0;
      psa = 0;
      v40 = 0;
      v41 = 0;
      if ( structureChangeType != StructureChangeType_ChildRemoved || !pRuntimeId || *pRuntimeId != 3 )
      {
LABEL_40:
        EventManager::RaiseEvent(pProvider, &v42, 0);
        if ( psa )
          SafeArrayUnaccessData(psa);
        if ( v20 )
          SafeArrayDestroy(v20);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_sqd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            v21,
            (unsigned int)"UiaRaiseStructureChangedEvent",
            (char)pProvider,
            structureChangeType);
        if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(v22, "x");
        return 0;
      }
      v24 = (struct IRawElementProviderFragment *)QI<IRawElementProviderFragment>(pProvider);
      v25 = v24;
      if ( v24 )
      {
        RuntimeIdFromPartial = UiaNode::ProviderGetRuntimeIdFromPartial(
                                 v24,
                                 pRuntimeId,
                                 cRuntimeIdLen,
                                 (struct tagSAFEARRAY **)hwnd);
        v27 = RuntimeIdFromPartial;
        if ( RuntimeIdFromPartial < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F0,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
            (const char *)(unsigned int)RuntimeIdFromPartial,
            (int)v35);
          ((void (__fastcall *)(struct IRawElementProviderFragment *))v25->lpVtbl->Release)(v25);
          if ( psa )
            SafeArrayUnaccessData(psa);
          AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(hwnd);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_sqd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              v32,
              (unsigned int)"UiaRaiseStructureChangedEvent",
              (char)pProvider,
              1);
        }
        else
        {
          v20 = (SAFEARRAY *)hwnd[0];
          if ( !hwnd[0] )
            goto LABEL_61;
          v28 = SafeArrayAccessor<int>::Access(&psa, hwnd[0]);
          v29 = v28;
          if ( v28 >= 0 )
          {
            v45 = v41;
            v46 = v40;
            goto LABEL_61;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F4,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
            (const char *)(unsigned int)v28,
            (int)v35);
          ((void (__fastcall *)(struct IRawElementProviderFragment *))v25->lpVtbl->Release)(v25);
          if ( psa )
            SafeArrayUnaccessData(psa);
          AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(hwnd);
          FlatApiCallTrace::~FlatApiCallTrace((FlatApiCallTrace *)v48);
          v27 = v29;
        }
        UiaRaiseTextEditTextChangedEvent_::_2_::PerfMarkerTrace::_PerfMarkerTrace(v37);
        return v27;
      }
LABEL_61:
      if ( v25 )
        ((void (__fastcall *)(struct IRawElementProviderFragment *))v25->lpVtbl->Release)(v25);
      goto LABEL_40;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautomationcoreapi.cpp",
      (const char *)(unsigned int)v10,
      (int)v35);
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        v30,
        (unsigned int)"UiaRaiseStructureChangedEvent",
        (char)pProvider,
        structureChangeType);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v31, "x");
    return v10;
  }
  else
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
      WPP_SF_sqd(
        (unsigned int)v8[2],
        13,
        (_DWORD)pRuntimeId,
        (unsigned int)"UiaRaiseStructureChangedEvent",
        0,
        structureChangeType);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v8, "x");
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180061b50  push    rbp
0x180061b52  push    rbx
0x180061b53  push    rsi
0x180061b54  push    rdi
0x180061b55  push    r12
0x180061b57  push    r13
0x180061b59  push    r14
0x180061b5b  push    r15
0x180061b5d  lea     rbp, [rsp-1Fh]
0x180061b62  sub     rsp, 0B8h
0x180061b69  mov     rax, cs:__security_cookie
0x180061b70  xor     rax, rsp
0x180061b73  mov     [rbp+57h+var_50], rax
0x180061b77  mov     r13d, r9d
0x180061b7a  mov     r12, r8
0x180061b7d  mov     r14d, edx
0x180061b80  mov     rsi, rcx
0x180061b83  mov     edi, 1
0x180061b88  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180061b8f  jnz     loc_180062014
0x180061b95  lea     r15, aUiaraisestruct_0; "UiaRaiseStructureChangedEvent"
0x180061b9c  mov     [rbp+57h+var_78], r15
0x180061ba0  mov     [rbp+57h+var_70], rsi
0x180061ba4  mov     [rbp+57h+var_68], r14d
0x180061ba8  lea     rax, WPP_GLOBAL_Control
0x180061baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bb6  cmp     rcx, rax
0x180061bb9  jz      short loc_180061BEA
0x180061bbb  test    byte ptr [rcx+1Ch], 10h
0x180061bbf  jz      short loc_180061BEA
0x180061bc1  mov     edx, 0Ch
0x180061bc6  mov     [rsp+0F0h+var_C8], r14d
0x180061bcb  mov     qword ptr [rsp+0F0h+var_D0], rsi; int
0x180061bd0  mov     r9, r15
0x180061bd3  mov     rcx, [rcx+10h]
0x180061bd7  call    WPP_SF_sqd
0x180061bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180061be3  lea     rax, WPP_GLOBAL_Control
0x180061bea  test    rsi, rsi
0x180061bed  jz      loc_180061F2E
0x180061bf3  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180061bf9  nop
0x180061bfa  test    al, al
0x180061bfc  jz      loc_1800621A0
0x180061c02  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isDesktop
0x180061c09  jz      loc_180061D91
0x180061c0f  mov     [rbp+57h+var_B8], 0
0x180061c16  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180061c1d  jnz     loc_18006213B
0x180061c23  mov     rax, [rsi]
0x180061c26  lea     rdx, [rbp+57h+var_B8]
0x180061c2a  mov     rcx, rsi
0x180061c2d  mov     rax, [rax+18h]
0x180061c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c36  mov     ebx, eax
0x180061c38  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180061c3f  jnz     loc_18006215E
0x180061c45  test    ebx, ebx
0x180061c47  js      loc_180061FA0
0x180061c4d  test    byte ptr [rbp+57h+var_B8], 80h
0x180061c51  jnz     loc_180061D91
0x180061c57  mov     [rbp+57h+fPending], 0
0x180061c5e  xor     r9d, r9d; lpContext
0x180061c61  lea     r8, [rbp+57h+fPending]; fPending
0x180061c65  xor     edx, edx; dwFlags
0x180061c67  lea     rbx, ?s_initOnceIsInCrossMachineRemoteSession@BasicUtils@@0T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE BasicUtils::s_initOnceIsInCrossMachineRemoteSession
0x180061c6e  mov     rcx, rbx; lpInitOnce
0x180061c71  call    cs:__imp___std_init_once_begin_initialize
0x180061c77  test    eax, eax
0x180061c79  jz      loc_180062031
0x180061c7f  cmp     [rbp+57h+fPending], 0
0x180061c83  jnz     loc_18006211F
0x180061c89  cmp     cs:?s_inCrossMachineRemoteSession@BasicUtils@@0_NA, 0; bool BasicUtils::s_inCrossMachineRemoteSession
0x180061c90  jnz     loc_180061D91
0x180061c96  mov     ecx, r14d
0x180061c99  test    r14d, r14d
0x180061c9c  jnz     loc_180061E90
0x180061ca2  mov     edi, 8000h
0x180061ca7  lea     r15d, [rdi+2]
0x180061cab  xor     ebx, ebx
0x180061cad  mov     [rbp+57h+hwnd], rbx
0x180061cb1  mov     [rbp+57h+fPending], ebx
0x180061cb4  mov     ecx, edi; event
0x180061cb6  call    cs:__imp_IsWinEventHookInstalled
0x180061cbc  test    eax, eax
0x180061cbe  jz      short loc_180061D17
0x180061cc0  lea     r8, [rbp+57h+fPending]; int *
0x180061cc4  lea     rdx, [rbp+57h+hwnd]; HWND *
0x180061cc8  mov     rcx, rsi; struct IRawElementProviderSimple *
0x180061ccb  call    ?GetProviderEventInfo@@YAJPEAUIRawElementProviderSimple@@PEAPEAUHWND__@@PEAJ@Z; GetProviderEventInfo(IRawElementProviderSimple *,HWND__ * *,long *)
0x180061cd0  mov     rbx, [rbp+57h+hwnd]
0x180061cd4  test    eax, eax
0x180061cd6  js      short loc_180061D17
0x180061cd8  mov     r8d, [rbp+57h+fPending]
0x180061cdc  test    r8d, r8d
0x180061cdf  jnz     short loc_180061D09
0x180061ce1  mov     r8, rsi
0x180061ce4  xor     eax, eax
0x180061ce6  cmp     r14d, 1
0x180061cea  cmovz   r8, rax; struct IRawElementProviderSimple *
0x180061cee  lea     r9, [rbp+57h+fPending]; int *
0x180061cf2  mov     rdx, rbx; HWND
0x180061cf5  lea     rcx, ?g_TheEventMap@@3V?$object_without_destructor_on_shutdown@VEventMap@@@wil@@A; Parameter
0x180061cfc  call    ?AddEntry@EventMap@@QEAAJPEAUHWND__@@PEAUIRawElementProviderSimple@@PEAJ@Z; EventMap::AddEntry(HWND__ *,IRawElementProviderSimple *,long *)
0x180061d01  test    eax, eax
0x180061d03  js      short loc_180061D17
0x180061d05  mov     r8d, [rbp+57h+fPending]; idObject
0x180061d09  xor     r9d, r9d; idChild
0x180061d0c  mov     rdx, rbx; hwnd
0x180061d0f  mov     ecx, edi; event
0x180061d11  call    cs:__imp_NotifyWinEvent
0x180061d17  test    r15d, r15d
0x180061d1a  jz      short loc_180061D8A
0x180061d1c  mov     ecx, r15d; event
0x180061d1f  call    cs:__imp_IsWinEventHookInstalled
0x180061d25  test    eax, eax
0x180061d27  jz      short loc_180061D8A
0x180061d29  test    rbx, rbx
0x180061d2c  jnz     loc_180061E7E
0x180061d32  lea     r8, [rbp+57h+fPending]; int *
0x180061d36  lea     rdx, [rbp+57h+hwnd]; HWND *
0x180061d3a  mov     rcx, rsi; struct IRawElementProviderSimple *
0x180061d3d  call    ?GetProviderEventInfo@@YAJPEAUIRawElementProviderSimple@@PEAPEAUHWND__@@PEAJ@Z; GetProviderEventInfo(IRawElementProviderSimple *,HWND__ * *,long *)
0x180061d42  test    eax, eax
0x180061d44  js      short loc_180061D8A
0x180061d46  mov     r8d, [rbp+57h+fPending]
0x180061d4a  mov     rbx, [rbp+57h+hwnd]
0x180061d4e  test    r8d, r8d
0x180061d51  jnz     short loc_180061D7B
0x180061d53  mov     r8, rsi
0x180061d56  xor     eax, eax
0x180061d58  cmp     r14d, 1
0x180061d5c  cmovz   r8, rax; struct IRawElementProviderSimple *
0x180061d60  lea     r9, [rbp+57h+fPending]; int *
0x180061d64  mov     rdx, rbx; HWND
0x180061d67  lea     rcx, ?g_TheEventMap@@3V?$object_without_destructor_on_shutdown@VEventMap@@@wil@@A; Parameter
0x180061d6e  call    ?AddEntry@EventMap@@QEAAJPEAUHWND__@@PEAUIRawElementProviderSimple@@PEAJ@Z; EventMap::AddEntry(HWND__ *,IRawElementProviderSimple *,long *)
0x180061d73  test    eax, eax
0x180061d75  js      short loc_180061D8A
0x180061d77  mov     r8d, [rbp+57h+fPending]; idObject
0x180061d7b  xor     r9d, r9d; idChild
0x180061d7e  mov     rdx, rbx; hwnd
0x180061d81  mov     ecx, r15d; event
0x180061d84  call    cs:__imp_NotifyWinEvent
0x180061d8a  lea     r15, aUiaraisestruct_0; "UiaRaiseStructureChangedEvent"
0x180061d91  mov     [rbp+57h+var_8C], 0
0x180061d98  mov     [rbp+57h+var_7C], 0
0x180061d9f  mov     [rbp+57h+var_98.Type], 2
0x180061da6  mov     [rbp+57h+var_98.EventId], 4E22h
0x180061dad  mov     [rbp+57h+var_90], r14d
0x180061db1  mov     [rbp+57h+var_88], r12
0x180061db5  mov     [rbp+57h+var_80], r13d
0x180061db9  xor     edi, edi
0x180061dbb  mov     [rbp+57h+hwnd], rdi
0x180061dbf  mov     [rbp+57h+psa], rdi
0x180061dc3  mov     [rbp+57h+var_A8], edi
0x180061dc6  mov     [rbp+57h+var_A0], rdi
0x180061dca  cmp     r14d, 1
0x180061dce  jz      loc_180061EA6
0x180061dd4  xor     r8d, r8d; bool
0x180061dd7  lea     rdx, [rbp+57h+var_98]; struct UiaEventArgs *
0x180061ddb  mov     rcx, rsi; struct IRawElementProviderSimple *
0x180061dde  call    ?RaiseEvent@EventManager@@SAXPEAUIRawElementProviderSimple@@PEAUUiaEventArgs@@_N@Z; EventManager::RaiseEvent(IRawElementProviderSimple *,UiaEventArgs *,bool)
0x180061de3  mov     rcx, [rbp+57h+psa]; psa
0x180061de7  test    rcx, rcx
0x180061dea  jz      short loc_180061DF2
0x180061dec  call    cs:__imp_SafeArrayUnaccessData
0x180061df2  test    rdi, rdi
0x180061df5  jz      short loc_180061E00
0x180061df7  mov     rcx, rdi; psa
0x180061dfa  call    cs:__imp_SafeArrayDestroy
0x180061e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180061e07  lea     rax, WPP_GLOBAL_Control
0x180061e0e  cmp     rcx, rax
0x180061e11  jz      short loc_180061E38
0x180061e13  test    byte ptr [rcx+1Ch], 10h
0x180061e17  jz      short loc_180061E38
0x180061e19  mov     edx, 0Dh
0x180061e1e  mov     [rsp+0F0h+var_C8], r14d
0x180061e23  mov     qword ptr [rsp+0F0h+var_D0], rsi
0x180061e28  lea     r9, aUiaraisestruct_0; "UiaRaiseStructureChangedEvent"
0x180061e2f  mov     rcx, [rcx+10h]
0x180061e33  call    WPP_SF_sqd
0x180061e38  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180061e3f  jz      short loc_180061E5C
0x180061e41  lea     rax, [rbp+57h+hwnd]
0x180061e45  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180061e4a  mov     r9d, 1
0x180061e50  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x180061e57  call    McGenEventWrite_EventWriteTransfer
0x180061e5c  xor     eax, eax
0x180061e5e  mov     rcx, [rbp+57h+var_50]
0x180061e62  xor     rcx, rsp; StackCookie
0x180061e65  call    __security_check_cookie
0x180061e6a  add     rsp, 0B8h
0x180061e71  pop     r15
0x180061e73  pop     r14
0x180061e75  pop     r13
0x180061e77  pop     r12
0x180061e79  pop     rdi
0x180061e7a  pop     rsi
0x180061e7b  pop     rbx
0x180061e7c  pop     rbp
0x180061e7d  retn
0x180061e7e  mov     r8d, [rbp+57h+fPending]
0x180061e82  test    r8d, r8d
0x180061e85  jnz     loc_180061D7B
0x180061e8b  jmp     loc_180061D32
0x180061e90  sub     ecx, edi
0x180061e92  jnz     loc_180061F7F
0x180061e98  mov     edi, 8003h
0x180061e9d  lea     r15d, [rdi-2]
0x180061ea1  jmp     loc_180061CAB
0x180061ea6  test    r12, r12
0x180061ea9  jz      loc_180061DD4
0x180061eaf  cmp     dword ptr [r12], 3
0x180061eb4  jnz     loc_180061DD4
0x180061eba  mov     rcx, rsi
0x180061ebd  call    ??$QI@UIRawElementProviderFragment@@@@YAPEAUIRawElementProviderFragment@@PEAUIUnknown@@@Z; QI<IRawElementProviderFragment>(IUnknown *)
0x180061ec2  mov     rbx, rax
0x180061ec5  test    rax, rax
0x180061ec8  jz      short loc_180061F14
0x180061eca  lea     r9, [rbp+57h+hwnd]; struct tagSAFEARRAY **
0x180061ece  mov     r8d, r13d; int
0x180061ed1  mov     rdx, r12; int *
0x180061ed4  mov     rcx, rax; struct IRawElementProviderFragment *
0x180061ed7  call    ?ProviderGetRuntimeIdFromPartial@UiaNode@@SAJPEAUIRawElementProviderFragment@@PEBHHPEAPEAUtagSAFEARRAY@@@Z; UiaNode::ProviderGetRuntimeIdFromPartial(IRawElementProviderFragment *,int const *,int,tagSAFEARRAY * *)
0x180061edc  mov     edi, eax
0x180061ede  test    eax, eax
0x180061ee0  js      loc_18006204B
0x180061ee6  mov     rdi, [rbp+57h+hwnd]
0x180061eea  test    rdi, rdi
0x180061eed  jz      short loc_180061F14
0x180061eef  mov     rdx, rdi
0x180061ef2  lea     rcx, [rbp+57h+psa]
0x180061ef6  call    ?Access@?$SafeArrayAccessor@H@@QEAAJPEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<int>::Access(tagSAFEARRAY *,ushort)
0x180061efb  mov     r15d, eax
0x180061efe  test    eax, eax
0x180061f00  js      loc_1800620D0
0x180061f06  mov     rax, [rbp+57h+var_A0]
0x180061f0a  mov     [rbp+57h+var_88], rax
0x180061f0e  mov     eax, [rbp+57h+var_A8]
0x180061f11  mov     [rbp+57h+var_80], eax
0x180061f14  test    rbx, rbx
0x180061f17  jz      short loc_180061F29
0x180061f19  mov     rax, [rbx]
0x180061f1c  mov     rcx, rbx
0x180061f1f  mov     rax, [rax+10h]
0x180061f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f28  nop
0x180061f29  jmp     loc_180061DD4
0x180061f2e  cmp     rcx, rax
0x180061f31  jz      short loc_180061F54
0x180061f33  test    byte ptr [rcx+1Ch], 10h
0x180061f37  jz      short loc_180061F54
0x180061f39  mov     edx, 0Dh
0x180061f3e  mov     [rsp+0F0h+var_C8], r14d
0x180061f43  mov     qword ptr [rsp+0F0h+var_D0], rsi
0x180061f48  mov     r9, r15
0x180061f4b  mov     rcx, [rcx+10h]
0x180061f4f  call    WPP_SF_sqd
0x180061f54  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180061f5b  jz      short loc_180061F75
0x180061f5d  lea     rax, [rbp+57h+hwnd]
0x180061f61  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180061f66  mov     r9d, edi
0x180061f69  lea     rdx, UIAutomationCoreAPI_UiaRaiseEvent_Stop; "x"
0x180061f70  call    McGenEventWrite_EventWriteTransfer
0x180061f75  mov     eax, 80070057h
0x180061f7a  jmp     loc_180061E5E
0x180061f7f  sub     ecx, edi
0x180061f81  jz      short loc_180061F93
0x180061f83  sub     ecx, edi
0x180061f85  jz      short loc_180061F93
0x180061f87  sub     ecx, edi
0x180061f89  jz      short loc_180061F93
0x180061f8b  cmp     ecx, edi
0x180061f8d  jnz     loc_180061D91
0x180061f93  xor     r15d, r15d
0x180061f96  mov     edi, 8004h
0x180061f9b  jmp     loc_180061CAB
0x180061fa0  mov     rcx, [rbp+5Fh]; this
0x180061fa4  mov     r9d, ebx; char *
0x180061fa7  lea     r8, aOnecoreWindows_45; "onecore\\windows\\accessibletech\\uiaut"...
0x180061fae  mov     edx, 1D9h; void *
0x180061fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180061fbf  lea     rax, WPP_GLOBAL_Control
0x180061fc6  cmp     rcx, rax
0x180061fc9  jz      short loc_180061FEC
0x180061fcb  test    byte ptr [rcx+1Ch], 10h
0x180061fcf  jz      short loc_180061FEC
0x180061fd1  mov     edx, 0Dh
0x180061fd6  mov     [rsp+0F0h+var_C8], r14d
0x180061fdb  mov     qword ptr [rsp+0F0h+var_D0], rsi
0x180061fe0  mov     r9, r15
0x180061fe3  mov     rcx, [rcx+10h]
0x180061fe7  call    WPP_SF_sqd
0x180061fec  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180061ff3  jz      short loc_18006200D
  ... truncated ...
```
