# pWdsImgSrvRefreshSettings(_IMG_SERVER_CONTEXT *)

- ea: `0x18000c69c`
- end: `0x18000cbce`
- name: `?pWdsImgSrvRefreshSettings@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z`
- size: `1330`
- prototype: `unsigned int __fastcall(struct _IMG_SERVER_CONTEXT *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006b10`
- `0x180007120`

## callees

- `0x1800026f8`
- `0x180002918`
- `0x180006a58`
- `0x180006e20`
- `0x180009460`
- `0x180009490`
- `0x18000aeac`
- `0x18000b370`
- `0x18000c69c`
- `0x18000cbd4`
- `0x18000ccf8`
- `0x180016020`
- `0x180017010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000c894`
- `ole32!CoCreateInstance` at `0x18000c8e9`
- `ole32!CoCreateInstance` at `0x18000c894`
- `ole32!CoCreateInstance` at `0x18000c8e9`
- `ole32!CoInitializeEx` at `0x18000c8ad`
- `ole32!CoInitializeEx` at `0x18000c8ad`
- `ole32!CLSIDFromProgID` at `0x18000c858`
- `ole32!CLSIDFromProgID` at `0x18000c858`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb71`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb71`
- `WdsCommonLib!?WaitForDirectoryServicesNetworking@@YAKK@Z` at `0x18000c79b`
- `WdsCommonLib!?WaitForDirectoryServicesNetworking@@YAKK@Z` at `0x18000c79b`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000c99c`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000c99c`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000ca46`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000ca46`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x18000c986`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x18000c986`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000ca10`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000ca10`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000cb30`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000cb5c`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000cb30`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000cb5c`

## string_xrefs

