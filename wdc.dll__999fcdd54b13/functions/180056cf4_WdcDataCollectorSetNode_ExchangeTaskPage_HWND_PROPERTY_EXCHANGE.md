# WdcDataCollectorSetNode::ExchangeTaskPage(HWND__ *,PROPERTY_EXCHANGE)

- ea: `0x180056cf4`
- end: `0x180056f80`
- name: `?ExchangeTaskPage@WdcDataCollectorSetNode@@AEAAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@@Z`
- size: `652`
- prototype: `__int64 __fastcall(__int64, HWND, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180058830`
- `0x180058d60`
- `0x180058f10`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18004c568`
- `0x180056cf4`
- `0x1800571b4`
- `0x18006a034`
- `0x180086010`

## import_xrefs

- `USER32!EnableWindow` at `0x180056eb0`
- `USER32!EnableWindow` at `0x180056eb0`
- `USER32!SetWindowTextW` at `0x180056f25`
- `USER32!SetWindowTextW` at `0x180056f25`
- `USER32!GetDlgItem` at `0x180056ea5`
- `USER32!GetDlgItem` at `0x180056f19`
- `USER32!GetDlgItem` at `0x180056ea5`
- `USER32!GetDlgItem` at `0x180056f19`
- `OLEAUT32!__imp_SysFreeString` at `0x180056f4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180056f4b`
- `OLEAUT32!__imp_VariantInit` at `0x180056d2b`
- `OLEAUT32!__imp_VariantInit` at `0x180056d2b`
- `OLEAUT32!__imp_VariantClear` at `0x180056f2f`
- `OLEAUT32!__imp_VariantClear` at `0x180056f2f`
- `PLA!PlaExpandTaskArguments` at `0x180056efd`
- `PLA!PlaExpandTaskArguments` at `0x180056efd`

## string_xrefs

- `0x180056d58`: `WdcDataCollectorSetNode::ExchangeTaskPage`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetNode::ExchangeTaskPage(__int64 a1, HWND a2, int a3)
{
  HRESULT DataSet; // eax
  const char *v7; // rdx
  int v8; // r8d
  int v9; // edi
  WCHAR *v10; // rsi
  WCHAR *lpString; // rax
  HWND DlgItem; // rax
  const WCHAR *v13; // rbx
  HWND v14; // rax
  const char *v15; // rdx
  int v16; // r8d
  __int64 v18; // [rsp+20h] [rbp-49h]
  BSTR args; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-11h] BYREF
  VARIANT vDataSet; // [rsp+70h] [rbp+7h] BYREF
  struct IDataCollectorSet *v22; // [rsp+E8h] [rbp+7Fh] BYREF

  args = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v22 = 0;
  VariantInit(&pvarg);
  DataSet = WdcDataCollectorSetNode::GetDataSet((WdcDataCollectorSetNode *)a1, 1, &v22);
  v9 = DataSet;
  if ( DataSet < 0 )
  {
    v10 = 0;
LABEL_3:
    LODWORD(v18) = DataSet;
LABEL_4:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
      "WdcDataCollectorSetNode::ExchangeTaskPage",
      0,
      L"FAILURE: 0x%08x",
      v18);
    goto LABEL_19;
  }
  lpString = (WCHAR *)WdcAlloc(0x800u, v7, v8);
  v10 = lpString;
  if ( !lpString )
  {
    v9 = -2147024882;
    LODWORD(v18) = -2147024882;
    goto LABEL_4;
  }
  *lpString = 0;
  v9 = WdcExchangePropertyString<IAlertDataCollector>(
         a2,
         (__int64) IConfigurationDataCollector::`vcall'{320,{flat}},
         (__int64) IDataCollectorSet::`vcall'{328,{flat}},
         *(WdcValidation **)(a1 + 528),
         lpString);
  if ( v9 >= 0 )
  {
    v9 = WdcExchangePropertyString<IAlertDataCollector>(
           a2,
           (__int64) IConfigurationDataCollector::`vcall'{352,{flat}},
           (__int64) IDataCollectorSet::`vcall'{360,{flat}},
           *(WdcValidation **)(a1 + 528),
           v10);
    if ( v9 >= 0 )
    {
      v9 = WdcExchangePropertyString<IAlertDataCollector>(
             a2,
             (__int64) IAlertDataCollector::`vcall'{368,{flat}},
             (__int64) IDataCollectorSet::`vcall'{376,{flat}},
             *(WdcValidation **)(a1 + 528),
             v10);
      if ( v9 >= 0 )
      {
        if ( a3 == 1 && (unsigned int)WdcValidation::Ignore(*(WdcValidation **)(a1 + 528), 0x836u) )
        {
          DlgItem = GetDlgItem(a2, 2103);
          EnableWindow(DlgItem, 0);
        }
        DataSet = ((__int64 (__fastcall *)(struct IDataCollectorSet *, GUID *, ULONG *))v22->lpVtbl->QueryInterface)(
                    v22,
                    &IID_IDispatch,
                    &pvarg.decVal.Lo32);
        v9 = DataSet;
        if ( DataSet < 0 )
          goto LABEL_3;
        pvarg.vt = 9;
        vDataSet = pvarg;
        DataSet = PlaExpandTaskArguments(&vDataSet, &args);
        v9 = DataSet;
        if ( DataSet < 0 )
          goto LABEL_3;
        v13 = args;
        v14 = GetDlgItem(a2, 2105);
        SetWindowTextW(v14, v13);
      }
      else
      {
        *(_DWORD *)(a1 + 40) = 2104;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 40) = 2102;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 40) = 2101;
  }
LABEL_19:
  VariantClear(&pvarg);
  if ( v10 )
    WdcFree(v10, v15, v16);
  if ( args )
  {
    SysFreeString(args);
    args = 0;
  }
  if ( v22 )
    ((void (__fastcall *)(struct IDataCollectorSet *))v22->lpVtbl->Release)(v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180056cf4  push    rbp
0x180056cf6  push    rbx
0x180056cf7  push    rsi
0x180056cf8  push    rdi
0x180056cf9  push    r14
0x180056cfb  push    r15
0x180056cfd  lea     rbp, [rsp-2Fh]
0x180056d02  sub     rsp, 98h
0x180056d09  xor     eax, eax
0x180056d0b  mov     rbx, rcx
0x180056d0e  xorps   xmm0, xmm0
0x180056d11  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180056d15  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180056d19  mov     [rbp+57h+args], rax
0x180056d1d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180056d21  mov     [rbp+57h+arg_18], rax
0x180056d25  mov     r15d, r8d
0x180056d28  mov     r14, rdx
0x180056d2b  call    cs:__imp_VariantInit
0x180056d31  lea     r8, [rbp+57h+arg_18]; struct IDataCollectorSet **
0x180056d35  mov     edx, 1; int
0x180056d3a  mov     rcx, rbx; this
0x180056d3d  call    ?GetDataSet@WdcDataCollectorSetNode@@IEAAJHPEAPEAUIDataCollectorSet@@@Z; WdcDataCollectorSetNode::GetDataSet(int,IDataCollectorSet * *)
0x180056d42  mov     edi, eax
0x180056d44  test    eax, eax
0x180056d46  jns     short loc_180056D70
0x180056d48  xor     esi, esi
0x180056d4a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180056d4e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180056d55  xor     r8d, r8d; int
0x180056d58  lea     rdx, aWdcdatacollect_58; "WdcDataCollectorSetNode::ExchangeTaskPa"...
0x180056d5f  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180056d66  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180056d6b  jmp     loc_180056F2B
0x180056d70  mov     ecx, 800h; dwBytes
0x180056d75  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180056d7a  mov     rsi, rax
0x180056d7d  test    rax, rax
0x180056d80  jnz     short loc_180056D8D
0x180056d82  mov     edi, 8007000Eh
0x180056d87  mov     dword ptr [rsp+0C0h+var_A0], edi
0x180056d8b  jmp     short loc_180056D4E
0x180056d8d  xor     eax, eax
0x180056d8f  mov     [rsp+0C0h+lpString], rsi; lpString
0x180056d94  mov     [rsi], ax
0x180056d97  mov     r8d, 835h
0x180056d9d  mov     rax, [rbx+210h]
0x180056da4  mov     edx, r15d
0x180056da7  mov     r9, [rbp+57h+arg_18]
0x180056dab  mov     rcx, r14; HWND
0x180056dae  mov     [rsp+0C0h+var_90], rax; WdcValidation *
0x180056db3  lea     rax, ??_9IDataCollectorSet@@$BBEI@AA; [thunk]: IDataCollectorSet::`vcall'{328,{flat}}
0x180056dba  mov     [rsp+0C0h+var_98], rax; __int64
0x180056dbf  lea     rax, ??_9IConfigurationDataCollector@@$BBEA@AA; [thunk]: IConfigurationDataCollector::`vcall'{320,{flat}}
0x180056dc6  mov     [rsp+0C0h+var_A0], rax; __int64
0x180056dcb  call    ??$WdcExchangePropertyString@UIAlertDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIAlertDataCollector@@P82@EAAJPEAPEAG@ZP82@EAAJPEAG@ZPEAVWdcValidation@@5K@Z; WdcExchangePropertyString<IAlertDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IAlertDataCollector *,long (IAlertDataCollector::*)(ushort * *),long (IAlertDataCollector::*)(ushort *),WdcValidation *,ushort *,ulong)
0x180056dd0  mov     edi, eax
0x180056dd2  test    eax, eax
0x180056dd4  jns     short loc_180056DE2
0x180056dd6  mov     dword ptr [rbx+28h], 835h
0x180056ddd  jmp     loc_180056F2B
0x180056de2  mov     rax, [rbx+210h]
0x180056de9  mov     r8d, 836h
0x180056def  mov     r9, [rbp+57h+arg_18]
0x180056df3  mov     edx, r15d
0x180056df6  mov     [rsp+0C0h+lpString], rsi; lpString
0x180056dfb  mov     rcx, r14; HWND
0x180056dfe  mov     [rsp+0C0h+var_90], rax; WdcValidation *
0x180056e03  lea     rax, ??_9IDataCollectorSet@@$BBGI@AA; [thunk]: IDataCollectorSet::`vcall'{360,{flat}}
0x180056e0a  mov     [rsp+0C0h+var_98], rax; __int64
0x180056e0f  lea     rax, ??_9IConfigurationDataCollector@@$BBGA@AA; [thunk]: IConfigurationDataCollector::`vcall'{352,{flat}}
0x180056e16  mov     [rsp+0C0h+var_A0], rax; __int64
0x180056e1b  call    ??$WdcExchangePropertyString@UIAlertDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIAlertDataCollector@@P82@EAAJPEAPEAG@ZP82@EAAJPEAG@ZPEAVWdcValidation@@5K@Z; WdcExchangePropertyString<IAlertDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IAlertDataCollector *,long (IAlertDataCollector::*)(ushort * *),long (IAlertDataCollector::*)(ushort *),WdcValidation *,ushort *,ulong)
0x180056e20  mov     edi, eax
0x180056e22  test    eax, eax
0x180056e24  jns     short loc_180056E32
0x180056e26  mov     dword ptr [rbx+28h], 836h
0x180056e2d  jmp     loc_180056F2B
0x180056e32  mov     rax, [rbx+210h]
0x180056e39  mov     r8d, 838h
0x180056e3f  mov     r9, [rbp+57h+arg_18]
0x180056e43  mov     edx, r15d
0x180056e46  mov     [rsp+0C0h+lpString], rsi; lpString
0x180056e4b  mov     rcx, r14; HWND
0x180056e4e  mov     [rsp+0C0h+var_90], rax; WdcValidation *
0x180056e53  lea     rax, ??_9IDataCollectorSet@@$BBHI@AA; [thunk]: IDataCollectorSet::`vcall'{376,{flat}}
0x180056e5a  mov     [rsp+0C0h+var_98], rax; __int64
0x180056e5f  lea     rax, ??_9IAlertDataCollector@@$BBHA@AA; [thunk]: IAlertDataCollector::`vcall'{368,{flat}}
0x180056e66  mov     [rsp+0C0h+var_A0], rax; __int64
0x180056e6b  call    ??$WdcExchangePropertyString@UIAlertDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIAlertDataCollector@@P82@EAAJPEAPEAG@ZP82@EAAJPEAG@ZPEAVWdcValidation@@5K@Z; WdcExchangePropertyString<IAlertDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IAlertDataCollector *,long (IAlertDataCollector::*)(ushort * *),long (IAlertDataCollector::*)(ushort *),WdcValidation *,ushort *,ulong)
0x180056e70  mov     edi, eax
0x180056e72  test    eax, eax
0x180056e74  jns     short loc_180056E82
0x180056e76  mov     dword ptr [rbx+28h], 838h
0x180056e7d  jmp     loc_180056F2B
0x180056e82  cmp     r15d, 1
0x180056e86  jnz     short loc_180056EB6
0x180056e88  mov     rcx, [rbx+210h]; this
0x180056e8f  mov     edx, 836h; unsigned int
0x180056e94  call    ?Ignore@WdcValidation@@QEAAHI@Z; WdcValidation::Ignore(uint)
0x180056e99  test    eax, eax
0x180056e9b  jz      short loc_180056EB6
0x180056e9d  mov     edx, 837h; nIDDlgItem
0x180056ea2  mov     rcx, r14; hDlg
0x180056ea5  call    cs:__imp_GetDlgItem
0x180056eab  mov     rcx, rax; hWnd
0x180056eae  xor     edx, edx; bEnable
0x180056eb0  call    cs:__imp_EnableWindow
0x180056eb6  mov     rcx, [rbp+57h+arg_18]
0x180056eba  lea     r8, [rbp+57h+pvarg+8]
0x180056ebe  lea     rdx, IID_IDispatch
0x180056ec5  mov     rax, [rcx]
0x180056ec8  mov     rax, [rax]
0x180056ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ed0  mov     edi, eax
0x180056ed2  test    eax, eax
0x180056ed4  js      loc_180056D4A
0x180056eda  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180056edf  lea     rdx, [rbp+57h+args]; args
0x180056ee3  mov     eax, 9
0x180056ee8  movsd   qword ptr [rbp+57h+vDataSet+10h], xmm1
0x180056eed  mov     word ptr [rbp+57h+pvarg], ax
0x180056ef1  lea     rcx, [rbp+57h+vDataSet]; vDataSet
0x180056ef5  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180056ef9  movaps  xmmword ptr [rbp+57h+vDataSet], xmm0
0x180056efd  call    cs:__imp_PlaExpandTaskArguments
0x180056f03  mov     edi, eax
0x180056f05  test    eax, eax
0x180056f07  js      loc_180056D4A
0x180056f0d  mov     rbx, [rbp+57h+args]
0x180056f11  mov     edx, 839h; nIDDlgItem
0x180056f16  mov     rcx, r14; hDlg
0x180056f19  call    cs:__imp_GetDlgItem
0x180056f1f  mov     rcx, rax; hWnd
0x180056f22  mov     rdx, rbx; lpString
0x180056f25  call    cs:__imp_SetWindowTextW
0x180056f2b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180056f2f  call    cs:__imp_VariantClear
0x180056f35  test    rsi, rsi
0x180056f38  jz      short loc_180056F42
0x180056f3a  mov     rcx, rsi; void *
0x180056f3d  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180056f42  mov     rcx, [rbp+57h+args]; bstrString
0x180056f46  test    rcx, rcx
0x180056f49  jz      short loc_180056F59
0x180056f4b  call    cs:__imp_SysFreeString
0x180056f51  mov     [rbp+57h+args], 0
0x180056f59  mov     rcx, [rbp+57h+arg_18]
0x180056f5d  test    rcx, rcx
0x180056f60  jz      short loc_180056F6E
0x180056f62  mov     rax, [rcx]
0x180056f65  mov     rax, [rax+10h]
0x180056f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f6e  mov     eax, edi
0x180056f70  add     rsp, 98h
0x180056f77  pop     r15
0x180056f79  pop     r14
0x180056f7b  pop     rdi
0x180056f7c  pop     rsi
0x180056f7d  pop     rbx
0x180056f7e  pop     rbp
0x180056f7f  retn
```
