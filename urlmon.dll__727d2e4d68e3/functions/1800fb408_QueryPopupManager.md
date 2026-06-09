# QueryPopupManager

- ea: `0x1800fb408`
- end: `0x1800fb752`
- name: `QueryPopupManager`
- size: `842`
- prototype: `__int64 __fastcall(IUnknown *punk)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800fac90`

## callees

- `0x180033980`
- `0x1800c40f0`
- `0x1800fa1ec`
- `0x1800fa514`
- `0x1800fb408`
- `0x1801258d8`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800fb6e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800fb6e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb6bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb6bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fb548`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fb548`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb51f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb5e2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb611`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb678`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb51f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb5e2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb611`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb678`
- `api-ms-win-shlwapi-ie-l1-1-0!SHRegGetBoolValueFromHKCUHKLM` at `0x1800fb70b`
- `api-ms-win-shlwapi-ie-l1-1-0!SHRegGetBoolValueFromHKCUHKLM` at `0x1800fb70b`

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
0x1800fb408  push    rbp
0x1800fb40a  push    rbx
0x1800fb40b  push    rsi
0x1800fb40c  push    rdi
0x1800fb40d  push    r12
0x1800fb40f  push    r14
0x1800fb411  push    r15
0x1800fb413  lea     rbp, [rsp-1C0h]
0x1800fb41b  sub     rsp, 2C0h
0x1800fb422  mov     rax, cs:__security_cookie
0x1800fb429  xor     rax, rsp
0x1800fb42c  mov     [rbp+1F0h+var_40], rax
0x1800fb433  xor     r12d, r12d
0x1800fb436  mov     r15, r8
0x1800fb439  mov     rdi, rdx
0x1800fb43c  mov     r14, rcx
0x1800fb43f  mov     ebx, r12d
0x1800fb442  test    rcx, rcx
0x1800fb445  jz      loc_1800FB727
0x1800fb44b  lea     edx, [r12+2]; dwFlags
0x1800fb450  lea     ecx, [rdx+3]; FeatureEntry
0x1800fb453  call    CoInternetIsFeatureEnabled
0x1800fb458  cmp     eax, 1
0x1800fb45b  jz      loc_1800FB727
0x1800fb461  mov     rax, [rdi]
0x1800fb464  lea     r9, [rbp+1F0h+pv]
0x1800fb468  xor     r8d, r8d
0x1800fb46b  mov     [rbp+1F0h+var_268], r12
0x1800fb46f  xor     edx, edx
0x1800fb471  mov     [rbp+1F0h+pv], r12
0x1800fb475  mov     rcx, rdi
0x1800fb478  lea     ebx, [r12+1]
0x1800fb47d  mov     rax, [rax+0A0h]
0x1800fb484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb489  test    eax, eax
0x1800fb48b  js      loc_1800FB6D8
0x1800fb491  lea     rdx, [rsp+2F0h+var_288]; ppvOut
0x1800fb496  mov     [rsp+2F0h+var_288], r12
0x1800fb49b  mov     rcx, r14; punk
0x1800fb49e  call    GetHTMLDoc2
0x1800fb4a3  mov     edi, eax
0x1800fb4a5  test    eax, eax
0x1800fb4a7  js      loc_1800FB6B7
0x1800fb4ad  mov     rcx, [rsp+2F0h+var_288]
0x1800fb4b2  lea     rdx, [rbp+1F0h+var_268]
0x1800fb4b6  mov     rax, [rcx]
0x1800fb4b9  mov     rax, [rax+140h]
0x1800fb4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb4c5  mov     edi, eax
0x1800fb4c7  test    eax, eax
0x1800fb4c9  js      short loc_1800FB4DA
0x1800fb4cb  mov     rsi, [rbp+1F0h+var_268]
0x1800fb4cf  test    rsi, rsi
0x1800fb4d2  jz      short loc_1800FB4DA
0x1800fb4d4  cmp     [rsi], r12w
0x1800fb4d8  jnz     short loc_1800FB4E2
0x1800fb4da  mov     rsi, r12
0x1800fb4dd  mov     edi, 80004005h
0x1800fb4e2  mov     rcx, [rsp+2F0h+var_288]
0x1800fb4e7  mov     rax, [rcx]
0x1800fb4ea  mov     rax, [rax+10h]
0x1800fb4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb4f3  test    edi, edi
0x1800fb4f5  js      loc_1800FB6B7
0x1800fb4fb  lea     rdi, IID_IInternetSecurityManager
0x1800fb502  mov     [rsp+2F0h+var_2A0], r12d
0x1800fb507  mov     r8, rdi; riid
0x1800fb50a  mov     [rsp+2F0h+var_290], r12d
0x1800fb50f  mov     rdx, rdi; guidService
0x1800fb512  mov     [rsp+2F0h+ppvOut], r12
0x1800fb517  lea     r9, [rsp+2F0h+ppvOut]; ppvOut
0x1800fb51c  mov     rcx, r14; punk
0x1800fb51f  call    cs:__imp_IUnknown_QueryService
0x1800fb526  nop     dword ptr [rax+rax+00h]
0x1800fb52b  test    eax, eax
0x1800fb52d  jns     short loc_1800FB55E
0x1800fb52f  lea     rax, [rsp+2F0h+ppvOut]
0x1800fb534  mov     r9, rdi; riid
0x1800fb537  xor     edx, edx; pUnkOuter
0x1800fb539  mov     [rsp+2F0h+ppv], rax; ppv
0x1800fb53e  mov     r8d, ebx; dwClsContext
0x1800fb541  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800fb548  call    cs:__imp_CoCreateInstance
0x1800fb54f  nop     dword ptr [rax+rax+00h]
0x1800fb554  mov     edi, eax
0x1800fb556  test    eax, eax
0x1800fb558  js      loc_1800FB6B7
0x1800fb55e  mov     rcx, [rsp+2F0h+ppvOut]
0x1800fb563  lea     rdx, [rsp+2F0h+var_290]
0x1800fb568  mov     [rsp+2F0h+var_2B0], r12d
0x1800fb56d  lea     r9, [rsp+2F0h+var_2A0]
0x1800fb572  mov     r8d, 4
0x1800fb578  mov     [rsp+2F0h+var_2B8], ebx
0x1800fb57c  mov     [rsp+2F0h+var_2C0], r8d
0x1800fb581  mov     rax, [rcx]
0x1800fb584  mov     [rsp+2F0h+var_2C8], rdx
0x1800fb589  mov     rdx, rsi
0x1800fb58c  mov     dword ptr [rsp+2F0h+ppv], r8d
0x1800fb591  mov     r8d, 1809h
0x1800fb597  mov     rax, [rax+38h]
0x1800fb59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb5a0  mov     rcx, [rsp+2F0h+ppvOut]
0x1800fb5a5  mov     edi, eax
0x1800fb5a7  mov     rax, [rcx]
0x1800fb5aa  mov     rax, [rax+10h]
0x1800fb5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb5b3  test    edi, edi
0x1800fb5b5  js      loc_1800FB6B7
0x1800fb5bb  mov     edx, [rsp+2F0h+var_2A0]
0x1800fb5bf  test    edx, edx
0x1800fb5c1  jnz     loc_1800FB6B0
0x1800fb5c7  lea     r9, [rsp+2F0h+punk]; ppvOut
0x1800fb5cc  mov     [rsp+2F0h+punk], r12
0x1800fb5d1  lea     r8, IID_IServiceProvider; riid
0x1800fb5d8  mov     rcx, r14; punk
0x1800fb5db  lea     rdx, SID_SContainerDispatch; guidService
0x1800fb5e2  call    cs:__imp_IUnknown_QueryService
0x1800fb5e9  nop     dword ptr [rax+rax+00h]
0x1800fb5ee  mov     edi, eax
0x1800fb5f0  test    eax, eax
0x1800fb5f2  js      loc_1800FB6B7
0x1800fb5f8  mov     rcx, [rsp+2F0h+punk]; punk
0x1800fb5fd  lea     rdx, IID_IQueryPopupMgr; guidService
0x1800fb604  mov     r8, rdx; riid
0x1800fb607  mov     [rsp+2F0h+var_280], r12
0x1800fb60c  lea     r9, [rsp+2F0h+var_280]; ppvOut
0x1800fb611  call    cs:__imp_IUnknown_QueryService
0x1800fb618  nop     dword ptr [rax+rax+00h]
0x1800fb61d  mov     edi, eax
0x1800fb61f  test    eax, eax
0x1800fb621  js      short loc_1800FB660
0x1800fb623  mov     rcx, [rsp+2F0h+var_280]
0x1800fb628  mov     r9, rsi
0x1800fb62b  mov     rdx, [rbp+1F0h+pv]
0x1800fb62f  mov     r8, r15
0x1800fb632  mov     dword ptr [rsp+2F0h+ppv], r12d
0x1800fb637  mov     rax, [rcx]
0x1800fb63a  mov     rax, [rax+18h]
0x1800fb63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb643  mov     rcx, [rsp+2F0h+var_280]
0x1800fb648  mov     edi, eax
0x1800fb64a  mov     rax, [rcx]
0x1800fb64d  mov     rax, [rax+10h]
0x1800fb651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb656  test    edi, edi
0x1800fb658  mov     ebx, r12d
0x1800fb65b  setnz   bl
0x1800fb65e  jmp     short loc_1800FB69D
0x1800fb660  lea     r9, [rbp+1F0h+var_260]; ppvOut
0x1800fb664  mov     [rbp+1F0h+var_260], r12
0x1800fb668  lea     r8, IID_IUnknown; riid
0x1800fb66f  xor     ecx, ecx; punk
0x1800fb671  lea     rdx, SID_SOuterMostXMLHostedCDoc; guidService
0x1800fb678  call    cs:__imp_IUnknown_QueryService
0x1800fb67f  nop     dword ptr [rax+rax+00h]
0x1800fb684  test    eax, eax
0x1800fb686  js      short loc_1800FB69A
0x1800fb688  mov     rcx, [rbp+1F0h+var_260]
0x1800fb68c  mov     rax, [rcx]
0x1800fb68f  mov     rax, [rax+10h]
0x1800fb693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb698  jmp     short loc_1800FB69D
0x1800fb69a  mov     ebx, r12d
0x1800fb69d  mov     rcx, [rsp+2F0h+punk]
0x1800fb6a2  mov     rax, [rcx]
0x1800fb6a5  mov     rax, [rax+10h]
0x1800fb6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb6ae  jmp     short loc_1800FB6B7
0x1800fb6b0  cmp     edx, 3
0x1800fb6b3  cmovz   ebx, r12d
0x1800fb6b7  mov     rcx, [rbp+1F0h+pv]; pv
0x1800fb6bb  call    cs:__imp_CoTaskMemFree
0x1800fb6c2  nop     dword ptr [rax+rax+00h]
0x1800fb6c7  mov     rdx, [rbp+1F0h+var_268]; unsigned __int16 *
0x1800fb6cb  call    ?SysFreeString@COleAutDll@@QEAAXPEAG@Z; COleAutDll::SysFreeString(ushort *)
0x1800fb6d0  test    ebx, ebx
0x1800fb6d2  jz      short loc_1800FB727
0x1800fb6d4  test    edi, edi
0x1800fb6d6  jns     short loc_1800FB727
0x1800fb6d8  lea     rcx, [rbp+1F0h+ModuleName]; unsigned __int16 *
0x1800fb6dc  call    ?GetFlashModuleName@@YAJPEAGK@Z; GetFlashModuleName(ushort *,ulong)
0x1800fb6e1  test    eax, eax
0x1800fb6e3  js      short loc_1800FB727
0x1800fb6e5  lea     rcx, [rbp+1F0h+ModuleName]; lpModuleName
0x1800fb6e9  call    cs:__imp_GetModuleHandleW
0x1800fb6f0  nop     dword ptr [rax+rax+00h]
0x1800fb6f5  test    rax, rax
0x1800fb6f8  jz      short loc_1800FB727
0x1800fb6fa  xor     r8d, r8d; fDefault
0x1800fb6fd  lea     rdx, aBlockcontrols; "BlockControls"
0x1800fb704  lea     rcx, pszKey; "Software\\Microsoft\\Internet Explorer"...
0x1800fb70b  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x1800fb712  nop     dword ptr [rax+rax+00h]
0x1800fb717  test    eax, eax
0x1800fb719  jnz     short loc_1800FB727
0x1800fb71b  call    ?IsFlashVersionGreaterThan_9_0_16_0@@YAHXZ; IsFlashVersionGreaterThan_9_0_16_0(void)
0x1800fb720  test    eax, eax
0x1800fb722  jnz     short loc_1800FB727
0x1800fb724  mov     ebx, r12d
0x1800fb727  neg     ebx
0x1800fb729  sbb     eax, eax
0x1800fb72b  and     eax, 80070005h
0x1800fb730  mov     rcx, [rbp+1F0h+var_40]
0x1800fb737  xor     rcx, rsp; StackCookie
0x1800fb73a  call    __security_check_cookie
0x1800fb73f  add     rsp, 2C0h
0x1800fb746  pop     r15
0x1800fb748  pop     r14
0x1800fb74a  pop     r12
0x1800fb74c  pop     rdi
0x1800fb74d  pop     rsi
0x1800fb74e  pop     rbx
0x1800fb74f  pop     rbp
0x1800fb750  retn
```
