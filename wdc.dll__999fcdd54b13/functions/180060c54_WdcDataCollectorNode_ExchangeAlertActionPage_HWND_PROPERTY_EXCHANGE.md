# WdcDataCollectorNode::ExchangeAlertActionPage(HWND__ *,PROPERTY_EXCHANGE)

- ea: `0x180060c54`
- end: `0x180060ee8`
- name: `?ExchangeAlertActionPage@WdcDataCollectorNode@@AEAAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(__int64, HWND, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180063ef0`
- `0x1800644c0`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18004c568`
- `0x18004c900`
- `0x18005e6e8`
- `0x180060c54`
- `0x180062a60`
- `0x180066e18`
- `0x180086010`

## import_xrefs

- `USER32!GetDlgItem` at `0x180060e15`
- `USER32!GetDlgItem` at `0x180060e15`
- `OLEAUT32!__imp_SysAllocString` at `0x180060db7`
- `OLEAUT32!__imp_SysAllocString` at `0x180060db7`
- `OLEAUT32!__imp_SysFreeString` at `0x180060ec7`
- `OLEAUT32!__imp_SysFreeString` at `0x180060ec7`
- `ole32!CoCreateInstance` at `0x180060d8d`
- `ole32!CoCreateInstance` at `0x180060d8d`

## string_xrefs

- `0x180060db0`: `service\*`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorNode::ExchangeAlertActionPage(__int64 a1, HWND a2, int a3)
{
  OLECHAR *v3; // rsi
  WCHAR *lpString; // r14
  HRESULT DataCollector; // eax
  int v9; // ebx
  const char *v10; // rdx
  int v11; // r8d
  WCHAR *v12; // rax
  const char *v13; // rdx
  int v14; // r8d
  BSTR v15; // rax
  HWND DlgItem; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-40h]
  int v19; // [rsp+28h] [rbp-38h]
  __int64 v20; // [rsp+50h] [rbp-10h] BYREF
  struct IDataCollector *v21; // [rsp+58h] [rbp-8h] BYREF
  struct IUnknown *v22; // [rsp+A8h] [rbp+48h] BYREF

  v3 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  lpString = 0;
  DataCollector = WdcDataCollectorNode::GetDataCollector((WdcDataCollectorNode *)a1, 1, &v21);
  v9 = DataCollector;
  if ( DataCollector < 0 )
    goto LABEL_16;
  DataCollector = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, __int64 *))v21->lpVtbl->QueryInterface)(
                    v21,
                    &IID_IAlertDataCollector,
                    &v20);
  v9 = DataCollector;
  if ( DataCollector < 0 )
    goto LABEL_16;
  v12 = (WCHAR *)WdcAlloc(0x800u, v10, v11);
  lpString = v12;
  if ( !v12 )
  {
LABEL_4:
    v9 = -2147024882;
    LODWORD(ppv) = -2147024882;
LABEL_17:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectornode.cpp",
      "WdcDataCollectorNode::ExchangeAlertActionPage",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_18;
  }
  *v12 = 0;
  v9 = WdcExchangePropertyBoolean<IAlertDataCollector>(a2, (int)ppv, v19, *(WdcValidation **)(a1 + 464));
  if ( v9 < 0 )
  {
    *(_DWORD *)(a1 + 40) = 1801;
    goto LABEL_18;
  }
  v9 = WdcExchangePropertyString<IAlertDataCollector>(
         a2,
         (__int64) IAlertDataCollector::`vcall'{368,{flat}},
         (__int64) IDataCollectorSet::`vcall'{376,{flat}},
         *(WdcValidation **)(a1 + 464),
         lpString);
  if ( v9 < 0 )
  {
    *(_DWORD *)(a1 + 40) = 1803;
    goto LABEL_18;
  }
  if ( a3 == 1 )
  {
    DataCollector = CoCreateInstance(
                      &CLSID_DataCollectorSetCollection,
                      0,
                      0x15u,
                      &IID_IDataCollectorSetCollection,
                      (LPVOID *)&v22);
    v9 = DataCollector;
    if ( DataCollector < 0 )
      goto LABEL_16;
    DataCollector = WdcCoSetSecurity(v22);
    v9 = DataCollector;
    if ( DataCollector < 0 )
      goto LABEL_16;
    v15 = SysAllocString(L"service\\*");
    v3 = v15;
    if ( !v15 )
    {
      LODWORD(ppv) = -2147024882;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
      goto LABEL_4;
    }
    DataCollector = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, BSTR))v22->lpVtbl[4].Release)(
                      v22,
                      *(_QWORD *)(a1 + 48),
                      v15);
    v9 = DataCollector;
    if ( DataCollector < 0
      || (DlgItem = GetDlgItem(a2, 1803),
          DataCollector = WdcForEach<IDataCollectorSet,IDataCollectorSetCollection>(
                            v22,
                            WdcDataCollectorNode::AddAlertDataSetOption,
                            1,
                            DlgItem),
          v9 = DataCollector,
          DataCollector < 0) )
    {
LABEL_16:
      LODWORD(ppv) = DataCollector;
      goto LABEL_17;
    }
  }
LABEL_18:
  if ( v21 )
  {
    ((void (__fastcall *)(struct IDataCollector *))v21->lpVtbl->Release)(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( lpString )
    WdcFree(lpString, v13, v14);
  if ( v3 )
    SysFreeString(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180060c54  mov     [rsp-28h+arg_0], rbx
0x180060c59  mov     [rsp-28h+arg_8], rsi
0x180060c5e  push    rbp
0x180060c5f  push    rdi
0x180060c60  push    r12
0x180060c62  push    r14
0x180060c64  push    r15
0x180060c66  mov     rbp, rsp
0x180060c69  sub     rsp, 60h
0x180060c6d  xor     esi, esi
0x180060c6f  mov     r15d, r8d
0x180060c72  mov     r12, rdx
0x180060c75  mov     [rbp+var_8], rsi
0x180060c79  lea     r8, [rbp+var_8]; struct IDataCollector **
0x180060c7d  mov     [rbp+var_10], rsi
0x180060c81  mov     rdi, rcx
0x180060c84  mov     [rbp+arg_18], rsi
0x180060c88  lea     edx, [rsi+1]; int
0x180060c8b  xor     r14d, r14d
0x180060c8e  call    ?GetDataCollector@WdcDataCollectorNode@@AEAAJHPEAPEAUIDataCollector@@@Z; WdcDataCollectorNode::GetDataCollector(int,IDataCollector * *)
0x180060c93  mov     ebx, eax
0x180060c95  test    eax, eax
0x180060c97  js      loc_180060E3A
0x180060c9d  mov     rcx, [rbp+var_8]
0x180060ca1  lea     r8, [rbp+var_10]
0x180060ca5  lea     rdx, IID_IAlertDataCollector
0x180060cac  mov     rax, [rcx]
0x180060caf  mov     rax, [rax]
0x180060cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cb7  mov     ebx, eax
0x180060cb9  test    eax, eax
0x180060cbb  js      loc_180060E3A
0x180060cc1  mov     ecx, 800h; dwBytes
0x180060cc6  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180060ccb  mov     r14, rax
0x180060cce  test    rax, rax
0x180060cd1  jnz     short loc_180060CE3
0x180060cd3  mov     edi, 8007000Eh
0x180060cd8  mov     ebx, edi
0x180060cda  mov     dword ptr [rsp+60h+ppv], edi
0x180060cde  jmp     loc_180060E3E
0x180060ce3  xor     eax, eax
0x180060ce5  mov     edx, r15d
0x180060ce8  mov     [r14], ax
0x180060cec  mov     rcx, r12; HWND
0x180060cef  mov     rax, [rdi+1D0h]
0x180060cf6  mov     r9, [rbp+var_10]
0x180060cfa  mov     [rsp+60h+var_30], rax; WdcValidation *
0x180060cff  call    ??$WdcExchangePropertyBoolean@UIAlertDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIAlertDataCollector@@P82@EAAJPEAF@ZP82@EAAJF@ZPEAVWdcValidation@@@Z; WdcExchangePropertyBoolean<IAlertDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IAlertDataCollector *,long (IAlertDataCollector::*)(short *),long (IAlertDataCollector::*)(short),WdcValidation *)
0x180060d04  mov     ebx, eax
0x180060d06  test    eax, eax
0x180060d08  jns     short loc_180060D16
0x180060d0a  mov     dword ptr [rdi+28h], 709h
0x180060d11  jmp     loc_180060E5B
0x180060d16  mov     rax, [rdi+1D0h]
0x180060d1d  mov     r8d, 70Bh
0x180060d23  mov     r9, [rbp+var_10]
0x180060d27  mov     edx, r15d
0x180060d2a  mov     [rsp+60h+lpString], r14; lpString
0x180060d2f  mov     rcx, r12; HWND
0x180060d32  mov     [rsp+60h+var_30], rax; WdcValidation *
0x180060d37  lea     rax, ??_9IDataCollectorSet@@$BBHI@AA; [thunk]: IDataCollectorSet::`vcall'{376,{flat}}
0x180060d3e  mov     [rsp+60h+var_38], rax; __int64
0x180060d43  lea     rax, ??_9IAlertDataCollector@@$BBHA@AA; [thunk]: IAlertDataCollector::`vcall'{368,{flat}}
0x180060d4a  mov     [rsp+60h+ppv], rax; __int64
0x180060d4f  call    ??$WdcExchangePropertyString@UIAlertDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIAlertDataCollector@@P82@EAAJPEAPEAG@ZP82@EAAJPEAG@ZPEAVWdcValidation@@5K@Z; WdcExchangePropertyString<IAlertDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IAlertDataCollector *,long (IAlertDataCollector::*)(ushort * *),long (IAlertDataCollector::*)(ushort *),WdcValidation *,ushort *,ulong)
0x180060d54  mov     ebx, eax
0x180060d56  test    eax, eax
0x180060d58  jns     short loc_180060D66
0x180060d5a  mov     dword ptr [rdi+28h], 70Bh
0x180060d61  jmp     loc_180060E5B
0x180060d66  cmp     r15d, 1
0x180060d6a  jnz     loc_180060E5B
0x180060d70  lea     rax, [rbp+arg_18]
0x180060d74  xor     edx, edx; pUnkOuter
0x180060d76  lea     r9, IID_IDataCollectorSetCollection; riid
0x180060d7d  mov     [rsp+60h+ppv], rax; ppv
0x180060d82  lea     r8d, [r15+14h]; dwClsContext
0x180060d86  lea     rcx, CLSID_DataCollectorSetCollection; rclsid
0x180060d8d  call    cs:__imp_CoCreateInstance
0x180060d93  mov     ebx, eax
0x180060d95  test    eax, eax
0x180060d97  js      loc_180060E3A
0x180060d9d  mov     rcx, [rbp+arg_18]; struct IUnknown *
0x180060da1  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x180060da6  mov     ebx, eax
0x180060da8  test    eax, eax
0x180060daa  js      loc_180060E3A
0x180060db0  lea     rcx, aService_0; "service\\*"
0x180060db7  call    cs:__imp_SysAllocString
0x180060dbd  mov     rsi, rax
0x180060dc0  test    rax, rax
0x180060dc3  jnz     short loc_180060DF0
0x180060dc5  mov     edi, 8007000Eh
0x180060dca  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180060dd1  xor     r8d, r8d; int
0x180060dd4  mov     dword ptr [rsp+60h+ppv], edi
0x180060dd8  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180060ddf  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180060de6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180060deb  jmp     loc_180060CD8
0x180060df0  mov     rcx, [rbp+arg_18]
0x180060df4  mov     r8, rsi
0x180060df7  mov     rdx, [rdi+30h]
0x180060dfb  mov     rax, [rcx]
0x180060dfe  mov     rax, [rax+70h]
0x180060e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e07  mov     ebx, eax
0x180060e09  test    eax, eax
0x180060e0b  js      short loc_180060E3A
0x180060e0d  mov     edx, 70Bh; nIDDlgItem
0x180060e12  mov     rcx, r12; hDlg
0x180060e15  call    cs:__imp_GetDlgItem
0x180060e1b  mov     rcx, [rbp+arg_18]
0x180060e1f  lea     rdx, ?AddAlertDataSetOption@WdcDataCollectorNode@@SAJPEAU_WDC_ENUM_CALL@@@Z; WdcDataCollectorNode::AddAlertDataSetOption(_WDC_ENUM_CALL *)
0x180060e26  mov     r9, rax
0x180060e29  mov     r8d, 1
0x180060e2f  call    ??$WdcForEach@UIDataCollectorSet@@UIDataCollectorSetCollection@@@@YAJPEAUIDataCollectorSetCollection@@P6AJPEAU_WDC_ENUM_CALL@@@ZKZZ; WdcForEach<IDataCollectorSet,IDataCollectorSetCollection>(IDataCollectorSetCollection *,long (*)(_WDC_ENUM_CALL *),ulong,...)
0x180060e34  mov     ebx, eax
0x180060e36  test    eax, eax
0x180060e38  jns     short loc_180060E5B
0x180060e3a  mov     dword ptr [rsp+60h+ppv], eax
0x180060e3e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180060e45  xor     r8d, r8d; int
0x180060e48  lea     rdx, aWdcdatacollect_71; "WdcDataCollectorNode::ExchangeAlertActi"...
0x180060e4f  lea     rcx, aBaseDiagnosisP_17; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180060e56  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180060e5b  mov     rcx, [rbp+var_8]
0x180060e5f  test    rcx, rcx
0x180060e62  jz      short loc_180060E78
0x180060e64  mov     rax, [rcx]
0x180060e67  mov     rax, [rax+10h]
0x180060e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e70  mov     [rbp+var_8], 0
0x180060e78  mov     rcx, [rbp+arg_18]
0x180060e7c  test    rcx, rcx
0x180060e7f  jz      short loc_180060E95
0x180060e81  mov     rax, [rcx]
0x180060e84  mov     rax, [rax+10h]
0x180060e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e8d  mov     [rbp+arg_18], 0
0x180060e95  mov     rcx, [rbp+var_10]
0x180060e99  test    rcx, rcx
0x180060e9c  jz      short loc_180060EB2
0x180060e9e  mov     rax, [rcx]
0x180060ea1  mov     rax, [rax+10h]
0x180060ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060eaa  mov     [rbp+var_10], 0
0x180060eb2  test    r14, r14
0x180060eb5  jz      short loc_180060EBF
0x180060eb7  mov     rcx, r14; void *
0x180060eba  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180060ebf  test    rsi, rsi
0x180060ec2  jz      short loc_180060ECD
0x180060ec4  mov     rcx, rsi; bstrString
0x180060ec7  call    cs:__imp_SysFreeString
0x180060ecd  lea     r11, [rsp+60h+var_s0]
0x180060ed2  mov     eax, ebx
0x180060ed4  mov     rbx, [r11+30h]
0x180060ed8  mov     rsi, [r11+38h]
0x180060edc  mov     rsp, r11
0x180060edf  pop     r15
0x180060ee1  pop     r14
0x180060ee3  pop     r12
0x180060ee5  pop     rdi
0x180060ee6  pop     rbp
0x180060ee7  retn
```
