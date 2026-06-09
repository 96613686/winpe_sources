# QueryPopupManager

- ea: `0x1800f11e0`
- end: `0x1800f14f9`
- name: `QueryPopupManager`
- size: `793`
- prototype: `__int64 __fastcall(IUnknown *punk, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f0aa0`

## callees

- `0x18002d6f0`
- `0x1800bbf60`
- `0x1800f0068`
- `0x1800f0368`
- `0x1800f11e0`
- `0x180118ee8`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f149d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f149d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1475`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f131a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f131a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f12f7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f13ae`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f13d7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f1438`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f12f7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f13ae`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f13d7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800f1438`
- `api-ms-win-shlwapi-ie-l1-1-0!SHRegGetBoolValueFromHKCUHKLM` at `0x1800f14b9`
- `api-ms-win-shlwapi-ie-l1-1-0!SHRegGetBoolValueFromHKCUHKLM` at `0x1800f14b9`

## pseudocode

```c
__int64 __fastcall QueryPopupManager(IUnknown *punk, __int64 *a2, __int64 a3)
{
  BOOL v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // edx
  HRESULT HTMLDoc2; // edi
  unsigned __int16 *v10; // rsi
  COleAutDll *v11; // rcx
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  void *v16; // [rsp+68h] [rbp-98h] BYREF
  void *v17; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *punka; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v20; // [rsp+88h] [rbp-78h] BYREF
  void *v21; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ModuleName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = 0;
  if ( punk && CoInternetIsFeatureEnabled(FEATURE_WEBOC_POPUPMANAGEMENT, 2u) != 1 )
  {
    v7 = *a2;
    v20 = 0;
    pv = 0;
    v6 = 1;
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, _QWORD, LPVOID *))(v7 + 160))(a2, 0, 0, &pv) < 0 )
      goto LABEL_33;
    v16 = 0;
    HTMLDoc2 = GetHTMLDoc2(punk, &v16);
    if ( HTMLDoc2 >= 0 )
    {
      HTMLDoc2 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **))(*(_QWORD *)v16 + 320LL))(v16, &v20);
      if ( HTMLDoc2 < 0 || (v10 = v20) == 0 || !*v20 )
      {
        v10 = 0;
        HTMLDoc2 = -2147467259;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
      if ( HTMLDoc2 >= 0 )
      {
        v13 = 0;
        v15 = 0;
        ppvOut = 0;
        if ( IUnknown_QueryService(punk, &IID_IInternetSecurityManager, &IID_IInternetSecurityManager, &ppvOut) >= 0
          || (HTMLDoc2 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, &ppvOut),
              HTMLDoc2 >= 0) )
        {
          HTMLDoc2 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, __int64, int *, int, int *, int, int, _DWORD))(*(_QWORD *)ppvOut + 56LL))(
                       ppvOut,
                       v10,
                       6153,
                       &v13,
                       4,
                       &v15,
                       4,
                       1,
                       0);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          if ( HTMLDoc2 >= 0 )
          {
            if ( v13 )
            {
              if ( v13 == 3 )
                v6 = 0;
            }
            else
            {
              punka = 0;
              HTMLDoc2 = IUnknown_QueryService(
                           punk,
                           (const GUID *const)&SID_SContainerDispatch,
                           &IID_IServiceProvider,
                           (void **)&punka);
              if ( HTMLDoc2 >= 0 )
              {
                v17 = 0;
                HTMLDoc2 = IUnknown_QueryService(punka, &IID_IQueryPopupMgr, &IID_IQueryPopupMgr, &v17);
                if ( HTMLDoc2 < 0 )
                {
                  v21 = 0;
                  if ( IUnknown_QueryService(0, (const GUID *const)&SID_SOuterMostXMLHostedCDoc, &IID_IUnknown, &v21) < 0 )
                    v6 = 0;
                  else
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
                }
                else
                {
                  HTMLDoc2 = (*(__int64 (__fastcall **)(void *, LPVOID, __int64, unsigned __int16 *, _DWORD))(*(_QWORD *)v17 + 24LL))(
                               v17,
                               pv,
                               a3,
                               v10,
                               0);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
                  v6 = HTMLDoc2 != 0;
                }
                ((void (__fastcall *)(IUnknown *))punka->lpVtbl->Release)(punka);
              }
            }
          }
        }
      }
    }
    CoTaskMemFree(pv);
    COleAutDll::SysFreeString(v11, v20);
    if ( v6 )
    {
      if ( HTMLDoc2 < 0 )
      {
LABEL_33:
        if ( (int)GetFlashModuleName(ModuleName, v8) >= 0
          && GetModuleHandleW(ModuleName)
          && !SHRegGetBoolValueFromHKCUHKLM(L"Software\\Microsoft\\Internet Explorer\\New Windows", L"BlockControls", 0)
          && !(unsigned int)IsFlashVersionGreaterThan_9_0_16_0() )
        {
          v6 = 0;
        }
      }
    }
  }
  return v6 ? 0x80070005 : 0;
}

