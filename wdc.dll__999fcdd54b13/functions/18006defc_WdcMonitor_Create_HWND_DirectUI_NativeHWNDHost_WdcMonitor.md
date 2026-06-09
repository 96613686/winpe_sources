# WdcMonitor::Create(HWND__ *,DirectUI::NativeHWNDHost * *,WdcMonitor * *)

- ea: `0x18006defc`
- end: `0x18006e45f`
- name: `?Create@WdcMonitor@@SAJPEAUHWND__@@PEAPEAVNativeHWNDHost@DirectUI@@PEAPEAV1@@Z`
- size: `1379`
- prototype: `__int64 __fastcall(HWND, struct DirectUI::NativeHWNDHost **, struct WdcMonitor **)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006c530`

## callees

- `0x180006e70`
- `0x18000b854`
- `0x180023cf4`
- `0x18003a3c0`
- `0x18003a7cc`
- `0x18003b0ac`
- `0x18003e4bc`
- `0x18006cde8`
- `0x18006d734`
- `0x18006defc`
- `0x18006f37c`
- `0x18006f888`
- `0x1800713bc`
- `0x180073170`
- `0x18007b558`
- `0x18007d1cc`
- `0x18007d750`
- `0x18007db64`
- `0x180086010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x18006e423`
- `KERNEL32!SetErrorMode` at `0x18006e423`
- `KERNEL32!GetErrorMode` at `0x18006e416`
- `KERNEL32!GetErrorMode` at `0x18006e416`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18006e117`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18006e117`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18006e201`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18006e332`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18006e201`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18006e332`
- `DUI70!StrToID` at `0x18006e1f5`
- `DUI70!StrToID` at `0x18006e326`
- `DUI70!StrToID` at `0x18006e1f5`
- `DUI70!StrToID` at `0x18006e326`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18006e3f7`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18006e3f7`
- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHIPEAPEAV12@@Z` at `0x18006e0f5`
- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHIPEAPEAV12@@Z` at `0x18006e0f5`
- `DUI70!?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18006e147`
- `DUI70!?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18006e147`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18006e175`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18006e175`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e19f`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e2db`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e356`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e19f`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e2db`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e356`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006e1d2`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006e314`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006e38b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006e1d2`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006e314`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18006e38b`
- `DUI70!??0DUIFactory@DirectUI@@QEAA@PEAUHWND__@@@Z` at `0x18006e23c`
- `DUI70!??0DUIFactory@DirectUI@@QEAA@PEAUHWND__@@@Z` at `0x18006e23c`
- `DUI70!?LoadFromResource@DUIFactory@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG1PEAVElement@2@PEAKPEAPEAV42@1@Z` at `0x18006e296`
- `DUI70!?LoadFromResource@DUIFactory@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG1PEAVElement@2@PEAKPEAPEAV42@1@Z` at `0x18006e296`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18006e2ab`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18006e2ab`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18006e3c5`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18006e3c5`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x18006e3d3`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x18006e3d3`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18006e3de`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18006e3de`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x18006e3eb`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x18006e3eb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18006e036`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18006e036`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18006e052`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18006e052`

## string_xrefs

- `0x18006e01a`: `WdcMonitor::Create`

## pseudocode