- `0x18000c9ba`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000c851`: `WdsMgmt.WdsDirectoryServicesManager`
- `0x18000c9db`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
__int64 __fastcall pWdsImgSrvRefreshSettings(struct _IMG_SERVER_CONTEXT *a1)
{
  __int64 ValueDwordWithDefault; // rsi
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  HKEY v29; // rdx
  unsigned int v30; // r9d
  CMRSWLock *v31; // r15
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rcx
  bool v42; // zf
  int Action; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-60h]
  __int16 v46; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v47; // [rsp+38h] [rbp-48h] BYREF
  __int64 v48; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-38h] BYREF
  __int64 v50; // [rsp+50h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-20h] BYREF
  GUID clsid; // [rsp+68h] [rbp-18h] BYREF

  v47 = 0;
  v50 = 0;
  LODWORD(ValueDwordWithDefault) = 0;
  v48 = 0;
  v46 = 0;
  bstrString = 0;
  phkResult = 0;
  v49 = 0;
  WdsImgTrace(0x10000u, L"-> pWdsImgSrvRefreshSettings");
  if ( a1 )
  {
    v3 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)a1 + 5) + 88LL))(*((_QWORD *)a1 + 5), &v48);
    if ( (int)ElValidateHr_1(v3, v4, v5, 1487) >= 0 )
    {
      v3 = (*(unsigned int (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v48 + 176LL))(v48, &v46);
      if ( (int)ElValidateHr_1(v3, v7, v8, 1490) >= 0 )
      {
        if ( v48 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
          v48 = 0;
        }
        if ( v46 && !*((_DWORD *)a1 + 26) )
        {
          ValueDwordWithDefault = WaitForDirectoryServicesNetworking(0x1D4C0u);
          if ( (unsigned int)ElValidateWin32_1(ValueDwordWithDefault, v9, v10, 1504) )
          {
LABEL_28:
            if ( (int)ValueDwordWithDefault > 0 )
              LODWORD(v3) = (unsigned __int16)ValueDwordWithDefault | 0x80070000;
            else
              LODWORD(v3) = ValueDwordWithDefault;
            goto LABEL_31;
          }
          *((_DWORD *)a1 + 26) = 1;
        }
        v3 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 8) + 64LL))(*((_QWORD *)a1 + 8));
        if ( (int)ElValidateHr_1(v3, v11, v12, 1514) >= 0 )
        {
          v3 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 11) + 64LL))(*((_QWORD *)a1 + 11));
          if ( (int)ElValidateHr_1(v3, v13, v14, 1521) >= 0 )
          {
            if ( v46 != -1 )
              goto LABEL_21;
            v15 = *((_QWORD *)a1 + 8);
            clsid = 0;
            v3 = (*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 104LL))(v15, &bstrString);
            if ( (int)ElValidateHr_1(v3, v16, v17, 1533) >= 0 )
            {
              v3 = (unsigned int)CLSIDFromProgID(L"WdsMgmt.WdsDirectoryServicesManager", &clsid);
              if ( (int)ElValidateHr_1(v3, v18, v19, 1536) >= 0 )
              {
                LODWORD(v3) = CoCreateInstance(&clsid, 0, 1u, &GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0, &v47);
                if ( (_DWORD)v3 != -2147221008
                  || (v3 = (unsigned int)CoInitializeEx(0, 0), (int)ElValidateHr_1(v3, v21, v22, 1546) >= 0)
                  && (v3 = (unsigned int)CoCreateInstance(
                                           &clsid,
                                           0,
                                           1u,
                                           &GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0,
                                           &v47),
                      (int)ElValidateHr_1(v3, v23, v24, 1553) >= 0) )
                {
                  if ( (int)ElValidateHr_1((unsigned int)v3, v20, v6, 1555) >= 0 )
                  {
                    v3 = (*(unsigned int (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v47 + 96LL))(
                           v47,
                           bstrString,
                           &v50);
                    if ( (int)ElValidateHr_1(v3, v25, v26, 1559) >= 0 )
                    {
LABEL_21:
                      v3 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 6) + 64LL))(*((_QWORD *)a1 + 6));
                      if ( (int)ElValidateHr_1(v3, v27, v28, 1567) >= 0 )
                      {
                        v31 = (CMRSWLock *)*((_QWORD *)a1 + 12);
                        if ( v31 )
                        {
                          LODWORD(ValueDwordWithDefault) = 0;
                          CMRSWLock::ReaderLock(*((CMRSWLock **)a1 + 12));
                          v32 = *((_DWORD *)v31 + 39);
                          CMRSWLock::ReaderRelease(v31);
                          if ( v32 )
                          {
                            ValueDwordWithDefault = CImageCache::OnChange(v31);
                            ElValidateWin32_0(
                              ValueDwordWithDefault,
                              v35,
                              "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                              369);
                          }
                          if ( (unsigned int)ElValidateWin32_1((unsigned int)ValueDwordWithDefault, v33, v34, 1575) )
                            goto LABEL_28;
                        }
                        ValueDwordWithDefault = CRegKey::Open(
                                                  &phkResult,
                                                  v29,
                                                  L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                                                  v30);
                        if ( (unsigned int)ElValidateWin32_1(ValueDwordWithDefault, v36, v37, 1585) )
                          goto LABEL_28;
                        ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault(
                                                  (CRegKey *)&phkResult,
                                                  L"ParseKnownDUIDs",
                                                  1u,
                                                  &v49);
                        if ( (unsigned int)ElValidateWin32_1(ValueDwordWithDefault, v38, v39, 1591) )
                          goto LABEL_28;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_31:
    if ( (int)v3 >= 0 )
      goto LABEL_33;
    goto LABEL_32;
  }
  LODWORD(v3) = -2147024809;
LABEL_32:
  LODWORD(ValueDwordWithDefault) = WIN32_FROM_HRESULT(v3);
LABEL_33:
  if ( (_DWORD)ValueDwordWithDefault )
  {
    if ( v47 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
      v47 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
  }
  else
  {
    CAutoWriterLock::CAutoWriterLock((CAutoWriterLock *)&clsid, (struct CMRSWLock *)g_Lock, v6);
    v40 = *((_QWORD *)a1 + 9);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v41 = *((_QWORD *)a1 + 10);
    *((_QWORD *)a1 + 9) = v47;
    v47 = 0;
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v42 = v49 == 0;
    *((_QWORD *)a1 + 10) = v50;
    v50 = 0;
    *((_DWORD *)a1 + 28) = !v42;
    CAutoWriterLock::Unlock((CAutoWriterLock *)&clsid);
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  Action = CTrackErrState::NextAction((CTrackErrState *)&qword_180022D58, ValueDwordWithDefault);
  if ( Action == 2 )
  {
    CEventLog::Log((CEventLog *)g_EventLog, 0x106010Bu, 0);
  }
  else if ( Action == 1 )
  {
    LODWORD(ppv) = ValueDwordWithDefault;
    CEventLog::Log((CEventLog *)g_EventLog, 0xC106010A, 1, 5, ppv);
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  WdsImgTrace(0x10000u, L"<- pWdsImgSrvRefreshSettings=%x", (unsigned int)ValueDwordWithDefault);
  CRegKey::Close((CRegKey *)&phkResult);
  return (unsigned int)ValueDwordWithDefault;
}

```

