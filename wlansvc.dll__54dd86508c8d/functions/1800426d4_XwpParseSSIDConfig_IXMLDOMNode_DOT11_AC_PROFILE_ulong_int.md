# XwpParseSSIDConfig(IXMLDOMNode *,_DOT11_AC_PROFILE *,ulong *,int *)

- ea: `0x1800426d4`
- end: `0x1800431e6`
- name: `?XwpParseSSIDConfig@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_AC_PROFILE@@PEAKPEAH@Z`
- size: `2834`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct _DOT11_AC_PROFILE *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180041ad4`
- `0x1801b3814`

## callees

- `0x180023750`
- `0x1800248e4`
- `0x180040f20`
- `0x1800426d4`
- `0x18004406c`
- `0x180080824`
- `0x180107318`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004309c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004309c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180042d4c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180042d4c`
- `OLEAUT32!__imp_SysAllocString` at `0x18004274e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800427d7`
- `OLEAUT32!__imp_SysAllocString` at `0x180042898`
- `OLEAUT32!__imp_SysAllocString` at `0x180042941`
- `OLEAUT32!__imp_SysAllocString` at `0x180042b29`
- `OLEAUT32!__imp_SysAllocString` at `0x180042bee`
- `OLEAUT32!__imp_SysAllocString` at `0x18004274e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800427d7`
- `OLEAUT32!__imp_SysAllocString` at `0x180042898`
- `OLEAUT32!__imp_SysAllocString` at `0x180042941`
- `OLEAUT32!__imp_SysAllocString` at `0x180042b29`
- `OLEAUT32!__imp_SysAllocString` at `0x180042bee`
- `OLEAUT32!__imp_SysFreeString` at `0x180042741`
- `OLEAUT32!__imp_SysFreeString` at `0x180042772`
- `OLEAUT32!__imp_SysFreeString` at `0x1800427a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800427ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800427eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004285f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004288b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800428ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180042920`
- `OLEAUT32!__imp_SysFreeString` at `0x180042934`
- `OLEAUT32!__imp_SysFreeString` at `0x180042955`
- `OLEAUT32!__imp_SysFreeString` at `0x180042987`
- `OLEAUT32!__imp_SysFreeString` at `0x180042b1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042b3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180042bb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180042be1`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c02`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180042741`
- `OLEAUT32!__imp_SysFreeString` at `0x180042772`
- `OLEAUT32!__imp_SysFreeString` at `0x1800427a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800427ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800427eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004285f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004288b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800428ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180042920`
- `OLEAUT32!__imp_SysFreeString` at `0x180042934`
- `OLEAUT32!__imp_SysFreeString` at `0x180042955`
- `OLEAUT32!__imp_SysFreeString` at `0x180042987`
- `OLEAUT32!__imp_SysFreeString` at `0x180042b1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180042b3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180042bb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180042be1`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c02`
- `OLEAUT32!__imp_SysFreeString` at `0x180042c6e`
- `OLEAUT32!__imp_VariantInit` at `0x180042bc7`
- `OLEAUT32!__imp_VariantInit` at `0x180042bc7`
- `OLEAUT32!__imp_VariantClear` at `0x180042d70`
- `OLEAUT32!__imp_VariantClear` at `0x180042d70`

## string_xrefs

- `0x180042747`: `WLANProfile:SSIDConfig`
- `0x1800427d0`: `WLANProfile:SSID`
- `0x180042891`: `WLANProfileV2:SSID`
- `0x18004293a`: `WLANProfileV2:SSIDBinaryList`
- `0x18004304a`: `WLANProfileV2:SSIDBinaryList`
- `0x180042b22`: `WLANProfileV2:SSIDPrefix`

## pseudocode

```c
__int64 __fastcall XwpParseSSIDConfig(struct IXMLDOMNode *a1, struct _DOT11_AC_PROFILE *a2, unsigned int *a3, int *a4)
{
  SIZE_T v5; // r14
  void *v6; // r15
  OLECHAR *v7; // rbx
  int v8; // esi
  int v9; // eax
  unsigned int NodeHexBinaryValue; // edi
  int v11; // r12d
  struct IXMLDOMNode *v12; // rdi
  OLECHAR *v13; // rbx
  int v14; // eax
  int v15; // eax
  _DWORD *v16; // rcx
  int v17; // r14d
  int v18; // r15d
  struct IXMLDOMNode *v19; // rdi
  OLECHAR *v20; // rbx
  int v21; // eax
  int v22; // edi
  int v23; // eax
  _DWORD *v24; // rcx
  struct IXMLDOMNode *v25; // rdi
  OLECHAR *v26; // rbx
  int v27; // eax
  int v28; // edi
  signed int v29; // ebx
  unsigned __int64 v30; // rax
  _DWORD *v32; // rax
  int v33; // r13d
  _DWORD *v34; // r12
  int v35; // r14d
  struct IXMLDOMNode *v36; // rdi
  OLECHAR *v37; // rbx
  int v38; // eax
  int v39; // edi
  int v40; // eax
  _DWORD *v41; // rcx
  struct IXMLDOMNode *v42; // r15
  _DWORD *v43; // rbx
  int v44; // r14d
  OLECHAR *v45; // rdi
  int v46; // eax
  int v47; // eax
  _DWORD *v48; // rcx
  int v49; // eax
  int v50; // eax
  int v51; // r15d
  int v52; // r14d
  unsigned int j; // ebx
  _DWORD *v54; // rax
  DWORD LastError; // eax
  __int64 i; // rcx
  int v57; // edx
  unsigned int v58; // ecx
  __int64 v59; // r14
  __int64 v60; // rbx
  unsigned int v61; // r15d
  unsigned __int8 *v62; // r9
  unsigned int v63; // edi
  int v64; // ebx
  __int64 v65; // rcx
  _DWORD *v66; // [rsp+48h] [rbp-79h] BYREF
  _DWORD *v67; // [rsp+50h] [rbp-71h] BYREF
  _DWORD *v68; // [rsp+58h] [rbp-69h]
  int v69; // [rsp+60h] [rbp-61h] BYREF
  struct IXMLDOMNode *v70; // [rsp+68h] [rbp-59h] BYREF
  int v71; // [rsp+70h] [rbp-51h] BYREF
  unsigned int v72[2]; // [rsp+78h] [rbp-49h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp-41h] BYREF
  void *lpMem; // [rsp+88h] [rbp-39h]
  unsigned __int8 *v75; // [rsp+90h] [rbp-31h] BYREF
  SIZE_T v76; // [rsp+98h] [rbp-29h]
  _DWORD *v77; // [rsp+A0h] [rbp-21h]
  _DWORD *v78; // [rsp+A8h] [rbp-19h]
  __int64 v79; // [rsp+B0h] [rbp-11h] BYREF
  _DWORD *v80; // [rsp+B8h] [rbp-9h]
  _DWORD *v81; // [rsp+C0h] [rbp-1h]
  SIZE_T v82; // [rsp+C8h] [rbp+7h]
  VARIANTARG pvarg; // [rsp+D0h] [rbp+Fh] BYREF

  v70 = 0;
  v78 = 0;
  v80 = 0;
  v77 = 0;
  v81 = 0;
  v79 = 0;
  v5 = 0;
  v76 = 0;
  v82 = 0;
  v71 = 1;
  v69 = 0;
  lpMem = 0;
  v6 = 0;
  v68 = 0;
  v75 = 0;
  v72[0] = 0;
  SysFreeString(0);
  v7 = SysAllocString(L"WLANProfile:SSIDConfig");
  v8 = 14;
  if ( v7 )
  {
    SysFreeString(0);
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, struct IXMLDOMNode **))a1->lpVtbl->selectSingleNode)(
           a1,
           v7,
           &v70);
    NodeHexBinaryValue = v9;
    if ( v9 == 1 )
    {
      NodeHexBinaryValue = 1168;
    }
    else if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        NodeHexBinaryValue = (unsigned __int16)v9;
    }
    else
    {
      NodeHexBinaryValue = 0;
    }
  }
  else
  {
    v7 = 0;
    NodeHexBinaryValue = 14;
  }
  SysFreeString(v7);
  if ( NodeHexBinaryValue == 1168 )
    goto LABEL_138;
  if ( NodeHexBinaryValue )
    goto LABEL_36;
  v11 = 0;
  v12 = v70;
  v66 = 0;
  LODWORD(v67) = 0;
  SysFreeString(0);
  v13 = SysAllocString(L"WLANProfile:SSID");
  if ( v13 )
  {
    SysFreeString(0);
    v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, _DWORD **))v12->lpVtbl->selectNodes)(v12, v13, &v66);
    NodeHexBinaryValue = v14;
    if ( v14 < 0 )
    {
      if ( (v14 & 0x1FFF0000) == 0x70000 )
        NodeHexBinaryValue = (unsigned __int16)v14;
      if ( NodeHexBinaryValue )
        goto LABEL_112;
    }
    v15 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD **))(*(_QWORD *)v66 + 64LL))(v66, &v67);
    NodeHexBinaryValue = v15;
    if ( v15 >= 0 )
    {
      NodeHexBinaryValue = 0;
LABEL_10:
      v78 = v66;
      v16 = 0;
      v66 = 0;
      v80 = v78;
      v11 = (int)v67;
      goto LABEL_11;
    }
    if ( (v15 & 0x1FFF0000) == 0x70000 )
      NodeHexBinaryValue = (unsigned __int16)v15;
    if ( !NodeHexBinaryValue )
      goto LABEL_10;
  }
  else
  {
    v13 = 0;
    NodeHexBinaryValue = 14;
  }
