# CopyToCache(IUpdateCollection *,int)

- ea: `0x140005c70`
- end: `0x14000654d`
- name: `?CopyToCache@@YAJPEAUIUpdateCollection@@H@Z`
- size: `2269`
- prototype: `__int64 __fastcall(struct IUpdateCollection *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140005c70`
- `0x140006a44`
- `0x1400075b0`

## callees

- `0x1400044e0`
- `0x140005c70`
- `0x14000c124`
- `0x14000e280`
- `0x14000ec58`
- `0x14000f240`
- `0x140013490`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000651b`
- `KERNEL32!LocalFree` at `0x14000651b`
- `msvcrt!wcsrchr` at `0x140005f2e`
- `msvcrt!wcsrchr` at `0x140005f2e`
- `OLEAUT32!__imp_SysAllocString` at `0x140005f9f`
- `OLEAUT32!__imp_SysAllocString` at `0x140005f9f`
- `OLEAUT32!__imp_SysFreeString` at `0x140005ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x14000600a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000618e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400063e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400063f6`
- `OLEAUT32!__imp_SysFreeString` at `0x140006406`
- `OLEAUT32!__imp_SysFreeString` at `0x140005ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x14000600a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000618e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400063e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400063f6`
- `OLEAUT32!__imp_SysFreeString` at `0x140006406`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140005e5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140005e5c`

## string_xrefs

- `0x140005cfb`: `Failed to get count of updates`
- `0x140005cee`: `CopyToCache`
- `0x140005f09`: `CopyToCache`
- `0x1400060b0`: `CopyToCache`
- `0x14000617d`: `CopyToCache`
- `0x140006210`: `CopyToCache`
- `0x140006228`: `CopyToCache`
- `0x140006271`: `CopyToCache`
- `0x1400062b9`: `CopyToCache`
- `0x14000630a`: `CopyToCache`
- `0x14000634c`: `CopyToCache`
- `0x140006507`: `CopyToCache`
- `0x1400063c2`: `Failed to get update out of collection`
- `0x1400063b4`: `Failed to get update title`
- `0x1400063a6`: `Failed to get update property BundledUpdates`
- `0x140005dd1`: `Found a bundle of updates %S; recursing`
- `0x1400061f3`: `Failed to recursively call CopyToCache`
- `0x140006398`: `Failed to get IUpdate2 interface`
- `0x14000637c`: `Failed to get download contents from update`
- `0x14000623e`: `Failed to build update payload full path`
- `0x140005f8f`: `Ready to copy %S to WU cache`
- `0x14000621c`: `Failed to allocate payload full path`
- `0x140006340`: `IUpdate18 interface doesn't exist. Skipping content applicability check.`
- `0x14000632f`: `Failed to get IUpdate18 interface. Skipping content applicability check. Error code 0X%x`
- `0x1400062fe`: `Failed to display no-update message box`
- `0x14000631b`: `Update is not applicable. Error code 0X%x`
- `0x1400062cb`: `Baseline update required. Error code 0X%x`
- `0x1400060ec`: `Failed to copy to cache, error code 0X%x`
- `0x14000635d`: `Failed to copy to cache, error code 0X%x`

## pseudocode

