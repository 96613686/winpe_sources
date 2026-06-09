# CShareWithListItemDevice::_OnRemove(void)

- ea: `0x1800100ac`
- end: `0x18001058a`
- name: `?_OnRemove@CShareWithListItemDevice@@AEAAJXZ`
- size: `1246`
- prototype: `__int64 __fastcall(CShareWithListItemDevice *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bb90`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x1800043e4`
- `0x1800049c0`
- `0x180005468`
- `0x1800091dc`
- `0x1800100ac`
- `0x180012dd8`
- `0x1800165e8`
- `0x18001d290`
- `0x18001e010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180010239`
- `KERNEL32!FormatMessageW` at `0x1800102c9`
- `KERNEL32!FormatMessageW` at `0x1800102fb`
- `KERNEL32!FormatMessageW` at `0x180010239`
- `KERNEL32!FormatMessageW` at `0x1800102c9`
- `KERNEL32!FormatMessageW` at `0x1800102fb`
- `ole32!CoTaskMemFree` at `0x18001052d`
- `ole32!CoTaskMemFree` at `0x18001052d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010513`
- `OLEAUT32!__imp_SysFreeString` at `0x180010513`
- `USER32!SetCursor` at `0x180010434`
- `USER32!SetCursor` at `0x1800104f7`
- `USER32!SetCursor` at `0x180010434`
- `USER32!SetCursor` at `0x1800104f7`
- `USER32!LoadCursorW` at `0x18001042b`
- `USER32!LoadCursorW` at `0x18001042b`
- `USER32!LoadStringW` at `0x18001020a`
- `USER32!LoadStringW` at `0x18001027e`
- `USER32!LoadStringW` at `0x18001029a`
- `USER32!LoadStringW` at `0x18001020a`
- `USER32!LoadStringW` at `0x18001027e`
- `USER32!LoadStringW` at `0x18001029a`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001046c`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001046c`
- `DUI70!?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z` at `0x1800104ee`
- `DUI70!?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z` at `0x1800104ee`

## pseudocode

```c
__int64 __fastcall CShareWithListItemDevice::_OnRemove(CShareWithListItemDevice *this)
{
  CDeviceSettings *v2; // rcx
  HRESULT DeviceName; // ebx
  CDeviceSettings *v4; // rcx
  HWND v5; // rax
  CDeviceSettings *v6; // rcx
  struct INSSDevice *v7; // rsi
  const struct _GUID *v8; // rdx
  const struct _GUID *v9; // r8
  HWND v10; // rcx
  HCURSOR CursorW; // rax
  HCURSOR v12; // r15
  DirectUI::Element *v13; // rcx
  __int64 v14; // r14
  int pnButton; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  struct INSSDevice *v18; // [rsp+50h] [rbp-B0h] BYREF
  int pnRadioButton; // [rsp+58h] [rbp-A8h] BYREF
  va_list Arguments; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+74h] [rbp-8Ch]
  int v24; // [rsp+7Ch] [rbp-84h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[8]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v28; // [rsp+138h] [rbp+38h]
  int v29; // [rsp+150h] [rbp+50h]
  WCHAR Buffer[504]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR lpBuffer[504]; // [rsp+550h] [rbp+450h] BYREF
  WCHAR Source[504]; // [rsp+940h] [rbp+840h] BYREF
  WCHAR v33[504]; // [rsp+D30h] [rbp+C30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = (CDeviceSettings *)*((_QWORD *)this + 27);
  pv = 0;
  DeviceName = CDeviceSettings::GetDeviceName(v2, (unsigned __int16 **)&pv);
  if ( DeviceName >= 0 )
  {
    v4 = (CDeviceSettings *)*((_QWORD *)this + 27);
    Arguments = (va_list)pv;
    LODWORD(bstrString) = 0;
    CDeviceSettings::IsDeviceConnected(v4, (int *)&bstrString);
    memset_0(lpBuffer, 0, 0x3E8u);
    memset_0(v33, 0, 0x3E8u);
    memset_0(Buffer, 0, 0x3E8u);
    memset_0(Source, 0, 0x3E8u);
    memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
    v5 = (HWND)*((_QWORD *)this + 28);
    pTaskConfig.cbSize = 160;
    pTaskConfig.hInstance = g_hinst;
    pTaskConfig.hwndParent = v5;
    pTaskConfig.dwFlags = 4104;
    pTaskConfig.pszWindowTitle = (PCWSTR)26;
    pTaskConfig.hMainIcon = (HICON)0xFFFF;
    pTaskConfig.cxWidth = 250;
    pnRadioButton = 0;
    pnButton = 0;
    if ( (_DWORD)bstrString )
    {
      LoadStringW(g_hinst, 0x1Cu, Buffer, 500);
      FormatMessageW(0x2400u, Buffer, 0, 0, lpBuffer, 0x1F4u, &Arguments);
      pTaskConfig.nDefaultButton = 1;
      pTaskConfig.pszContent = lpBuffer;
      pTaskConfig.dwCommonButtons = 1;
      pTaskConfig.hMainIcon = (HICON)0xFFFF;
      DeviceName = TaskDialogIndirect(&pTaskConfig, &pnButton, &pnRadioButton, 0);
    }
    else
    {
      LoadStringW(g_hinst, 0x3Eu, Buffer, 500);
      LoadStringW(g_hinst, 0x1Bu, Source, 500);
      FormatMessageW(0x2400u, Buffer, 0, 0, v33, 0x1F4u, &Arguments);
      FormatMessageW(0x2400u, Source, 0, 0, lpBuffer, 0x1F4u, &Arguments);
      pTaskConfig.dwFlags |= 0x10u;
      pTaskConfig.pszMainInstruction = v33;
      v23 = 106;
      v22 = 403;
      pTaskConfig.pszContent = lpBuffer;
      v24 = 404;
      pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v22;
      v25 = 109;
      pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)ElevationTaskDialogCallback;
      pTaskConfig.nDefaultButton = 403;
      pTaskConfig.dwCommonButtons = 8;
      pTaskConfig.cButtons = 2;
      pTaskConfig.lpCallbackData = 403;
      DeviceName = TaskDialogIndirect(&pTaskConfig, &pnButton, &pnRadioButton, 0);
      if ( DeviceName >= 0 && pnButton == 403 )
      {
        v6 = (CDeviceSettings *)*((_QWORD *)this + 27);
        v18 = 0;
        DeviceName = CDeviceSettings::GetDevice(v6, &v18);
        if ( DeviceName >= 0 )
        {
          v7 = v18;
          bstrString = 0;
          DeviceName = (*(__int64 (__fastcall **)(struct INSSDevice *, BSTR *))(*(_QWORD *)v18 + 56LL))(
                         v18,
                         &bstrString);
          if ( DeviceName >= 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                258,
                &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
                bstrString);
            v10 = (HWND)*((_QWORD *)this + 28);
            v18 = 0;
            DeviceName = CoCreateInstanceAsAdmin(v10, v8, v9, (void **)&v18);
            if ( DeviceName >= 0 )
            {
              CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
              v12 = SetCursor(CursorW);
              DeviceName = (*(__int64 (__fastcall **)(struct INSSDevice *, BSTR))(*(_QWORD *)v18 + 40LL))(
                             v18,
                             bstrString);
              if ( DeviceName >= 0 )
              {
                v13 = (DirectUI::Element *)*((_QWORD *)this + 10);
                if ( v13 )
                {
                  DirectUI::Element::Remove(v13, this);
                  v14 = *((_QWORD *)this + 27);
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
                  }
                  *(_DWORD *)(v14 + 84) = 1;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
                  }
                }
                v28 = CShareMediaPage::AuthorizationChange;
                v29 = 3;
                DirectUI::Element::FireEvent(this, (struct DirectUI::Event *)v27, 1, 0);
              }
              SetCursor(v12);
              (*(void (__fastcall **)(struct INSSDevice *))(*(_QWORD *)v18 + 16LL))(v18);
            }
            SysFreeString(bstrString);
          }
          (*(void (__fastcall **)(struct INSSDevice *))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
    }
    CoTaskMemFree(pv);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      259,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)DeviceName);
  return (unsigned int)DeviceName;
}