LABEL_112:
  v16 = v66;
LABEL_11:
  if ( v16 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 16LL))(v16);
  SysFreeString(v13);
  if ( NodeHexBinaryValue )
    goto LABEL_92;
  if ( v11 < 1 )
  {
LABEL_138:
    NodeHexBinaryValue = 1206;
    goto LABEL_36;
  }
  v17 = 0;
  v18 = 0;
  v19 = v70;
  v66 = 0;
  LODWORD(v67) = 0;
  SysFreeString(0);
  v20 = SysAllocString(L"WLANProfileV2:SSID");
  if ( v20 )
  {
    SysFreeString(0);
    v21 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, _DWORD **))v19->lpVtbl->selectNodes)(v19, v20, &v66);
    v22 = v21;
    if ( v21 < 0 )
    {
      if ( (v21 & 0x1FFF0000) == 0x70000 )
        v22 = (unsigned __int16)v21;
      if ( v22 )
        goto LABEL_114;
    }
    v23 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD **))(*(_QWORD *)v66 + 64LL))(v66, &v67);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v22 = 0;
LABEL_19:
      v77 = v66;
      v24 = 0;
      v66 = 0;
      v81 = v77;
      v17 = (int)v67;
      goto LABEL_20;
    }
    if ( (v23 & 0x1FFF0000) == 0x70000 )
      v22 = (unsigned __int16)v23;
    if ( !v22 )
      goto LABEL_19;
  }
  else
  {
    v20 = 0;
    v22 = 14;
  }