```c
__int64 __fastcall CopyToCache(struct IUpdateCollection *a1, int a2)
{
  struct IUpdateCollectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_Count)(IUpdateCollection *, LONG *); // rax
  OLECHAR *v6; // rdi
  HRESULT v7; // ebx
  unsigned int i; // r14d
  int v9; // edx
  unsigned int v10; // esi
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  __int64 v13; // r8
  int v14; // eax
  const char *v15; // r8
  __int64 v16; // rdx
  HLOCAL v17; // rdi
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  struct IUpdateCollection *v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR psz[264]; // [rsp+90h] [rbp-70h] BYREF

  lpVtbl = a1->lpVtbl;
  v23 = 0;
  v19 = 0;
  v26 = 0;
  get_Count = lpVtbl->get_Count;
  v6 = 0;
  v31 = 0;
  v21 = 0;
  ppv = 0;
  v25 = 0;
  v28 = 0;
  bstrString = 0;
  Str = 0;
  v7 = ((__int64 (__fastcall *)(struct IUpdateCollection *, int *))get_Count)(a1, &v23);
  if ( v7 < 0 )
  {
    WusaLogDebugEventA(L"CopyToCache", 330, "Failed to get count of updates");
    goto LABEL_82;
  }
  for ( i = 0; (int)i < v23; ++i )
  {
    v7 = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, __int64 *))a1->lpVtbl->get_Item)(a1, i, &v19);
    if ( v7 < 0 )
    {
      WusaLogDebugEventA(L"CopyToCache", 336, "Failed to get update out of collection");
      goto LABEL_81;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 56LL))(v19, &bstrString);
    if ( v7 < 0 )
    {
      WusaLogDebugEventA(L"CopyToCache", 339, "Failed to get update title");
      goto LABEL_81;
    }
    if ( dword_140020188 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 376LL))(v19);
      if ( v7 < 0 )
      {
        WusaLogDebugEventA(L"CopyToCache", 344, "Failed to accept EULA");
        goto LABEL_81;
      }
    }
    v7 = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection **))(*(_QWORD *)v19 + 72LL))(v19, &v21);
    if ( v7 < 0 )
    {
      WusaLogDebugEventA(L"CopyToCache", 354, "Failed to get update property BundledUpdates");
      goto LABEL_81;
    }
    v29 = 0;
    ((void (__fastcall *)(struct IUpdateCollection *, int *))v21->lpVtbl->get_Count)(v21, &v29);
    if ( v29 <= 0 )
    {
      v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
             v19,
             &GUID_144fe9b0_d23d_4a8b_8634_fb4457533b7a,
             &v26);
      if ( v7 < 0 )
      {
        WusaLogDebugEventA(L"CopyToCache", 378, "Failed to get IUpdate2 interface");
        goto LABEL_81;
      }
      v7 = CoCreateInstance(
             &GUID_72c97d74_7c3b_40ae_b77d_abdb22eba6fb,
             0,
             1u,
             &GUID_eff90582_2ddc_480f_a06d_60f3fbc362c3,
             &ppv);
      if ( v7 < 0 )
      {
        WusaLogDebugEventA(L"CopyToCache", 382, "Failed to get IStringCollection interface");
        goto LABEL_81;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 408LL))(v19, &v25);
      if ( v7 < 0 )
      {
        WusaLogDebugEventA(L"CopyToCache", 385, "Failed to get download contents from update");
        goto LABEL_81;
      }
      v22 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 72LL))(v25, &v22);
      if ( v7 < 0 )
      {
        WusaLogDebugEventA(L"CopyToCache", 390, "Failed to get download count");
        goto LABEL_81;
      }
      v10 = 0;
      if ( v22 > 0 )
      {
        while ( 1 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 56LL))(v25, v10, &v28);
          if ( v7 < 0 )
            break;
          v7 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v28 + 56LL))(v28, &Str);
          if ( v7 < 0 )
          {
            WusaLogDebugEventA(L"CopyToCache", 398, "Failed to get download URL");
            goto LABEL_81;
          }
          WusaLogDebugEventA(L"CopyToCache", 399, "Download URL: %S", Str);
          v11 = wcsrchr(Str, 0x2Fu);
          if ( !v11 )
          {
            v7 = -2147467259;
            WusaLogDebugEventA(L"CopyToCache", 406, "Can't find file name from url");
            goto LABEL_81;
          }
          v12 = v11 + 1;
          WusaLogDebugEventA(L"CopyToCache", 411, "Download file: %S", v11 + 1);
          v7 = StringCchPrintfW(psz, 0x104u, L"%ls\\%ls", TargetPath, v12);
          if ( v7 < 0 )
          {
            WusaLogDebugEventA(L"CopyToCache", 416, "Failed to build update payload full path");
            goto LABEL_81;
          }
          WusaLogDebugEventA(L"CopyToCache", 418, "Ready to copy %S to WU cache", psz);
          v6 = SysAllocString(psz);
          if ( !v6 )
          {
            WusaLogDebugEventA(L"CopyToCache", 421, "Failed to allocate payload full path");
            v7 = -2147024882;
            goto LABEL_82;
          }
          LODWORD(hMem) = 0;
          v7 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, HLOCAL *))(*(_QWORD *)ppv + 96LL))(ppv, v6, &hMem);
          if ( v7 < 0 )
          {
            WusaLogDebugEventA(L"CopyToCache", 425, "Failed to add file to string collection");
            goto LABEL_82;
          }
          if ( v28 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            v28 = 0;
          }
          if ( Str )
          {
            SysFreeString(Str);
            Str = 0;
          }
          SysFreeString(v6);
          if ( (int)++v10 >= v22 )
            goto LABEL_31;
        }
        WusaLogDebugEventA(L"CopyToCache", 395, "Failed to get download contents from the collection");
LABEL_81:
        v6 = 0;
        break;
      }
LABEL_31:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl'::`2'::impl) )
      {
        if ( a2 )
        {
          v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
                  v19,
                  &GUID_08d5fa75_016a_42a5_a9c5_726fc8a0154c,
                  &v31);
          v7 = v14;
          if ( v14 == -2147467262 )
          {
            WusaLogDebugEventA(
              L"CopyToCache",
              444,
              "IUpdate18 interface doesn't exist. Skipping content applicability check.");
            v7 = 0;
            goto LABEL_81;
          }
          if ( v14 < 0 )
          {
            v15 = "Failed to get IUpdate18 interface. Skipping content applicability check. Error code 0X%x";
            v16 = 447;
            goto LABEL_39;
          }
          v14 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v31 + 216LL))(v31, ppv);
          v7 = v14;
          if ( v14 == -1047526399 )
          {
            if ( (int)WusaMessageBox(0xEA64u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0) < 0 )
              WusaLogDebugEventA(L"CopyToCache", 455, "Failed to display no-update message box");
            v7 = -2145124329;
            WusaLogDebugEventA(L"CopyToCache", 459, "Update is not applicable. Error code 0X%x", 2149842967LL);
            goto LABEL_81;
          }
          if ( v14 == -2146498504 )
          {
            if ( (int)WusaMessageBox(0xEA7Fu, 0xEA60u, 1, (PCWSTR)0xFFFE, 0) < 0 )
              WusaLogDebugEventA(L"CopyToCache", 465, "Failed to display baseline required message box");
            WusaLogDebugEventA(L"CopyToCache", 468, "Baseline update required. Error code 0X%x", 2148468792LL);
            goto LABEL_81;
          }
          if ( v14 < 0 )
          {
            v15 = "Failed to evaluate content applicability. Error code 0X%x";
            v16 = 471;
LABEL_39:
            WusaLogDebugEventA(L"CopyToCache", v16, v15, (unsigned int)v14);
            goto LABEL_81;
          }
        }
        else
        {
          WusaPostMessage(0x401u, 0, v13);
          v14 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v26 + 440LL))(v26, ppv);
          v7 = v14;
          if ( v14 < 0 )
          {
            v15 = "Failed to copy to cache, error code 0X%x";
            v16 = 479;
            goto LABEL_39;
          }
        }
      }
      else
      {
        WusaPostMessage(0x401u, 0, v13);
        v14 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v26 + 440LL))(v26, ppv);
        v7 = v14;
        if ( v14 < 0 )
        {
          v15 = "Failed to copy to cache, error code 0X%x";
          v16 = 488;
          goto LABEL_39;
        }
      }
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
      v6 = 0;
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v25 = 0;
      }
    }
    else
    {
      WusaLogDebugEventA(L"CopyToCache", 362, "Found a bundle of updates %S; recursing", bstrString);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl'::`2'::impl) )
        v9 = a2;
      else
        v9 = 0;
      v7 = CopyToCache(v21, v9);
      if ( v7 < 0 )
      {
        WusaLogDebugEventA(L"CopyToCache", 373, "Failed to recursively call CopyToCache");
        goto LABEL_81;
      }
      v6 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( v21 )
    {
      ((void (__fastcall *)(struct IUpdateCollection *))v21->lpVtbl->Release)(v21);
      v21 = 0;
    }
  }
