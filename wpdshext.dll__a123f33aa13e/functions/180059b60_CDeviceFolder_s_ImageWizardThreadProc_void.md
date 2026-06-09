# CDeviceFolder::s_ImageWizardThreadProc(void *)

- ea: `0x180059b60`
- end: `0x180059d4d`
- name: `?s_ImageWizardThreadProc@CDeviceFolder@@CAKPEAX@Z`
- size: `493`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000cb90`
- `0x1800285c8`
- `0x180035590`
- `0x1800361ba`
- `0x180056444`
- `0x18005949c`
- `0x180059b60`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180059cfd`
- `ole32!CoTaskMemFree` at `0x180059cfd`
- `ole32!CoCreateInstance` at `0x180059bec`
- `ole32!CoCreateInstance` at `0x180059c93`
- `ole32!CoCreateInstance` at `0x180059bec`
- `ole32!CoCreateInstance` at `0x180059c93`
- `ole32!CoAllowSetForegroundWindow` at `0x180059c0a`
- `ole32!CoAllowSetForegroundWindow` at `0x180059ca6`
- `ole32!CoAllowSetForegroundWindow` at `0x180059c0a`
- `ole32!CoAllowSetForegroundWindow` at `0x180059ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x180059d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180059d0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDeviceFolder::s_ImageWizardThreadProc(WCHAR *lpThreadParameter)
{
  WCHAR *v1; // rsi
  HRESULT Instance; // edi
  unsigned int v3; // r8d
  HRESULT v4; // eax
  __int64 result; // rax
  BSTR bstrString; // [rsp+50h] [rbp-258h] BYREF
  IUnknown *pUnk; // [rsp+58h] [rbp-250h] BYREF
  IUnknown *ppv; // [rsp+60h] [rbp-248h] BYREF
  int v9; // [rsp+68h] [rbp-240h]
  int v10; // [rsp+6Ch] [rbp-23Ch] BYREF
  WCHAR *v11; // [rsp+70h] [rbp-238h]
  int v12; // [rsp+78h] [rbp-230h] BYREF
  unsigned __int16 v13[264]; // [rsp+80h] [rbp-228h] BYREF

  v1 = lpThreadParameter;
  v11 = lpThreadParameter;
  ppv = 0;
  pUnk = 0;
  bstrString = 0;
  memset_0(v13, 0, 0x208u);
  v10 = 0;
  if ( !v1 )
  {
    Instance = -2147024809;
    goto LABEL_11;
  }
  if ( CoCreateInstance(
         &CLSID_PhotoAcquireAutoPlayHWEventHandler,
         0,
         4u,
         &GUID_c1fb73d0_ec3a_4ba2_b512_8cdb9187b6d1,
         (LPVOID *)&pUnk) >= 0 )
  {
    ATL::CComBSTR::operator=(&bstrString, v1);
    CoAllowSetForegroundWindow(pUnk, 0);
    v4 = ((__int64 (__fastcall *)(IUnknown *, BSTR, const WCHAR *, const WCHAR *))pUnk->lpVtbl[1].AddRef)(
           pUnk,
           bstrString,
           &String,
           &String);
    goto LABEL_10;
  }
  Instance = CDeviceFolder::_MapPnPDevicePathToDeviceID(v1, v13, v3);
  if ( Instance < 0 )
    goto LABEL_11;
  try
  {
    ATL::CComBSTR::operator=(&bstrString, v13);
  }
  catch ( ATL::CAtlException v12 )
  {
    v9 = v12;
    Instance = v9;
    v1 = v11;
    if ( v9 >= 0 )
      goto LABEL_8;
LABEL_11:
    CoTaskMemFree(v1);
    DllRelease();
    SysFreeString(bstrString);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pUnk);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    result = (unsigned int)Instance;
  }
LABEL_8:
  Instance = CoCreateInstance(&rclsid, 0, 4u, &GUID_ae6287b0_0084_11d2_973b_00a0c9068f2e, (LPVOID *)&ppv);
  if ( Instance < 0 )
    goto LABEL_11;
  CoAllowSetForegroundWindow(ppv, 0);
  v4 = ((__int64 (__fastcall *)(IUnknown *, GUID *, _QWORD, BSTR, _QWORD, _DWORD, _QWORD, int *, _DWORD))ppv->lpVtbl[1].QueryInterface)(
         ppv,
         &GUID_NULL,
         0,
         bstrString,
         0,
         0,
         0,
         &v10,
         0);
LABEL_10:
  Instance = v4;
  goto LABEL_11;
}

```

## disassembly