LABEL_114:
  v24 = v66;
LABEL_20:
  if ( v24 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v24 + 16LL))(v24);
  SysFreeString(v20);
  if ( v22 )
    v17 = 0;
  v25 = v70;
  SysFreeString(0);
  v26 = SysAllocString(L"WLANProfileV2:SSIDBinaryList");
  if ( v26 )
  {
    SysFreeString(0);
    v27 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, __int64 *))v25->lpVtbl->selectSingleNode)(
            v25,
            v26,
            &v79);
    v28 = v27;
    if ( v27 == 1 )
    {
      v28 = 1168;
    }
    else if ( v27 < 0 )
    {
      if ( (v27 & 0x1FFF0000) == 0x70000 )
        v28 = (unsigned __int16)v27;
    }
    else
    {
      v28 = 0;
    }
  }
  else
  {
    v26 = 0;
    v28 = 14;
  }
  SysFreeString(v26);
  if ( !v28 )
  {
    NodeHexBinaryValue = XcGetNodeHexBinaryValue(v70, L"WLANProfileV2:SSIDBinaryList", &v75, v72);
    if ( NodeHexBinaryValue )
      goto LABEL_33;
    for ( i = 0; (unsigned int)i < v72[0]; i = v58 + 1 )
    {
      v57 = v75[i];
      if ( (unsigned int)(v57 - 1) > 0x1F || (v58 = v57 + i, v58 >= v72[0]) )
      {
        NodeHexBinaryValue = 1206;
        goto LABEL_33;
      }
      ++v18;
    }
  }
  v29 = v11 + v18 + v17;
  if ( (unsigned int)v29 > 0x2810 )
    goto LABEL_165;
  dwBytes = 0;
  v30 = 36LL * v29;
  if ( is_mul_ok(v29, 0x24u) && v30 < 0xFFFFFFFFFFFFFFF4uLL )
  {
    dwBytes = v30 + 12;
    v32 = Xc_Process_user_allocate(v30 + 12);
    lpMem = v32;
    v67 = v32;
    if ( !v32 )
    {
      LastError = GetLastError();
      v6 = v68;
LABEL_32:
      NodeHexBinaryValue = LastError;
      if ( !LastError )
        goto LABEL_33;
LABEL_92:
      if ( lpMem )
        Xc_Process_user_free(lpMem);
      if ( v6 )
        Xc_Process_user_free(v6);
      goto LABEL_33;
    }
    *v32 = 3146112;
    v32[1] = v29;
    v32[2] = v29;
    v66 = v78;
    if ( v78 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v78 + 8LL))(v78);
    NodeHexBinaryValue = XwpParseSSIDConfigSSIDNodes(
                           v11,
                           (unsigned int)&v66,
                           (unsigned int)&v67,
                           0,
                           1,
                           (__int64)a3,
                           (__int64)&v71);
    if ( NodeHexBinaryValue )
      goto LABEL_91;
    if ( v17 > 0 )
    {
      v66 = v77;
      if ( v77 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v77 + 8LL))(v77);
      NodeHexBinaryValue = XwpParseSSIDConfigSSIDNodes(
                             v17,
                             (unsigned int)&v66,
                             (unsigned int)&v67,
                             v11,
                             0,
                             (__int64)a3,
                             (__int64)&v69);
      if ( NodeHexBinaryValue )
        goto LABEL_91;
      v33 = v69 & v71;
    }
    else
    {
      v33 = v71;
    }
    if ( v18 > 0 )
    {
      v59 = (unsigned int)(v11 + v17);
      v60 = 0;
      v61 = v72[0];
      v34 = lpMem;
      while ( (unsigned int)v60 < v61 )
      {
        v62 = v75;
        v63 = v75[v60];
        if ( v63 - 1 > 0x1F || v63 + (unsigned int)v60 >= v61 )
          goto LABEL_165;
        v64 = v60 + 1;
        v65 = 9 * v59;
        v59 = (unsigned int)(v59 + 1);
        v34[v65 + 3] = v63;
        memcpy_0(&v34[v65 + 4], &v62[v64], v63);
        v60 = v63 + v64;
      }
    }
    else
    {
      v34 = lpMem;
    }
    v35 = 0;
    v36 = v70;
    v66 = 0;
    LODWORD(v67) = 0;
    SysFreeString(0);
    v37 = SysAllocString(L"WLANProfileV2:SSIDPrefix");
    if ( v37 )
    {
      SysFreeString(0);
      v38 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, _DWORD **))v36->lpVtbl->selectNodes)(
              v36,
              v37,
              &v66);
      v39 = v38;
      if ( v38 < 0 )
      {
        if ( (v38 & 0x1FFF0000) == 0x70000 )
          v39 = (unsigned __int16)v38;
        if ( v39 )
          goto LABEL_116;
      }
      v40 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD **))(*(_QWORD *)v66 + 64LL))(v66, &v67);
      v39 = v40;
      if ( v40 >= 0 )
      {
        v39 = 0;
LABEL_59:
        v76 = (SIZE_T)v66;
        v41 = 0;
        v66 = 0;
        v82 = v76;
        v35 = (int)v67;
        goto LABEL_60;
      }
      if ( (v40 & 0x1FFF0000) == 0x70000 )
        v39 = (unsigned __int16)v40;
      if ( !v39 )
        goto LABEL_59;
    }
    else
    {
      v37 = 0;
      v39 = 14;
    }