LABEL_82:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v6 )
    SysFreeString(v6);
  if ( Str )
  {
    SysFreeString(Str);
    Str = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl'::`2'::impl)
    && v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v21 )
  {
    ((void (__fastcall *)(struct IUpdateCollection *))v21->lpVtbl->Release)(v21);
    v21 = 0;
  }
  if ( v7 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v7, (unsigned __int16 **)&hMem);
    v17 = hMem;
    WusaLogDebugEventA(L"CopyToCache", 519, "Exit with error code 0X%x (%ls)", v7, (const wchar_t *)hMem);
    if ( v17 )
      LocalFree(v17);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140005c70  mov     [rsp-8+arg_10], rbx
0x140005c75  push    rbp
0x140005c76  push    rsi
0x140005c77  push    rdi
0x140005c78  push    r12
0x140005c7a  push    r13
0x140005c7c  push    r14
0x140005c7e  push    r15
0x140005c80  lea     rbp, [rsp-1B0h]
0x140005c88  sub     rsp, 2B0h
0x140005c8f  mov     rax, cs:__security_cookie
0x140005c96  xor     rax, rsp
0x140005c99  mov     [rbp+1E0h+var_40], rax
0x140005ca0  mov     rax, [rcx]
0x140005ca3  xor     r13d, r13d
0x140005ca6  mov     r12d, edx
0x140005ca9  mov     [rsp+2E0h+var_294], r13d
0x140005cae  lea     rdx, [rsp+2E0h+var_294]
0x140005cb3  mov     [rsp+2E0h+var_2B0], r13
0x140005cb8  mov     r15, rcx
0x140005cbb  mov     [rsp+2E0h+var_280], r13
0x140005cc0  mov     rax, [rax+50h]
0x140005cc4  mov     edi, r13d
0x140005cc7  mov     [rbp+1E0h+var_258], r13
0x140005ccb  mov     [rsp+2E0h+var_2A0], r13
0x140005cd0  mov     [rsp+2E0h+var_2A8], r13
0x140005cd5  mov     [rsp+2E0h+var_288], r13
0x140005cda  mov     [rsp+2E0h+var_270], r13
0x140005cdf  mov     [rsp+2E0h+bstrString], r13
0x140005ce4  mov     [rsp+2E0h+Str], r13
0x140005ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cee  lea     rsi, aCopytocache; "CopyToCache"
0x140005cf5  mov     ebx, eax
0x140005cf7  test    eax, eax
0x140005cf9  jns     short loc_140005D14
0x140005cfb  lea     r8, aFailedToGetCou; "Failed to get count of updates"
0x140005d02  mov     edx, 14Ah
0x140005d07  mov     rcx, rsi
0x140005d0a  call    WusaLogDebugEventA
0x140005d0f  jmp     loc_1400063D9
0x140005d14  mov     r14d, r13d
0x140005d17  cmp     [rsp+2E0h+var_294], r13d
0x140005d1c  jle     loc_1400063D9
0x140005d22  mov     rax, [r15]
0x140005d25  lea     r8, [rsp+2E0h+var_2B0]
0x140005d2a  mov     edx, r14d
0x140005d2d  mov     rcx, r15
0x140005d30  mov     rax, [rax+38h]
0x140005d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d39  mov     ebx, eax
0x140005d3b  test    eax, eax
0x140005d3d  js      loc_1400063C2
0x140005d43  mov     rcx, [rsp+2E0h+var_2B0]
0x140005d48  lea     rdx, [rsp+2E0h+bstrString]
0x140005d4d  mov     rax, [rcx]
0x140005d50  mov     rax, [rax+38h]
0x140005d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d59  mov     ebx, eax
0x140005d5b  test    eax, eax
0x140005d5d  js      loc_1400063B4
0x140005d63  cmp     cs:dword_140020188, r13d
0x140005d6a  jz      short loc_140005D8A
0x140005d6c  mov     rcx, [rsp+2E0h+var_2B0]
0x140005d71  mov     rax, [rcx]
0x140005d74  mov     rax, [rax+178h]
0x140005d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d80  mov     ebx, eax
0x140005d82  test    eax, eax
0x140005d84  js      loc_1400061E2
0x140005d8a  mov     rcx, [rsp+2E0h+var_2B0]
0x140005d8f  lea     rdx, [rsp+2E0h+var_2A0]
0x140005d94  mov     rax, [rcx]
0x140005d97  mov     rax, [rax+48h]
0x140005d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005da0  mov     ebx, eax
0x140005da2  test    eax, eax
0x140005da4  js      loc_1400063A6
0x140005daa  mov     rcx, [rsp+2E0h+var_2A0]
0x140005daf  lea     rdx, [rsp+2E0h+var_268]
0x140005db4  mov     [rsp+2E0h+var_268], r13d
0x140005db9  mov     rax, [rcx]
0x140005dbc  mov     rax, [rax+50h]
0x140005dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005dc5  cmp     [rsp+2E0h+var_268], r13d
0x140005dca  jle     short loc_140005E18
0x140005dcc  mov     r9, [rsp+2E0h+bstrString]
0x140005dd1  lea     r8, aFoundABundleOf; "Found a bundle of updates %S; recursing"
0x140005dd8  mov     edx, 16Ah
0x140005ddd  mov     rcx, rsi
0x140005de0  call    WusaLogDebugEventA
0x140005de5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU> `wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl(void)'::`2'::impl
0x140005dec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(void)
0x140005df1  mov     rcx, [rsp+2E0h+var_2A0]; struct IUpdateCollection *
0x140005df6  test    al, al
0x140005df8  jz      short loc_140005DFF
0x140005dfa  mov     edx, r12d
0x140005dfd  jmp     short loc_140005E01
0x140005dff  xor     edx, edx; int
0x140005e01  call    ?CopyToCache@@YAJPEAUIUpdateCollection@@H@Z; CopyToCache(IUpdateCollection *,int)
0x140005e06  mov     ebx, eax
0x140005e08  test    eax, eax
0x140005e0a  js      loc_1400061F3
0x140005e10  mov     rdi, r13
0x140005e13  jmp     loc_140006184
0x140005e18  mov     rcx, [rsp+2E0h+var_2B0]
0x140005e1d  lea     r8, [rsp+2E0h+var_280]
0x140005e22  lea     rdx, _GUID_144fe9b0_d23d_4a8b_8634_fb4457533b7a
0x140005e29  mov     rax, [rcx]
0x140005e2c  mov     rax, [rax]
0x140005e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e34  mov     ebx, eax
0x140005e36  test    eax, eax
0x140005e38  js      loc_140006398
0x140005e3e  xor     edx, edx; pUnkOuter
0x140005e40  lea     rax, [rsp+2E0h+var_2A8]
0x140005e45  lea     r9, _GUID_eff90582_2ddc_480f_a06d_60f3fbc362c3; riid
0x140005e4c  mov     [rsp+2E0h+ppv], rax; ppv
0x140005e51  lea     rcx, _GUID_72c97d74_7c3b_40ae_b77d_abdb22eba6fb; rclsid
0x140005e58  lea     r8d, [rdx+1]; dwClsContext
0x140005e5c  call    cs:__imp_CoCreateInstance
0x140005e62  mov     ebx, eax
0x140005e64  test    eax, eax
0x140005e66  js      loc_14000638A
0x140005e6c  mov     rcx, [rsp+2E0h+var_2B0]
0x140005e71  lea     rdx, [rsp+2E0h+var_288]
0x140005e76  mov     rax, [rcx]
0x140005e79  mov     rax, [rax+198h]
0x140005e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e85  mov     ebx, eax
0x140005e87  test    eax, eax
0x140005e89  js      loc_14000637C
0x140005e8f  mov     rcx, [rsp+2E0h+var_288]
0x140005e94  lea     rdx, [rsp+2E0h+var_298]
0x140005e99  mov     [rsp+2E0h+var_298], r13d
0x140005e9e  mov     rax, [rcx]
0x140005ea1  mov     rax, [rax+48h]
0x140005ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eaa  mov     ebx, eax
0x140005eac  test    eax, eax
0x140005eae  js      loc_14000636E
0x140005eb4  mov     esi, r13d
0x140005eb7  cmp     [rsp+2E0h+var_298], r13d
0x140005ebc  jle     loc_14000601C
0x140005ec2  mov     rcx, [rsp+2E0h+var_288]
0x140005ec7  lea     r8, [rsp+2E0h+var_270]
0x140005ecc  mov     edx, esi
0x140005ece  mov     rax, [rcx]
0x140005ed1  mov     rax, [rax+38h]
0x140005ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eda  mov     ebx, eax
0x140005edc  test    eax, eax
0x140005ede  js      loc_14000627D
0x140005ee4  mov     rcx, [rsp+2E0h+var_270]
0x140005ee9  lea     rdx, [rsp+2E0h+Str]
0x140005eee  mov     rax, [rcx]
0x140005ef1  mov     rax, [rax+38h]
0x140005ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005efa  mov     ebx, eax
0x140005efc  test    eax, eax
0x140005efe  js      loc_140006265
0x140005f04  mov     r9, [rsp+2E0h+Str]
0x140005f09  lea     rdi, aCopytocache; "CopyToCache"
0x140005f10  mov     rcx, rdi
0x140005f13  lea     r8, aDownloadUrlS; "Download URL: %S"
0x140005f1a  mov     edx, 18Fh
0x140005f1f  call    WusaLogDebugEventA
0x140005f24  mov     rcx, [rsp+2E0h+Str]; Str
0x140005f29  mov     edx, 2Fh ; '/'; Ch
0x140005f2e  call    cs:__imp_wcsrchr
0x140005f34  mov     rcx, rdi
0x140005f37  test    rax, rax
0x140005f3a  jz      loc_14000624F
0x140005f40  lea     rbx, [rax+2]
0x140005f44  mov     edx, 19Bh
0x140005f49  mov     r9, rbx
0x140005f4c  lea     r8, aDownloadFileS; "Download file: %S"
0x140005f53  call    WusaLogDebugEventA
0x140005f58  mov     r9, cs:TargetPath
0x140005f5f  lea     r8, aLsLs; "%ls\\%ls"
0x140005f66  mov     edx, 104h; unsigned __int64
0x140005f6b  mov     [rsp+2E0h+ppv], rbx
0x140005f70  lea     rcx, [rbp+1E0h+psz]; unsigned __int16 *
0x140005f74  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005f79  mov     ebx, eax
0x140005f7b  mov     rcx, rdi
0x140005f7e  test    eax, eax
0x140005f80  js      loc_14000623E
0x140005f86  lea     r9, [rbp+1E0h+psz]
0x140005f8a  mov     edx, 1A2h
0x140005f8f  lea     r8, aReadyToCopySTo; "Ready to copy %S to WU cache"
0x140005f96  call    WusaLogDebugEventA
0x140005f9b  lea     rcx, [rbp+1E0h+psz]; psz
0x140005f9f  call    cs:__imp_SysAllocString
0x140005fa5  mov     rdi, rax
0x140005fa8  test    rax, rax
0x140005fab  jz      loc_14000621C
0x140005fb1  mov     rcx, [rsp+2E0h+var_2A8]
0x140005fb6  lea     r8, [rbp+1E0h+hMem]
0x140005fba  mov     dword ptr [rbp+1E0h+hMem], r13d
0x140005fbe  mov     rdx, [rcx]
0x140005fc1  mov     rax, [rdx+60h]
0x140005fc5  mov     rdx, rdi
0x140005fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fcd  mov     ebx, eax
0x140005fcf  test    eax, eax
0x140005fd1  js      loc_140006204
0x140005fd7  mov     rcx, [rsp+2E0h+var_270]
0x140005fdc  test    rcx, rcx
0x140005fdf  jz      short loc_140005FF2
0x140005fe1  mov     rax, [rcx]
0x140005fe4  mov     rax, [rax+10h]
0x140005fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fed  mov     [rsp+2E0h+var_270], r13
0x140005ff2  mov     rcx, [rsp+2E0h+Str]; bstrString
0x140005ff7  test    rcx, rcx
0x140005ffa  jz      short loc_140006007
0x140005ffc  call    cs:__imp_SysFreeString
0x140006002  mov     [rsp+2E0h+Str], r13
0x140006007  mov     rcx, rdi; bstrString
0x14000600a  call    cs:__imp_SysFreeString
0x140006010  inc     esi
0x140006012  cmp     esi, [rsp+2E0h+var_298]
0x140006016  jl      loc_140005EC2
0x14000601c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU> `wil::Feature<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::GetImpl(void)'::`2'::impl
0x140006023  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WUSARebaseMultiMSU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSARebaseMultiMSU>::__private_IsEnabled(void)
0x140006028  test    al, al
0x14000602a  jz      loc_1400060FA
0x140006030  test    r12d, r12d
0x140006033  jz      loc_1400060C1
0x140006039  mov     rcx, [rsp+2E0h+var_2B0]
0x14000603e  lea     r8, [rbp+1E0h+var_258]
0x140006042  lea     rdx, _GUID_08d5fa75_016a_42a5_a9c5_726fc8a0154c
0x140006049  mov     rax, [rcx]
0x14000604c  mov     rax, [rax]
0x14000604f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006054  mov     ebx, eax
0x140006056  cmp     eax, 80004002h
0x14000605b  jz      loc_140006340
0x140006061  test    eax, eax
0x140006063  js      loc_14000632F
0x140006069  mov     rcx, [rbp+1E0h+var_258]
0x14000606d  mov     rdx, [rsp+2E0h+var_2A8]
0x140006072  mov     rax, [rcx]
0x140006075  mov     rax, [rax+0D8h]
0x14000607c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006081  mov     ebx, eax
0x140006083  cmp     eax, 0C1900401h
0x140006088  jz      loc_1400062DC
0x14000608e  cmp     eax, 800F0838h
0x140006093  jz      loc_14000628B
0x140006099  test    eax, eax
0x14000609b  jns     loc_140006129
0x1400060a1  lea     r8, aFailedToEvalua; "Failed to evaluate content applicabilit"...
0x1400060a8  mov     edx, 1D7h
0x1400060ad  mov     r9d, eax
0x1400060b0  lea     rcx, aCopytocache; "CopyToCache"
0x1400060b7  call    WusaLogDebugEventA
0x1400060bc  jmp     loc_1400063D6
0x1400060c1  xor     edx, edx; wParam
0x1400060c3  mov     ecx, 401h; Msg
0x1400060c8  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x1400060cd  mov     rcx, [rsp+2E0h+var_280]
0x1400060d2  mov     rdx, [rsp+2E0h+var_2A8]
0x1400060d7  mov     rax, [rcx]
0x1400060da  mov     rax, [rax+1B8h]
0x1400060e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060e6  mov     ebx, eax
0x1400060e8  test    eax, eax
0x1400060ea  jns     short loc_140006129
0x1400060ec  lea     r8, aFailedToCopyTo; "Failed to copy to cache, error code 0X%"...
0x1400060f3  mov     edx, 1DFh
0x1400060f8  jmp     short loc_1400060AD
0x1400060fa  xor     edx, edx; wParam
0x1400060fc  mov     ecx, 401h; Msg
0x140006101  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x140006106  mov     rcx, [rsp+2E0h+var_280]
0x14000610b  mov     rdx, [rsp+2E0h+var_2A8]
0x140006110  mov     rax, [rcx]
0x140006113  mov     rax, [rax+1B8h]
0x14000611a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000611f  mov     ebx, eax
0x140006121  test    eax, eax
0x140006123  js      loc_14000635D
0x140006129  mov     rcx, [rsp+2E0h+var_2A8]
0x14000612e  test    rcx, rcx
0x140006131  jz      short loc_140006144
0x140006133  mov     rax, [rcx]
0x140006136  mov     rax, [rax+10h]
0x14000613a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000613f  mov     [rsp+2E0h+var_2A8], r13
0x140006144  mov     rcx, [rsp+2E0h+var_280]
0x140006149  test    rcx, rcx
0x14000614c  jz      short loc_14000615F
0x14000614e  mov     rax, [rcx]
0x140006151  mov     rax, [rax+10h]
0x140006155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000615a  mov     [rsp+2E0h+var_280], r13
0x14000615f  mov     rcx, [rsp+2E0h+var_288]
0x140006164  mov     rdi, r13
0x140006167  test    rcx, rcx
  ... truncated ...
```