```asm
0x180059b60  mov     [rsp+arg_8], rsi
0x180059b65  push    rdi
0x180059b66  sub     rsp, 2A0h
0x180059b6d  mov     rax, cs:__security_cookie
0x180059b74  xor     rax, rsp
0x180059b77  mov     [rsp+2A8h+var_18], rax
0x180059b7f  mov     rsi, rcx
0x180059b82  mov     [rsp+2A8h+var_238], rcx
0x180059b87  mov     [rsp+2A8h+var_248], 0
0x180059b90  mov     [rsp+2A8h+pUnk], 0
0x180059b99  mov     [rsp+2A8h+bstrString], 0
0x180059ba2  xor     edx, edx; Val
0x180059ba4  mov     r8d, 208h; Size
0x180059baa  lea     rcx, [rsp+2A8h+var_228]; void *
0x180059bb2  call    memset_0
0x180059bb7  mov     [rsp+2A8h+var_23C], 0
0x180059bbf  test    rsi, rsi
0x180059bc2  jnz     short loc_180059BCE
0x180059bc4  mov     edi, 80070057h
0x180059bc9  jmp     loc_180059CFA
0x180059bce  lea     rax, [rsp+2A8h+pUnk]
0x180059bd3  mov     [rsp+2A8h+ppv], rax; ppv
0x180059bd8  lea     r9, _GUID_c1fb73d0_ec3a_4ba2_b512_8cdb9187b6d1; riid
0x180059bdf  xor     edx, edx; pUnkOuter
0x180059be1  lea     r8d, [rdx+4]; dwClsContext
0x180059be5  lea     rcx, CLSID_PhotoAcquireAutoPlayHWEventHandler; rclsid
0x180059bec  call    cs:__imp_CoCreateInstance
0x180059bf2  test    eax, eax
0x180059bf4  js      short loc_180059C35
0x180059bf6  mov     rdx, rsi
0x180059bf9  lea     rcx, [rsp+2A8h+bstrString]
0x180059bfe  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180059c03  xor     edx, edx; lpvReserved
0x180059c05  mov     rcx, [rsp+2A8h+pUnk]; pUnk
0x180059c0a  call    cs:__imp_CoAllowSetForegroundWindow
0x180059c10  mov     rcx, [rsp+2A8h+pUnk]
0x180059c15  mov     rax, [rcx]
0x180059c18  lea     r8, String
0x180059c1f  mov     r9, r8
0x180059c22  mov     rdx, [rsp+2A8h+bstrString]
0x180059c27  mov     rax, [rax+20h]
0x180059c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c30  jmp     loc_180059CF8
0x180059c35  lea     rdx, [rsp+2A8h+var_228]; unsigned __int16 *
0x180059c3d  mov     rcx, rsi; psz1
0x180059c40  call    ?_MapPnPDevicePathToDeviceID@CDeviceFolder@@CAJPEBGPEAGI@Z; CDeviceFolder::_MapPnPDevicePathToDeviceID(ushort const *,ushort *,uint)
0x180059c45  mov     edi, eax
0x180059c47  test    eax, eax
0x180059c49  js      loc_180059CFA
0x180059c4f  lea     rdx, [rsp+2A8h+var_228]
0x180059c57  lea     rcx, [rsp+2A8h+bstrString]
0x180059c5c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180059c61  nop
0x180059c62  jmp     short loc_180059C75
0x180059c64  mov     edi, [rsp+2A8h+var_240]
0x180059c68  mov     rsi, [rsp+2A8h+var_238]
0x180059c6d  test    edi, edi
0x180059c6f  js      loc_180059CFA
0x180059c75  lea     rax, [rsp+2A8h+var_248]
0x180059c7a  mov     [rsp+2A8h+ppv], rax; ppv
0x180059c7f  lea     r9, _GUID_ae6287b0_0084_11d2_973b_00a0c9068f2e; riid
0x180059c86  xor     edx, edx; pUnkOuter
0x180059c88  lea     r8d, [rdx+4]; dwClsContext
0x180059c8c  lea     rcx, rclsid; rclsid
0x180059c93  call    cs:__imp_CoCreateInstance
0x180059c99  mov     edi, eax
0x180059c9b  test    eax, eax
0x180059c9d  js      short loc_180059CFA
0x180059c9f  xor     edx, edx; lpvReserved
0x180059ca1  mov     rcx, [rsp+2A8h+var_248]; pUnk
0x180059ca6  call    cs:__imp_CoAllowSetForegroundWindow
0x180059cac  mov     rcx, [rsp+2A8h+var_248]
0x180059cb1  mov     rax, [rcx]
0x180059cb4  mov     [rsp+2A8h+var_268], 0
0x180059cbc  lea     rdx, [rsp+2A8h+var_23C]
0x180059cc1  mov     [rsp+2A8h+var_270], rdx
0x180059cc6  mov     [rsp+2A8h+var_278], 0
0x180059ccf  mov     [rsp+2A8h+var_280], 0
0x180059cd7  mov     [rsp+2A8h+ppv], 0
0x180059ce0  mov     r9, [rsp+2A8h+bstrString]
0x180059ce5  xor     r8d, r8d
0x180059ce8  lea     rdx, GUID_NULL
0x180059cef  mov     rax, [rax+18h]
0x180059cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059cf8  mov     edi, eax
0x180059cfa  mov     rcx, rsi; pv
0x180059cfd  call    cs:__imp_CoTaskMemFree
0x180059d03  call    DllRelease
0x180059d08  nop
0x180059d09  mov     rcx, [rsp+2A8h+bstrString]; bstrString
0x180059d0e  call    cs:__imp_SysFreeString
0x180059d14  nop
0x180059d15  lea     rcx, [rsp+2A8h+pUnk]
0x180059d1a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d1f  nop
0x180059d20  lea     rcx, [rsp+2A8h+var_248]
0x180059d25  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059d2a  mov     eax, edi
0x180059d2c  mov     rcx, [rsp+2A8h+var_18]
0x180059d34  xor     rcx, rsp; StackCookie
0x180059d37  call    __security_check_cookie
0x180059d3c  mov     rsi, [rsp+2A8h+arg_8]
0x180059d44  add     rsp, 2A0h
0x180059d4b  pop     rdi
0x180059d4c  retn
```