LABEL_116:
    v41 = v66;
LABEL_60:
    if ( v41 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v41 + 16LL))(v41);
    SysFreeString(v37);
    if ( v39 || v35 <= 0 )
      goto LABEL_63;
    if ( (unsigned int)v35 <= 0x20 )
    {
      NodeHexBinaryValue = VariableListSize(0xCu, v35, 0x24u, &dwBytes);
      if ( !NodeHexBinaryValue )
      {
        v54 = Xc_Process_user_allocate(dwBytes);
        v6 = v54;
        v68 = v54;
        v66 = v54;
        if ( !v54 )
        {
          LastError = GetLastError();
          goto LABEL_32;
        }
        *v54 = 3146112;
        v54[1] = v35;
        v54[2] = v35;
        dwBytes = v76;
        if ( v76 )
          (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)v76 + 8LL))(v76);
        NodeHexBinaryValue = XwpParseSSIDConfigSSIDNodes(
                               v35,
                               (unsigned int)&dwBytes,
                               (unsigned int)&v66,
                               0,
                               0,
                               (__int64)a3,
                               (__int64)&v69);
        if ( NodeHexBinaryValue )
          goto LABEL_92;
        v33 &= v69;
LABEL_63:
        v42 = v70;
        VariantInit(&pvarg);
        *(_QWORD *)v72 = 0;
        v43 = 0;
        v44 = 0;
        v66 = 0;
        LODWORD(v67) = 0;
        SysFreeString(0);
        v45 = SysAllocString(L"WLANProfile:nonBroadcast");
        if ( v45 )
        {
          SysFreeString(0);
          v46 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, _DWORD **))v42->lpVtbl->selectNodes)(
                  v42,
                  v45,
                  &v66);
          v8 = v46;
          if ( v46 < 0 )
          {
            if ( (v46 & 0x1FFF0000) == 0x70000 )
              v8 = (unsigned __int16)v46;
            if ( v8 )
              goto LABEL_118;
          }
          v47 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD **))(*(_QWORD *)v66 + 64LL))(v66, &v67);
          v8 = v47;
          if ( v47 >= 0 )
          {
            v8 = 0;
LABEL_67:
            v43 = v66;
            v48 = 0;
            v66 = 0;
            v44 = (int)v67;
            goto LABEL_68;
          }
          if ( (v47 & 0x1FFF0000) == 0x70000 )
            v8 = (unsigned __int16)v47;
          if ( !v8 )
            goto LABEL_67;
        }
        else
        {
          v45 = 0;
        }