## disassembly

```asm
0x18000c69c  mov     [rsp-28h+arg_8], rbx
0x18000c6a1  mov     [rsp-28h+arg_10], rsi
0x18000c6a6  mov     [rsp-28h+arg_18], rdi
0x18000c6ab  push    rbp
0x18000c6ac  push    r12
0x18000c6ae  push    r13
0x18000c6b0  push    r14
0x18000c6b2  push    r15
0x18000c6b4  mov     rbp, rsp
0x18000c6b7  sub     rsp, 80h
0x18000c6be  mov     rax, cs:__security_cookie
0x18000c6c5  xor     rax, rsp
0x18000c6c8  mov     [rbp+var_8], rax
0x18000c6cc  xor     r12d, r12d
0x18000c6cf  lea     rdx, aPwdsimgsrvrefr; "-> pWdsImgSrvRefreshSettings"
0x18000c6d6  mov     r14, rcx
0x18000c6d9  mov     [rbp+var_48], r12
0x18000c6dd  mov     ecx, 10000h; unsigned int
0x18000c6e2  mov     [rbp+var_30], r12
0x18000c6e6  mov     esi, r12d
0x18000c6e9  mov     [rbp+var_40], r12
0x18000c6ed  mov     [rbp+var_50], r12w
0x18000c6f2  mov     [rbp+bstrString], r12
0x18000c6f6  mov     [rbp+phkResult], r12
0x18000c6fa  mov     [rbp+var_38], r12d
0x18000c6fe  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x18000c703  lea     r13d, [r12+1]
0x18000c708  test    r14, r14
0x18000c70b  jnz     short loc_18000C717
0x18000c70d  mov     edi, 80070057h
0x18000c712  jmp     loc_18000CA44
0x18000c717  mov     rcx, [r14+28h]
0x18000c71b  lea     rdx, [rbp+var_40]
0x18000c71f  mov     rax, [rcx]
0x18000c722  mov     rax, [rax+58h]
0x18000c726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c72b  mov     r9d, 5CFh
0x18000c731  mov     ecx, eax
0x18000c733  mov     edi, eax
0x18000c735  call    ElValidateHr_1
0x18000c73a  test    eax, eax
0x18000c73c  js      loc_18000CA40
0x18000c742  mov     rcx, [rbp+var_40]
0x18000c746  lea     rdx, [rbp+var_50]
0x18000c74a  mov     rax, [rcx]
0x18000c74d  mov     rax, [rax+0B0h]
0x18000c754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c759  mov     r9d, 5D2h
0x18000c75f  mov     ecx, eax
0x18000c761  mov     edi, eax
0x18000c763  call    ElValidateHr_1
0x18000c768  test    eax, eax
0x18000c76a  js      loc_18000CA40
0x18000c770  mov     rcx, [rbp+var_40]
0x18000c774  test    rcx, rcx
0x18000c777  jz      short loc_18000C789
0x18000c779  mov     rax, [rcx]
0x18000c77c  mov     rax, [rax+10h]
0x18000c780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c785  mov     [rbp+var_40], r12
0x18000c789  cmp     [rbp+var_50], r12w
0x18000c78e  jz      short loc_18000C7C2
0x18000c790  cmp     [r14+68h], r12d
0x18000c794  jnz     short loc_18000C7C2
0x18000c796  mov     ecx, 1D4C0h
0x18000c79b  call    cs:__imp_?WaitForDirectoryServicesNetworking@@YAKK@Z; WaitForDirectoryServicesNetworking(ulong)
0x18000c7a2  nop     dword ptr [rax+rax+00h]
0x18000c7a7  mov     ecx, eax
0x18000c7a9  mov     r9d, 5E0h
0x18000c7af  mov     esi, eax
0x18000c7b1  call    ElValidateWin32_1
0x18000c7b6  test    eax, eax
0x18000c7b8  jnz     loc_18000CA2F
0x18000c7be  mov     [r14+68h], r13d
0x18000c7c2  mov     rcx, [r14+40h]
0x18000c7c6  mov     rax, [rcx]
0x18000c7c9  mov     rax, [rax+40h]
0x18000c7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d2  mov     r9d, 5EAh
0x18000c7d8  mov     ecx, eax
0x18000c7da  mov     edi, eax
0x18000c7dc  call    ElValidateHr_1
0x18000c7e1  test    eax, eax
0x18000c7e3  js      loc_18000CA40
0x18000c7e9  mov     rcx, [r14+58h]
0x18000c7ed  mov     rax, [rcx]
0x18000c7f0  mov     rax, [rax+40h]
0x18000c7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f9  mov     r9d, 5F1h
0x18000c7ff  mov     ecx, eax
0x18000c801  mov     edi, eax
0x18000c803  call    ElValidateHr_1
0x18000c808  test    eax, eax
0x18000c80a  js      loc_18000CA40
0x18000c810  cmp     [rbp+var_50], 0FFFFh
0x18000c815  jnz     loc_18000C950
0x18000c81b  mov     rcx, [r14+40h]
0x18000c81f  lea     rdx, [rbp+bstrString]
0x18000c823  xorps   xmm0, xmm0
0x18000c826  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18000c82a  mov     rax, [rcx]
0x18000c82d  mov     rax, [rax+68h]
0x18000c831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c836  mov     r9d, 5FDh
0x18000c83c  mov     ecx, eax
0x18000c83e  mov     edi, eax
0x18000c840  call    ElValidateHr_1
0x18000c845  test    eax, eax
0x18000c847  js      loc_18000CA40
0x18000c84d  lea     rdx, [rbp+clsid]; lpclsid
0x18000c851  lea     rcx, aWdsmgmtWdsdire; "WdsMgmt.WdsDirectoryServicesManager"
0x18000c858  call    cs:__imp_CLSIDFromProgID
0x18000c85f  nop     dword ptr [rax+rax+00h]
0x18000c864  mov     ecx, eax
0x18000c866  mov     r9d, 600h
0x18000c86c  mov     edi, eax
0x18000c86e  call    ElValidateHr_1
0x18000c873  test    eax, eax
0x18000c875  js      loc_18000CA40
0x18000c87b  lea     rax, [rbp+var_48]
0x18000c87f  mov     r8d, r13d; dwClsContext
0x18000c882  lea     r9, _GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0; riid
0x18000c889  mov     [rsp+80h+ppv], rax; ppv
0x18000c88e  xor     edx, edx; pUnkOuter
0x18000c890  lea     rcx, [rbp+clsid]; rclsid
0x18000c894  call    cs:__imp_CoCreateInstance
0x18000c89b  nop     dword ptr [rax+rax+00h]
0x18000c8a0  mov     edi, eax
0x18000c8a2  cmp     eax, 800401F0h
0x18000c8a7  jnz     short loc_18000C90C
0x18000c8a9  xor     edx, edx; dwCoInit
0x18000c8ab  xor     ecx, ecx; pvReserved
0x18000c8ad  call    cs:__imp_CoInitializeEx
0x18000c8b4  nop     dword ptr [rax+rax+00h]
0x18000c8b9  mov     ecx, eax
0x18000c8bb  mov     r9d, 60Ah
0x18000c8c1  mov     edi, eax
0x18000c8c3  call    ElValidateHr_1
0x18000c8c8  test    eax, eax
0x18000c8ca  js      loc_18000CA40
0x18000c8d0  lea     rax, [rbp+var_48]
0x18000c8d4  mov     r8d, r13d; dwClsContext
0x18000c8d7  lea     r9, _GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0; riid
0x18000c8de  mov     [rsp+80h+ppv], rax; ppv
0x18000c8e3  xor     edx, edx; pUnkOuter
0x18000c8e5  lea     rcx, [rbp+clsid]; rclsid
0x18000c8e9  call    cs:__imp_CoCreateInstance
0x18000c8f0  nop     dword ptr [rax+rax+00h]
0x18000c8f5  mov     ecx, eax
0x18000c8f7  mov     r9d, 611h
0x18000c8fd  mov     edi, eax
0x18000c8ff  call    ElValidateHr_1
0x18000c904  test    eax, eax
0x18000c906  js      loc_18000CA40
0x18000c90c  mov     r9d, 613h
0x18000c912  mov     ecx, edi
0x18000c914  call    ElValidateHr_1
0x18000c919  test    eax, eax
0x18000c91b  js      loc_18000CA40
0x18000c921  mov     rcx, [rbp+var_48]
0x18000c925  lea     r8, [rbp+var_30]
0x18000c929  mov     rdx, [rbp+bstrString]
0x18000c92d  mov     rax, [rcx]
0x18000c930  mov     rax, [rax+60h]
0x18000c934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c939  mov     r9d, 617h
0x18000c93f  mov     ecx, eax
0x18000c941  mov     edi, eax
0x18000c943  call    ElValidateHr_1
0x18000c948  test    eax, eax
0x18000c94a  js      loc_18000CA40
0x18000c950  mov     rcx, [r14+30h]
0x18000c954  mov     rax, [rcx]
0x18000c957  mov     rax, [rax+40h]
0x18000c95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c960  mov     r9d, 61Fh
0x18000c966  mov     ecx, eax
0x18000c968  mov     edi, eax
0x18000c96a  call    ElValidateHr_1
0x18000c96f  test    eax, eax
0x18000c971  js      loc_18000CA40
0x18000c977  mov     r15, [r14+60h]
0x18000c97b  test    r15, r15
0x18000c97e  jz      short loc_18000C9DB
0x18000c980  mov     rcx, r15
0x18000c983  mov     esi, r12d
0x18000c986  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000c98d  nop     dword ptr [rax+rax+00h]
0x18000c992  mov     ebx, [r15+9Ch]
0x18000c999  mov     rcx, r15
0x18000c99c  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000c9a3  nop     dword ptr [rax+rax+00h]
0x18000c9a8  test    ebx, ebx
0x18000c9aa  jz      short loc_18000C9CA
0x18000c9ac  mov     rcx, r15; this
0x18000c9af  call    ?OnChange@CImageCache@@QEAAKXZ; CImageCache::OnChange(void)
0x18000c9b4  mov     r9d, 171h
0x18000c9ba  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000c9c1  mov     ecx, eax
0x18000c9c3  mov     esi, eax
0x18000c9c5  call    ElValidateWin32_0
0x18000c9ca  mov     r9d, 627h
0x18000c9d0  mov     ecx, esi
0x18000c9d2  call    ElValidateWin32_1
0x18000c9d7  test    eax, eax
0x18000c9d9  jnz     short loc_18000CA2F
0x18000c9db  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WD"...
0x18000c9e2  lea     rcx, [rbp+phkResult]; phkResult
0x18000c9e6  call    ?Open@CRegKey@@QEAAKPEAUHKEY__@@PEBGK@Z; CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000c9eb  mov     r9d, 631h
0x18000c9f1  mov     ecx, eax
0x18000c9f3  mov     esi, eax
0x18000c9f5  call    ElValidateWin32_1
0x18000c9fa  test    eax, eax
0x18000c9fc  jnz     short loc_18000CA2F
0x18000c9fe  lea     r9, [rbp+var_38]
0x18000ca02  mov     r8d, r13d
0x18000ca05  lea     rdx, aParseknownduid; "ParseKnownDUIDs"
0x18000ca0c  lea     rcx, [rbp+phkResult]
0x18000ca10  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000ca17  nop     dword ptr [rax+rax+00h]
0x18000ca1c  mov     ecx, eax
0x18000ca1e  mov     r9d, 637h
0x18000ca24  mov     esi, eax
0x18000ca26  call    ElValidateWin32_1
0x18000ca2b  test    eax, eax
0x18000ca2d  jz      short loc_18000CA40
0x18000ca2f  test    esi, esi
0x18000ca31  jg      short loc_18000CA37
0x18000ca33  mov     edi, esi
0x18000ca35  jmp     short loc_18000CA40
0x18000ca37  movzx   edi, si
0x18000ca3a  or      edi, 80070000h
0x18000ca40  test    edi, edi
0x18000ca42  jns     short loc_18000CA54
0x18000ca44  mov     ecx, edi
0x18000ca46  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000ca4d  nop     dword ptr [rax+rax+00h]
0x18000ca52  mov     esi, eax
0x18000ca54  test    esi, esi
0x18000ca56  jnz     short loc_18000CAC3
0x18000ca58  lea     rdx, ?g_Lock@@3VCMRSWLock@@A; struct CMRSWLock *
0x18000ca5f  lea     rcx, [rbp+clsid]; this
0x18000ca63  call    ??0CAutoWriterLock@@QEAA@PEAVCMRSWLock@@H@Z; CAutoWriterLock::CAutoWriterLock(CMRSWLock *,int)
0x18000ca68  mov     rcx, [r14+48h]
0x18000ca6c  test    rcx, rcx
0x18000ca6f  jz      short loc_18000CA7D
0x18000ca71  mov     rax, [rcx]
0x18000ca74  mov     rax, [rax+10h]
0x18000ca78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca7d  mov     rax, [rbp+var_48]
0x18000ca81  mov     rcx, [r14+50h]
0x18000ca85  mov     [r14+48h], rax
0x18000ca89  mov     [rbp+var_48], r12
0x18000ca8d  test    rcx, rcx
0x18000ca90  jz      short loc_18000CA9E
0x18000ca92  mov     rax, [rcx]
0x18000ca95  mov     rax, [rax+10h]
0x18000ca99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca9e  mov     rax, [rbp+var_30]
0x18000caa2  lea     rcx, [rbp+clsid]; this
0x18000caa6  cmp     [rbp+var_38], r12d
0x18000caaa  mov     [r14+50h], rax
0x18000caae  mov     eax, r12d
0x18000cab1  setnz   al
0x18000cab4  mov     [rbp+var_30], r12
0x18000cab8  mov     [r14+70h], eax
0x18000cabc  call    ?Unlock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Unlock(void)
0x18000cac1  jmp     short loc_18000CAF5
0x18000cac3  mov     rcx, [rbp+var_48]
0x18000cac7  test    rcx, rcx
0x18000caca  jz      short loc_18000CADC
0x18000cacc  mov     rax, [rcx]
0x18000cacf  mov     rax, [rax+10h]
0x18000cad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad8  mov     [rbp+var_48], r12
0x18000cadc  mov     rcx, [rbp+var_30]
0x18000cae0  test    rcx, rcx
0x18000cae3  jz      short loc_18000CAF5
0x18000cae5  mov     rax, [rcx]
0x18000cae8  mov     rax, [rax+10h]
0x18000caec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caf1  mov     [rbp+var_30], r12
0x18000caf5  mov     rcx, [rbp+var_40]
0x18000caf9  test    rcx, rcx
0x18000cafc  jz      short loc_18000CB0E
0x18000cafe  mov     rax, [rcx]
0x18000cb01  mov     rax, [rax+10h]
0x18000cb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb0a  mov     [rbp+var_40], r12
0x18000cb0e  mov     edx, esi; unsigned int
0x18000cb10  lea     rcx, qword_180022D58; this
0x18000cb17  call    ?NextAction@CTrackErrState@@QEAAHK@Z; CTrackErrState::NextAction(ulong)
0x18000cb1c  cmp     eax, 2
0x18000cb1f  jnz     short loc_18000CB3E
0x18000cb21  xor     r8d, r8d
0x18000cb24  lea     rcx, ?g_EventLog@@3VCEventLog@@A; CEventLog g_EventLog
0x18000cb2b  mov     edx, 106010Bh
0x18000cb30  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000cb37  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