```c
__int64 __fastcall WdcMonitor::Create(HWND a1, struct DirectUI::NativeHWNDHost **a2, struct WdcMonitor **a3)
{
  WdcMonitor *v3; // rdi
  int v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // rdx
  WdcMonitor *v9; // rax
  void *v10; // rdx
  __int64 v11; // r8
  int v13; // eax
  int v14; // ebx
  WdcMonitor *v15; // r12
  __int64 v16; // rsi
  unsigned __int16 v17; // ax
  struct DirectUI::Element *Descendent; // r15
  DirectUI::DUIFactory *v19; // rax
  DirectUI::DUIFactory *v20; // rax
  unsigned int *v21; // r12
  int v22; // eax
  unsigned __int16 v23; // ax
  struct DirectUI::Element *v24; // r15
  struct DirectUI::NativeHWNDHost **v25; // rcx
  struct DirectUI::NativeHWNDHost *v26; // rax
  UINT ErrorMode; // eax
  __int64 v28; // [rsp+20h] [rbp-69h]
  struct DirectUI::DUIXmlParser *v29; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v30; // [rsp+68h] [rbp-21h] BYREF
  struct DirectUI::Element *v31; // [rsp+70h] [rbp-19h] BYREF
  struct DirectUI::NativeHWNDHost *v32; // [rsp+78h] [rbp-11h] BYREF
  struct WdcMonitor **v33; // [rsp+80h] [rbp-9h]
  char v34[16]; // [rsp+88h] [rbp-1h] BYREF
  struct DirectUI::NativeHWNDHost **v35; // [rsp+98h] [rbp+Fh] BYREF

  v3 = 0;
  v33 = a3;
  v35 = a2;
  v32 = 0;
  v31 = 0;
  v29 = 0;
  if ( (Microsoft_Windows_Diagnosis_WDCEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(WDC_PROVIDER_GUID_Context, Launch_Start, a3, 1, v34);
  v6 = DirectUI::ClassInfo<WdcMonitor,DirectUI::HWNDElement,DirectUI::StandardCreator<WdcMonitor>>::Register();
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  v6 = DirectUI::ClassInfo<WdcGraph,DirectUI::HWNDHost,DirectUI::StandardCreator<WdcGraph>>::Register();
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  v6 = DirectUI::ClassInfo<WdcListView,DirectUI::HWNDElement,DirectUI::StandardCreator<WdcListView>>::Register();
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  v6 = DirectUI::ClassInfo<WdcSplitter,DirectUI::Thumb,DirectUI::StandardCreator<WdcSplitter>>::Register();
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  v6 = DirectUI::ClassInfo<WdcEdit,DirectUI::Edit,DirectUI::StandardCreator<WdcEdit>>::Register();
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  v6 = DirectUI::ClassInfo<WdcTab,DirectUI::HWNDHost,DirectUI::StandardCreator<WdcTab>>::Register();
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  *a3 = 0;
  v9 = (WdcMonitor *)DirectUI::HAllocAndZero((DirectUI *)0x5A0, v8);
  v3 = v9;
  if ( !v9 )
  {
LABEL_13:
    v7 = -2147024882;
    LODWORD(v28) = -2147024882;
    goto LABEL_14;
  }
  WdcMonitor::WdcMonitor(v9);
  if ( !*((_QWORD *)v3 + 35) )
  {
    (**(void (__fastcall ***)(WdcMonitor *, _QWORD))v3)(v3, 0);
    DirectUI::HFree(v3, v10);
    v3 = 0;
    goto LABEL_13;
  }
  v6 = DirectUI::NativeHWNDHost::Create(L"RPM_Window", a1, 0, 0x80000000, 0x80000000, 0, 0, 0, 0x40000000, 2u, &v32);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  g_MainWindow = a1;
  *((_QWORD *)v3 + 36) = DirectUI::NativeHWNDHost::GetHWND(v32);
  v30 = 0;
  v13 = DirectUI::HWNDElement::Initialize(v3, *((HWND *)v3 + 36), 1, 0, 0, &v30);
  v7 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v28) = v13;
    goto LABEL_14;
  }
  v6 = DirectUI::DUIXmlParser::Create(
         &v29,
         0,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))WdcPE,
         0);
  v7 = v6;
  if ( v6 < 0
    || (v6 = DirectUI::DUIXmlParser::SetXMLFromResource(v29, 0x7530u, g_hInstance, (HINSTANCE)&_ImageBase),
        v7 = v6,
        v6 < 0)
    || (v6 = DirectUI::DUIXmlParser::CreateElement(v29, L"resmon", v3, 0, 0, &v31), v7 = v6, v6 < 0) )
  {
LABEL_4:
    LODWORD(v28) = v6;
LABEL_14:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\monitor.cpp",
      "WdcMonitor::Create",
      0,
      L"FAILURE: 0x%08x",
      v28);
    goto LABEL_15;
  }
  v14 = 0;
  v15 = v3;
  v16 = 0;
  do
  {
    v17 = StrToID(off_1800AE6F8[3 * v16]);
    Descendent = DirectUI::Element::FindDescendent(v3, v17);
    if ( !Descendent )
      goto LABEL_44;
    if ( ((v14 - 1) & 0xFFFFFFFC) != 0 || v14 == 2 )
    {
      v21 = (unsigned int *)&dword_1800AE6F4[6 * v16];
      if ( (int)DirectUI::DUIXmlParser::SetXMLFromResource(v29, *v21, g_hInstance, (HINSTANCE)&_ImageBase) < 0 )
        goto LABEL_43;
      v22 = DirectUI::DUIXmlParser::CreateElement(v29, off_1800AE6F8[3 * v16], Descendent, 0, 0, &v31);
    }
    else
    {
      v19 = (DirectUI::DUIFactory *)operator new(0x20u);
      v20 = (DirectUI::DUIFactory *)DirectUI::DUIFactory::DUIFactory(v19, *((HWND *)v3 + 36));
      if ( !v20 )
        goto LABEL_44;
      *((_QWORD *)v15 + v16 + 37) = v20;
      v21 = (unsigned int *)&dword_1800AE6F4[6 * v16];
      if ( (int)DirectUI::DUIFactory::LoadFromResource(
                  v20,
                  g_hInstance,
                  (const unsigned __int16 *)*(unsigned __int16 *)v21,
                  off_1800AE6F8[3 * v16],
                  0,
                  0,
                  &v31,
                  0) < 0 )
        goto LABEL_43;
      v22 = DirectUI::Element::Add(Descendent, v31);
    }
    if ( v22 < 0 )
      goto LABEL_42;
    v23 = StrToID((&off_1800AE700)[3 * v16]);
    v24 = DirectUI::Element::FindDescendent(v3, v23);
    if ( v24 && (int)DirectUI::DUIXmlParser::SetXMLFromResource(v29, *v21, g_hInstance, (HINSTANCE)&_ImageBase) >= 0 )
    {
      DirectUI::DUIXmlParser::CreateElement(v29, (&off_1800AE700)[3 * v16], v24, 0, 0, &v31);
LABEL_42:
      v15 = v3;
      goto LABEL_44;
    }
LABEL_43:
    v15 = v3;
LABEL_44:
    ++v14;
    ++v16;
  }
  while ( v14 < 5 );
  v6 = WdcMonitor::Setup(v3);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_4;
  DirectUI::Element::SetAccessible(v3, 1);
  DirectUI::Element::SetAccRole(v3, 9);
  DirectUI::Element::SetVisible(v3, 1);
  DirectUI::NativeHWNDHost::Host(v32, v3);
  DirectUI::Element::EndDefer(v3, v30);
  v25 = v35;
  *v33 = v3;
  v26 = v32;
  *v25 = v32;
  *((_QWORD *)v3 + 33) = v26;
  ErrorMode = GetErrorMode();
  SetErrorMode(ErrorMode | 0x8001);
  memset_0(qword_1800B1960, -1, sizeof(qword_1800B1960));
  WdcMonitor::ApplySettings(v3, (const struct _WDC_SETTINGS *)&WdcDefaultSettings);
  WdcMonitor::Start(v3, 0);
  v7 = 0;
LABEL_15:
  if ( v29 )
  {
    DirectUI::DUIXmlParser::Destroy(v29);
    v29 = 0;
  }
  if ( v7 < 0 && v3 )
    DirectUI::Element::Destroy(v3, 1);
  if ( (Microsoft_Windows_Diagnosis_WDCEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(WDC_PROVIDER_GUID_Context, Launch_Stop, v11, 1, &v35);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006defc  mov     [rsp-8+arg_18], rbx
0x18006df01  push    rbp
0x18006df02  push    rsi
0x18006df03  push    rdi
0x18006df04  push    r12
0x18006df06  push    r13
0x18006df08  push    r14
0x18006df0a  push    r15
0x18006df0c  lea     rbp, [rsp-27h]
0x18006df11  sub     rsp, 0B0h
0x18006df18  mov     rax, cs:__security_cookie
0x18006df1f  xor     rax, rsp
0x18006df22  mov     [rbp+57h+var_38], rax
0x18006df26  xor     edi, edi
0x18006df28  mov     [rbp+57h+var_60], r8
0x18006df2c  test    cs:Microsoft_Windows_Diagnosis_WDCEnableBits, 8
0x18006df33  mov     r14, r8
0x18006df36  mov     [rbp+57h+var_48], rdx
0x18006df3a  mov     rsi, rcx
0x18006df3d  mov     [rbp+57h+var_68], 0
0x18006df45  mov     [rbp+57h+var_70], 0
0x18006df4d  mov     [rbp+57h+var_80], 0
0x18006df55  jz      short loc_18006DF77
0x18006df57  lea     rax, [rbp+57h+var_58]
0x18006df5b  lea     r9d, [rdi+1]
0x18006df5f  mov     [rsp+0E0h+var_C0], rax
0x18006df64  lea     rdx, Launch_Start
0x18006df6b  lea     rcx, WDC_PROVIDER_GUID_Context
0x18006df72  call    McGenEventWrite_EventWriteTransfer
0x18006df77  call    ?Register@?$ClassInfo@VWdcMonitor@@VHWNDElement@DirectUI@@V?$StandardCreator@VWdcMonitor@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WdcMonitor,DirectUI::HWNDElement,DirectUI::StandardCreator<WdcMonitor>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18006df7c  mov     ebx, eax
0x18006df7e  test    eax, eax
0x18006df80  jns     short loc_18006DF8B
0x18006df82  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18006df86  jmp     loc_18006E010
0x18006df8b  call    ?Register@?$ClassInfo@VWdcGraph@@VHWNDHost@DirectUI@@V?$StandardCreator@VWdcGraph@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WdcGraph,DirectUI::HWNDHost,DirectUI::StandardCreator<WdcGraph>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18006df90  mov     ebx, eax
0x18006df92  test    eax, eax
0x18006df94  js      short loc_18006DF82
0x18006df96  call    ?Register@?$ClassInfo@VWdcListView@@VHWNDElement@DirectUI@@V?$StandardCreator@VWdcListView@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WdcListView,DirectUI::HWNDElement,DirectUI::StandardCreator<WdcListView>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18006df9b  mov     ebx, eax
0x18006df9d  test    eax, eax
0x18006df9f  js      short loc_18006DF82
0x18006dfa1  call    ?Register@?$ClassInfo@VWdcSplitter@@VThumb@DirectUI@@V?$StandardCreator@VWdcSplitter@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WdcSplitter,DirectUI::Thumb,DirectUI::StandardCreator<WdcSplitter>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18006dfa6  mov     ebx, eax
0x18006dfa8  test    eax, eax
0x18006dfaa  js      short loc_18006DF82
0x18006dfac  call    ?Register@?$ClassInfo@VWdcEdit@@VEdit@DirectUI@@V?$StandardCreator@VWdcEdit@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WdcEdit,DirectUI::Edit,DirectUI::StandardCreator<WdcEdit>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18006dfb1  mov     ebx, eax
0x18006dfb3  test    eax, eax
0x18006dfb5  js      short loc_18006DF82
0x18006dfb7  call    ?Register@?$ClassInfo@VWdcTab@@VHWNDHost@DirectUI@@V?$StandardCreator@VWdcTab@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<WdcTab,DirectUI::HWNDHost,DirectUI::StandardCreator<WdcTab>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18006dfbc  mov     ebx, eax
0x18006dfbe  test    eax, eax
0x18006dfc0  js      short loc_18006DF82
0x18006dfc2  mov     ecx, 5A0h; this
0x18006dfc7  mov     [r14], rdi
0x18006dfca  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18006dfcf  mov     rdi, rax
0x18006dfd2  test    rax, rax
0x18006dfd5  jz      short loc_18006E007
0x18006dfd7  mov     rcx, rax; this
0x18006dfda  call    ??0WdcMonitor@@QEAA@XZ; WdcMonitor::WdcMonitor(void)
0x18006dfdf  cmp     qword ptr [rdi+118h], 0
0x18006dfe7  jnz     loc_18006E0AC
0x18006dfed  mov     rax, [rdi]
0x18006dff0  xor     edx, edx
0x18006dff2  mov     rcx, rdi
0x18006dff5  mov     rax, [rax]
0x18006dff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dffd  mov     rcx, rdi; this
0x18006e000  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x18006e005  xor     edi, edi
0x18006e007  mov     ebx, 8007000Eh
0x18006e00c  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18006e010  xor     r8d, r8d; int
0x18006e013  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006e01a  lea     rdx, aWdcmonitorCrea; "WdcMonitor::Create"
0x18006e021  lea     rcx, aBaseDiagnosisP_4; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x18006e028  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006e02d  mov     rcx, [rbp+57h+var_80]
0x18006e031  test    rcx, rcx
0x18006e034  jz      short loc_18006E044
0x18006e036  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18006e03c  mov     [rbp+57h+var_80], 0
0x18006e044  test    ebx, ebx
0x18006e046  jns     short loc_18006E058
0x18006e048  test    rdi, rdi
0x18006e04b  jz      short loc_18006E058
0x18006e04d  mov     dl, 1
0x18006e04f  mov     rcx, rdi
0x18006e052  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18006e058  test    cs:Microsoft_Windows_Diagnosis_WDCEnableBits, 8
0x18006e05f  jz      short loc_18006E083
0x18006e061  lea     rax, [rbp+57h+var_48]
0x18006e065  mov     r9d, 1
0x18006e06b  lea     rdx, Launch_Stop
0x18006e072  mov     [rsp+0E0h+var_C0], rax
0x18006e077  lea     rcx, WDC_PROVIDER_GUID_Context
0x18006e07e  call    McGenEventWrite_EventWriteTransfer
0x18006e083  mov     eax, ebx
0x18006e085  mov     rcx, [rbp+57h+var_38]
0x18006e089  xor     rcx, rsp; StackCookie
0x18006e08c  call    __security_check_cookie
0x18006e091  mov     rbx, [rsp+0E0h+arg_18]
0x18006e099  add     rsp, 0B0h
0x18006e0a0  pop     r15
0x18006e0a2  pop     r14
0x18006e0a4  pop     r13
0x18006e0a6  pop     r12
0x18006e0a8  pop     rdi
0x18006e0a9  pop     rsi
0x18006e0aa  pop     rbp
0x18006e0ab  retn
0x18006e0ac  lea     rax, [rbp+57h+var_68]
0x18006e0b0  mov     r9d, 80000000h
0x18006e0b6  mov     [rsp+0E0h+var_90], rax
0x18006e0bb  lea     rcx, aRpmWindow; "RPM_Window"
0x18006e0c2  mov     [rsp+0E0h+var_98], 2
0x18006e0ca  xor     r8d, r8d
0x18006e0cd  mov     [rsp+0E0h+var_A0], 40000000h
0x18006e0d5  mov     rdx, rsi
0x18006e0d8  mov     dword ptr [rsp+0E0h+var_A8], 0
0x18006e0e0  mov     dword ptr [rsp+0E0h+var_B0], 0
0x18006e0e8  mov     dword ptr [rsp+0E0h+var_B8], 0
0x18006e0f0  mov     dword ptr [rsp+0E0h+var_C0], r9d
0x18006e0f5  call    cs:__imp_?Create@NativeHWNDHost@DirectUI@@SAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHIPEAPEAV12@@Z; DirectUI::NativeHWNDHost::Create(ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,uint,DirectUI::NativeHWNDHost * *)
0x18006e0fb  mov     ebx, eax
0x18006e0fd  test    eax, eax
0x18006e0ff  js      loc_18006DF82
0x18006e105  mov     rcx, [rbp+57h+var_68]
0x18006e109  lea     r13, [rdi+120h]
0x18006e110  mov     cs:?g_MainWindow@@3PEAUHWND__@@EA, rsi; HWND__ * g_MainWindow
0x18006e117  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x18006e11d  mov     [r13+0], rax
0x18006e121  xor     r9d, r9d
0x18006e124  mov     [rbp+57h+var_78], 0
0x18006e12b  mov     r8b, 1
0x18006e12e  mov     rdx, [r13+0]
0x18006e132  lea     rax, [rbp+57h+var_78]
0x18006e136  mov     [rsp+0E0h+var_B8], rax
0x18006e13b  mov     rcx, rdi
0x18006e13e  mov     [rsp+0E0h+var_C0], 0
0x18006e147  call    cs:__imp_?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x18006e14d  xor     r8d, r8d
0x18006e150  mov     ebx, eax
0x18006e152  test    eax, eax
0x18006e154  jns     short loc_18006E15F
0x18006e156  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18006e15a  jmp     loc_18006E013
0x18006e15f  lea     r9, ?WdcPE@@YAXPEBG0HPEAX@Z; WdcPE(ushort const *,ushort const *,int,void *)
0x18006e166  mov     [rsp+0E0h+var_C0], 0
0x18006e16f  xor     edx, edx
0x18006e171  lea     rcx, [rbp+57h+var_80]
0x18006e175  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18006e17b  mov     ebx, eax
0x18006e17d  test    eax, eax
0x18006e17f  js      loc_18006DF82
0x18006e185  mov     r8, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006e18c  lea     r15, __ImageBase
0x18006e193  mov     rcx, [rbp+57h+var_80]
0x18006e197  mov     r9, r15
0x18006e19a  mov     edx, 7530h
0x18006e19f  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18006e1a5  mov     ebx, eax
0x18006e1a7  test    eax, eax
0x18006e1a9  js      loc_18006DF82
0x18006e1af  mov     rcx, [rbp+57h+var_80]
0x18006e1b3  lea     rax, [rbp+57h+var_70]
0x18006e1b7  mov     [rsp+0E0h+var_B8], rax
0x18006e1bc  lea     rdx, aResmon; "resmon"
0x18006e1c3  xor     r9d, r9d
0x18006e1c6  mov     [rsp+0E0h+var_C0], 0
0x18006e1cf  mov     r8, rdi
0x18006e1d2  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18006e1d8  mov     ebx, eax
0x18006e1da  test    eax, eax
0x18006e1dc  js      loc_18006DF82
0x18006e1e2  xor     ebx, ebx
0x18006e1e4  mov     r12, rdi
0x18006e1e7  xor     esi, esi
0x18006e1e9  lea     r14, [rsi+rsi*2]
0x18006e1ed  mov     rcx, rva off_1800AE6F8[r15+r14*8]; "overtab_graphs" ...
0x18006e1f5  call    cs:__imp_StrToID
0x18006e1fb  movzx   edx, ax
0x18006e1fe  mov     rcx, rdi
0x18006e201  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18006e207  mov     r15, rax
0x18006e20a  test    rax, rax
0x18006e20d  jz      loc_18006E399
0x18006e213  lea     ecx, [rbx-1]
0x18006e216  test    ecx, 0FFFFFFFCh
0x18006e21c  jnz     loc_18006E2BA
0x18006e222  cmp     ebx, 2
0x18006e225  jz      loc_18006E2BA
0x18006e22b  mov     ecx, 20h ; ' '; Size
0x18006e230  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e235  mov     rdx, [r13+0]
0x18006e239  mov     rcx, rax
0x18006e23c  call    cs:__imp_??0DUIFactory@DirectUI@@QEAA@PEAUHWND__@@@Z; DirectUI::DUIFactory::DUIFactory(HWND__ *)
0x18006e242  xor     edx, edx
0x18006e244  test    rax, rax
0x18006e247  jz      loc_18006E399
0x18006e24d  mov     [r12+rsi*8+128h], rax
0x18006e255  lea     r9, __ImageBase
0x18006e25c  mov     [rsp+0E0h+var_A8], rdx
0x18006e261  lea     r12, rva dword_1800AE6F4[r9]
0x18006e268  mov     r9, rva off_1800AE6F8[r9+r14*8]; "overtab_graphs" ...
0x18006e270  lea     rcx, [rbp+57h+var_70]
0x18006e274  mov     [rsp+0E0h+var_B0], rcx
0x18006e279  lea     r12, [r12+r14*8]
0x18006e27d  movzx   r8d, word ptr [r12]
0x18006e282  mov     rcx, rax
0x18006e285  mov     [rsp+0E0h+var_B8], rdx
0x18006e28a  mov     [rsp+0E0h+var_C0], rdx
0x18006e28f  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006e296  call    cs:__imp_?LoadFromResource@DUIFactory@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG1PEAVElement@2@PEAKPEAPEAV42@1@Z; DirectUI::DUIFactory::LoadFromResource(HINSTANCE__ *,ushort const *,ushort const *,DirectUI::Element *,ulong *,DirectUI::Element * *,ushort const *)
0x18006e29c  test    eax, eax
0x18006e29e  js      loc_18006E396
0x18006e2a4  mov     rdx, [rbp+57h+var_70]
0x18006e2a8  mov     rcx, r15
0x18006e2ab  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18006e2b1  lea     r15, __ImageBase
0x18006e2b8  jmp     short loc_18006E31A
0x18006e2ba  mov     r8, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006e2c1  lea     r9, __ImageBase
0x18006e2c8  mov     rcx, [rbp+57h+var_80]
0x18006e2cc  lea     r12, rva dword_1800AE6F4[r9]
0x18006e2d3  lea     r12, [r12+r14*8]
0x18006e2d7  mov     edx, [r12]
0x18006e2db  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18006e2e1  test    eax, eax
0x18006e2e3  js      loc_18006E396
0x18006e2e9  mov     rcx, [rbp+57h+var_80]
0x18006e2ed  lea     rax, [rbp+57h+var_70]
0x18006e2f1  mov     r8, r15
0x18006e2f4  mov     [rsp+0E0h+var_B8], rax
0x18006e2f9  lea     r15, __ImageBase
0x18006e300  mov     [rsp+0E0h+var_C0], 0
0x18006e309  mov     rdx, rva off_1800AE6F8[r15+r14*8]; "overtab_graphs" ...
0x18006e311  xor     r9d, r9d
0x18006e314  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18006e31a  test    eax, eax
0x18006e31c  js      short loc_18006E391
0x18006e31e  mov     rcx, rva off_1800AE700[r15+r14*8]; "overtab_tables" ...
0x18006e326  call    cs:__imp_StrToID
0x18006e32c  movzx   edx, ax
0x18006e32f  mov     rcx, rdi
0x18006e332  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18006e338  mov     r15, rax
0x18006e33b  test    rax, rax
0x18006e33e  jz      short loc_18006E396
0x18006e340  mov     r8, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006e347  lea     r9, __ImageBase
0x18006e34e  mov     edx, [r12]
0x18006e352  mov     rcx, [rbp+57h+var_80]
0x18006e356  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18006e35c  test    eax, eax
0x18006e35e  js      short loc_18006E396
0x18006e360  mov     rcx, [rbp+57h+var_80]
0x18006e364  lea     rax, [rbp+57h+var_70]
0x18006e368  mov     r8, r15
0x18006e36b  mov     [rsp+0E0h+var_B8], rax
0x18006e370  lea     r15, __ImageBase
0x18006e377  mov     [rsp+0E0h+var_C0], 0
0x18006e380  mov     rdx, rva off_1800AE700[r15+r14*8]; "overtab_tables" ...
0x18006e388  xor     r9d, r9d
0x18006e38b  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18006e391  mov     r12, rdi
0x18006e394  jmp     short loc_18006E3A0
0x18006e396  mov     r12, rdi
0x18006e399  lea     r15, __ImageBase
0x18006e3a0  inc     ebx
0x18006e3a2  inc     rsi
0x18006e3a5  cmp     ebx, 5
0x18006e3a8  jl      loc_18006E1E9
0x18006e3ae  mov     rcx, rdi; this
0x18006e3b1  call    ?Setup@WdcMonitor@@QEAAJXZ; WdcMonitor::Setup(void)
0x18006e3b6  mov     ebx, eax
0x18006e3b8  test    eax, eax
0x18006e3ba  js      loc_18006DF82
0x18006e3c0  mov     dl, 1
0x18006e3c2  mov     rcx, rdi
0x18006e3c5  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x18006e3cb  mov     edx, 9
0x18006e3d0  mov     rcx, rdi
0x18006e3d3  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x18006e3d9  mov     dl, 1
0x18006e3db  mov     rcx, rdi
0x18006e3de  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18006e3e4  mov     rcx, [rbp+57h+var_68]
0x18006e3e8  mov     rdx, rdi
0x18006e3eb  call    cs:__imp_?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z; DirectUI::NativeHWNDHost::Host(DirectUI::Element *)
0x18006e3f1  mov     edx, [rbp+57h+var_78]
0x18006e3f4  mov     rcx, rdi
0x18006e3f7  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18006e3fd  mov     rax, [rbp+57h+var_60]
0x18006e401  mov     rcx, [rbp+57h+var_48]
0x18006e405  mov     [rax], rdi
0x18006e408  mov     rax, [rbp+57h+var_68]
  ... truncated ...
```