LABEL_118:
        v48 = v66;
LABEL_68:
        if ( v48 )
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v48 + 16LL))(v48);
        SysFreeString(v45);
        NodeHexBinaryValue = 1206;
        if ( !v8 )
        {
          if ( v44 <= 0 )
          {
            v8 = 1168;
          }
          else if ( v44 > 1 )
          {
            v8 = 1206;
          }
          else
          {
            v49 = (*(__int64 (__fastcall **)(_DWORD *, _QWORD, unsigned int *))(*(_QWORD *)v43 + 56LL))(v43, 0, v72);
            v8 = v49;
            if ( v49 < 0 )
            {
              if ( (v49 & 0x1FFF0000) == 0x70000 )
                v8 = (unsigned __int16)v49;
            }
            else
            {
              v8 = 0;
            }
          }
        }
        if ( v43 )
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v43 + 16LL))(v43);
        if ( !v8 )
        {
          v50 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *))(**(_QWORD **)v72 + 240LL))(*(_QWORD *)v72, &pvarg);
          if ( v50 < 0 )
          {
            v8 = (unsigned __int16)v50;
            if ( (v50 & 0x1FFF0000) != 0x70000 )
              v8 = v50;
          }
          else if ( pvarg.vt != 8 || !pvarg.llVal )
          {
            v8 = 1168;
          }
        }
        if ( *(_QWORD *)v72 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v72 + 16LL))(*(_QWORD *)v72);
        v51 = 0;
        if ( v8 == 1168 )
        {
          NodeHexBinaryValue = 0;
          v52 = 0;
        }
        else
        {
          v52 = 0;
          if ( v8 )
          {
            NodeHexBinaryValue = v8;
          }
          else
          {
            for ( j = 0; j < 4; ++j )
            {
              if ( !lstrcmpW((&off_18022D000)[2 * j], pvarg.bstrVal) )
              {
                v51 = *((_DWORD *)&off_18022D000 + 4 * j + 2);
                NodeHexBinaryValue = 0;
                v52 = 1;
                break;
              }
            }
          }
        }
        VariantClear(&pvarg);
        if ( !NodeHexBinaryValue )
        {
          if ( v52 )
          {
            *((_DWORD *)a2 + 1) |= 4u;
            if ( v51 )
              *((_DWORD *)a2 + 6) |= 2u;
          }
          *((_QWORD *)a2 + 1) = v34;
          *((_QWORD *)a2 + 5) = v68;
          if ( a4 )
            *a4 = v33;
          goto LABEL_33;
        }
      }
LABEL_91:
      v6 = v68;
      goto LABEL_92;
    }
LABEL_165:
    NodeHexBinaryValue = 1206;
    goto LABEL_91;
  }
  NodeHexBinaryValue = 534;
LABEL_33:
  if ( v75 )
    Xc_Process_user_free(v75);
  v5 = v76;
LABEL_36:
  if ( v5 )
    (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v79 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  if ( v77 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v77 + 16LL))(v77);
  if ( v78 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v78 + 16LL))(v78);
  if ( v70 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v70->lpVtbl->Release)(v70);
  return NodeHexBinaryValue;
}