```

## disassembly

```asm
0x1800100ac  mov     [rsp-8+arg_8], rbx
0x1800100b1  mov     [rsp-8+arg_10], rsi
0x1800100b6  push    rbp
0x1800100b7  push    rdi
0x1800100b8  push    r12
0x1800100ba  push    r14
0x1800100bc  push    r15
0x1800100be  lea     rbp, [rsp-1030h]
0x1800100c6  mov     eax, 1130h
0x1800100cb  call    _alloca_probe
0x1800100d0  sub     rsp, rax
0x1800100d3  mov     rax, cs:__security_cookie
0x1800100da  xor     rax, rsp
0x1800100dd  mov     [rbp+1050h+var_30], rax
0x1800100e4  mov     rdi, rcx
0x1800100e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100ee  lea     r12, WPP_GLOBAL_Control
0x1800100f5  cmp     rcx, r12
0x1800100f8  jz      short loc_180010115
0x1800100fa  test    byte ptr [rcx+1Ch], 20h
0x1800100fe  jz      short loc_180010115
0x180010100  mov     rcx, [rcx+10h]
0x180010104  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18001010b  mov     edx, 101h
0x180010110  call    WPP_SF_
0x180010115  mov     rcx, [rdi+0D8h]; this
0x18001011c  lea     rdx, [rsp+1150h+pv]; unsigned __int16 **
0x180010121  xor     r14d, r14d
0x180010124  mov     [rsp+1150h+pv], r14
0x180010129  call    ?GetDeviceName@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetDeviceName(ushort * *)
0x18001012e  mov     ebx, eax
0x180010130  test    eax, eax
0x180010132  js      loc_180010533
0x180010138  mov     rax, [rsp+1150h+pv]
0x18001013d  lea     rdx, [rsp+1150h+bstrString]; int *
0x180010142  mov     rcx, [rdi+0D8h]; this
0x180010149  mov     [rsp+1150h+var_10F0], rax
0x18001014e  mov     dword ptr [rsp+1150h+bstrString], r14d
0x180010153  call    ?IsDeviceConnected@CDeviceSettings@@QEAAJPEAH@Z; CDeviceSettings::IsDeviceConnected(int *)
0x180010158  mov     ebx, 3E8h
0x18001015d  lea     rcx, [rbp+1050h+var_C00]; void *
0x180010164  mov     r8d, ebx; Size
0x180010167  xor     edx, edx; Val
0x180010169  call    memset_0
0x18001016e  mov     r8d, ebx; Size
0x180010171  lea     rcx, [rbp+1050h+var_420]; void *
0x180010178  xor     edx, edx; Val
0x18001017a  call    memset_0
0x18001017f  mov     r8d, ebx; Size
0x180010182  lea     rcx, [rbp+1050h+Buffer]; void *
0x180010186  xor     edx, edx; Val
0x180010188  call    memset_0
0x18001018d  mov     r8d, ebx; Size
0x180010190  lea     rcx, [rbp+1050h+Source]; void *
0x180010197  xor     edx, edx; Val
0x180010199  call    memset_0
0x18001019e  mov     ebx, 0A0h
0x1800101a3  lea     rcx, [rbp+1050h+pTaskConfig]; void *
0x1800101a7  mov     r8d, ebx; Size
0x1800101aa  xor     edx, edx; Val
0x1800101ac  call    memset_0
0x1800101b1  lea     r8, [rbp+1050h+Buffer]; lpBuffer
0x1800101b5  mov     rcx, cs:g_hinst; hInstance
0x1800101bc  mov     esi, 0FFFFh
0x1800101c1  mov     rax, [rdi+0E0h]
0x1800101c8  mov     [rbp+1050h+pTaskConfig.cbSize], ebx
0x1800101cb  mov     ebx, 1F4h
0x1800101d0  mov     r9d, ebx; cchBufferMax
0x1800101d3  mov     [rbp+1050h+pTaskConfig.hInstance], rcx
0x1800101d7  mov     [rbp+1050h+pTaskConfig.hwndParent], rax
0x1800101db  mov     [rbp+1050h+pTaskConfig.dwFlags], 1008h
0x1800101e2  mov     [rbp+1050h+pTaskConfig.pszWindowTitle], 1Ah
0x1800101ea  mov     qword ptr [rbp+1050h+pTaskConfig.24h], rsi
0x1800101ee  mov     [rbp+1050h+pTaskConfig.cxWidth], 0FAh
0x1800101f5  mov     [rsp+1150h+pnRadioButton], r14d
0x1800101fa  mov     [rsp+1150h+pnButton], r14d
0x1800101ff  cmp     dword ptr [rsp+1150h+bstrString], r14d
0x180010204  jz      short loc_180010279
0x180010206  lea     edx, [r14+1Ch]; uID
0x18001020a  call    cs:__imp_LoadStringW
0x180010210  lea     rax, [rsp+1150h+var_10F0]
0x180010215  xor     r9d, r9d; dwLanguageId
0x180010218  mov     [rsp+1150h+Arguments], rax; Arguments
0x18001021d  lea     rdx, [rbp+1050h+Buffer]; lpSource
0x180010221  lea     rax, [rbp+1050h+var_C00]
0x180010228  mov     [rsp+1150h+nSize], ebx; nSize
0x18001022c  xor     r8d, r8d; dwMessageId
0x18001022f  mov     [rsp+1150h+lpBuffer], rax; lpBuffer
0x180010234  mov     ecx, 2400h; dwFlags
0x180010239  call    cs:__imp_FormatMessageW
0x18001023f  lea     rax, [rbp+1050h+var_C00]
0x180010246  mov     [rbp+1050h+pTaskConfig.nDefaultButton], 1
0x18001024d  xor     r9d, r9d; pfVerificationFlagChecked
0x180010250  mov     [rbp+1050h+pTaskConfig.pszContent], rax
0x180010254  lea     r8, [rsp+1150h+pnRadioButton]; pnRadioButton
0x180010259  mov     [rbp+1050h+pTaskConfig.dwCommonButtons], 1
0x180010260  lea     rdx, [rsp+1150h+pnButton]; pnButton
0x180010265  mov     qword ptr [rbp+1050h+pTaskConfig.24h], rsi
0x180010269  lea     rcx, [rbp+1050h+pTaskConfig]; pTaskConfig
0x18001026d  call    TaskDialogIndirect
0x180010272  mov     ebx, eax
0x180010274  jmp     loc_180010528
0x180010279  mov     edx, 3Eh ; '>'; uID
0x18001027e  call    cs:__imp_LoadStringW
0x180010284  mov     rcx, cs:g_hinst; hInstance
0x18001028b  lea     r8, [rbp+1050h+Source]; lpBuffer
0x180010292  mov     r9d, ebx; cchBufferMax
0x180010295  mov     edx, 1Bh; uID
0x18001029a  call    cs:__imp_LoadStringW
0x1800102a0  lea     rax, [rsp+1150h+var_10F0]
0x1800102a5  xor     r9d, r9d; dwLanguageId
0x1800102a8  mov     [rsp+1150h+Arguments], rax; Arguments
0x1800102ad  lea     rdx, [rbp+1050h+Buffer]; lpSource
0x1800102b1  lea     rax, [rbp+1050h+var_420]
0x1800102b8  mov     [rsp+1150h+nSize], ebx; nSize
0x1800102bc  xor     r8d, r8d; dwMessageId
0x1800102bf  mov     [rsp+1150h+lpBuffer], rax; lpBuffer
0x1800102c4  mov     ecx, 2400h; dwFlags
0x1800102c9  call    cs:__imp_FormatMessageW
0x1800102cf  lea     rax, [rsp+1150h+var_10F0]
0x1800102d4  xor     r9d, r9d; dwLanguageId
0x1800102d7  mov     [rsp+1150h+Arguments], rax; Arguments
0x1800102dc  lea     rdx, [rbp+1050h+Source]; lpSource
0x1800102e3  lea     rax, [rbp+1050h+var_C00]
0x1800102ea  mov     [rsp+1150h+nSize], ebx; nSize
0x1800102ee  xor     r8d, r8d; dwMessageId
0x1800102f1  mov     [rsp+1150h+lpBuffer], rax; lpBuffer
0x1800102f6  mov     ecx, 2400h; dwFlags
0x1800102fb  call    cs:__imp_FormatMessageW
0x180010301  or      [rbp+1050h+pTaskConfig.dwFlags], 10h
0x180010305  lea     rax, [rbp+1050h+var_420]
0x18001030c  mov     [rbp+1050h+pTaskConfig.pszMainInstruction], rax
0x180010310  lea     r8, [rsp+1150h+pnRadioButton]; pnRadioButton
0x180010315  mov     esi, 193h
0x18001031a  mov     [rsp+1150h+var_10DC], 6Ah ; 'j'
0x180010323  lea     rax, [rbp+1050h+var_C00]
0x18001032a  mov     [rsp+1150h+var_10E0], esi
0x18001032e  mov     [rbp+1050h+pTaskConfig.pszContent], rax
0x180010332  lea     rdx, [rsp+1150h+pnButton]; pnButton
0x180010337  lea     rax, [rsp+1150h+var_10E0]
0x18001033c  mov     [rsp+1150h+var_10D4], 194h
0x180010344  mov     [rbp+1050h+pTaskConfig.pButtons], rax
0x180010348  lea     rcx, [rbp+1050h+pTaskConfig]; pTaskConfig
0x18001034c  lea     rax, ?ElevationTaskDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z; ElevationTaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180010353  mov     [rbp+1050h+var_10D0], 6Dh ; 'm'
0x18001035b  xor     r9d, r9d; pfVerificationFlagChecked
0x18001035e  mov     [rbp+1050h+pTaskConfig.pfCallback], rax
0x180010362  mov     [rbp+1050h+pTaskConfig.nDefaultButton], esi
0x180010365  mov     [rbp+1050h+pTaskConfig.dwCommonButtons], 8
0x18001036c  mov     [rbp+1050h+pTaskConfig.cButtons], 2
0x180010373  mov     [rbp+1050h+pTaskConfig.lpCallbackData], rsi
0x180010377  call    TaskDialogIndirect
0x18001037c  mov     ebx, eax
0x18001037e  test    eax, eax
0x180010380  js      loc_180010528
0x180010386  cmp     [rsp+1150h+pnButton], esi
0x18001038a  jnz     loc_180010528
0x180010390  mov     rcx, [rdi+0D8h]; this
0x180010397  lea     rdx, [rsp+1150h+var_1100]; struct INSSDevice **
0x18001039c  mov     [rsp+1150h+var_1100], r14
0x1800103a1  call    ?GetDevice@CDeviceSettings@@QEAAJPEAPEAUINSSDevice@@@Z; CDeviceSettings::GetDevice(INSSDevice * *)
0x1800103a6  mov     ebx, eax
0x1800103a8  test    eax, eax
0x1800103aa  js      loc_180010528
0x1800103b0  mov     rsi, [rsp+1150h+var_1100]
0x1800103b5  lea     rdx, [rsp+1150h+bstrString]
0x1800103ba  mov     [rsp+1150h+bstrString], r14
0x1800103bf  mov     rcx, rsi
0x1800103c2  mov     rax, [rsi]
0x1800103c5  mov     rax, [rax+38h]
0x1800103c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ce  mov     ebx, eax
0x1800103d0  test    eax, eax
0x1800103d2  js      loc_180010519
0x1800103d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103df  cmp     rcx, r12
0x1800103e2  jz      short loc_180010404
0x1800103e4  test    byte ptr [rcx+1Ch], 8
0x1800103e8  jz      short loc_180010404
0x1800103ea  mov     r9, [rsp+1150h+bstrString]
0x1800103ef  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800103f6  mov     rcx, [rcx+10h]
0x1800103fa  mov     edx, 102h
0x1800103ff  call    WPP_SF_S
0x180010404  mov     rcx, [rdi+0E0h]; HWND
0x18001040b  lea     r9, [rsp+1150h+var_1100]; void **
0x180010410  mov     [rsp+1150h+var_1100], r14
0x180010415  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18001041a  mov     ebx, eax
0x18001041c  test    eax, eax
0x18001041e  js      loc_18001050E
0x180010424  mov     edx, 7F02h; lpCursorName
0x180010429  xor     ecx, ecx; hInstance
0x18001042b  call    cs:__imp_LoadCursorW
0x180010431  mov     rcx, rax; hCursor
0x180010434  call    cs:__imp_SetCursor
0x18001043a  mov     r8, [rsp+1150h+var_1100]
0x18001043f  mov     r15, rax
0x180010442  mov     rdx, [rsp+1150h+bstrString]
0x180010447  mov     rcx, [r8]
0x18001044a  mov     rax, [rcx+28h]
0x18001044e  mov     rcx, r8
0x180010451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010456  mov     ebx, eax
0x180010458  test    eax, eax
0x18001045a  js      loc_1800104F4
0x180010460  mov     rcx, [rdi+50h]
0x180010464  test    rcx, rcx
0x180010467  jz      short loc_1800104CF
0x180010469  mov     rdx, rdi
0x18001046c  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x180010472  mov     r14, [rdi+0D8h]
0x180010479  mov     rcx, cs:WPP_GLOBAL_Control
0x180010480  cmp     rcx, r12
0x180010483  jz      short loc_1800104A0
0x180010485  test    byte ptr [rcx+1Ch], 20h
0x180010489  jz      short loc_1800104A0
0x18001048b  mov     rcx, [rcx+10h]
0x18001048f  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x180010496  mov     edx, 22h ; '"'
0x18001049b  call    WPP_SF_
0x1800104a0  mov     dword ptr [r14+54h], 1
0x1800104a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104af  cmp     rcx, r12
0x1800104b2  jz      short loc_1800104CF
0x1800104b4  test    byte ptr [rcx+1Ch], 20h
0x1800104b8  jz      short loc_1800104CF
0x1800104ba  mov     rcx, [rcx+10h]
0x1800104be  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x1800104c5  mov     edx, 23h ; '#'
0x1800104ca  call    WPP_SF_
0x1800104cf  mov     rax, cs:?AuthorizationChange@CShareMediaPage@@2VUID@@A; UID CShareMediaPage::AuthorizationChange
0x1800104d6  lea     rdx, [rbp+1050h+var_1020]
0x1800104da  xor     r9d, r9d
0x1800104dd  mov     [rbp+1050h+var_1018], rax
0x1800104e1  mov     r8b, 1
0x1800104e4  mov     [rbp+1050h+var_1000], 3
0x1800104eb  mov     rcx, rdi
0x1800104ee  call    cs:__imp_?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z; DirectUI::Element::FireEvent(DirectUI::Event *,bool,bool)
0x1800104f4  mov     rcx, r15; hCursor
0x1800104f7  call    cs:__imp_SetCursor
0x1800104fd  mov     rcx, [rsp+1150h+var_1100]
0x180010502  mov     rax, [rcx]
0x180010505  mov     rax, [rax+10h]
0x180010509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001050e  mov     rcx, [rsp+1150h+bstrString]; bstrString
0x180010513  call    cs:__imp_SysFreeString
0x180010519  mov     rax, [rsi]
0x18001051c  mov     rcx, rsi
0x18001051f  mov     rax, [rax+10h]
0x180010523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010528  mov     rcx, [rsp+1150h+pv]; pv
0x18001052d  call    cs:__imp_CoTaskMemFree
0x180010533  mov     rcx, cs:WPP_GLOBAL_Control
0x18001053a  cmp     rcx, r12
0x18001053d  jz      short loc_18001055D
0x18001053f  test    byte ptr [rcx+1Ch], 20h
0x180010543  jz      short loc_18001055D
0x180010545  mov     rcx, [rcx+10h]
0x180010549  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180010550  mov     edx, 103h
0x180010555  mov     r9d, ebx
0x180010558  call    WPP_SF_d
0x18001055d  mov     eax, ebx
0x18001055f  mov     rcx, [rbp+1050h+var_30]
0x180010566  xor     rcx, rsp; StackCookie
0x180010569  call    __security_check_cookie
0x18001056e  lea     r11, [rsp+1150h+var_20]
0x180010576  mov     rbx, [r11+38h]
0x18001057a  mov     rsi, [r11+40h]
0x18001057e  mov     rsp, r11
0x180010581  pop     r15
0x180010583  pop     r14
0x180010585  pop     r12
0x180010587  pop     rdi
0x180010588  pop     rbp
0x180010589  retn
```