```

## disassembly

```asm
0x1800f11e0  push    rbp
0x1800f11e2  push    rbx
0x1800f11e3  push    rsi
0x1800f11e4  push    rdi
0x1800f11e5  push    r12
0x1800f11e7  push    r14
0x1800f11e9  push    r15
0x1800f11eb  lea     rbp, [rsp-1C0h]
0x1800f11f3  sub     rsp, 2C0h
0x1800f11fa  mov     rax, cs:__security_cookie
0x1800f1201  xor     rax, rsp
0x1800f1204  mov     [rbp+1F0h+var_40], rax
0x1800f120b  xor     r12d, r12d
0x1800f120e  mov     r15, r8
0x1800f1211  mov     rdi, rdx
0x1800f1214  mov     r14, rcx
0x1800f1217  mov     ebx, r12d
0x1800f121a  test    rcx, rcx
0x1800f121d  jz      loc_1800F14CF
0x1800f1223  lea     edx, [r12+2]; dwFlags
0x1800f1228  lea     ecx, [rdx+3]; FeatureEntry
0x1800f122b  call    CoInternetIsFeatureEnabled
0x1800f1230  cmp     eax, 1
0x1800f1233  jz      loc_1800F14CF
0x1800f1239  mov     rax, [rdi]
0x1800f123c  lea     r9, [rbp+1F0h+pv]
0x1800f1240  xor     r8d, r8d
0x1800f1243  mov     [rbp+1F0h+var_268], r12
0x1800f1247  xor     edx, edx
0x1800f1249  mov     [rbp+1F0h+pv], r12
0x1800f124d  mov     rcx, rdi
0x1800f1250  lea     ebx, [r12+1]
0x1800f1255  mov     rax, [rax+0A0h]
0x1800f125c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1261  test    eax, eax
0x1800f1263  js      loc_1800F148C
0x1800f1269  lea     rdx, [rsp+2F0h+var_288]; ppvOut
0x1800f126e  mov     [rsp+2F0h+var_288], r12
0x1800f1273  mov     rcx, r14; punk
0x1800f1276  call    GetHTMLDoc2
0x1800f127b  mov     edi, eax
0x1800f127d  test    eax, eax
0x1800f127f  js      loc_1800F1471
0x1800f1285  mov     rcx, [rsp+2F0h+var_288]
0x1800f128a  lea     rdx, [rbp+1F0h+var_268]
0x1800f128e  mov     rax, [rcx]
0x1800f1291  mov     rax, [rax+140h]
0x1800f1298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f129d  mov     edi, eax
0x1800f129f  test    eax, eax
0x1800f12a1  js      short loc_1800F12B2
0x1800f12a3  mov     rsi, [rbp+1F0h+var_268]
0x1800f12a7  test    rsi, rsi
0x1800f12aa  jz      short loc_1800F12B2
0x1800f12ac  cmp     [rsi], r12w
0x1800f12b0  jnz     short loc_1800F12BA
0x1800f12b2  mov     rsi, r12
0x1800f12b5  mov     edi, 80004005h
0x1800f12ba  mov     rcx, [rsp+2F0h+var_288]
0x1800f12bf  mov     rax, [rcx]
0x1800f12c2  mov     rax, [rax+10h]
0x1800f12c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12cb  test    edi, edi
0x1800f12cd  js      loc_1800F1471
0x1800f12d3  lea     rdi, IID_IInternetSecurityManager
0x1800f12da  mov     [rsp+2F0h+var_2A0], r12d
0x1800f12df  mov     r8, rdi; riid
0x1800f12e2  mov     [rsp+2F0h+var_290], r12d
0x1800f12e7  mov     rdx, rdi; guidService
0x1800f12ea  mov     [rsp+2F0h+ppvOut], r12
0x1800f12ef  lea     r9, [rsp+2F0h+ppvOut]; ppvOut
0x1800f12f4  mov     rcx, r14; punk
0x1800f12f7  call    cs:__imp_IUnknown_QueryService
0x1800f12fd  test    eax, eax
0x1800f12ff  jns     short loc_1800F132A
0x1800f1301  lea     rax, [rsp+2F0h+ppvOut]
0x1800f1306  mov     r9, rdi; riid
0x1800f1309  xor     edx, edx; pUnkOuter
0x1800f130b  mov     [rsp+2F0h+ppv], rax; ppv
0x1800f1310  mov     r8d, ebx; dwClsContext
0x1800f1313  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800f131a  call    cs:__imp_CoCreateInstance
0x1800f1320  mov     edi, eax
0x1800f1322  test    eax, eax
0x1800f1324  js      loc_1800F1471
0x1800f132a  mov     rcx, [rsp+2F0h+ppvOut]
0x1800f132f  lea     rdx, [rsp+2F0h+var_290]
0x1800f1334  mov     [rsp+2F0h+var_2B0], r12d
0x1800f1339  lea     r9, [rsp+2F0h+var_2A0]
0x1800f133e  mov     r8d, 4
0x1800f1344  mov     [rsp+2F0h+var_2B8], ebx
0x1800f1348  mov     [rsp+2F0h+var_2C0], r8d
0x1800f134d  mov     rax, [rcx]
0x1800f1350  mov     [rsp+2F0h+var_2C8], rdx
0x1800f1355  mov     rdx, rsi
0x1800f1358  mov     dword ptr [rsp+2F0h+ppv], r8d
0x1800f135d  mov     r8d, 1809h
0x1800f1363  mov     rax, [rax+38h]
0x1800f1367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f136c  mov     rcx, [rsp+2F0h+ppvOut]
0x1800f1371  mov     edi, eax
0x1800f1373  mov     rax, [rcx]
0x1800f1376  mov     rax, [rax+10h]
0x1800f137a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f137f  test    edi, edi
0x1800f1381  js      loc_1800F1471
0x1800f1387  mov     edx, [rsp+2F0h+var_2A0]
0x1800f138b  test    edx, edx
0x1800f138d  jnz     loc_1800F146A
0x1800f1393  lea     r9, [rsp+2F0h+punk]; ppvOut
0x1800f1398  mov     [rsp+2F0h+punk], r12
0x1800f139d  lea     r8, IID_IServiceProvider; riid
0x1800f13a4  mov     rcx, r14; punk
0x1800f13a7  lea     rdx, SID_SContainerDispatch; guidService
0x1800f13ae  call    cs:__imp_IUnknown_QueryService
0x1800f13b4  mov     edi, eax
0x1800f13b6  test    eax, eax
0x1800f13b8  js      loc_1800F1471
0x1800f13be  mov     rcx, [rsp+2F0h+punk]; punk
0x1800f13c3  lea     rdx, IID_IQueryPopupMgr; guidService
0x1800f13ca  mov     r8, rdx; riid
0x1800f13cd  mov     [rsp+2F0h+var_280], r12
0x1800f13d2  lea     r9, [rsp+2F0h+var_280]; ppvOut
0x1800f13d7  call    cs:__imp_IUnknown_QueryService
0x1800f13dd  mov     edi, eax
0x1800f13df  test    eax, eax
0x1800f13e1  js      short loc_1800F1420
0x1800f13e3  mov     rcx, [rsp+2F0h+var_280]
0x1800f13e8  mov     r9, rsi
0x1800f13eb  mov     rdx, [rbp+1F0h+pv]
0x1800f13ef  mov     r8, r15
0x1800f13f2  mov     dword ptr [rsp+2F0h+ppv], r12d
0x1800f13f7  mov     rax, [rcx]
0x1800f13fa  mov     rax, [rax+18h]
0x1800f13fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1403  mov     rcx, [rsp+2F0h+var_280]
0x1800f1408  mov     edi, eax
0x1800f140a  mov     rax, [rcx]
0x1800f140d  mov     rax, [rax+10h]
0x1800f1411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1416  test    edi, edi
0x1800f1418  mov     ebx, r12d
0x1800f141b  setnz   bl
0x1800f141e  jmp     short loc_1800F1457
0x1800f1420  lea     r9, [rbp+1F0h+var_260]; ppvOut
0x1800f1424  mov     [rbp+1F0h+var_260], r12
0x1800f1428  lea     r8, IID_IUnknown; riid
0x1800f142f  xor     ecx, ecx; punk
0x1800f1431  lea     rdx, SID_SOuterMostXMLHostedCDoc; guidService
0x1800f1438  call    cs:__imp_IUnknown_QueryService
0x1800f143e  test    eax, eax
0x1800f1440  js      short loc_1800F1454
0x1800f1442  mov     rcx, [rbp+1F0h+var_260]
0x1800f1446  mov     rax, [rcx]
0x1800f1449  mov     rax, [rax+10h]
0x1800f144d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1452  jmp     short loc_1800F1457
0x1800f1454  mov     ebx, r12d
0x1800f1457  mov     rcx, [rsp+2F0h+punk]
0x1800f145c  mov     rax, [rcx]
0x1800f145f  mov     rax, [rax+10h]
0x1800f1463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1468  jmp     short loc_1800F1471
0x1800f146a  cmp     edx, 3
0x1800f146d  cmovz   ebx, r12d
0x1800f1471  mov     rcx, [rbp+1F0h+pv]; pv
0x1800f1475  call    cs:__imp_CoTaskMemFree
0x1800f147b  mov     rdx, [rbp+1F0h+var_268]; unsigned __int16 *
0x1800f147f  call    ?SysFreeString@COleAutDll@@QEAAXPEAG@Z; COleAutDll::SysFreeString(ushort *)
0x1800f1484  test    ebx, ebx
0x1800f1486  jz      short loc_1800F14CF
0x1800f1488  test    edi, edi
0x1800f148a  jns     short loc_1800F14CF
0x1800f148c  lea     rcx, [rbp+1F0h+ModuleName]; unsigned __int16 *
0x1800f1490  call    ?GetFlashModuleName@@YAJPEAGK@Z; GetFlashModuleName(ushort *,ulong)
0x1800f1495  test    eax, eax
0x1800f1497  js      short loc_1800F14CF
0x1800f1499  lea     rcx, [rbp+1F0h+ModuleName]; lpModuleName
0x1800f149d  call    cs:__imp_GetModuleHandleW
0x1800f14a3  test    rax, rax
0x1800f14a6  jz      short loc_1800F14CF
0x1800f14a8  xor     r8d, r8d; fDefault
0x1800f14ab  lea     rdx, aBlockcontrols; "BlockControls"
0x1800f14b2  lea     rcx, pszKey; "Software\\Microsoft\\Internet Explorer"...
0x1800f14b9  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x1800f14bf  test    eax, eax
0x1800f14c1  jnz     short loc_1800F14CF
0x1800f14c3  call    ?IsFlashVersionGreaterThan_9_0_16_0@@YAHXZ; IsFlashVersionGreaterThan_9_0_16_0(void)
0x1800f14c8  test    eax, eax
0x1800f14ca  jnz     short loc_1800F14CF
0x1800f14cc  mov     ebx, r12d
0x1800f14cf  neg     ebx
0x1800f14d1  sbb     eax, eax
0x1800f14d3  and     eax, 80070005h
0x1800f14d8  mov     rcx, [rbp+1F0h+var_40]
0x1800f14df  xor     rcx, rsp; StackCookie
0x1800f14e2  call    __security_check_cookie
0x1800f14e7  add     rsp, 2C0h
0x1800f14ee  pop     r15
0x1800f14f0  pop     r14
0x1800f14f2  pop     r12
0x1800f14f4  pop     rdi
0x1800f14f5  pop     rsi
0x1800f14f6  pop     rbx
0x1800f14f7  pop     rbp
0x1800f14f8  retn
```