```

## disassembly

```asm
0x1800426d4  mov     rax, rsp
0x1800426d7  mov     [rax+8], rbx
0x1800426db  mov     [rax+20h], r9
0x1800426df  mov     [rax+18h], r8
0x1800426e3  mov     [rax+10h], rdx
0x1800426e7  push    rbp
0x1800426e8  push    rsi
0x1800426e9  push    rdi
0x1800426ea  push    r12
0x1800426ec  push    r13
0x1800426ee  push    r14
0x1800426f0  push    r15
0x1800426f2  lea     rbp, [rax-5Fh]
0x1800426f6  sub     rsp, 0E0h
0x1800426fd  mov     rdi, rcx
0x180042700  xor     ecx, ecx; bstrString
0x180042702  mov     [rbp+57h+var_B0], rcx
0x180042706  mov     [rbp+57h+var_70], rcx
0x18004270a  mov     [rbp+57h+var_60], rcx
0x18004270e  mov     [rbp+57h+var_78], rcx
0x180042712  mov     [rbp+57h+var_58], rcx
0x180042716  mov     [rbp+57h+var_68], rcx
0x18004271a  mov     r14d, ecx
0x18004271d  mov     [rbp+57h+var_80], rcx
0x180042721  mov     [rbp+57h+var_50], rcx
0x180042725  mov     [rbp+57h+var_A8], 1
0x18004272c  mov     [rbp+57h+var_B8], ecx
0x18004272f  mov     [rbp+57h+lpMem], rcx
0x180042733  mov     r15d, ecx
0x180042736  mov     [rbp+57h+var_C0], rcx
0x18004273a  mov     [rbp+57h+var_88], rcx
0x18004273e  mov     [rbp+57h+var_A0], ecx
0x180042741  call    cs:__imp_SysFreeString
0x180042747  lea     rcx, aWlanprofileSsi; "WLANProfile:SSIDConfig"
0x18004274e  call    cs:__imp_SysAllocString
0x180042754  mov     rbx, rax
0x180042757  lea     esi, [r15+0Eh]
0x18004275b  mov     r13d, 1FFF0000h
0x180042761  mov     r12d, 490h
0x180042767  test    rax, rax
0x18004276a  jz      loc_180042FA3
0x180042770  xor     ecx, ecx; bstrString
0x180042772  call    cs:__imp_SysFreeString
0x180042778  mov     rax, [rdi]
0x18004277b  lea     r8, [rbp+57h+var_B0]
0x18004277f  mov     rdx, rbx
0x180042782  mov     rcx, rdi
0x180042785  mov     rax, [rax+128h]
0x18004278c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042791  mov     edi, eax
0x180042793  cmp     eax, 1
0x180042796  jnz     loc_180042E10
0x18004279c  mov     edi, r12d
0x18004279f  mov     rcx, rbx; bstrString
0x1800427a2  call    cs:__imp_SysFreeString
0x1800427a8  cmp     edi, r12d
0x1800427ab  jz      loc_180042FAC
0x1800427b1  test    edi, edi
0x1800427b3  jnz     loc_1800429F0
0x1800427b9  xor     r12d, r12d
0x1800427bc  mov     rdi, [rbp+57h+var_B0]
0x1800427c0  mov     [rbp+57h+var_D0], r12
0x1800427c4  mov     dword ptr [rbp+57h+var_C8], r12d
0x1800427c8  xor     ecx, ecx; bstrString
0x1800427ca  call    cs:__imp_SysFreeString
0x1800427d0  lea     rcx, aWlanprofileSsi_0; "WLANProfile:SSID"
0x1800427d7  call    cs:__imp_SysAllocString
0x1800427dd  mov     rbx, rax
0x1800427e0  test    rax, rax
0x1800427e3  jz      loc_180042FE2
0x1800427e9  xor     ecx, ecx; bstrString
0x1800427eb  call    cs:__imp_SysFreeString
0x1800427f1  mov     rax, [rdi]
0x1800427f4  lea     r8, [rbp+57h+var_D0]
0x1800427f8  mov     rdx, rbx
0x1800427fb  mov     rcx, rdi
0x1800427fe  mov     rax, [rax+120h]
0x180042805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004280a  mov     edi, eax
0x18004280c  test    eax, eax
0x18004280e  js      loc_180042FB6
0x180042814  mov     rcx, [rbp+57h+var_D0]
0x180042818  mov     rax, [rcx]
0x18004281b  lea     rdx, [rbp+57h+var_C8]
0x18004281f  mov     rax, [rax+40h]
0x180042823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042828  mov     edi, eax
0x18004282a  test    eax, eax
0x18004282c  js      loc_180042FCC
0x180042832  xor     edi, edi
0x180042834  mov     rax, [rbp+57h+var_D0]
0x180042838  mov     [rbp+57h+var_70], rax
0x18004283c  xor     ecx, ecx
0x18004283e  mov     [rbp+57h+var_D0], rcx
0x180042842  mov     [rbp+57h+var_60], rax
0x180042846  mov     r12d, dword ptr [rbp+57h+var_C8]
0x18004284a  test    rcx, rcx
0x18004284d  jz      short loc_18004285C
0x18004284f  mov     rax, [rcx]
0x180042852  mov     rax, [rax+10h]
0x180042856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004285b  nop
0x18004285c  mov     rcx, rbx; bstrString
0x18004285f  call    cs:__imp_SysFreeString
0x180042865  test    edi, edi
0x180042867  jnz     loc_180042D82
0x18004286d  cmp     r12d, 1
0x180042871  jl      loc_180042FAC
0x180042877  xor     r14d, r14d
0x18004287a  xor     r15d, r15d
0x18004287d  mov     rdi, [rbp+57h+var_B0]
0x180042881  mov     [rbp+57h+var_D0], r14
0x180042885  mov     dword ptr [rbp+57h+var_C8], r14d
0x180042889  xor     ecx, ecx; bstrString
0x18004288b  call    cs:__imp_SysFreeString
0x180042891  lea     rcx, aWlanprofilev2S_1; "WLANProfileV2:SSID"
0x180042898  call    cs:__imp_SysAllocString
0x18004289e  mov     rbx, rax
0x1800428a1  test    rax, rax
0x1800428a4  jz      loc_18004301A
0x1800428aa  xor     ecx, ecx; bstrString
0x1800428ac  call    cs:__imp_SysFreeString
0x1800428b2  mov     rax, [rdi]
0x1800428b5  lea     r8, [rbp+57h+var_D0]
0x1800428b9  mov     rdx, rbx
0x1800428bc  mov     rcx, rdi
0x1800428bf  mov     rax, [rax+120h]
0x1800428c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428cb  mov     edi, eax
0x1800428cd  test    eax, eax
0x1800428cf  js      loc_180042FEB
0x1800428d5  mov     rcx, [rbp+57h+var_D0]
0x1800428d9  mov     rax, [rcx]
0x1800428dc  lea     rdx, [rbp+57h+var_C8]
0x1800428e0  mov     rax, [rax+40h]
0x1800428e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428e9  mov     edi, eax
0x1800428eb  test    eax, eax
0x1800428ed  js      loc_180043004
0x1800428f3  xor     edi, edi
0x1800428f5  mov     rax, [rbp+57h+var_D0]
0x1800428f9  mov     [rbp+57h+var_78], rax
0x1800428fd  xor     ecx, ecx
0x1800428ff  mov     [rbp+57h+var_D0], rcx
0x180042903  mov     [rbp+57h+var_58], rax
0x180042907  mov     r14d, dword ptr [rbp+57h+var_C8]
0x18004290b  test    rcx, rcx
0x18004290e  jz      short loc_18004291D
0x180042910  mov     rax, [rcx]
0x180042913  mov     rax, [rax+10h]
0x180042917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004291c  nop
0x18004291d  mov     rcx, rbx; bstrString
0x180042920  call    cs:__imp_SysFreeString
0x180042926  xor     eax, eax
0x180042928  test    edi, edi
0x18004292a  cmovnz  r14d, eax
0x18004292e  mov     rdi, [rbp+57h+var_B0]
0x180042932  xor     ecx, ecx; bstrString
0x180042934  call    cs:__imp_SysFreeString
0x18004293a  lea     rcx, aWlanprofilev2S; "WLANProfileV2:SSIDBinaryList"
0x180042941  call    cs:__imp_SysAllocString
0x180042947  mov     rbx, rax
0x18004294a  test    rax, rax
0x18004294d  jz      loc_180043039
0x180042953  xor     ecx, ecx; bstrString
0x180042955  call    cs:__imp_SysFreeString
0x18004295b  mov     rax, [rdi]
0x18004295e  lea     r8, [rbp+57h+var_68]
0x180042962  mov     rdx, rbx
0x180042965  mov     rcx, rdi
0x180042968  mov     rax, [rax+128h]
0x18004296f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042974  mov     edi, eax
0x180042976  cmp     eax, 1
0x180042979  jnz     loc_180042E1F
0x18004297f  mov     edi, 490h
0x180042984  mov     rcx, rbx; bstrString
0x180042987  call    cs:__imp_SysFreeString
0x18004298d  test    edi, edi
0x18004298f  jz      loc_180043042
0x180042995  lea     ebx, [r15+r14]
0x180042999  add     ebx, r12d
0x18004299c  cmp     ebx, 2810h
0x1800429a2  ja      loc_180043101
0x1800429a8  mov     [rbp+57h+dwBytes], 0
0x1800429b0  movsxd  rcx, ebx
0x1800429b3  mov     eax, 24h ; '$'
0x1800429b8  mul     rcx
0x1800429bb  test    rdx, rdx
0x1800429be  jnz     short loc_1800429CE
0x1800429c0  lea     rcx, [rax+0Ch]; dwBytes
0x1800429c4  cmp     rcx, 0Ch
0x1800429c8  jnb     loc_180042A7A
0x1800429ce  mov     edi, 216h
0x1800429d3  jmp     short loc_1800429DF
0x1800429d5  mov     edi, eax
0x1800429d7  test    eax, eax
0x1800429d9  jnz     loc_180042D82
0x1800429df  mov     rax, [rbp+57h+var_88]
0x1800429e3  test    rax, rax
0x1800429e6  jnz     loc_1800431D8
0x1800429ec  mov     r14, [rbp+57h+var_80]
0x1800429f0  test    r14, r14
0x1800429f3  jz      short loc_180042A05
0x1800429f5  mov     rax, [r14]
0x1800429f8  mov     rcx, r14
0x1800429fb  mov     rax, [rax+10h]
0x1800429ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a04  nop
0x180042a05  mov     rcx, [rbp+57h+var_68]
0x180042a09  test    rcx, rcx
0x180042a0c  jz      short loc_180042A1B
0x180042a0e  mov     rax, [rcx]
0x180042a11  mov     rax, [rax+10h]
0x180042a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a1a  nop
0x180042a1b  mov     rcx, [rbp+57h+var_78]
0x180042a1f  test    rcx, rcx
0x180042a22  jz      short loc_180042A31
0x180042a24  mov     rax, [rcx]
0x180042a27  mov     rax, [rax+10h]
0x180042a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a30  nop
0x180042a31  mov     rcx, [rbp+57h+var_70]
0x180042a35  test    rcx, rcx
0x180042a38  jz      short loc_180042A47
0x180042a3a  mov     rax, [rcx]
0x180042a3d  mov     rax, [rax+10h]
0x180042a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a46  nop
0x180042a47  mov     rcx, [rbp+57h+var_B0]
0x180042a4b  test    rcx, rcx
0x180042a4e  jz      short loc_180042A5D
0x180042a50  mov     rax, [rcx]
0x180042a53  mov     rax, [rax+10h]
0x180042a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a5c  nop
0x180042a5d  mov     eax, edi
0x180042a5f  mov     rbx, [rsp+110h+arg_0]
0x180042a67  add     rsp, 0E0h
0x180042a6e  pop     r15
0x180042a70  pop     r14
0x180042a72  pop     r13
0x180042a74  pop     r12
0x180042a76  pop     rdi
0x180042a77  pop     rsi
0x180042a78  pop     rbp
0x180042a79  retn
0x180042a7a  mov     [rbp+57h+dwBytes], rcx
0x180042a7e  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180042a83  mov     [rbp+57h+lpMem], rax
0x180042a87  mov     [rbp+57h+var_C8], rax
0x180042a8b  test    rax, rax
0x180042a8e  jz      loc_18004309C
0x180042a94  mov     dword ptr [rax], 300180h
0x180042a9a  mov     [rax+4], ebx
0x180042a9d  mov     [rax+8], ebx
0x180042aa0  mov     rcx, [rbp+57h+var_70]
0x180042aa4  mov     [rbp+57h+var_D0], rcx
0x180042aa8  test    rcx, rcx
0x180042aab  jz      short loc_180042ABA
0x180042aad  mov     rax, [rcx]
0x180042ab0  mov     rax, [rax+8]
0x180042ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ab9  nop
0x180042aba  lea     rax, [rbp+57h+var_A8]
0x180042abe  mov     [rsp+30h], rax
0x180042ac3  mov     rbx, [rbp+57h+arg_10]
0x180042ac7  mov     [rsp+110h+var_E8], rbx
0x180042acc  mov     dword ptr [rsp+110h+var_F0], 1
0x180042ad4  xor     r9d, r9d
0x180042ad7  lea     r8, [rbp+57h+var_C8]
0x180042adb  lea     rdx, [rbp+57h+var_D0]
0x180042adf  mov     ecx, r12d
0x180042ae2  call    ?XwpParseSSIDConfigSSIDNodes@@YAKKV?$CComPtr@UIXMLDOMNodeList@@@ATL@@PEAPEAUDOT11_SSID_LIST@@KHPEAKPEAH@Z; XwpParseSSIDConfigSSIDNodes(ulong,ATL::CComPtr<IXMLDOMNodeList>,DOT11_SSID_LIST * *,ulong,int,ulong *,int *)
0x180042ae7  mov     edi, eax
0x180042ae9  test    eax, eax
0x180042aeb  jnz     loc_180042D7E
0x180042af1  test    r14d, r14d
0x180042af4  jg      loc_180042ECB
0x180042afa  mov     r13d, [rbp+57h+var_A8]
0x180042afe  test    r15d, r15d
0x180042b01  jg      loc_1800430AB
0x180042b07  mov     r12, [rbp+57h+lpMem]
0x180042b0b  xor     r14d, r14d
0x180042b0e  mov     rdi, [rbp+57h+var_B0]
0x180042b12  mov     [rbp+57h+var_D0], r14
0x180042b16  mov     dword ptr [rbp+57h+var_C8], r14d
0x180042b1a  xor     ecx, ecx; bstrString
0x180042b1c  call    cs:__imp_SysFreeString
0x180042b22  lea     rcx, aWlanprofilev2S_0; "WLANProfileV2:SSIDPrefix"
0x180042b29  call    cs:__imp_SysAllocString
0x180042b2f  mov     rbx, rax
0x180042b32  test    rax, rax
0x180042b35  jz      loc_18004313F
0x180042b3b  xor     ecx, ecx; bstrString
0x180042b3d  call    cs:__imp_SysFreeString
0x180042b43  mov     rax, [rdi]
0x180042b46  lea     r8, [rbp+57h+var_D0]
  ... truncated ...
```
